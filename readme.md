### 概要
英単語学習アプリ「Leaf」の環境構築リポジトリです。  
Leafはシンプルながらも機能豊富な設計を採用し、効率的かつ効果的な英単語学習をサポートします。最新のWeb技術とデザイン原則を取り入れることで、直感的な操作性と高いパフォーマンスを両立しています。

**webサーバー：** Nginx

### 使用している技術
- **環境構築： ** Docker-compose (PHP, Nginx, MySQL, Redis)
- **バックエンド：** Laravel  
- **フロントエンド：** Vue、Typescript、TailwindCSS  
- **データベース：** MySQL  
- **外部API：** GeminiAPI

### 環境構築手順
1. **リポジトリのクローン**  
   Gitを使用してリポジトリをクローンしてください。  
   ```bash
   git clone https://github.com/YukiYamamotty0713/leaf-docker .
   ```

2. **依存関係のインストール**  
   - **バックエンド（Laravel）の依存関係のインストール：**  
     ```bash
     composer install
     ```  
   - **フロントエンドの依存関係のインストール：**  
     ```bash
     npm install
     ```

3. **環境変数の設定**  
   プロジェクトルートにある `.env.example` ファイルをコピーして `.env` ファイルを作成し、必要な設定値（データベース接続情報、APIキーなど）を記入してください。  
   ```bash
   cp .env.example .env
   ```  
   その後、Laravelアプリケーションキーを生成します:  
   ```bash
   php artisan key:generate
   ```

4. **Dockerによる環境構築（オプション）**  
   Docker環境を利用する場合、以下のコマンドでコンテナを起動してください:  
   ```bash
   docker-compose up -d
   ```

5. **アプリケーションの起動**  
   - **ローカルサーバーでの起動（Laravelの場合）：**  
     ```bash
     php artisan serve
     ```  
   - **Docker環境の場合：**  
     設定されたポートでアクセス可能になります。



問題や疑問が発生した場合は、Issueトラッカーにて申し立ていただけると幸いです
