# 澄阅 PDF · ChengYue PDF

**面向 macOS 的轻量、强大 PDF 阅读与编辑工具。中文界面，本地处理。**

把阅读、搜索、批注、页面整理、表单填写和编辑放进一个工作空间。优先复用成熟的原生 PDF 引擎，现有专业工具和辅助组件继续随应用内置，常用处理按需运行。

## 下载源码与查看版本

[1.0.22 版本说明与附件](https://github.com/RGB-hengzhi/ChengYuePDF/releases/tag/v1.0.22) · [下载完整对应源码 ZIP](https://github.com/RGB-hengzhi/ChengYuePDF/releases/download/v1.0.22/ChengYuePDF-1.0.22-source.zip)

仓库主页面提供介绍与下载入口；**1.0.22 / V26 的完整对应源码在版本 Release 的 ZIP 附件中，包含 1557 个文件**。解压后先阅读 `BUILDING.md`；各操作说明、示例、许可证与第三方材料保留在源码中。对应本地源码提交为 `686b5b854720f4641ade808027e94c1eb83b6d8c`。

GitHub 自动生成的 `Source code (zip)` 仅包含主页仓库内容；请使用上面的 `ChengYuePDF-1.0.22-source.zip` 获取完整源码。

**源码 ZIP 是开发材料，不能直接安装为 macOS 应用。暂未提供公开二进制安装包。** 尚未完成从全新环境到成品的完整自动重建；当前实际验证环境为 Apple Silicon、macOS 27，Intel Mac 和旧系统未验证。

源码包未包含部分历史 timestamp QA runner 依赖的 `sources/qa` 资料，因此不承诺全部历史验收脚本解压后即可独立执行；构建与验证范围以包内 `BUILDING.md` 为准。

## 常用能力

| 工作 | 当前能力 |
| --- | --- |
| 阅读与查找 | 缩放、页面导航、缩略图、书签、正文搜索与多文档搜索 |
| 批注与审阅 | 高亮、便签、文字框、手绘、批注回复与汇总导出 |
| 页面整理 | 合并拆分、旋转、页面尺寸与白边裁剪预览 |
| 表单填写 | 填写交互表单、查看字段、导入导出数据与保存 |
| 文字与内容编辑 | 受支持的正文查找替换、局部字体/字号/颜色和真实预览 |
| 本地 OCR | macOS Vision 识别与校对入口 |
| 多文件处理 | 水印、页眉页脚、连续编号、OCR、文字/PNG 导出与结果打开 |
| 图片合成 PDF | 调整多图顺序、数字自然排序、按方向每张生成一页 |
| 标题多级书签 | 正文标题识别、候选修改与勾选，保留原书签并追加三级树 |
| 保存与导出 | 保存、另存、打印和已接入的文字、图像与文档转换工具 |

正文编辑受 PDF 结构和字体约束，需要核对预览；当前不支持任意 PDF 像 Word 一样自由重排。扫描件应先 OCR 并人工校对。

## 1.0.22：正文标题多级书签

从“书签管理 → 按正文标题生成多级书签…”进入。按物理字号或固定文字前缀找出候选，先预览，再修改标题、调整层级与勾选。确认后，新树追加到原书签根目录末尾，保留已有书签、动作及属性；可撤销、重做，并另存副本。

本轮使用原生文字布局与 PDF 对象引擎，没有新增 Python 处理依赖或常驻服务。正式安装版已对两页中文示例完成六个三级标题的预览、生成、另存、新进程重开与跳转检查。以下三图均为 **1.0.22 实际安装版截图**。

**标题候选预览**

![标题候选预览：中文标题、页码与三级层级](https://github.com/RGB-hengzhi/ChengYuePDF/releases/download/v1.0.22/headings-preview-122.jpg)

**书签树与正文**

![书签树与正文：六个标题组成三级树](https://github.com/RGB-hengzhi/ChengYuePDF/releases/download/v1.0.22/headings-tree-122.jpg)

**保存后重新打开**

![保存后重新打开：书签保留并跳到第二章](https://github.com/RGB-hengzhi/ChengYuePDF/releases/download/v1.0.22/headings-reopen-122.jpg)

标题候选仍需人工确认。取消核验覆盖候选预览取消与原生已取消事务；较大文档扫描中途取消的真实 GUI 场景尚未覆盖。指定样本通过不代表任意 PDF、全部历史工具或完整 PDF-XChange Editor PRO 等价能力已通过验收。完整内置说明现有组件的交付方式，具体支持范围见 ZIP 内的 `docs/已知限制.md` 与各工具说明。

## 轻量与资源占用

常用操作在本机处理，OCR 和辅助工具按需启动。本机 1.0.22 应用普通文件约 **688.04 MiB**，较 1.0.21 净减少 **10.93 MiB**；共享约 **11.72 MiB** 重复翻译资源，新增代码和资料抵消了部分减少，现有高级组件继续完整内置。

两页中文示例完成扫描、生成六个书签与另存时，主编辑进程内存单点约 **200.16 MiB**。这是有限观测，不是空闲基准或峰值上限；本轮没有 CPU 观测数据，也不保证所有文件的处理时间、内存或临时磁盘占用。

## 其他工作区实景

以下阅读、批注、内容编辑三图是 **1.0.19 历史实际截图**；批量处理、图片合成、进度三图是 **1.0.21 历史实际安装版截图**，沿用能力与版本标签一并保留。

**阅读与导航（1.0.19）**

![阅读与导航（1.0.19）](https://github.com/RGB-hengzhi/ChengYuePDF/releases/download/v1.0.22/reading.png)

**批注工作区（1.0.19）**

![批注工作区（1.0.19）](https://github.com/RGB-hengzhi/ChengYuePDF/releases/download/v1.0.22/annotations.png)

**内容编辑工作区（1.0.19）**

![内容编辑工作区（1.0.19）](https://github.com/RGB-hengzhi/ChengYuePDF/releases/download/v1.0.22/editing.png)

**批量处理工作区（1.0.21）**

![批量处理工作区（1.0.21）](https://github.com/RGB-hengzhi/ChengYuePDF/releases/download/v1.0.22/batch.png)

**图片合成工作区（1.0.21）**

![图片合成工作区（1.0.21）](https://github.com/RGB-hengzhi/ChengYuePDF/releases/download/v1.0.22/images.png)

**真实处理计数（1.0.21）**

![真实处理计数（1.0.21）](https://github.com/RGB-hengzhi/ChengYuePDF/releases/download/v1.0.22/progress.png)

## 开源基础与许可

核心工程基于 [PDF4QT](https://github.com/JakubMelka/PDF4QT) v1.6.0.0，基线提交 `23f3829ae0420da801824a0d53d82c53baa2bee9`，保留其 MIT 许可证与版权声明。界面使用 Qt，OCR 使用 Apple Vision，本地工具复用 PyMuPDF、pdf2docx 等项目。

项目新增代码采用 **AGPL-3.0-or-later**；第三方组件遵循各自许可证。完整许可与版权材料见源码 ZIP 内的 `LICENSE`、`upstream/LICENSE`、`THIRD_PARTY_NOTICES.md`。公开二进制分发所需的依赖对应源码、重链及许可材料还需进一步整理。

[报告问题](https://github.com/RGB-hengzhi/ChengYuePDF/issues)：请附系统版本、操作步骤和不含私人资料的最小示例。
