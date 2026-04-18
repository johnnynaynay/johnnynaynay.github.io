source "https://rubygems.org"

# Use Jekyll 4 for better performance and features
gem "jekyll", "~> 4.4.1"

group :jekyll_plugins do
  gem "jekyll-feed", "~> 0.12"
  gem "jekyll-toc"
end

# Windows compatibility
platforms :mingw, :x64_mingw, :mswin, :jruby do
  gem "tzinfo", ">= 1", "< 3"
  gem "tzinfo-data"
  gem "wdm", "~> 0.1"
end

gem "http_parser.rb", "~> 0.6.0", :platforms => [:jruby]
