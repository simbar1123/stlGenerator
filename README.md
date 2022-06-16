# CompGeo_Make_STL
## Objective
Develop a simple web app/page to create and download STL files for any user provided multivariable (limit to 2: x, y) mathematical expression.
- The mathematical expression represents a 3D surface, where x, y and result of the expression, are 3 values representing cartesian co-ordinates in 3D space
- For example, the expression (x-2)^2+(y-2)^2+2 represents the following surface...
![image](https://user-images.githubusercontent.com/91622575/172967186-0d411590-662e-4344-8a23-33286d679915.png)
## Web Interface
The web page will have the following visual elements...
- A field for the user to enter a mathematical expression ('Function entry').
- A button to begin the process of generating the STL file after user enters the expression above ('Generate STL').
- Window/Region to display a 3D shape in the STL just generated.
- Another button to download the STL file generated above ('Download').
## Operation
The program will operate and be used as described below...
- User should be able to enter any two variable expression, such as `(x-2)^2+(y-2)^2+2`.
- The program should understand and support various mathematical operations, including addition, subtraction, multiplication, division and power function, including fractional values for root functions. Support for additional mathematical operations - exponent, trignometric functions, etc. may be added as a bonus.
- Once the desired expression is entered, clicking the 'Generate STL' button should begin the process of generating and displaying corresponding STL.
  * The program will process the expression to generate a point cloud with sufficient granularity so it fairly represents details of the geometry.
  * Convert the point cloud into a STL mesh.
  * The STL mesh will then be rendered in the display window.
- Once generated, the user can click the 'Download' button to cause the generated STL to be downloaded.
## Requirements
- The app may be developed using any framework/programming language the user is comfortable with (although Python is our preferred language).
- The deliverables must include documentation and all artifacts necessary to deploy and run the application.
- To enable review, deliverables must include code - not just executables. And per good programming practices, be sufficiently documented for ease of understanding.
## Submission
In order to submit the assignment, do the following:

1. Navigate to GitHub's project import page: [https://github.com/new/import](https://github.com/new/import)

2. In the box titled "Your old repository's clone URL", paste the homework repository's link: [https://github.com/Machina-Labs/CompGeo_Make_STL](https://github.com/Machina-Labs/CompGeo_Make_STL)

3. In the box titled "Repository Name", add a name for your local homework (ex. `Make_STL_soln`)

4. Set privacy level to "Public", then click "Begin Import" button at bottom of the page.

5. Develop your homework solution in the cloned repository and push it to Github when you're done. Extra points for good Git hygiene.

6. Send us the link to your repository.
