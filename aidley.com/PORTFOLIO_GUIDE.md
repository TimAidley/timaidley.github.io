# Portfolio/Projects Page Guide

This guide explains how to manage and update your projects page on your Hugo website.

## Overview

Your projects page uses Hugo's Anatole theme portfolio feature with a YAML data file approach. All project information is stored in a single file for easy maintenance.

## File Structure

```
aidley.com/
├── data/
│   └── portfolio.yml              # Main project data file (EDIT THIS)
├── content/
│   └── portfolio/
│       └── _index.md              # Portfolio page metadata
├── static/
│   └── images/
│       └── projects/              # Project images directory
│           ├── games/             # Game project images
│           ├── software/          # Software project images
│           └── film/              # Film/TV project images
└── hugo.toml                      # Site config (menu already configured)
```

## How to Update Projects

### Editing Project Information

All project data is in [`aidley.com/data/portfolio.yml`](aidley.com/data/portfolio.yml). Edit this file to:
- Update project descriptions
- Add release dates
- Change project status
- Add or modify tags
- Add images (when ready)

### YAML Structure

The file is organized into three main categories:

```yaml
portfolioitems:
  - title: Games                    # Category name
    description: 'Category description'
    portfolioitem:                  # List of projects in this category
      - name: Project Name          # Required: Project title
        company: 'Company Name'     # Optional: Company you worked for
        image: '/images/projects/games/image.jpg'  # Optional: Box art/main image
        status: 'Released'          # Optional: Project status
        start: '2020'               # Optional: Release year or start date
        end: '2021'                 # Optional: End date (for ongoing projects)
        description: 'Your role'    # Required: Your contribution/role
        screenshots:                # Optional: List of screenshot paths
          - '/images/projects/games/screenshot1.jpg'
          - '/images/projects/games/screenshot2.jpg'
        tags:                       # Optional: List of tags
          - Platform
          - Technology
```

### Available Fields

- **name** (required): The project title
- **company** (optional): The company you worked for on this project (displays with a building icon)
- **image** (optional): Path to box art or main project image (relative to `/static/`). Displays on the left side.
- **status** (optional): Project status (e.g., "Released", "Unreleased", "In Development")
- **start** (optional): Release year or start date
- **end** (optional): End date for ongoing projects
- **description** (required): Your role and contributions to the project
- **screenshots** (optional): List of screenshot image paths (relative to `/static/`). Displays below the main content in a grid.
- **tags** (optional): List of relevant tags (platform, technology, genre, etc.)
- **link** (optional): External link to project website or more info
- **linktext** (optional): Custom text for the link button (defaults to "Visit Site")

### Adding a New Project

1. Open [`aidley.com/data/portfolio.yml`](aidley.com/data/portfolio.yml)
2. Find the appropriate category (Games, Other Software, or Film & Television)
3. Add a new entry under `portfolioitem:` following this template:

```yaml
      - name: New Project Name
        company: 'Company Name'
        image: '/images/projects/games/new-project.jpg'
        status: 'Released'
        start: '2024'
        description: 'Describe your role and contributions here'
        screenshots:
          - '/images/projects/games/new-project-screen1.jpg'
          - '/images/projects/games/new-project-screen2.jpg'
        tags:
          - Platform
          - Technology
```

### Adding Images

When you're ready to add images:

1. Place your image in the appropriate directory:
   - Games: `aidley.com/static/images/projects/games/`
   - Software: `aidley.com/static/images/projects/software/`
   - Film/TV: `aidley.com/static/images/projects/film/`

2. Update the project entry in [`portfolio.yml`](aidley.com/data/portfolio.yml):

```yaml
      - name: Project Name
        image: '/images/projects/games/your-image.jpg'  # Add this line
        status: 'Released'
        # ... rest of fields
```

**Image Guidelines:**
- Recommended size: 800x600 pixels or similar aspect ratio
- Supported formats: JPG, PNG, WebP, GIF
- Use descriptive filenames (e.g., `redline-racer-pc.jpg`)

### Updating Descriptions

Currently, all projects have placeholder text: "Your role and contribution to be added"

To update a project description:

1. Open [`aidley.com/data/portfolio.yml`](aidley.com/data/portfolio.yml)
2. Find the project you want to update
3. Replace the placeholder text with your actual role description

Example:
```yaml
      - name: Tilt Brush by Google
        company: 'Google'
        status: 'Released'
        start: '2016'
        description: 'Led the Oculus Quest port, optimizing rendering performance and adapting UI for standalone VR. Implemented custom shaders and memory management solutions.'
        tags:
          - VR
          - Google
          - Creative Tools
```

## Adding a New Category

To add a new project category:

1. Open [`aidley.com/data/portfolio.yml`](aidley.com/data/portfolio.yml)
2. Add a new section at the end of `portfolioitems:`:

```yaml
  - title: New Category Name
    description: 'Description of this category'
    portfolioitem:
      - name: First Project
        company: 'Company Name'
        description: 'Project details'
        # ... other fields
```

## Visual Layout

## Visual Layout

The portfolio uses a custom layout with:
- **Box art/main image** on the left (250px wide)
- **Project details** on the right (takes up remaining space)
  - Project name
  - Company, status, and date metadata with icons
  - Description
  - Tags
- **Screenshots section** below (optional)
  - Displays in a responsive grid
  - Automatically adjusts columns based on screen size

### Layout Features:
- Consistent left-to-right layout (no alternating)
- Responsive design for mobile devices
- Screenshot hover effects
- Clean separation between projects

## Testing Your Changes

After making changes:

1. Save [`portfolio.yml`](aidley.com/data/portfolio.yml)
2. Run your Hugo development server: `hugo server -D`
3. Navigate to: `http://localhost:1313/portfolio/`
4. Verify your changes appear correctly

## Tips

- Keep descriptions concise but informative (2-3 sentences)
- Use consistent tag naming across projects
- Add images gradually - the page works fine without them
- Use the `status` field to highlight unreleased or ongoing projects
- Consider adding `link` fields to projects with public websites or demos

## Need Help?

- Hugo Documentation: https://gohugo.io/documentation/
- Anatole Theme: https://github.com/lxndrblz/anatole
- YAML Syntax: https://yaml.org/spec/1.2.2/