source "https://rubygems.org"

# Use github-pages gem for GitHub Pages compatibility
gem "github-pages", group: :jekyll_plugins

# Windows and JRuby does not include zoneinfo files, so bundle the tzinfo-data gem
# and associated library
platforms :windows, :jruby do
  gem "tzinfo-data"
end

# Lock jekyll version for compatibility with github-pages
gem "jekyll", "~> 3.9.3"

# Required standard library gems that are not included in Ruby 3.4+
gem "csv"
gem "fiddle"
gem "ostruct"

# Windows specific gems
platform :windows do
  gem "wdm", ">= 0.1.0"
  gem "webrick"
end

# Additional dependencies
gem "faraday-retry"

# If you have any plugins, put them here!
group :jekyll_plugins do
  gem "jekyll-paginate"
  gem "jekyll-sitemap"
  gem "jekyll-gist"
  gem "jekyll-feed"
  gem "jemoji"
  gem "jekyll-include-cache"
  gem "jekyll-algolia"
end