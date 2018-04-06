# awesome-DL-remotes-sensing

Open-sources of  Deep Learning remote sensing

Data

2016 IEEE Data fusion context 
Mou and Zhu, Spatiotemporal Scene Interpretation of Space Videos via Deep Neural Network And Tracklet Analysis, 2016 IEEE GRSS Data Fusion Contest. https://www.sipeo.bgu.tum.de/downloads/gt4dfc16video.rar
J-SparseFI 
Zhu et al., Exploiting Joint Sparsity for Pan-sharpening – the J-SparseFI Algorithm. IEEE Transactions on Geoscience and Remote Sensing 54(5), 2664-2681, 2016. https://www.sipeo.bgu.tum.de/downloads/J_SparseFI_Data.zip
SARptical 
Wang et al., “Fusing Meter-Resolution 4-D InSAR Point Clouds and Optical Images for Semantic Urban Infrastructure Monitoring,” IEEE Transactions on Geoscience and Remote Sensing, 55(1), 14–26, 2017. https://www.sipeo.bgu.tum.de/downloads/SARptical_data.zip
Benchmark of streetview image of individual building instance 
Kang et al., Building instance classification using street view images, ISPRS Journal of Photogrammetry and Remote Sensing, in press. 
https://www.sipeo.bgu.tum.de/downloads/BIC_GSV.tar.gz



 
Scene classiﬁcation (one image is classiﬁed into a single label):
 
The UC Merced dataset [177]. This dataset is a collection of aerial images (256×256 pixels
in RGB space) depicting 21 land use classes. Each class comprises 100 images. Since each
image comes with a single label, the dataset can be only used for image classiﬁcation
purposes, i.e., to classify the whole image into a single land use class. The dataset can be
downloaded at http://vision.ucmerced.edu/datasets/landuse.html.

The AID dataset [74]. This dataset is a collection of 10,000 annotated aerial images dis-
tributed in 30 land use scene classes and can be used for image classiﬁcation purpose. In
comparison with the UC Merced dataset, AID contains much more images and covers a
wider range of scene categories. Thus it is in line with the data requirements of modern deep
learning. The dataset can be downloaded at http://www.lmars.whu.edu.cn/xia/AID-project.html.

The NWPU-RESISC45 dataset [178]. This dataset contains 31,500 aerial images spread over
45 scene classes. So far, it is the largest dataset for land use scene classiﬁcation in terms
of both total number of images and number of scene classes. The dataset can be obtained
at http://www.escience.cn/people/JunweiHan/NWPU-RESISC45.html.

 Image classiﬁcation (each pixel of an image is classiﬁed into a label):
 
 The Zurich Summer Dataset [179]. This dataset is a collection of 20 image chips from a
single large QuickBird image acquired over Zurich, Switzerland, in 2002. Each image chip
is pansharpened to 0.6m resolution and 8 land use classes are presented. All images are
released, along with their ground truths. The dataset can be obtained at https://sites.google.
com/site/michelevolpiresearch/data/zurich-dataset.

Zeebruges, or the Data Fusion Contest 2015 dataset [127] In 2015, the Image Analysis
and Data Fusion Technical Committee of the IEEE GRSS organized a data processing
competition aiming at 5-centimeter resolution land mapping. To do so, the organizers
provided both a RGB aerial image and a dense (65 pts/m 2 ) lidar point cloud over the
harbour of Zeebruges (Belgium). The data are organized on seven 100000 × 100000 pixels
tiles. All the tiles have been labeled densely in 8 land classes, including land use (building,
roads) and objects (vehicle, boats) classes [126]. The data can be obtained from the Data
and Algorithm Standard Evaluation Website (DASE) http://dase.ticinumaerospace.com/. On
DASE, users can download the seven tiles and labels for ﬁve tiles. To assess models on the
two remaining tiles, users can upload the classiﬁed maps on the DASE server.

The ISPRS 2D semantic labeling challenge. The working group II/4 of the ISPRS ‘3D
Scene Reconstruction and Analysis’ provided a sub-decimeter resolution dataset over the
two cities of Vaihingen and Potsdam. The data are similar to those of the Zeebruges data
above, with the difference that the height information is provided as a digital surface model
at the same resolution of the image data. Moreover, images are provided with an infrared
channel. The dataset is also fully labeeld into six classes, including land classes (roads,
meadows) and objects (cars). It also comes with a clutter class gathering all unknown
objects. The Vaihingen dataset comes with 33 tiles of average size of 2000 × 3000 pixels.
Half of the tiles come with labels. The other 17 tiles come with no labels and participants
must upload classiﬁcation maps for evaluation. The Potsdam dataset comes with 24 labeled
tiles (6000 × 6000 pixels) and 14 unlabeled ones. Both datasets can be obtained from
http://www2.isprs.org/commissions/comm3/wg4/semantic-labeling.html.

