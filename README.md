# job-hunt-coach — 求职教练

**从 HR 和用人负责人的筛选视角出发，帮候选人成为"对方愿意面试和雇佣"的人。**

定位为 `career-advisor` → `study-planner` → `learning-coach` 链条的最终下游。用户已经学完、有代码产出，缺的是求职落地。

## 调用链中的位置

```
career-advisor  →  study-planner  →  learning-coach  →  job-hunt-coach
     │                  │                  │                  │
     ├─ 诊断职业方向      ├─ 设计学习路径      ├─ 执行教学          ├─ 求职落地
     ├─ 市场数据验证      ├─ 产出计划文档      ├─ 项目代码          ├─ 简历 + 面试 + 谈薪
     └─ 技术路线          └─ CONTEXT+PROFILE   └─ PROGRESS.md      └─ 背调 + offer 对比
```

- **上游依赖**：必须先完成 learning-coach 的学习阶段（有项目代码和 PROGRESS.md）
- **入口文件**：`config/CAREER-PROFILE.md`（career-advisor 产出） + `config/PROGRESS.md`（learning-coach 产出）

## 它解决什么问题

career-advisor 告诉你"学什么"，job-hunt-coach 告诉你"怎么把自己卖出去"——从负责人的视角：

- **HR 用关键词 30 秒筛一份简历**，不看你的 GitHub
- **内推不是可选项，是主渠道**
- **薪酬谈判谁先出价谁被动**
- **背调是双向的——不只公司查你，你也该查公司**
- **面试后不复盘的候选人，同样的问题下次还会卡**

全流程 14 步：搜 → 断 → 简历 → 内推 → 自我介绍 → 投递追踪 → 技术面 → HR 面 → 面试复盘 → 薪酬谈判 → offer 对比 → 反向背调 → 背调准备 → 存档。

## 安装

```bash
mkdir -p ~/.trae/skills/job-hunt-coach
cp SKILL.md ~/.trae/skills/job-hunt-coach/
```

## 使用

```
Use Skill: job-hunt-coach
```

## 声明边界

| 做 | 不做 |
|----|------|
| 从负责人视角出发的求职策略 | 模拟面试（AI 做不到） |
| 简历逐行审查 + 包装话术 | 实时岗位列表（教用户自己搜） |
| 内推策略 + 勾搭话术 | 诊断学习方向（找 career-advisor） |
| 面试后复盘 + 弱点追踪 | 设计学习路径（找 study-planner） |
| 薪酬谈判策略 + offer 对比 | 保证 offer 结果 |
| 反向背调 + 背调准备 | |

## 已验证

基于 career-advisor 案例贯穿测试：Java 35 岁空窗 1 年广州 → 完成 learning-coach 学习阶段 → 档案刷新 → 简历包装 + 内推策略 + 跟踪表 + HR 面话术 + 薪酬谈判框架 → 完整求职闭环通过。
