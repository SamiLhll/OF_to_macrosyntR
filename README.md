# OF_to_macrosyntR
Shell script to post-process OrthoFinder's output into pairwise tables used in macrosyntR 

[![License: GPL v3](https://img.shields.io/badge/License-GPLv3-blue.svg)](https://www.gnu.org/licenses/gpl-3.0)


# Installation :

* download :
```{bash}
 wget https://github.com/SamiLhll/OF_to_macrosyntR/releases/download/V1.0.1/OF_to_macrosyntR.tar.gz
```
* uncompress :
```{bash}
tar -xzf OF_to_macrosyntR.tar.gz
```

(OPTIONAL) you can add an alias to your ~/.bashrc so you can run the script by typing OF_to_macrosyntR in the terminal.   
To do it type the following command, replacing *<path_to_OF_to_macrosyntR.sh>* by the actual path of this file on your machine :

```{bash}
echo "alias OF_to_macrosyntR=\"./<path_to_OF_to_macrosyntR.sh>\"" | tee -a ~/.bashrc
source ~/.bashrc
```


# Usage : 

Run the bashscript in a terminal with the following mandatory arguments :   

-i INPUT_DIR, path to the OrthoFinder's result directory, omitting the last "/ "   
-o OUTPUT_DIR, path where to write the resulting tables, omitting the last "/", default is current dir   

It echoes in the standard output the list of the files that it writes.   

It is recommended to use OrthoFinder with shorter input proteomes (e.g. "Hsap.fa") as it is the header for OrthoFinder's output tables that will also be used to generate the output tables by OF_to_macrosyntR

# Example : 

On an OrthoFinder run that included Cele, Dmel, Hsap and Mmus . 
The script would extract all single copy orthogroups that feature one ortholog in all the species (listed in OrthoFinder's output file Orthogroups/Orthogroups_SingleCopyOrthologues.txt)   
Then it creates the following two columns ortholog tables that can be used separately as input to the Rpackage macrosyntR :   

```{bash}
Cele_vs_Dmel.tab
Cele_vs_Hsap.tab
Cele_vs_Mmus.tab
Dmel_vs_Hsap.tab
Dmel_vs_Mmus.tab
Hsap_vs_Mmus.tab
```
