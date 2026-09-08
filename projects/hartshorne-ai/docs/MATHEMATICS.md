# Mathematical foundations and construction families

Throughout, $\mathbf P^n=\mathbf P^n_{\mathbf C}$, $H=c_1(\mathcal O(1))$, and “bundle” means locally free. Computations may begin over $\mathbf Q$, with their characteristic-zero base-change meaning recorded. Rank-two decomposability here is precisely splitting as a sum of two line bundles.

## 1. Conjecture, charts, and gauges

The target is Hartshorne's rank-two conjecture: every such bundle on $\mathbf P^n$, $n\ge7$, splits as $\mathcal O(a)\oplus\mathcal O(b)$. [Stapleton](https://arxiv.org/abs/2001.11075) states this formulation and describes torus-equivariant cases; the search must not be restricted to a class already forced to split.

Use $U_i=\{x_i\ne0\}\simeq\mathbf A^n$, $i=0,\ldots,n$. With local coordinate columns satisfying $v_i=g_{ij}v_j$, the conditions are

$$
g_{ij}\in\mathrm{GL}_2(\mathcal O(U_i\cap U_j)),\quad
g_{ii}=I,\quad g_{ji}=g_{ij}^{-1},\quad g_{ij}g_{jk}=g_{ik}.
$$

In $U_i$-coordinates, the overlap ring is the polynomial chart ring localised at $x_j/x_i$. Entries must lie in that ring and the determinant must be a unit there. Frame changes $h_i\in\mathrm{GL}_2(\mathcal O(U_i))$ act by $g'_{ij}=h_i g_{ij}h_j^{-1}$. On an affine-space chart, an invertible polynomial matrix has nonzero constant determinant. Elementary polynomial shears are safe gauge generators. Sampling invertible numerical matrices at finitely many points does not establish these conditions.

