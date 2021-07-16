# Extracting-lines-from-the-image
This project uses Hough Transform to extract lines.


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
