# docs/ ディレクトリ

プロジェクトのドキュメントをライフサイクル管理付きで運用するための構造。

## ディレクトリ構成

```text
docs/
├── guides/           # 開発ガイド・ルール（ライフサイクル対象外）
├── adr/              # ADR（意思決定記録）
├── spec/             # 仕様書
├── research/         # 調査・分析
└── design-tokens/    # デザイントークン定義（ライフサイクル対象外）
```

## ライフサイクル

`adr/`, `spec/`, `research/` 配下のドキュメントには YAML frontmatter で `status` を持たせる。

| ステータス | 意味 |
| --- | --- |
| `wip` | 作成中・レビュー待ち |
| `accepted` | 承認済み・実装の根拠として有効 |
| `archive` | 廃止・過去の記録 |

詳細は [guides/document-lifecycle.md](guides/document-lifecycle.md) を参照。

## ドキュメントの作り方

1. 対象ディレクトリの `_template.md` をコピー
2. ファイル名を `NNNN-タイトル.md` に変更（例: `0002-auth-method.md`）
3. frontmatter を埋めて `status: wip` で作成
4. レビュー・承認後に `status: accepted` に変更

## AIツールとの連携

- AIツールは `status: accepted` のドキュメントのみを実装の根拠とする
- `wip` は明示的に指示がない限り実装に使わない
- 詳細は [guides/document-lifecycle.md](guides/document-lifecycle.md) を参照
