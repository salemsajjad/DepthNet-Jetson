# DepthNet-Jetson
Here are my sample codes to implement a pre-trained DepthNet model on NVIDIA Jetson Nano.

# Implement DepthNet on Jetson Nano using this tutorial:

https://github.com/NobuoTsukamoto/tensorrt-examples/tree/main/python/depth_estimation

1. First of all, the GitHub repo the GitHub repo should be downloaded.
2. After that the model's data files should be stored via download.sh that exists in its particular directory.
3. The model should be converted to trt wit/without fp16 flag using this command:
	this command needs to Python files: common.py and convertonnxgs2trt.py in the same directory.
	$ python3 convert_onnxgs2trt.py \
	--model <working_directory>/depthNet/PINTO_model_zoo/149_depth_estimation/saved_model_180x320/depth_estimation_mbnv2_180x320.onnx \
	--output <working_directory>/tensorrt-examples/models/depth_estimation_mbnv2_180x320_fp16.trt \
	--fp16
4. After converting to trt, it needed to be inferenced on Jetson Nano.
	this section needs common.py as well as a script between trt_depth_estimation_capture.py 
	and trt_depth_estimation_image.py
	I have written a script named run_infet.py that can run the trt_depth_estimation_image.py
5. All the files are stored in this directory.

U can see the results for an FP16 model running on NVIDIA Jetson Nano:

640x360_FP16:

![640x360_FP16](https://github.com/salemsajjad/DepthNet-Jetson/assets/31271355/beb24167-c585-4608-aa23-d6016ccc2ec2)



180x320_FP16:

![180x320_FP16](https://github.com/salemsajjad/DepthNet-Jetson/assets/31271355/436efaf3-f84a-41f5-96ca-57ab0213e4af)




