# Mathematics for Machine Learning — Study Notes, Exercises & Implementations

This repository documents my structured self-study of the core mathematical foundations of Artificial Intelligence and Machine Learning following Deisenroth, Faisal, and Ong's [*Mathematics for Machine Learning*](https://mml-book.github.io/) (Chapters 2 to 7), paired with Gilbert Strang's MIT 18.06 (*Linear Algebra*), Saylor MA122 (*Calculus I*), and Saylor MA121 (*Statistics*).

The goal is to cover the full mathematical curriculum required for graduate-level machine learning—**Linear Algebra, Analytic Geometry, Matrix Decompositions, Vector Calculus & Backpropagation, Probability & Bayesian Inference, and Continuous & Constrained Optimization**—through theoretical notes, analytical exercise derivations, and from-scratch Python/NumPy implementations.

---

## Overview of Mathematical Domains Covered

| Chapter & Domain | Core AI & ML Mathematical Topics | Paired Coursework | Status |
| --- | --- | --- | --- |
| **Ch. 2 — Linear Algebra** | Linear systems, Gaussian elimination ($PA=LU$, RREF), vector spaces, linear independence, basis & rank, four fundamental subspaces, basis change, affine spaces | MIT 18.06 Unit 1 (Lectures 1–13) | **In Progress** |
| **Ch. 3 — Analytic Geometry** | Norms, inner products, lengths & distances, angles & orthogonality, orthonormal bases, Gram-Schmidt, orthogonal projections (geometry of least squares & PCA), rotations | MIT 18.06 Unit 2 (Lectures 14–20) | Planned |
| **Ch. 4 — Matrix Decompositions** | Determinant & trace, eigenvalues & eigenvectors, Cholesky decomposition ($A=LL^\top$), eigendecomposition & diagonalisation, SVD ($A=U\Sigma V^\top$) & Eckart-Young low-rank approximation | MIT 18.06 Units 2 & 3 (Lectures 21–29) | Planned |
| **Ch. 5 — Vector Calculus** | Partial derivatives, gradients, Jacobians, Hessians, matrix calculus identities, chain rule, reverse-mode automatic differentiation (backpropagation), multivariate Taylor series | Saylor MA122 Calculus I + MIT 18.06 | Planned |
| **Ch. 6 — Probability & Distributions** | Probability spaces, discrete & continuous random variables, Bayes' theorem, multivariate Gaussian marginals & Schur-complement conditionals, conjugate priors, exponential family, change of variables | Saylor MA121 Statistics | Planned |
| **Ch. 7 — Continuous Optimization** | Unconstrained gradient descent, condition numbers, heavy-ball momentum, stochastic gradient descent (SGD), Lagrange multipliers, convex sets/functions, Lagrangian duality & KKT conditions | Synthesis of Chapters 5 & 6 | Planned |

---

## Planned From-Scratch Python/NumPy Notebooks

