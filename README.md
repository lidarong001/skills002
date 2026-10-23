# software-test-case-generator

将需求截图 / PRD 自动转换为结构化测试点与测试用例（CSV）的 Skill。

## 工作方式

1. 用户上传需求截图并告知功能名称 → 按「日期 + 功能」存入 `input/YYYY-MM-DD-<功能名称>/`，图片按 `001.png` 顺序编号
2. AI 识别截图文字 → 汇总为 `input/YYYY-MM-DD-<功能名称>/requirement.md`
3. 按 `references/testing-strategy.md` 的测试策略生成测试点与用例
4. 输出到 `output/<一级模块>/<二级模块>/<功能名>/`

## 目录

| 路径 | 说明 |
| --- | --- |
| `SKILL.md` | Skill 主文件：流程、规则、输出格式规范 |
| `input/YYYY-MM-DD/` | 需求截图、OCR 汇总的 requirement.md、可选的 field.md |
| `references/testing-strategy.md` | 测试策略，唯一规则源 |
| `output/` | 生成的 `test-point-*.md` 与 `test-case-*.csv` |

## 输出格式

- 测试点：Markdown 表格，字段为编号 / 描述 / 覆盖类型 / 关联需求条款 / 优先级 / 来源需求
- 测试用例：UTF-8 BOM 编码 CSV，固定 11 列表头（需求摘抄/问题描述、案例编号、功能点、测试场景、测试数据及测试预期、测试结果及截图/验证、测试环境、测试类型、测试分类、是否自动化测试、用例标签是否废弃）

## 使用

在对话中说「根据这份需求截图生成测试用例」并上传截图即可。详细规则见 `SKILL.md`。
