# Article Wizard - AI-Powered Content Generator

Article Wizard is a modern web application that generates high-quality, SEO-optimized articles based on keywords and titles. It also provides AI-generated image prompts to help create visual content for your articles.

## Features

- Generate complete articles from keywords and SEO titles
- Create AI image prompts for featured images and instructional visuals
- View articles in both preview and HTML code modes
- Copy HTML code with one click
- Export articles as JSON
- Browse and load recent articles
- Direct integration with Make.com for content generation

## Setup Instructions

### Make.com Integration Setup

1. Create a free account on [Make.com](https://www.make.com/)
2. Create a new scenario with a webhook trigger
3. Configure the webhook to receive:
   - `keyword` (string)
   - `seoTitle` (string)
   - `externalLink` (string, optional)
   - `timestamp` (string)
4. Add your AI content generation steps (e.g., OpenAI, ChatGPT)
5. Add a "Webhook response" module to return the generated content
6. The response should include:
   - `content` (the generated article HTML)
   - `featuredImagePrompt` (string)
   - `stepByStepImagePrompt` (string)
   - `servingSuggestionsPrompt` (string)
   - `id` (optional, will be generated if not provided)
7. Copy your webhook URL and update it in `src/config/makeConfig.ts`

## Development

### Installation

```bash
npm install
```

### Running the Development Server

```bash
npm run dev
```

### Building for Production

```bash
npm run build
```

## How It Works

1. **Input Phase**: User enters a keyword, SEO title, and optional external link
2. **Generation Phase**: The app sends this data directly to Make.com via webhook
3. **Processing Phase**: Make.com processes the request through AI services
4. **Response Phase**: Make.com returns the generated content directly in the webhook response
5. **Display Phase**: The app displays the generated content and stores it in local storage for future reference

## Customization

You can customize the application by:

1. Modifying the article template in the Make.com scenario
2. Adjusting the image prompt generation logic
3. Changing the UI theme by updating Tailwind CSS classes
4. Adding additional tabs or features as needed

## License

© 2025 Article Wizard. All rights reserved.