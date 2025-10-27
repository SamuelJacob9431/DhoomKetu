# DhoomKetu - Asteroid Impact Simulator

## Overview

DhoomKetu is an interactive 3D visualization tool that simulates asteroid impacts on Earth using real NASA Near-Earth Object (NEO) data. The application provides realistic impact modeling with visual effects, damage radius calculations, and fatality estimates based on population density.

## Features

- **Real NASA Data Integration**: Fetches current asteroid data from NASA's NEO API
- **3D Earth Visualization**: Interactive globe with realistic textures and cloud layers
- **Impact Simulation**: Visualizes asteroid entry, impact effects, and crater formation
- **Damage Assessment**: Calculates and displays multiple impact zones:
  - Fireball radius
  - Destruction radius  
  - Ejecta radius
  - Danger and warning zones
- **Fatality Estimation**: Estimates casualties based on population density context
- **Text-to-Speech**: Audio summary of impact results
- **Responsive Design**: Works on both desktop and mobile devices

## Technical Implementation

### Core Technologies
- Three.js for 3D rendering and visualization
- NASA NEO API for real asteroid data
- Web Audio API for sound effects
- Speech Synthesis API for text-to-speech
- Responsive CSS with mobile-first design

### Key Components

#### Impact Physics Model
- Calculates energy release in megatons
- Determines impact outcome (airburst vs. crater formation)
- Models thermal radiation, overpressure, and seismic effects
- Estimates crater dimensions for ground impacts

#### Visualization Features
- Realistic Earth model with color, specular, bump, and cloud textures
- Animated asteroid entry trajectories
- Visual effects for impacts (flashes, shockwaves, debris)
- Interactive radius rings showing damage zones
- Crater decals for ground impacts

#### User Interface
- Left-side control panel (desktop) or bottom sheet (mobile)
- Asteroid selection from NASA data
- Adjustable entry angle and speed parameters
- Population density settings
- Interactive globe for impact location selection
- Screen-anchored information cards

## Setup and Usage

### Prerequisites
- Modern web browser with WebGL support
- Internet connection for CDN resources and NASA API

### Installation
1. Clone or download the project files
2. Serve via HTTP server (not file:// protocol due to CORS)
3. Open index.html in a web browser

### Basic Operation
1. Select an asteroid from the dropdown (loaded from NASA NEO API)
2. Adjust impact parameters:
   - Entry angle (15-90 degrees)
   - Speed (5-70 km/s, or use NASA data)
   - Population density context
3. Click on the globe to choose impact location
4. Click "LAUNCH" to simulate the impact
5. View results in the legend panel and listen to TTS summary

## File Structure
```
dhoomketu/
├── index.html          # Main application file
├── textures/           # Earth texture assets
│   ├── earth_color_custom.jpg
│   ├── earth_spec_custom.jpg  
│   ├── earth_bump_custom.jpg
│   └── earth_clouds_8k.jpg
└── boom.wav           # Impact sound effect
```

## API Integration

### NASA NEO API
- Endpoint: `https://api.nasa.gov/neo/rest/v1/feed`
- Fetches asteroids approaching Earth on the current date
- Provides diameter estimates and velocity data
- Falls back to preset data if API is unavailable

## Browser Compatibility
- Chrome 60+
- Firefox 55+
- Safari 11+
- Edge 79+

## Performance Considerations
- Automatic texture quality fallbacks
- Geometry disposal for memory management
- Responsive design for various screen sizes
- Mobile-optimized touch interactions

## License
This project is for educational and demonstration purposes. NASA data usage should comply with their terms of service.

## Acknowledgments
- NASA for asteroid data and imagery
- Three.js community for 3D graphics framework
- Cloud texture resources from Three.js examples
