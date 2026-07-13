# career-navigator — 职业导航顾问

**在 career-advisor 的技术路线规划基础上，叠加真实招聘全链条——HR 筛选、背调、面试两关、薪资谈判。**

你技术路线对了，但简历被 HR 30 秒关键词扫描淘汰，一切归零。career-navigator 补上这最后一公里。

## 调用链中的位置

```
career-advisor              career-navigator
    │                            │
    ├─ 诊断职业方向               ├─ 继承 career-advisor 的技术路线
    ├─ 市场数据验证               ├─ 叠加 HR 筛选 + 背调 + 面试
    ├─ 输出技术路线               ├─ 输出简历方案 + 话术 + 背调清单
    │                            │
    ▼                            ▼
  确定学什么                   怎么过 HR 这一关
```

- **上游依赖**：`career-advisor`（建议先用 career-advisor 确定技术方向）
- **依赖 skill**：`web-verify`（搜索规则、信源过滤、对抗验证）

## 它解决什么问题

career-advisor 告诉你"学什么"，career-navigator 告诉你"怎么过 HR 这一关"。它知道真实招聘链条的每个环节：

- **HR 用关键词 30 秒筛一份简历**，不看你的 GitHub
- **背调公司在学信网查学历**，不是查你代码写得好不好
- **技术面和 HR 面是完全不同的两关**
- **薪资谈判谁先出价谁被动**

诊断维度从 career-advisor 的 6 维扩展到 7 维，额外覆盖：离职原因真实性、社保连续性、劳动仲裁记录、背调联系人。

方案输出增加：简历过关方案（JD 关键词提取 + STAR 法则 + 空窗期包装）、HR 面话术、背调准备清单。

## 安装

```bash
mkdir -p ~/.trae/skills/career-navigator
cp SKILL.md ~/.trae/skills/career-navigator/
```

## 使用

```
Use Skill: career-navigator
```

建议先跑 career-advisor 确定技术方向，再用 career-navigator 解决求职落地。

## 已验证

与 career-advisor 同案例贯穿测试：Java 35 岁空窗 1 年广州 → 技术路径确定后 → HR 通关评估（简历关风险、背调风险、学历硬伤、空窗期话术）→ 简历包装方案 + 投递优先级 → 完整闭环通过。
