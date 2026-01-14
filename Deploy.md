# **為替レート表示アプリ デプロイ手順書**

このドキュメントでは、作成したアプリケーションをGitHub Pagesを利用してWeb上に公開する手順を説明します。

## **事前準備**

* GitHubアカウント  
* GitがインストールされたPC（またはGitHub DesktopなどのGUIツール）

## **手順 1: リポジトリの作成**

1. GitHubにログインします。  
2. 画面右上の「+」アイコンをクリックし、**New repository** を選択します。  
3. **Repository name** に任意の名前を入力します（例: exchange-rate-app）。  
4. Public（公開）が選択されていることを確認します（GitHub Pagesの無料枠利用のため）。  
5. **Create repository** ボタンをクリックします。

## **手順 2: ファイルの準備とアップロード**

このプロジェクトは単一の index.html ファイルで構成されていますが、GitHub Pagesはこれを認識してWebサイトとして表示します。

### **方法A: Webブラウザから直接アップロードする場合（簡単）**

1. 作成したリポジトリの画面にある **uploading an existing file** のリンクをクリックします。  
2. 作成した index.html ファイルをドラッグ＆ドロップします。  
3. ページ下部の "Commit changes" 欄に適当なメッセージ（例: Initial commit）を入力し、**Commit changes** ボタンをクリックします。

### **方法B: コマンドライン（Git）を使用する場合**

ローカルでフォルダを作成し、そこに index.html を保存してから以下のコマンドを実行します。

\# ユーザー名とリポジトリ名は適宜変更してください  
git init  
git add index.html  
git commit \-m "Initial commit"  
git branch \-M main  
git remote add origin \[https://github.com/あなたのユーザー名/exchange-rate-app.git\](https://github.com/あなたのユーザー名/exchange-rate-app.git)  
git push \-u origin main

## **手順 3: GitHub Pages の設定**

1. リポジトリのページ上部にある **Settings** タブをクリックします。  
2. 左サイドバーのメニューから **Pages** をクリックします。  
3. **Build and deployment** セクションの **Source** が "Deploy from a branch" になっていることを確認します。  
4. **Branch** の設定で、main (または master) ブランチを選択し、フォルダは /(root) のままにして **Save** をクリックします。

## **手順 4: 公開の確認**

1. 設定を保存して数分待つと、ページ上部に以下のようなメッセージが表示されます。Your site is live at https://www.google.com/search?q=https://%E3%81%82%E3%81%AA%E3%81%9F%E3%81%AE%E3%83%A6%E3%83%BC%E3%82%B6%E3%83%BC%E5%90%8D.github.io/exchange-rate-app/  
2. 表示されたURLをクリックして、アプリケーションが正しく表示されるか確認してください。

## **トラブルシューティング**

* **ページが404エラーになる**: デプロイ処理に数分かかる場合があります。5分ほど待ってからリロードしてください。  
* **スタイルが崩れている**: Tailwind CSSをCDN経由で読み込んでいるため、インターネット接続が必要です。

## **ソースコード構成について**

本プロジェクトは学習・デプロイの簡易化のため単一ファイル (index.html) に統合されていますが、将来的に拡張する場合は以下のようにファイルを分割することを推奨します。

* index.html: 構造のみ  
* styles.css: \<style\>タグの中身を移動  
* app.js: \<script\>タグの中身を移動  
* data.json: 通貨データを外部ファイル化（fetchAPI等で読み込み）