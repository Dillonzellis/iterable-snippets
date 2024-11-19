# Newsletter Template System Documentation

## Table of Contents

1. [Folder Structure](#folder-structure)
2. [Naming Conventions](#naming-conventions)
3. [Best Practices](#best-practices)
4. [Snippet Creation Guide](#snippet-creation-guide)
5. [Validation Checklist](#validation-checklist)

## Folder Structure

### Root Organization

```
Templates/
└── Newsletter_Modular/
    ├── Config/
    ├── Snippets/
    ├── Newsletter Specific/
    ├── Temporary/
    └── Archive/
```

### Snippets Directory Structure

```
Snippets/
├── Styles/
│   ├── Base Styles
│   ├── Branding Colors
│   └── Layouts/
├── Content-Blocks/
├── Components/
│   ├── Headers
│   ├── Footers
│   ├── Ads
│   └── Interactive
├── Typography/
├── Utility/
└── Helpers/
```

### Purpose of Each Directory

#### Core Directories

- **Config**: Global configuration and variables
- **Snippets**: Reusable components and layouts
- **Newsletter Specific**: Custom implementations for individual newsletters
- **Temporary**: Testing and development files
- **Archive**: Deprecated or seasonal content

#### Snippet Categories

- **Styles**: Base styling, branding, and layout frameworks
- **Content-Blocks**: Major content section templates
- **Components**: Standalone, reusable UI elements
- **Typography**: Text styling and formatting
- **Utility**: Helper classes and common utilities
- **Helpers**: Building blocks for larger snippets

## Naming Conventions

### Basic Rules

1. Use underscores to separate hierarchical elements
2. Use lowercase for all names
3. Mirror the folder structure in the name
4. Be descriptive but concise

### Pattern

```
[category]_[subcategory]_[element]
```

### Examples

- `components_header_main`
- `typography_heading_h1`
- `utility_divider_horizontal`
- `styles_layout_2column`

### Versioning (When Necessary)

```
[standard_name]_v[version_number]
```

Example: `components_header_v2`

## Best Practices

### Snippet Development

1. **Prioritize Reusability**

   - Use Iterable Variables for customizable elements
   - Implement conditional rendering for variations
   - Keep snippets modular and single-purpose

2. **Documentation**

   - Include clear descriptions for each snippet
   - Document all available variables and options
   - Provide usage examples

3. **Maintenance**
   - Avoid creating duplicate snippets
   - Use versioning only when necessary
   - Move deprecated snippets to Archive folder

### Variable Usage

```handlebars
{{#ifMatchesRegexStr newsletter "pattern"}}
  <div>Conditional Content</div>
{{/ifMatchesRegexStr}}

{{#assign "variableName"}}content{{/assign}}
```

## Snippet Creation Guide

### Steps for Creating New Snippets

1. Check existing snippets for similar functionality
2. Determine appropriate category and naming
3. Create snippet with proper documentation
4. Test across different newsletter types
5. Add usage examples to Main-All-Snippets-Example

### Documentation Template

```
Description:
[Brief description of snippet purpose]

Variables:
- [variableName]: [description] (required/optional)
- [variableName]: [description] (required/optional)

Usage Examples:
[Include common implementation examples]

Notes:
[Any additional information or special considerations]
```

## Validation Checklist

### Pre-Creation

- [ ] Verified no existing snippet serves the same purpose
- [ ] Identified appropriate category and subcategory
- [ ] Planned for potential variations and use cases
- [ ] Determined required variables and options

### Implementation

- [ ] Follows naming convention
- [ ] Uses proper variable structure
- [ ] Implements conditional rendering where needed
- [ ] Includes responsive design considerations
- [ ] Tested across email clients

### Documentation

- [ ] Clear description provided
- [ ] All variables documented
- [ ] Usage examples included
- [ ] Edge cases and limitations noted
- [ ] Added to Main-All-Snippets-Example if applicable

### Quality Assurance

- [ ] Tested in all target newsletters
- [ ] Validated HTML structure
- [ ] Checked for accessibility compliance
- [ ] Verified responsive behavior
- [ ] Reviewed by team member

### Maintenance

- [ ] Added to version control (if applicable)
- [ ] Old versions properly archived
- [ ] Updated main documentation
- [ ] Team notified of new snippet availability

## Quick Reference

### Common Variables

```handlebars
{{newsletter}}
- Newsletter identifier
{{section}}
- Content section
{{theme}}
- Visual theme
{{layout}}
- Layout type
```

### Frequent Patterns

```handlebars
<!-- Newsletter-specific content -->
{{#ifMatchesRegexStr newsletter "AM"}}
  <div>AM Newsletter Content</div>
{{/ifMatchesRegexStr}}

<!-- Theme variations -->
{{#ifMatchesRegexStr theme "dark"}}
  <div class="dark-theme">...</div>
{{/ifMatchesRegexStr}}

<!-- Layout options -->
{{#ifMatchesRegexStr layout "2col"}}
  <div class="two-column">...</div>
{{/ifMatchesRegexStr}}
```
