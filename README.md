# Newsletter Template System Documentation

## Table of Contents

1. [Quick Reference](#quick-reference)
2. [Overview and Goals](#overview-and-goals)
3. [Folder Structure](#folder-structure)
4. [Naming Conventions](#naming-conventions)
5. [Snippet System](#snippet-system)
6. [Workflow Guide](#workflow-guide)

## Quick Reference

### Common Paths

```
# New campaign template
builds/[newsletter]/campaigns/

# Newsletter-specific blocks
builds/[newsletter]/blocks/

# Reusable components
design-system/components/

# Utility snippets
design-system/utilities/
```

### Naming Examples

```
# Components
components-headers
components-footers

# Utilities
utilities-journalist
utilities-spacing

# Newsletter-specific
sports-daily-header
politics-pm-footer
```

## Overview and Goals

### Key Objectives

- Create reusable snippets across multiple newsletters
- Provide flexible components through Iterable's "Variables"
- Enable easy discovery of snippets and templates
- Maintain consistent naming and organization
- Prevent regression issues through conditional rendering

### Discovery Methods

Editorial staff can find snippets through two primary methods:

1. **Direct Search**: Using the naming convention to search for specific snippets
2. **Template Browse**: Exploring template folders to see grouped snippets in context

For example, browsing `design-system > components > components-headers` shows all header snippets and their implementations, helping editors understand available options without diving into HTML.

## Folder Structure

### Template Organization

```
newsletter-modular/
├── archive/
├── builds/
│   ├── am-atl/
│   │   ├── blocks/
│   │   └── campaigns/
│   │       └── am-atl-base.html
│   ├── politics-pm/
│   │   ├── blocks/
│   │   │   └── politics-pm-header.html
│   │   └── campaigns/
│   │       └── politics-pm-base.html
│   ├── sports-daily/
│   │   ├── blocks/
│   │   │   └── sports-daily-header.html
│   │   └── campaigns/
│   │       └── sports-daily-base.html
│   └── uatl/
│       ├── campaigns/
│       └── core/
├── design-system/
│   ├── base-styles.html
│   ├── components/
│   │   ├── components-ads.html
│   │   ├── components-feeds.html
│   │   ├── components-footers.html
│   │   ├── components-headers.html
│   │   ├── components-showcase.html
│   │   └── components-text.html
│   └── utilities/
│       ├── utilities-date.html
│       ├── utilities-images.html
│       ├── utilities-journalist.html
│       ├── utilities-showcase.html
│       ├── utilities-spacing.html
│       └── utilities-unengaged.html
└── temporary/
```

### Campaigns Structure

```
newsletter-modular-campaigns/
├── am-atl/
├── politics-pm/
├── sports-daily/
└── uatl/
```

### Folder Purposes

- **archive**: Storage for deprecated templates and snippets
- **builds**: Newsletter-specific implementations and campaigns
- **design-system**: Reusable components and base styles
- **temporary**: Development and testing files

## Snippet System

### Organization Strategy

Since Iterable doesn't support folders in the Snippets section, we've implemented snippet folders within the Templates section to:

- Group related snippets
- Showcase example implementations
- Demonstrate best practices
- Provide visual reference for snippet options

## Naming Conventions

### Basic Rules

1. Use hyphens to separate elements
2. Use lowercase for all names
3. Start with category prefix
4. Mirror template folder structure in snippet names

### Pattern Examples

- `components-headers`
- `utilities-journalist`
- `sports-daily-[element]`

### Versioning Guidelines

Versioning should be avoided when possible, preferring conditional rendering. When necessary:

- Standard version: `sports-daily-header-v1`
- Semantic version: `sports-daily-header-braves-playoffs`

## Workflow Guide

### Creating New Templates

1. **Start Location**:

   - Build in `newsletter-modular > builds > [newsletter] > campaigns`
   - Copy existing template when possible
   - Use base template if starting fresh

2. **From Scratch Process**:
   - Copy base-styles from `newsletter-modular > design-system > base-styles`
   - Reference snippet templates for components
   - Import needed snippets with parameters
   - Add new conditional logic as needed

### Modifying Snippets

1. **Adding Features**:

   - Prefer adding if/else clauses to existing snippets
   - Avoid regression issues through conditional logic

2. **Major Changes**:
   - Create new version if changes affect existing uses
   - Place original in archive after deprecation
   - Create clean new version without version numbers

### Version Control

- Avoid versioning when possible
- Use conditional rendering for variations
- Create semantic names for special cases
- Archive deprecated versions promptly
