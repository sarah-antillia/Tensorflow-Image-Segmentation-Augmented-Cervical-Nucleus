<h2>Tensorflow-Image-Segmentation-Augmented-Cervical-Nucleus (2024/08/30)</h2>

This is the first experiment of Image Segmentation for CNSeg (Cervical Nucleus Segmentation)
 based on
the <a href="https://github.com/sarah-antillia/Tensorflow-Image-Segmentation-API">Tensorflow-Image-Segmentation-API</a>, and
<a href="https://drive.google.com/file/d/1Bv0MuqoBEJnWNxUz4gaAAYgNEIocsE9Q/view?usp=sharing">
Cervical-Nucleus-ImageMask-Dataset.zip</a>, which was derived by us from 
<a href="https://www.kaggle.com/datasets/zhaojing0522/cervical-nucleus-segmentation">
Cervical Nucleus Segmentation
</a>
<br>
<br>
Please see also 
<a href="https://github.com/sarah-antillia/ImageMask-Dataset-Cervical-Nucleus">
ImageMask-Dataset-Cervical-Nucleus</a><br>

<br>
<b>
Experiment Strategies
</b><br>

<b>1. Data Augmentation:</b><br>
 To address the limited size of the ImageMask-Dataset-Cervical-Nucleus dataset, 
 we employed <a href="./src/ImageMaskAugmentor.py">an online augmentation tool</a> to enhance segmentation accuracy.<br>
 
<b>2. Color Space Conversion:</b><br>
We converted augmented training and test images from RGB to HSV color space. 
This transformation aids in identifying blue cell nuclei regions, which appear green in HSV, 
potentially improving segmentation performance. 
<br>
<br>
<table>
<tr>
<th>RGB</th>
<th>HSV</th>
<th>Mask</th>
</tr>
<tr>
<td><img src="./projects/TensorflowSlightlyFlexibleUNet/Cervical-Nucleus/mini_test/images/10286.jpg" width="320" height="auto"></td>
<td><img src="./projects/TensorflowSlightlyFlexibleUNet/Cervical-Nucleus/hsvimage/10286.jpg" width="320" height="auto"></td>
<td><img src="./projects/TensorflowSlightlyFlexibleUNet/Cervical-Nucleus/mini_test/masks/10286.jpg" width="320" height="auto"></td>

</tr>

</table>
<br>

<hr>
<b>Actual Image Segmentation for Images of 512x512 pixels</b><br>
As shown below, the tiled inferred masks look similar to the ground truth masks. <br>

<table>
<tr>
<th>Input: image</th>
<th>Mask (ground_truth)</th>
<th>Prediction: inferred_mask</th>
</tr>
<tr>
<td><img src="./projects/TensorflowSlightlyFlexibleUNet/Cervical-Nucleus/mini_test/images/10282.jpg" width="320" height="auto"></td>
<td><img src="./projects/TensorflowSlightlyFlexibleUNet/Cervical-Nucleus/mini_test/masks/10282.jpg" width="320" height="auto"></td>
<td><img src="./projects/TensorflowSlightlyFlexibleUNet/Cervical-Nucleus/mini_test_output/10282.jpg" width="320" height="auto"></td>
</tr>

<tr>
<td><img src="./projects/TensorflowSlightlyFlexibleUNet/Cervical-Nucleus/mini_test/images/10294.jpg" width="320" height="auto"></td>
<td><img src="./projects/TensorflowSlightlyFlexibleUNet/Cervical-Nucleus/mini_test/masks/10294.jpg" width="320" height="auto"></td>
<td><img src="./projects/TensorflowSlightlyFlexibleUNet/Cervical-Nucleus/mini_test_output/10294.jpg" width="320" height="auto"></td>
</tr>

<tr>
<td><img src="./projects/TensorflowSlightlyFlexibleUNet/Cervical-Nucleus/mini_test/images/10312.jpg" width="320" height="auto"></td>
<td><img src="./projects/TensorflowSlightlyFlexibleUNet/Cervical-Nucleus/mini_test/masks/10312.jpg" width="320" height="auto"></td>
<td><img src="./projects/TensorflowSlightlyFlexibleUNet/Cervical-Nucleus/mini_test_output/10312.jpg" width="320" height="auto"></td>
</tr>

</table>

<hr>
<br>
In this experiment, we used the simple UNet Model 
<a href="./src/TensorflowUNet.py">TensorflowSlightlyFlexibleUNet</a> for this BCNB Segmentation Model.<br>
As shown in <a href="https://github.com/sarah-antillia/Tensorflow-Image-Segmentation-API">Tensorflow-Image-Segmentation-API</a>.
you may try other Tensorflow UNet Models:<br>

