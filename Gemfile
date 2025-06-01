# frozen_string_literal: true

source "https://rubygems.org"

# Theme
gem "jekyll-theme-chirpy", "~> 7.3"

# Development and testing tools
gem "html-proofer", "~> 5.0", group: :test
gem "jekyll-compose", group: :jekyll_plugins

# Windows compatibility
platforms :mingw, :x64_mingw, :mswin, :jruby do
  gem "tzinfo", ">= 1", "< 3"
  gem "tzinfo-data"
end

gem "wdm", "~> 0.2.0", :platforms => [:mingw, :x64_mingw, :mswin]
