# docker for macインストール
https://www.docker.com/products/docker#/mac
# ソース取得
# コマンド実行
## 初回
docker-compose run web rails new . --force --database=postgresql --skip-bundle
docker-compose build
docker-compose up
docker-compose run web bundle exec  rake db:create
## 2回目以降
docker-compose up
## migration、seed実行
docker-compose run web  bundle exec rake db:migrate
docker-compose run web bundle exec rake db:seed_fu
# ブラウザで確認
http://localhost:3000/
# 起動しない時
- tmp/pids/server.pidを削除してdocker-compose up
- 上のコマンドをdocker-compose buildから再度実行する
