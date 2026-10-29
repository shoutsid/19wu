# -*- coding: utf-8 -*-
#
# Some gems cannot/should not be installed on heroku and/or travis, but
# `bundle --without` cannot be used. Put these gems into group :development
# in such situations
# should work until heroku changes the HOME directory location
is_heroku = ['/app/','/app'].include?(ENV['HOME']) # ENV['HOME'] = '/app' in rails console or rake
sqlite3_group = is_heroku ? :development : :sqlite3
mysql2_group = is_heroku ? :development : :mysql2

# Uncomment following lines to deploy 19wu to heroku
# https://devcenter.heroku.com/articles/rails4
# ruby '2.0.0'
# gem 'rails_12factor', group: :production

if ENV['TRAVIS']
  source 'https://rubygems.org'
else
  source 'https://rubygems.org'
end

# if not encoding, `bundle install` command would be error. (Invalid byte sequence in GBK)
# see http://bit.ly/12VbO9n
if RUBY_VERSION =~ /1.9/
  Encoding.default_external = Encoding::UTF_8
  Encoding.default_internal = Encoding::UTF_8
end

gem 'rails', '4.0.13'
gem 'slim-rails', '~> 1.1.1'
gem 'simple_form', '~> 3.0.0.rc'
gem 'ransack'
gem 'html-pipeline'
# html-pipeline depends on escape_utils, lock its version for Windows
gem 'escape_utils', '0.2.4'
gem 'has_html_pipeline'
gem 'kramdown', :platform => [:jruby]
gem 'gravtastic'
gem "cancancan", "~> 1.15.0"
gem 'cohort_me'
gem 'acts_as_follower', git: 'https://github.com/flingbob/acts_as_follower.git', ref: '28a1f3f98ba7965a9b546aad8fdac325927989ee'
gem "angularjs-rails"
gem "rabl"
gem 'whenever', :require => false
gem "tabs_on_rails"
gem "china_sms"
gem 'china_city'
gem 'alipay', git: 'https://github.com/saberma/alipay.git', ref: '356eff558c1efcf3cf635710eaabc95d2d183445'
gem 'priceable', git: 'https://github.com/saberma/priceable.git', ref: '72f6322f798353ae2d740306bf4d38563a21e631' # fixed: migration break.
gem 'jbuilder'
gem 'state_machine'
gem 'state_machine-audit_trail'
gem 'axlsx_rails'

group :pg do
  gem 'pg', :platform => [:ruby, :mswin, :mingw]
  gem 'activerecord-jdbcpostgresql-adapter', :platform => [:jruby]
end

group sqlite3_group do
  gem 'sqlite3'
end

group mysql2_group do
  gem 'mysql2', '0.3.11'
end

gem "devise", "~> 3.0.0"
gem 'devise_invitable', git: 'https://github.com/scambra/devise_invitable.git', ref: '9e5a9a7e0e5ad489206386865efdfca5b87de62b'
gem 'settingslogic'
gem "delayed_job", "~> 4.0.0.beta2"
gem 'delayed_job_active_record', '~> 4.0.0.beta3'
gem 'daemons'
gem "carrierwave", "~> 0.9.0"
gem 'friendly_id', git: 'https://github.com/norman/friendly_id.git', branch: 'master'
gem 'mini_magick', '3.5.0'
gem 'rails-timeago'

group :production do
  # Use unicorn as the app server
  gem 'unicorn', :platforms => :ruby
  gem 'exception_notification'
end

group :development do
  gem 'rvm-capistrano', require: false
  gem 'mails_viewer'
  gem 'quiet_assets'
  gem 'guard-delayed', git: 'https://github.com/jasl/guard-delayed.git', ref: 'd7bb1b89263b321917fb0084fbd255cf90c556a1'
  gem 'guard-rails'
  gem 'guard-zeus'

  # Export state_machine transition diagram
  gem 'ruby-graphviz', :require => 'graphviz'
end

group :development, :test do
  gem "rspec-rails", "~> 2.14.0"
  gem 'jasmine-rails', git: 'https://github.com/searls/jasmine-rails.git', ref: 'd1140c3a6ba6947af0df3c865198b3555640b5c6'
  gem 'factory_girl_rails', '~> 4.0' # generator will use it in development.
  gem 'thin', '~> 1.5.0', :platform => [:ruby, :mswin, :mingw] # thin cannot run under jruby
  gem 'pry-rails'
  gem 'pry-nav'
  gem 'guard-livereload'
end

group :test do
  gem 'capybara'
  gem 'capybara-email'
  gem "database_cleaner", "~> 1.0"
  gem 'selenium-webdriver'
  gem 'poltergeist'
  gem 'simplecov', :require => false
  gem 'coveralls', require: false
  gem 'timecop'
end

# group :assets do
gem "sass-rails", "~> 4.0.5"
gem 'coffee-rails',   '~> 4.0.0'
gem 'bootstrap-sass', '~> 2.3.2.0'
gem 'uglifier',       '>= 1.3.0'
gem 'jquery-rails'
gem 'bootstrap-datepicker-rails'
gem 'jquery-fileupload-rails'
gem 'bootstrap-timepicker-rails-addon'

  # 推荐安装 node.js，而不要 therubyracer
  #gem 'libv8', '3.11.8.3', :platforms => :ruby # therubyracer 从 0.11 开始没有依赖 lib8. http://git.io/EtMkCg
  #gem 'therubyracer', :platforms => :ruby
# end

# fallback
gem 'rails-observers'
gem "mimemagic", "= 0.3.9"
