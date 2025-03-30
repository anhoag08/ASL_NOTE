#Paper #LabTesting 

Script Model:
$[Action]$ \[Widget] \[Location]

# Approach
- Screen Recording resample to 5 frames/second
- Normalize to fixed sequence length by up/down sampling
- 3 Main inputs:
	- Calculate similarity map between 2 frames
	- Cropped according to different zone
	- Original frame
	- All inputs resized to 224x224
- Use 3D CNN as based model


