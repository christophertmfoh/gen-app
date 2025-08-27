# For Generations - Pony V6 XL Prompt Generator

A sophisticated, single-file React SPA for generating high-quality prompts for Pony Diffusion V6 XL. Built for creators who need consistent, professional NSFW anime outputs with modular control over subjects, poses, expressions, locations, styles, and LoRAs.

![Modern UI Screenshot](https://via.placeholder.com/800x400/0f172a/0ea5e9?text=For+Generations+UI)

## ⚠️ Content Warning

**This application is designed for adult content creation only.** It generates explicit prompts for AI image generation. Users must be 18+ and should follow ethical AI practices.

## 🚀 Quick Start

### Option 1: Direct Browser Use (Recommended)
1. Download `for-generations.html`
2. Open the file in any modern web browser
3. Start generating prompts immediately!

### Option 2: Local Server
```bash
# Using Python 3
python3 -m http.server 8000
# Then open http://localhost:8000/for-generations.html

# Using Node.js
npx serve .
# Then open the provided URL
```

## ✨ Features

### 🎯 Core Functionality
- **📦 Complete Content Catalog**: 40 subjects, 40 poses, 20 expressions, 20 locations, 20 styles, 31 LoRAs
- **🎲 Smart Randomization**: Cryptographically secure RNG with seeded PRNG for reproducible results
- **🔒 Character LoRA Priority**: Character LoRAs automatically override generic subjects
- **🎨 Style Blending**: Mix 2-3 styles with intelligent weighting
- **📝 Perfect Prompt Structure**: Follows exact Pony V6 XL placement rules
- **🚫 No E-Girl Bias**: Only includes e-girl aesthetic if randomly selected

### 🛠️ Advanced Controls
- **🔄 No-Repeat System**: Exhausts each category before repeating
- **🔐 Individual Locks**: Lock specific categories (Subject/Pose/Expression/Location/Style)
- **🎛️ LoRA Management**: 0-5 LoRA selection with automatic weight assignment
- **🌱 Seed Locking**: Deterministic generation for consistent results
- **⚙️ Settings Randomization**: Randomize sampler, steps, CFG, etc.

### 💾 Data Management
- **➕ Add Custom Content**: Seamlessly add new subjects, poses, expressions, locations, styles, and LoRAs
- **✅ Built-in Validation**: Checks for duplicates, weight ranges, and formatting
- **💾 Auto-Persistence**: All additions saved to localStorage
- **📊 Export Options**: Download prompts (.txt) and complete catalog (.json)
- **🕐 History Tracking**: Last 20 generations with restore functionality

## 🎨 How to Use

### Basic Generation
1. **Click "Generate Prompt"** - Creates a complete prompt with all components
2. **Copy Components** - Click any catalog item to copy it to clipboard
3. **Copy Outputs** - Use copy buttons for Prompt, Negative Prompt, and Settings

### Customization Options
- **🎛️ Toggles**: Configure generation behavior (no-repeat, style blending, etc.)
- **🔒 Locks**: Prevent specific categories from changing on re-generation
- **🎚️ LoRA Slider**: Control how many LoRAs to include (0-5)
- **🌱 Seed Control**: Lock seed for consistent results across generations

### Adding New Content
Each category has an "Add New" form in the catalog:
- **Subjects**: Full character descriptions
- **Poses**: Text + camera angle
- **Expressions**: Name + optional weight range
- **Locations**: 2-3 environmental details
- **Styles**: Artistic style descriptions
- **LoRAs**: Name, triggers, weights, notes

## 📋 Generated Output Structure

### Prompt Format
```
1girl, score_9, score_8_up, score_7_up, score_6_up, score_5_up, score_4_up, source_anime, rating_explicit, (1girl:1.3), [SUBJECT], with [EXPRESSION], [POSE], [ANGLE], in [LOCATION], [STYLE], <lora:NAME:WEIGHT>, [TRIGGERS]
```

### Settings JSON
```json
{
  "model": "Perfect Pony XL V6",
  "sampler": "Euler a",
  "steps": 25,
  "cfg": 7.0,
  "hires_strength": 0.4,
  "aspect_ratio": "512x768",
  "clip_skip": -2,
  "prompt_enhance": true,
  "prompt_behavior": "V2 Unlimited",
  "upscaler": "REAL-ESRGAN-X4-ANIME-CFORMER",
  "seed": 1234567890
}
```

## 🔧 Technical Details

### Architecture
- **Single HTML File**: No build process required
- **React 18**: Modern hooks-based components
- **Tailwind CSS**: Utility-first styling with custom theme
- **Babel Standalone**: Client-side JSX compilation
- **LocalStorage**: Persistent user data and history

### Browser Compatibility
- **Chrome/Chromium**: Full support
- **Firefox**: Full support
- **Safari**: Full support
- **Edge**: Full support
- **Mobile Browsers**: Responsive design

### Data Structure
```javascript
{
  subjects: [{id, description}],
  poses: [{id, text, angle}],
  expressions: [{id, text, weightRange?}],
  locations: [{id, text}],
  styles: [{id, text}],
  loras: [{id, name, triggers, weightRange, notes?, tattooPlacements?}]
}
```

## 🎮 LoRA Classification System

The app automatically categorizes LoRAs by type:

| Type | Color | Examples | Behavior |
|------|-------|----------|----------|
| **CHARACTER** | Pink | Rebecca, Lucy, Rogue | Override subjects |
| **STYLE** | Blue | Vintage, Gothic, Pop Art | Artistic effects |
| **LIGHTING** | Yellow | S1 Dramatic Lighting | Illumination |
| **POSE** | Purple | Bestfootpose, Prone | Body positioning |
| **CONCEPT** | Green | Tattoos, E-Girls | Thematic elements |

## 📱 User Interface

### Modern Design Features
- **🌙 Dark Theme**: Professional dark interface with subtle gradients
- **✨ Glass Morphism**: Backdrop blur effects and transparency
- **🎨 Color-Coded Sections**: Each content type has its own accent color
- **📱 Responsive**: Works on desktop, tablet, and mobile
- **♿ Accessible**: WCAG compliant with proper focus management

### Visual Indicators
- **🔵 Dots**: Section identifiers with category colors
- **🏷️ Tags**: LoRA type badges with color coding
- **📊 Progress**: LoRA count with usage recommendations
- **⚡ Animations**: Smooth transitions and hover effects

## 🛡️ Privacy & Security

- **🔒 Client-Side Only**: No server communication
- **💾 Local Storage**: All data stays on your device
- **🔐 Secure RNG**: Uses crypto.getRandomValues() when available
- **🚫 No Analytics**: No tracking or data collection

## 🐛 Troubleshooting

### Common Issues

**Q: LoRA slider shows warning**
A: More than 5 LoRAs can cause image degradation. Keep at 5 or below.

**Q: Character LoRA not overriding subject**
A: Make sure the LoRA is properly classified. Check the pink "CHARACTER" tag.

**Q: Custom items not persisting**
A: Ensure your browser allows localStorage. Check browser settings.

**Q: Validation errors when adding content**
A: Check for duplicate names/descriptions and ensure weight ranges are valid (min ≤ max).

### Browser Requirements
- **JavaScript**: Must be enabled
- **Local Storage**: Must be allowed
- **Modern Browser**: Chrome 60+, Firefox 60+, Safari 12+, Edge 79+

## 📄 File Structure

```
for-generations.html          # Complete single-file application
README.md                    # This documentation
for generations packet.txt   # Source data (embedded in HTML)
```

## 🤝 Contributing

This is a single-file application with embedded data. To modify:

1. **Edit Content**: Use the built-in "Add New Items" interface
2. **Export Data**: Use the "Download .json" button to backup your catalog
3. **Code Changes**: Edit the `for-generations.html` file directly

## 📚 Prompt Engineering Notes

### Best Practices
- **Quality Tags**: Always included automatically (score_9, etc.)
- **Subject Placement**: Character description comes first after base tags
- **Expression Timing**: Placed immediately after subject for proper context
- **LoRA Balance**: 1-4 LoRAs typically work best
- **Style Blending**: Use sparingly for best results

### Pony V6 Specific
- **Rating Tags**: `rating_explicit` for NSFW content
- **Source Tags**: `source_anime` for anime style
- **Negative Prompt**: Always includes standard TI codes and artifact blockers

## 🔗 Integration

### Mage.space Compatible
All generated settings work directly with Mage.space:
- Copy the settings JSON
- Copy prompt and negative prompt
- Use provided sampler/steps/CFG values

### Other Platforms
Settings can be adapted for:
- **Automatic1111**: Use sampler and steps values
- **ComfyUI**: Extract individual parameters
- **Invoke AI**: Most settings transfer directly

## 📄 License

This project is provided as-is for adult content creators. Use responsibly and follow ethical AI practices.

---

**Made for creators who demand quality and control in their AI art generation workflow.**