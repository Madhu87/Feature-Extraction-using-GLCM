# Feature-Extraction-using-GLCM
Extracting Features using GLCM for Single Image and Multiple Image from a folder


Gray Level Co-occurrence Matrix Method (GLCM)

(Statistics method)

Gray-level co-occurrence matrix

Definition :

Describe the joint probability of two pixel values ​​separated by d appearing at the same time

Several concepts:

* Step size n

    * The distance from the center pixel (x, y) (number of pixels)

* Direction α

    * Four directions

        0°(0,d) （x,y+d）
        
        45°（d,-d） (x+d,y-d)
        
        90°（d,0） (x+d,y)
        
        135°（-d,-d） (x-d,y-d)
        
        
Matrix order:

    * The maximum gray level of the image, such as an 8-bit grayscale image, the maximum gray level is 256, then the shape of the co-occurrence matrix is ​​256*256


Solution steps:
    1. Determine the number of gray levels of the image n*n
    
    2. Determine the matrix order n
    
    3. Determine the direction and step length
    
    4. Count the frequency of pixel pairs of adjacent pixel pairs according to the given method
    
    5. Convert frequency to frequency or probability
    
    
Texture feature extraction:

* Angle second moment (energy) ASM

    * Measure whether the grayscale distribution is uniform or not, whether the texture is thick or not, even & fine, with large
    
* Correlation COR

    * The gray scale of rows and columns has a large linear relationship, and the value is large

* Contrast CON

    * Sharp edges, large color difference, large value

* Differential DISL

    * Large local contrast, large value

* Entropy

    * Image complexity, large complexity value

* Inverse difference matrix HOMO

    * The image texture is clear and regular, the clearer the more regular the value is

*Significance*

* The performance of adjacent pixels correlation

* The diagonal elements of the co-occurrence matrix reflect the degree of gray change

    * The diagonal is deviated to 0, the gray level in the specified direction is less repetitive and the change is large
    
    * The diagonal element value deviates from 0, the change is small

Pros and cons

* Advantage:

    -Simple method
    
     Easy to implement
    
     GLCM method is recognized as an effective method
     
     It has strong adaptability and robustness.
     
* Disadvantages:

    It is out of touch with the human visual model, lacks the use of global information, and it is difficult to study the inheritance or dependence of pixels between texture scales
    
    Lack of theoretical support
    
    The computational complexity is very high, which restricts its practical application

Python implementation

Step:

    1. Grayscale the image
    
    2. The image is converted to 8-bit unsigned integer
    
    3. Perform feature compression on the image, compress 256 levels of gray to 16 levels
    
    4. Solve the co-occurrence matrix
    
    5. Get each texture feature
