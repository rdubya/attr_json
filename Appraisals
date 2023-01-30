appraise "rails-6-0" do
  gem 'combustion', "~> 1.0"

  gem "rails", ">= 6.0.0", "< 6.1"
  gem "pg", "~> 1.0"
  gem "rspec-rails", "~> 5.0"
end

appraise "rails-6-1" do
  gem 'combustion', "~> 1.0"

  gem "rails", "~> 6.1.0"
  gem "pg", "~> 1.0"

  # sprockets-rails is already a rails 6.1 dependency, but combustion is failing
  # to require it, this is one way to get it required.
  # https://github.com/pat/combustion/issues/128
  gem "sprockets-rails"
end

appraise "rails-7-0" do
  gem 'combustion', "~> 1.0"

  gem "rails", "~> 7.0.0"
  gem "pg", "~> 1.0"
end

appraise "rails-edge" do
  # need combustion edge to work with rails edge, will no longer
  # be true on next combustion release, probably no later than Rails 7.1
  # https://github.com/pat/combustion/pull/126
  gem 'combustion', "~> 1.0", github: "pat/combustion"

  gem "rails", git: "https://github.com/rails/rails.git", branch: "main"
  gem "pg", "~> 1.0"

  # Edge rails, future Rails 7.1 currently allows rack 3 -- but rails itself
  # and some of our other dependencies may not actually work with rack 3 yet,
  # let's test under rack 2. (Nothing in this gem deals with levels as low as rack)
  #
  # Bundler was having trouble resolving unless we specified rackup and rack-session
  # limits too, I think it was a bundler failure, we actually only care about
  # rack < 3 here.
  gem "rack", "~> 2.0"
  gem "rackup", "< 2"
  gem "rack-session", "< 2"
end
