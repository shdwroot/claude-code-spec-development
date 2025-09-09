# Project Structure and Organization

## Directory Architecture

### Root Level Organization
```
solar-system-test/
├── index.html                  # Main HTML entry point
├── style.css                  # UI styling and layout
├── main.js                    # App class - main controller
├── simulation.js              # SolarSystemSimulation - 3D rendering
├── physics.js                 # PhysicsEngine - gravitational calculations
├── celestial-bodies.js        # CelestialBody class and solar system data
├── README.md                  # User documentation and usage guide
└── .claude/                   # Development and AI agent system
    ├── steering/              # Project context and guidelines
    ├── workflows/             # Development workflow definitions
    ├── agents/                # AI agent configurations and prompts
    ├── config/                # Agent behavior and coordination settings
    └── templates/             # Reusable document templates
```

### Core Application Structure
```
Application Layer (index.html)
├── UI Framework (style.css)
├── Application Controller (main.js)
│   ├── Event handling and user interaction
│   ├── UI state management
│   └── Simulation lifecycle management
├── 3D Visualization Layer (simulation.js)
│   ├── Three.js scene management
│   ├── Camera and controls
│   ├── Mesh creation and rendering
│   └── User interaction processing
├── Physics Simulation (physics.js)
│   ├── Gravitational force calculations
│   ├── N-body dynamics
│   ├── Time integration
│   └── State management (save/load/rewind)
└── Data and Models (celestial-bodies.js)
    ├── CelestialBody class definition
    ├── Solar system factory
    ├── Astronomical data (CELESTIAL_DATA)
    └── Custom body creation utilities
```

## File Organization Principles

### Modular Architecture
- **Single Responsibility**: Each file contains one primary class or domain
- **Clear Dependencies**: Explicit imports and well-defined interfaces
- **Domain Separation**: Physics, rendering, data, and UI concerns separated
- **Educational Clarity**: File structure mirrors conceptual architecture

### Class-to-File Mapping
```
main.js              → App class (application controller)
simulation.js        → SolarSystemSimulation class (3D rendering)
physics.js           → PhysicsEngine class (gravitational simulation)
celestial-bodies.js  → CelestialBody class + SolarSystemFactory + data
index.html           → Application entry point and UI structure
style.css           → UI styling and responsive layout
```

### Data Organization

#### Astronomical Data Structure (CELESTIAL_DATA)
```javascript
const CELESTIAL_DATA = {
    sun: {
        // Central star properties
        mass, radius, color, position, velocity, rotationPeriod
    },
    mercury: {
        // Inner planet properties
        mass, radius, color, distance, orbitalVelocity, rotationPeriod
    },
    // ... other planets with moons
    jupiter: {
        // Gas giant properties + moon system
        mass, radius, color, rings: { innerRadius, outerRadius },
        moons: [
            { name: 'Io', mass, radius, distance, orbitalVelocity },
            { name: 'Europa', mass, radius, distance, orbitalVelocity },
            // ... other moons
        ]
    }
}
```

## Code Organization Standards

### Class Definition Patterns

#### CelestialBody Class Structure
```javascript
class CelestialBody {
    constructor(config)     // Initialize from configuration
    update(deltaTime)       // Per-frame updates (rotation, etc.)
    getDistanceFromSun()    // Utility calculations
    getOrbitalPeriod()      // Physics-based calculations
    // Properties: position, velocity, mass, radius, color, etc.
}
```

#### PhysicsEngine Class Structure
```javascript
class PhysicsEngine {
    // Core simulation loop
    step()                              // Main physics timestep
    
    // Force calculations
    calculateGravitationalForce()       // N-body gravitational forces
    updateVelocities()                  // Apply forces to velocities
    updatePositions()                   // Integrate motion
    
    // State management
    saveState() / loadState()           // History for rewind functionality
    
    // Utility methods
    calculateOrbitalVelocity()          // Stable orbit calculations
    getTotalEnergy()                    // Energy conservation monitoring
}
```

#### SolarSystemSimulation Class Structure
```javascript
class SolarSystemSimulation {
    // Initialization
    constructor()                       // Setup Three.js scene
    initRenderer() / initCamera()       // Graphics initialization
    initControls() / initLighting()     // Interaction and lighting
    
    // Scene management
    createSolarSystem()                 // Generate solar system from data
    createMeshes() / updateMeshPositions() // Visual representation
    
    // Interaction
    onMouseClick() / onMouseDrag()      // User interaction handling
    selectBody() / focusOnBody()        // Object selection and focus
    
    // Advanced features
    startRideAlong() / updateRideAlongCamera() // Follow-cam functionality
    toggleOrbits() / toggleLabels()     // Visual options
    
    // Animation loop
    animate()                           // Main render loop
}
```

#### App Class Structure
```javascript
class App {
    constructor() / init()              // Application initialization
    initUIControls()                    // Event listener setup
    
    // UI event handlers
    // - Time controls (play/pause/speed)
    // - View controls (camera/orbits/labels)
    // - Body manipulation (add custom bodies)
    // - Keyboard shortcuts
    
    // Advanced features
    saveSimulationState()               // Persistence utilities
    startPerformanceMonitoring()       // Development tools
}
```

## Naming Conventions

### File and Class Names
- **Files**: `kebab-case.js` (e.g., `celestial-bodies.js`)
- **Classes**: `PascalCase` (e.g., `SolarSystemSimulation`)
- **Methods**: `camelCase` (e.g., `calculateGravitationalForce`)
- **Constants**: `SCREAMING_SNAKE_CASE` (e.g., `CELESTIAL_DATA`)
- **Variables**: `camelCase` with descriptive names

