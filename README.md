# CLASS with Interacting Dark Energy

A modification of [CLASS v3.2.3](https://github.com/lesgourg/class_public/tree/v3.2.3) with an interaction between cold dark matter and dark energy:

```text
Q = delta_DMDE * H * rho_DE
d(rho_c)/dt  + 3 H rho_c            =  Q
d(rho_DE)/dt + 3 H (1 + w) rho_DE   = -Q
```

Here `t` is cosmic time. A positive `delta_DMDE` transfers energy from dark energy to cold dark matter in an expanding universe with positive dark energy density.

## Parameters

| Input | Meaning | Default |
| --- | --- | --- |
| `delta_DMDE` | Dimensionless interaction coefficient | `0.0` |

Use constant `w0_fld` with `wa_fld=0`, `Omega_Lambda=0`, `use_ppf=no`, `gauge=synchronous`, and `cs2_fld=1`.
The implemented interacting-fluid branch requires `w0_fld != -1` and `3*w0_fld + delta_DMDE != 0`.

## Compilation

Requires a C compiler, a C++11 compiler, and `make`. From the repository root:

```bash
make -j4 class
```

For the Python interface, use Python 3.9 in a separate environment:

```bash
python -m pip install numpy==1.26.4 scipy==1.11.4 Cython==3.0.11 setuptools==58.1.0
make -j4 libclass.a
cd python
python setup.py build_ext --inplace
```

The resulting `classy` module can be imported from the `python` directory.

## Citation

Please cite D. Blas, J. Lesgourgues and T. Tram, *The Cosmic Linear Anisotropy Solving System (CLASS). II. Approximation schemes*, JCAP 07 (2011) 034, [arXiv:1104.2933](https://arxiv.org/abs/1104.2933), and identify this repository when using the IDE modification.

See [NOTICE.md](NOTICE.md) for upstream acknowledgements and usage conditions.
