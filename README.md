# STL Generator
## Web app Location/Instructions
The app is located [here](https://stlgenerator.anvil.app)

Upon entering the app, you will be prompted to enter the following 7 fields:
1. Function: the function you wish to render, must be written in proper numpy syntax
2. X minimum: edge of rectangular domain 
3. X maximum: edge of rectangular domain
4. Y minimum: edge of rectangular domain
5. Y maximum: edge of rectangular domain
6. Number of points y: number of equispaced subdivisions in y direction
7. Number of points x: number of equispaced subdivisions in x direction

**Note that the function must be written in proper python syntax using numpy as np**, I recommend trying np.sin(x)+np.sin(y), using something like -10 to 10 for both axes and around 100 points each direction.  Function also must be well defined on entered domain.  Any numpy function can be used as np.function.

Pressing View 3d Point Cloud will display two views of the 3 dimensional point cloud used to generate the stl file (this may display an error banner at some times but ignore that for now, it still works regardless)


Pressing Download STL will generate and download the stl file, this takes like 15 seconds as explained later in this readme.


## Back end
I wrote the back end of this code in a jupyter notebook via google colab.  It works roughly as follows:
1. Generate function that evaluates string function input
2. Create Lattice of XY plane according to specified bounds/number of subdivisions
3. Evaluate all points in lattice w/ function 
4. Using open3d library, generate point cloud and normals 
5. a) If displaying point cloud, create plot and send as image to front end. End of function.
5. b) If downloading Stl, generate mesh via ball pivoting
6. Upload file to google drive folder to be exported via app, delete old copy of file.

A thing to note: because this process involves uploading and downloading from drive, it takes some time. Towards the end of the function downloadSTL, you will find two calls to time.sleep(7).  Depending on your internet connection speed, it may be nescessary to have increased these times in order to download the correct files.  What time works best has varied for me depending on which device I've been editing on.  Too small of a time here will result in downloading whatever file was generated previously. **If you find that incorrect files are being downloaded or you receive a fatal server uplink error, please let me know and I will regenerate the web app with accordingly.**

More detail of exactly what I'm doing is found in comments, please feel free to reach out if there are questions
## Front End
To be completely honest, I do not have much if any front end experience, and thus if front end is a significant part of the computational geometry roll, I think you would do better with a different candidate.  I had never built a web app before, so this is all stuff that I learned over the span of about two days, so please bare with me if it isn't the most beautiful app.

The front end is written in Anvil, which is new to me but fairly intuitive to learn.
I created 7 text box inputs, one image, and two buttons.  All of these are fairly intuitive, the buttons used to generate the stl/images simply take the textbox fields and send them as input to the backend functions.  I am uploading some of the code used to run the button functions, but if you wanted to actually build the app again instead of just looking at the code attached, you will need more information than what is provided as it interfaces directly with my google drive.

## Thoughts
There are a couple of changes I would try to make to this code if I wasn't already preoccupied by my current job, classes, and qualifying exams.
1. use poisson reconstruction instead of ball pivoting
2. figure out how to get files without need for google drive to speed up process
3. display an interactable 3d plot of the stl instead of multiple 2d images (I generated the object within python don't think it can be displayed with anvil)
4. offer ways to discretize domain that aren't always equispaced 

I enjoyed this project, and appreciate you all taking the time to consider me as an employee. I hope to hear back from you soon.
