# ComfyUI-LTX2_ICLoRA-ImageEdit-I2V
An Image-to-Video (I2V) workflow adapted from LTX-2_ICLoRA_Distilled, integrated with Qwen image editing, featuring toggle switches for control options.


![WorkflowPreview](workflows/I2V+EditImage/LTX-2_ICLoRA+QwenImageEdit.png)

## About the Files
This contains three ComfyUI workflows. You can run them separately or use the combined workflow:

### I2V + EditImage ###
A combined workflow based on LTX-2_ICLoRA_Distilled workflow and QwenImageEdit2509. It includes toggle switches to enable or disable steps, or to switch controls within the same workflow:

Step 1. Automatically extracts the first frame from an input video (or uses a provided image). Edits the frame using a reference style/image and prompt.
Step 2. Uses the edited image as input for the LTX-2 section. In the main Subgraph node, select the control type using SelectControl (values 1–3), make sure to select the corresponding LoRA:
 - 1 – Depth
 - 2 – Canny
 - 3 – Pose
