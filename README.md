> Note: For full code, contact `stackseeker.human137@dralias.com` or WhatsApp `+91 7026217029`. It's Free.

# gen-blog

A Node.js library that generates SEO-friendly blog posts from YouTube videos using Google Gemini and OpenAI APIs. 

## Features

- 🎥 Automatic YouTube transcript extraction
- 📝 SEO-optimized blog post generation
- 📱 Short-form content creation
- 🤖 Dual AI support (Google Gemini and OpenAI)
- 🎨 Customizable output formats
- ⚙️ Flexible configuration options

## Requirements

- Node.js v18+
- YouTube Transcript API
- Google Generative AI SDK
- OpenAI SDK (optional)
- dotenv

## Installation

```sh
git clone <url you will get in an email>

npm install path/to/gen-blog
# or
pnpm install path/to/gen-blog
```

## Setup

1. **Configure Environment**  
   Create a `.env` file:
   ```env
   OPENAI_API_KEY=your-openai-key
   GEMINI_API_KEY=your-gemini-key
   ```

2. **Basic Usage**
   ```javascript
   import { ContentGenerator } from 'gen-blog';
   
   const generator = await new ContentGenerator().init();
   const results = await generator.generate("https://youtube.com/watch?v=your-video-id");
   ```

## Configuration Options

```javascript
const config = {
  // API Keys (optional if set in .env)
  openaiKey: "your-openai-key",
  geminiKey: "your-gemini-key",
  
  // Output Configuration
  outputDir: "./output",      // Output directory
  blogExtension: "md",        // Blog file extension
  shortsExtension: "txt",     // Shorts file extension
  dateFormat: "YYYY-MM-DD",   // Date format
  verbose: true,              // Enable logging
  prefix: "custom",           // File prefix
  
  // Custom Prompts (optional)
  blogPrompt: "Your custom blog prompt",
  shortsPrompt: "Your custom shorts prompt"
};

const generator = await new ContentGenerator(config).init();
```

## Output Structure

The generator creates two types of files:

### Blog Posts (Markdown)
```markdown
---
title: SEO-Friendly Title
description: SEO Description
date: 2024-03-06
category: [Category]
tags: [tag1, tag2]
---

Content...
```

### Shorts Script (Text)
```text
[Scene 1: Introduction]
Content...

[Scene 2: Main Points]
Content...
```

## Advanced Usage

```javascript
// Generate both blog and shorts
const results = await generator.generate(videoUrl, {
  blog: true,
  shorts: true,
  outputOptions: {
    prefix: "custom",
    silent: false,
    logLevel: "debug"
  }
});

// Generate blog post only
const blogOnly = await generator.generate(videoUrl, {
  blog: true,
  shorts: false
});
```

## Customization

- Custom prompts via configuration
- Flexible output formats
- Configurable file naming
- Verbose/silent modes
- Custom file extensions

## Future Scope

- Batch processing multiple URLs
- Additional AI models integration
- Video metadata extraction
- Image generation
- Web service/API deployment
- CLI interface
- Multi-platform support

## Contributing

Pull requests are welcome! See [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines.
