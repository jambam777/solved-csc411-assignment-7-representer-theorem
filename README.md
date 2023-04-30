Download Link: https://assignmentchef.com/product/solved-csc411-assignment-7-representer-theorem
<br>
<ol>

 <li><strong>Representer Theorem. </strong>In this question, you’ll prove and apply a simplified version of the Representer Theorem, which is the basis for a lot of kernelized algorithms. Consider a linear model:</li>

</ol>

<em>z </em>= <strong>w</strong><sup>&gt;</sup><em>ψ</em>(<strong>x</strong>) <em>y </em>= <em>g</em>(<em>z</em>)<em>,</em>

where <em>ψ </em>is a feature map and <em>g </em>is some function (e.g. identity, logistic, etc.). We are given a training set . We are interested in minimizing the expected loss plus an <em>L</em><sub>2 </sub>regularization term:

where L is some loss function. Let <strong>Ψ </strong>denote the feature matrix

Observe that this formulation captures a lot of the models we’ve covered in this course, including linear regression, logistic regression, and SVMs.

<ul>

 <li><strong> </strong>Show that the optimal weights must lie in the row space of <strong>Ψ</strong>.</li>

</ul>

<em>Hint: Given a subspace </em>S<em>, a vector </em><strong>v </strong><em>can be decomposed as </em><strong>v </strong>= <strong>v</strong><sub>S </sub>+<strong>v</strong><sub>⊥</sub><em>, where </em><strong>v</strong><sub>S </sub><em>is the projection of </em><strong>v </strong><em>onto </em>S<em>, and </em><strong>v</strong><sub>⊥ </sub><em>is orthogonal to </em>S<em>. (You may assume this fact without proof, but you can review it here</em><a href="#_ftn1" name="_ftnref1"><sup>[1]</sup></a><em>.) Apply this decomposition to </em><strong>w </strong><em>and see if you can show something about one of the two components.</em>

<ul>

 <li><strong>[3pts] </strong>Another way of stating the result from part (a) is that <strong>w </strong>= <strong>Ψ</strong><sup>&gt;</sup><em>α </em>for some vector <em>α</em>. Hence, instead of solving for <strong>w</strong>, we can solve for <em>α</em>. Consider the vectorized form of the <em>L</em><sub>2 </sub>regularized linear regression cost function:</li>

</ul>

<strong>Ψw</strong><strong>  </strong><em>.</em>

Substitute in <strong>w </strong>= <strong>Ψ</strong><sup>&gt;</sup><em>α</em>, to write the cost function as a function of <em>α</em>. Determine the optimal value of <em>α</em>. Your answer should be an expression involving <em>λ</em>, <strong>t</strong>, and the Gram matrix <strong>K </strong>= <strong>ΨΨ</strong><sup>&gt;</sup>. For simplicity, you may assume that <strong>K </strong>is positive definite. (The algorithm still works if <strong>K </strong>is merely PSD, it’s just a bit more work to derive.)

<em>Hint: the cost function </em>J(<em>α</em>) <em>is a quadratic function. Simplify the formula into the following form:</em>

<em>for some positive definite matrix </em><strong>A</strong><em>, vector </em><strong>b </strong><em>and constant c (which can be ignored). You may assume without proof that the minimum of such a quadratic function is given by </em><em>α </em>= −<strong>A</strong><sup>−1</sup><strong>b</strong><em>.</em>

<ol start="2">

 <li><strong>] Compositional Kernels. </strong>One of the most useful facts about kernels is that they can be composed using addition and multiplication. I.e., the sum of two kernels is a kernel, and the product of two kernels is a kernel. We’ll show this in the case of kernels which represent dot products between finite feature vectors.

  <ul>

   <li><strong> </strong>Suppose <em>k</em><sub>1</sub>(<em>x,x</em><sup>0</sup>) = <em>ψ</em><sub>1</sub>(<em>x</em>)<sup>&gt;</sup><em>ψ</em><sub>1</sub>(<em>x</em><sup>0</sup>) and <em>k</em><sub>2</sub>(<em>x,x</em><sup>0</sup>) = <em>ψ</em><sub>2</sub>(<em>x</em>)<sup>&gt;</sup><em>ψ</em><sub>2</sub>(<em>x</em><sup>0</sup>). Let <em>k</em><sub>S </sub>be the sum kernel <em>k</em><sub>S</sub>(<em>x,x</em><sup>0</sup>) = <em>k</em><sub>1</sub>(<em>x,x</em><sup>0</sup>)+<em>k</em><sub>2</sub>(<em>x,x</em><sup>0</sup>). Find a feature map <em>ψ</em><sub>S </sub>such that <em>k</em><sub>S</sub>(<em>x,x</em><sup>0</sup>) = <em>ψ</em><sub>S</sub>(<em>x</em>)<sup>&gt;</sup><em>ψ</em><sub>S</sub>(<em>x</em><sup>0</sup>).</li>

   <li><strong> </strong>Suppose <em>k</em><sub>1</sub>(<em>x,x</em><sup>0</sup>) = <em>ψ</em><sub>1</sub>(<em>x</em>)<sup>&gt;</sup><em>ψ</em><sub>1</sub>(<em>x</em><sup>0</sup>) and <em>k</em><sub>2</sub>(<em>x,x</em><sup>0</sup>) = <em>ψ</em><sub>2</sub>(<em>x</em>)<sup>&gt;</sup><em>ψ</em><sub>2</sub>(<em>x</em><sup>0</sup>). Let <em>k</em><sub>P </sub>be the product kernel <em>k</em><sub>P</sub>(<em>x,x</em><sup>0</sup>) = <em>k</em><sub>1</sub>(<em>x,x</em><sup>0</sup>)<em>k</em><sub>2</sub>(<em>x,x</em><sup>0</sup>). Find a feature map <em>ψ</em><sub>P </sub>such that <em>k</em><sub>P</sub>(<em>x,x</em><sup>0</sup>) = <em>ψ</em><sub>P</sub>(<em>x</em>)<sup>&gt;</sup><em>ψ</em><sub>P</sub>(<em>x</em><sup>0</sup>).</li>

  </ul></li>

</ol>

<em>Hint: For inspiration, consider the quadratic kernel from Lecture 20, Slide 11.</em>

2

<a href="#_ftnref1" name="_ftn1">[1]</a> <a href="https://metacademy.org/graphs/concepts/projection_onto_a_subspace">https://metacademy.org/graphs/concepts/projection_onto_a_subspace</a>