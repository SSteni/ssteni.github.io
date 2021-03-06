<p align="left">

Earlier this month, I began researching the Computer Vision field in AI and came across Prof. Fei Fei Li’s work. Back in 2006, Prof. Li, a newly minted Computer Science Professor, started pondering the idea of building a repository of Image dataset. While most of her colleagues across academia and the AI industry focused on models and algorithms, Prof. Li wanted to expand and improve the data available to train AI algorithms. The best algorithm wouldn’t work well if the data it learned from didn’t reflect the real world. Prof. Li and her team at Princeton went on to build ImageNet starting from the word database — WordNet — and used many of its features. They used Amazon Mechanical Turk to help with the classification of images. I read through the original paper ImageNet: A Large-Scale Hierarchical Image Database, and here is an excerpt. Apart from explaining how ImageNet was developed, the researchers also emphasize how resourceful ImageNet can be for visual recognition applications such as object recognition, image classification and object localization.
ImageNet is a large-scale ontology of images, it is a critical resource for developing advanced, large-scale content-based image search and image understanding algorithms, as well as for providing critical training and benchmarking data for such algorithms. ImageNet is built upon the hierarchical structure of WordNet. Each meaningful concept in WordNet, described by multiple words or phrases is called a “synonym set” or “synset”. There are around 80,000 noun synsets in WordNet. ImageNet provides on average 500–1000 images to illustrate each synset. ImageNet will therefore offer tens of millions of cleanly sorted images.
  
<h5>Scale</h5>
  
At the time of writing, ImageNet consists of 12 subtrees with a total of 3.2 million cleanly annotated images spread over 5247 categories. On average over 600 images are collected for each synset.
  
<h5>Hierarchy</h5>
  
ImageNet organizes different classes of images in a densely populated semantic hierarchy. Synsets of images in ImageNet are linked by several types of relations, the “IS-A” relation being the most comprehensive and useful.
  
<h5>Accuracy</h5>
  
An average of 99.7% precision is achieved for each synset. Achieving a high precision for all depths of the ImageNet tree is challenging because the lower in the hierarchy a synset is, the harder it is to classify.
  
<h5>Diversity</h5>
  
ImageNet is constructed such that objects in the image should have variable appearances, positions, view points, poses as well as background clutter and occlusions. A synset containing diverse images will result in a blurrier average image, the extreme being a gray image, whereas a synset with little diversity will result in a more structured, sharper average image. Therefore a smaller JPG file size of the average image of a more diverse synset is expected.

<h4>Constructing ImageNet</h4>
  
<h5>Collecting Candidate Images</h5>
  
Candidate images are collected from the Internet by querying several image search engines. For each synset, the queries are the set of WordNet synonyms. Search engines typically limit the number of images retrievable. To obtain as many images as possible, the query set is expanded by appending the queries with the word from parent synsets. For example, when querying “whippet”, according to WordNet’s gloss a “small slender dog of greyhound type developed in England”, they also use “whippet dog” and “whippet greyhound”. To further enlarge and diversify the candidate pool, the queries are translated into other languages including Chinese, Spanish, Dutch and Italian.
  
<h5>Cleaning Candidate Images</h5>
  
Amazon Mechanical Turk has been used for labelling vision data. Users are presented with a set of candidate images and the definition of target synsets. Users are then asked to verify whether each image contains objects of the synsets. To account for accuracy ´, a quality control system is set up. There are 2 issues here. 1) Human users make mistakes and not all users follow the instructions. 2) Users do not always agree with each other, especially for more subtle or confusing synsets, at the deeper levels of the tree. The solution to these issues is to have multiple users independently label the same image. An image is considered positive only if it gets a convincing majority of the votes.

<h4>ImageNet Application</h4>
  
Non-parametric object recognition underlines the advantages of having clean, full-resolution images; tree-based image classification exploits the tree structure of ImageNet, whereas Object Localization outlines a possible extension and gives more insights into the data.
  
<h5>1. Non-parametric Object Recognition</h5>
  
Given an image containing an unknown object, its object class is recognized by querying similar images in ImageNet. Given a large number of images, simple nearest neighbour methods can achieve reasonable performances despite a high level of noise. With a clean set of full-resolution images, object recognition can be more accurate, especially by exploiting more feature level information.
Four different object recognition experiments are run on images from the 16 common categories 7 between Caltech256 and the mammal subtree. The classification performance on each category is measured in the form of ROC curve. For each category, the negative set consists of all images from the other 15 categories.
  
<h5>2. Tree-Based Image Classification</h5>
  
The usefulness of the ImageNet hierarchy is illustrated by a simple object classification method called the “tree-max classifier”. Imagine there is a classifier at each synset node of the tree and we want to decide whether an image contains an object of that synset or not. The idea is to not only consider the classification score at a node such as “dog” but also of its child synsets, such as “German shepherd”, “English terrier”, etc. The maximum of all the classifier responses in this subtree becomes the classification score of the query image.
  
<h5>3. Automatic Object Localization</h5>
  
ImageNet can be extended to provide additional information about each image. One such information is the spatial extent of the objects in each image. For training, a robust object detection algorithm often needs localized objects in different poses and under different viewpoints. Having localized objects in cluttered scenes enables users to use ImageNet as a benchmark dataset for object localization algorithms.

<h5>Future Work</h5>
  
ImageNet is a central resource for a broad range of vision-related research. For the computer vision community in particular, and the possible applications include:
- A training resource
- A benchmark dataset
- Introducing new semantic relations for visual modelling.
- To advance human vision research.
  
</p>
