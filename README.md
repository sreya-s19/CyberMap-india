# Cybermap India

https://cyber-map-india.netlify.app/

*(A screenshot of the Cybermap India project showing the timeline for West Bengal)*

## 📖 About The Project

Cybermap India is an interactive 3D data visualization tool designed to make complex cybercrime data accessible and engaging. The application presents users with a dynamic, rotating 3D model of the Earth, which they can explore freely. As a user zooms in, the globe transitions from a world map to a detailed map of India, revealing clickable state-level boundaries. Clicking on a state opens a historical timeline of significant cybercrime incidents for that region.

This project's goal is to provide geographical and historical context to digital threats by transforming raw data into an intuitive and informative visual experience.

## ✨ Key Features

*   **Interactive 3D Globe:** A fully interactive and rotatable 3D Earth rendered with Three.js.
*   **Zoom-based Level of Detail:** Country borders appear on zoom, followed by more detailed Indian state borders as the user gets closer.
*   **Cinematic Camera Animation:** A smooth "Focus on India" animation powered by Tween.js.
*   **Data-Driven Timeline:** A dynamic UI overlay displays a chronological history of cybercrime incidents for the selected state.
*   **Hover & Click Interaction:** States highlight on mouse hover, and the entire state area is clickable, thanks to raycasting on invisible meshes.
*   **Responsive Design:** The UI is designed to be functional and aesthetically pleasing on various screen sizes.

## 🛠️ Technology Stack

*   **3D Rendering:** [**Three.js**](https://threejs.org/)
*   **Camera Animation:** [**Tween.js**](https://github.com/tweenjs/tween.js/)
*   **User Interaction:** [**OrbitControls**](https://threejs.org/docs/#examples/en/controls/OrbitControls)
*   **Front-End:** HTML5, CSS3, Vanilla JavaScript (ES6 Modules)
*   **Geospatial Data:** [**GeoJSON**](https://geojson.org/)
*   **Deployment:** [**Surge.sh**](https://surge.sh/)

## ⚙️ How It Works

The application is built around a core Three.js scene containing a textured sphere.

1.  **Geographical Layers:** GeoJSON files for world countries and Indian states are fetched asynchronously. The coordinate data is parsed and converted from latitude/longitude to 3D vectors on the sphere's surface. These vectors are used to create `Line` objects for visible borders.
2.  **Interaction:** To make entire states clickable (not just the thin lines), an invisible `Mesh` is created for each state. A `Raycaster` listens for mouse movements and clicks, checking for intersections with these invisible meshes.
3.  **User Experience:**
    *   On hover, the `Raycaster` identifies the state, and its corresponding visible outline is swapped with a "hover" material (changing its color).
    *   On click, the identified state's name is used to retrieve data from a local JavaScript object acting as a mock database.
    *   This data is then used to dynamically generate the HTML for the timeline overlay, which is then made visible.
    *   The "Focus on India" button uses Tween.js to smoothly animate the camera's position and target coordinates over a 2-second duration.

## 🚀 Getting Started

To run this project locally, you will need a modern web browser and a local web server to handle the module imports correctly. The easiest way is using the **Live Server** extension for Visual Studio Code.

### Prerequisites

*   A code editor (e.g., [VS Code](https://code.visualstudio.com/))
*   The [Live Server](https://marketplace.visualstudio.com/items?itemName=ritwickdey.LiveServer) extension for VS Code.

### Installation

1.  **Download the project files.**
    (Or clone the repository if you have Git installed: `git clone <repository-url>`)

2.  **Open the project folder** in Visual Studio Code.

3.  **Go Live!**
    Click the "Go Live" button in the bottom-right corner of the VS Code window, or right-click the `index.html` file and select "Open with Live Server".

    

4.  A new browser tab will open with the project running.

## 🔮 Future Enhancements

*   **Real-time Database:** Connect the application to a cloud database like Firebase Firestore to fetch and manage cybercrime data dynamically.
*   **Advanced Visualization:** Add more visual cues on the globe itself, such as glowing points or arcs to represent cyber attack origins and targets.
*   **Data Filtering:** Implement UI controls to filter the timeline by year or type of crime.
*   **Performance Optimization:** Use techniques like geometry simplification for less detailed zoom levels to improve performance.

## 🙏 Acknowledgments

*   **Earth Textures:** [NASA Visible Earth](https://visibleearth.nasa.gov/)
*   **GeoJSON Data:** [World Countries](https://github.com/johan/world.geo.json), [India States](https://github.com/geohacker/india)
*   **Inspiration:** The desire to make data more tangible and understandable through 3D visualization.
