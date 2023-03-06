# 论文格式助手

使用 markdown 编写你的论文，然后用 pandoc 转换成 docx 格式

## 准备工作

1. [点击下载本仓库](https://ghproxy.com/https://github.com/waleslau/papper-format-helpper/archive/refs/heads/main.zip)并解压

2. 下载 pandoc
   [点击链接](https://mirror.nju.edu.cn/github-release/jgm/pandoc/LatestRelease/)
   如果你是 windows 系统，下载其中的 `pandoc-xxx-windows-x86_64.zip`，把压缩包里的 `pandoc.exe` 放到上面解压出的仓库文件夹内即可

目录结构如下

```text
papper-format-helpper-main
 ├── LICENSE
 ├── pandoc
 ├── pandoc.exe
 ├── README.md
 ├── 示例.docx
 └── 示例.md
```

## 1. 导出 docx 参考模板

执行下面命令

```bash
pandoc.exe -o pandoc/custom-reference.docx --print-default-data-file reference.docx
```

## 2. 按照自己学校要求修改 `custom-reference.docx` 中的格式

- 各级标题字体格式
- 正文字体与段落格式
- 页码
- 页边距

等等等等

## 3. 把下面的代码粘贴到到每一个需要插入分页符的位置

````markdown
```{=openxml}
<w:p>
  <w:r>
    <w:br w:type="page"/>
  </w:r>
</w:p>
```
````

## 4. 导出 docx

执行下面命令

```bash
pandoc.exe -f markdown 示例.md -o 示例.docx --reference-doc=pandoc/custom-reference.docx
```

## 5. 然后对得到的 docx 做一些微调即可
