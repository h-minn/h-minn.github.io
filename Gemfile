# frozen_string_literal: true

source "https://rubygems.org"

# ----------------------------------------
# Core Theme
# ----------------------------------------
gem "jekyll-theme-chirpy", "~> 7.3"

# ----------------------------------------
# Plugins
# ----------------------------------------
gem "jekyll-feed"
gem "jekyll-compose", group: :jekyll_plugins

# ----------------------------------------
# Development & Testing
# ----------------------------------------
group :test do
  gem "html-proofer", "~> 5.0"
end

# ----------------------------------------
# Windows Compatibility
# ----------------------------------------
platforms :mingw, :x64_mingw, :mswin, :jruby do
  gem "tzinfo", ">= 1", "< 3"
  gem "tzinfo-data"
end

gem "wdm", "~> 0.2.0", platforms: [:mingw, :x64_mingw, :mswin]
