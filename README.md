cucumber_in_groups
==================

Splits your cucumber features into groups to run them separately.

Usage
=====

In your Gemfile

    gem "cucumber_in_groups", :git => "git@github.com:vovayartsev/cucumber_in_groups.git"


Then add this line to your cucumber.yml

    ci: <%= std_opts %> --tags ~@unstable  --tags ~@noci  <%=ENV["FEATURES"] %>


Then in Semaphore test script, use GROUP environment variable. Group
numbers are 1-based (e.g. 1of3, 2of3, 3of3)

    RAILS_ENV=test GROUP=1of2 bundle exec rake cucumber:ci
