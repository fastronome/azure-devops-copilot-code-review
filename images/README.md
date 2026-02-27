# Extension Icons

The Azure DevOps marketplace requires a PNG icon (minimum 128x128 pixels).

## Current Status

Source logo is stored as `logo-fastronome.jpg`. Generated PNG variants are used for the extension manifests.

Current generated files:

- `logo-fastronome-128.png` - Marketplace manifest icon (used by `vss-extension*.json`)
- `logo-fastronome-256.png` - Higher-resolution icon variant
- `logo-fastronome.png` - Full-size PNG conversion of the source image

If you replace the source logo, regenerate the PNG variants:

```bash
convert images/logo-fastronome.jpg -strip -resize 256x256 images/logo-fastronome-256.png
convert images/logo-fastronome.jpg -strip -resize 128x128 images/logo-fastronome-128.png
convert images/logo-fastronome.jpg -strip images/logo-fastronome.png
```

## Recommended Icon Sizes

- Minimum: 128x128 pixels
- Recommended: 256x256 pixels for better quality on high-DPI displays

## Icon Guidelines

- Use simple, recognizable imagery
- Ensure good contrast for visibility
- Consider how it looks at small sizes
- Follow Azure DevOps marketplace branding guidelines
