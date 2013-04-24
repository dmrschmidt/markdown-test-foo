# BlueShell [![Gem Version](https://badge.fury.io/rb/blue-shell.png)](http://badge.fury.io/rb/blue-shell)

Friendly command-line test runner and matchers for shell scripting in ruby using RSpec.

## Installation

With Bundler, add the following to your Gemfile:

```ruby
group :test do
  gem "blue-shell"
end
```

Then require and configure BlueShell in your `spec_helper.rb`:

```ruby
require 'blue-shell'

RSpec.configure do |c|
  c.include BlueShell::Matchers
end
```

## Credits

BlueShell is maintained and funded by [Pivotal Labs](http://www.pivotallabs.com).
Thank you to all the [contributors](https://github.com/pivotal/blue-shell/contributors).

Copyright
---------
Copyright &copy; Pivotal Labs. See [LICENSE](https://raw.github.com/pivotal/blue-shell/master/LICENSE) for details.