[GAGA](https://www.numdam.org/item/AIF_1956__6__1_0/) algebraises holomorphic bundles on projective space. Quillen–Suslin gives algebraic triviality over each affine-space chart. Neither permits arbitrary meromorphic/rational gauges nor identifies algebraic triviality with mere topological triviality.

Fix the sign convention: for $\mathcal O(a)$, $g_{ij}=(x_j/x_i)^a$. On $\mathbf P^1$, put $t=x_1/x_0$, $u=t^{-1}$. For a split bundle, $D(t)=\operatorname{diag}(t^a,t^b)$; an obscured presentation is

$$
G(t)=H_0(t)D(t)H_1(t^{-1})^{-1}.
$$

Its entries and inverse must be Laurent-polynomial matrices. The stored inverse gauges provide a constructive splitting certificate, but must never enter the predictor's input.

## 2. Chern baseline and its limits

For $n\ge2$, write $c_1(E)=sH$, $c_2(E)=pH^2$. A split pair must satisfy

$$
a+b=s,\qquad ab=p,\qquad \Delta=s^2-4p=(a-b)^2.
$$

Hence a candidate exists exactly when $\Delta=m^2\ge0$ for an integer $m$ and $s\equiv m\pmod2$; then it is $\{(s-m)/2,(s+m)/2\}$. Absence of such a pair proves nonsplitting **after validity is established**. Existence of the pair proves nothing about splitting. On $\mathbf P^1$, $c_2$ vanishes and $c_1=a+b$ does not determine the pair. The exact section-count formula for a split bundle on $\mathbf P^1$ is

$$
h^0(E(q))=\max(a+q+1,0)+\max(b+q+1,0).
$$

Twisting by $\mathcal O(q)$ gives $s'=s+2q$, $p'=p+qs+q^2$. The discriminant is unchanged. A normalised-Chern-bin holdout should therefore be included when testing beyond memorised twists.

## 3. Why one fixed plane suffices

Let $E$ be a vector bundle, of any rank, on $\mathbf P^N$, $N\ge3$, and let $L\simeq\mathbf P^2$ be any fixed linear plane. Then

$$
E\text{ splits}\quad\Longleftrightarrow\quad E|_L\text{ splits}.
$$

For rank two, splitting degrees on the two spaces agree. This is a consequence of the hyperplane lifting argument underlying Horrocks' criterion; see [references](REFERENCES.md). Here is a proof, included to make the reduction independently checkable.

Let $F$ be a vector bundle on $\mathbf P^m$, $m\ge3$, whose restriction to a hyperplane $D$ splits. The sequence

$$
0\longrightarrow F(t-1)\longrightarrow F(t)\longrightarrow F|_D(t)\longrightarrow0
$$

and $H^1(F|_D(t))=0$ show that $H^1(F(t-1))\to H^1(F(t))$ is surjective for all $t$. For sufficiently negative $t$, $H^1(F(t))=0$ by Serre duality and Serre vanishing applied to $F^\vee$. Surjectivity propagates this vanishing to every twist. If $A=\bigoplus_j\mathcal O(a_j)$ has the splitting degrees of $F|_D$, the isomorphism $A|_D\to F|_D$ lifts to a map $A\to F$ since $H^1(F(-a_j-1))=0$ for every summand. Restriction identifies determinants, and $\operatorname{Pic}(\mathbf P^m)\to\operatorname{Pic}(D)$ is an isomorphism. The determinant of the lifted map is therefore a constant, nonzero on $D$, hence everywhere nonzero. The map is an isomorphism. Apply this repeatedly along a flag from $L$ to $\mathbf P^N$.

Boundaries: local freeness on all of $\mathbf P^N$ is essential. For example, $\mathcal I_p\oplus\mathcal O$ on $\mathbf P^3$ restricts to a trivial bundle on a plane avoiding $p$, but is not a bundle globally. Restriction to $\mathbf P^1$ cannot detect splitting on $\mathbf P^2$, since all bundles on the line split. Finally, an arbitrary nonsplit plane bundle need not extend to higher projective space. The fixed-plane theorem reduces **detection for an existing bundle**, not its construction or extension.

## 4. Plane syzygy family: equivalence, not splitting classification

Let $S=\mathbf C[x,y,z]$, $d\ge2$, and let $W=\langle f_1,f_2,f_3\rangle\subset S_d$ be three-dimensional with no common projective zero. Define

$$
0\longrightarrow E_W\longrightarrow\mathcal O^3
\xrightarrow{(f_1,f_2,f_3)}\mathcal O(d)\longrightarrow0.
$$

Basepoint-freeness makes the map surjective everywhere, so the kernel is locally free of rank two. It is certified by $(f_1,f_2,f_3):(x,y,z)^\infty=S$. Exactness and $H^1(\mathcal O(t))=0$ on $\mathbf P^2$ yield the graded-module isomorphism

$$
H^1_*(E_W)\simeq (S/(f_1,f_2,f_3))(d),
$$

where the degree-$t$ piece on the right is $(S/I)_{t+d}$. Its annihilator recovers $I$; since all three generators have degree $d$, $I_d=W$. Thus, at fixed $d$ and fixed base coordinates, bundle isomorphism implies equality of $W$. Conversely, changing a basis of $W$ by $\mathrm{GL}_3$ gives isomorphic kernels. Exact row reduction of the coefficient matrix therefore supplies an identifier for this family. Quotienting by automorphisms of $\mathbf P^2$ is a different equivalence relation and is not implicit here.

The Chern calculation is immediate:

$$
c(E_W)=(1+dH)^{-1}=1-dH+d^2H^2,\qquad \Delta=-3d^2<0.
$$

All these bundles are nonsplit. Mixing this family alone with split examples would permit classification by a trivial Chern obstruction. Use it to test generators, equivalence, deduplication, and presentation invariance, not to claim nontrivial splitting learning.

Initial fixtures (proposed, not computed): $W=\langle x^2,y^2,z^2\rangle$ and $W'=\langle x^2+yz,y^2,z^2\rangle$ are distinct basepoint-free row spaces. The triple $(x^2,xy,xz)$ is invalid for this family: the map vanishes along $x=0$. Its generic kernel rank is not sufficient.

## 5. Chern-matched split/nonsplit controls

Fix $a\le b$, choose $k>b$, and a reduced finite subscheme $Z\subset\mathbf P^2$ of length $\ell=(k-a)(k-b)>0$. Construct a locally free extension

$$
0\longrightarrow\mathcal O(k)\longrightarrow E_Z
\longrightarrow\mathcal I_Z(a+b-k)\longrightarrow0.
$$

For clarity about existence, twist by $-k$ and put $c=a+b-2k<0$. A reduced finite $Z$ is a codimension-two local complete intersection. Its required determinant condition holds on the finite reduced scheme, and $H^2(\mathcal O(-c))=0$; Hartshorne–Serre therefore applies. Equivalently, select a global extension class whose local component is nonzero at every point of $Z$. Not every class is locally free. Store the class and check the resulting presentation. See [Arrondo](https://arxiv.org/abs/math/0610015) for the correspondence; the following are direct calculations for this family.

$$
c_1(E_Z)=(a+b)H,\qquad
c_2(E_Z)=\bigl(k(a+b-k)+\ell\bigr)H^2=abH^2.
$$

Twisting the extension by $-k$, its right term has no global sections since $a+b-2k<0$. Consequently $h^0(E_Z(-k))=1$. But $h^0((\mathcal O(a)\oplus\mathcal O(b))(-k))=0$. The Chern pair allows no other split target, so $E_Z$ is nonsplit. These bundles are unstable; instability is not synonymous with splitting.

A smallest conceptual fixture is $(a,b,k)=(0,0,1)$, with $Z$ one reduced point: compare the resulting nonsplit bundle with $\mathcal O^{\oplus2}$. Both have $(c_1,c_2)=(0,0)$. This is a theoretical fixture, not a stored computed certificate.

## 6. Exact general equivalence test

Let $E,F$ be verified rank-two bundles on the same $\mathbf P^n$ with $\det E\simeq\det F$, and fix such a determinant identification. Compute the **complete** space $H^0(E^\vee\otimes F)$, with basis $\phi_1,\ldots,\phi_r$. Then

$$
q(\lambda)=\det\left(\sum_i\lambda_i\phi_i\right)
\in H^0(\mathcal O_{\mathbf P^n})[\lambda_1,\ldots,\lambda_r]
=\mathbf C[\lambda_1,\ldots,\lambda_r]
$$

is a homogeneous scalar quadratic. If it is not identically zero, some linear combination has nonzero constant determinant and is an isomorphism. If it is identically zero and the Hom basis is complete, no isomorphism exists. Testing only individual basis maps is insufficient: an invertible linear combination may exist even if all basis maps are singular. A bounded subset of Hom with identically zero determinant proves nothing.

For splitting with $n\ge2$, compute the unique candidate $F=\mathcal O(a)\oplus\mathcal O(b)$ from Chern classes if it exists, and apply this test. If computations are over $\mathbf Q$, completeness and field extension must be justified; nonzero polynomials over the infinite field $\mathbf Q$ admit rational nonvanishing evaluations.

## 7. Higher-dimensional barriers

Three positive-degree homogeneous forms in $n+1$ variables with $n\ge3$ have a common projective zero: an ideal with three generators has height at most three, smaller than the irrelevant ideal's height. Hence the plane three-form ansatz cannot supply the same globally surjective construction in higher dimension.

Do not choose a short monad of line bundles merely because its matrices are easy to sample. Audit its forced cohomology first; splitting criteria can exclude every desired counterexample within the ansatz. In particular, the inner-cohomology constraints in Kumar–Peterson–Rao must be checked before approving such a search space. The optional $\mathbf P^3$ stage uses separately audited constructions. No $\mathbf P^7$ candidate family is currently approved.
