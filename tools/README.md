# Formatting new basis sets 

The script `format_basis.py` will format a basis exchange copied files. 

To obtain a new basis set, go to the [basis set exchange](https://www.basissetexchange.org/) and select the basis
set you'd like to add to GAMESS. Make sure it is not already there! Make sure also to select GAMESS-US format. 

The `format_basis.py` will need some input from you...

```
# Basis name mapping
basis_map = {
    "def2-SVP": "dsvp",
    "def2-SVPD": "dsvpd",
    "def2-TZVP": "dtzvp",
    "def2-TZVPD": "dtzpd",
    "def2-TZVPP": "dtzpp",
    "def2-QZVP": "dqzvp",
    "def2-QZVPP": "dqzvpp",
    "def2-QZVPPD": "dqzvppd"
}
```
You'll need to create a mapping, it relies on finding the comment from the basis set exchange, i.e. this:

```

!----------------------------------------------------------------------
! Basis Set Exchange
! Version 0.11
! https://www.basissetexchange.org
!----------------------------------------------------------------------
!   Basis set: def2-SVP
! Description: def2-SVP
!        Role: orbital
!     Version: 1  (Data from Turbomole 7.3)
!----------------------------------------------------------------------
```

To know where it has started and finished a section. The mapping will then change the name to the format EXBAS needs:

```
H dsvp
S   3
1        13.0107010              0.19682158E-01
2         1.9622572              0.13796524
3         0.44453796             0.47831935
S   1
1         0.12194962             1.0000000
P   1
1         0.8000000              1.0000000

```

## How to use the script

Simply `python3 format_basis.py file`


To see how to run with your new basis set please go to the README.md in the top level.
