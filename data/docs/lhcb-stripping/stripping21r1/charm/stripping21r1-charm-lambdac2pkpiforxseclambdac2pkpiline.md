[[stripping21r1 lines]](./stripping21r1-index)

# StrippingLambdac2PKPiForXSecLambdac2PKPiLine

## Properties:

|                |                                                    |
|----------------|----------------------------------------------------|
| OutputLocation | Phys/Lambdac2PKPiForXSecLambdac2PKPiLine/Particles |
| Postscale      | 1.0000000                                          |
| HLT            | HLT_PASS_RE('Hlt1MB.\*')                           |
| Prescale       | 1.0000000                                          |
| L0DU           | None                                               |
| ODIN           | None                                               |

## Filter sequence:

CheckPV/checkPVmin1

|        |     |
|--------|-----|
| MinPVs | 1   |
| MaxPVs | -1  |

LoKi::VoidFilter/SelFilterPhys_StdAllNoPIDsPions_Particles

|      |                                                                                                      |
|------|------------------------------------------------------------------------------------------------------|
| Code | CONTAINS('Phys/[StdAllNoPIDsPions](./stripping21r1-commonparticles-stdallnopidspions)/Particles')\>0 |

LoKi::VoidFilter/SelFilterPhys_StdAllNoPIDsKaons_Particles

|      |                                                                                                      |
|------|------------------------------------------------------------------------------------------------------|
| Code | CONTAINS('Phys/[StdAllNoPIDsKaons](./stripping21r1-commonparticles-stdallnopidskaons)/Particles')\>0 |

LoKi::VoidFilter/SelFilterPhys_StdAllNoPIDsProtons_Particles

|      |                                                                                                          |
|------|----------------------------------------------------------------------------------------------------------|
| Code | CONTAINS('Phys/[StdAllNoPIDsProtons](./stripping21r1-commonparticles-stdallnopidsprotons)/Particles')\>0 |

CombineParticles/Lambdac2PKPiForXSecLambdac2PKPiLine

|                  |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
|------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Inputs           | [ 'Phys/[StdAllNoPIDsKaons](./stripping21r1-commonparticles-stdallnopidskaons)' , 'Phys/[StdAllNoPIDsPions](./stripping21r1-commonparticles-stdallnopidspions)' , 'Phys/[StdAllNoPIDsProtons](./stripping21r1-commonparticles-stdallnopidsprotons)' ]                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
| DaughtersCuts    | { '' : 'ALL' , 'K+' : '(PT \> 200.0)& (BPVIPCHI2() \> 1.0)&(HASRICH)& (in_range(pidFiducialPMin, P, pidFiducialPMax))& (in_range(2.0, ETA, 5.0))& ((PIDK-PIDpi) \> 0.0)' , 'K-' : '(PT \> 200.0)& (BPVIPCHI2() \> 1.0)&(HASRICH)& (in_range(pidFiducialPMin, P, pidFiducialPMax))& (in_range(2.0, ETA, 5.0))& ((PIDK-PIDpi) \> 0.0)' , 'p+' : '(PT \> 200.0)& (BPVIPCHI2() \> 1.0)&(HASRICH)& (in_range(pidFiducialPMin, P, pidFiducialPMax))& (in_range(2.0, ETA, 5.0))& ((PIDp-PIDpi) \> 0.0)& ((PIDp-PIDK) \> 0.0)' , 'pi+' : '(PT \> 200.0)& (BPVIPCHI2() \> 1.0)&(HASRICH)& (in_range(pidFiducialPMin, P, pidFiducialPMax))& (in_range(2.0, ETA, 5.0))& ((PIDK-PIDpi) \< 3.0)' , 'pi-' : '(PT \> 200.0)& (BPVIPCHI2() \> 1.0)&(HASRICH)& (in_range(pidFiducialPMin, P, pidFiducialPMax))& (in_range(2.0, ETA, 5.0))& ((PIDK-PIDpi) \< 3.0)' , 'p~-' : '(PT \> 200.0)& (BPVIPCHI2() \> 1.0)&(HASRICH)& (in_range(pidFiducialPMin, P, pidFiducialPMax))& (in_range(2.0, ETA, 5.0))& ((PIDp-PIDpi) \> 0.0)& ((PIDp-PIDK) \> 0.0)' } |
| CombinationCut   | (ADAMASS('Lambda_c+') \< 90.0)& (AMAXCHILD(PT) \> 1000.0)& (AMAXCHILD(BPVIPCHI2()) \> 4.0)& (ANUM(PT \> 400.0) \>= 2)& (ANUM(BPVIPCHI2() \> 1.0) \>= 2)& (ADOCAMAX('') \< 0.5)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| MotherCut        | (VFASPF(VCHI2/VDOF) \< 25.0)& (((BPVVDCHI2 \> 4.0)\|(BPVLTIME() \> 0.075 \* picosecond)))& (BPVDIRA \> bpvdirathresh)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| DecayDescriptor  | None                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| DecayDescriptors | [ '[Lambda_c+ -\> p+ K- pi+]cc' ]                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| Output           | Phys/Lambdac2PKPiForXSecLambdac2PKPiLine/Particles                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |