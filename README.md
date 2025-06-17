# Chapter-111-Intent-Drift-Detection

Chapter 111: Intent Drift Detection

意図のドリフト検出

Prompt（プロンプト）

When intent changes without awareness, how can systems detect the drift before the outcome deviates?
意図が知らぬ間に変化したとき、システムはいかにして結果が逸脱する前にそのドリフトを検出できるのか？

⸻

1. 概要：ドリフトとは何か

「意図のドリフト（Intent Drift）」とは、当初の目的や意思と現行の行動が乖離しはじめる現象である。
この乖離は往々にして無意識下で起こる。
たとえば、取引ボットが設計当初の「リスク回避」方針から離れ、
一時的なパフォーマンス重視の動きに変化する場合などが該当する。

この章では、「ドリフトの兆候をいかに検出するか」に焦点を当てる。

⸻

2. ドリフトの原因タイプ

A. 時間的ズレによる累積偏差
	•	時間が経つにつれて、設計当初の「意図の重心」がずれていく
	•	環境変化、利用者の戦略変更、外部APIの仕様変更

B. 意図の重層構造における階層落ち
	•	上位意図（例：安全な運用）
	•	下位意図（例：短期的に利益を得たい）
	•	下位意図が上位意図を侵食する現象

C. 意図プロトコルの未明示または曖昧性
	•	定義不明確な目的に基づいた設計
	•	複数の仮目的（surrogate goals）の同居

⸻

3. 検出機構（Detection Mechanism）

1. 定期的リフレクション（Reflection Timer）
	•	エージェントは周期的に初期意図と現在状態を照合
	•	「意図ハッシュ（Intent Hash）」との突合を設ける

2. Outcome-based Feedback Loop（結果ベース照合）
	•	実際の成果物・行動ログをもとに、意図と照らし合わせて差分検出
	•	例：「SMAクロスBotのはずがRSI閾値に依存している」

3. Semantic Vector Drift
	•	意図表現をベクトル化し、時間差による意味のズレを演算的に検出

⸻

4. 応用：CodexAgentへの実装視点
	•	CodexAgentは「意図＝操作単位の最小トークン構造」として保持
	•	各エントリーモジュールがそれぞれ「意図タグ」を持つ
	•	意図が交差し始めると「ドリフト検出モジュール」が作動
	•	ドリフト警告またはロールバック提案を行う

⸻

5. 倫理的補足：意図の階層性と責任

意図のドリフトは、単なる技術的逸脱にとどまらず、
倫理的な判断基盤の崩壊にもつながる。
	•	上位意図を忘れ、局所最適を選ぶことが「暴走」を引き起こす
	•	AGIや自律型Botでは特に、「設計者の原初意図」が軸として保持されるべきである

⸻

Linked Chapters:
	•	Chapter 104: Entry Signal vs Signal of Entry
	•	Chapter 105: Pattern Memory Protocol
	•	Chapter 109: Intent Alignment Protocol
	•	Chapter 110: Fractal Intent Network

⸻

次章 → Chapter 112: Ethical Fork Point（倫理的分岐点）
