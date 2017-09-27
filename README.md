# README

## Prerequisites
* Ruby: 2.4.0p0
* Rails: 5.1.4
* PostgreSQL: 9.3

## Prepared Rails for BDD
### Skip unit test, bundle and used PostgreSQL
```
rails new rails-bdd -T --skip-test-unit, -B --skip-bundle, -d postgresql
```

### Install gem locally
```bash
bundle install --path vendor/bundle
```

### Add Rspec Rails gem to Gemfile
```bash
group :development, :test do
  gem 'rspec-rails'
end
```
#### Install gem locally
```bash
bundle install --path vendor/bundle
```
#### Bootstrap the application with RSpec
```bash
bundle exec rails generate rspec:install
```

* Ruby version

* System dependencies

* Configuration

* Database creation

* Database initialization

* How to run the test suite

* Services (job queues, cache servers, search engines, etc.)

* Deployment instructions

* ...