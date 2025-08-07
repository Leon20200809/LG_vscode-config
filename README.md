# ⚙️ VS Code 環境再現マニュアル（Windows専用）

この手順では、別のPCで **VS Code の設定をまるごと再現**できます。  
必要なファイルは以下の2つだけ！

- `settings.json`（VS Code の個人設定）
- `extensions.txt`（拡張機能の一覧）

---

## ✅ 再現手順（Windows）

### ① VS Code をインストール（未インストールの場合）

[https://code.visualstudio.com/](https://code.visualstudio.com/)  
から最新版をダウンロードしてインストール。

---

### ② 本リポジトリをクローンまたはZIPダウンロード

```bash
git clone https://github.com/yourname/vscode-config.git
cd vscode-config
```

または ZIP ダウンロードして展開。

---

### ③ `settings.json` を VS Code の設定フォルダにコピー

✅settings.jsonの場所
C:\Users\ユーザー名\AppData\Roaming\Code\User\settings.json

```bash
copy settings.json "%APPDATA%\Code\User\"
```

---

### ④ 拡張機能を一括インストール

```bash
cd C:\Users\あなたの名前\Downloads\vscode-config  # 例：拡張一覧があるフォルダへ移動
cat extensions.txt | xargs -n1 code --install-extension
```


---

## 🧠 補足メモ

- `phpcs` などグローバルCLIツールは別途セットアップが必要
- `composer global` で入れたツールのパスは、環境によって異なります
- VS Code の同期機能も併用すればさらにラク！


✅ 現在入ってる拡張機能の一覧を出力する：

```bash
code --list-extensions > extensions.txt
```
これが唯一の公式方法。

---

## 🎉 完了！

これでどのパソコンでも同じ環境でVSコードが使える！
