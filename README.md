# Datadog::JSONLogger

[![Rubocop and Rspec](https://github.com/Eth3rnit3/datadog-json_logger/actions/workflows/main.yml/badge.svg?branch=main)](https://github.com/Eth3rnit3/datadog-json_logger/actions/workflows/main.yml)

`Datadog::JSONLogger` is a Ruby gem designed to seamlessly integrate Ruby applications with Datadog's logging and tracing services. This gem allows your Ruby application to format its output as JSON, including necessary correlation IDs and other details for optimal Datadog functionality.

## Installation

Add this line to your application's Gemfile:

```ruby
gem 'datadog-json_logger'
```

And then execute:

```bash
bundle install
```

Or install it yourself as:

```bash
gem install datadog-json_logger
```

## Usage

### JSONLogger

`Datadog::JSONLogger` can be easily integrated into your Ruby application. Here's a quick example of how to use it in a Sinatra application:

```ruby
# Example in Sinatra (app.rb)
require 'datadog/json_logger'

def logger
  @logger ||= Datadog::JSONLogger.new
end

set :logger, logger
```

### SinatraMiddleware

`Datadog::SinatraMiddleware` formats Rack requests as JSON and disables the default textual stdout of `Rack::CommonLogger`:

```ruby
# Example in Sinatra (app.rb)
require 'datadog/sinatra_middleware'

use Datadog::SinatraMiddleware, logger
```

## Development

After checking out the repo, run `bundle install` to install dependencies. Then, run `rake spec` to run the tests. You can also run `bin/console` for an interactive prompt that will allow you to experiment.

To install this gem onto your local machine, run `bundle exec rake install`.

## Contributing

Bug reports and pull requests are welcome on GitHub at https://github.com/eth3rnit3/datadog-json_logger. This project is intended to be a safe, welcoming space for collaboration, and contributors are expected to adhere to the [code of conduct](https://github.com/eth3rnit3/datadog-json_logger/blob/main/CODE_OF_CONDUCT.md).

1. Fork the repository (https://github.com/eth3rnit3/datadog-json_logger/fork)
2. Create your feature branch (`git checkout -b feature/my_feature`)
3. Commit your changes (`git commit -am 'Add a new feature'`)
4. Push the branch (`git push origin feature/my_feature`)
5. Open a Pull Request

## License

This gem is available as open source under the terms of the [MIT License](https://opensource.org/licenses/MIT).

## Code of Conduct

Everyone interacting in the Datadog::JSONLogger project's codebases, issue trackers, chat rooms, and mailing lists is expected to follow the [code of conduct](https://github.com/eth3rnit3/datadog-json_logger/blob/main/CODE_OF_CONDUCT.md).