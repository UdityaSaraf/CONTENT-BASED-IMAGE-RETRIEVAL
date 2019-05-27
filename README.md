Content Based Image Retrieval

In this digital era, image repository is increasing at a tremendous rate. First of all, people have a comparative ease of access to image capturing devices such as smartphones, digital cameras and scanning devices, then what it used to be a few years ago. Not only this, massive amount of data is also generated from medical sciences and satellite imaging every single day. The collection of images available on the internet is also growing at a much faster pace. “According to a study, there are 180 million images on the Web, a total amount of image data of about 3Tb along with 1 million or more digital images are being produced every single day”.Image retrieval performed by matching the feature of a query image with images in the dataset, has become a problem of interest to many people. A lot of research study has been going on in this field to develop systems and tools that shall enable efficient and accurate image browsing and retrieval. For instance, Flipkart had initiated image search on its website but later shut it down in less than a year of its launch because the results that it produced were a lot of times irrelevant and customers did not cater interest in this feature. We therefore, looked into various on going developments in this field and implemented a system that can provide as much best results possible. 

There are two major image retrieval techniques: 

			1)Text based Image Retrieval 

			2)Content Based Image Retrieval 

Text based Image retrieval is retrieval of images based on keywords or annotations that are either added manually to the images or sometimes the text that is associated in the form of subtitle or caption. Keywords are phrases that describe the content in an image. So, all the images in a database have these tags or keywords associated with them that are manually added to describe “what the image contains”. This approach was the most initial methods of retrieval but it has its own disadvantages:

			 I.This method is very time consuming and exhaustive.

			II.Sometimes different words have different meanings, therefore it is context driven. This can result in a large number of inaccurate results.

		       III.Images might have a subjective matter such as feelings or emotions associated which may be different for different audience. 

CBIR overcomes the limitations of Text Based Retrieval whereby the retrieval occurs on the actual “content” of images that is visible. CBIR works with low-level features such as color, shape or texture. 


When building an image search engine we will first have to index our dataset. Indexing a dataset is the process of quantifying our dataset by utilizing an image descriptor to extract features from each image. An image descriptor defines the algorithm that we are utilizing to describe our image.The important takeaway here is that the image descriptor governs how the image is quantified. Features, on the other hand, are the output of an image descriptor. When you put an image into an image descriptor, you will get features out the other end. In the most basic terms, features (or feature vectors) are just a list of numbers used to abstractly represent and quantify images.Feature vectors can then be compared for similarity by using a distance metric or similarity function. Distance metrics and similarity functions take two feature vectors as inputs and then output a number that represents how “similar” the two feature vectors are. Given two feature vectors, a distance function is used to determine how similar the two feature vectors are. The output of the distance function is a single floating point value used to represent the similarity between the two images.

The 4 Steps of Any CBIR System

	1)Defining your image descriptor: At this phase you need to decide what aspect of the image you want to describe. Are you interested in the color of the image? The shape of an object in the image? Or do you want to characterize texture?

	2)Indexing your dataset: Now that you have your image descriptor defined, your job is to apply this image descriptor to each image in your dataset, extract features from these images, and write the features to storage (ex. CSV file, RDBMS, Redis, etc.) so that they can be later compared for similarity.

	3)Defining your similarity metric: Cool, now you have a bunch of feature vectors. But how are you going to compare them? Popular choices include the Euclidean distance, Cosine distance, and chi-squared distance, but the actual choice is highly dependent on (1) your dataset and (2) the types of features you extracted.

	4)Searching: The final step is to perform an actual search. A user will submit a query image to the system and your job will be to (1) extract features from this query image and then (2) apply your similarity function to compare the query features to the features already indexed. From there, you simply return the most relevant results according to your similarity function.

These are the most basic 4 steps of any CBIR system. As they become more complex and utilize different feature representations, the number of steps grow and a substantial number of sub-steps are added to each step mentioned above. For the time being, let’s keep things simple and utilize just these 4 steps.

	1.Indexing the dataset and subsequently creating the index.csv file -python index.py --dataset dataset --index index.csv

	2.Searching through the metadata of the dataset with the metadata of the query image-python search.py --index index.csv --query queries/108100.png --result-path dataset
