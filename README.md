# Newsletter Template System Documentation

## Table of Contents

1. [Folder Structure](#folder-structure)
2. [Naming Conventions](#naming-conventions)
3. [Best Practices](#best-practices)
4. [Template Creation Guide](#template-creation-guide)
5. [Validation Checklist](#validation-checklist)

## Folder Structure

### Root Organization

```
newsletter-modular/
├── archive/
├── builds/
│   ├── am-atl/
│   ├── politics-pm/
│   ├── sports-daily/
│   └── uatl/
├── design-system/
└── temporary/
```

### Design System Structure

```
design-system/
├── base-styles.html
├── components/
│   ├── components-ads.html
│   ├── components-feeds.html
│   ├── components-footers.html
│   ├── components-headers.html
│   ├── components-showcase.html
│   └── components-text.html
└── utilities/
    ├── utilities-date.html
    ├── utilities-images.html
    ├── utilities-journalist.html
    ├── utilities-showcase.html
    ├── utilities-spacing.html
    └── utilities-unengaged.html
```

### Purpose of Each Directory

#### Core Directories

- **archive**: Storage for deprecated templates and snippets
- **builds**: Newsletter-specific implementations and campaigns
- **design-system**: Reusable components and base styles
- **temporary**: Development and testing files

#### Build Categories

- **campaigns**: Active newsletter templates
- **blocks**: Newsletter-specific components
- **core**: Essential newsletter elements

## Naming Conventions

### Basic Rules

1. Use hyphens to separate elements
2. Use lowercase for all names
3. Start with category prefix
4. Be descriptive but concise

### Pattern

```
[category]-[subcategory]-[element]
```

### Examples

- `components-headers`
- `utilities-journalist`
- `sports-daily-header`

### Versioning (When Necessary)

```
[standard-name]-v[version_number]
```

Example: `sports-daily-header-v1`

## Best Practices

### Snippet Development

1. **Prioritize Reusability**

   - Use conditional rendering over versioning
   - Keep snippets flexible through variables
   - Implement modular design

2. **Documentation**

   - Include clear descriptions
   - Document all available parameters
   - Provide usage examples

3. **Maintenance**
   - Archive unused versions
   - Avoid duplicate snippets
   - Use semantic naming for special cases

### Workflow Guidelines

1. Start with existing templates when possible
2. Reference design system components
3. Copy base styles for new templates
4. Use conditional logic for variations
5. Archive outdated versions

## Template Creation Guide

### Steps for Creating New Templates

1. Check `builds` folder for similar templates
2. Start from base template or copy existing
3. Import required design system components
4. Add newsletter-specific customizations
5. Test with various content scenarios

### Documentation Example

```
Description:
[Purpose of the template/snippet]

Parameters:
- [paramName]: [description] (required/optional)
- [paramName]: [description] (required/optional)

Usage:
[Implementation examples]

Notes:
[Additional information]
```

## Validation Checklist

### Pre-Creation

- [ ] Verified no existing template serves the same purpose
- [ ] Identified appropriate location in builds folder
- [ ] Planned for variations and use cases
- [ ] Determined required components and utilities

### Implementation

- [ ] Follows naming convention
- [ ] Uses base styles appropriately
- [ ] Implements conditional rendering where needed
- [ ] Includes all required snippets
- [ ] Tested with sample content

### Documentation

- [ ] Clear description provided
- [ ] All parameters documented
- [ ] Usage examples included
- [ ] Limitations noted
- [ ] Added to relevant campaign folder

### Maintenance

- [ ] Versioned if necessary
- [ ] Old versions archived
- [ ] Updated folder structure
- [ ] Team notified of new template

## Quick Reference

### Common Folder Paths

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

### Versioning Notes

```
# Avoid when possible, use conditional rendering instead
sports-daily-header-v1
sports-daily-header-braves-playoffs

# Preferred approach
components-headers.html with conditional logic
```
