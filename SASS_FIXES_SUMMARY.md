# Sass Deprecation Fixes Summary

This document summarizes the changes made to fix the Sass deprecation warnings related to `lighten()` and `darken()` functions in the shards-ui project.

## Changes Made

### 1. Updated Sass Files to Use New Color Functions

Replaced all instances of deprecated `lighten()` and `darken()` functions with:
- `color.scale()` for lightening colors
- `color.adjust()` for darkening colors

### 2. Added Required Module Imports

Added `@use "sass:color"` imports to the following files:
- `src/scss/shards.scss`
- `src/extras/scss/shards-extras.scss`
- `src/extras/scss/shards-demo.scss`
- `src/scss/mixins/_forms.scss`

### 3. Fixed Unit Issues

Fixed unit issues with color functions by ensuring all percentage values include the `%` symbol.

### 4. Updated Extras Stylesheets

Updated the following extras stylesheets to use the new color functions:
- `src/extras/scss/_agency-landing.scss`
- `src/extras/scss/_app-promo.scss`

## Files Modified

1. `src/scss/_variables.scss` - Replaced lighten/darken with color.scale/color.adjust
2. `src/scss/_custom-forms.scss` - Fixed unit issue
3. `src/scss/_functions.scss` - Fixed unit issue
4. `src/scss/_popover.scss` - Replaced darken with color.adjust
5. `src/scss/_custom-datepicker.scss` - Replaced lighten/darken with color.scale/color.adjust
6. `src/scss/_nav.scss` - Replaced lighten with color.scale
7. `src/scss/_alert.scss` - Replaced lighten with color.scale
8. `src/scss/mixins/_alert.scss` - Replaced darken with color.adjust
9. `src/scss/mixins/_background-variant.scss` - Replaced darken with color.adjust
10. `src/scss/mixins/_badge.scss` - Replaced darken with color.adjust
11. `src/scss/mixins/_buttons.scss` - Replaced darken with color.adjust
12. `src/scss/mixins/_forms.scss` - Added color module import and replaced lighten with color.scale
13. `src/scss/mixins/_list-group.scss` - Replaced darken with color.adjust
14. `src/scss/mixins/_table-row.scss` - Replaced darken with color.adjust
15. `src/scss/mixins/_text-emphasis.scss` - Replaced darken with color.adjust
16. `src/scss/utilities/_text.scss` - Replaced darken with color.adjust
17. `src/scss/shards.scss` - Added color module import
18. `src/extras/scss/shards-extras.scss` - Added color module import
19. `src/extras/scss/shards-demo.scss` - Added color module import
20. `src/extras/scss/_agency-landing.scss` - Replaced lighten with color.scale
21. `src/extras/scss/_app-promo.scss` - Replaced lighten with color.scale

## Results

The build now completes successfully without any `lighten()` or `darken()` deprecation warnings. The remaining deprecation warnings are from Bootstrap's own code and would require upgrading Bootstrap to fix.