# PLM_restraint
Scripts and input data for "Combining Rosetta sequence design with protein language model predictions using Evolutionary Scale modeling (ESM) as restraint".

Provided are the relaxed pdb files of the de novo benchmark and the calculated pssm's in `./input`. Scripts and XML files for FixBB design, LayerDesign, LLM constrained design and PSSM generation can be found in `./scripts/`.

For detailed information on how to compile Rosetta with Tensorflow see the [documentation](https://www.rosettacommons.org/docs/latest/scripting_documentation/RosettaScripts/Movers/movers_pages/trRosettaProtocol#trrosettaprotocol-mover_compilation-requirements).

## Examples
Creating the pssms provided in `./input/` (requires Rosetta compilation with Tensorflow):
```
./scripts/create_pssm.sh inputs/2KL8_beta_relax_0001_fixBB_0211.pdb output_name.pssm
```

Running different design methods:
```
./scripts/design.sh inputs/2KL8_beta_relax_0001_fixBB_0211.pdb
./scripts/layer_design.sh inputs/2KL8_beta_relax_0001_fixBB_0211.pdb
./scripts/favor_design.sh inputs/2KL8_beta_relax_0001_fixBB_0211.pdb inputs/2KL8_beta_relax_0001_fixBB_0211.pssm
``` 

