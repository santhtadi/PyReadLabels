# PyReadLabels

A Python Package to read labels from an image

## USAGE

```
from PyReadLabels import pyreadlabels
```

To return a dictionary with the following keys: lines

```
result = pyreadlabels.detect( "path_to_image" )
#or img = cv2.imread("path_to_image")
##  result = pyreadlabels.detect( img )
print( result["lines"] )
```

To return a dictionary with the following keys: lines, image, pos

```
result = pyreadlabels.detect( "path_to_image", conf=0.25, get_positions=True, x_line=0.2, y_line=0.1, return_image=True )
#or img = cv2.imread("path_to_image")
##  result = pyreadlabels.detect( img, conf=0.25, get_positions=True, x_line=0.2, y_line=0.1, return_image=True )
print( result )
```

conf - confidence score above which the label characters are considered.  
x_line - the percentage difference between x coordinates above which a new line starts.  
y_line - the percentage difference between x coordinates above which a new line starts.  
get_positions - Boolean Value, True returns a "pos" key which contains boxes (absolute x,y,w,h values), correspondind labels, and confidences  
return_image - Boolean Value, True Returns a "image" key which can be used to display image.  

```
import cv2
cv2.imshow( "result", result["image"] )
cv2.waitKey(0)
cv2.destroyAllWindows()
```
