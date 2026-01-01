# 🌟 DAEMON - Your Living Desktop Companion

DAEMON is an interactive 3D desktop pet that brings life to your workspace. Watch as a dynamic, evolving organism responds to your activity, changes with the time of day, and creates a unique ambient experience on your desktop.

![DAEMON Preview](https://via.placeholder.com/800x400?text=DAEMON+Desktop+Pet)

## ✨ What Makes DAEMON Special

DAEMON isn't just another desktop widget—it's a living, breathing companion that:

- **Responds to Your Activity**: The organism reacts to file system changes, growing and evolving as you work
- **Adapts to Time**: Watch the environment shift from day to night with dynamic lighting and atmosphere
- **Lives on Your Desktop**: Runs as a transparent overlay that doesn't interfere with your workflow
- **Mesmerizing 3D Graphics**: Built with Three.js for smooth, beautiful animations
- **Lightweight & Efficient**: Optimized performance that won't slow down your system

## 🚀 Installation

### Prerequisites

Before you begin, ensure you have the following installed:

- **Node.js** (v18 or higher) - [Download here](https://nodejs.org/)
- **npm** (comes with Node.js) or **yarn**
- **Git** (optional, for cloning) - [Download here](https://git-scm.com/)

### Step-by-Step Installation

1. **Clone the repository** (or download the ZIP):

```bash
git clone https://github.com/goatfahad/DAEMON.git
cd DAEMON
```

2. **Install dependencies**:

```bash
npm install
# or if you prefer yarn
yarn install
```

3. **Run in development mode**:

```bash
npm run dev
# or
yarn dev
```

4. **Build for production**:

```bash
npm run build
# or
yarn build
```

5. **Package the application** (creates distributable):

```bash
npm run package
# or
yarn package
```

## 📖 Usage Examples

### Basic Usage

Once installed and running, DAEMON will appear as a transparent window on your desktop. The organism will:

1. **Monitor your file system** - As you create, modify, or delete files, DAEMON responds with visual changes
2. **Track time of day** - The lighting and atmosphere automatically adjust based on your system time
3. **Evolve organically** - The 3D form shifts and morphs, creating a unique experience every time

### Customization

You can customize DAEMON's behavior by modifying the configuration:

**Adjust organism sensitivity** (in `src/hooks/useDaemon.ts`):
```typescript
// Change how responsive the organism is to file changes
const SENSITIVITY = 0.5; // Range: 0.0 to 1.0
```

**Modify visual appearance** (in `src/components/Organism.tsx`):
```typescript
// Customize colors, size, and animation speed
const color = new THREE.Color(0x00ff88); // Change organism color
const scale = 2.0; // Adjust size
```

**Change monitoring directory** (in `electron/main.ts`):
```typescript
// Monitor a specific folder instead of home directory
const watchPath = 'C:\\Users\\YourName\\Documents';
```

### Keyboard Shortcuts

- **Ctrl+Q** (Windows/Linux) or **Cmd+Q** (Mac) - Quit DAEMON
- **Ctrl+R** (Windows/Linux) or **Cmd+R** (Mac) - Reload (development mode)
- **F12** - Open Developer Tools (development mode)

## 🛠️ Tech Stack

DAEMON is built with modern, cutting-edge technologies:

- **[React 19](https://react.dev/)** - UI framework with latest features
- **[TypeScript](https://www.typescriptlang.org/)** - Type-safe development
- **[Electron 33](https://www.electronjs.org/)** - Cross-platform desktop framework
- **[Three.js](https://threejs.org/)** - 3D graphics and animations
- **[@react-three/fiber](https://docs.pmnd.rs/react-three-fiber/)** - React renderer for Three.js
- **[Vite](https://vitejs.dev/)** - Lightning-fast build tool
- **[Tailwind CSS 4](https://tailwindcss.com/)** - Utility-first styling

## 📁 Project Structure

```
electron-pixel-pet/
├── electron/              # Electron main process
│   ├── main.ts          # Main process entry point
│   ├── preload.ts       # Preload script for IPC
│   └── electron.d.ts    # TypeScript definitions
├── src/                 # React application
│   ├── components/      # React components
│   │   ├── Organism.tsx # 3D organism component
│   │   └── Scene.tsx    # Three.js scene setup
│   ├── hooks/           # Custom React hooks
│   │   └── useDaemon.ts # File system monitoring hook
│   ├── App.tsx          # Main app component
│   └── main.tsx         # React entry point
├── public/              # Static assets
├── scripts/             # Build and utility scripts
├── package.json         # Dependencies and scripts
├── vite.config.ts       # Vite configuration
└── tsconfig.json        # TypeScript configuration
```

## 🎯 Key Features

### 1. **Real-Time File System Monitoring**
DAEMON watches your file system and responds to changes in real-time. Every file creation, modification, or deletion triggers a visual response in the organism.

### 2. **Dynamic Day/Night Cycle**
The environment automatically adjusts based on your system time:
- **Morning (6 AM - 12 PM)**: Bright, energetic lighting
- **Afternoon (12 PM - 6 PM)**: Warm, golden tones
- **Evening (6 PM - 10 PM)**: Soft, ambient lighting
- **Night (10 PM - 6 AM)**: Cool, calm atmosphere

### 3. **Transparent Desktop Overlay**
Runs as a click-through transparent window that sits on your desktop without interfering with your work.

### 4. **Optimized Performance**
Recent optimizations include:
- Reduced 3D mesh complexity for better frame rates
- Throttled file system events to prevent overload
- Batch processing for efficient IPC communication
- Memoized components to minimize re-renders

### 5. **Cross-Platform Support**
Built with Electron, DAEMON runs on:
- Windows 10/11
- macOS (10.13+)
- Linux (Ubuntu, Fedora, etc.)

## 🐛 Troubleshooting

### DAEMON won't start
- Ensure Node.js v18+ is installed: `node --version`
- Delete `node_modules` and reinstall: `rm -rf node_modules && npm install`
- Check for port conflicts (Vite uses port 5173 by default)

### Performance issues
- Close other resource-intensive applications
- Reduce organism complexity in `Organism.tsx` (lower segment count)
- Disable file system monitoring temporarily for testing

### Transparent window not working
- Ensure your system supports transparency (some Linux window managers may not)
- Check GPU drivers are up to date
- Try disabling hardware acceleration in Electron settings

### File system monitoring not responding
- Verify the monitored path exists and is accessible
- Check file permissions for the watched directory
- Review console logs for error messages

## 🔮 Future Roadmap

- [ ] **Multiple organism types** - Choose from different visual styles
- [ ] **Sound effects** - Audio feedback for interactions
- [ ] **User preferences panel** - GUI for customization
- [ ] **Cloud sync** - Save your organism's state across devices
- [ ] **Interaction modes** - Click and drag to interact with the organism
- [ ] **Performance metrics** - Display system stats within the organism
- [ ] **Themes** - Pre-built color schemes and styles

## 📄 License

This project is licensed under the MIT License - see the LICENSE file for details.

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## 💬 Support

If you encounter any issues or have questions:
- Open an issue on GitHub
- Check existing issues for solutions
- Join our community discussions

---

**Made with ❤️ by developers who believe your desktop should be alive**
