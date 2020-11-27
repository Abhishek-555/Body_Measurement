# Body Measurements using CV

### LYIT dissertation project

The goal of this project was to make ***real-world body part*** measurements using 2D images. The repository includes methods to measure ***shoulder distance, wrist-to-shoulder measurement, and waist approximation***.

To run code, change to *src/* directory and type linux shell:
```
python code2.py -i1 ../Images/aman1.jpg -i2 ../Images/aman2.jpg -i3 ../Images/aman3.jpg -a <Correction_mode>
```

## Notes on running the code

1. The code has been tested and developed in ***python3*** using OpenCV version `4.4.0`
2. Images required for above code are specific, and been taken from an opensource site.
3. Correction_mode parameter is the flag, which tells code whether to perform ***affine + metric correction*** on the image. Enter `True` to perform correction else `False`

## Additional Notes

1. First 2 images that pops up is for finding `waist` circumference. Mark waist ends on both the image.
2. Next 2 images are for calculating `shoulder` length. Mark fall near neck both sides in first image and mark shoulder, both-sides in second image.
3. Repeat step 2 again. This is again calculating shoulder length for robustness from different image.
4. Mark both the `wrist` - end of hands nearly in the next popped image. 
5. While in 2,3,4 points, there is also projected points shown. You can manually mark or not mark.


### Input Image1 

This image is with the subject holding a ***checkered board*** in hands. This helps measure ***shoulder*** distance.

Checkered board is important as it helps in ***calibration*** of camera image for ***3D measurements***. If you use any other chess-type board, measure the side length of ***unit square and*** change ***global ref_ht*** parameter in ***code2.py***.

### Input Image2 

This image is with the subject spreading out his hands. This helps in ***wrist-to-shoulder*** measurement, and provide width of waist's projection.


### Input Image3 

This image is capturing side-view of subject. This provide thickness of waist and helps complete ***waist*** measurement.

Waist is modelled as an ***ellipse*** and measured analogous to finding ***perimeter of ellipse***. Hence ***appromation*** is mentioned.

When code runs, you will be shown points selected by our ***heuristic*** as to-be shoulder/wrist. If suspicious/incorrect, you can ***explicitly*** select those points on image and pressing `esc` key thereafter.


###Output

Following will be the output produced by the model

![alt text](https://github.com/Abhishek-555/LYIT_Dissertation_Body_Measurement/blob/main/Outputofthemodel.png)
