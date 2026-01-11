$\lVert v+w \rVert^{2}=(v+w)\cdot(v+w)=\lVert v \rVert^{2}+\lVert w \rVert^{2}+2v\cdot w\leq \lVert v \rVert^{2}+\lVert w \rVert^{2}+2\lvert v+w \rvert\leq \lVert v \rVert^{2}+\lVert w \rVert^{2}+2\lVert v \rVert\lVert w \rVert=(\lVert v \rVert+\lVert w \rVert)^{2}$

$\Longleftrightarrow$

```dataviewjs
// 收集所有 markdown 笔记
let results = [];

for (let page of dv.pages()) {
    // 只看 .md 文件
    if (!page.file.path.endsWith(".md")) continue;

    const file = app.vault.getAbstractFileByPath(page.file.path);
    if (!file) continue;

    // 读取全文内容
    const content = await app.vault.cachedRead(file);

    // 粗略按“非空白字符块”统计单词/字数
    const words = content.match(/\S+/g) ?? [];
    const wordCount = words.length;

    results.push({
        page,
        wordCount
    });
}

// 按字数从高到低排序
results.sort((a, b) => b.wordCount - a.wordCount);

// 取前 5 篇，输出表格
dv.table(
    ["笔记", "字数"],
    results.slice(0, 5).map(r => [
        r.page.file.link,
        r.wordCount
    ])
);


```

