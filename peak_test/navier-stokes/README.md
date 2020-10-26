# PCD Preconditioner for Oseen Equation

> <font color=ligblue>**Created Date: 2020-10-23**</font>

## Numerical Example

The Oseen problem on the domain $\Omega:=[0,1]^2$, $\partial\Omega$ is the boundary of the domain $\Omega$
$$
\left\{\begin{split}
-\nu\Delta\boldsymbol{\mathrm u} + \boldsymbol b\cdot\nabla\boldsymbol{\mathrm u} + \nabla p &= \boldsymbol f,\qquad\quad \rm{in}\ \Omega, \\
\nabla\cdot\boldsymbol{\mathrm u} &= 0,\qquad\quad \rm{in}\ \Omega, \\
\boldsymbol{\mathrm u}(x, y) &= (1, 0)^T,\ \ \ \rm{on}\ \partial\Omega^\uparrow:=\{(x, y)\in\partial\Omega\ |\ y = 1\} \\
\boldsymbol{\mathrm u}(x, y) &= \boldsymbol 0,\qquad\quad \rm{elsewhere\ on}\ \partial\Omega,
\end{split}\right.
$$
where $\boldsymbol b$ is defined as follows
$$
\boldsymbol b = \begin{pmatrix}
2(2y-1)(1-(2x-1)^2) \\
-2(2x-1)(1-(2y-1)^2)
\end{pmatrix},
$$
and $\boldsymbol f = \boldsymbol 0$.

## Document description

- `oseen-2d-PETSc.edp` is the main file
- `Operator.idp` stored some macro of operators such as Grad, UgradV, etc
- `macro_ddm_append.idp`: adding `defPart` and `initPart` in some functions such as `reconstructDmesh`, `createMat`, meanwhile, rename these functions as `reconstructDmeshSetDefInit`, `createMatSetDefInit` to support both vectorial FE-space and scalar FE-space.

## Command Line Options

`-nn 64`: $64\times 64$ initial grid (default: $64$)

`-refi 0`: refinement index (default: $0$)

`-Re 100.`: Reynolds number (default: $100.$)

`-epsilon 0.`: pressure stabilization (default: $0.$)

`-visual 0`: whether to visualize numerical solutions (default: $0$)

`ff-mpirun -np 4 oseen-2d-PETSc.edp -v 0`