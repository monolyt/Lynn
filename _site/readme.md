# LYNN - A Simple Digital Identity Kit

A simple Jekyll theme for creators who believe in calm web design. Built as a self-hosted alternative to formats like Linktree - no tracking – complete independence.

Clean typography, fast loading, and purposeful design that gets out of the way. Perfect for musicians, artists, and anyone who wants to have one place online to link their most important places, profiles, webshops and socials to.

## Features

- **Minimalist Design**: Clean, brutalist aesthetic with bold typography
- **Image Carousel**: Support for a single or multiple images with smooth navigation
- **Responsive**: Works perfectly on mobile and desktop
- **Adaptable Themes**: Choose a pre-built theme or create your own
- **Fast Loading**: Lightweight and minimized CSS, HTML, JS
- **Easy Customization**: Simple YAML configuration and modular HTML

## Quick Start

### Prerequisites

Before installing LYNN, make sure you have:

- **Ruby** (version 2.7 or higher) - [Download here](https://www.ruby-lang.org/en/downloads/)
- **Bundler** - Install with `gem install bundler`
- **Git** - [Download here](https://git-scm.com/downloads)

**Check your setup:**
```bash
ruby --version
bundle --version
git --version
```

### 1. Installation

Clone this repository:
```bash
git clone https://github.com/monolyt/lynn.git
cd lynn
```

Install dependencies:
```bash
bundle install
```

Run locally:
```bash
bundle exec jekyll serve
```

Your site will be available at `http://localhost:4000`

### 2. Basic Configuration

Edit `_config.yml` to customize your site:

```yaml
title: "YOUR NAME"              # Your name/brand
description: "Your bio"         # Meta description for SEO
show_description_on_card: True  # Show description text on the card
mail_text: "Email me"           # Link text for you email address
mail: "your@email.com"          # Your email address
color-theme: "color"            # Choose "color", "bw" or create your own theme
background-image: ""            # Optional background image path
```

## Customizing Your Site

### Changing Your Links

Edit `_data/links.yml` to add your social media and important links:

For example:

```yaml
- title: "Pixelfed"
  url: "gram.social/yourhandle"
  openInNewTab: False
- title: "Mastodon"
  url: "https://mastodon.social/yourhandle"
  openInNewTab: False
- title: "Bluesky"
  url: "https://bsky.app/profile/yourhandle"
  openInNewTab: False
```

**Parameters:**
- `title`: The text displayed on the card
- `url`: Where the link goes (use `mailto:` for email links)
- `openInNewTab`: Set to `True` to open in new tab, `False` to open in same tab

### Adding/Changing Images

Edit `_data/images.yml` to customize your image carousel:

```yaml
- path: "https://your-image-url.com/image1.jpg"
  description: "Alt text for image hosted online"
- path: "assets/image2.jpg"
  description: "Alt text for image hosted locally"
```

**Tips:**
- Use images with a 3:2 aspect ratio for best results, you can customize the aspect-ratio in the [theme files](#creating-custom-themes)
- For local images, place them in the `/assets/` folder and reference as `assets/filename.jpg`
- For external images, use the full URL
- If you only have one image, the carousel arrow won't appear
- Kepp image size as small as possible (preferably as .webp image format)

### Changing Your Bio

Edit the bio text directly in `_config.yml`. Look for this section:

```yaml
description: >-
    Your description goes here.
```

Replace the text with your own bio. Keep it concise, 1-2 sentences work best.

### Email Contact

The "Email me" link in the header can be customized in `_config.yml`:

```yaml
mail_text: "Email me"   # Show description text on the card
mail: "your@email.com"  # Your email address
```

The theme will automatically create the mailto link for you.

## Theme Customization

### Switching Between Themes

Change the `color-theme` in `_config.yml`:

- `color-theme: "color"` - Orange accent with light background
- `color-theme: "bw"` - Pure black and white

### Creating Custom Themes

1. Create a new file `_sass/_theme-yourname.scss`
2. Copy the structure from `_sass/_theme-color.scss`
3. Customize the CSS variables:

```scss
:root {
    --color-text: #000000;           // Text color
    --color-background: #ffffff;     // Page background
    --color-border: #000000;         // Border color
    --color-card: #ff6b35;          // Card background
    --color-selection: #0051FF;     // Text selection color
    --card-width: 480px;            // Card width on desktop
    --border: 2px solid var(--color-border);
    --border-radius: 1.5rem;        // Rounded corners
    --fontstring: "Your Font", sans-serif;
    --image-aspect-ratio: 3 / 2;    // Image proportions
}
```

3. Update `_config.yml`: `color-theme: "yourname"`

All existing themes can be adapted to your liking in in the .scss files.

## Advanced Customization

### Adding a Background Image

1. Add your image to `/assets/`
2. Update `_config.yml`:
```yaml
background-image: "/assets/your-background.jpg"
```

### Customizing Fonts

1. Add your font files to `/assets/`
2. Update `_sass/_typefaces.scss`:
```scss
@font-face {
    font-family: "YourFont";
    src: url(/assets/YourFont.woff2) format(woff2);
}
```
3. Update your theme file's `--fontstring` variable

Make sure you own all of the rights necessary to host your own fonts.
A good source for license free fonts is ![Uncut.wtf](https://uncut.wtf)

### Modifying Layout

The main layout is in `_layouts/default.html`. The structure is:

- `.card__header` - Title and email link
- `.card__carousel` - Image carousel
- `.card__text` - Bio section
- `.card__links` - Link buttons

## Deployment

### GitHub Pages

1. Push your code to a GitHub repository
2. Go to Settings → Pages
3. Select "Deploy from a branch" and choose `main`
4. Your site will be live at `https://yourusername.github.io/repository-name`

### Netlify

1. Connect your GitHub repository to Netlify
2. Build settings:
   - Build command: `bundle exec jekyll build`
   - Publish directory: `_site`

### Custom Domain

Update the `url` in `_config.yml` to your custom domain:
```yaml
url: "https://yourdomain.com"
```

## License

This theme is open source and available under the MIT License.
