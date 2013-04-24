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

## Usage

### Running commands

Shell commands in BlueShell get executed by creating a new runner instance `BlueShell::Runner.run`.
Running a command by default times out after 5 seconds or raises a `Timeout::Error`.

```ruby
BlueShell::Runner.run 'sleep 1' # success
BlueShell::Runner.run 'sleep 5' # fails with Timeout::Error
```

## Credits

BlueShell is maintained and funded by [Pivotal Labs](http://www.pivotallabs.com).
Thank you to all the [contributors](https://github.com/pivotal/blue-shell/contributors).

Copyright
---------
Copyright &copy; Pivotal Labs. See [LICENSE](https://raw.github.com/pivotal/blue-shell/master/LICENSE) for details.
