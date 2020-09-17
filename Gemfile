source 'https://rubygems.org'
git_source(:github) { |repo| "https://github.com/#{repo}.git" }

ruby '2.7.1'

# Bundle edge Rails instead: gem 'rails', github: 'rails/rails'
gem 'rails', '~> 6.0.3', '>= 6.0.3.3' # https://rubyonrails.org
# Use postgresql as the database for Active Record
gem 'pg', '>= 0.18', '< 2.0' # https://github.com/ged/ruby-pg
# Use Puma as the app server
gem 'puma', '~> 4.1' # http://puma.io
# Use SCSS for stylesheets
gem 'sass-rails', '>= 6' # https://github.com/rails/sass-rails
# Transpile app-like JavaScript. Read more: https://github.com/rails/webpacker
gem 'webpacker', '~> 4.0' # https://github.com/rails/webpacker
# Turbolinks makes navigating your web application faster. Read more: https://github.com/turbolinks/turbolinks
gem 'turbolinks', '~> 5' # https://github.com/turbolinks/turbolinks
# Build JSON APIs with ease. Read more: https://github.com/rails/jbuilder
gem 'jbuilder', '~> 2.7' # https://github.com/rails/jbuilder
# Use Redis adapter to run Action Cable in production
# gem 'redis', '~> 4.0'
# Use Active Model has_secure_password
# gem 'bcrypt', '~> 3.1.7'

# Use Active Storage variant
# gem 'image_processing', '~> 1.2'

# Reduces boot times through caching; required in config/boot.rb
gem 'bootsnap', '>= 1.4.2', require: false # https://github.com/Shopify/bootsnap

group :development, :test do
  # Call 'byebug' anywhere in the code to stop execution and get a debugger console
  gem 'byebug', platforms: [:mri, :mingw, :x64_mingw] # https://github.com/deivid-rodriguez/byebug
end

group :development do
  # Access an interactive console on exception pages or by calling 'console' anywhere in the code.
  gem 'web-console', '>= 3.3.0' # https://github.com/rails/web-console
  gem 'listen', '~> 3.2' # https://github.com/guard/listen
  # Spring speeds up development by keeping your application running in the background. Read more: https://github.com/rails/spring
  gem 'spring' # https://github.com/rails/spring
  gem 'spring-watcher-listen', '~> 2.0.0' # https://github.com/jonleighton/spring-watcher-listen
end

# Windows does not include zoneinfo files, so bundle the tzinfo-data gem
gem 'tzinfo-data', platforms: [:mingw, :mswin, :x64_mingw, :jruby] # https://tzinfo.github.io

gem 'awesome_print' # https://github.com/awesome-print/awesome_print
gem 'bootstrap', '~>4.5' # https://github.com/twbs/bootstrap-rubygem
gem 'devise', '~> 4.7', '>= 4.7.1' # https://github.com/heartcombo/devise
gem 'font-awesome-sass', '~> 5.13' # https://github.com/FortAwesome/font-awesome-sass
gem 'haml-rails', '~> 2.0' # https://github.com/indirect/haml-rails
gem 'rack-timeout' # https://github.com/sharpstone/rack-timeout
group :development do
  gem 'annotate' # http://github.com/ctran/annotate_models
  gem 'annotate_gem' # https://github.com/ivantsepp/annotate_gem
  gem 'guard' # http://guardgem.org
  gem 'guard-brakeman', require: false # https://github.com/guard/guard-brakeman
  gem 'guard-haml_lint' # https://github.com/yatmsu/guard-haml-lint
  gem 'guard-livereload', require: false # https://rubygems.org/gems/guard-livereload
  gem 'guard-process'
  gem 'guard-reek' # https://github.com/grantspeelman/guard-reek
  gem 'guard-rspec' # https://github.com/guard/guard-rspec
  gem 'guard-rubocop' # https://github.com/yujinakayama/guard-rubocop
  gem 'html2haml' # http://haml.info
  gem 'meta_request' # https://github.com/dejan/rails_panel/tree/master/meta_request
  gem 'prettier' # https://github.com/prettier/plugin-ruby#readme
  gem 'rack-livereload' # https://github.com/onesupercoder/rack-livereload
  gem 'rails_layout' # http://github.com/RailsApps/rails_layout/
  gem 'rubocop' # https://github.com/rubocop-hq/rubocop
  gem 'spring-commands-rspec' # https://github.com/jonleighton/spring-commands-rspec
  gem 'terminal-notifier' # https://github.com/julienXX/terminal-notifier
  gem 'terminal-notifier-guard' # https://github.com/Springest/terminal-notifier-guard
end

group :test do
  gem 'factory_bot_rails' # https://github.com/thoughtbot/factory_bot_rails
  gem 'faker' # https://github.com/faker-ruby/faker
  gem 'selenium-webdriver' # https://github.com/SeleniumHQ/selenium
  gem 'simplecov' # https://github.com/simplecov-ruby/simplecov
  gem 'simplecov-lcov' # http://github.com/fortissimo1997/simplecov-lcov
end

group :development, :test do
  gem 'pry-byebug' # https://github.com/deivid-rodriguez/pry-byebug
  gem 'pry-rails' # https://github.com/rweng/pry-rails
  gem 'rspec-rails' # https://github.com/rspec/rspec-rails
  gem 'rubocop-rspec' # https://github.com/rubocop-hq/rubocop-rspec
  gem 'shoulda-matchers', '~> 4.4' # https://matchers.shoulda.io/
end