| Notebook | Domain | Implementation & Verification Scope | Status |
| --- | --- | --- | --- |
| `NB01_gaussian_elimination.ipynb` | Linear Algebra (Ch. 2) | Gaussian elimination with partial pivoting, back-substitution, and RREF verified against `numpy.linalg.solve` | Planned |
| `NB02_rank_nullspace_basis.ipynb` | Linear Algebra (Ch. 2) | Rank, column space, nullspace extraction via the Minus-1 Trick, and change-of-basis transformations | Planned |
| `NB03_gram_schmidt_projections_least_squares.ipynb` | Analytic Geometry (Ch. 3) | Modified Gram-Schmidt ($A=QR$), orthogonal subspace projections $P = B(B^\top B)^{-1}B^\top$, and OLS vs `numpy.linalg.lstsq` | Planned |
| `NB04_determinant_eigen_power_iteration.ipynb` | Matrix Decompositions (Ch. 4) | Recursive Laplace expansion vs LU determinants; Power Iteration + Hotelling deflation vs `numpy.linalg.eigh` | Planned |
| `NB05_cholesky.ipynb` | Matrix Decompositions (Ch. 4) | Cholesky factorisation $A=LL^\top$ from scratch and triangular forward/backward substitution vs `scipy.linalg.cho_solve` | Planned |
| `NB06_svd_low_rank.ipynb` | Matrix Decompositions (Ch. 4) | Full SVD, rank-$k$ matrix approximation, and empirical verification of the Eckart-Young spectral/Frobenius error bounds | Planned |
| `NB07_gradient_check.ipynb` | Vector Calculus (Ch. 5) | Analytical gradients vs forward and central finite differences across step sizes $h \in [10^{-12}, 10^{-1}]$ (truncation vs roundoff error) | Planned |
| `NB08_backprop_from_scratch.ipynb` | Vector Calculus (Ch. 5) | Reverse-mode automatic differentiation (backpropagation) for a multi-layer neural network verified against finite differences | Planned |
| `NB09_gaussian_conditioning.ipynb` | Probability & Distributions (Ch. 6) | Multivariate Gaussian sampling via Cholesky ($x = \mu + Lz$) and exact analytical conditional distributions $p(x_A \mid x_B)$ | Planned |
| `NB10_bayes_beta_binomial.ipynb` | Probability & Distributions (Ch. 6) | Sequential conjugate Beta-Binomial Bayesian updating, posterior variance shrinkage, and 95% credible intervals | Planned |
| `NB11_gradient_descent_momentum_sgd.ipynb` | Continuous Optimization (Ch. 7) | Full-batch GD, heavy-ball momentum, and mini-batch SGD trajectories on ill-conditioned quadratics and linear regression | Planned |
| `NB12_constrained_optimization.ipynb` | Continuous Optimization (Ch. 7) | Analytical Lagrange multipliers and KKT active-set geometry verified against `scipy.optimize.minimize` (SLSQP) | Planned |

---

## Detailed Syllabus & Progress Checklist

