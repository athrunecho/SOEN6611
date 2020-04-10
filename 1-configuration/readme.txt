This folder contains the configuration file which we used to collect data
 
1.For data collection work in M1, M2, M4, we're adding jacoco plugin into the pom.xml for each project.
 
Steps:
1)copy paste the content of the "jacoco configuration.txt"
2)run "mvn clean install" or "mvn clean install -Dmaven.test.failure.ignore=true"
3)jacoco report will be generated in target/jacoco-ut folder of the project. 
 
2.For data collection work in M3, we add pit plugin into the pom.xml for each project.
 
Steps:
1)copy paste the content of the "pitest configuration.txt"
2)run "mvn clean test org.pitest:pitest-maven:mutationCoverage" or "mvn clean install -Dverbose=true" or "mvn -Dverbose=true org.pitest:pitest-maven:mutationCoverage"
3)pi test report will be generated in target/pit-reports folder of the project. 
 
3.For data collection work in M5, we used a small program called diffcount to get the DLOC between versions. Before running the program, we will manually delete the non-Java files and the test directory to obtain accurate data. If the file directory structure is different, we will change the structure to make sure files are the same directory.

4.For data collection work in M6, we're rely on issue tracking system of each project, and using some conditions to filter the result. We review the issues of the project GitHub repository and calculate BMI by tracking the number of issues arrived and how many of them closed in the specific version lifetime.