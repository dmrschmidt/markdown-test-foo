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
BlueShell::Runner.run 'sleep 6' # fails with Timeout::Error
```

### Expectations on exit codes

```ruby
BlueShell::Runner.run 'false' do |runner|
  runner.should exit_with 1
  runner.should have_exit_code 1 # #exit_with and #have_exit_code are aliases
end
```

### Expectations on STDOUT

```ruby
BlueShell::Runner.run 'echo "foo bar"' do |runner|
  runner.should say 'foo'
  runner.should have_output 'bar' # #say and #have_output are aliases
end
```

### Interacting with STDIN

### Increasing the timeout

## Credits

BlueShell is maintained and funded by [Pivotal Labs](http://www.pivotallabs.com).
Thank you to all the [contributors](https://github.com/pivotal/blue-shell/contributors).

Copyright
---------
Copyright &copy; Pivotal Labs. See [LICENSE](https://raw.github.com/pivotal/blue-shell/master/LICENSE) for details.
