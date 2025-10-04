# ai_connector

A Ruby (and Rails-friendly) gem that provides a **unified interface** for multiple AI providers such as **OpenAI ChatGPT**, **Google Gemini**, and **Perplexity AI**.  

With `ai_connector`, you can swap providers with just a single line of code—no more juggling multiple SDKs.

---

## ✨ Features
- 🔌 Connect to **OpenAI (ChatGPT)**, **Gemini**, and **Perplexity** with one client.  
- 🔄 Switch providers easily (`:openai`, `:gemini`, `:perplexity`).  
- 🛠 Rails support with initializer configuration.  
- 📡 Simple API for chat/completions.  
- 🚀 Future-proof (easy to extend for more AI providers).  

---

## 📦 Installation

Add this line to your Gemfile:

```ruby
gem 'ai_connector'
```

And then execute:

```bash
bundle install
```

Or install it yourself:

```bash
gem install ai_connector
```

---

## ⚡ Quick Start

```ruby
require "ai_connector"

# Example: OpenAI
client = AIConnector::Client.new(provider: :openai, api_key: ENV["OPENAI_API_KEY"])
puts client.chat("Tell me a joke about Ruby on Rails.")

# Example: Gemini
client = AIConnector::Client.new(provider: :gemini, api_key: ENV["GEMINI_API_KEY"])
puts client.chat("Summarize Rails in 3 sentences.")

# Example: Perplexity
client = AIConnector::Client.new(provider: :perplexity, api_key: ENV["PERPLEXITY_API_KEY"])
puts client.chat("What is the future of AI in 2025?")
```

---

## ⚙️ Rails Configuration (optional)

Create an initializer file:  
`config/initializers/ai_connector.rb`

```ruby
AIConnector.configure do |config|
  config.default_provider = :openai
  config.api_keys = {
    openai: ENV["OPENAI_API_KEY"],
    gemini: ENV["GEMINI_API_KEY"],
    perplexity: ENV["PERPLEXITY_API_KEY"]
  }
end
```

Now in your app:

```ruby
client = AIConnector.client
puts client.chat("Hello from Rails!")
```

---

## 🧩 Providers Supported

- ✅ OpenAI (ChatGPT, GPT-4, GPT-3.5)  
- ✅ Google Gemini (Gemini 1.5, Flash)  
- ✅ Perplexity AI (Sonar models)  
- ⏳ Coming soon: Anthropic Claude, Mistral AI  

---

## 🛠 Development

Clone the repo and run:

```bash
bundle install
rake spec
```

Build the gem locally:

```bash
gem build ai_connector.gemspec
gem install ./ai_connector-0.1.0.gem
```

---

## 🤝 Contributing

Bug reports and pull requests are welcome on GitHub at:  
[https://github.com/your-username/ai_connector](https://github.com/your-username/ai_connector)

---

## 📜 License

The gem is available as open source under the terms of the [MIT License](LICENSE).  
