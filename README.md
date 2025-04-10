# external_bases
External basis set files in a format that will be readable by GAMESS when using EXTBAS in the input file 

## How to load an external basis into GAMESS

To load an external basis set the first you need to do is edit your `gms-files.csh/bash`

```
setenv  EXTBAS /path/to/your/basis/basis-file-name
```

For example, the file in `basis_sets/def2` in this repository contains the def2 basis sets. 

If you have your GAMESS directory in say `$HOME/GAMESS` this is your `$GMSPATH`. `EXTBAS` needs to just be findable by 
GAMESS. Let's say you copy def2 to the directory `$GMSPATH/auxdata/def2`. This is then your `EXTBAS` path:

```
setenv EXTBAS $GMSPATH/auxdata/def2
```

## How to enable an external basis in your input file 

You will need  a combination of the following input file parameters 

 - `gbasis` : this is the name you gave your basis in your external file, for example def2-QZVPPD is dqzvppd
 - `basnam` : this is the name of the file where your external basis set is, for example `def2`
 - `extfil` : set to true means that you're using an external basis file

```
!   File created by MacMolPlt 7.7.2
 $CONTRL SCFTYP=RHF RUNTYP=energy MAXIT=30 MULT=1 $END
 $contrl nprint=-5 $end
 $scf DIIS=.t. $end
 $SYSTEM mwords=100 $END
 $basis gbasis=dqzvppd basnam=def2 extfil=.true. $end
 $SCF DIRSCF=.TRUE. $END
 $DATA
Title
C1
H     1.0   -14.71970    -2.81363    -5.04909
H     1.0   -14.48970    -1.19363    -5.00909
O     8.0   -14.93970    -1.94363    -5.49909
 $END
````

## Basis sets included in def2
Defined for all elements shown in the basis set exchange. 
```
!   Basis set: def2-SVP
!   Basis set: def2-SVPD
!   Basis set: def2-TZVP
!   Basis set: def2-TZVPD
!   Basis set: def2-TZVPP
!   Basis set: def2-QZVP
!   Basis set: def2-QZVPP
!   Basis set: def2-QZVPPD
```
