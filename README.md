[![Build Status](https://travis-ci.org/shayonj/emergency_number.svg?branch=master)](https://travis-ci.org/shayonj/emergency_number)
[![Coverage Status](https://coveralls.io/repos/github/shayonj/emergency_number/badge.svg?branch=master)](https://coveralls.io/github/shayonj/emergency_number?branch=master)
[![Gem Version](https://badge.fury.io/rb/emergency_number.svg)](https://badge.fury.io/rb/emergency_number)
# EmergencyNumber
```EmergencyNumber``` is a ruby gem for the [Emergency Number API](http://emergencynumberapi.com/) application.

 * Returns handy object to for any emergency numbers for any country in the world.
 * Takes in one argument - ```country code```. Country can be an ISO3361-1_alpha-2 or ISO3361-1_numeric code.
 * Authentication is not required. Rate limit is the same as it is mentioned in  [Emergency Number API docs](http://emergencynumberapi.com/docs#rate-limiting).

## Requirements
* Ruby 2.0.0 or higher

## Installation

Add this line to your application's Gemfile:

```ruby
gem 'emergency_number'
```

And then execute:

```ruby
$ bundle
```

Or install it yourself as:

```ruby
$ gem install emergency_number
```

## Usage
```ruby
require "emergency_number"
```
### Examples
```ruby
$ EmergencyNumber.get_country(:us) # or EmergencyNumber.get_country(840)
$ EmergencyNumber.get_country(:in) # or EmergencyNumber.get_country(356)
$ EmergencyNumber.get_country(:fr) # or EmergencyNumber.get_country(250)
$ EmergencyNumber.get_country(:au) # or EmergencyNumber.get_country(36)
```
```ruby
$ @result = EmergencyNumber.get_country(:us)
{
    :disclaimer => "The data from this API is provided without any claims of accuracy, you should use this data as guidance, and do your own due diligence.",
         :error => "",
          :data => {
           :country => {
                  :name => "United States of America",
               :ISOCode => "US",
            :ISONumeric => "840"
        },
         :ambulance => {
              :all => [""],
              :gsm => nil,
            :fixed => nil
        },
              :fire => {
              :all => [""],
              :gsm => nil,
            :fixed => nil
        },
            :police => {
              :all => [""],
              :gsm => nil,
            :fixed => nil
        },
          :dispatch => {
              :all => ["911"],
              :gsm => nil,
            :fixed => nil
        },
        :member_112 => false,
         :localOnly => false,
            :nodata => false
    }
}
```

### Retrieving Data

```ruby
$ @result.data
{
       :country => {
              :name => "United States of America",
           :ISOCode => "US",
        :ISONumeric => "840"
    },
     :ambulance => {
          :all => [""],
          :gsm => nil,
        :fixed => nil
    },
          :fire => {
          :all => [""],
          :gsm => nil,
        :fixed => nil
    },
        :police => {
          :all => [""],
          :gsm => nil,
        :fixed => nil
    },
      :dispatch => {
          :all => ["911"],
          :gsm => nil,
        :fixed => nil
    },
    :member_112 => false,
     :localOnly => false,
        :nodata => false
}
```

### Retrieving country name
```ruby
$ @result.data.country.name
=> "United States of America"
```

## Development

After checking out the repo, run `bin/setup` to install dependencies. Then, run `bundle exec rspec` to run the tests. You can also run `bin/console` for an interactive prompt that will allow you to experiment.

To install this gem onto your local machine, run `bundle exec rake install`. To release a new version, update the version number in `version.rb`, and then run `bundle exec rake release`, which will create a git tag for the version, push git commits and tags, and push the `.gem` file to [rubygems.org](https://rubygems.org).

## Contributing
Bug reports and pull requests are welcome on GitHub at https://github.com/shayonj/emergency_number. This project is intended to be a safe, welcoming space for collaboration, and contributors are expected to adhere to the [Contributor Covenant](http://contributor-covenant.org) code of conduct.

## GEM License

[MIT License](https://github.com/shayonj/emergency_number/blob/master/MIT-LICENSE)

## Data License

[Open Database License](https://github.com/shayonj/emergency_number/blob/master/Open-Database-License)
