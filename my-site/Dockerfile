# ベースイメージ
FROM klakegg/hugo:ext-alpine AS build

# 作業ディレクトリの設定
WORKDIR /app

# プロジェクトのソースコードをコピー
COPY . /app

# サイトのビルド（`public/`を生成）
RUN hugo --minify

# ランタイムイメージ
FROM nginx:alpine

# 公開ディレクトリをNginxのHTMLルートにコピー
COPY --from=build /app/public /usr/share/nginx/html

# Nginxを起動
EXPOSE 80
CMD ["nginx", "-g", "daemon off;"]
