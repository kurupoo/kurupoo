# AGENTS.md

このファイルは Codex (codex.ai) 向けのガイダンスである。

- **CLAUDE.md と AGENTS.md は互いのツインであり、内容は宛先行を除いて同一に保つこと。**
  片方を更新したら、必ずもう一方も同じ内容に揃えること。宛先の違いだけが差分で、
  それ以外に差を作らないこと（CLAUDE.md は Claude Code 宛て、AGENTS.md は Codex (codex.ai) 宛て）。
- 応答・コメント・コミットメッセージは日本語でよい。バッジの識別子・URL・console ブロックの
  英文はそのまま英語で扱う。

## これは何か

GitHub の**プロフィール README リポジトリ**（`kurupoo/kurupoo`。ユーザー名と同名の特別なリポジトリで、
`README.md` がプロフィールページの先頭に表示される）。**成果物は実質 `README.md` 1 枚のみ**で、
ビルドもテストもアプリケーションコードも存在しない。「編集」とはほぼ常に `README.md` の中身を
いじることを指す。

## README の構成

ターミナル/コンソール風の見た目で統一されている。GitHub のダークテーマ配色を基調とし、
アクセントは緑（`3FB950`）、背景は `0D1117` / `161B22`、補助色に黄系（`D29922`）を使う。
この配色は全パーツで揃えること。

セクションは疑似シェルのプロンプト見出し（`$ whoami` / `$ cat ~/.stack` / `$ git log --stat` /
`$ exit`）で区切られる。上部の ASCII アートは "KURUPOO" のバナー。

外部サービスに依存する動的パーツ:

| 種別 | サービス | 用途 |
|---|---|---|
| タイピング SVG | `readme-typing-svg.demolab.com` | 冒頭のプロンプト演出と末尾の `logout` |
| バッジ | `img.shields.io`（`style=flat-square`） | 連絡先リンク・技術スタック表示 |
| 訪問者カウンタ | `komarev.com/ghpvc` | visitors |
| 統計カード | `github-stats-extended.vercel.app`（`/api` と `/api/top-langs`） | コミット統計・言語割合 |
| ストリーク | `streak-stats.demolab.com` | 連続コントリビュート |
| アクティビティグラフ | `github-readme-activity-graph.vercel.app` | 活動推移 |

カード類の URL はいずれも `username=kurupoo` と配色パラメータ（`bg_color=0D1117`,
`title_color=3FB950` など）を持つ。配色を変えるときはカード間で一貫させること。

## 編集時の慣習・方針

過去のコミットが繰り返し守ってきた方針。踏襲すること。

- **技術スタックは実際のリポジトリ内容に合わせる。誇張しない。** 過去に、実体のない
  Docker / Cloudflare / Python / TypeScript / Neovim といったバッジや、GitHub が言語として
  検知していない JavaScript バッジが削除された（`44d250e` / `386c2c2`）。スタックのバッジを
  足すときは、それを裏付けるリポジトリ/言語が実在するか確認すること。
- **バッジの img は必ず `<div>` で囲む。** 囲まないと img 1 行ごとに段落化されて縦積みになる
  （`386c2c2`）。README 内のコメントにもこの注意が明記されている。
- **AWS バッジはロゴ指定なし。** Simple Icons から Amazon のマークが削除され、shields.io に
  存在しないため（`386c2c2`）。ロゴ付きに「直す」と壊れる。
- **統計カードは `github-stats-extended` を使う。** 本家 `anuraghazra/github-readme-stats` は
  非推奨となり公開インスタンスが停止したため、維持されている後継に移行した（`b720a3e`）。
  パラメータ互換なので、古い `github-readme-stats.vercel.app` に戻さないこと。

## 注意点

- **外部カードサービスは水物**。公開インスタンスの停止・非推奨化・ロゴの欠落が起きるので、
  「表示が壊れた」報告はまず参照先サービスの生死を疑う（本家 stats の停止・Amazon ロゴ削除は
  いずれも上流側の変更だった）。
- README は日本語と英語（console ブロック内）が混在する。演出テキストの英文と、
  `消すのが仕事。` のような日本語コピーの両方があるので、トーンを崩さないこと。
- このリポジトリでは git 操作（commit / push / PR）を勝手に行わないこと。編集は
  `README.md` の変更にとどめる。
