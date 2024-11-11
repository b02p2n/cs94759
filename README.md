java c
CS/ECE/ISyE 524 
Introduction to Optimization 
Fall 2024 
Homework 4a: Convex and Quadratic Programming 
Due date: Friday November 8, 2024 
All solutions should be uploaded to Canvas.
1. [10 points] Heat pipe design. A heated fluid at temperature T (degrees above ambient temperature) flows in a pipe with fixed length and circular cross section with radius r. A layer of insulation, with thickness w, surrounds the pipe to reduce heat loss through the pipe walls (w is much smaller than r). The design variables in this problem are T, r, and w.
The energy cost due to heat loss is roughly equal to α1T r/w. The cost of the pipe, which has a fixed wall thickness, is approximately proportional to the total material, i.e., it is given by α2r. The cost of the insulation is also approximately proportional to the total insulation material, i.e., roughly α3rw. The total cost is the sum of these three costs.
The heat flow down the pipe is entirely due to the flow of the fluid, which has a fixed velocity, i.e., it is given by α4T r2. The constants αi are all positive, as are the variables T, r, and w.
Your task is to maximize the total heat flow down the pipe, subject to an upper limit Cmax on total cost, and the constraints
Tmin ≤ T ≤ Tmax,              rmin ≤ r ≤ rmax              wmin ≤ w ≤ wmax,              w ≤ 0.1r
. a) Express this problem as a geometric program. Recall that a generic geometric program has the following form.

b) Turn out the geometric program into a convex optimization problem, and try to simplify it as much as possible.
c) Consider a simple instance of this problem, where Cmax = 500 and α1 = α2 = α3 = α4 = 1. Also assume for simplicity that each variable has a lower bound of zero and no upper bound. Implement this problem using JuMP with the Ipopt solver. What is the optimal T, r, and w?
2. [10 points] Quadratic form. positivity. You’re presented with the constraint:
2x2 + 2y2 + 9z2 + 8xy − 6xz − 6yz ≤ 1                                      (1)
a) Write the constraint (1) in the standard form. vTQv ≤ 1. Where Q is a symmetric matrix. What is Q and what is v?
b) It turns out the above constraint is not convex. Explain why this is the case.
Hint: You can perform. an eigenvalue decomposition of a symmetric matrix Q in Julia by first loading the linear algebra operators with using LinearAlgebra and then typing
(L,U) = eigen(Q) # L is the vector of eigenvalues and U is orthogonal
(You are not required to submit your Julia code as part of the solution!)
c) Find a direction for vector (x, y, z) such that ∥(x, y, z)∥2 (the norm) is unbounded (can be made代 写CS/ECE/ISyE 524 Introduction to Optimization Fall 2024 Homework 4a: Convex and Quadratic ProgrammingMatlab
代做程序编程语言 arbitrarily large) while satisfying the constraint (1).
d) We can also write the constraint (1) using norms by putting it in the form.
∥Av∥2 − ∥Bv∥2 ≤ 1
What is v and what are the matrices A and B that make the constraint above equivalent to (1)?
Hint: Consider the difference of positive matrices.
3. [10 points] Spline fitting. We are running a series of experiments to evaluate the properties of a new fluorescent material. As we vary the intensity of the incident light, the material should fluoresce different amounts. Unfortunately, the material isn’t perfectly uniform. and our method for measuring fluorescence is not very accurate. After testing 200 different intensities, we obtained the result below (also available in xy_data.csv). The intensities xi and fluorescences yi are recorded in the first and second columns of the data matrix, respectively.

The material has interesting nonlinear properties, and we would like to characterize the relationship between intensity and fluorescence by using an approximate model that agrees well with the trend of our experimental data. Although there is noise in the data, we know from physics that the fluorescence must be zero when the intensity is zero. This fact must be reflected in all of our models!
a) [5 points] Polynomial fit. Use least squares to find the best cubic polynomial fit to the data. In other words, look for a function of the form. y = a1x3 + a2x2 + a3x + a4 that has the best possible agreement with the data. Remember that the model should have (exactly) zero fluorescence when the intensity is zero! Include a plot of the data along with your best-fit cubic on the same axes.
b) [5 points] Spline fit. Instead of using a single cubic polynomial, we will look for a fit to the data using two quadratic polynomials. Specifically, we want to find coefficients pi and qi so that our data is well modeled by the piecewise quadratic function:

These quadratic functions must be designed so that:
• as in the cubic model, there is zero fluorescence when the intensity is zero.
• both quadratic pieces have the same value at x = 4.
• both quadratic pieces have the same slope at x = 4.
In other words, we are looking for a smooth piecewise quadratic. This is also known as a spline (this is just one type of spline, there are many other types). Include a plot of the data along with your best-fit model.
4. [Final project] Please upload your final project description (one per group) and a copy of your team agreement (one per group, signed by all members) to Canvas by Tuesday, November 12.





         
加QQ：99515681  WX：codinghelp  Email: 99515681@qq.com
