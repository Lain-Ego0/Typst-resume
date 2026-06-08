# Typst 中文简历模板库

这个仓库包含多套可直接修改的 Typst 简历模板，并保留对应的 PDF 与预览图。

## 文档目录

- [目录结构](#目录结构)
- [模板总览](#模板总览)
- [预览](#预览)
- [快速使用](#快速使用)
- [依赖安装](#依赖安装)
- [进阶](#进阶)
- [常见问题](#常见问题)
- [说明](#说明)
- [致谢](#致谢)

## 目录结构

```text
Typst-resume-template/
├─ typ/      模板文件（直接改这里）
├─ images/   预览图与头像图片（可选）
├─ pdf/      导出的 PDF
└─ README.md
```

## 模板总览

### A. 基础模板

- `typ/no_profile_picture.typ`
- `typ/with_profile_picture.typ`
- `typ/resume_classic_with_photo.typ`
- `typ/minimal_ats.typ`
- `typ/bracket_index_titles.typ`
- `typ/split_banner_titles.typ`
- `typ/side_label_titles.typ`

### B. 扩展模板

- `typ/ref_golixp_resume_zh_cn.typ`
- `typ/ref_uniquecv_typst.typ`
- `typ/ref_typst_cv_miku.typ`
- `typ/ref_moderncv_typst.typ`
- `typ/ref_resume_typ.typ`
- `typ/ref_chicv.typ`
- `typ/ref_bamboovir_typst_resume_template.typ`
- `typ/ref_brilliant_cv.typ`
- `typ/ref_chinese_resume_in_typst.typ`

## 预览

> GitHub 的 Markdown 表格会把多列图片压得很窄，这里改为两列预览。
> 点击图片可查看原图。

<p>
  <a href="images/bracket_index_titles_page_1.png"><img src="images/bracket_index_titles_page_1.png" alt="bracket_index_titles" width="48%" /></a>
  <a href="images/minimal_ats_page_1.png"><img src="images/minimal_ats_page_1.png" alt="minimal_ats" width="48%" /></a>
</p>
<p>
  <a href="images/no_profile_picture_page_1.png"><img src="images/no_profile_picture_page_1.png" alt="no_profile_picture" width="48%" /></a>
  <a href="images/ref_bamboovir_typst_resume_template_page_1.png"><img src="images/ref_bamboovir_typst_resume_template_page_1.png" alt="ref_bamboovir_typst_resume_template" width="48%" /></a>
</p>
<p>
  <a href="images/ref_brilliant_cv_page_1.png"><img src="images/ref_brilliant_cv_page_1.png" alt="ref_brilliant_cv" width="48%" /></a>
  <a href="images/ref_chicv_page_1.png"><img src="images/ref_chicv_page_1.png" alt="ref_chicv" width="48%" /></a>
</p>
<p>
  <a href="images/ref_chinese_resume_in_typst_page_1.png"><img src="images/ref_chinese_resume_in_typst_page_1.png" alt="ref_chinese_resume_in_typst" width="48%" /></a>
  <a href="images/ref_golixp_resume_zh_cn_page_1.png"><img src="images/ref_golixp_resume_zh_cn_page_1.png" alt="ref_golixp_resume_zh_cn" width="48%" /></a>
</p>
<p>
  <a href="images/ref_moderncv_typst_page_1.png"><img src="images/ref_moderncv_typst_page_1.png" alt="ref_moderncv_typst" width="48%" /></a>
  <a href="images/ref_resume_typ_page_1.png"><img src="images/ref_resume_typ_page_1.png" alt="ref_resume_typ" width="48%" /></a>
</p>
<p>
  <a href="images/ref_typst_cv_miku_page_1.png"><img src="images/ref_typst_cv_miku_page_1.png" alt="ref_typst_cv_miku" width="48%" /></a>
  <a href="images/ref_uniquecv_typst_page_1.png"><img src="images/ref_uniquecv_typst_page_1.png" alt="ref_uniquecv_typst" width="48%" /></a>
</p>
<p>
  <a href="images/resume_classic_with_photo_page_1.png"><img src="images/resume_classic_with_photo_page_1.png" alt="resume_classic_with_photo" width="48%" /></a>
  <a href="images/side_label_titles_page_1.png"><img src="images/side_label_titles_page_1.png" alt="side_label_titles" width="48%" /></a>
</p>
<p>
  <a href="images/split_banner_titles_page_1.png"><img src="images/split_banner_titles_page_1.png" alt="split_banner_titles" width="48%" /></a>
  <a href="images/with_profile_picture_page_1.png"><img src="images/with_profile_picture_page_1.png" alt="with_profile_picture" width="48%" /></a>
</p>

## 快速使用

1. 打开任意 `typ/*.typ` 文件。
2. 替换姓名、电话、邮箱、教育/项目经历。
3. 使用 Typst 导出 PDF。

示例：

```bash
typst compile typ/ref_uniquecv_typst.typ pdf/ref_uniquecv_typst.pdf
```

批量编译所有 `ref_` 模板：

```bash
mkdir -p pdf
for f in typ/ref_*.typ; do
  name=$(basename "${f%.typ}")
  typst compile "$f" "pdf/${name}.pdf"
done
```

## 依赖安装

### 1) Typst CLI

macOS（Homebrew）：

```bash
brew install typst
```

跨平台（已安装 Rust/Cargo）：

```bash
cargo install --locked typst-cli
```

**推荐：直接使用VS Code + `Tinymist Typst`插件**

### 2) 字体下载与安装

- 为了减少环境差异，模板都设置了字体回退列表；若你已安装对应字体，显示会更接近参考项目。
- 如果未安装推荐字体，`typst compile` 可能给出 `unknown font family` warning，但模板仍可正常编译。

> 下面命令覆盖了这些模板常见字体：
> Noto/Source Han CJK、IBM Plex、Roboto、Source Sans、Mulish、Nerd Font Symbols。

下载到项目内 `fonts/`：

```bash
mkdir -p fonts && cd fonts

curl -L -o source-han-sans-sc.zip \
  https://github.com/adobe-fonts/source-han-sans/releases/latest/download/SourceHanSansSC.zip

curl -L -o source-han-serif-cn.zip \
  https://github.com/adobe-fonts/source-han-serif/releases/latest/download/12_SourceHanSerifCN.zip

curl -L -o nerd-font-symbols.zip \
  https://github.com/ryanoasis/nerd-fonts/releases/latest/download/NerdFontsSymbolsOnly.zip

curl -L -o roboto.zip "https://fonts.google.com/download?family=Roboto"
curl -L -o source-sans-3.zip "https://fonts.google.com/download?family=Source%20Sans%203"
curl -L -o source-sans-pro.zip "https://fonts.google.com/download?family=Source%20Sans%20Pro"
curl -L -o mulish.zip "https://fonts.google.com/download?family=Mulish"
curl -L -o ibm-plex-sans.zip "https://fonts.google.com/download?family=IBM%20Plex%20Sans"
curl -L -o ibm-plex-serif.zip "https://fonts.google.com/download?family=IBM%20Plex%20Serif"
curl -L -o ibm-plex-mono.zip "https://fonts.google.com/download?family=IBM%20Plex%20Mono"
```

安装到 Linux 用户字体目录：

```bash
mkdir -p ~/.local/share/fonts/typst-resume
for z in fonts/*.zip; do
  unzip -o "$z" -d ~/.local/share/fonts/typst-resume
done
fc-cache -f -v
```

### 3) `typst-cv-miku` 里提到的 `kpfonts`

如果你要尽量贴近该项目原效果：

```bash
# 需要 TeX Live
tlmgr install kpfonts
```

## 进阶

### 1) 仓库内安装 Tinymist

适合不想改系统环境，或在受限环境（如部分 Snap 会话）里使用：

```bash
mkdir -p .local/bin .local/config
curl --proto '=https' --tlsv1.2 -LsSf \
  https://github.com/Myriad-Dreamin/tinymist/releases/latest/download/tinymist-installer.sh \
  | XDG_BIN_HOME="$(pwd)/.local/bin" \
    XDG_CONFIG_HOME="$(pwd)/.local/config" \
    TINYMIST_NO_MODIFY_PATH=1 sh
```

### 2) 可选：为当前终端会话设置 PATH

```bash
export PATH="$(pwd)/.local/bin:$PATH"
```

## 常见问题

### 1. `unknown font family`

系统没装对应字体。先执行上面的字体下载与安装命令，或者把模板中的字体改成你机器已有字体。

### 2. `image not found`

检查头像路径与文件名是否一致，建议使用 `images/image.png`。

### 3. 看不到预览

在 VS Code 执行 `Typst: Open Preview`。

## 致谢

### 参考

- golixp-resume-zh-cn: <https://typst.app/universe/package/golixp-resume-zh-cn/>
- uniquecv-typst: <https://github.com/gaoachao/uniquecv-typst>
- typst-cv-miku: <https://github.com/ice-kylin/typst-cv-miku>
- moderncv.typst: <https://github.com/giovanniberti/moderncv.typst>
- resume.typ: <https://github.com/wusyong/resume.typ>
- chicv: <https://github.com/skyzh/chicv>
- bamboovir/typst-resume-template: <https://github.com/bamboovir/typst-resume-template>
- brilliant-CV: <https://github.com/yunanwg/brilliant-CV>
- Chinese-Resume-in-Typst: <https://github.com/OrangeX4/Chinese-Resume-in-Typst>
