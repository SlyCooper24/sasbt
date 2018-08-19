# SASBT 0.1 (READ AS RAW TEXT) 
Software for Automated Search of Biological Targets (SASBT)

Version: 0.1 (BETA)
Authors:
  Software Developer: Vinícius Santos de Pontes
  Researchers: Rafael Nicolay Baptista da Silva, Manuela Leal da Silva 

README file written by: Vinícius Santos de Pontes
Date: 12/08/2018

Tested on:
  Ubuntu 14.04 LTS
  Ubuntu 16.04 LTS
  Ubuntu 18.04 LTS
  
  Probably will run on other Debian based distributions that also have Bash as default command interpreter, but compatibility
  is not assured. We are working to expand the platforms supported list, but please, do not ask us for adding support for any 
  system.
  
Note about user permissions:

  Users are permitted to download and use SASBT for free, but, decompiling, modifiying or charging others to use is not allowed. 
  Infringing these rules or any other of the exclusive copyright will lead to legal actions.      
  
Installing SASBT:

  After downloading SASBT, you will have to execute it once for downloading and installing some other needed software (listed in 
  "Third part software"). Follow these steps:

  1 – Open the terminal in the same folder where SASBT is located;
  2 – Type: chmod 777 SASBT;
  2 – Type: ./SASBT;
  3 – Type your sudo password when asked;
  4 – Wait until the software say that could install everting with success. If the installation was unsuccessfully, read the 
  "Installation error" item.

  After following the steps above, you can move the SASBT executable to /usr/bin in order to be able to execute it without the 
  necessity of moving the software into the same folder where the input files are located. Follow these steps:

  1 – Open the terminal in the same folder where SASBT is located;
  2 – Type: mv SASBT /usr/bin/ or cp SASBT /usr/bin/. The "cp" command is for copying and "mv" for moving.

  Doing so, you will be able to use SASBT just typing SASBT in the terminal anywhere and putting the parameters that are going to 
  be explained in the next item.
  
  Note: Despite showing how to use SASBT with more practicality, we are going to consider in the next items that you have the 
  software executable in the same directory as the input files.   

SASBT parameters:

  In order to know how to use SASBT, you can just type: ./SASBT -h. It is going to open the help page.
  The help page is as follows:
  
  ====
  Syntax example: ./SASBT -f fragments.fasta -r reference.fasta -o result

  Mandatory values:

	  -f --> Used to set the fragments file path.

	  -r --> Used to set the reference file path.

	  -o --> Used to set the output file path.

  Not mandatory:

	  -id --> Used to set the minimum identity percentage that the fragments must have with the reference to be considered. The default value is "50".

	  -c --> Used to set the minimum coverage that the fragments must have with the reference to be considered. The default value is "50".

	  -fid --> Used to set the minimal identity percentage that the assembled sequence must have with its reference in order to be considered valid. The default value is "50".

	  -fs --> Used to set the minimal similarity percentage that the assembled sequence must have with its reference in order to be considered valid. The default value is "50".

	  -fc --> Used to set the minimal coverage percentage that the assembled sequence must have with its reference in order to be considered valid. The default value is "50".

	  -th --> Used to set the number of threads to be used. Still in alpha, there is not significant performance increase.
  ====

Output files:

  SASBT can have up to 3 files as output. The files are:
  
    -output: File containing information about the sequences identified and the values used as cut off (minimum) in each 
    step of the software.
    
    -output.fasta: File containing the sequences assembled by the software in FASTA format.
    
    -output.fails – File containing a list of sequences that could not be identified and some information about why it 
    was not possible.
    
  Consider “output” as the name of the file you settled using “-o”. 

Third part software:

  SASBT downloads and uses the third part software listed here. Note that we do not own any rights over these programs and 
  they should be used under their own user's license. List:
  
  -ClustalO
    Website: http://www.clustal.org/omega/
  -NCBI BLAST+ Package
    Website: https://blast.ncbi.nlm.nih.gov/Blast.cgi?CMD=Web&PAGE_TYPE=BlastHome
  -ABACAS
    Website: http://abacas.sourceforge.net/
  -Bash
    Website: https://www.gnu.org/software/bash/
  
  The versions used by SASBT are always the last disponible on Ubuntu's repositories.
  
Uninstalling:

  To remove just SASBT from your computer, delete the executable and then its folder with "rm -r /home/user/.SASBTFiles". 
  Consider "user" as your username in the system.
  
  If you also want to remove the other software installed by SASBT, you will have to do it manually for each one of them.

  Uninstall NCBI BLAST+ Package:

   sudo apt purge ncbi-blast+

  Uninstall ABACAS:

   sudo apt purge abacas

  Uninstall ClustalO:

   sudo apt purge clustalo
    
  Attention! Bash is the default commands interpreter in many of the GNU/Linux distributions, removing it can result in several
  errors.
  
  Uninstall Bash:
  
   sudo apt purge bash
   
  Note: The above commands need sudo privileges. You will have to put your user password in order to remove them.
  
Installation error:

  The main reasons why you can get an error when trying to install SASBT are:
    
    -You are not connected to the internet or the server is refusing connections to the Ubuntu's repositories.
    -You do not have sudo privileges in the user.
    -You are typing a wrong sudo password.
    -SASBT does not have privileges for creating files on your user home directory.

 
