# Dotify - Your.Music

A modern music playlist management web application built with HTML, CSS (Bulma framework), and vanilla JavaScript. The project uses [Eleventy (11ty)](https://www.11ty.dev/) as a static site generator to build and deploy the site.

## Project Overview

Dotify is a Spotify-inspired web application that displays and manages music playlists. The project features a responsive design with a dark theme, showcasing playlists in an elegant card-based layout.

## Features

- **Responsive Navigation**: Mobile-friendly navbar with hamburger menu
- **Playlist Cards**: Visual playlist representation with images and descriptions
- **Dark Theme**: Modern black and grey color scheme
- **Interactive UI**: Play, Open, and Remove buttons for each playlist
- **Bulma Framework**: Utilizing Bulma CSS for consistent, responsive design

## Tech Stack

- **Eleventy (11ty)**: Static site generator for building the site
- **HTML5**: Semantic markup
- **CSS**: [Bulma CSS Framework](https://bulma.io/) v1.0.2 (via CDN)
- **JavaScript**: Vanilla JS for interactive components
- **Images**: Unsplash for placeholder images

## Project Structure

```bash
dotify-html/
├── .eleventy.js            # Eleventy configuration
├── index.html              # Main application page (source)
├── README.md               # Project documentation
├── _site/                  # Generated output (build directory)
│   ├── index.html          # Built HTML file
│   ├── images/             # Copied image assets
│   ├── js/                 # Copied JavaScript files
│   └── README/
│       └── index.html
├── images/                 # Image assets (source)
│   ├── favicon.png
│   ├── logo-with-name.png
│   └── logo-white.png
└── js/                     # JavaScript files (source)
    └── bulma.js           # Bulma interactive components
```

## Getting Started

### Prerequisites

- **Node.js** (v22 or higher) and npm
- A modern web browser (Chrome, Firefox, Safari, Edge)

### Installation

1. **Clone the repository**
```bash
git clone git@github.com:johnrellis/dotify-html.git
cd dotify-html
```

2. **Install dependencies**

Ensure eleventy is installed if you want to use it globally

3. **Run the development server**

If you have eleventy installed

```bash
eleventy --serve
```
You could also use npx.

```bash
npx @11ty/eleventy --serve
```

4. **Access the application**
   
   Navigate to `http://localhost:8080` in your browser (Eleventy's default port)
   
   The development server will:
   - Watch for file changes
   - Automatically rebuild the site
   - Live reload the browser


## Development

### Eleventy Configuration

The `.eleventy.js` file configures how Eleventy processes your site:

```javascript
module.exports = function(eleventyConfig) {
  eleventyConfig.addPassthroughCopy("css");
  eleventyConfig.addPassthroughCopy("js");
  eleventyConfig.addPassthroughCopy("images");
};
```

This configuration ensures that CSS, JavaScript, and images are copied directly to the `_site/` output directory without processing.

### Making Changes

1. **Edit source files** - Make changes to `index.html`, `js/`, `images/`, etc.
2. **Eleventy watches and rebuilds** - If the dev server is running, changes are detected automatically
3. **View changes** - Browser automatically reloads with updates
4. **Built files** - Generated output appears in `_site/` directory

**Note:** Never edit files directly in the `_site/` directory - they will be overwritten on the next build.

### Available Commands

```bash
# Build the site once
npx @11ty/eleventy

# Build and serve with live reload
npx @11ty/eleventy --serve

# Build with detailed output for debugging
npx @11ty/eleventy --quiet=false
```

### Browser Compatibility

- Modern browsers (ES6+ support)
- Responsive design for mobile, tablet, and desktop

## Build/Deployment

### Building for Production

```bash
npx @11ty/eleventy
```

This generates the production-ready site in the `_site/` directory.

### Deployment Options

**Netlify** (Recommended)
1. Connect your GitHub repository
2. Build command: `npx @11ty/eleventy`
3. Publish directory: `_site`
4. Automatic deployments on every push

**Vercel**
1. Import your GitHub repository
2. Vercel auto-detects Eleventy
3. Deploy with zero configuration

**GitHub Pages**
```bash
# Build the site
npx @11ty/eleventy

# Deploy _site directory to gh-pages branch
npx gh-pages -d _site
```

**Manual Deployment**
- Build the site with `npx @11ty/eleventy`
- Upload the contents of `_site/` to your web server

### Environment-Specific Builds

You can customize Eleventy behavior based on environment:

```javascript
// .eleventy.js
module.exports = function(eleventyConfig) {
  const isProduction = process.env.NODE_ENV === 'production';
  
  // Add environment-specific configuration
};
```

## Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add some amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## License

This project is open source and available for educational purposes.

## Authors

- **johnrellis** - Initial work

## Acknowledgments

- [Eleventy](https://www.11ty.dev/) for the fast and flexible static site generator
- [Bulma CSS Framework](https://bulma.io/) for the responsive design system
- [Unsplash](https://unsplash.com/) for placeholder images
- Inspired by Spotify's design language