### Chapter 2: Linear Algebra
- **Section Notes**:
  - [x] **2.1 Systems of Linear Equations** — [2.1_systems_of_linear_equations.md](ch02_linear_algebra/notes/2.1_systems_of_linear_equations.md) *(Row picture vs. column picture, span of columns, solution regimes)*
  - [ ] **2.2 Matrices** *(Matrix multiplication views, transpose, symmetry, inverse matrices)*
  - [ ] **2.3 Solving Systems of Linear Equations** *(Particular & general solutions, elementary row operations, RREF, Minus-1 Trick, Moore-Penrose pseudo-inverse)*
  - [ ] **2.4 Vector Spaces** *(Groups, vector spaces, vector subspaces)*
  - [ ] **2.5 Linear Independence** *(Linear combinations, testing independence via Gaussian elimination)*
  - [ ] **2.6 Basis and Rank** *(Generating sets, basis, rank, Strang's four fundamental subspaces)*
  - [ ] **2.7 Linear Mappings** *(Matrix representation of linear mappings, basis change $\tilde{A}_\Phi = T^{-1}A_\Phi S$, image & kernel, rank-nullity theorem)*
  - [ ] **2.8 Affine Spaces** *(Affine subspaces $x_0 + U$, hyperplanes, affine mappings)*
- **Exercises**:
  - [x] **Exercise 2.1** — [ex_2.1.md](ch02_linear_algebra/exercises/ex_2.1.md) *(Abelian group proof on $\mathbb{R}\setminus\{-1\}$ with $a \star b = ab + a + b$ and solving $3 \star x \star x = 15$)*
  - [ ] Exercises 2.2 – 2.20 *(Group structures, matrix products, inhomogeneous linear systems, subspace proofs, linear independence, basis change, kernel & image)*
- **Notebooks**:
  - [ ] `NB01_gaussian_elimination.ipynb`
  - [ ] `NB02_rank_nullspace_basis.ipynb`

### Chapter 3: Analytic Geometry
- **Section Notes**:
  - [ ] **3.1 Norms** *(Manhattan $\ell_1$, Euclidean $\ell_2$, triangle inequality, Cauchy-Schwarz)*
  - [ ] **3.2 Inner Products** *(Bilinear, symmetric, positive-definite forms; non-standard SPD inner products $\langle x, y \rangle = x^\top A y$)*
  - [ ] **3.3 Lengths and Distances** *(Induced metrics, Mahalanobis distance)*
  - [ ] **3.4 Angles and Orthogonality** *(Cosine similarity, orthogonal vectors and matrices $Q^\top Q = I$)*
  - [ ] **3.5 Orthonormal Basis** *(Coordinate representation $x = \sum \langle x, b_i \rangle b_i$, Parseval's identity)*
  - [ ] **3.6 Orthogonal Complement** *($U^\perp$, direct sum decomposition $V = U \oplus U^\perp$, fundamental theorem of linear algebra $\text{null}(A^\top) = \text{col}(A)^\perp$)*
  - [ ] **3.7 Inner Product of Functions** *($L^2([a,b])$ inner product, orthogonal polynomials & Fourier basis)*
  - [ ] **3.8 Orthogonal Projections** *(Projection onto 1D lines and $m$-dimensional subspaces $P_\pi = B(B^\top B)^{-1}B^\top$, normal equations $B^\top B\lambda = B^\top x$, Gram-Schmidt orthogonalisation)*
  - [ ] **3.9 Rotations** *(Givens rotations in $\mathbb{R}^2$ and $\mathbb{R}^n$, $SO(n)$)*
- **Exercises**:
  - [ ] Exercises 3.1 – 3.10 *(Inner product proofs, distances & angles under general SPD matrices, Gram-Schmidt, orthogonal projections, least-squares residuals)*
- **Notebooks**:
  - [ ] `NB03_gram_schmidt_projections_least_squares.ipynb`

### Chapter 4: Matrix Decompositions
- **Section Notes**:
  - [ ] **4.1 Determinant and Trace** *(Geometric volume scaling, Laplace expansion, multiplicative property, cyclic trace invariance)*
  - [ ] **4.2 Eigenvalues and Eigenvectors** *(Characteristic polynomial $p(\lambda)=\det(A-\lambda I)$, algebraic vs. geometric multiplicity, spectral theorem for symmetric matrices)*
  - [ ] **4.3 Cholesky Decomposition** *($A = LL^\top$ for symmetric positive-definite matrices, applications to linear solvers and Gaussian sampling)*
  - [ ] **4.4 Eigendecomposition and Diagonalisation** *($A = PDP^{-1}$, orthogonal diagonalisation $A = Q\Lambda Q^\top$, matrix powers)*
  - [ ] **4.5 Singular Value Decomposition (SVD)** *($A = U\Sigma V^\top$, connection to eigenvalues of $A^\top A$ and $AA^\top$, geometric mapping of the unit sphere)*
  - [ ] **4.6 Matrix Approximation** *(Rank-$k$ truncated SVD $A_k = \sum_{i=1}^k \sigma_i u_i v_i^\top$, Eckart-Young theorem in spectral and Frobenius norms)*
  - [ ] **4.7 Matrix Phylogeny** *(Hierarchy of general, square, normal, orthogonal, symmetric, and SPD matrices)*
- **Exercises**:
  - [ ] Exercises 4.1 – 4.12 *(Determinants, characteristic polynomials, eigenspaces, Cholesky factorisation, SVD derivations, rank-1 approximations, Moore-Penrose pseudo-inverse via SVD)*
- **Notebooks**:
  - [ ] `NB04_determinant_eigen_power_iteration.ipynb`
  - [ ] `NB05_cholesky.ipynb`
  - [ ] `NB06_svd_low_rank.ipynb`

### Chapter 5: Vector Calculus
- **Section Notes**:
  - [ ] **5.1 Differentiation of Univariate Functions** *(Difference quotients, Taylor polynomials, differentiation rules)*
  - [ ] **5.2 Partial Derivatives and Gradients** *(Row-vector gradient convention $\nabla_x f \in \mathbb{R}^{1 \times n}$, directional derivatives, steepest ascent)*
  - [ ] **5.3 Gradients of Vector-Valued Functions** *(Jacobian matrix $J \in \mathbb{R}^{m \times n}$, multivariable chain rule via Jacobian multiplication)*
  - [ ] **5.4 Gradients of Matrices** *(Tensor derivatives, reshaping vs. trace trick)*
  - [ ] **5.5 Useful Identities for Computing Gradients** *(Gradients of linear forms, quadratic forms $x^\top Ax$, trace, and $\log\det X$)*
  - [ ] **5.6 Backpropagation and Automatic Differentiation** *(Computation graphs, forward mode vs. reverse mode autodiff, sensitivity propagation $\delta^{(l)}$)*
  - [ ] **5.7 Higher-Order Derivatives** *(Hessian matrix $H \in \mathbb{R}^{n \times n}$, curvature, positive-definiteness at local minima)*
  - [ ] **5.8 Linearization and Multivariate Taylor Series** *(First-order linear and second-order quadratic local approximations)*
- **Exercises**:
  - [ ] Exercises 5.1 – 5.9 *(Jacobians, gradients of quadratic forms, ridge regression & log-determinant derivatives, chain rule through neural layers, Hessians)*
- **Notebooks**:
  - [ ] `NB07_gradient_check.ipynb`
  - [ ] `NB08_backprop_from_scratch.ipynb`

### Chapter 6: Probability and Distributions
- **Section Notes**:
  - [ ] **6.1 Construction of a Probability Space** *(Sample space $\Omega$, event $\sigma$-algebra, Kolmogorov axioms, random variables)*
  - [ ] **6.2 Discrete and Continuous Probabilities** *(PMFs, PDFs, CDFs, joint & marginal distributions)*
  - [ ] **6.3 Sum Rule, Product Rule, and Bayes' Theorem** *(Prior, likelihood, marginal likelihood / evidence, posterior inference)*
  - [ ] **6.4 Summary Statistics and Independence** *(Expectation, variance, covariance matrices $\Sigma$, statistical independence vs. zero correlation)*
  - [ ] **6.5 Gaussian Distribution** *(Univariate & multivariate Gaussians $\mathcal{N}(\mu, \Sigma)$, precision matrices, analytical marginalisation and Schur-complement conditioning, linear transformations)*
  - [ ] **6.6 Conjugacy and the Exponential Family** *(Bernoulli-Beta, Multinomial-Dirichlet, Gaussian-Gaussian conjugacy; natural parameters $\theta$, sufficient statistics $\phi(x)$, log-partition cumulants)*
  - [ ] **6.7 Change of Variables / Inverse Transform** *(Inverse CDF sampling, Jacobian determinant formula $p_y(y) = p_x(f^{-1}(y))\left|\det J_{f^{-1}}(y)\right|$)*
- **Exercises**:
  - [ ] Exercises 6.1 – 6.13 *(Bayes' theorem, law of total variance, Gaussian conditioning & linear combinations, Beta-Binomial conjugacy, exponential family representations, change of variables)*
- **Notebooks**:
  - [ ] `NB09_gaussian_conditioning.ipynb`
  - [ ] `NB10_bayes_beta_binomial.ipynb`

### Chapter 7: Continuous Optimization
- **Section Notes**:
  - [ ] **7.1 Optimization Using Gradient Descent** *(Unconstrained optimization, step-size bounds via $\lambda_{\max}(H)$, condition number $\kappa = \lambda_{\max}/\lambda_{\min}$, heavy-ball momentum, stochastic gradient descent)*
  - [ ] **7.2 Constrained Optimization and Lagrange Multipliers** *(Equality & inequality constraints, Lagrangian $\mathcal{L}(x, \lambda, \nu)$, Karush-Kuhn-Tucker (KKT) conditions, complementary slackness)*
  - [ ] **7.3 Convex Optimization** *(Convex sets & functions, first-order supporting hyperplane and second-order PSD Hessian characterisations, Legendre-Fenchel conjugate, LP and QP Lagrangian duals, strong duality)*
- **Exercises**:
  - [ ] Exercises 7.1 – 7.11 *(Stationary point classification, unbiased SGD variance bounds, LP/QP dual derivations, KKT conditions for hard-margin SVM, Legendre-Fenchel conjugates)*
- **Notebooks**:
  - [ ] `NB11_gradient_descent_momentum_sgd.ipynb`
  - [ ] `NB12_constrained_optimization.ipynb`

---

## Local Environment Setup

```bash
python3 -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
```
