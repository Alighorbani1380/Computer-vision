# Querstion:
Try to create the image below using bitwise operations available in the OpenCV library with the help of a circle and a rectangle.
# Main Subject: Creating and Manipulating Shapes in an Image using OpenCV
## Description:
This Python script employs the OpenCV library to create an image containing geometric shapes and demonstrates basic image manipulation techniques. The script initializes a blank canvas and draws a filled white circle and a filled white square on it. A half-circle is extracted and rotated before being combined with the rectangle to form a visually interesting composite image. The final result is displayed in a window and saved to a file named shape.jpg.

## Code Explanation:
Imports and Setup:

The script imports the necessary libraries: cv2 for image processing and numpy for numerical operations.
It sets the height and width of the canvas to 300 pixels.
### Creating a Blank Image:

A blank image (image) is created with a black background using np.zeros.
### Drawing a Circle:

A white filled circle is drawn at the center of the image.
The circle's coordinates, radius, color, and thickness are defined.
### Drawing a Square:

A white filled square is defined using the top-left and bottom-right coordinates.
The square is drawn on a separate black canvas (rectangle).
### Creating a Mask for Half-Circle:

A mask is created to define the area for a half-circle.
The half-circle is extracted from the full circle using a bitwise AND operation.
### Rotating the Half-Circle:

The half-circle is rotated by -35 degrees.
The rotation is performed using an affine transformation based on the rotation matrix obtained from cv2.getRotationMatrix2D.
### Combining Shapes:

The rotated half-circle is combined with the rectangle using a bitwise OR operation to create the final image.
Displaying and Saving the Result:

The resulting image is displayed in a window titled 'output' and saved as shape.jpg.

![image](https://github.com/user-attachments/assets/ed8ba455-ce3b-4f6e-96db-670f7b22de18)