<li><a href="./src/TensorflowSwinUNet.py">TensorflowSwinUNet.py</a></li>
<li><a href="./src/TensorflowMultiResUNet.py">TensorflowMultiResUNet.py</a></li>
<li><a href="./src/TensorflowAttentionUNet.py">TensorflowAttentionUNet.py</a></li>
<li><a href="./src/TensorflowEfficientUNet.py">TensorflowEfficientUNet.py</a></li>
<li><a href="./src/TensorflowUNet3Plus.py">TensorflowUNet3Plus.py</a></li>
<li><a href="./src/TensorflowDeepLabV3Plus.py">TensorflowDeepLabV3Plus.py</a></li>

<br>

<h3>1. Dataset Citation</h3>
<a href="https://dl.acm.org/doi/abs/10.1016/j.cmpb.2023.107732">
<b>CNSeg: : A dataset for cervical nuclear segmentation</b>
</a>
<br>

<b>Authors:</b><br>
 Jing Zhao, Yong-jun He, Shu-Hang Zhou, Jian Qin, Yi-ning Xie<br>
<br>
@article{ZHAO2023107732, title = {CNSeg: A dataset for cervical nuclear segmentation}, <br>
journal = {Computer Methods and Programs in Biomedicine}, volume = {241}, pages = {107732}, year = {2023}, issn = {0169-2607}, <br>
doi = {https://doi.org/10.1016/j.cmpb.2023.107732}, <br>
url = {https://www.sciencedirect.com/science/article/pii/S016926072300398X}, 
author = {Jing Zhao and Yong-jun He and Shu-Hang Zhou and Jian Qin and Yi-ning Xie} }<br>

<br>
Please see also:<a href="https://github.com/jingzhaohlj/AL-Net">https://github.com/jingzhaohlj/AL-Net</a><br>

You can download CNSeg dataset from the kaggle website:<br>
<a href="https://www.kaggle.com/datasets/zhaojing0522/cervical-nucleus-segmentation">
</a>
<br>
<b>License</b>: Unknown <br>
<br>

<h3>
<a id="2">
2 Cervical-Nucleus ImageMask Dataset
</a>
</h3>
 If you would like to train this Cervical-NucleusSegmentation model by yourself,
 please download the dataset from the google drive 
<a href="https://drive.google.com/file/d/1Bv0MuqoBEJnWNxUz4gaAAYgNEIocsE9Q/view?usp=sharing">
Cervical-Nucleus-ImageMask-Dataset.zip</a>
<br>
<br>
, expand the downloaded ImageMaskDataset and put it under <b>./dataset</b> folder to be
<pre>
./dataset
└─Cervical-Nucleus
    ├─test
    │   ├─images
    │   └─masks
    ├─train
    │   ├─images
    │   └─masks
    └─valid
        ├─images
        └─masks
</pre>

<b>Cervical-Nucleus Dataset Statistics</b><br>
<img src ="./projects/TensorflowSlightlyFlexibleUNet/Cervical-Nucleus/Cervical-Nucleus-ImageMask-Dataset_Statistics.png" width="512" height="auto"><br>
<br>
As shown above, the number of images of train and valid datasets is large enough to use for a training set for our segmentation model, 
but we used an online augmentation tool <a href="./src/ImageMaskAugmentor.py">ImageMaskAugmentor.py</a> 
to improve generalization performance.
<br>

<br>
<b>Train_images_sample</b><br>
<img src="./projects/TensorflowSlightlyFlexibleUNet/Cervical-Nucleus/asset/train_images_sample.png" width="1024" height="auto">
<br>
<b>Train_masks_sample</b><br>
<img src="./projects/TensorflowSlightlyFlexibleUNet/Cervical-Nucleus/asset/train_masks_sample.png" width="1024" height="auto">
<br>

<h3>
3 Train TensorflowUNet Model
</h3>
 We have trained Cervical-NucleusTensorflowUNet Model by using the following
<a href="./projects/TensorflowSlightlyFlexibleUNet/Cervical-Nucleus/train_eval_infer.config"> <b>train_eval_infer.config</b></a> file. <br>
Please move to ./projects/TensorflowSlightlyFlexibleUNet/Cervical-Nucleus and run the following bat file.<br>
<pre>
>1.train.bat
</pre>
, which simply runs the following command.<br>
<pre>
>python ../../../src/TensorflowUNetTrainer.py ./train_eval_infer.config
</pre>
<hr>
<pre>
; train_eval_infer.config
; 2024/08/30 (C) antillia.com

[model]
model          = "TensorflowUNet"
generator      = True
image_width    = 512
image_height   = 512
image_channels = 3
input_normalize = False
normalization  = False
num_classes    = 1
base_filters   = 16
base_kernels   = (9,9)
num_layers     = 8
dropout_rate   = 0.05
learning_rate  = 0.0001
clipvalue      = 0.5
dilation       = (1,1)
;loss           = "bce_iou_loss"
loss           = "bce_dice_loss"
metrics        = ["dice_coef"]
show_summary   = False

[dataset]
datasetclass  = "ImageMaskDataset"
;Please specify a resize interpolation algorithm in case of ImageMaskDatast.
resize_interpolation = "cv2.INTER_CUBIC"


[train]
epochs        = 100
batch_size    = 2
steps_per_epoch  = 320
validation_steps = 80
patience      = 10

;metrics       = ["iou_coef", "val_iou_coef"]
metrics       = ["dice_coef", "val_dice_coef"]

model_dir     = "./models"
eval_dir      = "./eval"
image_datapath = "../../../dataset/Cervical-Nucleus/train/images/"
mask_datapath  = "../../../dataset/Cervical-Nucleus/train/masks/"

epoch_change_infer     = True
epoch_change_infer_dir = "./epoch_change_infer"
epoch_changeinfer     = False
epoch_changeinfer_dir = "./epoch_changeinfer"
num_infer_images       = 1

create_backup  = False

learning_rate_reducer = True
reducer_factor     = 0.4
reducer_patience   = 4
save_weights_only  = True

[eval]
image_datapath = "../../../dataset/Cervical-Nucleus/valid/images/"
mask_datapath  = "../../../dataset/Cervical-Nucleus/valid/masks/"

[test] 
image_datapath = "../../../dataset/Cervical-Nucleus/test/images/"
mask_datapath  = "../../../dataset/Cervical-Nucleus/test/masks/"

[infer] 
images_dir    = "./mini_test/images"
output_dir    = "./mini_test_output"

[segmentation]
colorize      = True
black         = "black"
white         = "green"
blursize      = None

[image]
;color_converter = None
color_converter = "cv2.COLOR_BGR2HSV_FULL"
gamma           = 0
sharpening      = 0

[mask]
blur      = False
blur_size = (3,3)
binarize  = False
;threshold = 128
threshold = 80

[generator]
debug        = False
augmentation = True

[augmentor]
vflip    = True
hflip    = True
rotation = True
angles   = [30, 60, 90, 120, 150, 180, 210, 240, 270, 300, 330]
shrinks  = [0.8,]
shears   = [0.1]

deformation = True
distortion  = True
sharpening  = False
brightening = False
barrdistortion = True

[deformation]
alpah     = 1300
sigmoids  = [8.0,]

[distortion]
gaussian_filter_rsigma= 40
gaussian_filter_sigma = 0.5
distortions           = [0.02, ]

[barrdistortion]
radius = 0.3
amount = 0.3
centers =  [(0.3, 0.3), (0.7, 0.3), (0.5, 0.5), (0.3, 0.7), (0.7, 0.7)]

[sharpening]
k        = 1.0

[brightening]
alpha  = 1.2
beta   = 10  
</pre>
<hr>
<b>Model parameters</b><br>
Defined a small <b>base_filters</b> and large <b>base_kernels</b> for the first Conv Layer of Encoder Block of 
<a href="./src/TensorflowUNet.py">TensorflowUNet.py</a> 
and a large num_layers (including a bridge between Encoder and Decoder Blocks).
<pre>
[model]
base_filters   = 16
base_kernels   = (9,9)
num_layers     = 8
</pre>

<b>Learning rate</b><br>
Defined a small learning rate.  
<pre>
[model]
learning_rate  = 0.0001
</pre>

<b>Online augmentation</b><br>
Enabled our online augmentation.  
<pre>
[model]
model         = "TensorflowUNet"
generator     = True
</pre>

<b>Loss and metrics functions</b><br>
Specified "bce_dice_loss" and "dice_coef".<br>
<pre>
[model]
loss           = "bce_dice_loss"
metrics        = ["dice_coef"]
</pre>
<b>Learning rate reducer callback</b><br>
Enabled learing_rate_reducer callback, and a small reducer_patience.
<pre> 
[train]
learning_rate_reducer = True
reducer_factor     = 0.4
reducer_patience   = 4
</pre>

<b>Enabled color space conversion</b><br>
<pre>
[image]
color_converter = "cv2.COLOR_BGR2HSV_FULL"
</pre>
<b>Early stopping callback</b><br>
Enabled early stopping callback with patience parameter.
<pre>
[train]
patience      = 10
</pre>

<b>Epoch change inference callbacks</b><br>
Enabled epoch_change_infer and epoch_changeinfer callbacks.<br>
<pre>
[train]
epoch_change_infer       = True
epoch_change_infer_dir   =  "./epoch_change_infer"
epoch_changeinfer        = False
epoch_changeinfer_dir    = "./epoch_changeinfer"
num_infer_images         = 1
</pre>

By using these callbacks, on every epoch_change, the inference procedures can be called
 for an image in <b>mini_test</b> folder. These will help you confirm how the predicted mask changes 
 at each epoch during your training process.<br> <br> 

<b>Epoch_change_inference output</b><br>
<img src="./projects/TensorflowSlightlyFlexibleUNet/Cervical-Nucleus/asset/epoch_change_infer.png" width="1024" height="auto"><br>
<br>
<br>

In this experiment, the training process was stopped at epoch 31 by EarlyStopping Callback.<br><br>
<img src="./projects/TensorflowSlightlyFlexibleUNet/Cervical-Nucleus/asset/train_console_output_at_epoch_31.png" width="720" height="auto"><br>
<br>

<br>
<a href="./projects/TensorflowSlightlyFlexibleUNet/Cervical-Nucleus/eval/train_metrics.csv">train_metrics.csv</a><br>
<img src="./projects/TensorflowSlightlyFlexibleUNet/Cervical-Nucleus/eval/train_metrics.png" width="520" height="auto"><br>

<br>
<a href="./projects/TensorflowSlightlyFlexibleUNet/Cervical-Nucleus/eval/train_losses.csv">train_losses.csv</a><br>
<img src="./projects/TensorflowSlightlyFlexibleUNet/Cervical-Nucleus/eval/train_losses.png" width="520" height="auto"><br>

<br>

<h3>
4 Evaluation
</h3>
Please move to a <b>./projects/TensorflowSlightlyFlexibleUNet/Cervical-Nucleus</b> folder,<br>
and run the following bat file to evaluate TensorflowUNet model for Cervical-Nucleus.<br>
<pre>
./2.evaluate.bat
</pre>
This bat file simply runs the following command.
<pre>
python ../../../src/TensorflowUNetEvaluator.py ./train_eval_infer_aug.config
</pre>

Evaluation console output:<br>
<img src="./projects/TensorflowSlightlyFlexibleUNet/Cervical-Nucleus/asset/evaluate_console_output_at_epoch_31.png" width="720" height="auto">
<br><br>

<a href="./projects/TensorflowSlightlyFlexibleUNet/Cervical-Nucleus/evaluation.csv">evaluation.csv</a><br>

The loss (bce_dice_loss) to this Cervical-Nucleus/test was not so low, and dice_coef not so high as shown below.
<br>
<pre>
loss,0.1585
dice_coef,0.7467
</pre>


<h3>
5 Inference
</h3>
Please move to a <b>./projects/TensorflowSlightlyFlexibleUNet/Cervical-Nucleus</b> folder<br>
,and run the following bat file to infer segmentation regions for images by the Trained-TensorflowUNet model for Cervical-Nucleus.<br>
<pre>
./3.infer.bat
</pre>
This simply runs the following command.
<pre>
python ../../../src/TensorflowUNetInferencer.py ./train_eval_infer_aug.config
</pre>
<hr>
<b>mini_test_images</b><br>
<img src="./projects/TensorflowSlightlyFlexibleUNet/Cervical-Nucleus/asset/mini_test_images.png" width="1024" height="auto"><br>
<b>mini_test_mask(ground_truth)</b><br>
<img src="./projects/TensorflowSlightlyFlexibleUNet/Cervical-Nucleus/asset/mini_test_masks.png" width="1024" height="auto"><br>

<hr>
<b>Inferred test masks</b><br>
<img src="./projects/TensorflowSlightlyFlexibleUNet/Cervical-Nucleus/asset/mini_test_output.png" width="1024" height="auto"><br>
<br>
<hr>
<b>Enlarged images and masks </b><br>

<table>
<tr>
<th>Image</th>
<th>Mask (ground_truth)</th>
<th>Inferred-mask</th>
</tr>

<tr>
<td><img src="./projects/TensorflowSlightlyFlexibleUNet/Cervical-Nucleus/mini_test/images/10286.jpg" width="320" height="auto"></td>
<td><img src="./projects/TensorflowSlightlyFlexibleUNet/Cervical-Nucleus/mini_test/masks/10286.jpg" width="320" height="auto"></td>
<td><img src="./projects/TensorflowSlightlyFlexibleUNet/Cervical-Nucleus/mini_test_output/10286.jpg" width="320" height="auto"></td>
</tr>

<tr>
<td><img src="./projects/TensorflowSlightlyFlexibleUNet/Cervical-Nucleus/mini_test/images/10293.jpg" width="320" height="auto"></td>
<td><img src="./projects/TensorflowSlightlyFlexibleUNet/Cervical-Nucleus/mini_test/masks/10293.jpg" width="320" height="auto"></td>
<td><img src="./projects/TensorflowSlightlyFlexibleUNet/Cervical-Nucleus/mini_test_output/10293.jpg" width="320" height="auto"></td>
</tr>

<tr>
<td><img src="./projects/TensorflowSlightlyFlexibleUNet/Cervical-Nucleus/mini_test/images/10300.jpg" width="320" height="auto"></td>
<td><img src="./projects/TensorflowSlightlyFlexibleUNet/Cervical-Nucleus/mini_test/masks/10300.jpg" width="320" height="auto"></td>
<td><img src="./projects/TensorflowSlightlyFlexibleUNet/Cervical-Nucleus/mini_test_output/10300.jpg" width="320" height="auto"></td>
</tr>
<tr>
<td><img src="./projects/TensorflowSlightlyFlexibleUNet/Cervical-Nucleus/mini_test/images/10312.jpg" width="320" height="auto"></td>
<td><img src="./projects/TensorflowSlightlyFlexibleUNet/Cervical-Nucleus/mini_test/masks/10312.jpg" width="320" height="auto"></td>
<td><img src="./projects/TensorflowSlightlyFlexibleUNet/Cervical-Nucleus/mini_test_output/10312.jpg" width="320" height="auto"></td>
</tr>
<tr>
<td><img src="./projects/TensorflowSlightlyFlexibleUNet/Cervical-Nucleus/mini_test/images/10322.jpg" width="320" height="auto"></td>
<td><img src="./projects/TensorflowSlightlyFlexibleUNet/Cervical-Nucleus/mini_test/masks/10322.jpg" width="320" height="auto"></td>
<td><img src="./projects/TensorflowSlightlyFlexibleUNet/Cervical-Nucleus/mini_test_output/10322.jpg" width="320" height="auto"></td>
</tr>

</table>
<hr>
<br>
<h3>
References
</h3>
<b>1. CNSeg: : A dataset for cervical nuclear segmentation</b><br>

<a href="https://dl.acm.org/doi/abs/10.1016/j.cmpb.2023.107732">
https://dl.acm.org/doi/abs/10.1016/j.cmpb.2023.107732
</a>
<br>
@article{ZHAO2023107732, title = {CNSeg: A dataset for cervical nuclear segmentation}, <br>
journal = {Computer Methods and Programs in Biomedicine}, volume = {241}, pages = {107732}, year = {2023}, issn = {0169-2607}, <br>
doi = {https://doi.org/10.1016/j.cmpb.2023.107732}, <br>
url = {https://www.sciencedirect.com/science/article/pii/S016926072300398X}, 
author = {Jing Zhao and Yong-jun He and Shu-Hang Zhou and Jian Qin and Yi-ning Xie} }
<br>
<br>
<b>2. ImageMask-Dataset-Cervical-Nucleus</b><br>
Toshiyuki Arai @antillia.com<br>
<a href="https://github.com/sarah-antillia/ImageMask-Dataset-Cervical-Nucleus">
https://github.com/sarah-antillia/ImageMask-Dataset-Cervical-Nucleus</a>

<br><br>
<b>3. Tensorflow-Tiled-Image-Segmentation-Augmented-Cervical-Cancer </b><br>
Toshiyuki Arai @antillia.com<br>
<a href="https://github.com/sarah-antillia/Tensorflow-Tiled-Image-Segmentation-Augmented-Cervical-Cancer">
https://github.com/sarah-antillia/Tensorflow-Tiled-Image-Segmentation-Augmented-Cervical-Cancer
</a>

<br><br>
<b>4. Tensorflow-Image-Segmentation-Augmented-White-Blood-Cell</b><br>
Toshiyuki Arai @antillia.com<br>
<a href="https://github.com/sarah-antillia/Tensorflow-Image-Segmentation-Augmented-White-Blood-Cell">
https://github.com/sarah-antillia/Tensorflow-Image-Segmentation-Augmented-White-Blood-Cell
</a>.


