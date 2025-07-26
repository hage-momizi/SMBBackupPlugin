# SMBBackupPlugin
SMBサーバーへバックアップをします / Back up to an SMB server

# 🌐 Nebulix SMBBackupPlugin - Paper 1.20～1.21対応 SMBバックアッププラグイン

**Nebulix SMBBackupPlugin** は、SMB（Samba）サーバーにワールドデータや任意のディレクトリを  
**自動・手動でバックアップできる**、**Paper 1.20～1.21対応**の高機能バックアッププラグインです。

[ダウンロード](https://github.com/hage-momizi/SMBBackupPlugin/releases/tag/Latest)

---

## ✨ 主な機能

✅ **SMBサーバーへの自動・手動バックアップ**  
✅ **cron形式によるスケジュールバックアップ**  
✅ **ワールドや複数の任意ディレクトリに対応**  
✅ **`/backup now` による即時バックアップ**  
✅ **バックアップ前に「推定時間・ファイル数・サイズ」を表示**  
✅ **SMBサーバーの空き容量（クオータ）チェックと警告**  
✅ **`/backup reload`, `/backup status` など便利なコマンド**  
✅ **Paper 1.20.x～1.21.x対応**

---

## 📄 ライセンスと利用条件

© 2025 **MomiziDC**

本プラグイン **「Nebulix SMBBackupPlugin」** は、MomiziDC によって開発されました。

以下の条件に同意する場合に限り、本プラグインを使用できます：

1. 本プラグインの **改変、逆コンパイル、リバースエンジニアリングを禁止** します。  
2. 本プラグインの **再配布（配布・転載）を禁止** します。  
3. 本プラグインの **ソースコードの公開は行っていません**。

> ⚠️ このライセンスに同意できない場合は、本プラグインを使用しないでください。

---

## ⚙️ インストール方法

1. ダウンロードした `.jar` ファイルを `plugins` フォルダに設置  
2. サーバーを起動し、自動生成される `config.yml` を編集  
3. 必要に応じて `/backup reload` コマンドで設定を再読み込み  

---

## 🛠️ 設定例（`config.yml`）

```yaml
smb:
  # SMBサーバーのIPアドレスまたはホスト名
  address: "192.168.1.100"

  # SMBユーザー名
  username: "your_username"

  # SMBパスワード
  password: "your_password"

  # 共有名
  share: "backup_share"

  # リモートディレクトリ（共有内のパス）
  remoteDir: "minecraft_backup"

backup:
  # バックアップの保存先ディレクトリ
  directories:
    - ./world

schedule:
  # スケジュールバックアップを有効にするか
  enabled: true
  cron: "0 2 * * *"  # デフォルト: 毎日午前2時
