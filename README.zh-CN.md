# 反例驱动的定理精炼（CDTR）

这是一个面向数学与理论研究的 AI 协作流程，而不是“神奇提示词合集”。

它的核心不是让 AI 帮你维护原来的想法，而是让 AI 主动攻击当前理论：

**删假设 -> 找反例 -> 提取 obstruction -> 修定理 -> 做 necessity/sufficiency -> 压到 primitives/observables -> 证明信息优势或附近失败 -> 重建依赖 DAG -> 验证**

## 为什么要做这个仓库

LLM 大幅降低了证明尝试、算例、代数推导、代码和变体搜索的成本，但它也非常容易顺着用户的想法继续往下写。对理论研究而言，这会造成一个危险：对话越来越完整，定理却未必越来越正确。

CDTR 的目标是把 AI 的角色改成一个 adversarial research partner：它首先负责尝试杀死命题，然后才负责修复命题。

## 最核心的规则

任何重要修改都尽量要求一个可检查的 certificate：

- 删除假设：给证明或反例；
- 声称必要：给 necessity proof；
- 声称 sharp：给 necessity / optimality / impossibility 边界；
- 声称 identification：排除 observational equivalence；
- 声称信息优势：证明弱信息下做不到，而不是只证明强信息下做得到。

每个重要命题保持状态标签：

`PROVED / DISPROVED / CONJECTURE / OPEN / NUMERICAL EVIDENCE / IMPORTED RESULT`

## 文件

- [`SKILL.md`](./SKILL.md)：完整版研究协议，可作为 agent / skill 指令。
- [`PROMPT.md`](./PROMPT.md)：单段可复制提示词。
- [`templates/RESEARCH_STATE.md`](./templates/RESEARCH_STATE.md)：长期项目的状态表。
- [`examples/minimal-example.md`](./examples/minimal-example.md)：最小示例。

## 这套流程特别强调的事情

1. **删假设**：每次只攻击一个假设，并要求 proof / counterexample / unresolved obligation。
2. **反例不是终点**：反例要继续提炼成可以解释一族失败的 obstruction。
3. **从 sufficient 到 iff**：分别测试充分性与必要性。
4. **危险假设倒过来**：如果一个假设看起来几乎等于结论，尝试把它变成 theorem 或 necessary condition。
5. **压到 primitives / observables / support / information**：不要停留在无法观察的抽象条件。
6. **证明 information advantage / nearby failure**：说明为什么额外信息真的不可替代。
7. **依赖关系重构**：避免 assumption creep，把 existence、uniqueness、identification 等不同结论拆开。
8. **最后再去掉对话痕迹**：研究过程可以很乱，但最终 theorem architecture 应该由定义、条件和结论组织。
9. **最后再做 novelty audit**：先把数学对象搞清楚，再查是不是新结果。

## 一个重要的停止规则

这套流程并不认为“假设越少越好”。如果继续削弱只会得到逻辑上更弱、但完全失去经济/数学解释的怪条件，就应该停止。

真正想优化的是：

- logical sharpness，
- structural meaning，
- primitive/observable content，
- interpretability，
- verifiability。

而不是单独优化“最少假设”。

## 起源

这套流程来自我自己使用 AI 做理论研究时逐渐形成的习惯。在一个 rational addiction 项目中，我最初相信存在一个独立的 exit mechanism；随着不断删假设、寻找反例、检查 identification，这个机制解释最终失败，而真正留下来的问题转向 compensated comparison、support、falsification 与 identification。

完整研究历史：

https://github.com/heggebittel-lang/Rational-Relapse-Theory

后续预印本：

https://papers.ssrn.com/sol3/papers.cfm?abstract_id=7363901

## 许可

本仓库的 prompt、文档与示例采用 **Creative Commons Attribution 4.0 International (CC BY 4.0)**。

你可以复制、修改、翻译、重新发布，也可以商业使用；只需要按照许可要求署名并说明修改。官方许可：

https://creativecommons.org/licenses/by/4.0/

建议署名：

> Yushang Cheng, *Counterexample-Driven Theorem Refinement (CDTR)*, CC BY 4.0.
