## Warm-up
If we have a matrix,
$$
\mathbf{M} =
\begin{bmatrix} a & b \\ c & d \end{bmatrix}
$$

We can ask what action does it have on the basis vectors,
$$
\mathbf{i} =
\begin{bmatrix} 1 \\ 0 \end{bmatrix}
\mathrm{ \;\; and \;\; }
\mathbf{j} =
\begin{bmatrix} 0 \\ 1 \end{bmatrix}
$$

if we calculate these then,
$$
\mathbf{M}\mathbf{i} =
\begin{bmatrix} a & b \\ c & d \end{bmatrix}
\begin{bmatrix} 1 \\ 0 \end{bmatrix} =
\begin{bmatrix} a \\ c \end{bmatrix}
\mathrm{ \;\; and \;\; }
\mathbf{M}\mathbf{j} =
\begin{bmatrix} a & b \\ c & d \end{bmatrix}
\begin{bmatrix} 0 \\ 1 \end{bmatrix} =
\begin{bmatrix} b \\ d \end{bmatrix}
$$

that is, we're picking out the first and second columns of the matrix.
In effect a matrix is a list of column vectors of where to send each basis vector.
i.e. for,
$$
\mathbf{a} =
\begin{bmatrix} a \\ c \end{bmatrix}
\mathrm{ \;\; and \;\; }
\mathbf{b} =
\begin{bmatrix} b \\ d \end{bmatrix}
$$

then,
$$
\mathbf{M} =
\begin{bmatrix} \mathbf{a} & \mathbf{b} \end{bmatrix}
$$

so concisely put,
$$
\mathbf{M}\mathbf{i} = \mathbf{a}
\mathrm{ \;\; and \;\; }
\mathbf{M}\mathbf{j} = \mathbf{b}
$$

## Eigenvalues and eigenvectors
The matrix $\mathbf{M}$ will have eigenvectors, $\mathbf{u}_1$ and $\mathbf{u}_2$, for which applying this matrix scales them by factors $λ_1$ and $λ_2$, but otherwise leaves the direction unchanged.
$$
\mathbf{M}\mathbf{u}_1 = \mathbf{λ}_1 \mathbf{u}_1
\mathrm{ \;\; and \;\; }
\mathbf{M}\mathbf{u}_2 = \mathbf{λ}_2 \mathbf{u}_2
$$

We want to see if we can represent $\mathbf{M}$ in terms of its eigenvalues and eigenvectors.
Let's start with the scaling part. A diagonal matrix will scale the basis vectors,
$$
\mathbf{D} = \begin{bmatrix} λ_1 & 0 \\ 0 & λ_2 \end{bmatrix}
$$

such that,
$$
\mathbf{D}\mathbf{i} = λ_1 \mathbf{i}
\mathrm{ \;\; and \;\; }
\mathbf{D}\mathbf{j} = λ_2 \mathbf{j}
$$

This is almost what we want from our matrix, but instead of scaling $\mathbf{i}$ and $\mathbf{j}$, we'd like it to operate on  $\mathbf{u}_1$ and $\mathbf{u}_2$ instead.
So can we construct a matrix which transforms $\mathbf{u}_1$ and $\mathbf{u}_2$ into $\mathbf{i}$ and $\mathbf{j}$?
Well, we can certainly do it the other way around, the matrix,
$$
\mathbf{U} =
\begin{bmatrix}
\mathbf{u}_1 & \mathbf{u}_2
\end{bmatrix}
$$

will send $\mathbf{i}$ to $\mathbf{u}_1$ and $\mathbf{j}$ to $\mathbf{u}_2$.
So, the inverse of this matrix,
$$
\mathbf{U}^{-1} =
\begin{bmatrix} \mathbf{u}_1 & \mathbf{u}_2 \end{bmatrix}^{-1}
$$

Will do exactly what we want, and send $\mathbf{u}_1$ to $\mathbf{i}$ and $\mathbf{u}_2$ to $\mathbf{j}$.

