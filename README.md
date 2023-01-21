<p align="center">
<img src="https://user-images.githubusercontent.com/263321/180779012-f2cad23b-0e27-4b78-a2e6-00426cf38e5f.png" alt="Quantum Banner">
</p>

![Python](https://img.shields.io/badge/python-3670A0?style=for-the-badge&logo=python&logoColor=ffdd54)

# Uniform Random Sampling of Configuration Spaces using Grover's Algorithm

Repository containing data and code for Q-SE 2023 submission 9292: Can Quantum Computing Improve Uniform Random Sampling of Large Configuration Spaces?

A [Jupyer Notebook](configproblem/SolvingSATWithGrover.ipynb) is available that contains our sampling method alongside detailed explanations and examples.

The accompanying [Python File](configproblem/SolvingSATWithGrover.py) was used to evaluate our method using the commandline tool [cnfinfo](configproblem/cnfinfo.py), which also gathers additional data about the feature models.

## Requirements

Anaconda virtual environment with the [requirements](requirements.txt) of this repository installed via `pip`.

To use the `cnfinfo` tool, in particular model counting, the operating system needs to be x86 Linux.
Further, [GANAK](https://github.com/meelgroup/ganak) is assumed to be available through the system PATH.
For approximate model counting the `pyapproxmc` wheel also needs to be installed via `pip`.

Keep in mind that simulating quantum circuits requires a lot of system RAM!

## Usage

1. Navigate to the root of this repository inside a terminal.
2. Load your anaconda virtual environment `conda activate <your_venv_name>`.

### Notebook

3. Run the `jupyter notebook` command. A web browser will open.
4. In the browser, navigate to `configproblem` and then open the `SolvingSATWithGrover` notebook.


### cnfinfo tool

3. Run `python configproblem/cnfinfo.py <your_cnf_file>` to get data about an individual cnf file.

You can also pass in folders that will be recursively walked to analyze all cnf files found.
See the [code](configproblem/cnfinfo.py#L18) for additional flags that cnfinfo accepts.


A practical example would be to run analysis on the FeatureIDE examples, count model solutions and output as CSV:
```
python configproblem/cnfinfo.py --ssat --csv benchmarks/featureide-examples
```

## Other repositories

Here is a list of tools that we used during our evaluation.

- [FeatureIDE](https://github.com/FeatureIDE/FeatureIDE) for modelling feature models and some example benchmarks.
- [GANAK](https://github.com/meelgroup/ganak) for exact model counting.
- [ApproxMC](https://github.com/meelgroup/approxmc) for approximate model counting.
- [BURST](https://github.com/diverse-project/samplingfm) for their suite of benchmark cnf files.
- [Qiskit](https://github.com/Qiskit) for creating and simulating quantum circuits.