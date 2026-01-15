# **為替レート表示アプリ デプロイ手順 (GitHub Pages)**

このドキュメントでは、GitHub Pagesを使用してアプリケーションをインターネット上に公開する手順を説明します。

## **1\. 準備**

1. GitHubアカウントにログインします。  
2. index.html ファイルを手元に用意します。

## **2\. リポジトリの作成**

1. GitHubのヘッダー右上の「+」アイコンをクリックし、「New repository」を選択します。  
2. 以下の情報を入力します：  
   * **Repository name**: currency-exchange-app (任意の名前)  
   * **Public/Private**: Public を選択します（GitHub Pagesの無料枠利用のため）。  
   * **Initialize this repository with**: チェック不要です。  
3. 「Create repository」ボタンをクリックします。

## **3\. ファイルのアップロード**

作成したリポジトリの画面が表示されたら、以下の手順でファイルをアップロードします。

1. 「...or create a new repository on the command line」などのオプションが表示されていますが、画面内のリンク **「uploading an existing file」** をクリックします。  
2. index.html をドラッグ＆ドロップエリアに配置します。  
3. アップロードが完了したら、ページ下部の "Commit changes" 欄で「Add index.html」などのコメントを入力し、「Commit changes」ボタンをクリックします。

## **4\. GitHub Pagesの設定**

1. リポジトリのメニュータブから **「Settings」** をクリックします。  
2. 左側のサイドバーメニューから **「Pages」** をクリックします。  
3. **"Build and deployment"** セクションで以下を設定します：  
   * **Source**: Deploy from a branch を選択。  
   * **Branch**: main (または master) を選択し、フォルダは /(root) のままにします。  
4. **「Save」** ボタンをクリックします。

## **5\. 公開の確認**

1. 設定を保存すると、ページ上部に「GitHub Pages source saved.」と表示されます。  
2. 数分待つと（通常1〜3分）、再度ページをリロードした際に、上部に以下のメッセージが表示されます。**Your site is live at https://\[ユーザー名\].github.io/currency-exchange-app/**  
3. 表示されたURLをクリックして、アプリケーションが正しく動作することを確認してください。

## **トラブルシューティング**

* **ページが404エラーになる場合**: 反映に時間がかかっている可能性があります。5分ほど待ってからリロードしてください。  
* **デザインが崩れている場合**: index.html 内の Tailwind CSS のCDNリンク (https://cdn.tailwindcss.com) が正しく読み込まれているか、ブラウザの開発者ツールでコンソールエラーが出ていないか確認してください。