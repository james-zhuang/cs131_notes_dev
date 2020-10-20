---
title: Segmentation
keywords: (insert comma-separated keywords here)
order: 9 # Lecture number for 2020
---

<!-----
NEW: Check the "Suppress top comment" option to remove this info from the output.

Conversion time: 5.586 seconds.


Using this Markdown file:

1. Paste this output into your source file.
2. See the notes and action items below regarding this conversion run.
3. Check the rendered output (headings, lists, code blocks, tables) for proper
   formatting and use a linkchecker before you publish this page.

Conversion notes:

* Docs to Markdown version 1.0β29
* Mon Oct 19 2020 22:50:28 GMT-0700 (PDT)
* Source doc: CS131 Oct 13 Lecture Notes

WARNING:
You have some equations: look for ">>>>>  gd2md-html alert:  equation..." in output.


ERROR:
undefined internal link to this URL: "#heading=h.uukt8vjex0pc".link text: here to see graphs in computer vision
?Did you generate a TOC?


ERROR:
undefined internal link to this URL: "#heading=h.re5gi23ydn10".link text: Diff -> difference between clusterings
?Did you generate a TOC?


ERROR:
undefined internal link to this URL: "#heading=h.gp7eu2t3oo7z".link text: In -> internal difference between clusterings
?Did you generate a TOC?

* This document has images: check for >>>>>  gd2md-html alert:  inline image link in generated source and store images to your server. NOTE: Images in exported zip file from Google Docs may not appear in  the same order as they do in your doc. Please check the images!


WARNING:
You have 9 H1 headings. You may want to use the "H1 -> H2" option to demote all headings by one level.

----->


<p style="color: red; font-weight: bold">>>>>>  gd2md-html alert:  ERRORs: 3; WARNINGs: 2; ALERTS: 36.</p>
<ul style="color: red; font-weight: bold"><li>See top comment block for details on ERRORs and WARNINGs. <li>In the converted Markdown or HTML, search for inline alerts that start with >>>>>  gd2md-html alert:  for specific instances that need correction.</ul>

<p style="color: red; font-weight: bold">Links to alert messages:</p><a href="#gdcalert1">alert1</a>
<a href="#gdcalert2">alert2</a>
<a href="#gdcalert3">alert3</a>
<a href="#gdcalert4">alert4</a>
<a href="#gdcalert5">alert5</a>
<a href="#gdcalert6">alert6</a>
<a href="#gdcalert7">alert7</a>
<a href="#gdcalert8">alert8</a>
<a href="#gdcalert9">alert9</a>
<a href="#gdcalert10">alert10</a>
<a href="#gdcalert11">alert11</a>
<a href="#gdcalert12">alert12</a>
<a href="#gdcalert13">alert13</a>
<a href="#gdcalert14">alert14</a>
<a href="#gdcalert15">alert15</a>
<a href="#gdcalert16">alert16</a>
<a href="#gdcalert17">alert17</a>
<a href="#gdcalert18">alert18</a>
<a href="#gdcalert19">alert19</a>
<a href="#gdcalert20">alert20</a>
<a href="#gdcalert21">alert21</a>
<a href="#gdcalert22">alert22</a>
<a href="#gdcalert23">alert23</a>
<a href="#gdcalert24">alert24</a>
<a href="#gdcalert25">alert25</a>
<a href="#gdcalert26">alert26</a>
<a href="#gdcalert27">alert27</a>
<a href="#gdcalert28">alert28</a>
<a href="#gdcalert29">alert29</a>
<a href="#gdcalert30">alert30</a>
<a href="#gdcalert31">alert31</a>
<a href="#gdcalert32">alert32</a>
<a href="#gdcalert33">alert33</a>
<a href="#gdcalert34">alert34</a>
<a href="#gdcalert35">alert35</a>
<a href="#gdcalert36">alert36</a>

<p style="color: red; font-weight: bold">>>>>> PLEASE check and correct alert issues and delete this message and the inline alerts.<hr></p>



# Segmentation

Image segmentation has a number of key goals: identify groups of pixels / image regions that go together, separate images into coherent “objects” or regions, group together similar-looking pixels for efficiency in future processing and others. An example of image segmentation that identifies groups of pixels that go together is shown below: 



<p id="gdcalert1" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: inline image link here (to images/image1.png). Store image on your image server and adjust path/filename/extension if necessary. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert2">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


![alt_text](images/image1.png "image_tooltip")


Tiger segmentation example from lecture 9.1

The table of contents



*   Gestalt Theory of Perceptual Grouping
*   Agglomerative Clustering-based Segmentation
*   Graph-based Segmentation


# Gestalt Theory of Perceptual Grouping

