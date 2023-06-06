# vsd_workshop - Advanced Physical design
<p> Introduction to OpenLANE - Sky130nm PDK
  <br> The main goal is to produce a clean GDSII without human intervention.
  
# Package(QFN-48) --> Chip (Die, Core, Pads)
<p> PLL, SRAM, ADC, DAC - Foundry IP's
<br> RISCV SoC, SPI - Macros
<br> For Digital ASIC opensource design --> RTL design, EDA tools, PDK are the required components.

![1](https://github.com/jenila19/vsd_workshop/assets/135401281/e8d98223-3baa-4e0d-b5ec-84a3230ddca3)
# Docker

![2](https://github.com/jenila19/vsd_workshop/assets/135401281/52b5e7c8-fc62-40db-a2de-81d4c4f64142)

# Design Preparation
$ docker
$ ./flow.tcl -interactive
$ package require openlane 0.9
$ prep -design picorv32a

![3](https://github.com/jenila19/vsd_workshop/assets/135401281/e9690df9-b40a-4a0e-9e22-f846e2a8132c)

$ run_synthesis

![4](https://github.com/jenila19/vsd_workshop/assets/135401281/7f4a01d8-a636-4e07-8417-5e75d85fbb50)

# Floorplanning 
1. It defines the width and height of core and die (dimensions of chip)
2. Also, define the locations of preplaced cells.
Parameters - Utilization factor and Aspect ratio

$ run_floorplan
<p> PDN generation was successful

![5](https://github.com/jenila19/vsd_workshop/assets/135401281/c8ea9ca2-2cab-4962-9e84-bead72cb2f56)

$ picorv32a.floorplan def file

![6](https://github.com/jenila19/vsd_workshop/assets/135401281/0e65e4c4-b1e4-4622-852b-f6fadc178312)
![7](https://github.com/jenila19/vsd_workshop/assets/135401281/ce21c8e8-51f9-4f5a-973c-7c2518874552)
![8](https://github.com/jenila19/vsd_workshop/assets/135401281/d77d1fd5-d63e-452b-8607-c289c36aa37d)

# Placement
$ run_placement

$ picorv32a.placement def file

![WhatsApp Image 2023-06-04 at 6 48 43 PM (1)](https://github.com/jenila19/vsd_workshop/assets/135401281/f032f792-64f5-4408-94cc-0d24d1d95555)
![WhatsApp Image 2023-06-04 at 6 48 43 PM](https://github.com/jenila19/vsd_workshop/assets/135401281/ea14249a-8ef4-4630-a595-58ef08cf920f)
![WhatsApp Image 2023-06-04 at 6 48 42 PM (3)](https://github.com/jenila19/vsd_workshop/assets/135401281/6be20b14-1b70-4914-881c-3866b474f2a9)

$ git clone nickson jose - vsdstdcelldesign

![WhatsApp Image 2023-06-04 at 6 48 42 PM (2)](https://github.com/jenila19/vsd_workshop/assets/135401281/f4258a5e-bdde-441e-be89-3c15673c8647)
![WhatsApp Image 2023-06-04 at 6 48 42 PM (1)](https://github.com/jenila19/vsd_workshop/assets/135401281/8cc7f0a1-5da8-49ad-9c24-feed8a0e8e6e)

$ Sky130_inv.spice

![WhatsApp Image 2023-06-04 at 6 48 42 PM](https://github.com/jenila19/vsd_workshop/assets/135401281/533a1d8a-a718-415a-ad50-29e792e898d8)
![WhatsApp Image 2023-06-04 at 6 48 41 PM (1)](https://github.com/jenila19/vsd_workshop/assets/135401281/6fb558c2-d474-497b-a16b-ef06227b23a4)
![WhatsApp Image 2023-06-04 at 6 48 41 PM](https://github.com/jenila19/vsd_workshop/assets/135401281/392c25bf-5fd6-4d25-92f5-447c63aa1dae)

# ngspice
$ ngspice sky130_inv.spice
$ plot y vs time a
  
 ![WhatsApp Image 2023-06-06 at 8 09 05 PM (1)](https://github.com/jenila19/vsd_workshop/assets/135401281/153c0433-059f-4670-bfef-dc1afacab453)
![WhatsApp Image 2023-06-06 at 8 09 05 PM](https://github.com/jenila19/vsd_workshop/assets/135401281/fba2f4c5-038a-471f-a0ac-c35390d9c5af)
![WhatsApp Image 2023-06-06 at 8 09 04 PM](https://github.com/jenila19/vsd_workshop/assets/135401281/21bd73c4-bd0f-4cfb-a9c4-5739d93d46ec)
![WhatsApp Image 2023-06-06 at 7 24 36 PM](https://github.com/jenila19/vsd_workshop/assets/135401281/4140aea4-8c11-4a03-959b-94f1267af908)


$ grid 0.46um 0.34um 0.23um 0.17um

![WhatsApp Image 2023-06-06 at 8 09 06 PM](https://github.com/jenila19/vsd_workshop/assets/135401281/b3717094-6fd1-4456-bb35-73d376e0cf1b)
![WhatsApp Image 2023-06-06 at 8 09 05 PM (2)](https://github.com/jenila19/vsd_workshop/assets/135401281/6b476ef8-91f5-4df7-b937-8c27443fb2c5)
 
# Clock Tree Synthesis (CTS)
$ run_cts
![WhatsApp Image 2023-06-06 at 7 24 37 PM (2)](https://github.com/jenila19/vsd_workshop/assets/135401281/7ced24d0-726e-4c46-9398-d13ad51cb1cc)
![WhatsApp Image 2023-06-06 at 7 24 37 PM (1)](https://github.com/jenila19/vsd_workshop/assets/135401281/60e61492-4b9a-45b2-97e2-1c52de1deb15)

# Routing
$ run_routing
![WhatsApp Image 2023-06-06 at 7 24 37 PM](https://github.com/jenila19/vsd_workshop/assets/135401281/78ca1dda-e308-49a5-942b-4de3f58ae747)



