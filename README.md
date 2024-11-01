java cCIS5200: Machine Learning Fall 2024
Homework 2
Release Date: October 9, 2024 Due Date: October 18, 2024
• HW2 will count for 10% of the grade. This grade will be split between the written (30 points)
and programming (40 points) parts.
• All written homework solutions are required to be formatted using LATEX. Please use the
template here. Do not modify the template. This is a good resource to get yourself more
familiar with LATEX, if you are still not comfortable.
• You will submit your solution for the written part of HW2 as a single PDF file via Gradescope.
The deadline is 11:59 PM ET. Contact TAs on Ed if you face any issues uploading your
homeworks.
• Collaboration is permitted and encouraged for this homework, though each student must
understand, write, and hand in their own submission. In particular, it is acceptable for
students to discuss problems with each other; it is not acceptable for students to look at
another student’s written Solutions when writing their own. It is also not acceptable to
publicly post your (partial) solution on Ed, but you are encouraged to ask public questions
on Ed. If you choose to collaborate, you must indicate on each homework with whom you
collaborated.
Please refer to the notes and slides posted on the website if you need to recall the material discussed
in the lectures.
1 Written Questions (30 points)
Problem 1: Gradient Descent (20 points)
Consider a training dataset S = {(x1, y1), . . . ,(xm, ym)} where for all i ∈ [m], ∥xi∥2 ≤ 1 and
yi ∈ {−1, 1}. Suppose we want to run regularized logistic regression, that is, solve the following
optimization problem: for regularization term R(w),
min
w m
1
mX
i=1
log  1 + exp  −yiw
⊤xi
 + R(w)
Recall: For showing that a twice differentiable function f is µ-strongly convex, it suffices to show
that the hessian satisfies: ∇2f ⪰ µI. Similarly to show hat a twice differentiable function f is
L-smooth, it suffices to show that the hessian satisfies: LI ⪰ ∇2f. Here I is the identity matrix of
the appropriate dimension.
1
1.1 (3 points) In the case where R(w) = 0, we know that the objective is convex. Is it strongly
convex? Explain your answer.
1.2 (3 points) In the case where R(w) = 0, show that the objective is 1-smooth.
1.3 (4 points) In the case of R(w) = 0, what is the largest learning rate that you can choose such
that the objective is non-increasing at each iteration? Explain your answer.
Hint: The answer is not 1/L for a L-smooth function.
1.4 (1 point) What is the convergence rate of gradient descent on this problem with R(w) = 0?
In other words, suppose I want to achieve F(wT +1) − F(w∗) ≤ ϵ, express the number of iterations
T that I need to run GD for.
Note: You do not need to reprove the convergence guarantee, just use the guarantee to provide the
rate.
1.5 (5 points) Consider the following variation of the ℓ2 norm regularizer called the weighted ℓ2norm regularizer: for λ1, . . . , λd ≥ 0,
Show that the objective with R(w) as defined above is µ-strongly convex and L-smooth for µ =
2 minj∈[d] λj and L = 1 + 2 maxj∈[d] λj .
1.6 (4 points) If a function is µ-strongly convex and L-smooth, after T iterations of gradient
descent we have:
Using the above, what is the convergence rate of gradient descent on the regularized logistic re gression problem with the weighted ℓ2 norm penalty? In other words, suppose I want to achieve
∥wT +1 − w∗∥2 ≤ ϵ, express the number of iterations T that I need to run GD.
Note: You do not need to prove the given convergence guarantee, just provide the rate.
Problem 2: MLE for Linear Regression (10 points)
In this question, you are going to derive an alternative justification for linear regression via the
squared loss. In particular, we will show that linear regression via minimizing the squared loss is
equivalent to maximum likelihood estimation (MLE) in the following statistical model.
Assume that for given x, there exists a true linear function parameterized by w so that the label y
is generated randomly as
y = w
⊤x + ϵ
2
where ϵ ∼ N (0, σ2
) is some normally distributed noise with mean 0 and variance σ
2 > 0. In other
words, the labels of your data are equal to some true linear function, plus Gaussian noise around
that line.
2.1 (3 points) Show that the above model implies that the conditional density of y given x is
P p(y|x) = 1.
Hint: Use the density function of the normal distribution, or the fact that adding a constant to a
Gaussian random variable shifts the mean by that constant.
2.2 (2 points) Show that the risk of the predictor f(x) = E[y|x] is σ.
2.3 (3 points) The likelihood for the given data {(x1, y1), . . . ,(xm, ym)} is given by.
Lˆ(w, σ) = p(y1, . . . , ym|x1, . . . , xm) =
Compute the log conditional likelihood, that is, log Lˆ(w, σ).
Hint: Use your expression for p(y | x) from part 2.1.
2.4 (2 points) Show that the maximizer of log Lˆ(w, σ) is the same as the minimizer of the empirical
risk with squared loss, ˆR(w) = m
Hint: Take the derivative of your result from 2.3 and set it equal to zero.
2 Programming Questions (20 points)
Use the link here to access the Google Colaboratory (Colab) file for this homework. Be sure to
make a copy by going to “File”, and “Save a copy in Drive”. As with the previous homeworks, this
assignment uses the PennGrader system for students to receive immediate feedback. As noted on
the notebook, please be sure to change the student ID from the default ‘99999999’ to your 8-digit
PennID.
Instructions for how to submit the programming component of HW 2 to Gradescope are included
in the Colab notebook. You may find this PyTorch linear algebra reference and this general
PyTorch reference to be helpful in perusing the documentation and finding useful functions for
your implementation.
3

         
加QQ：99515681  WX：codinghelp  Email: 99515681@qq.com
