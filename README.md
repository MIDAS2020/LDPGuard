# LDPGuard

This is our implementation for the paper:

LDPGuard: Defenses against Data Poisoning Attacks to Local Differential Privacy Protocols

LDPGuard is implemented with Python 3.10 (JDK1.8).

# Environments

Python 3.10

Pycharm

# Dataset

AIDS antiviral dataset https://wiki.nci.nih.gov/display/NCIDTPdata/AIDS+Antiviral+Screen+Data

PubChem dataset ftp://ftp.ncbi.nlm.nih.gov/pubchem/Compound/CURRENT-Full/SDF/

eMolecule dataset https://www.emolecules.com/info/plus/download-database

# Example to run the codes
We first illustrate how to run TED with an exapmle. Then, examples of its variants (BASE, DSS, PRM, and TEDLite, see Section 7.1) are presented.

Let the dataset be AIDS40K, inputfile "AIDS40k", outputfile "AIDS40k_result.txt".

TED
Step 1: Parameter Setting in main/Arguments.java.

    1） hyperparameter setting. 
    
         inFilePath  =  "AIDS40k";  outFilePath =  "AIDS40k_result.txt"; minSup  =  1;  swapcondition  = "swap1"; maxNodeNum = 11;
         
         numberofpatterns = 5;      numberofgraphs   = 40000;  isPESIndex  = true;
         
    2)  parameter setting for optimization strategies
    
         Since all optimization strategies are used by TED,  we set hasPRM = true;  hasDSS = true;  hasInitialPatternGenerator  = true
         
         In addition, we set isLightVersion = false.
Step 2: Run the main class, main/TEDSMain.java. The results can be found in the outputfile.

TED's variants
Step 1: Unless specified otherwise, the parameter settings are the same as above.

     1) PRM:  Set hasInitialPatternGenerator  = false; 2) DSS:  Set hasInitialPatternGenerator  = false and hasPRM = false; 
     
     3) BASE: Set hasInitialPatternGenerator  = false, hasPRM = false, and hasDSS = false;
     
     4) TEDLite:  Set isLightVersion = true.
Step 2: Run the main class, main/TEDSMain.java. The results can be found in the outputfile.
