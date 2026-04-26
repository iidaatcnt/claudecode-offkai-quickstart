# クロコ Mac インストール 特急チェックシート（スタッフ用）

---

## 受け取り前
- [ ] **再起動してから**渡してもらう

---

## ターミナルで確認

```bash
# 起動時間（再起動済みか）
last reboot | head -1

# クロコのインストール状況＋バージョン
ls -ld /Applications/Claude.app 2>/dev/null && defaults read /Applications/Claude.app/Contents/Info.plist CFBundleShortVersionString || echo "❌ 未インストール"

# OSバージョン
sw_vers -productVersion

# アップデート確認（時間かかるので先に流す）
softwareupdate -l
```

- [ ] 起動時間が今日 → OK　／　古い → 再起動してもらう
- [ ] クロコ：インストール済み → **「クロコのインストール」をスキップ**
- [ ] OS：マイナーアップデートがあれば実施（メジャーバージョンアップは対象外、後日自分で）

```bash
# マイナー・セキュリティアップデートのみ（メジャーOSアップグレードは行わない）
softwareupdate -ia
```

---

## Git ＆ Xcode 確認

```bash
git --version
xcode-select --install
```

- [ ] `git version x.x.x` が表示された → OK
- [ ] Xcode のダイアログが出た → 「インストール」を押して待つ

---

## クロコのインストール

- [ ] `https://claude.ai/download` を開く
- [ ] **macOS (Apple Silicon)** を選んでダウンロード
- [ ] `.dmg` を開いて Applications フォルダにドラッグ

---

## 後始末・動作確認

```bash
# 作業フォルダ作成（ユーザーフォルダ直下・日付フォルダ）
mkdir -p ~/ClaudeCodeFolder/$(date +%Y%m%d)
```

- [ ] Applications フォルダから Claude を起動できた
- [ ] **Dock に追加**（Dock のアイコンを右クリック → オプション → Dock に追加）
- [ ] デスクトップの `.dmg` アイコンを取り出した（右クリック → 取り出す）
- [ ] ダウンロードフォルダの `.dmg` を削除した
- [ ] `~/ClaudeCodeFolder/YYYYMMDD/` フォルダができているのを確認

---

## 動作確認

- [ ] **チャット**モードで「こんにちは」→ 返事が来た
- [ ] **Code** モードに切り替えた
- [ ] Code モードで `~/ClaudeCodeFolder/YYYYMMDD/` を開いた
- [ ] 簡単な動作確認（例：「test.txtを作って」）

---

## Claude in Chrome のインストール

- [ ] Chrome ウェブストアで「Claude」を検索してインストール
- [ ] Anthropic アカウントでログイン
- [ ] デモをスキップしてホーム画面を確認

---

## 完了 🎉

*スタッフ用 特急版 v1.1*