***The Gestalt School: *** Grouping elements and understanding relationships between elements are key parts of our visual perception. For vision, we could say that “The whole is greater than the sum of parts.” Consider how elements in the figure below take on much more meaning when considered altogether. 



<p id="gdcalert2" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: inline image link here (to images/image2.png). Store image on your image server and adjust path/filename/extension if necessary. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert3">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


![alt_text](images/image2.png "image_tooltip")


From this example, we see that grouping together the elements on the right holds far more meaning than looking at each component individually like on the left. This example specifically represents the Law of Closure in Gestalt theory, which will be discussed shortly.


# ### Gestalt Factors

The Gestalt school of thought broke down the ways in which we group elements into several principles.

***Proximity:*** Things that are close together appear to be more related than things that are farther apart. 



<p id="gdcalert3" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: inline image link here (to images/image3.png). Store image on your image server and adjust path/filename/extension if necessary. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert4">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


![alt_text](images/image3.png "image_tooltip")


***Similarity:*** When things appear similar to each other, we group them together and tend to think they have the same function.



<p id="gdcalert4" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: inline image link here (to images/image4.png). Store image on your image server and adjust path/filename/extension if necessary. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert5">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


![alt_text](images/image4.png "image_tooltip")


Similar colors are automatically grouped together by our visual perception.

***Common Fate:***  Humans tend to perceive elements moving in the same direction as being more related than elements that are stationary or that move in different directions.



<p id="gdcalert5" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: inline image link here (to images/image5.png). Store image on your image server and adjust path/filename/extension if necessary. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert6">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


![alt_text](images/image5.png "image_tooltip")


***Common Region:*** When objects lie within the same closed region, they are grouped together. 



<p id="gdcalert6" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: inline image link here (to images/image6.png). Store image on your image server and adjust path/filename/extension if necessary. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert7">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


![alt_text](images/image6.png "image_tooltip")


***Continuity:*** Elements arranged on a line or curve are perceived to be more related than elements not on the line or curve, despite any occlusions.



<p id="gdcalert7" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: inline image link here (to images/image7.png). Store image on your image server and adjust path/filename/extension if necessary. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert8">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


![alt_text](images/image7.png "image_tooltip")


***Closure:***  We tend to look for a single recognizable pattern when looking at a complex arrangement of visual elements.



<p id="gdcalert8" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: inline image link here (to images/image8.png). Store image on your image server and adjust path/filename/extension if necessary. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert9">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


![alt_text](images/image8.png "image_tooltip")


***Symmetry:*** Elements that are symmetrical to each other tend to be perceived as a unified group.



<p id="gdcalert9" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: inline image link here (to images/image9.png). Store image on your image server and adjust path/filename/extension if necessary. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert10">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


![alt_text](images/image9.png "image_tooltip")


Despite the importance of Gestalt factors, they are unfortunately very difficult to translate to algorithms. 



<p id="gdcalert10" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: inline image link here (to images/image10.png). Store image on your image server and adjust path/filename/extension if necessary. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert11">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


![alt_text](images/image10.png "image_tooltip")


Here, we see that the grouping of different shapes has a huge role on how our brain perceives the image. In image D, the image looks like a snake, rather than just a random group of squiggly lines, and in image C, our brain tells us that there is a 3-dimensional sphere with connected spikes, even though neither of these images contain only one color (black) or any depth.

For grouping in Gestalt Theory, we can use several different factors. These include, proximity, similarity, common fate, common region, parallelism, symmetry, continuity, and closure. Some factors are harder to determine than others, such as parallelism. As mentioned in lecture, it’s difficult for the computer to determine elements in parallel in the image. 


# Agglomerative Clustering-based 


# Segmentation

One way to think about segmentation tasks is to think of them as clustering tasks. Clustering is an unsupervised learning technique where the object is to group together similar data points _x<sub>1</sub>, …, x<sub>n</sub> _∈ ℝ<sup>d</sup> (like pixels) into a cluster and represent them with a single token. Clustering extends beyond segmentation and can be used for prediction, counting, and data summarization tasks. 

****Agglomerative clustering**** is a “bottoms-up” approach to clustering where the idea is to look at a distance / similarity measurement between clusters of data points in order to iteratively merge each cluster with the closest cluster. In agglomerative clustering, each data point starts in its own cluster, leading to a “bottoms-up” clustering process where clusters form as data points begin to merge with their most similar pairings.

Table of contents:



1. Data Point Similarity Measures
2. Desirable Clustering Algorithm Properties
3. Agglomerative Clustering Algorithm
4. Cluster Similarity Measures
5. Conclusions


# Distance Measures 

