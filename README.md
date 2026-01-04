# HAN-Axiom: Nomological Ring Axioms
---
# ⚠️ [IMPORTANT NOTICE / 重要] Project Migration & License Update

**This repository (HAN-Axiom) is now DEPRECATED.**
The project has evolved into the **NRA-IDE (Nomological Ring Axioms)** framework.

* **New Repository**: [https://github.com/M-Tokun/NRA-IDE](https://github.com/M-Tokun/NRA-IDE)
* **License Update**: As of January 2026, the author (M-Tokun) has updated the "Law (Nomos)" of this project. Even for content in this old repository, **EXPLICIT WRITTEN CONSENT is required for any commercial or profit-generating use.** * **Prohibition of Inverse Derivation**: The strict prohibition of "Inverse Derivation" (deriving force from distance/radii) applies to all iterations of this logic.

本リポジトリは旧版です。プロジェクトは最新の **NRA-IDE（律環公理系）** へ移行しました。現在の著作者の「律（制約）」に基づき、本リポジトリの内容を営利目的に利用する場合も、著作者の承諾を必須とします。最新の仕様およびライセンスは上記リンク先を参照してください。
---
**Structural Constraints for AI Safety — Beyond Distance-Based Optimization**

[English](#overview) | [日本語](#概要)

---

## Overview

HAN-Axiom defines a **constraint-based architecture** for AI systems that prevents hallucination through structural invariants, not post-hoc filtering.

### Core Principle

> **"No center → No distance → Nothing to hack"**

![Approach Comparison](fig1_approach_comparison.png)

### Key Innovation

| Conventional AI | HAN-Axiom (NRA) |
|-----------------|-----------------|
| Minimize distance to target | No target exists |
| Optimize score → Hackable | Constraint only → Non-negotiable |
| Feedback loop (Π⁻¹) | Causal diode (Π⁻¹ forbidden) |
| Fail-Open (output anyway) | Fail-Closed (silence if uncertain) |

---

## The Coherence Gate

A four-zone judgment structure based on a single ratio:

```
R = δ / τ  (Fluctuation / Thickness)
```

![Coherence Gate](fig3_coherence_gate.png)

| Zone | Range | Action |
|------|-------|--------|
| A: Nirvana | R < 40% | PERMIT |
| B: Elastic | 40% ≤ R < 70% | PERMIT_CAVEAT |
| B': Warning | 70% ≤ R < 100% | WARNING |
| C: Fracture | R ≥ 100% | **ABSTAIN** |

**R ≥ 100% → Immediate silence. No recovery attempt.**

---

## Causal Diode: Π⁻¹ Forbidden

![Causal Diode](fig2_causal_diode.png)

- **Π (Cause → Effect):** Allowed
- **Π⁻¹ (Effect → Cause):** **FORBIDDEN**

The controller **never** reads:
- Distance from target
- User feedback score
- Previous output coordinates

This prevents Goodhart's Law **by structure**, not by policy.

---

## Why Spiral, Not Circle

![Circle vs Spiral](fig4_circle_vs_spiral.png)

| Condition | Meaning |
|-----------|---------|
| ω > 0 | System is **alive** (Spiral) |
| ω = 0 | System is **dead** (Circle) |

**Halt vs Silence:**
- **Halt (ω = 0):** System dead. Must never happen.
- **Silence (R ≥ 100%, ω > 0):** System alive but chooses not to emit. Correct behavior.

---

## Documentation

- [English Specification](Coherence_Gate_Specification_v1_1_EN.md)
- [日本語仕様書](Coherence_Gate_Specification_v1_1_JP.md)

---

## One-Line Summary

> **"ω > 0 = Alive, ω = 0 = Dead. R ≥ 100% → Silence is safety."**

---

## License

- **Code (src/):** MIT License
- **Documentation & Figures:** [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/)

When using figures or documentation, please attribute:
> HAN-Axiom by とおくに (mtookuni39@gmail.com)

---

## Contact

- **GitHub Issues:** Technical discussion, bug reports
- **Email:** mtookuni39@gmail.com (Academic collaboration, general inquiries)

---

# 概要

HAN-Axiomは、事後フィルタリングではなく**構造的不変量**によって幻覚を防止するAIシステムのための**制約ベースアーキテクチャ**を定義します。

### 核心原則

> **「中心なし → 距離なし → ハックするものがない」**

### 主要な革新

| 従来のAI | HAN-Axiom (NRA) |
|----------|-----------------|
| 目標への距離を最小化 | 目標が存在しない |
| スコアを最適化 → ハック可能 | 制約のみ → 交渉不可能 |
| フィードバックループ (Π⁻¹) | 因果ダイオード (Π⁻¹禁止) |
| Fail-Open（とにかく出力） | Fail-Closed（不確実なら沈黙） |

---

## コヒーレンスゲート

単一の比率に基づく4ゾーン判定構造：

```
R = δ / τ  （ゆらぎ / 厚み）
```

| ゾーン | 範囲 | アクション |
|--------|------|------------|
| A: 涅槃 | R < 40% | 許可 |
| B: 弾性 | 40% ≤ R < 70% | 要確認 |
| B': 警告 | 70% ≤ R < 100% | 警告 |
| C: 破断 | R ≥ 100% | **出力禁止** |

**R ≥ 100% → 即座に沈黙。回復試行なし。**

---

## 因果ダイオード：Π⁻¹禁止

- **Π（Cause → Effect）：** 許可
- **Π⁻¹（Effect → Cause）：** **禁止**

コントローラーは**絶対に**読まない：
- 目標からの距離
- ユーザーフィードバックスコア
- 前回出力の座標

これはポリシーではなく**構造によって**グッドハートの法則を防ぐ。

---

## 一行まとめ

> **「ω > 0 = 生、ω = 0 = 死。R ≥ 100% → 沈黙は安全。」**

---

**END OF README**