### Physics and Astronomy Naming
- **Physical Properties**: Use standard scientific names
  - `mass` (kg), `radius` (km), `position` (m), `velocity` (m/s)
  - `rotationPeriod` (hours), `orbitalVelocity` (m/s)
- **Celestial Bodies**: Use official astronomical names
  - Planet names: `mercury`, `venus`, `earth`, etc.
  - Moon names: `moon` (Earth's), `io`, `europa`, `ganymede`, etc.
- **Physics Constants**: Standard scientific notation
  - `G` (gravitational constant), `timeStep`, `timeMultiplier`

### UI and Interaction Naming
- **HTML IDs**: `kebab-case` (e.g., `toggle-orbits`, `body-info`)
- **CSS Classes**: `kebab-case` with semantic names
- **Event Handlers**: Descriptive action names (e.g., `onMouseClick`, `onDoubleClick`)
- **UI State**: Clear boolean names (e.g., `isPlaying`, `showOrbits`, `rideAlongMode`)

## Feature Organization

### Modular Feature Implementation

#### Core Features (Must Have)
```
Physics Simulation
├── Gravitational calculations (physics.js)
├── N-body interactions
├── Energy conservation
└── Time manipulation (rewind/fast-forward)

3D Visualization  
├── Three.js scene management (simulation.js)
├── Mesh creation and updates
├── Camera controls and interaction
└── Visual effects (lighting, atmosphere)

User Interaction
├── Click and drag manipulation (simulation.js)
├── Object selection and information display
├── Time controls (main.js)
└── View controls (orbits, labels, scaling)
```

#### Advanced Features (Should Have)
```
Ride-Along Mode
├── Camera following system (simulation.js)
├── Dynamic camera positioning
├── Smooth transitions
└── UI feedback and controls

Custom Body Creation
├── User input validation (main.js)
├── Dynamic body instantiation
├── Orbital velocity calculation
└── Integration with physics engine

Educational Tools
├── Body information panels
├── Performance monitoring
├── Keyboard shortcuts
└── Save/load functionality (partial implementation)
```

### Code Extension Patterns

#### Adding New Celestial Bodies
1. Add data to `CELESTIAL_DATA` in `celestial-bodies.js`
2. Include physical properties (mass, radius, orbital parameters)
3. Specify visual properties (color, texture references)
4. Define moon systems if applicable
5. Factory automatically handles instantiation

#### Adding New Physics Features
1. Extend `PhysicsEngine` class in `physics.js`
2. Add new force calculation methods
3. Integrate with main `step()` loop
4. Update energy conservation calculations
5. Add visualization support in `simulation.js`

#### Adding New Interaction Modes
1. Add event handlers to `SolarSystemSimulation`
2. Implement state management for new mode
3. Add UI controls in `main.js`
4. Update help documentation
5. Add keyboard shortcuts for accessibility

## Development Workflow Organization

### AI Agent Structure (/.claude/)
```
.claude/
├── steering/                   # Project context files
│   ├── product.md             # Educational vision and user needs
│   ├── tech.md               # Technical architecture and standards
│   ├── structure.md          # This file - organization rules
│   └── security.md           # Security considerations
├── workflows/                 # Development process definitions
│   ├── onboarding-complete.yml  # Comprehensive project analysis
│   ├── project-initialization.yml # Initial setup workflow
│   └── spec-generation.yml   # Feature development workflow
├── agents/                    # Specialized AI agent configurations
│   ├── initialization-coordinator/  # Project setup agent
│   ├── codebase-archaeologist/     # Code analysis agent
│   ├── architecture-detective/     # Architecture analysis agent
│   └── [other specialized agents]
├── config/                    # Agent behavior configuration
└── templates/                 # Reusable document templates
```

### Feature Development Structure

#### When Adding New Features
```
1. Analysis Phase
   - Understand existing codebase patterns
   - Identify integration points
   - Assess impact on physics simulation
   - Consider educational value

2. Design Phase  
   - Follow existing architectural patterns
   - Maintain separation of concerns
   - Ensure physics accuracy
   - Plan user interaction design

3. Implementation Phase
   - Extend existing classes where appropriate
   - Maintain code clarity for educational use
   - Add proper error handling
   - Include performance considerations

4. Integration Phase
   - Test with existing solar system
   - Verify physics accuracy
   - Update documentation
   - Add user interface controls
```

## Quality Assurance Structure

### Code Quality Standards
- **Physics Accuracy**: All astronomical data from reliable sources
- **Performance**: Maintain 60 FPS with full solar system
- **Educational Value**: Code should be readable and well-commented
- **Browser Compatibility**: Support modern browsers with WebGL
- **Error Handling**: Graceful degradation and user feedback

### Testing Organization
```
Manual Testing Areas:
├── Physics Validation
│   ├── Energy conservation over time
│   ├── Orbital stability
│   └── Collision detection
├── Rendering Quality
│   ├── Visual accuracy
│   ├── Performance benchmarks
│   └── Cross-browser compatibility
├── User Interaction
│   ├── Mouse/keyboard controls
│   ├── Touch device support
│   └── Accessibility features
└── Educational Effectiveness
    ├── Concept demonstration clarity
    ├── Ease of experimentation
    └── Information presentation quality
```

### Documentation Standards
- **README.md**: User-focused documentation with examples
- **Code Comments**: Explain physics principles and complex calculations
- **Architectural Comments**: Document design decisions and patterns
- **Educational Notes**: Explain educational objectives and use cases

This structure supports both the educational objectives of the simulation and the technical requirements for a maintainable, extensible physics-based web application.