# 调查方法论

这些方法用于现场还原和归因前的思考。只在相关场景读取，不要把所有方法机械套用到每个问题。

## Legacy Issue Analysis

使用场景:
- 问题来自长期存在的模板、旧系统、旧流程、历史产品或多年未改的交付物。
- 有人用“过去一直这样”或“以前没人投诉”作为判断依据。

核心问题:
- 旧版本是否也存在同一差异？
- 过去无人投诉，是没人发现、未触发场景，还是已有共识？
- 是否存在 waiver、accepted deviation、known limitation 或 special handle？
- 当前客户、场景、合同、验收标准是否不同？

需补 Evidence:
- 旧 release package、旧 upstream、旧验收记录、release notes。
- 老邮件、ticket、waiver、deviation list、known issue list。
- 历史客户 complaint / no complaint 记录。

可能结论:
- latent legacy issue 被新产品暴露。
- 历史 accepted deviation 在当前项目未被继承或未被确认。
- 当前投诉属于新场景触发，不是当前开发首次引入。
- 缺少历史证据，只能作为 Contextual Evidence。

高风险说法:
- “十几年没人投诉，所以客户错了。”
- “这是前人的问题，和当前 release 无关。”

稳妥表达:
- “长期无投诉不能直接证明没有问题，但它提示需要追溯历史 acceptance、waiver 或 special handle，再判断当前 complaint 是否构成 defect。”

## Baseline / Delta Analysis

使用场景:
- 项目要求 fully copy、clone、migration、版本继承或按某个 baseline 发布。
- 当前结果与原始模板、上游文件或 release package 不一致。

核心问题:
- 原始 baseline 是什么？
- 后续是否发生过 baseline change？
- change 是否进入 change control？
- release 时 frozen baseline 是哪个版本？
- 当前 complaint 是对比哪个 baseline 提出的？

需补 Evidence:
- baseline 定义、copy 指令、版本号、commit、变更记录。
- release checklist、approval、frozen package、diff 报告。

可能结论:
- 当前执行符合原 baseline，但 baseline 后续漂移。
- release gate 未捕捉 upstream 与 final product 的差异。
- fully copy 本身复制的是 legacy package，而不是干净规格。

高风险说法:
- “我 fully copy 了，所以后续都不归我管。”

稳妥表达:
- “需要先确认 release 时采用的 frozen baseline，再判断当前差异是执行偏差、baseline drift，还是 change-control gap。”

## Complaint Validity Challenge

使用场景:
- 客户、Requester 或上游提出 complaint，但 expected behavior 未明确。
- 看到差异不一定等于合同意义上的 defect。

核心问题:
- 客户看到的现象是否真实？
- 客户依据的是合同、spec、旧版本、当前 upstream，还是主观期待？
- 影响是否达到 issue 级别？
- 是否属于 enhancement、preference、scope drift 或 late change？

需补 Evidence:
- 客户原话、截图、复现方式、合同条款、验收标准、影响范围。

可能结论:
- 观察真实，但 issue 尚未成立。
- issue 成立，但归因仍未明确。
- complaint 实际是 change request。

高风险说法:
- “客户抱怨不真实。”
- “这不算 issue。”但没有说明 expected behavior 和影响。

稳妥表达:
- “客户观察到的 gap 需要先拆成 factual observation 和 contract-level defect 两层判断。”

## Waiver / Special Handle Search

使用场景:
- 历史上有偏离标准但长期保留的行为。
- 有人怀疑这是 deliberate exception，而不是漏检。

核心问题:
- 是否有人正式接受过该偏差？
- special handle 的适用范围是谁、哪个客户、哪个版本、哪个场景？
- 当前项目是否继承该 exception？
- exception 是否有到期、条件或替代方案？

需补 Evidence:
- waiver、deviation approval、meeting minutes、customer sign-off、exception list。

可能结论:
- 当前行为受历史 waiver 支持。
- waiver 不适用于当前客户或新版本。
- 没有证据，不能把历史沉默当成批准。

高风险说法:
- “以前都这样，所以这是默认同意。”

稳妥表达:
- “除非找到 waiver 或 special handle 记录，否则历史沉默只能算 Contextual Evidence，不能直接作为 approval。”

## Change Control Drift

使用场景:
- 有人修改 upstream、配置、scope、requirement 或 handoff input，但最终交付没有同步。

核心问题:
- 谁提出 change？
- 谁批准 change？
- 谁负责 downstream sync？
- 是否通知 release Owner 和 QA？
- checklist 是否覆盖 change impact？

需补 Evidence:
- change request、commit、review、approval、notification、release checklist。

可能结论:
- change 本身合理，但没有进入 release control。
- upstream Owner 未完成 impact handoff。
- downstream release gate 未发现 mismatch。

高风险说法:
- “我只是好心提醒，所以没有责任。”

稳妥表达:
- “需要区分 change 的正确性、change handoff、release consistency check 三层责任。”

## RACI / Handoff Boundary

使用场景:
- 多个 team、Owner、上游、下游、客户或 release gate 共同参与。

核心问题:
- 谁 Responsible 执行？
- 谁 Accountable 签核？
- 谁 Consulted 提供必要输入？
- 谁 Informed 只需要被通知？
- handoff contract 是否写清输入、输出、时间和验收方式？

需补 Evidence:
- RACI、SOP、handoff checklist、邮件确认、ticket Owner、approval chain。

可能结论:
- 执行 Owner 与签核 Owner 不同。
- 修复 Owner 与根因 Owner 不同。
- 没有定义 Owner，属于 Process / Contract Gap。

高风险说法:
- “谁最后碰过就是谁负责。”

稳妥表达:
- “需要把 Responsible、Accountable、Consulted、Informed 拆开，否则会把执行责任、签核责任和修复责任混在一起。”

## Fix Owner vs Root Cause Owner

使用场景:
- 用户需要推进修复，但责任归因还没有定论。

核心问题:
- 谁最适合修复？
- 谁导致问题？
- 谁拥有防复发流程？
- 哪些 action 是止血，哪些 action 是预防？

需补 Evidence:
- ownership map、代码/文件 Owner、流程 Owner、approval Owner、SOP Owner。

可能结论:
- 我方负责修复，不等于我方是根因。
- 上游是根因 Owner，但下游需要增加 resilience 或 release check。
- 流程 Owner 需要更新 gate。

高风险说法:
- “谁修就是谁的锅。”

稳妥表达:
- “修复 Owner 和 root cause Owner 要分开；当前先明确谁能关闭风险，再基于 Evidence 讨论根因归属。”
