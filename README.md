# MinecraftModShareingTool
いくつかのステップで簡単にMinecraftのMod環境を共有できるツール

# Note
[Releases](https://github.com/Rin-ot/MinecraftModShareingTool/releases/) からダウンロードするとPyinstallerで実行可能ファイル化しているのでウィルス判定で削除されることがあるかも。  
セルフコンパイルするかウィルス対策ソフトから除外して使ってください。

このアプリは[Cloudflare R2 Object Storage](https://www.cloudflare.com/ja-jp/developer-platform/products/r2/)に依存します  
Cloudflare R2 Object Storageの仕様上、ZIP圧縮後の累計総容量が10GBを超える場合従量課金制となります  
このアプリを使用して従量課金が発生した場合でも開発者は責任を負いません  

# 使い方
### 1: [Cloudflare](https://dash.cloudflare.com/sign-up) に登録。  
新規登録時に登録する目的は？みたいなアンケートが出ますが基本全スキップでOKです。  
※すでにCFのアカウントを持っている場合は省略して大丈夫です。  

### 2: サイドメニューの "Storage & databases" -> "R2 Object Storage" -> "Overview" の順に開きます。  
<img width="1834" height="906" scale="25%" alt="images" src="https://github.com/user-attachments/assets/84ef18dc-0097-49f0-bca0-0eeb042928e5" />

### 3: "Add R2 subscription to my account" を押して、決済情報を保存します。  
（既に決済情報を登録済みの場合、これは表示されないかも。）  
<img width="1335" height="703" scale="25%" alt="images" src="https://github.com/user-attachments/assets/259cf328-65f2-4541-8651-4dedf07937fa" />

### 4: 新しいバケットを作成する
<img width="1432" height="674" scale="25%" alt="images" src="https://github.com/user-attachments/assets/5c92096d-7290-40cf-a80b-6fede7f7a0f0" />

#### （ここで指定するバケット名は、Mod環境を共有される側のユーザに共有する必要のあるものです）
<img width="876" height="833" scale="25%" alt="images" src="https://github.com/user-attachments/assets/3eba1b1e-c9ea-4a70-8a42-c8d96b348e2d" />

### 5: バケット作成後、トークンの管理を開きます。
<img width="1432" height="674" scale="25%" alt="images" src="https://github.com/user-attachments/assets/6d1f9cad-4ac8-405f-ad24-bcfc9e8e8313" />

#### Account API トークンを発行します。
<img width="1268" height="606" scale="25%" alt="images" src="https://github.com/user-attachments/assets/6a6d2875-510b-4fef-ae03-420fbdfa235e" />

トークン名は自由、アクセス許可の設定は "オブジェクト読み取りと書き込み" 、バケットの指定には先ほど作成したバケットを選択します。
<img width="1279" height="764" scale="25%" alt="images" src="https://github.com/user-attachments/assets/c7ca40cc-1f57-4a1a-ba63-ef42796442b2" />

### 6: トークンを保存する
<img width="1269" height="848" scale="25%" alt="images" src="https://github.com/user-attachments/assets/b2e8a2ba-2ebc-4b4e-a24a-b0c17c15afa2" />

## :warning: このトークンを不用意に第三者が閲覧できる場所に投稿しないでください。  
悪意あるユーザがこれを取得した場合、悪戯に利用される可能性があります。

#### 無事トークンが発行出来たら、
- Endpoint URL: 最下部のURL
- Access Key ID: アクセス キー ID
- Secret Access Key: シークレット アクセス キー
- Bucket Name: 登録したバケットの名前
  
をMCMSの設定画面に入力して保存します。

### これで設定は完了です。
