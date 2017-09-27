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
#### Install Rspec Rails gem
```bash
bundle
```
#### Bootstrap the application with RSpec
```bash
bundle exec rails generate rspec:install
```
### Add Shoulda Matchers gem to Gemfile
```bash
group :test do
  gem 'shoulda-matchers'
end
```
#### Configure Shoulda Matchers gem
Add the following block to the end of `spec/rails_helper.rb`
```bash
Shoulda::Matchers.configure do |config|
  config.integrate do |with|
    with.test_framework :rspec
    with.library :rails
  end
end
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