# What is QMA2?

QMA2 is a class where the verifier ("Arthur"), a quantum computer, checks a computation from two unentangled provers ("Merlins").

The verifier receives two quantum  ("witnesses"), *which are guaranteed to be unentangled*. This is the key difference from QMA.

For more info, see this [QMA2 primer](http://www.billfefferman.com/wp-content/uploads/2016/11/bill-qma2Tutorial.pdf) from Bill Fefferman.

## Why is this important?

In QMA2, the verifier is given the extra power of "unentanglement" [[ABDFS08]](https://arxiv.org/pdf/0804.0802.pdf). When a quantum computer's input is guaranteed two be two separable states, it might be able to "do more" than if it was initialized with an unknown quantum state.

But how much more?

# QMAk, QMA2, QMA

We can imagine a generalization of QMA2, where we are given $$k$$ quantum states that are guaranteed to be unentangled.

In general, QMA$$k_1 subseteq$$ QMA$$k_2$$, for $$k_1 \le k_2$. If Arthur can verify given $$k_1$$ unentangled quantum states, then Arthur can verify given any $$k_2 \ge k_1$$ unentengled states, where the extra unentangled states can be ignored.

It turns out that QMAk = QMA2 [[HM13]](https://arxiv.org/pdf/1001.0017.pdf). Their approach uses the SWAP test (checking that two quantum states are similar); this primitive can be used for any $$k \ge 2$$.

But what about the standard class QMA (i.e., when $$k=1$$?) This is still open, even in the oracle setting:

**Open problem [[Problem 2, Aaronson 2021]](https://arxiv.org/pdf/2109.06917.pdf)**: Is there any (classical or quantum) oracle $$\mathcal{O}$$ where QMA $$\ne$$ QMA2?

# QMA2-complete problems

## Hamiltonian problem

One natural problem for QMA2 is the *sparse separable Hamiltonian problem* [[CD10]](https://arxiv.org/pdf/1111.5247.pdf): Decide if there is a separable state that has ground state $$\le a$$, or all states are $$\ge b$$, where $$b-a = \Omega(1/poly(n))$$. This is related to the *sparse Hamiltonian problem*, which is QMA-complete.

One strange result is that both the *k-local Hamiltonian problem* and the *k-local separable Hamiltonian problem* **are QMA-complete**. This means that knowing that the Hamiltonian is a sum of terms operating on only a constant number of qubits, even deciding whether a separable state is of low-energy is possible "without the power of unentanglement".

A natural open question here is: why is there a difference between the *sparse* setting and the *k-local* setting?

## Basis checks and SQMA2
Another
- [QMA vs SQMA](https://arxiv.org/pdf/1410.2882.pdf)

# Error in QMA2
* strong error reduction // in-place error reduction (it was resolved!)

# Properties of QMA2

* Scott -- the power of unentanglement (QMA2 can have very short proofs) (and extensions of this)
- [QMA2 and the quantum polynomial hierarchy](https://arxiv.org/pdf/1805.11139.pdf)

# Resources

- [2016 QuICS Workshop on QMA2](http://qma2016.quics.umd.edu/agenda)
- [Problems slightly harder than QMA](https://ieeexplore.ieee.org/abstract/document/6875473)

---

Thanks to Justin Yirka for direction when starting this document.

More to add? Email me at [kmarw@uchicago.edu](mailto:kmarw@uchicago.edu).
