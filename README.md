# make project

example
## web with database
docker-compose run web bundle exec rails new . --force --database=mysql

## api with no database
docker-compose run web bundle exec rails new . --force --api -T -C -M -O -S –skip-turbolinks --skip-action-mailbox --skip-action-text

# add rspec
## mod Gemfile
```
group :development, :test do
  gem "rspec-rails"
  gem "factory_bot_rails"
end
```
## bundle install
```
docker-compose build
```
## rspec install
```
docker-compose run web bundle exec rails generate rspec:install
```
## set rspec generated file settings
`config/application.rb`
```
config.generators do |g|
  g.test_framework :rspec, 
        request_spec: true,
        model_spec: true,
        view_specs: false, 
        helper_specs: false, 
        controller_specs: false, 
        routing_specs: false
end
```
## set factory bot settings
`spec/rails_helper.rb`
```
RSpec.configure do |config|
+  config.include FactoryBot::Syntax::Methods
end
```
