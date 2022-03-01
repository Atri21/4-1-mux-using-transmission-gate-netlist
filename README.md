# 4-1-mux-using-transmission-gate-netlist
*  Generated for: PrimeSim
*  Design library name: test
*  Design cell name: t3
*  Design view name: schematic
.lib 'saed32nm.lib' TT

*Custom Compiler Version S-2021.09
*Sun Feb 27 10:14:48 2022

.global gnd!
********************************************************************************
* Library          : transmission_gate
* Cell             : transmission_gate
* View             : schematic
* View Search List : hspice hspiceD schematic spice veriloga
* View Stop List   : hspice hspiceD
********************************************************************************
.subckt transmission_gate a s sb y  
xm12 y net40 net36 net36 p105 w=0.1u l=0.03u nf=1 m=1  
xm3 net25 sb net29 net14 p105 w=0.1u l=0.03u nf=1 m=1  
xm2 net29 net40 net36 net14 p105 w=0.1u l=0.03u nf=1 m=1  
xm1 net40 net25 net36 net36 p105 w=0.1u l=0.03u nf=1 m=1  
xm0 net25 s a a p105 w=0.1u l=0.03u nf=1 m=1  
xm13 y net40 gnd! gnd! n105 w=0.1u l=0.03u nf=1 m=1  
xm7 net29 net40 gnd! net30 n105 w=0.1u l=0.03u nf=1 m=1  
xm6 net25 s net29 net30 n105 w=0.1u l=0.03u nf=1 m=1  
xm5 net40 net25 gnd! gnd! n105 w=0.1u l=0.03u nf=1 m=1  
xm4 a sb net25 net25 n105 w=0.1u l=0.03u nf=1 m=1  
v10 net36 gnd! dc=1.8  
c15 y gnd! c=0.1p  
.ends transmission_gate   
 
********************************************************************************
* Library          : test
* Cell             : t3
* View             : schematic
* View Search List : hspice hspiceD schematic spice veriloga
* View Stop List   : hspice hspiceD
********************************************************************************
v32 net71 gnd! dc=0 pulse ( 0 1.8 0 1n 1n 64u 128u )  
v31 net72 gnd! dc=0 pulse ( 1.8 0 0 1n 1n 64u 128u )  
v24 net56 gnd! dc=0 pulse ( 1.8 0 0 1n 1n 8u 16u )  
v22 net57 gnd! dc=0 pulse ( 1.8 0 0 1n 1n 16u 32u )  
v17 net55 gnd! dc=0 pulse ( 0 1.8 0 1n 1n 32u 64u )  
v16 net62 gnd! dc=0 pulse ( 1.8 0 0 1n 1n 32u 64u )   
v15 net41 gnd! dc=0 pulse ( 1.8 0 0 1n 1n 4u 8u )   
v14 net39 gnd! dc=0 pulse ( 1.8 0 0 1n 1n 2u 4u )   
xi29 net65 net71 net72 y transmission_gate  
xi28 net82 net72 net71 y transmission_gate  
xi26 net56 net62 net55 net65 transmission_gate  
xi25 net57 net55 net62 net65 transmission_gate  
xi13 net41 net55 net62 net82 transmission_gate  
xi12 net39 net62 net55 net82 transmission_gate  
  


.tran '20u' '250u' name=tran  

.option primesim_remove_probe_prefix = 0  
.probe v(*) i(*) level=1  
.probe tran v(y) v(net39) v(net41) v(net55) v(net56) v(net57) v(net62) v(net65) + v(net71) v(net72) v(net82)  

.temp 25  

.option primesim_output=wdf  


.option parhier = LOCAL


.end
