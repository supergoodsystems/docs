# Ruby

### 1. Install the Supergood library

{% code title="Gem" %}
```bash
gem install supergood
```
{% endcode %}

### 2. Initialize the Supergood Library

**Environment Variables**

Set the environment variables `SUPERGOOD_CLIENT_ID` and `SUPERGOOD_CLIENT_SECRET` respectively, using the API keys generated in the previous instructions.

Initialize the Supergood Client at the root of your application, or anywhere you're making API calls with the following lines of code:

```ruby
require 'supergood'

Supergood.init()
```

**Passing Keys**

You can also pass the API keys in manually without setting environment variables.\
\
Replace `<CLIENT_ID>` and `<CLIENT_SECRET>` with the API keys you generated in the previous step.

```ruby
require 'supergood'

Supergood.init("<CLIENT_ID>", "<CLIENT_SECRET>")
```

### 3. That's it!&#x20;

Head back to your [dashboard](https://dashboard.supergood.ai) to start monitoring your API calls and receiving reports.

### Links

* [Supergood RubyGems Project](https://rubygems.org/gems/supergood)
* [Supergood-rb Source Code](https://github.com/supergoodsystems/supergood-rb)
