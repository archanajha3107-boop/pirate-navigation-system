⚓ The Pirate Navigation System

A web-based maritime navigation system designed to calculate safe and optimal courses between islands while avoiding dangerous maritime zones such as naval blockades, storms, shallow reefs, and restricted waters.

## 🌊 Overview

The Pirate Navigation System combines a cinematic maritime interface with a functional route-planning system.

Users can select a departure island, destination island, and vessel speed. The system calculates an optimal maritime route using a graph-based Dijkstra algorithm and displays the calculated course on an interactive map.

When an active hazard affects the selected route, the system automatically detects the conflict, blocks the affected route, and recalculates an alternative course.

> **PIRATE = Visual Identity | MARITIME NAVIGATION = Product**

## 🚀 Key Features

- Departure and destination island selection
- Maritime route calculation
- Dijkstra shortest-path algorithm
- Interactive Leaflet map
- OpenStreetMap basemap
- Nautical distance calculation
- Travel time estimation using vessel speed in knots
- Hazard zone management
- Royal Naval Blockade detection
- Automatic route conflict detection
- Dynamic route recalculation
- Alternative safe route generation
- Simulated vessel awareness
- Crew operations module
- Cinematic pirate-themed interface
- Animated ocean, ship, fog, clouds and particles
- Responsive interface

## 🗺️ How Route Calculation Works

The island network is represented as a weighted graph:

- **Islands = Nodes**
- **Sea routes = Edges**
- **Route distance = Edge Weight**

When the user selects a departure and destination:

1. The system creates the available route graph.
2. Dijkstra's algorithm searches for the shortest available path.
3. The total route distance is calculated in nautical miles.
4. Travel time is estimated using the selected vessel speed.
5. The route is displayed on the interactive map.

### Dynamic Rerouting

If a hazard affects an active route:

1. The system detects the affected route edge.
2. The affected edge is temporarily blocked.
3. The graph is rebuilt without the blocked route.
4. Dijkstra's algorithm runs again.
5. An alternative route is generated.
6. The new route is displayed on the map.

## ⛵ Distance & ETA

Travel time is calculated using:

```text
Time = Distance / Speed
````

Where:

* Distance is measured in nautical miles (NM)
* Speed is measured in knots
* 1 knot = 1 nautical mile per hour

## ⚠️ Hazard System

The system includes simulated hazards such as:

* Royal Naval Blockade
* Devil's Triangle Storm
* Razor Reef Shallows
* Cursed Waters
* Pirate Hunter Patrol
* Sea Monster Territory

Hazards can be activated or deactivated from the hazard control panel.

## 🚢 Vessel Awareness

The system displays simulated vessels including pirate, navy, merchant, cargo and rescue vessels.

> **SIMULATION MODE — NOT REAL AIS DATA**

The vessel positions and movement are generated locally for demonstration purposes.

## 👥 Crew Operations

A secondary crew operations module provides simulated information about:

* Navigation
* Engineering
* Deck
* Galley
* Safety
* Crew members
* Assigned tasks
* Task status

This module is an additional feature and is not the primary navigation functionality.

## 🛠️ Technology Stack

### Frontend

* HTML5
* CSS3
* JavaScript (ES6+)

### Mapping

* Leaflet.js
* OpenStreetMap

### Algorithms

* Dijkstra's shortest-path algorithm
* Graph data structures

### Visual & Animation

* CSS animations
* HTML5 Canvas API
* SVG
* JavaScript requestAnimationFrame
* Google Fonts

## 📁 Project Structure

```text
pirate-navigation-system/
│
├── index.html
│
├── css/
│   └── styles.css
│
├── js/
│   ├── app.js
│   ├── data.js
│   ├── routing.js
│   └── animations.js
│
└── README.md
```

## 🧩 Architecture

```text
Simulated Data
      ↓
Graph Construction
      ↓
Dijkstra Algorithm
      ↓
Hazard Detection
      ↓
Route Conflict
      ↓
Block Affected Route
      ↓
Recalculate Route
      ↓
Leaflet Map
      ↓
Visual Route Display
```

## 💡 Why This Project?

Maritime navigation can involve changing environmental and operational conditions. A route that is optimal under normal conditions may become unsafe when a hazard or naval blockade appears.

This project demonstrates how a navigation system can respond dynamically to such changes by recalculating the available route.

## ⚠️ Project Scope & Limitations

This is a hackathon prototype using simulated maritime data.

* Island and route data are predefined.
* Route distances are simulated values.
* Hazards are predefined and linked to specific route edges.
* Vessel positions are simulated.
* The system does not use real AIS data.
* No backend or database is currently required.
* The system is not intended for real-world maritime navigation.

## 🔮 Future Improvements

Possible future enhancements include:

* Real-time AIS vessel data
* Live weather and storm data
* Real maritime charts
* Backend and database integration
* User authentication
* Persistent voyage history
* More advanced route optimization
* Fuel-aware route planning
* Weather-aware routing
* Real-time collaborative navigation

## 🏴‍☠️ Hackathon

Developed as a hackathon prototype for:

**PS #02 — The Pirate Navigation System**

> Chart optimal maritime courses between archipelago islands while dodging dangerous royal naval blockades, razor reefs, and cursed waters.

---

## 👩‍💻 Team

Developed as a collaborative student hackathon project.

---

## 📜 License

This project is created for educational and hackathon purposes.

````

### `.gitignore`

Since your project is plain frontend, you don't need a huge `.gitignore`. Create a file named:

```text
.gitignore
````

and put:

```gitignore
# Dependencies
node_modules/

# Environment variables
.env
.env.local
.env.*.local

# Build / cache
dist/
build/
.next/
.cache/

# Editor files
.vscode/
.idea/

# OS files
.DS_Store
Thumbs.db

# Logs
*.log

# Temporary files
*.tmp
*.temp
```

Even though you **currently don't have a backend or API key**, keeping `.env` ignored is a good habit if you later add something like Groq.

### ⚠️ One important thing before you push

Because your project uses **OpenStreetMap tiles**, keep the proper attribution in your Leaflet map — which your current code already has. And don't put any future API keys directly inside `app.js`; use environment/server-side handling if you later add an API.

For your current project, the clean GitHub identity is:
**Stack:** `HTML5 · CSS3 · JavaScript · Leaflet.js · OpenStreetMap · Dijkstra Algorithm`
