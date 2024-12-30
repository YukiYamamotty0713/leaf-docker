## 概要

英単語学習アプリ<br><br>
スクリーンショット1
![LeafCapture](src/img/LeafCapture.png)<br><br>
スクリーンショット2
![LeafCapture2](src/img/LeafCapture2.png)<br><br>
スクリーンショット3
![LeafCapture2](src/img/LeafCapture3.png)<br><br>

## フレームワーク/言語

Backend:Laravel/Inertia<br>
Frontend:Vue/TypeScript/TailwindCSS<br>

## テスト
PHPUnit

## 開発環境
WSL/DockerCompose/Apline

## Webサーバー
Nginx

## データベース
MySQL



## セットアップ手順

1:gitをインストール済み前提<br>
git clone https://github.com/YukiYamamotty0713/leaf-docker .

2:(Docker Desktop導入済み)<br>
docker-compose upを実行
コンテナの中でアプリソースをclone
(var/www/srcにて) git clone https://github.com/YukiYamamotty0713/leaf-app . を実行

3:サーバー側ライブラリ同期<br>
composer update

4:フロント側ライブラリ同期 およびビルド<br>
npm install & npm run build

5:ホットリロードモード:<br>
npm run dev


