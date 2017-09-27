# README
[![Build Status](https://semaphoreci.com/api/v1/fybwid/rails-bdd/branches/master/shields_badge.svg)](https://semaphoreci.com/fybwid/rails-bdd)
[![Build Status](https://travis-ci.org/fybwid/rails-bdd.svg?branch=master)](https://travis-ci.org/fybwid/rails-bdd)
[ ![Codeship Status for fybwid/rails-bdd](https://app.codeship.com/projects/eeb4b470-8579-0135-763e-229a8d5fb755/status?branch=master)](https://app.codeship.com/projects/247933)
[![Coverage Status](https://coveralls.io/repos/github/fybwid/rails-bdd/badge.svg?branch=master)](https://coveralls.io/github/fybwid/rails-bdd?branch=master)

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
### Added Cucumber gem
```bash
group :test do
  gem 'shoulda-matchers'
  gem 'cucumber-rails', require: false
  gem 'database_cleaner'
end
```
#### Install Cucumber gem
```bash
bundle
```
### Bootstrap the application with Cucumber
```bash
rails generate cucumber:install
```

## Testing
### Running all test (RSpec and Cucumber)
`bundle exec rake ci:tests`
### RSpec
#### Single test
`rspec spec/models/post_spec.rb`
#### All test
`rspec`

### RSpec
#### Single test
`cucumber features/home_page.feature`
#### All test
`cucumber`
* Ruby version

* System dependencies

* Configuration

* Database creation

* Database initialization

* How to run the test suite

* Services (job queues, cache servers, search engines, etc.)

* Deployment instructions

* ...