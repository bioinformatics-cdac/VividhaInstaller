=======================================================================
# VIVIDHA Installer
=======================================================================


PreRequisite :
            Hadoop Installation
            R Installation
            Tools Intsallation

# Step 1:     Start Hadoop
            start all the hadoop deamons (start-all.sh)
# Step 2:     Tools Installation (Optional)
# Step 3:     Update Tools path and Hadoop Configuration in /home/<username>/demo_htvam/conf/application.properties
  
                BCF=/home/<username>/demo_htvam/tools/bcftools-1.9
                SAMTOOL=/home/<username>/demo_htvam/tools/samtools-1.8
                GATK= /home/<username>/gatk-4.beta.6
                HADOOP=/demo_htvam/tools/hadoop-3.0.1
                R=/demo_htvam/tools/R

# Step 4:       Copy/ Put Sample files in Hadoop HDFS File system
                /htvam/users/<username>/InputBamFile/<sample files>
                /htvam/users/<username>/SplittedInputFiles
                /htvam/users/<username>/referenceFile/<sample files>

                Commands For eference

                Sample input File copy to HDFS -     
                hadoop fs -put /demo_htvam/InputBamFile/* /htvam/users/<username>/InputBamFile

                Sample splitted input Files copy to HDFS -     
                hadoop fs -put /home/<username>/demo_htvam/SplitedInputFiles/*.bam /htvam/users/<username>/SplitedInputFiles/"+ "\n"

                Sample reference files copy to HDFS -  
                hadoop fs -put /demo_htvam/referenceFile/* /htvam/users/<username>/referenceFile

# Step 5:         Run VIVIDHA Intsaller

                java -jar VividhaInstaller-jar-with-dependencies.jar


### 1. Download VIVIDHA Installer (Contains BCFTools, Samtools, gatk, Wildfly Server and sample input BAM and reference files) 

https://drive.google.com/file/d/1REnayrrQ4Xa1qxYht07t9FVwBOHd5_RJ/view?usp=sharing
