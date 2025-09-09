# Technology Stack and Architecture Guidelines

## Overview

This document defines the technology choices, architectural patterns, and engineering practices for the Interactive Solar System Simulation. It serves as the authoritative guide for all technical decisions and implementation approaches in this educational physics simulation.

## Core Technology Stack

### Frontend Runtime Environment
- **Platform**: Client-side web application (browser-based)
- **Target Browsers**: Chrome 80+, Firefox 75+, Safari 13+, Edge 80+
- **WebGL**: Required for Three.js 3D rendering
- **ES Modules**: Modern JavaScript module system with import maps

### 3D Graphics and Physics
- **3D Rendering**: Three.js 0.158+
  - WebGL-based 3D graphics rendering
  - Comprehensive geometry, materials, and lighting system
  - Extensive addon library (OrbitControls, etc.)
  - Active community and excellent documentation
- **Physics Engine**: Custom gravitational physics implementation
  - Newton's law of universal gravitation
  - Verlet integration for numerical stability
  - N-body gravitational interactions
  - Energy conservation monitoring

### JavaScript Architecture
- **Language**: Vanilla JavaScript (ES6+)
  - No build system complexity for educational transparency
  - Direct browser compatibility
  - Easy to understand and modify for learners
- **Module System**: ES6 modules with import maps
  - Clean separation of concerns
  - Explicit dependencies
  - Modern browser native support
- **Class-Based Architecture**: Object-oriented design
  - Clear inheritance relationships
  - Encapsulation of related functionality
  - Familiar patterns for educational purposes

### Data and Configuration
- **Astronomical Data**: Static JavaScript objects (CELESTIAL_DATA)
  - NASA/JPL-sourced planetary parameters
  - Masses, radii, orbital distances, rotation periods
  - Moon systems and planetary characteristics
- **No External Database**: Self-contained application
  - All data embedded in JavaScript
  - No server-side dependencies
  - Easy deployment and sharing

## Architecture Patterns

### Modular Class-Based Architecture

#### Core Class Structure
```
┌─────────────────────────────────┐
│            App (main.js)              │  ← Main application controller
│  - UI event handling                  │
│  - Keyboard shortcuts                 │
│  - Application lifecycle              │
├─────────────────────────────────┤
│  SolarSystemSimulation (simulation.js)│  ← 3D rendering and visualization
│  - Three.js scene management          │
│  - Camera and controls                │
│  - Mesh creation and updates          │
│  - User interaction handling          │
├─────────────────────────────────┤
│      PhysicsEngine (physics.js)       │  ← Physics calculations
│  - Gravitational force calculations   │
│  - Velocity and position updates      │
│  - Energy conservation monitoring     │
│  - Time manipulation (rewind/FF)      │
├─────────────────────────────────┤
│   CelestialBody (celestial-bodies.js) │  ← Individual celestial objects
│  - Position and velocity data         │
│  - Physical properties (mass, radius) │
│  - Orbital path tracking              │
│  - Rotation and rendering state       │
├─────────────────────────────────┤
│  SolarSystemFactory (celestial-bodies)│  ← System creation and configuration
│  - Solar system instantiation         │
│  - Custom body creation               │
│  - Orbital velocity calculations      │
└─────────────────────────────────┘
```

#### Key Architectural Principles
- **Single Responsibility**: Each class has a focused purpose (physics, rendering, data)
- **Loose Coupling**: Classes interact through well-defined interfaces
- **Composition Over Inheritance**: PhysicsEngine and rendering logic composed together
- **Data-Driven Design**: Celestial body properties defined in static data structures

### Physics Simulation Architecture

#### Gravitational N-Body System
```javascript
// Core physics loop pattern
class PhysicsEngine {
  step() {
    this.saveState();           // Save current state for rewind capability
    this.updateVelocities();    // Calculate gravitational forces
    this.updatePositions();     // Update positions based on velocities
    this.currentTimeIndex++;    // Advance simulation time
  }
  
  calculateGravitationalForce(body1, body2) {
    // F = G * m1 * m2 / r^2
    // Applied as vector force in 3D space
  }
}
```

#### Time Management
- **Discrete Time Steps**: Fixed time step (86400 seconds = 1 day)
- **Variable Time Multiplier**: User-controllable simulation speed
- **State History**: Circular buffer for rewind functionality
- **Energy Monitoring**: Track conservation for simulation validation

### 3D Rendering Architecture

#### Three.js Scene Management
```javascript
// Scene composition pattern
class SolarSystemSimulation {
  constructor() {
    this.scene = new THREE.Scene();           // 3D world container
    this.camera = new THREE.PerspectiveCamera(); // View perspective
    this.renderer = new THREE.WebGLRenderer();   // WebGL rendering
    this.controls = new OrbitControls();         // Camera interaction
    
    // Rendering state
    this.bodyMeshes = new Map();    // CelestialBody -> Three.js Mesh
    this.orbitLines = new Map();    // CelestialBody -> Orbit path
    this.labels = new Map();        // CelestialBody -> HTML label
  }
}
```

#### Render Loop Integration
- **Physics-Driven Rendering**: Mesh positions updated from physics state
- **Smooth Interpolation**: Visual smoothing between physics steps
- **Level of Detail**: Adaptive rendering quality based on camera distance
- **Performance Optimization**: Frustum culling and object pooling

### User Interaction Architecture

