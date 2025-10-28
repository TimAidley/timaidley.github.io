# Project Images Directory

This directory contains images for the portfolio/projects page.

## Directory Structure

- `games/` - Images for video game projects
- `software/` - Images for software and tools projects
- `film/` - Images for film and TV projects

## Adding Images

1. Place your project images in the appropriate subdirectory
2. Use descriptive filenames (e.g., `redline-racer-pc.jpg`, `tilt-brush.png`)
3. Recommended image dimensions: 800x600 pixels or similar aspect ratio
4. Supported formats: JPG, PNG, WebP, GIF

## Updating the Portfolio

To add an image to a project, edit `aidley.com/data/portfolio.yml` and add the `image` field:

```yaml
- name: Project Name
  image: '/images/projects/games/project-name.jpg'
  status: 'Released'
  start: '2020'
  description: 'Your role description'
  tags:
    - Tag1
    - Tag2
```

The image path should be relative to the `static` directory, starting with `/images/projects/`.