# Changelog

## v2.4.0
- Paper-matte theme family
    - Replaced the light/dark toggle with a theme picker offering seven paper-matte variations: Paper, Parchment, Cream, Ivory, Kraft, Charcoal, Night
    - All surfaces, code viewers, badges, overlays, and syntax-highlight colors are theme-aware via CSS variables
    - Theme selection is saved in `localStorage` and honored before first paint to avoid flashes
- Optimizations
    - Removed the unused embedded bzip2 library (~260 lines) and the unused EVP_BytesToKey helper
    - Removed ~80 noisy `console.log` debug statements (actionable failure warnings retained)
    - File rows now use event delegation instead of inline `onclick` handlers with JSON-in-attribute quoting
- Enrichments
    - Search filter for the backup file list
    - Per-file download button in the preview modal
    - Escape key and backdrop click close all modals; focus is restored on close
    - Keyboard-accessible file rows (Enter/Space opens the preview)
    - Added meta description, theme-color, and an inline SVG favicon

## v2.0.1
- Maximum call stack size exceeded fix
    - Replaced the String.fromCharCode.apply(null, data) conversion with a safe Uint8Array→WordArray helper
    - Added uint8ArrayToWordArray to build CryptoJS WordArrays without apply
- Enhance file input styling and functionality

## v2.0.0 (Initial Release)
- Added BSON to JSON conversion in browser
- Automatic DEFLATE decompression for ZIP-compressed files
- Gzip decompression with proper magic byte detection
- Data descriptor handling for ZIP files
- Download fixed ZIP with all decompressed files
- CRC-32 validation for reconstructed ZIPs
- Enhanced file preview with hex dumps
- Improved error handling and logging

## v1.0 (Pre-release)
- Static AES-128-CBC decryption
- ZIP extraction and file listing
- File preview for text and images
- BSON database info
- Works with UniFi v7-v9.5+