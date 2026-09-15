# Markdown Embedder

A simple, lightweight, web-based tool that renders markdown files from any URL or local file directly in your browser with a clean, book-inspired [Markdown Viewer](https://github.com/markdown-viewer/docs) editorial theme.

## 🌟 Features

- **Zero Dependencies Backend**: 100% client-side HTML, CSS, and JavaScript — host it on GitHub Pages with zero server setup
- **Markdown Viewer Style**: Warm editorial aesthetic, top toolbar with file badge, outline sidebar toggle, and typography tuned for reading
- **Table of Contents (Outline)**: Automatically generated hierarchical outline with icons, smooth scrolling, and live scroll-spy highlight
- **Interactive Landing Page**: When no URL is provided, displays an elegant landing page with URL input, drag-and-drop file upload, and quick samples
- **Local File Preview**: Drag & drop or browse `.md` files to preview immediately via HTML5 FileReader without uploading anywhere
- **Smart URL Converter**: Automatically translates standard GitHub URLs (`github.com/.../blob/...`) into raw content endpoints
- **Reading Controls**: Integrated zoom (`-`, `100%`, `+`), raw source toggle (`<>`), in-browser markdown editor (✏️), and download button (💾)
- **Dark Mode**: Seamless toggle between warm paper theme and dark mode with persistent preference and auto-detection
- **Code Highlighting & Copy**: Syntax highlighting for code blocks with one-click copy button
- **GitHub-Flavored Markdown**: Full support for tables, task lists, blockquotes, badges, and images

## 🚀 Quick Start

### Using the Hosted Version

Simply add your markdown file URL as a query parameter:

```
https://andronasef.github.io/markdown-embedder/?url=YOUR_MARKDOWN_URL
```

Or visit `https://andronasef.github.io/markdown-embedder/` directly to use the landing page and drop your file or paste a link.

### Self-Hosting

1. Clone this repository:
   ```bash
   git clone https://github.com/andronasef/markdown-embedder.git
   ```

2. Serve it with Bun or any static web server:
   ```bash
   # Using Bun
   bun x serve
   
   # Or using Python
   python -m http.server 8000
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

You can also paste standard GitHub URLs directly into the landing page:
```
https://github.com/username/repo/blob/main/README.md
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

1. The tool checks for a `url` query parameter.
2. If no `url` is present, it displays the interactive landing page with URL input, sample buttons, and drag-and-drop file upload.
3. If a `url` is present, it fetches the markdown content (auto-converting GitHub web URLs to raw URLs).
4. Parses and renders GitHub-Flavored Markdown safely in the browser using Marked and DOMPurify with Highlight.js code styling.
5. Dynamically builds the interactive Table of Contents (Outline) with icons and scroll tracking.

## ⚠️ Limitations

- **CORS**: External markdown URLs must be served with CORS enabled (CORS fallback proxy included for public endpoints).
- **Public URLs Only**: Direct fetching requires publicly accessible URLs. For private files, simply drag and drop them onto the landing page.

## 🛠️ Technical Details

- **No Backend Required**: Runs entirely client-side in the browser.
- **Libraries Used**: Marked.js (GFM parser), Highlight.js (syntax highlighting), DOMPurify (sanitizer).
- **Compatibility**: Modern browsers (Chrome, Firefox, Safari, Edge).

## 🤝 Contributing

Contributions are welcome! Feel free to:

- Report bugs by opening an issue
- Suggest new features or themes
- Submit pull requests

### Development

The project is contained in `index.html`. To develop locally:

1. Fork the repository
2. Run `bun x serve` or `bun -e "Bun.serve({ port: 3000, fetch: req => new Response(Bun.file('.' + (new URL(req.url).pathname === '/' ? '/index.html' : new URL(req.url).pathname))) })"`
3. Make your changes and test
4. Submit a pull request

## 📝 License

This project is open source and available under the [MIT License](LICENSE).

## 💡 Use Cases

- **Documentation Sites**: Embed markdown docs in any website or documentation portal.
- **GitHub Pages**: Display markdown content without Jekyll build overhead.
- **Offline & Local Preview**: Drop any local markdown file to read it in a clean book-like reader.
- **Quick Previews**: Share or preview markdown files from any URL.

## 🔗 Links

- [GitHub Repository](https://github.com/andronasef/markdown-embedder)
- [Live Demo](https://andronasef.github.io/markdown-embedder/?url=https://raw.githubusercontent.com/andronasef/markdown-embedder/master/README.md)

## 📞 Support

If you encounter any issues or have questions, please [open an issue](https://github.com/andronasef/markdown-embedder/issues) on GitHub.

---

Made with ❤️ by [andronasef](https://github.com/andronasef)
