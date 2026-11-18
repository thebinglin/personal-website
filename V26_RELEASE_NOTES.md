# Version 26 — divider seam and modest image-height adjustments

This small update changes only the shared layout stylesheet imports and a new `src/styles/v26.css` file.

- Research and Photography now use a **paint-backed SVG wave** in the exact colour of the following section. The heroes no longer have a transparent mask revealing the outer page background.
- Removed the negative-margin underlap between those two hero images and their next sections. This eliminates a source of dark-colour seams.
- Research, Photography, and Writing images are each approximately 5% shorter than the natural image ratio, with full page width retained. At widths below 700 px, cropping is only about 2.5% for better text room.
- Home and Book heroes are left alone.

## Validation

Check the Research and Photography hero boundaries after deploying, at wide desktop and narrow phone widths. The build command remains `npm run build`, output directory `dist`. No Cloudflare configuration changes are needed.
