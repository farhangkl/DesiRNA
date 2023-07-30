# 2DesignRNA
DesiRNA is a structure-based design of RNA sequences with a Monte Carlo approach. DesiRNA accurately design seqeuness for a given target secondary structures including psudonknots and multichains.


# Requirements
## 1- **Python** >= 3.7
## 2- **RNA**>=2.6.0
   - Description: `RNA` is a library for secondary structure prediction and analysis of RNA sequences. It provides algorithms for RNA folding, energy calculations, and more.
    `pip install RNA`
    - Official Documentation: [RNA - ViennaRNA Package](https://www.tbi.univie.ac.at/RNA/)
## 2- **numpy**>=1.24.4:
   - Description: `numpy` is a powerful library for numerical computing in Python. It provides support for large, multi-dimensional arrays and matrices, along with a vast collection of mathematical functions.
   `pip install numpy`
   - Official Website: [NumPy](https://numpy.org/)
3. **pandas**>=1.1.3:
    - Description: `pandas` is a popular library for data manipulation and analysis in Python. It provides data structures like DataFrames, which are highly efficient for handling structured data.
    `pip install pandas`
    - Official Website: [pandas](https://pandas.pydata.org/)
# Usage
DesiRNA is excutable in a commandline enviroment and iis excutable in both Wndows and bash enviroment.
```bash
python 2DesignRNA.py <-f filename> [options]
```
Here is a detailed explanation of each argument:

- `-f`, `--filename`: **(Required)** The name of the input file containing secondary structures and constraints. This file should be in the correct format for the program to interpret the secondary structures and constraints correctly.

- `-R`, `--replicas`: **(Optional, default = 10)** The number of replicas to create for the simulation. Increasing this number will likely result in a more diverse set of RNA sequences, but may increase computation time.

- `-e`, `--exchange`: **(Optional, default = 10)** The number of accepted exchanges for Metropolis Monte Carlo simulation. Increasing this number will likely result in a more diverse set of RNA sequences, but may increase computation time.

- `-t`, `--timelimit`: **(Optional, default = 60)** The time limit for running the program, in seconds. Increase this to allow the program more time to find optimal solutions.

- `-n`, `--number_of_sequences`: **(Optional, default = 10)** The number of best sequences that the program should return. Increasing this number will yield a greater number of resultant sequences, but may increase computation time.

- `-acgu`, `--ACGU`: **(Optional, default = 'off')** This option enables or disables the ACGU constraints in the sequence design.

- `-pk`, `--PK`: **(Optional, default = 'off')** This option enables or disables pseudoknots in the sequence design.

- `-l`, `--lambda`: **(Optional, default = 1000)** This option sets the temperature factor for the Metropolis criterion used in the Monte Carlo simulation.

- `-o`, `--oligomerization`: **(Optional, default = 'off')** This option enables or disables oligomerization in the sequence design.

- `-d`, `--dimer`: **(Optional, default = 'off')** This option enables or disables dimerization in the sequence design.

- `-p`, `--param`: **(Optional, default = '2004')** This option allows you to choose the energy parameter model. The default model is the Turner 2004 model. The '1999' option allows you to use the Turner 1999 model.

- `-sf`, `--scoring_function`: **(Optional, default = 'dmt')** This option allows you to choose the scoring function for the sequence design. The default is 'dmt'. Other options include 'mcc', 'mfe', and 'mix'.

To use the program with specific options, include the corresponding arguments in your command. For example, to execute the program with 20 replicas, your command would look like this:

## Example
```bash
python 2DesignRNA.py -f yourfile -R 20
```

Replace `yourfile` with the path to your input file and `20` with the number of replicas you want to use. If your file path contains spaces, please enclose it in quotation marks.

Remember, the more precise the input parameters, the more accurate the resulting RNA sequence designs will be.

## Sample of input file structure
```
>name
1c2x
>sec_struct
((((((((.(.....((.(((.(.......((((.............))))........).)))..)).((.......((((((((...)))))))).......))...).)))))))).
>seq_restr
NNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNN
```
## Sample of genearted output for 10 designed sequences
GCUGGUACGAGUCUGCUCGGAGGUUCCUAUUGCCUACGAAACGGCACGGCAUCAAGACUCAUCCUUAGUUCACCCGACGGCCGCAUCUUAUGCGGCCACCACCGGAAGCUGGUACCAGCC
CAAUCCCUUCGUUGUCCCCUAUACCCAGUUACCAUCUUGUGACCCAUUGGUUUCGAGCUUGUAGGCGGCCUCCGAGUUCGGCUCCCACAGGGAGCCGCGACGCCAGCAUGUAGGGAUUGC
CACUACACUUAGUGGUAAGCAAAUCCACCAUUCUAGAACGGAACCACAGAAUCCGCAAAUAUGCGCUAACGUUCAUGGUGACAACUCUCAGUUGUCAAACAUCCCGUUUAGGUGUAGUGA
GCAUGAGAGGACGAUGCUCCCGGCAAUGCACCUUUGAGUUAUAAGCCAAGGGGUCUAGCCAGGGGGGCUGCUUGAUCUCCGGCCACUGAGUGGCCGGGUGAUGCGCGCACGUCUCAUGCA
AGAUGUCAAUAGUCGCGAUCGUGAUCUCCGUACGUGCGAGACUUGGACGUAUACGCUGCCACGAUCCGCGCGGUGUCUACACGCGCCAUGCGCGUGUCCUUUGUGCUGAAAUGACAUCUC
GCACCCUUCUAUGCAUGAGUCCGGGUUUUCGAGGACCAGAACGCUGGCCUCGACUUAGUCCGACGGCAUGCUCUGAGGGCUGGGUGACUCACCCAGCAACUUAAGCGGGAAAAGGGUGCU
CACCCGACUGAUUUAGAGGUAGAUAUCUCCGUCGGGGCGAGCCCAAACGACCAGGAGGCUAUACGUUCACCAGCUCGCUCCUGCAUUUAAUGCAGGAUAGGACGGGUUUCAGUCGGGUGA
CGGGGCGGGAGUUACGCACGCUCAGGGAAGGCUGCGAGAUACUCCGCCAGCUAUCUCAGGGGCGAGGCCAGUAGACUUCACUUGCGUAACGCAAGUGUCAGAGUCUCGAUCCCGCCCCGG
GGUGAUGGUAUGUACGUCGCCUGGCAUUAUACGGACGAGUACGGCGUCCGUCCUGGGCGCAGGCGAACAGAGAGCGUAUUCGGUCGCCACGACCGAAGAUCCCUUCCGCUUCCAUCACCC
GUCCUGGUGGCCACCGUCCCCACGUCACGUUCGCAUGGGUGAAAUAUGCGAGGUAGUAUGCGGGAGACCCGUGUUGGUACCCGCGCUGCGCGCGGGUGUUAAUCCGGCGCUACCAGGACA