#### Event-Driven Interaction
```javascript
// Interaction pattern
class SolarSystemSimulation {
  initEventListeners() {
    this.renderer.domElement.addEventListener('click', this.onMouseClick.bind(this));
    this.renderer.domElement.addEventListener('mousedown', this.onMouseDown.bind(this));
    // ... additional mouse and keyboard handlers
  }
  
  onMouseClick(event) {
    // 1. Convert screen coordinates to 3D ray
    // 2. Raycast against celestial body meshes
    // 3. Select intersected body
    // 4. Update UI to show body information
  }
}
```

#### Interaction Modes
- **Selection Mode**: Click to select and view body information
- **Drag Mode**: Click and drag to reposition celestial bodies
- **Ride-Along Mode**: Camera follows selected body through space
- **Focus Mode**: Automatic camera positioning on selected objects

## File Organization

### Project Structure
```
solar-system-test/
├── index.html              # Main HTML entry point
├── style.css              # UI styling and layout
├── main.js                # App class - main application controller
├── simulation.js          # SolarSystemSimulation - 3D rendering
├── physics.js             # PhysicsEngine - gravitational calculations
├── celestial-bodies.js    # CelestialBody class and solar system data
├── README.md             # User documentation
└── .claude/              # Development and steering files
    ├── steering/          # Technical guidance documents
    ├── workflows/         # Development workflows
    └── agents/           # AI agent configurations
```

### File Naming Conventions
- **Classes**: kebab-case files containing PascalCase classes
- **Main Entry**: `index.html` and `main.js` for application entry
- **Domain Separation**: Each major domain (physics, rendering, data) in separate file
- **Self-Documenting**: File names clearly indicate contents and purpose

## Performance Optimization

### Rendering Performance
- **60 FPS Target**: Maintain smooth animation even with full solar system
- **Geometry Reuse**: Share sphere geometries across similar objects
- **Texture Management**: Efficient loading and caching of planetary textures
- **Frustum Culling**: Don't render objects outside camera view
- **Level of Detail**: Reduce geometry complexity for distant objects

### Physics Performance
- **Efficient Force Calculations**: O(n²) gravitational calculations optimized
- **Spatial Partitioning**: Consider quadtree/octree for many-body systems
- **Numerical Stability**: Verlet integration prevents energy drift
- **Adaptive Time Steps**: Smaller steps during close encounters

### Memory Management
- **Object Pooling**: Reuse objects to minimize garbage collection
- **Orbit Path Limits**: Circular buffers prevent unbounded memory growth
- **Texture Optimization**: Appropriate resolution for performance/quality balance
- **Event Listener Cleanup**: Proper cleanup to prevent memory leaks

## Educational Design Principles

### Code Transparency
- **Readable Physics**: Clear implementation of gravitational equations
- **Minimal Abstraction**: Avoid over-engineering that obscures concepts
- **Educational Comments**: Explain physics principles in code comments
- **Parameter Exposure**: Make physical constants easily findable and modifiable

### Extensibility Patterns
- **Data-Driven Bodies**: Easy to add new planets, moons, or asteroids
- **Modular Physics**: Separate physics allows for different force models
- **Plugin Architecture**: New visualization modes can be easily added
- **Configuration Options**: Expose simulation parameters for experimentation

## Browser Compatibility

### Modern Web Standards
- **ES6 Modules**: Use import/export for clean module boundaries
- **WebGL Support**: Required for Three.js rendering
- **High Performance**: Utilize modern browser optimizations
- **Progressive Enhancement**: Graceful degradation for older browsers

### Feature Detection
```javascript
// Capability checking
if (!window.WebGLRenderingContext) {
    showError('WebGL is required for this simulation');
    return;
}

if (typeof window.OrbitControls === 'undefined') {
    console.warn('OrbitControls not found, using basic camera controls');
    this.setupBasicControls();
}
```

### Cross-Platform Considerations
- **Touch Support**: Consider mobile/tablet interaction patterns
- **Performance Scaling**: Adaptive quality based on device capabilities
- **Screen Sizes**: Responsive layout for different display sizes
- **Input Methods**: Support both mouse and touch interactions

## Security Considerations

### Client-Side Security
- **Input Validation**: Validate user input for custom celestial bodies
- **XSS Prevention**: Sanitize any user-generated content
- **Resource Limits**: Prevent excessive memory or CPU usage
- **Safe Defaults**: Reasonable limits on simulation parameters

### Content Security
- **CDN Dependencies**: Use reputable CDNs for external libraries
- **Subresource Integrity**: Verify integrity of external resources
- **HTTPS Delivery**: Serve over secure connections
- **No Sensitive Data**: Pure educational content with no personal data

## Testing and Quality Assurance

### Physics Validation
- **Energy Conservation**: Monitor total system energy over time
- **Orbital Stability**: Verify planets maintain stable orbits
- **Collision Detection**: Test interaction when objects get very close
- **Time Reversibility**: Ensure rewind functionality produces consistent results

### Rendering Quality
- **Visual Regression Testing**: Screenshots of known good states
- **Performance Benchmarking**: Frame rate monitoring across devices
- **Cross-Browser Testing**: Verify compatibility across target browsers
- **User Interaction Testing**: Verify all mouse/keyboard interactions

### Code Quality
- **Static Analysis**: ESLint for catching common errors
- **Code Review**: Manual review for physics accuracy and educational value
- **Documentation**: Ensure all complex physics calculations are well-commented
- **Educational Review**: Verify code serves educational objectives

This architecture provides a solid foundation for an educational physics simulation that is both technically sound and pedagogically effective, with clear separation of concerns and room for future enhancement.