Registration / matching:
The SARptical Dataset [180]. With the growing attention on very high resolution SAR
data, the fusion of optical and SAR images in dense urban area has become an emerging
and timely topic. Lying at the base of such fusion topic is the challenging task of the co-
registration of SAR and optical images. Such two images are acquired with intrinsically
different imaging geometries, and thus are nearly impossible to be co-registered without a
precise 3D model of the imaged scene. SARptical is a unique dataset for SAR and optical
image matching in dense urban areas. It consists of 10,000 pairs of corresponding SAR and
optical image patches in central Berlin, with the center pixels of each patch pair precisely
co-registered. They are generated based on co-registered 3D InSAR point clouds (which
are reconstructed by SAR tomography using tens of TerraSAR-X high resolution spotlight
images), and 3D optical point clouds (which are reconstructed by structure from motion
followed by dense stereo matching using several UltraCam images with a ground spacing
of 20cm). This dataset can be downloaded from https://www.sipeo.bgu.tum.de/downloads.

Showcasing

Deconvolution network in MatConvNet. The ﬁrst example is released by the authors of [92]
and corresponds to the architecture in Fig. 11. It exploits the MatConvNet library for
MATLAB (http://www.vlfeat.org/matconvnet/). It provides a pre-trained network for both
the Vaihingen and Potsdam datasets described above. The initial models are speciﬁc to
remote sensing data and have been trained on each dataset separately. This example is
mostly meant to show how to ﬁne-tune an existing model in MatConvNet by training few
extra iteration to improve the model weights. It can, of course, be trained from scratch by
reinitializing the weights randomly. A function to test the additional images of the datasets
is also provided. Overall, it allows one to reproduce the results in [92] which are similar
to the last column of Fig. 12. By removing the deconvolutional part of the network and
adding a fully connected layer at the bottleneck, one can reproduce the CNN-PC model. If
instead, one adds a spatial upsampling layer (e.g. a spatial interpolation of the bottleneck),
one can also reproduce the results of the CNN-SPL model of Fig. 12. In both cases, the
models must be re-trained (or at least heavily ﬁne tuned).
The code can be downloaded from https://sites.google.com/site/michelevolpiresearch/codes/
dense-labeling.

 Fully convolutional (SegNet) architecture in Caff`e. The second example is released by the
authors of [142] and exploits the Caff`e library (http://caffe.berkeleyvision.org/). The model
exploits the SegNet architecture from Kendall et al. [181]. Authors release the pre-trained
model to reproduce the results of [142] on the Vaihingen dataset. The network conﬁguration,
database generation and training ﬁles are given in Python.
The code can be downloaded from https://github.com/nshaud/DeepNetsForEO.

AConvNet for SAR ATR in Caffe. The third example is released by the authors of [42]. It
implements a CNN-based SAR target recognition and demonstrates via the MSTAR dataset.
It includes the model conﬁguration ﬁle and the source code for training and testing, as well
as a successfully trained CNN model.
The code can be downloaded from https://github.com/fudanxu/MSTAR-AConvNet.


 Residual Conv-Deconv Network in TensorFlow. The last example is released by the authors
of [33, 34] and shows how to build up a residual Conv-Deconv network for unsupervised
spectral-spatial feature learning of hyperspectral data. It exploits TensorFlow (https://www.
tensorﬂow.org/) and Keras (https://keras.io/) libraries. One can transfer the trained network
for their own classiﬁcation purpose by ﬁne-tuning on the target data sets or obtain “free”
object detection using the learned ﬁlters in the ﬁrst residual block of the residual Conv-
Deconv network.The code can be downloaded from https://www.sipeo.bgu.tum.de/downloads.

SnapNet: point cloud semantization using deep segmentation network
https://github.com/aboulch/snapnet
 aerial/satellite semantic segmentation to PyTorch
 https://github.com/nshaud/DeepNetsForEO










