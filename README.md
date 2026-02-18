# Markdown Embedder

A simple, lightweight web-based tool that renders markdown files from any URL directly in your browser using GitHub's Markdown API.

## 🌟 Features

- **Zero Dependencies**: Pure HTML and JavaScript - no build tools or packages required
- **Universal Rendering**: Renders any publicly accessible markdown file from any URL
- **GitHub-Flavored Markdown**: Uses GitHub's official Markdown API for consistent, high-quality rendering
- **Instant Preview**: Real-time markdown rendering without page reload
- **Embeddable**: Perfect for embedding markdown documentation in iframes or as standalone pages

## 🚀 Quick Start

### Using the Hosted Version

Simply add your markdown file URL as a query parameter:

```
https://andronasef.github.io/markdown-embedder/?url=YOUR_MARKDOWN_URL
```

### Self-Hosting

1. Clone this repository:
   ```bash
   git clone https://github.com/andronasef/markdown-embedder.git
   ```

2. Open `index.html` in your browser or serve it via any web server:
   ```bash
   # Using Python
   python -m http.server 8000
   
   # Using Node.js
   npx serve
   ```

3. Navigate to:
   ```
   http://localhost:8000/?url=YOUR_MARKDOWN_URL
   ```

## 📖 Usage Examples

### Embedding a GitHub README

```
?url=https://raw.githubusercontent.com/username/repo/main/README.md
```

### Embedding a Gist

```
?url=https://gist.githubusercontent.com/username/gist-id/raw/file.md
```

### Embedding from any web server

```
?url=https://example.com/docs/documentation.md
```

### Using in an iframe

```html
<iframe 
  src="https://andronasef.github.io/markdown-embedder/?url=https://raw.githubusercontent.com/username/repo/main/README.md"
  width="100%" 
  height="600"
  frameborder="0">
</iframe>
```

## 🔧 How It Works

1. The tool extracts the `url` parameter from the query string
2. Fetches the markdown content from the provided URL
3. Sends the content to GitHub's Markdown API (`https://api.github.com/markdown`)
4. Renders the returned HTML in the browser

## ⚠️ Limitations

- **CORS**: The markdown file must be accessible via a CORS-enabled endpoint
- **GitHub API Rate Limits**: The GitHub Markdown API has rate limits for unauthenticated requests (60 requests per hour per IP)
- **Public URLs Only**: Can only fetch markdown from publicly accessible URLs
- **No Authentication**: Does not support authenticated requests to private repositories

## 🛠️ Technical Details

- **No Backend Required**: Runs entirely in the browser
- **API Used**: [GitHub Markdown API](https://docs.github.com/en/rest/markdown)
- **Compatibility**: Works in all modern browsers (Chrome, Firefox, Safari, Edge)

## 🤝 Contributing

Contributions are welcome! Feel free to:

- Report bugs by opening an issue
- Suggest new features
- Submit pull requests

### Development

The project consists of a single `index.html` file. To modify:

1. Fork the repository
2. Make your changes
3. Test locally
4. Submit a pull request

## 📝 License

This project is open source and available under the [MIT License](LICENSE).

## 💡 Use Cases

- **Documentation Sites**: Embed markdown docs in your website
- **GitHub Pages**: Display markdown content without Jekyll
- **Learning Resources**: Share formatted markdown content easily
- **Quick Previews**: Preview markdown files from any source
- **Presentations**: Display markdown-based slides or notes

## 🔗 Links

- [GitHub Repository](https://github.com/andronasef/markdown-embedder)
- [Live Demo](https://andronasef.github.io/markdown-embedder/?url=https://raw.githubusercontent.com/andronasef/markdown-embedder/main/README.md)

## 📞 Support

If you encounter any issues or have questions, please [open an issue](https://github.com/andronasef/markdown-embedder/issues) on GitHub.

---

Made with ❤️ by [andronasef](https://github.com/andronasef)
