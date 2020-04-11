To query the parameter information, please use diffcount --help to get help

The use method is introduced through examples as follows:

1. Difference Statistics

  Count the amount of code changes of a certain version of the code package relative to an original baseline code package
  And the results of the non-empty and non-comment lines (NBNC) in each language in the changed code amount
  
  The default diffcount implementation is difference statistics, just keep up with the directories of the two code packages
  
  Execute in the diffcount directory:
  
     diffcount test \ sp1 test \ sp2
  
  In actual use, there may be a case where the file name and directory name are inconsistent, if you want to ignore
  The file name case difference, you need to use the --ignore-case parameter, otherwise two identical files
  One will count as deletion and one will count as addition
     
G: \ diffcount> diffcount test \ sp1 test \ sp2

Diffcount [test \ sp1] and [test \ sp2] result:

LANG ADD MOD DEL A & M BLK CMT NBNC RATE
-------------------------------------------------- ---------------------
C 44 7 26 51 8 11 35 1.00
Pascal 0 0 25 0 0 0 0 0.23
Java 7 4 11 11 0 3 9 0.41
Config 31 4 0 35 1 0 34 0.12
XML 126 0 0 126 2 0 124 0.12
-------------------------------------------------- ---------------------
  Convert all NBNC lines to standard C
      Total: 57.65 (standard C lines)

The meanings of ADD MOD DEL A & M BLK CMT NBNC RATE are:
Add, modify, delete, add + modify, blank line, comment, non-empty non-comment line, standard C conversion rate
