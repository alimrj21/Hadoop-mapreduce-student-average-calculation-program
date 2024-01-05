# Hadoop-mapreduce-student-average-calculation-program
 Hadoop MapReduce program  calculate the average grades of students from a dataset ( text file ) 

the execution commands :

1) sudo groupadd supergroup

2) sudo usermod -aG supergroup hduser

3) sudo /usr/local/hadoop/sbin/./start-all.sh

4) hadoop fs -ls /

5) hadoop fs -mkdir /GradeAnalysisProject

6) export HADOOP_CLASSPATH=$($HADOOP_HOME/bin/hadoop classpath)

7) hadoop fs -put /home/ubuntu22r/student_records.txt /GradeAnalysisProject/

8) hadoop fs -ls /GradeAnalysisProject/

9) javac -classpath $(hadoop classpath) -d GradeAnalysisProject/classes GradeAnalysisProject/src/*.java

10) jar -cvf GradeAnalysis.jar -C GradeAnalysisProject/classes .

remove file (if the file already exists)
hadoop fs -rm /GradeAnalysisProject/student_records.txt

remove directory (if the directory already exists)
hadoop fs -rm -r /input/

11) Create input directory in HDFS
hadoop fs -mkdir /input

12) Upload the dataset to HDFS
hadoop fs -put /home/ubuntu22r/student_records.txt /input/student_records.txt

13) hadoop jar GradeAnalysis.jar GradeAnalysisDriver /input/student_records.txt /output/grade_analysis

14) View the output in HDFS
hadoop fs -cat /output/grade_analysis/part-r-00000




