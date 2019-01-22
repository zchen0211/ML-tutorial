# Autonomous Driving

## Waymo
- Mayank Bansal, Alex Krizhevsky, Abhijit Ogale. ChauffeurNet: Learning to Drive by Imitating the Best and Synthesizing the Worst. 2018
	- Inputs: roadmap, traffic lights, speed limit, route, current agent box, dynamic boxes, past agent poses, future agent poses
	- **Imitation Learning**
	- Loss design:
		- Agent position, heading and box prediction;
		- Meta prediction: speed, subpixel
		- Collision Loss: overlap of the predicted agent box with all scene objects
		- On road loss
		- Geometry loss
