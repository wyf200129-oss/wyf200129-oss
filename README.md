# 🧪 QA Playground — 王贺龙的测试技术仓库

> 2.5年测试开发经验 | 期望城市：大连 | Python 自动化 | Cursor AI 双端流水线

---

## 👤 关于我

2.5 年 Web/App 双端测试开发经验，从 0 到 1 独立搭建 UI（POM + Selenium）和接口（关键字驱动 + Requests）两套自动化框架，共 600+ 条用例接入 Jenkins 定时回归。基于 Cursor .cursorrules 定制 POM 截图驱动和接口契约驱动双端 AI 流水线。AI 辅助测试方面，用例设计工时缩短 50%，需求场景覆盖率从 80% 提升至 95%。

---

## 🔧 技术栈

| 类别 | 技能 |
|------|------|
| **语言** | Python |
| **UI 自动化** | Selenium · POM 设计模式 · YAML 数据驱动 · Cursor 截图驱动流水线 |
| **接口自动化** | Requests · 关键字驱动 · JSONPath · pytest-allure · Cursor 契约驱动流水线 |
| **性能测试** | JMeter · TPS / 95线 / 错误率分析 |
| **CI/CD** | Jenkins Pipeline · Allure 报告 · Git SCM |
| **数据库** | MySQL 多表联查 |
| **工具链** | Git · Docker · Linux Shell · 禅道 · Cursor AI .cursorrules |

---

## 📂 仓库内容

### 🤖 AI 辅助测试实践
- [AI 需求解析 → 用例生成工作流](./ai-testing/workflow.md)
- Prompt 工程 + RAG 辅助测试设计，工时 -50%，覆盖率 80%→95%

### 🖥️ UI 自动化框架 — Cursor 截图驱动流水线
- [POM + YAML 数据驱动 + Cursor 12步流水线](./automation-demos/ui-pom/)
- 5条规则 + 1个Skill，实现「截图 → 页面对象 → 自检 → 用例 → pytest → Allure」
- 定位器失败自愈：id→name→css→xpath 优先级自动替换（≤3次重试）

### 🔌 AI 接口自动化框架 — Cursor 契约驱动工作流
- [关键字驱动 + 契约驱动四阶段门禁](./automation-demos/api-keyword/)
- **4条规则**：pytest骨架与实现 · 契约优先 · 落盘路径 · fixture治理
- **3个Skill**：测试用例生成 · fixture与用例实现 · pytest失败修复闭环

```
OpenAPI契约 → A试点骨架 → B试点实现 → C全盘骨架 → D全盘实现
     ↑ 每阶段人工评审通过才能进入下一阶段 ↑
                         ↓
              失败修复闭环（红→绿 / xfail / skip）
```

**四条铁律**：
1. **契约优先**：path/method/status/schema 全来自 OpenAPI，禁止编造
2. **body → status 联合断言**：先验 body 字段/类型/语义，再联合 status_code，禁止仅 `assert status_code == 200`
3. **四阶段不越级**：A→B→C→D 逐级评审，禁止一次写到 D
4. **pytest 执行后才定 xfail/skip**：写用例时不预设标记

**断言示例**：
```python
# ✅ 正确：先 body 后 status
token = api.get_text(res.json(), "$..token")
assert token and len(token) > 20         # 1. 先 body
assert res.status_code == 200             # 2. 再 status

# ❌ 假绿：pytest 过了但什么都没验证
assert response.status_code == 200
```

### 🚀 开源工具部署实践
- [TestHub 全栈部署实录](./deploy-notes/)（Django + Vue3 + MySQL + Docker）

---

## 📈 项目经历速览

### ERP 企业资源计划系统（2025.05 – 2026.03）
面向服装企业的 Web + App 双端进销存系统，覆盖 13 个业务模块。

- 主导采购/销售/库存三模块全流程测试，覆盖 12 类核心单据
- 独立搭建 POM UI 自动化（200+ 条）+ 关键字驱动接口自动化（400+ 条），接入 Jenkins
- Cursor .cursorrules 定制双端 AI 流水线：POM 截图驱动 + 接口契约驱动
- AI 辅助测试设计：用例设计工时缩短 50%，覆盖率 80%→95%

### CCAS 后台管理系统（2024.10 – 2025.04）
电子档案编制管理系统，支持多层级归档、CA 数字证书电子签章。

### TestHub 智能测试管理平台（2026.03 – 2026.04）
开源测试平台全栈部署，验证 AI 功能用例生成、测试数据工厂等模块。

---

## 📬 联系方式

- 📧 邮箱：346296043@qq.com
- 📱 电话：18840823821
- 🐙 GitHub：[github.com/wyf200129-oss](https://github.com/wyf200129-oss)

---

> 💡 **"不只会用工具，更会从 0 到 1 搭建工具 + AI 驱动效率。"**
