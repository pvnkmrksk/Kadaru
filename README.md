# Kadaru ಕದರು

**Kadaru** (ಕದರು) means "mix" or "scramble" in Kannada. This web application scrambles images while preserving local texture and destroying global structure.

## 🌟 Features

### Scrambling Modes
- **Block Mode**: Splits the image into square blocks and shuffles them
- **Column Mode**: Splits the image into vertical strips/columns and shuffles them

### Customizable Parameters
- **Block Size / Column Count**: Control the granularity of scrambling
- **Max Block Distance**: Constrain how far blocks/columns can move (preserves some spatial locality)
- **Smoothing**: Cross-fade edges to eliminate harsh boundaries (Block mode only)
- **Seeded Random**: Consistent scrambling for the same image

### Additional Features
- Real-time preview with before/after comparison
- PNG download of scrambled images
- Maintains original image dimensions and quality
- Responsive design for mobile and desktop
- Beautiful, modern UI with gradient backgrounds

## 🚀 GitHub Pages Deployment

This project is ready to be deployed as a static GitHub Pages site. Follow these steps:

### Quick Setup

1. **Create a new GitHub repository** (or use an existing one)
2. **Push the files** to your repository:
   ```bash
   git init
   git add .
   git commit -m "Initial commit: Kadaru image scrambler"
   git branch -M main
   git remote add origin https://github.com/your-username/kadaru.git
   git push -u origin main
   ```

3. **Enable GitHub Pages**:
   - Go to your repository on GitHub
   - Navigate to **Settings** → **Pages**
   - Under "Source", select **"Deploy from a branch"**
   - Select branch: `main` and folder: `/ (root)`
   - Click **Save**

4. **Your site will be live at**: `https://your-username.github.io/kadaru/`

The `.nojekyll` file is included to ensure GitHub Pages serves the site correctly without Jekyll processing.

## 📖 How It Works

### Block Mode
- Divides image into a grid of square blocks
- Shuffles blocks using a seeded random number generator
- Optional distance constraint limits block movement
- Optional smoothing blends block edges

### Column Mode
- Divides image into N vertical strips
- Shuffles columns left-right
- Optional distance constraint limits column movement
- Preserves vertical coherence within each strip

### Seeded Randomization
The scrambler uses a seed derived from:
- Image dimensions (width × height)
- First 100 pixel values

This ensures:
- Same image always produces same scrambling
- Different images produce different scrambling
- Reproducible results

## 🎨 Use Cases

- **Privacy**: Obscure sensitive images while preserving texture
- **Art**: Create abstract compositions from photos
- **Research**: Study texture vs. structure in image recognition
- **Data Augmentation**: Generate varied training data

## 🛠️ Technical Details

- **Pure JavaScript**: No external dependencies
- **Canvas API**: Direct pixel manipulation
- **Client-side Processing**: All processing happens in browser
- **File Size**: Single HTML file (~15KB)
- **No Build Process**: Just upload and deploy!

## 📱 Browser Support

Works on all modern browsers:
- Chrome/Edge 90+
- Firefox 88+
- Safari 14+
- Mobile browsers (iOS Safari, Chrome Android)

## 🎯 Parameters Guide

### Block Size (Block Mode)
- **Small (1-10px)**: Fine-grained scrambling, abstract result
- **Medium (10-50px)**: Balanced, recognizable elements scrambled
- **Large (50px+)**: Coarse shuffling, maintains larger features

### Column Count (Column Mode)
- **Few (2-10)**: Large vertical strips, minimal scrambling
- **Medium (10-30)**: Balanced column shuffling
- **Many (30+)**: Fine vertical strips, heavily scrambled

### Max Block Distance
- **0% (Unlimited)**: Complete random shuffling
- **25-50%**: Moderate constraint, regional scrambling
- **75-100%**: Strong constraint, mostly local shuffling

### Smoothing (Block Mode)
- **0%**: Sharp block boundaries (fastest)
- **25-50%**: Subtle edge blending
- **75-100%**: Heavy blending, smooth transitions

## 💡 Tips

1. **Start with default settings** and adjust from there
2. **Large images** (>2000px) may be slow to process
3. **Smoothing** significantly increases processing time
4. **Column mode** is faster than block mode for most images
5. Use **distance constraints** to preserve some spatial structure

## 🐛 Known Limitations

- Very large images (>4000px) may cause slowdown
- Smoothing with large radius is computationally intensive
- Mobile browsers may have reduced performance

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🤝 Contributing

This is a single-file application. To modify:
1. Open `index.html` in a text editor
2. Make your changes
3. Test by opening in a browser
4. Deploy to GitHub Pages

## 📞 Support

For issues or questions:
- Open an issue on GitHub
- Check browser console for errors
- Ensure browser supports Canvas API

---

Made with ❤️ by [@pvnkmrksk](https://github.com/pvnkmrksk)
