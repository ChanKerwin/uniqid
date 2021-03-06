# Uniqid

'Uniqid' is a distributed unique ID generator inspired by Twitter's Snowflake.

## Installation

Add this line to your application's Gemfile:

```ruby
gem 'uniqid'
```

And then execute:

    $ bundle install

Or install it yourself as:

    $ gem install uniqid

## Usage

```ruby
# app/models/application_record.rb

class ApplicationRecord < ActiveRecord::Base
  self.abstract_class = true
  before_create :set_uniqid

  def set_uniqid

    # TODO: get your worker_id and server_id

    self.id = UniqID.generate(worker_id, server_id)
  end
end
```

## Development

After checking out the repo, run `bin/setup` to install dependencies. Then, run `rake spec` to run the tests. You can also run `bin/console` for an interactive prompt that will allow you to experiment.

To install this gem onto your local machine, run `bundle exec rake install`. To release a new version, update the version number in `version.rb`, and then run `bundle exec rake release`, which will create a git tag for the version, push git commits and tags, and push the `.gem` file to [rubygems.org](https://rubygems.org).

## Contributing

1.Fork it ( https://github.com/ChanKerwin/uniqid/fork )

2.Create your feature branch (git checkout -b my-new-feature)

3.Commit your changes (git commit -am 'Add some feature')

4.Push to the branch (git push origin my-new-feature)

5.Create a new Pull Request


## License

The gem is available as open source under the terms of the [MIT License](https://opensource.org/licenses/MIT).

## Code of Conduct

Everyone interacting in the Uniqid project's codebases, issue trackers, chat rooms and mailing lists is expected to follow the [code of conduct](https://github.com/ChanKerwin/uniqid/blob/main/CODE_OF_CONDUCT.md).
