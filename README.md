# Extracting-lines-from-the-image
This project uses Hough Transform to extract lines.

<br>

# Tutorial
Let's extract a straight lines from the image shown in Figure 1.  
|![Hough-example](https://user-images.githubusercontent.com/82690385/125887474-f4279c30-c963-42ac-850a-386a77165360.png)|
|:--|
Figure 1

First, we get the edges of this image using `getEdge(original, converted, padding)`. In this example, we set the parameter `padding` to `valid`. The result is shown in Figure 2.
|![edge_Hough-example](https://user-images.githubusercontent.com/82690385/125888804-f0cf0a46-27d1-46e5-84b3-a7469e3121db.png)|
|:--|
Figure 2

Next, we binarize this image using `binarize(size_x, original, converted, threshold)`. In this example, we set `threshold` to 120. The result is shown in Figure 3.
|![binary_Hough-example](https://user-images.githubusercontent.com/82690385/125889450-8376b0e9-b1b5-4165-848c-915a786918fd.png)|
|:--|
Figure 3

Then, we Hough transform this binarized edge image using `houghTransform(original, converted, list)`. Pass an empty list to `list` and we get a list of pairs of intensity and coordinates for all pixels. The result is shown in Figure 4.
|![hough_transform_Hough-example](https://user-images.githubusercontent.com/82690385/125889850-97346c10-7672-4cc4-89b7-37437f02e4bd.png)|
|:--|
Figure 4

Then, we binarize this image using `binarize(size_x, original, converted, threshold)`, and remove the noise using `maxFilter(image, list)`. In this example, we set `threshold` to 170.　Pass `list` the list that we sorted using `quickSort(x, begin, end, depth)`. The result is shown in Figure 5.
|![filtered_binary_hough_Hough-example](https://user-images.githubusercontent.com/82690385/125890767-18152696-2b66-44fe-ac8d-69f1e52045c6.png)|
|:--|
Figure 5

Then, inverse Hough transforming this image using `inverseHoughTransform(original, converted)`, we get the extracted straight line. The result is shown in Figure 6.
|![inverse_hough_transform_Hough-example](https://user-images.githubusercontent.com/82690385/125891141-6ea59104-26d0-4a03-9132-68b218ee4a64.png)|
|:--|
Figure 6

Turn this extracted line green and overlay it on the original image, and the result is shown in Figure 7.
|![overlay_Hough-example](https://user-images.githubusercontent.com/82690385/125891610-806bb9cd-736b-42ce-8a3b-dab78f9d1c05.png)|
|:--|
Figure 7

<br>





# function
## load(f1, fp1, filepath)
  Loads the image.
  
  ### Parameters
  * f1  
    A matrix that receives loaded image.  
    <br>
    
  * fp1  
    A file pointer.  
    <br>
    
  * filepath  
      Relative path to the image to load.  
      <br>
      
      
      
 ## save(sizeOfImage, g1, fp2, filepath)
  Saves the image.
  
  ### Parameters
 * sizeOfImage  
    Size of the image to save.  
    <br>
    
  * g1  
    A matrix that holds the image to be saved.  
    <br>
    
  * fp2  
    A file pointer.  
    <br>
    
  * filepath  
      Relative path to the image to save.  
      <br>
      
 
 
 ## getEdge(original, converted, padding)
  Extracts image edges.
  
  ### Parameters
 * original  
    A matrix that holds the image being extracted for edges.  
    <br>
    
  * converted  
    A matrix that receives edge image.  
    <br>
    
  * padding  
    A file pointer.  
    <br>
    
 
      
## binarize(size_x, original, converted, threshold)
  Binarizes the image.
  
  ### Parameters
 * size_x  
    Size of the image to save.  
    <br>
    
  * original  
    A matrix that holds the image to be binarized.  
    <br>
    
  * converted  
    A matrix that receives binarized image.  
    <br>
    
  * threshold  
      Threshold for binarization.  
      <br>
      
 
 
## houghTransform(original, converted, list)
  Hough transform the image.
  
  ### Parameters
 * original  
    A matrix that holds the image to be Hough transformed.  
    <br>
    
  * converted  
    A matrix that receives Hough transformed image.  
    <br>
    
  * list  
      A list that holds pairs of coordinates and intensity for all pixels.  
      <br>
      
 
 
## inverseHoughTransform(original, converted)
  Inverse Hough transform the image.
  
  ### Parameters
 * original  
    A matrix that holds the image to be Inverse Hough transformed.  
    <br>
    
  * converted  
    A matrix that receives Inverse Hough transformed image.  
    <br>
  
      
 
## quickSort(x, begin, end, depth)
  Inverse Hough transform the image.
  
  ### Parameters
  * x  
    A list to be sorted.  
    <br>
    
  * begin  
    The index at the top of the list. 
    <br>
    
  * end  
    The index at the end of the list.  
    <br>
    
  * depth  
      The value for the recursive process. Set to 0 when calling this function.  
      <br>
  
      
 
## maxFilter(image, list)
  Removes the noise contained in the binarized image after the Hough transform.
  
  ### Parameters
  * image  
    A matrix that holds the binarized image after the Hough transform.  
    <br>
    
  * list  
      A sorted list in ascending order of intensity values.  
      <br>
      
      
      
# Requirement
The size of the input image must be N x N. (The value of N can be specified in `SIZE` in settings.h.)
