## Welcome to Linda's Website

<img src="https://raw.githubusercontent.com/abhinavs/moonwalk/master/_screenshots/moonwalk.png" />

<h3 align="center">
  <img src="https://raw.githubusercontent.com/abhinavs/moonwalk/master/logo.png" width="24"/>
<a href="https://abhinavs.github.io/moonwalk/">TRY THE DEMO</a>
</h3>

## Features
* Two hand-tuned themes, light and dark, inspired by GitHub's own light/dark palettes - with a theme switcher (respects `prefers-reduced-motion`)
* Typeset in [IBM Plex Sans](https://www.ibm.com/plex/) (headings) and [IBM Plex Mono](https://www.ibm.com/plex/) (body & code)
* [Agent-friendly out of the box](#agent-friendly-by-default) - per-page `.md` siblings, `/llms.txt`, and `/llms-full.txt`
* Built-in client-side search over post titles, tags, and excerpts
* Hover-preview cards on internal post links (opt-in)
* Footnote tooltips - read footnotes inline without scrolling (opt-in)
* Smooth page transitions via the View Transitions API in supporting browsers
* Drop-cap on the first paragraph of a post (opt-in via `dropcap: true`)
* Tag cloud with frequency-weighted sizing on the tag archive
* Personality 404 with random-post link
* Vertical list, horizontal list, card list
* Landing page with navbar, footer, portfolio
* Fast (very minimal CSS) - 100/100 on performance, accessibility, best practices and SEO, please see [Lighthouse Report](https://raw.githubusercontent.com/abhinavs/moonwalk/master/_screenshots/lighthouse-report.png) for more details
* Responsive and mobile friendly
* SEO optimized with auto-generated sitemap
* RSS feed (uses [Jekyll Feed](https://github.com/jekyll/jekyll-feed))
* [GitHub Markdown Alerts](#github-markdown-alerts) (NOTE, TIP, IMPORTANT, WARNING, CAUTION)
* Polished `<details>` collapsibles for asides and "long version" expansions
* Tag archive page with clickable tags
* Light and dark mode syntax highlighting with language label on each code block
* Accessible - ARIA labels, keyboard friendly
* Reading progress bar (opt-in)
* Back-to-top button (opt-in)
* Previous/next post navigation (opt-in)
* Table of contents via `toc: true` front matter (opt-in)
* Code block copy button with language label (opt-in)
* Easy to extend
* Fully compatible with [GitHub Pages](https://pages.github.com/) (see [GitHub Pages installation](#github-pages-installation))
* Auto-generated share images for social media (using [Soopr](https://www.soopr.co))
* Share & like buttons (using [Soopr](https://www.soopr.co))

## Customizing

You can edit `_config.yml` file to customize your blog. You can change things such as the name of the blog, the author, the appearance of the theme (light, dark or auto), how dates are formatted, etc. Customizable fields should be straightforward to understand. Still, `_config.yml` contains some comments to help you understand what each field does.

For further customization (e.g. layout, CSS) see the [official Jekyll's documentation](https://jekyllrb.com/docs/themes/#overriding-theme-defaults) on customizing gem-based themes.

### Customize the menu

In order to add/edit/delete entries in the home page, you can copy the `home.yml` file inside `_data` folder. Through that file you can define the structure of the menu and add data for navbar, footer, portfolio or simply remove all of that and use simple blog layout. Take a look at the default configuration to get an idea of how it works and read on for a more comprehensive explanation.

The `home.yml` file accepts the following fields:

1. Vertical list
  - `entries` define a new unordered list that will contain menu entries
  - each entry is marked by a `-` at the beginning of the line
  - each entry has the following attributes:
    - `title`, which defines the text to render for that menu entry
    - `url`, which can either be a URL or `false`. If it is `false`, the entry will be rendered as plain text; otherwise the entry will be rendered as a link pointing to the specified URL. Note that the URL can either be relative or absolute.
    - `post_list`, which can be `true` or `false`. If it is true, the entry will have all posts in the site as subentries. This is used to render your post list.
    - `entries`, yes, you can have entries inside entries. In this way you can create nested sublists!
2. Card list - cards are used to showcase portfolio projects. Please see `project_entries` in `_data/home.yml` file
  - each entry is marked by a `-` at the beginning of the line
  - each entry has the following attributes:
    - `title` defines the header of the card
    - `desc` is the body of the card
    - `url` is a relative or absolute link which this card can point to.
    - `highlight` in case you want to highlight something, keep the text short though
3. Horizontal list - moonwalk uses horizontal lists to create navbar and footer. Please see `navbar_entries` and `footer_entries` in `data/home.yml` file
  - each entry is marked by a `-` at the beginning of the line
  - each entry has the following attributes:
    - `title` defines the header of the card
    - `url` is a relative or absolute link which this card can point to.


### Pro tips
1. Moonwalk has 3 in-built layouts:
  - post - for content
  - blog - for listing blog posts
  - home - for landing page
  you can change your `index.md` file to use either home or blog layout.

2. It is extremely easy to tweak the color scheme. Moonwalk ships with a light and dark theme inspired by GitHub's own palettes - override either mixin in your own SCSS to make it your own.
  - light mode
```css
@mixin light-appearance {
  html, body {
      --bg: #ffffff;
      --bg-secondary: #eaeef2;
      --bg-subtle: #f6f8fa;
      --headings: #1f2328;
      --text: #1f2328;
      --text-secondary: #59636e;
      --links: #0969da;
      --highlight: #fff8c5;
      --code-text: #8250df;
  }
}
```
  - dark mode
```css
@mixin dark-appearance {
  html, body  {
      --headings: #f0f6fc;
      --links: #4493f8;
      --highlight: #e3b341;
      --bg: #0d1117;
      --bg-secondary: #21262d;
      --bg-subtle: #161b22;
      --text: #c9d1d9;
      --text-secondary: #8b949e;
      --code-text: #d2a8ff;
  };
}
```

3. Want different fonts? Moonwalk uses IBM Plex Sans / IBM Plex Mono via two CSS variables. Override them in your own SCSS:
```css
:root {
    --font-sans: "Inter", system-ui, sans-serif;
    --font-mono: "JetBrains Mono", monospace;
}
```
Don't forget to update the `<link>` to Google Fonts in `_includes/head.html` to match.



## Acknowledgement Credits
Thank you Abhinav Saxena for the creating such a wonderful website template.
