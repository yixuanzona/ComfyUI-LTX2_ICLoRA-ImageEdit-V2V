# ComfyUI-LTX2_ICLoRA-ImageEdit-V2V
An Video-to-Video (V2V) workflow based on LTX-2_ICLoRA_Distilled pipeline, integrated with Qwen image editing, featuring toggle switches for control options.


![WorkflowPreview](workflows/I2V+EditImage/LTX-2_ICLoRA+QwenImageEdit.png)

## 📝About the Files
This contains three ComfyUI workflows. You can run them separately or use the combined workflow:

### I2V + EditImage 
(This workflow is for anyone who wants everything in one place.)

A combined workflow based on LTX-2_ICLoRA_Distilled pipeline and QwenImageEdit2509. It includes toggle switches to enable or disable steps, or to switch controls within the same workflow:

**Step 1.** Automatically extracts the first frame from an input video (or uses a provided image). Edits the frame using a reference style/image and prompt.

**Step 2.** Uses the edited image as input for the LTX-2 section. In the main Subgraph node, select the control type using SelectControl (values 1–3), make sure to select the corresponding LoRA:
 - 1 – Depth (Depth Anything V2)
 - 2 – Canny
 - 3 – Pose (ViTPose)

**Important** Qwen and LTX-2 need to run separately, otherwise you'll hit a memory error. Make sure to turn off the LTX-2 switch before running Qwen.

 ![WorkflowPreview](result/result_depth.gif)

### I2V 
A standalone Image-to-Video workflow using LTX-2_ICLoRA_Distilled. The settings are the same as the I2V part in the combined workflow, without the image editing steps.

 ![WorkflowPreview](result/depth.PNG)
 
### EditImage 
A standalone workflow for image editing and upscaling. It uses the QwenImageEdit2509(GGUF) pipeline together with SeedVR2 upscaling.
(You can also swap in other model versions as needed.)

![WorkflowPreview](result/edit.png)


## Requirements
### Custom Nodes
Install the following nodes (It is best to use ComfyUI Manager):
* [ComfyUI-LTXVideo](https://github.com/Lightricks/ComfyUI-LTXVideo)

* [ComfyUI-KJNodes](https://github.com/kijai/ComfyUI-KJNodes)

* [ComfyUI-Impact-Pack](https://github.com/ltdrdata/ComfyUI-Impact-Pack)

* [ComfyUI-SeedVR2_VideoUpscaler](https://github.com/numz/ComfyUI-SeedVR2_VideoUpscaler)

* [ComfyUI-VideoHelperSuite](https://github.com/Kosinkadink/ComfyUI-VideoHelperSuite)

### Models
* [LTX-2_ICLoRA_Distilled](https://github.com/Lightricks/ComfyUI-LTXVideo)
* [Qwen-Image-Edit-2509-GGUF](https://huggingface.co/QuantStack/Qwen-Image-Edit-2509-GGUF)
* [Qwen-Image-Lightning](https://huggingface.co/lightx2v/Qwen-Image-Lightning/tree/main/Qwen-Image-Edit-2509)


## Important Note:
If you load the workflow without ComfyUI-LTXVideo installed, some items on the Subgraph (such as SelectControl) may disappear. Once the nodes are installed, simply drag the workflow into ComfyUI again and it will display correctly.
