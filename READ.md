# make project

example

## web with database
docker-compose run web bundle exec rails new . --force --database=mysql

## api
docker-compose run web bundle exec rails new . --force --api -T -C -M -O -S –skip-turbolinks --skip-action-mailbox --skip-action-text