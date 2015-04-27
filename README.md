#Chemistry-Engine
Models Chemical reactions with or without catalysts by utilizing randomly moving particles based on a [Boltzmann distribution](http://en.wikipedia.org/wiki/Boltzmann_distribution). There's also 2 really nifty visualizer to view the particles and overall reaction concentrations.

##Notables:
**/project:** where all the awesome code is

**/commands:** text files for each example. A reaction can be forward `->` or reversable `<->` , and the first two numbers are the forward and backward activation energy, respectivly. Each reactant is depicted by `[Number of Particles][Name] [Concentration] [Color]`. Writing `DEFAULT` as the color selects a random rgb. Each catalyst needs to be in its own file, and follows reactant protocol, with the addition of `[Delta Activation Energy]` at the end. 

##Examples:
**Example 1:** Models the Reaction NH3 + HCL -> NH4Cl (ammonium chloride).

Command Text: `0 0 1NH3 2.734E-23 BLUE 1HCl 5.852E-23 GREEN -> 1NH4Cl 8.586E-23 RED`

![Ex 1](/pictures/ex1.png)

**Example 2:** CO2 + 2H2O <-> HCO3- + H3O+

Command Text: `1E-20 1E-20 1CO2 7.064E-23 BLUE 2H2O 2.892E-23 GREEN <-> 1HCO3 9.794E-23 RED 1H3O 3.053E-23 ORANGE`

![Ex 2](/pictures/ex2.png)

**Example 3:** Example 2, but with the catalyst carbonic anhydrase and reacts noticably faster. 

Command Text: Level 2, plus `CAH 2.734E-23 PINK 10`

**Challenge:** The full [Krebs Cycle](http://en.wikipedia.org/wiki/Citric_acid_cycle), which produces NADH, a precursor to the very important [ATP](http://en.wikipedia.org/wiki/Adenosine_triphosphate).

Command Text: `0 0 1ACETY-COA 1.34E-21 RED 1H2O 3E-23 BLUE -> 1CITRATE 3.19E-22 ORANGE
0 0 1CITRATE 3.19E-22 ORANGE -> 1H2O 3E-23 BLUE 1CIS-ACONITATE 2.84E-22 YELLOW
0 0 1CIS-ACONITATE 2.84E-22 YELLOW 1H2O 3E-23 BLUE -> 1ISOCITRATE 3.19E-22 GREEN
0 0 1ISOCITRATE 3.19E-22 GREEN 1NAD 1.10E-21 LIGHTGRAY -> 1A-K-GLUTARATE 2.42E-22 CYAN 1NADH 1.10E-21 GRAY
0 0 1A-K-GLUTARATE 2.42E-22 CYAN 1NAD 1.10E-21 LIGHTGRAY -> 1SUCCINYL-COA 1.44E-21 PINK 1NADH 1.10E-21 GRAY
0 0 1SUCCINYL-COA 1.44E-21 PINK 1H2O 3E-23 BLUE 1GDP 7.35E-22 DEFAULT -> 1GTP 8.68E-22 DEFAULT 1SUCCINATE 1.96E-22 DEFAULT
0 0 1SUCCINATE 1.96E-22 DEFAULT 1FAD 1.3E-21 DEFAULT -> 1FUMARATE 1.93E-22 DEFAULT
0 0 1FUMARATE 1.93E-22 DEFAULT 1H2O 3E-23 BLUE -> 1MALATE 2.23E-22 DEFAULT
0 0 1MALATE 2.23E-22 DEFAULT 1NAD 1.10E-21 LIGHTGRAY -> 1NADH 1.10E-21 GRAY 1OXALOACETATE 2.19E-22 DEFAULT
0 0 1OXALOACETATE 2.19E-22 DEFAULT -> 1ACETY-COA 1.34E-21 RED`

![Challenge](/pictures/challenge.png)