In order to group similar data points together, we need a pairwise distance or similarity function between items in order to evaluate which data points are most similar to each other. When data (e.g. images, objects, documents) are represented by feature vectors, commonly used measures include **_**euclidean distance**_** or **_**cosine similarity**_**

The Euclidean distance measures the distances between two data points x and x’ ∈ ℝ<sup>d</sup> by considering the intuitive straight-line distance between the two points in Euclidean space: 



<p id="gdcalert11" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: equation: use MathJax/LaTeX if your publishing platform supports it. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert12">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>



The cosine similarity measure accounts for the angle between the two given data points and is defined as:



<p id="gdcalert12" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: equation: use MathJax/LaTeX if your publishing platform supports it. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert13">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>



<p id="gdcalert13" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: equation: use MathJax/LaTeX if your publishing platform supports it. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert14">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>




# Desirable Clustering Algorithm Properties

There are multiple properties that one must consider when choosing or designing a clustering algorithm including:



1. **Scalability_ _**(in terms of both running time and memory space)
2. **Different data types **(maintains the ability to deal with different data types)
3. **Input parameters **(has minimal requirements for domain knowledge in order to tune any input parameters for the algorithm)
4. **Interpretable_ _**(the results should be able to be understood and interpreted)
5. **Customizable** (allows for the incorporation of user-specified constraints)


# Agglomerative Clustering Algorithm

The agglomerative clustering algorithm works by initializing each data point as its own cluster, computing the similarity or distance measures between data points in order to group the closest or most similar data points together into larger clusters --- these clusters then merge into even larger clusters until there is one remaining cluster that contains every data point. This clustering process creates a dendrogram tree and can be best visualized below:



<p id="gdcalert14" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: inline image link here (to images/image11.png). Store image on your image server and adjust path/filename/extension if necessary. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert15">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


![alt_text](images/image11.png "image_tooltip")


The first step has all the data points isolated into their own cluster group labeled “A” through “E”. In each step, the algorithm takes the two most similar clusters and merges them together (the red cluster is the first cluster pair that merges together) until the last two cluster groups are merged together and every data point is grouped under one cluster (the purple cluster). The resulting dendrogram clustering result is seen in the final picture. 

The general agglomerative algorithm can be described as:



1. Initialize each item x1, …, xn in its own cluster C1, …, Cn.
2. Repeat until there is only one cluster left:
    1. Find the most similar pair of clusters C_i and C_j
    2. Merge the similar pair of clusters into a parent cluster

When designing an agglomerative clustering implementation one must take into account multiple factors like:



*   How to define cluster similarity --- there are multiple ways to evaluate what makes two clusters more similar than any other pair that can take into account features like the distance between points within the cluster, the maximum or minimum distance between cluster data points, the distance between the average points in a cluster, etc.
*   How many clusters do we end up selecting --- the resulting dendrogram presents multiple cluster groups that we may have to filter in order to have a meaningful and useful clustering scheme. When creating the dendrogram, we can add a threshold based on the maximum number of clusters we want or based on the distance between merges.


# Cluster Similarity Measures

Below are three different schemes for determining the similarity or distance between cluster groups.



1. **Single Link **

	In a single link scheme, we compare clusters by utilizing the minimum distance between two points in each cluster. This is equivalent to determining the minimum spanning tree between clusters. The distance between clusters is computed with the following formula



<p id="gdcalert15" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: inline image link here (to images/image12.png). Store image on your image server and adjust path/filename/extension if necessary. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert16">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


![alt_text](images/image12.png "image_tooltip")


With single linkage, one can set a threshold and stop clustering once the distance between clusters is above the threshold. SIngle linkage tends to produce long and skinny clusters:



<p id="gdcalert16" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: inline image link here (to images/image13.png). Store image on your image server and adjust path/filename/extension if necessary. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert17">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


![alt_text](images/image13.png "image_tooltip")
 



2. **Complete Link**

	In a complete link scheme, we compare clusters by utilizing the maximum distance between two points in each cluster. The distance formula is given by:



<p id="gdcalert17" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: inline image link here (to images/image14.png). Store image on your image server and adjust path/filename/extension if necessary. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert18">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


![alt_text](images/image14.png "image_tooltip")


Complete linkage tends to produce “tight” clusters that are compact and roughly equal in diameter:



<p id="gdcalert18" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: inline image link here (to images/image15.png). Store image on your image server and adjust path/filename/extension if necessary. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert19">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


![alt_text](images/image15.png "image_tooltip")




3. **Average Link**

	In an average link scheme, we compare clusters by utilizing the average distance between items in a cluster pair. The formula is given by:



