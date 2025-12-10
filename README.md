# Argumentation-Decision-Framework
A bipolar argumentation-based framework to support technology selection in software architecture.  
The framework models design options as arguments, captures attack and support relations, and applies argumentation semantics to derive explainable and rational architectural decisions.

## Project status
This is an ongoing project whose aim is to model software design choices with argumentation frameworks. It is supported by the PNRR project FAIR –- Future AI Research (PE00000013), Spoke 9 -- Green-aware AI, under the NRRP MUR program funded by the NextGenerationEU. 

## Authors
  - Gianluca Amato (gianluca.amato@unich.it)
  - Fabio Fioravanti
  - Maria Chiara Meo
  - Francesca Scozzari

## Repository structure
Files with extension `.af` are argumentation frameworks. For some of them, the files with same name and extension `.txt` show the correspoing results.

## How to run the model

1. Download [DLV](https://www.dlvsystem.it/dlvsite/dlv-download/) (an implementation of disjunctive Datalog with ASP extensions);
2. Download the file `baf.dl` from the [ASPARTIX for Bipolar AFs](https://www.dbai.tuwien.ac.at/research/argumentation/aspartix/baf.html) page.  
   *Note:* ASPARTIX is not a single software package, but rather a collection of programs for DLV or Clingo (another ASP implementation) that implement the semantics of argumentation frameworks. Different types of frameworks use different programs, and often even different semantics for the same type of framework require separate programs.
3. Download the file `baf_model.af` (or other similar file) that contains our argumentation framework.
4. Put everything in the same folder, open a terminal window, and run the command:
   
   ```bash
   dlv baf_model.af baf.dl -filter=in
   ```
The `.af` files are configured to compute closed preferred extensions. It is possible to change the `c_prefex` line in those files with one of the following to compute under a different semantics:  
  - `d_adm`, `s_adm`, `c_adm`: Indicate to the system that you want to compute Dung admissible, stable, or closed extensions.
  - `d_prefex`, `s_prefex`, `c_prefex`: As above, but for preferred extensions.
