
## Template
```
<type>(<scope>): <simple description>

<detailed description>

<footer>
```
## 字段说明

- **type**：变更的类别，常用的有
    
    - `feat`：新功能
    - `fix`：bug 修复
    - `docs`：文档更新
    - `style`：格式（不影响功能，如空格、分号等）
    - `refactor`：重构（既不是新增功能，也不是修复 bug）
    - `perf`：性能优化
    - `test`：测试相关
    - `chore`：构建流程或辅助工具变动
        
- **scope**（可选）：影响范围，比如模块名、文件名
    
- **简洁描述**：一句话说明本次提交做了什么，**不超过 50 字**，首字母小写，不以句号结尾
    
- **详细描述**（可选，90 字以内一行）：
    
    - 问题背景
    - 解决方案要点
    - 可能的副作用或兼容性说明
- **footer**（可选）：
    
    - 关联 Issue，如 `Closes #123`
    - BREAKING CHANGE: 描述不兼容的重大变更


## Example 0

```
feat(preprocess): 支持 auto-orient EXIF 旋转

自动读取照片 EXIF Orientation 信息，并在 resize 前先行旋转，  
保证所有后续处理层面对齐结果一致。  

Closes #45
```

## Example 1
```
fix(export): 修复 H.264 编码时无声音轨的问题

- 在 ffmpeg 合成命令中添加 `-map 0:a?`，保证有音轨时能被正确合并  
- 保留无音轨时的兼容性  

BREAKING CHANGE: 默认改为同时生成带/不带音轨的两个版本
```