<p id="gdcalert19" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: inline image link here (to images/image16.png). Store image on your image server and adjust path/filename/extension if necessary. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert20">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


![alt_text](images/image16.png "image_tooltip")


Average linkage tends to be more robust to noise since the distance measurement is not dependent on any one data point pair:



<p id="gdcalert20" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: inline image link here (to images/image17.png). Store image on your image server and adjust path/filename/extension if necessary. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert21">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


![alt_text](images/image17.png "image_tooltip")



# Conclusions

Agglomerative clustering presents multiple benefits and drawbacks.

The benefits:



*   Simple to implement, widespread application.
*   Clusters have adaptive shapes
*   Provides a hierarchy of clusters.
*   No need to specify the number of clusters in advance

The drawbacks:



*   May have imbalance clusters.
*   Requires tuning the number of clusters or a threshold
*   Does not scale well due it runtime of O(n^3)
*   Can get stuck at a local optima.


# Graph-based Segmentation (jacob palisch- jpalisch)

A graph, G, is made up of a set of vertices, V, and edges, E. Each edge has a weight w(v_i, v_j), where v_i and v_j are vertices in V. So, we want to find some segmentation of G, which we call S, such that G’ =(V, E’) where E’ ⊂ E. S divides G into G’ such that it contains distinct cluster C. Click 

<p id="gdcalert21" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: undefined internal link (link text: "here to see graphs in computer vision"). Did you generate a TOC? </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert22">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>

[here to see graphs in computer vision](#heading=h.uukt8vjex0pc)

So how do we define these clusterings?

<p id="gdcalert22" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: equation: use MathJax/LaTeX if your publishing platform supports it. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert23">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>



We define 2 functions for comparing clusterings.

<p id="gdcalert23" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: equation: use MathJax/LaTeX if your publishing platform supports it. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert24">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>



For two clusters 

<p id="gdcalert24" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: equation: use MathJax/LaTeX if your publishing platform supports it. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert25">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>

and 

<p id="gdcalert25" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: equation: use MathJax/LaTeX if your publishing platform supports it. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert26">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>

:



<p id="gdcalert26" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: equation: use MathJax/LaTeX if your publishing platform supports it. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert27">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>

 if 

<p id="gdcalert27" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: equation: use MathJax/LaTeX if your publishing platform supports it. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert28">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>





<p id="gdcalert28" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: undefined internal link (link text: "Diff -> difference between clusterings"). Did you generate a TOC? </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert29">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>

[Diff -> difference between clusterings](#heading=h.re5gi23ydn10)



<p id="gdcalert29" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: undefined internal link (link text: "In -> internal difference between clusterings"). Did you generate a TOC? </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert30">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>

[In -> internal difference between clusterings](#heading=h.gp7eu2t3oo7z)


# Difference Between Clusterings

The difference between clusterings is simple.

For two clusters 

<p id="gdcalert30" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: equation: use MathJax/LaTeX if your publishing platform supports it. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert31">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>

, the difference between them is defined by:

	

<p id="gdcalert31" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: equation: use MathJax/LaTeX if your publishing platform supports it. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert32">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>



In other words, the difference between two clusterings is the shortest distance between two points in opposite clusters.


# Internal Difference Between Clusterings

The internal difference is a slightly more complicated calculation.

For two clusters 

<p id="gdcalert32" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: equation: use MathJax/LaTeX if your publishing platform supports it. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert33">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>

and 

<p id="gdcalert33" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: equation: use MathJax/LaTeX if your publishing platform supports it. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert34">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>

, the internal difference between them is defined by:

	

<p id="gdcalert34" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: equation: use MathJax/LaTeX if your publishing platform supports it. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert35">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>



In simpler terms, the internal difference is the maximum weight edge that connects two nodes in the same component, plus some constant 

<p id="gdcalert35" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: equation: use MathJax/LaTeX if your publishing platform supports it. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert36">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>

 

This constant sets the threshold by which the components need to be different. If you select higher k, you are able to create a preference for larger groupings. However it does not set a minimum.



<p id="gdcalert36" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: inline image link here (to images/image18.png). Store image on your image server and adjust path/filename/extension if necessary. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert37">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


![alt_text](images/image18.png "image_tooltip")
 


# Graphs in Computer Vision

Every pixel is defined by their (x,y) location, but also by their (r,g,b) values. Thus we can define a screen space as a graph defined by (x,y,r,g,b).

**Edges **are between every perpendicular neighboring pixel.

**Weights **are the difference in pixel intensities (r,g,b)

	Determined using L2, or Euclidean, distance in this feature space(x,y,r,g,b)

Also, only to 10 nearest neighbors in feature space are chosen to keep a run time of O(n log n)

