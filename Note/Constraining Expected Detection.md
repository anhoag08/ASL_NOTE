#ML #ComVis 

# 1. Possible Approaches
- Dynamic Thresholding:
	- Create rules to increment thresholds by fixed steps when detections exceed upper bounds
	- Decrease thresholds when detection counts fall below minimum requirements
	- Store threshold adjustment history to identify patterns and optimize adjustment rates
	- Note: Cant use expected label
- Loss Function:
	- Develop a count-based regularization term to add to the existing loss calculation
	- Construct penalties that scale with the difference between predicted and target detection counts
	- Note: Most pre-trained models restrict loss function modifications due to architecture constraints
- Non Maximum Suppression:
	- Change the removal of objects based on overlapping bounding boxes.
	- Note: Most pre-trained models restrict supression function modifications due to architecture constraints

# 2. Cursor Tracking
- Pixel matching: Use template picture of cursor and calculate similarity between each region in frame to find best match
- Object Detection Model: Train model on cursor label to detect cursor

# 3. Action Detection
- Click: Cursor move then stop, change cursor shape to click shape, screen changes
- Input Text: Cursor move to text box then stop, change shape to input cursor, text appear

# 2. Reading Researchs
## [Smart Count System Based on Object Detection Using Deep Learning](file:///C:/Users/Lenovo/Desktop/remotesensing-14-03761-v2.pdf):
- Summary: Counter using CNN and Intersection over Union (IOU) to identify and remove duplicates
- Note:

## [DAVE – A Detect-and-Verify Paradigm for Low-Shot Counting](https://openaccess.thecvf.com/content/CVPR2024/papers/Pelhan_DAVE_-_A_Detect-and-Verify_Paradigm_for_Low-Shot_Counting_CVPR_2024_paper.pdf)
- Summary:
- Note:

## [Counting using deep learning regression gives value to ecological surveys](https://www.nature.com/articles/s41598-021-02387-9.pdf)
- Summary:
- Note:


# 3. Possible Aproach
- Step 1: Use LLM with input the keyframe to predict how many web elements are there and label (Text box, button, etc)
- Step 2: Use YOLO11 to extract possible Web Elements and their bounding box
- Use LLM to pair up the labeled web elements from Step 1 and the bounding box in Step 2.
- Pros: 
	- Use context from Web UI (LLM predict based on image)
- Cons:
	- If YOLO11 cant detect important elements then LLM cant pair it up.


- If keyframe happened at time T, extract information at T - x frames.
- Tái sử dụng data format YOLO 11