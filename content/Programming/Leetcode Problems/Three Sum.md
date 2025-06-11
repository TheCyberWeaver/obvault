[15. 3Sum](https://leetcode.com/problems/3sum/)
Given an integer array nums, return all the triplets `[nums[i], nums[j], nums[k]]` such that `i != j`, `i != k`, and `j != k`, and `nums[i] + nums[j] + nums[k] == 0`.

Notice that the solution set must not contain duplicate triplets.

题目目测可以找到$O(n^2)$ 复杂度的解法。
重点在于如何去除重复triplets：
- 遍历前两个元素并利用set可以达到$O(n^2logn)$ 的复杂度。
- 无论如何可以先排序，$O(nlogn)$的复杂度完全可以忽略
- 容易想到遍历前两个元素，并用hashmap寻找第三个元素
- 使用hashmap需要着重考虑怎么排除重复triplets
### 方法一  Hashmap
利用hashmap， 本身找第三个元素并不需要hashmap的value部分，但用hashmap去重是个麻烦的问题，我们可以用hashmap存储元素最后出现的index 。这样只需要判断第三个元素的index是否大于第二个index即可保证无重复

```cpp fold:implementation
vector<vector<int>> answer;
for(int i = 0 ; i < nums.size() - 2 ; ++i){
	if(nums[i] > 0){     //这条让排名从50%上升到80%
		break;
	}
	for(int j = i + 1 ; j < nums.size() - 1 ; ++j){
		int required = -1*(nums[i] + nums[j]);
		if(hashMap.count(required) && hashMap.find(required)->second > j){ 
		//If it exists in hashmap and its last occurrence index > 2nd fixed index, we found our triplet.
			answer.push_back({nums[i] , nums[j] , required});
		}
		j = hashMap.find(nums[j])->second; //Update j to last occurence of 2nd fixed number to avoid duplicate triplets.
	}
	i = hashMap.find(nums[i])->second;     //Update i to last occurence of 1st fixed number to avoid duplicate triplets.
}
```
### 方法二 [[Two Pointers]]
看到答案才意识到双指针的用法。同样遍历第一个元素，二三元素使用双指针。由于提前排序，可以通过移动上下界使得和逐渐逼近0。同样由于排序，一样的元素在一块，当发现双指针和上一个指向的位置一样的时候直接跳过就好了，对于第一个元素的遍历同理。由于元素是排好序的，且指针$i<l<r$ ，所以只要保证没有triplet被跳过即可。
如果triplet有元素相同，有两种情况：
- $a=b<c$ 
- $a< b=c$ 
- $0=0=0$
三种情况都至少会被处理一次均不需要特殊处理

```cpp fold:implementation
sort(nums.begin(), nums.end());
    for (int i = 0; i < n - 1; i++) {
      int l = i + 1, r = n - 1;
      while (l < r) {
        if (nums[i] + nums[l] + nums[r] > 0) {
          r--;
        } else if (nums[i] + nums[l] + nums[r] < 0) {
          l++;
        } else {
          ans.push_back({nums[i], nums[l], nums[r]});
          int tempIndex1 = l, tempIndex2 = r;
          while (l < r && nums[l] == nums[tempIndex1])
            l++;
          while (l < r && nums[r] == nums[tempIndex2])
            r--;
        }
      }
      while (i + 1 < n && nums[i] == nums[i + 1])
        i++;
    }
```

