# GPS Orbital Mechanics Visualization

This Python program simulates and visualizes GPS (Global Positioning System) satellite orbits using the two-body equation of motion and Keplerian orbital elements. The visualization allows users to explore how each orbital parameter affects the shape and orientation of satellite orbits.

## Overview

The program provides an interactive console interface to:
- Modify the six Keplerian orbital parameters
- Visualize a single GPS satellite orbit in 3D
- Animate a satellite's movement along its orbit
- View the complete GPS constellation with multiple orbital planes

## Google Colab Setup

This code is designed to run in Google Colab using the notebook `unperturbed_satellite_orbit_simulation.ipynb`.

1. **Open the Notebook**:
   - Access Google Colab (https://colab.research.google.com/)
   - Open the `unperturbed_satellite_orbit_simulation.ipynb` file
   - You can upload it from your computer or access it from Google Drive

2. **Run the Required Packages**:
   - No manual installation is required as NumPy and Matplotlib are pre-installed in Colab
   - If needed, you can install additional packages using:
   ```python
   !pip install package_name
   ```

3. **Run the Notebook**:
   - Either run all cells using the Runtime menu: **Runtime > Run all**
   - Or run cells individually by pressing the play button next to each cell

4. **Important Notes for Colab**:
   - Interactive visualizations work best with `%matplotlib inline` or `%matplotlib widget`
   - For animations to display properly in Colab, add this before visualization code:
   ```python
   from google.colab import output
   output.enable_custom_widget_manager()
   ```
   - 3D visualizations may require you to manually rotate the view using the mouse

## Features

### Interactive Parameter Control

The program allows you to adjust the six Keplerian orbital elements that define a satellite's orbit:

1. **Semi-major axis (a)**: Controls the size of the orbit (default: 26,560 km for GPS)
2. **Eccentricity (e)**: Determines how circular or elliptical the orbit is (default: 0.01, nearly circular for GPS)
3. **Inclination (i)**: The angle between the orbital plane and Earth's equatorial plane (default: 55° for GPS)
4. **Right Ascension of the Ascending Node (RAAN/Ω)**: Defines where the orbit crosses the equatorial plane going northward
5. **Argument of Perigee (ω)**: The angle within the orbital plane from the ascending node to the point of closest approach
6. **Mean Anomaly (M)**: Defines the satellite's position along the orbital path

### Visualization Options

- **Single Satellite View**: Displays one GPS satellite orbit with the current parameter settings
- **Animation**: Shows the satellite moving along its orbit over time
- **Full Constellation View**: Visualizes all GPS satellites (24 satellites in 6 orbital planes)

### Visual Elements

The visualization includes:
- Earth represented as a blue sphere
- The orbital path highlighted in red
- The satellite's current position
- Perigee (closest point to Earth) and apogee (farthest point) markers
- The orbital plane shown as a transparent surface
- Earth's equatorial plane
- Coordinate axes for reference

## Usage

1. Run the notebook cells
2. The console will display the current GPS orbital parameters
3. Select options 1-6 to modify individual parameters
4. Choose option 7 to visualize a single satellite orbit with current parameters
5. Select option 8 to see an animated visualization
6. Pick option 9 to view the complete GPS constellation
7. Use option 10 to exit the program

## Understanding Orbital Parameters

- **Semi-major axis (a)**: Increasing this value makes the orbit larger
- **Eccentricity (e)**: 
  - e=0: perfectly circular orbit
  - 0<e<1: elliptical orbit (larger values create more elongated ellipses)
  - e=1: parabolic escape trajectory
  - e>1: hyperbolic escape trajectory
- **Inclination (i)**:
  - i=0°: equatorial orbit
  - 0°<i<90°: prograde orbit (satellite moves eastward)
  - i=90°: polar orbit
  - 90°<i<180°: retrograde orbit (satellite moves westward)
- **RAAN (Ω)**: Rotates the orbital plane around Earth's axis
- **Argument of Perigee (ω)**: Rotates the orbit within its plane
- **Mean Anomaly (M)**: Changes the satellite's position along the orbit

## Example Scenarios

Try these parameter combinations to see different orbit types:

1. **GPS Orbit (Default)**
   - a = 26,560 km
   - e = 0.01
   - i = 55°

2. **Geostationary Orbit**
   - a = 42,164 km
   - e = 0
   - i = 0°

3. **Polar Orbit**
   - a = 7,000 km
   - e = 0.01
   - i = 90°

4. **Highly Elliptical Orbit**
   - a = 26,560 km
   - e = 0.7
   - i = 63°

## Notes

- The program uses simplified two-body physics and does not account for perturbations
- Earth's dimensions and gravitational parameters are used for calculations
- The animation speed is not to scale with actual orbital periods
- If you encounter display issues in Colab, try restarting the runtime or checking browser compatibility
