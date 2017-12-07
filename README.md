# Apache Hadoop MapReduce project

The code has test coverage line number and test function as input shown in Input.txt file.
Then a mapreduce java program maps the input(test function name,line number covered) to (line numbers,test function)So it tells what all lines numbers were covered with the test functions.

Deployed it on Hortonworks Apache hadoop sandbox and got output.
Then deployed it on Amazon EMR and put the jar file and executed by step
https://aws.amazon.com/emr/


How do I get set up?
I have only the gradle file in this project.So that is running. As in homework1 also I had same java file called strman-java-master (3) has strmanTests.jav file.Used itfor test coverage also The code covergae was run for "each" method using Intellij tool as shown in video. Thecode coverage was run for each and every method as dented by filename inside infolder.So I used a junit to execute my test cases and along with that used jacaco text coverage for every method. All output file were converted from html to text and saved in infolder. Then the HadoopMapReduce Project was compiled for it's java file using:javac -cp hadoop classpath TaskLine.java.Then I generated the jar file using jar -cvf TaskLine.jar *.class. Finally in sandbox I just executed the hadoop hadoop jar TaskLine.jar TaskLine /MapReduce/input /Mapreduce/output Note here that the file in infolder need to be uploaded in hdfs format for which I used ambari console. I had created a Manifest file in the jar also called mainmanifest.txt which had Main-Class: TaskLine Then in Amazon EMR as shown in the video I uploaded the file in S3.The argument to the jar will be the input folder containing all the file in infolder.Then the output will consist of one output file having line number followed by comma seperated strings of test names


Create an input directory in HDFS:
# hadoop fs -mkdir mapreduce/input/
STEP 2: Verify that the input directory has been created in the Hadoop file system:
STEP 3: Load the sample.log input file into HDFS:
# hadoop fs -put sample.log /user/root/mapreduce/input/
Note: You are also creating the input directory in this step.
STEP 4: Verify that the sample.log has been loaded into HDFS:
# hadoop fs -ls /user/root/mapreduce/input/
# hadoop fs -ls /user/root/mapreduce/
STEP 5: Run the Hadoop MapReduce job
hadoop jar tutorial1.jar Tutorial1 tutorial1/input/sample.log tutorial1/output


The input file input.txt was used
youtube video:https://youtu.be/ngay5Yr2760
