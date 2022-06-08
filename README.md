=======================================================================
# VIVIDHA Installer
=======================================================================


## VIVIDHA: Variant Analysis & Visualization Interface for Dynamic High-Throughput Application


The advent of high throughput sequencing technologies resulted in an explosive growth of sequencing data, which mandates availability of faster and more efficient data analysis tools.
Variant calling is a key link in the NGS data analysis workflow. The quality of call sets directly affects downstream analysis such as disease-causing gene detection.Joint variant calling is highly relevant in the present scenario of large cohort studies being taken up for genotype-phenotype associations and are of great importance for personalised genomics and precision medicine.
The objective of the present work is to develop a computational methodology using high performance compute clusters for variant calling of multiple samples at a single instance.
With the increasing size of datasets, there is a dire need to develop scalable and cost-effective methodologies for variant calling.
To address this issue, we propose a methodology based on distribution of mapped files (BAM/SAM) into several overlapping chunks to enable fast computation without compromising on the quality of the called variants.Several callers have been employed on the sample dataset and a consensus strategy is used to arrive at the 'optimal set of variants'.
This methodology would enable variant discovery in low coverage data and reduce the overall 'False Discovery Rate'.
The methodology has been developed using map-reduce on Hadoop. The data is stored in a distributed manner using HDFS.

## Key Features:
 - With the increasing size of datasets, there is a dire need to develop scalable and cost-effective methodologies for variant calling
 - VIVIDHA is based on distribution of mapped files (BAM/SAM) into several overlapping chunks to enable fast computation without compromising on the quality of the called variants
 - Several callers have been employed on the sample dataset and a consensus strategy is used to arrive at the 'optimal set of variants'
 - VIVIDHA enables variant discovery in low coverage data and reduce the overall 'False Discovery Rate'
 - VIVIDHA has been developed using map-reduce on Hadoop wherein data is stored in a distributed manner using HDFS

## Vividha Methodology 

		                                                                                                                                                         |---------------------------------------------------------------|
		|								|
		|			Interface				|
		-----------------------------------------------------------------
					     |
					     |
		-----------------------------------------------------------------
                |		Tools of Vividha Application     		|
                |        	   VarScan,BCFtools,GATK			|
	 	|								|
		-----------------------------------------------------------------
					     |
					     |
                -----------------------------------------------------------------
		|		Hadoop Cluster Nodes			  	|
		|								|
		-----------------------------------------------------------------




## Sample Input Data

Sample Input data is provided here.

## Link for the sample input data and Reference files. To download Click here

**InputBamFile : **
	https://drive.google.com/drive/folders/1Cp5as_3HYLMzSPENuG34tlPPAum_KHug?usp=sharing
Reference Files : 
	https://drive.google.com/drive/folders/1Jjf5s9lcr_lgzOx1jAz9zIYUX4L-NrXj?usp=sharing

## Usage

Using the deployed WAR and Jar file, the tool can be as web client over the internet and executed on hadoop environment. Upload the genomics file over the hadoop environment.
Following is the way to install and execute it.

# Installation

# VIVIDHA Installer

## PreRequisite :
            Hadoop Installation
            Visualization-
			apt install tabix

                        R Installation (Version >3.0)
			Note : Location for R should be < /usr/bin/R >

                        library(shiny)
                        library(ggplot2)
                        library(vcfR)
                        library(pinfsc50)
                        library(reshape2)
                        library(ggplot2)
                        library(gganimate)
                        library(gapminder)
			
			JAVA 1.8
                        
                        Copy reference file and gff(annotation file) in demo_htvam/FinalVcf location
                        
            Tools Intsallation requirement -
                         GATK
                         Varscan
                         BCF
                         
                         Specify installation location in application.properties file

## Step 1:     Start Hadoop
               start all the hadoop deamons (start-all.sh)
               
## Step 2:     Tools Installation (Optional)

## Step 3:     Update Tools path and Hadoop Configuration in application.properties file

                Path for application.properties - /home/<username>/demo_htvam/conf/application.properties
  
                BCF=/home/<username>/demo_htvam/tools/bcftools-1.9
                SAMTOOL=/home/<username>/demo_htvam/tools/samtools-1.8
                GATK= /home/<username>/gatk-4.beta.6
                HADOOP=/demo_htvam/tools/hadoop-3.0.1
                R=/demo_htvam/R

## Step 4:       Copy/ Put Sample files in Hadoop HDFS File system

                /htvam/users/<username>/InputBamFile/<sample files>
                /htvam/users/<username>/SplittedInputFiles
                /htvam/users/<username>/referenceFile/<sample files>

                Commands For reference

                Sample input File copy to HDFS -     
                hadoop fs -put /demo_htvam/InputBamFile/* /htvam/users/<username>/InputBamFile

                Sample splitted input Files copy to HDFS -     
                hadoop fs -put /home/<username>/demo_htvam/SplitedInputFiles/*.bam /htvam/users/<username>/SplitedInputFiles/"+ "\n"

                Sample reference files copy to HDFS -  
                hadoop fs -put /demo_htvam/referenceFile/* /htvam/users/<username>/referenceFile
               
## Step 5:      Download VIVIDHA Installer (Contains Wildfly Server and sample input BAM and reference files) 
                        https://drive.google.com/file/d/13NL_tBlvfFG1zvGhrjqJIYGBBlHVSI7M/view?usp=sharing

## Step 6:      Run VIVIDHA Intsaller

                java -jar VividhaInstaller-jar-with-dependencies.jar
		
		OR
		Run with sudo privilege - 
		
		sudo sh vivdha.sh

## Get Started
 Default Portal Access URL :
 http://<Application server>:8080/vividha

By default hdpuser user is created for ADMIN module (password hdpuser). Change the password once logged in and create appropriate users for vividha module.
User can log in to the application via web portal using his /her credentials approved by hdp user.
Appropriate input files should be used with respective scripts by user to run the job as mentioned above from step 1 to 5.


## **Note** : 
	gff file is required to visualize the vcf file.
	
