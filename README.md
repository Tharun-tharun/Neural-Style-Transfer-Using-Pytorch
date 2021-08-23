## Style Transfer 

Style Transfer is a process in which we strive to modify the style of an image while preserving its content. Given an input image and a style image, we can compute an output image with the original content but a new style.

![A simple dog with style from "The Scream" painting.](example.png)

## Some of the output images generated while training them the results are:

# Note

I only made upto 10 iterations to make the result more quicker and it's upto you, can train to many interations that you want to be to make image more clear it depends on the image clarity and the style you choose. 

## Input

  ![input](https://user-images.githubusercontent.com/41158838/130415587-17cf0faf-cfc9-4542-a087-046b7f3a7877.png)
  
## Style

  ![style](https://user-images.githubusercontent.com/41158838/130415637-6657e237-da03-431c-86ee-5c6e194d7e0b.png)
  
## Output

### 1 iteration

  ![Iteration 1](https://user-images.githubusercontent.com/41158838/130415749-9ff18a46-0304-4ed8-962f-93ad962f9261.png)

### 2 iterations

  ![Iteration 2](https://user-images.githubusercontent.com/41158838/130415776-7904e875-6c06-487f-8aab-518addba01d3.png)

### 5 iterations

  ![Iteration 5](https://user-images.githubusercontent.com/41158838/130415861-ba9e4176-444d-4c82-af7c-138eee5bbf23.png)
  
 ### 10 iterations 
  
  ![example](https://user-images.githubusercontent.com/41158838/130412992-f2a5bd4c-9f18-4932-9d4f-ef2c39222d10.png)
  
  ## Output
  
  ![example of elon (2)](https://user-images.githubusercontent.com/41158838/130413002-7875d505-6f2e-4695-b246-366e758d82ff.png)
  ![example of elon (1)](https://user-images.githubusercontent.com/41158838/130413014-cd4b8584-812d-474e-b8ae-70ef5035e077.png)
  
## How does it work?
1. I've taken input image and style images and resize them to equal shapes.
2. Then i loaded a pre-trained CNN (VGG16).
3. Knowing that we can distinguish layers that are responsible for the style (basic shapes, colors etc.) and the ones responsible for the content (image-specific features), we can separate the layers to independently work on the content and style.
4. Then I set our task as an optimization problem where we are going to minimize:
	* **content loss** (distance between the input and output images - we strive to preserve the content)
	* **style loss** (distance between the style and output images - we strive to apply a new style)
	* **total variation loss** (regularization - spatial smoothness to denoise the output image)
5. Finally, I set our gradients and optimize with the [L-BFGS](https://en.wikipedia.org/wiki/Limited-memory_BFGS) algorithm.
 
## Credits
This code is inspired from the [pytorch tutorial](https://pytorch.org/tutorials/advanced/neural_style_tutorial.html),
Thanks to the original style transfer paper from [Gatys and al.](https://zpascal.net/cvpr2016/Gatys_Image_Style_Transfer_CVPR_2016_paper.pdf)
