# Capybara-Choices

A Capybara plugin to make testing [Choices.js](https://github.com/Choices-js/Choices) form fields a nicer experience.

## Installation

Add `capybara-choices` to your application's Gemfile and then run `bundle`.

```ruby
group :test do
  gem 'capybara-select-2'
end
```

And load it from Rspec

```ruby
# spec_helper.rb
RSpec.configure do |config|
  config.include CapybaraChoices
end
```

## Usage

### Testing a single choice dropdown

```ruby
# Using a CSS selector
choices 'XBox', css: '#single'

# Using a label
choices 'XBox', from: 'Select game console'

# Using an XPath
choices 'XBox', xpath: "//div[@id='single']"
```

### Selecting multiple options at once
```ruby
choices 'Buy Milk', 'Go to gym', css: '#multiple'
```

### Use Choices search feature to find an item
```ruby
# Search by option text
choices 'XBox', css: '#single', search: true

# Search by a specific string
choices 'XBox', css: '#single', search: 'Box'

# Select the first item that matches the search
choices 'PlayStation', css: '#single', search: true, match: :first
```
