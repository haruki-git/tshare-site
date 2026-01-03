# Changelog
この変更履歴は Keep a Changelog 形式で記録します。:contentReference[oaicite:1]{index=1}  
（必要になったら SemVer を採用して v1.0.0 などの番号運用に移行できます）:contentReference[oaicite:2]{index=2}

## [Unreleased]
### Added
- （例）新しいツール／新ページ
### Changed
- （例）UIや導線の変更
### Fixed
- （例）バグ修正
### Security
- （例）ヘッダー強化、鍵管理の見直し

## [2026-01-03]
### Added
- Cloudflare Pages（GitHub連携）での公開フローを導入（push をトリガに自動反映）
- /var/www/html → /home/hi/tshare-site への同期 → commit/push を行う同期スクリプトを導入（tshare-pages-sync.sh）
- 記事生成（tshare-genba-weekly）後に pages-sync を実行し、記事・音声・index を Pages へ自動反映
- ITニュース用の top_news.json を Pages 側へ反映できるように運用を整理

### Changed
- 公開先の前提を「Dynamic DNS」から「Pages 配信」へ移行（案内文や運用の前提を更新）

### Fixed
- Pages 側で ITニュースが古いままになる問題を解消（生成物を /var/www/html/assets/top_news.json として反映 → 同期で push）

### Security
- GitHub Deploy key（SSH）を利用して自動 push を実現（鍵をリポジトリ単位で運用）
- SSH の Host エイリアス（github-tshare）で特定鍵のみ使用する設定を追加（~/.ssh/config）

