# UTCP Manuals Repository

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

A comprehensive collection of Universal Tool Calling Protocol (UTCP) manual JSON files for various useful APIs, services, and tools. These manuals can be directly used with UTCP-compatible clients to interact with popular web services, development tools, data sources, and AI services.

## Table of Contents

- [What is UTCP?](#what-is-utcp)
- [Repository Structure](#repository-structure)
- [Available UTCP Manuals](#available-utcp-manuals)
  - [Web APIs](#web-apis)
  - [Development Tools](#development-tools)
  - [Data & Analytics](#data--analytics)
  - [AI & Machine Learning](#ai--machine-learning)
- [Usage Examples](#usage-examples)
- [Authentication Requirements](#authentication-requirements)
- [Getting Started](#getting-started)
- [API Key Registration Links](#api-key-registration-links)
- [Contributing](#contributing)
- [License](#license)
- [Disclaimer](#disclaimer)
- [Support](#support)

## What is UTCP?

The Universal Tool Calling Protocol (UTCP) is a standardized format for defining how AI agents and applications can interact with external tools and APIs. For more details, see the [official UTCP specification](https://github.com/universal-tool-calling-protocol/utcp-specification). Each UTCP manual is a JSON file that describes:

- Tool functions and their parameters
- Input/output schemas
- Authentication methods
- Transport protocols (HTTP, etc.)
- Usage examples and metadata

## Repository Structure

```
utcp-manuals-repository/
├── web-apis/
│   ├── weather/
│   │   └── openweathermap.json
│   ├── social-media/
│   │   └── github.json
│   ├── news/
│   │   └── newsapi.json
│   └── finance/
│       └── coingecko.json
├── development-tools/
│   ├── testing/
│   │   └── jsonplaceholder.json
│   └── utilities/
│       ├── tinyurl.json
│       └── qr-server.json
├── data-analytics/
│   ├── geography/
│   │   └── rest-countries.json
│   └── network/
│       └── ipapi.json
├── ai-ml/
│   ├── huggingface.json
│   └── openai.json
└── README.md
```

## Available UTCP Manuals

### Web APIs

#### Weather Services
- **OpenWeatherMap** (`web-apis/weather/openweathermap.json`)
  - Get current weather by coordinates or city name
  - Supports multiple units and languages
  - Requires API key

#### Social Media & Development
- **GitHub** (`web-apis/social-media/github.json`)
  - Get user information and repositories
  - Search repositories
  - Get repository details
  - No authentication required for public data

#### News & Media
- **NewsAPI** (`web-apis/news/newsapi.json`)
  - Search news articles from 150,000+ sources
  - Get top headlines by country/category
  - Get news sources information
  - Requires API key

#### Finance & Cryptocurrency
- **CoinGecko** (`web-apis/finance/coingecko.json`)
  - Get cryptocurrency prices and market data
  - Get detailed coin information
  - Get trending cryptocurrencies
  - Get global crypto market statistics
  - No authentication required

### Development Tools

#### Testing
- **JSONPlaceholder** (`development-tools/testing/jsonplaceholder.json`)
  - Fake REST API for testing and prototyping
  - Get/create posts, users, comments
  - No authentication required

#### Utilities
- **TinyURL** (`development-tools/utilities/tinyurl.json`)
  - Shorten long URLs
  - Optional custom aliases
  - No authentication required

- **QR Server** (`development-tools/utilities/qr-server.json`)
  - Generate QR codes from text/URLs
  - Read QR codes from images
  - Customizable size, colors, format
  - No authentication required

### Data & Analytics

#### Geography
- **REST Countries** (`data-analytics/geography/rest-countries.json`)
  - Get information about all world countries
  - Search countries by name, code, or region
  - Comprehensive country data including population, area, languages, currencies
  - No authentication required

#### Network
- **IP API** (`data-analytics/network/ipapi.json`)
  - Get geolocation information for IP addresses
  - Support for current IP or specific IP lookup
  - Batch IP lookup capabilities
  - No authentication required

### AI & Machine Learning

#### Hugging Face
- **Hugging Face** (`ai-ml/huggingface.json`)
  - Text generation with various models
  - Text classification and sentiment analysis
  - Question answering
  - Text-to-image generation
  - Speech recognition
  - Requires API key

#### OpenAI
- **OpenAI** (`ai-ml/openai.json`)
  - Chat completions with GPT models
  - Text embeddings
  - Image generation with DALL-E
  - Speech-to-text with Whisper
  - Text-to-speech
  - Requires API key

## Usage Examples

### Basic Usage Pattern

Each UTCP manual follows a standard structure:

```json
{
  "utcp_version": "1.0.0",
  "manual_version": "1.0.0",
  "tools": [
    {
      "name": "tool_function_name",
      "description": "What this tool does",
      "inputs": {
        "type": "object",
        "properties": {
          "parameter_name": {
            "type": "string",
            "description": "Parameter description"
          }
        },
        "required": ["parameter_name"]
      },
      "outputs": {
        "type": "object",
        "properties": {
          "result_field": {
            "type": "string"
          }
        }
      },
      "tags": ["category", "keywords"],
      "average_response_size": 1000,
      "tool_transport": {
        "transport_type": "http",
        "url": "https://api.example.com/endpoint",
        "http_method": "GET",
        "query_params": {
          "param": "{parameter_name}"
        },
        "auth": {
          "auth_type": "api_key",
          "api_key": "YOUR_API_KEY",
          "var_name": "apiKey",
          "location": "query"
        }
      }
    }
  ]
}
```

### Example: Using the Weather API

```json
{
  "tool": "get_current_weather",
  "inputs": {
    "lat": 40.7128,
    "lon": -74.0060,
    "units": "metric"
  }
}
```

### Example: Using the GitHub API

```json
{
  "tool": "get_user",
  "inputs": {
    "username": "octocat"
  }
}
```

## Authentication Requirements

### APIs Requiring Keys
- **OpenWeatherMap**: Free tier available, requires registration
- **NewsAPI**: Free tier available, requires registration  
- **Hugging Face**: Free tier available, requires registration
- **OpenAI**: Paid service, requires API key

### APIs Without Authentication
- **GitHub**: Public data accessible without authentication
- **CoinGecko**: Free access to market data
- **JSONPlaceholder**: Completely free testing API
- **TinyURL**: Free URL shortening service
- **QR Server**: Free QR code generation/reading
- **REST Countries**: Free country information
- **IP API**: Free IP geolocation service

## Getting Started

1. **Choose a UTCP manual** from the repository based on your needs
2. **Review the authentication requirements** for your chosen API
3. **Obtain API keys** if required (see links below)
4. **Load the UTCP manual** into your UTCP-compatible client
5. **Configure authentication** by replacing placeholder API keys
6. **Start making tool calls** using the defined functions

## API Key Registration Links

- [OpenWeatherMap API](https://openweathermap.org/api)
- [NewsAPI](https://newsapi.org/)
- [Hugging Face](https://huggingface.co/settings/tokens)
- [OpenAI](https://platform.openai.com/api-keys)

## Contributing

This repository aims to provide high-quality UTCP manuals for popular and useful APIs. Contributions are welcome for:

- New API manuals
- Updates to existing manuals
- Bug fixes and improvements
- Documentation enhancements

### Manual Quality Standards

Each UTCP manual should include:
- Comprehensive input/output schemas
- Proper authentication configuration
- Relevant tags for discoverability
- Accurate average response sizes
- Complete transport configuration
- Clear descriptions and examples

### Supported API Categories

- **Web APIs**: Public web services and APIs
- **Development Tools**: Testing, utilities, and developer services
- **Data & Analytics**: Data sources, statistics, and information services
- **AI & ML**: Artificial intelligence and machine learning services
- **Productivity**: Tools that enhance workflow and productivity
- **Communication**: Messaging, email, and communication services

## License

This repository is provided as-is for educational and development purposes. Each API service has its own terms of service and usage limits. Please review the individual API documentation and terms before use.

## Disclaimer

- API endpoints and schemas may change over time
- Rate limits and authentication requirements vary by service
- Some services may have usage costs or require paid subscriptions
- Always refer to official API documentation for the most current information

## Support

For issues with specific UTCP manuals or suggestions for new APIs to include, please refer to the individual API documentation or contact the respective service providers.

---

**Total APIs**: 11 services across 4 categories  
**Last Updated**: July 2025  
**UTCP Version**: 1.0.0
