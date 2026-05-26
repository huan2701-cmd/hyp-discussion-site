# Hyp Functional Prediction · Discussion Tree

与陈悦老师的会议讨论树。15 个问题、5 个主题、可评论可跟进。

**核心定位**：让陈老师 (或其他合作者) 点开任意问题，直接用 GitHub 账号评论、回复、跟进。

---

## 一、本地预览

```bash
# 任意 Python 3
python -m http.server 8000

# 浏览器打开
http://localhost:8000
```

---

## 二、部署状态

| 项                | 状态                                                            |
| ----------------- | --------------------------------------------------------------- |
| GitHub Repo       | https://github.com/huan2701-cmd/hyp-discussion-site             |
| GitHub Pages      | https://huan2701-cmd.github.io/hyp-discussion-site/             |
| Discussions       | 已开 (Q&A 分类已就绪)                                           |
| Giscus 参数       | 已填入 `index.html` (`R_kgDOSoh1cg` / `DIC_kwDOSoh1cs4C948T`)  |
| **唯一剩余步骤** | **安装 Giscus App** ← 见下方                                    |

### 启用评论（唯一手动步骤）

访问 https://github.com/apps/giscus → **Install** → 选择 `hyp-discussion-site` 仓库 → **Save**

完成后，刷新页面，每个问题下方就会自动显示评论框。陈老师用 GitHub 账号点开任意问题都可以直接评论。

> **为什么需要这一步？** Giscus 是个 GitHub App，必须由仓库 owner 主动授权才能在外部网页里操作仓库的 Discussions。这是 GitHub 的安全机制，没法用 API 跳过。

---

## 三、给陈老师的分享话术（中文模板）

> 陈老师好，上次会议梳理出 15 个问题，做成了一个讨论页：
>
> https://huan2701-cmd.github.io/hyp-discussion-site/
>
> Q4（指标）和 Q12（验证）是最高优先级，您方便的时候点进去用 GitHub 账号留言就行，
> 一条评论会落在一个 GitHub Discussion 里，方便后续追溯。

---

## 四、文件结构

```
hyp-discussion-site/
├── index.html       # 主页（15 个问题 + Giscus 加载逻辑）
├── style.css        # 样式（深色学术风）
├── .nojekyll        # 告诉 GitHub Pages 跳过 Jekyll
└── README.md        # 部署说明（本文件）
```

---

## 五、问题清单速查

| ID  | 主题   | 优先级    | 标题                                    |
| --- | ------ | --------- | --------------------------------------- |
| Q1  | 结构   | Normal    | 羟基化修饰的结构功能假设是否成立？      |
| Q2  | 结构   | Normal    | 结构变化 → Hyp 功能性的生物学基础？     |
| Q3  | 结构   | Normal    | 只比较静态结构是否足够？                |
| Q4  | 方法   | **Crit**  | **用什么指标量化结构差异？**            |
| Q5  | 方法   | High      | AF3 自带指标能直接用作功能预测吗？      |
| Q6  | 方法   | High      | 已预测结构上再建模 PTM 是否可行？       |
| Q7  | 方法   | Normal    | ESM-2 路线是否完全放弃？                |
| Q8  | 方法   | Low       | PTM-Mamba 是否值得调研？                |
| Q9  | 规模   | High      | 如何批量处理成千上万个位点？            |
| Q10 | 规模   | High      | 批量比较 pipeline 怎么设计？            |
| Q11 | 规模   | Normal    | 多 Hyp 位点：全加还是逐一加？           |
| Q12 | 验证   | **Crit**  | **如何验证结构变化分数和功能相关？**    |
| Q13 | 验证   | High      | 已知功能位点的结构变化符合预期吗？      |
| Q14 | 协作   | Normal    | 是否邀请结构生物学方向的人评估？        |
| Q15 | 协作   | Normal    | 现在的阶段定位是什么？                  |

---

## 六、依赖关系

```
Q4 (指标) → Q12 (验证) → Q5/6/9/10 (规模化) → Q14/15 (节奏)
```

Q4 和 Q12 不解决，下游问题就没法落地。
