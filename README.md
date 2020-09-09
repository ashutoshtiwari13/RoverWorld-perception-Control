## Rover World Perception Control Project
Uses essential elements of Robotics, perception, decision making and Actuation to drive a rover Autonomously.

<p align="center">
  <img src="https://github.com/ashutoshtiwari13/RoverWorld-perception-Control/blob/master/SimulationOutput/simulate2.gif" width="750px" height="400px"/></p>

### Project Details

- [Project Setup](#Project-Setup)
- [Run Simulation](#Run-Simulation)

## Project Setup
### The Simulator
Download the simulator build that's appropriate for your operating system.  Here are the links for [Linux](https://s3-us-west-1.amazonaws.com/udacity-robotics/Rover+Unity+Sims/Linux_Roversim.zip), [Mac](	https://s3-us-west-1.amazonaws.com/udacity-robotics/Rover+Unity+Sims/Mac_Roversim.zip), or [Windows](https://s3-us-west-1.amazonaws.com/udacity-robotics/Rover+Unity+Sims/Windows_Roversim.zip).  
One can test out the simulator by opening it up and choosing "Training Mode."

### Data Analysis
Included in the IPython notebook called `Rover_simulator.ipynb` are the methods needed to perform autonomous navigation and mapping.
To see what's in the notebook and execute the code there, start the jupyter notebook server at the command line like this in the `code` directory.

```sh
jupyter notebook
```
Run the cells in the notebook from top to bottom to see the various data analysis steps.
The last two cells in the notebook are for running the analysis on a folder of test images to create a map of the simulator environment and write the output to a video.

### Navigating Autonomously
- The lib folder contains the `perception.py`, `decision.py` and `utils.py`.

     * `perception.py` contains the method `perception_step` which contains all the analyzing tests done from the Jupyter notebook under the `process_image` method.
     *  `decision.py` has conditional statements that demonstrate how the rover makes decisions about adjusting throttle, brake and steering inputs.
     *	`utils.py` contain three main methods:
             * `create_output_images` method is where the `Rover.worldmap` is compared with the ground map and gets converted, along with `Rover.vision_image`, into base64 strings to send back to the rover.
             * `RoverState` class is used to keep track of telemetry values and results from the analyzing test from the Jupyter notebook.
             * `telemetry`  method runs every time the simulator sends a new batch of data. It updates the Rover() object with new telemetry values.
- The file called `run_rover.py` is used to navigate the environment in autonomous mode.
```sh
python drive_rover.py
```  
- Then launch the simulator and choose "Autonomous Mode." The rover should drive itself now!

## Run Simulation
The simulator ran on a resolution of 800x600 with the graphics set to fantastic.
From these settings, the rover was able to map most of the map with fidelity from 60% to 70% and find the location of rocks from his navigation path.
<p align="center">
  <img src="https://github.com/ashutoshtiwari13/RoverWorld-perception-Control/blob/master/SimulationOutput/simulate1.gif" width="750px" height="400px"/></p>
