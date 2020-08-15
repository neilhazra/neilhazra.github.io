# Two Wheel Robot

Project Goals:
  1. Create a complete, ideal model of an unstable two wheel robot with Lagrangian dynamics
  2. Use the mathematical model to generate possible robot trajectories from a given starting location to ending location (feed forward control)
  3. Use the mathematical model to design a time-variant Linear Quatratic Regulator to stabalize and execute the trajectory (feed back control)
 
 Throughout I will use MATLAB's computer algebra toolkit to simplify tedious equations. 

## Physical Model with Lagrangian Dynamics

Lagrangian dynamics (https://scholar.harvard.edu/files/david-morin/files/cmchap6.pdf) reduces the task of computing a mathematical model of a mechanical system to a straightforward applicatoin of differential equations and energetics. While Newtonian dynamics requires keeping track of explicit constraint forces and requires the use of a cartesian coordinate system, Lagrangian dynamics is very effective at simplifying complex systems by enforcing constraints implicitly, which greatly reduces the the number of equations and variables required to model a system. 

Lagrangian dynamics is based on the principle of least action (https://en.wikipedia.org/wiki/Principle_of_least_action) which states that the motion of an observed phsyical phenomena minimizes its action-a functional defined by <insert action definition>. Thus Lagrangian mechanics roughly boils down to minimizing this functional to find the equations of motion.  
  
### Generalized Coordinates

In lagrangian dynamics generalized coordinates refer to minimal set of independent parameters needed to describe the state of the mechanical system. For instance, a  swinging pendulum can be described with one generalized coordinate (the angle theta). A double pendulum can be described with a mere two coordinates (the angle of the first pendulum with respect to the horizontal and the angle of the second pendulum with respect to the first). 

For the two wheel robot the generalized coordinates are as follows:

### Lagrangian

The lagrangian, defined by L = Kinetic Energy - Potential Energy, can be simply computed by carefully breaking down the system. 

### Constraints

One of the benefits of lagrangian dynamics is that holonomic constraints are implicit because of the careful choice of generalized coordinates. For instance, there is no need to take account of the normal force because none of the above-mentioned generalized coordinates can describe vertical motion. Likewise, I do not have to worry about internal joint forces on the bearings that hold the axle in place because the generalized coordinates do not describe any motion where the wheel and body move apart. 
 
Unfortunately, an ideal wheel satisfies the rolling-without-slipping assumption which creates a non-holonomic constraint in the two-wheel robot system. This paper describes the non-slip condition in great detail: https://robotics.caltech.edu/~me72/class/DiffDrive2.pdf. By extending the results from the paper, I derived the non-slip condition for my two-wheeled robot stated below:
      No slip condition
        
### Generalized Forces
Lagrangian dynamics works best with only conservative forces, but by using the concept of generalized forces external non-conservative forces can be incorporated with the lagrangian method. 

### Euler Lagrange Equations

```markdown
Syntax highlighted code block

# Header 1
## Header 2
### Header 3

- Bulleted
- List

1. Numbered
2. List

**Bold** and _Italic_ and `Code` text

[Link](https://mail.google.com/mail/u/0/#inbox) and ![Image](src)
```

For more details see [GitHub Flavored Markdown](https://guides.github.com/features/mastering-markdown/).

### Jekyll Themes

Your Pages site will use the layout and styles from the Jekyll theme you have selected in your [repository settings](https://github.com/neilhazra/neilhazra.github.io/settings). The name of this theme is saved in the Jekyll `_config.yml` configuration file.

### Support or Contact

Having trouble with Pages? Check out our [documentation](https://docs.github.com/categories/github-pages-basics/) or [contact support](https://github.com/contact) and we’ll help you sort it out.