So we have an operation $\mathbf{U}^{-1}$ that will transform eigenvectors into the basis vectors, an operation $\mathbf{D}$ that will scale the basis vectors, and an operation $\mathbf{U}$ that will transform the basis vectors back into unit vectors. Which means, if we combine them right-to-left, we can reconstruct the action of the original matrix $\mathbf{M}$.
$$
\mathbf{M} =
\mathbf{U}\mathbf{D}\mathbf{U}^{-1} =
\begin{bmatrix} \mathbf{u}_1 & \mathbf{u}_2 \end{bmatrix}
\begin{bmatrix} λ_1 & 0 \\ 0 & λ_2 \end{bmatrix}
\begin{bmatrix} \mathbf{u}_1 & \mathbf{u}_2 \end{bmatrix}^{-1}
$$

with action,
$$
\mathbf{M}\mathbf{u}_1 = \mathbf{λ}_1 \mathbf{u}_1
\mathrm{ \;\; and \;\; }
\mathbf{M}\mathbf{u}_2 = \mathbf{λ}_2 \mathbf{u}_2
$$

as required.

One thing to note is that it doesn't matter the magnitude of the eigenvectors, as this gets cancelled out with the inverse matrix. As such, we often specify the eigenvalues as unit vectors. And if they are real valued, they can be expressed with a single value.
$$
\mathbf{u}_1 =
\begin{bmatrix} \cos θ_1 \\ \sin θ_1 \end{bmatrix}
\mathrm{ \;\; and \;\; }
\mathbf{u}_2 =
\begin{bmatrix} \cos θ_2 \\ \sin θ_2 \end{bmatrix}
$$

So if we want, we can write the matrix as,
$$
\mathbf{M} =
\mathbf{U}\mathbf{D}\mathbf{U}^{-1} =
\begin{bmatrix} \cos θ_1  & \cos θ_2 \\ \sin θ_1 & \sin θ_2 \end{bmatrix}
\begin{bmatrix} λ_1 & 0 \\ 0 & λ_2 \end{bmatrix}
\begin{bmatrix} \cos θ_1  & \cos θ_2 \\ \sin θ_1 & \sin θ_2 \end{bmatrix}^{-1}
$$

Which specifies the matrix with four parameters, $λ_1$, $λ_2$, $θ_1$, and $θ_2$, of the eigenbasis, instead of the usual $a$, $b$, $c$, and $d$ of the basis vectors.
This is the form presented on https://fourier.space/matrices.

## Dynamic Systems
This diagonal form comes in very usefully when looking at dynamic systems with a first order linear differential equation.

i.e., for,
$$
\frac{\mathrm{d}}{\mathrm{d}t} \mathbf{x}(t) =
\mathbf{M} \mathbf{x}(t)
$$

The time evolution of the system is given by,
$$
\mathbf{x}(t) =
\begin{bmatrix} \mathbf{u}_1 & \mathbf{u}_2 \end{bmatrix}
\begin{bmatrix} e^{λ_1 t} & 0 \\ 0 & e^{λ_2 t} \end{bmatrix}
\begin{bmatrix} \mathbf{u}_1 & \mathbf{u}_2 \end{bmatrix}^{-1}
\mathbf{x}(0)
$$

Which, reading right-to-left says, take the initial condition $\mathbf{x}(0)$ and express it in the eigenbasis of the matrix ($\mathbf{u}_1$ and $\mathbf{u}_2$), then in those directions exponentially decay or grow the contribution of that eigenvector at a rate given by the eigenvalues $λ_1$ and $λ_2$, then re-express the result in the starting basis ($\mathbf{i}$ and $\mathbf{j}$).

The sign of the real part of the eigenvalues is important. Positive real-part eigenvalues will exponentially grow their corresponding eigenvector in the system evolution, where negative real-part eigenvectors will decay it.
If we have all negative real-part eigenvalues, then we have a stable attractor, where nearby trajectories will evolve to.
Having purely imaginary eigenvalues is an orbit that neither grows nor decays, and complex eigenvalues will spiral in or out depending on the real part sign.
