Hello! This is the repository for my website code. 

My goal is to ultimately keep everything in one spot, from ideas to recipes, from my PhD journey to hobbies. Sort of like journaling, but without being able to lose a journal. Enjoy! 

I used the Prologue Jekyll theme, which is a single page responsive site template from [HTML5 UP](https://html5up.net/prologue), now available as a blog-aware Jekyll theme from [Chris Bobbe](https://chrisbobbe.github.io). 

To add my Spotify playlists, I adapted code from this repository: DoomPatrol/responsive-spotify-widget

# Build your homepage

1. **Your `_config.yml` file must include the following line or your homepage won't work**: `collections: [sections]`. This tells Jekyll to look in the _sections folder (which you will create) for your content and render it all on one page.

2. **Create a `_sections` folder** in your project's root directory and start adding content to your homepage. Set a cover photo in any of the sections by adding `cover-photo: path/to/photo.jpg` and `cover-photo-alt: your alt text here` to the section's frontmatter. Sample content is provided in the [GitHub repository](https://github.com/chrisbobbe/jekyll-theme-prologue/tree/master/_sections).

All new sections should be added as html or Markdown documents in the `_sections` folder. The following section variables can be set with [frontmatter](https://jekyllrb.com/docs/frontmatter/):
- `title` (required)
- `order` (required; orders the sequence of sections on the page. Example: `1`)
- `cover-photo` (optional; sets a background image for the section. Example: `assets/images/banner.jpg`)
- `cover-photo-alt` (required if using a cover photo. Describes the photo for screen readers and SEO; e.g. "Dome of Light art installation, Kaohsiung, Taiwan")
- `icon` (optional; see [Font Awesome](https://fontawesome.com/icons) for icon codes. Example: `fa-github`)
- `icon-style` (optional; "solid" is default, "regular" for outline style icons, or "brands" for logos)
- `auto-header` (optional; "use-title" is default, "none" for no header, or custom header text)
- `hide` (optional; if `true`, the section won't appear)

# Start blogging!

Jekyll has great resources to get you started writing blog posts. Check out [this Jekyll Docs page](https://jekyllrb.com/docs/posts/) first. When you've written a post or two, copy the following into a new file in your project directory called `blog.html`, and you'll see a link to your blog from the homepage:

```
---
layout: blog
title: My Blog
---
```

-- and that's it!

# Add a page

To add a page, just make a new .html or .md file in your project directory. There's an example called `reading-list` [provided](https://github.com/chrisbobbe/jekyll-theme-prologue/blob/master/reading-list.md) with the GitHub repository. Add this frontmatter:

```
---
title: My New Page
layout: page
---
```

You can also set these page variables in the frontmatter, if you want:
- `subtitle`
- `order` (orders links in the nav menu, e.g. `1`)
- `icon` (optional; see [Font Awesome](https://fontawesome.com/icons) for icon codes. Example: `fa-github`)
- `icon-style` (optional; "solid" is default, "regular" for outline style icons, or "brands" for logos)
- `hide` (optional; if `true`, a link won't appear in the nav menu. All this does is remove the nav link; your page will still be served to anyone who has the URL.)

**This same set of frontmatter variables (including `title`) can also be set in `index.md` and `blog.html`.** You may want to give them titles, or hide the homepage link with `hide: true` if the homepage is the only page.

# Credits

Thanks to @andrewbanchich for his many Jekyll adaptations of HTML5 UP's elegant themes, which helped and inspired me, and of course many thanks to HTML5 UP.

