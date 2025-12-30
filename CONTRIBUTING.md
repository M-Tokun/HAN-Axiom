# Contributing to IDE/HAN Project

Thank you for your interest in contributing to this project.

## How to Contribute

### Reporting Issues

1. Check existing [Issues](../../issues) to avoid duplicates
2. Use appropriate tags:
   - `[Bug]` - Unexpected behavior
   - `[Feature]` - New feature request
   - `[Inquiry]` - Questions / Clarifications
   - `[Doc]` - Documentation improvements

### Pull Requests

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/your-feature`)
3. Ensure your code passes validation checklists (see `/docs/validation/`)
4. Submit a Pull Request with clear description

### Code Standards

- **Language:** TypeScript for core logic, Markdown for documentation
- **Naming:** Follow existing conventions in codebase
- **Comments:** Required for non-obvious logic, especially physics constraints

## Critical Rules (MUST Follow)

This project has strict architectural constraints. **Violations will be rejected.**

| Rule | Description |
|------|-------------|
| **No Spatial Variables in Cause** | `x, y, z, distance` forbidden in causal core |
| **Causal Diode** | Π⁻¹ (Effect → Cause) is strictly prohibited |
| **Write-Only Log** | Log cannot be read back into computation |
| **ω > 0** | System must maintain positive angular velocity |

Before submitting, run: **"全ての違反チェックして"** (All Violation Check)

## Questions?

Open an Issue with `[Inquiry]` tag.

---

# 貢献ガイドライン（日本語）

本プロジェクトへの関心をお寄せいただきありがとうございます。

## 貢献方法

### Issue報告

1. 重複を避けるため既存の [Issues](../../issues) を確認
2. 適切なタグを使用：
   - `[Bug]` - 予期しない動作
   - `[Feature]` - 新機能リクエスト
   - `[Inquiry]` - 質問・確認
   - `[Doc]` - ドキュメント改善

### プルリクエスト

1. リポジトリをフォーク
2. 機能ブランチを作成 (`git checkout -b feature/your-feature`)
3. 検証チェックリストに合格することを確認 (`/docs/validation/` 参照)
4. 明確な説明付きでPRを提出

## 重要規則（必須遵守）

本プロジェクトには厳格なアーキテクチャ制約があります。**違反は却下されます。**

| 規則 | 説明 |
|------|------|
| **Cause内空間変数禁止** | `x, y, z, distance` は因果コアで使用不可 |
| **因果ダイオード** | Π⁻¹（Effect→Cause）は厳禁 |
| **Write-Onlyログ** | ログを計算に読み戻すこと禁止 |
| **ω > 0** | 正の角速度を維持すること |

提出前に実行：**「全ての違反チェックして」**

## 質問

`[Inquiry]` タグ付きでIssueを作成してください。
