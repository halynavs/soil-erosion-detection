# soil-erosion-detection

As a person who never faced with geo data for modeling, first I've made a research about  working with .jp2 files and masks on python.

Two packages used for data loading, representation and masking:
  - rasterio

    Rasterio reads raster data into numpy arrays so plotting a single band as two dimensional data can be accomplished directly with pyplot
  - geopandas

    GeoPandas is an open source project to make working with geospatial data in python easier. GeoPandas extends the datatypes used by pandas to allow spatial operations on geometric types. Geometric operations are performed by shapely. Geopandas further depends on fiona for file access and matplotlib for plotting.

### Research about model for soil erosion detection

- In article 'Facing Erosion Identification in Railway Lines Using Pixel-Wise Deep-Based Approaches'(Keiller Nogueira, Gabriel L. S. Machado, Pedro H. T. Gama, Caio C. V. da Silva, Remis Balaniuk, and Jefersson A. dos Santos) was  propose a novel deep learning-based framework capable of performing erosion identification in railway lines. Six techniques were evaluated, including:

  1. Pixelwise a segmentation algorithm that classifies each pixel independently using context
windows
  2. Fully Convolutional Network (FCN) one of the first fully convolution architectures proposed for pixel labeling
  3. Deconvolution network, an encoder–decoder fully convolutional architecture proposed for semantic segmentation
  4. DeepLabV3+, a multi-scale semantic segmentation approach that combines atrous spatial pyramid pooling with an encoder–decoder architecture based on depthwise separable convolutions
  5. Dynamic Dilated ConvNet (DDCN) a pixel labeling approach based on dilated convolutions that exploits multi-scale information by allowing the training with dynamic patch sizes
  6. Mask R-CNN, an instance segmentation technique which proposes regions and then annotates each pixel of such proposals by using a fully convolutional network.

  This approaches can be tasted for givven task
  
    [source-codes for the framework and for the ArcGIS tool are publicly available](https://github.com/Gabriellm2003/Deep-Learning-ArcGIS-Plugin)


- Geospatial Deep Learning with ArcGIS
the arcgis.learn module (in ArcGIS API for Python) can be used for solving problem, but better to use in conjunction with ArcGIS, which will cost money. But it can be also usefull for analysis approaches.

     [tutorial](https://www.youtube.com/watch?v=adrqRm4q5Ic&ab_channel=EsriEvents)
     
- Article 'The Use of Deep Machine Learning for the Automated Selection of Remote Sensing Data for the Determination of Areas of Arable Land Degradation Processes Distribution' (Dmitry I. Rukhovich, Polina V. Koroleva, Danila D. Rukhovich and Natalia V. Kalinina)
    CNN used for filtering of satellite images in predetermined boundary conditions in conjunction with calculation NDVI(Normalized Difference Vegetation Index). Fits for binary masks.
    
- Article 'Evaluation of Different Machine Learning Models for Predicting Soil Erosion in Tropical Sloping Lands of Northeast Vietnam'(Tuan Vu Dinh, Nhat-Duc Hoang and Xuan-Linh Tran)
    Were tested ML algorithms: fuzzy k-nearest neighbor (FKNN) support vector machine (SVM), least squares support vector machine (LSSVM), relevance vector machine (RVM) and DL - artificial neural network (ANN) - by description multilaer net wth softmax axtivation function.
    [link](https://www.hindawi.com/journals/aess/2021/6665485/)
    
    
- Article 'Artificial neural networks of soil erosion and runoff prediction at the plot scale'(P Licznar, Mark A. Nearing)

    **insight - Soil loss was somewhat better predicted when values were processed using a natural logarithm transformation prior to network development.** 
    
    [sourse](https://www.researchgate.net/publication/222403468_Artificial_neural_networks_of_soil_erosion_and_runoff_prediction_at_the_plot_scale)
    
- Article 'The use of Kohonen neural networks for runoff–erosion modeling'(Camilo Allyson Simões de Farias, C. Santos)

    **insight - Kohonen Neural Networks are used**
    
    [sourse](https://www.semanticscholar.org/paper/The-use-of-Kohonen-neural-networks-for-modeling-Farias-Santos/234fae4ec92ef8bfef8e6c66b81830b6b2238d71)
    
- Article 'Machine learning based soil erosion susceptibility prediction using social spider algorithm optimized multivariate adaptive regression spline'

  **insight - advanced data-driven method which relies on the Multivariate Adaptive Regression Splines (MARS) machine learning and Social Spider Algorithm (SSA) metaheuristic for predicting soil erosion susceptibility**
  
  [sourse](https://www.semanticscholar.org/paper/Machine-learning-based-soil-erosion-susceptibility-Vu-Tran/145583426be065fe9e859d7cea8030c54adade1d)

# After small research became obvious that Mask R-CNN spreedly used. But there are a lot off specific approaches to take into account.
For building and testing first model is needed one more week. (by circumstances had 2 days on this task)
