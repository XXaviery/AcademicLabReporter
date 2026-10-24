# AcademicLabReporter

用于制作和修订中文高校实验报告（DOCX）的 Codex skill。根据任务书、学校模板、实验代码、实测数据和照片组织报告，适用于不同类型的实验。

Skill 名称：`academic-lab-report-workflow`。规则文件以英文撰写，报告产物使用中文。

## 功能

- 根据实际实验和模板组织正文，保留实测证据与预期结果的区别。
- 规范黑色标题、正文、三线表、图题、目录和真实 Word 页码域。
- 使用可渲染公式，并逐图检查尺寸、可读性和页面留白。
- 源代码以可编辑文本放入正文，使用五号（10.5 磅）字体、1.2 倍行距、白底和 1 磅浅灰蓝色左侧竖线；后接正文时留半行间距，保留语言语法、缩进和必要注释。
- 父代理负责写作、生成、排版和修改，多个只读子代理并行审查内容、格式和语言，提供评分及修改建议。
- 完成内部修正和复查后交付同一份最终 DOCX，不为常规步骤增加额外的对话确认。

审查使用教师提供的评分标准；缺少该标准时采用明确标注的内部评分。内部评分不保证教师最终成绩。系统强制权限审批仍由运行环境控制。

## 安装

将仓库克隆到本机 Codex 的 skills 目录，并保留 skill 的目录名。例如，在 Windows PowerShell 中：

```powershell
$skillDir = Join-Path $env:USERPROFILE '.codex\skills\academic-lab-report-workflow'
git clone https://github.com/XXaviery/AcademicLabReporter.git $skillDir
```

## 使用

在项目聊天中调用 skill，并提供任务书、模板、材料位置和实际结果，例如：

```text
使用 $academic-lab-report-workflow，根据项目中的任务书、学校模板、
实验代码和实测结果制作中文实验报告。最终 DOCX 放在项目根目录。
```

已有报告的修订复用原有生成目录、脚本和最终文件名。材料不足时保留明确占位，不编造实验结果。

## 文件

| 文件 | 用途 |
| --- | --- |
| [SKILL.md](SKILL.md) | 工作流、权限边界、文件管理和父子代理分工 |
| [references/report-spec.md](references/report-spec.md) | 正文、字体、源代码、表格、图片、公式和页面检查规范 |
| [references/review-protocol.md](references/review-protocol.md) | 并行审查、评分依据、修正及复查流程 |
| [agents/openai.yaml](agents/openai.yaml) | skill 的显示名称和默认调用提示词 |
