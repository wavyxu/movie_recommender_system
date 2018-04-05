# MovieRecommenderSystem
Implement a recommender algorithm -- Item Collaborative Filtering ( Item CF )

## How to run:
cd RecommenderSystem <br> 
hdfs dfs -mkdir /input <br> 
hdfs dfs -put input/* /input  <br> 
hdfs dfs -rm -r /dataDividedByUser <br> 
hdfs dfs -rm -r /coOccurrenceMatrix <br> 
hdfs dfs -rm -r /Normalize <br> 
hdfs dfs -rm -r /Multiplication <br> 
hdfs dfs -rm -r /Sum <br> 
cd src/main/java/ <br> 
hadoop com.sun.tools.javac.Main *.java <br> 
jar cf recommender.jar *.class <br> 
hadoop jar recommender.jar Driver /input /dataDividedByUser /coOccurrenceMatrix /Normalize /Multiplication /Sum <br> 
hdfs dfs -cat /Sum/*  <br>
#args0: original dataset <br>
#args1: output directory for DividerByUser job <br>
#args2: output directory for coOccurrenceMatrixBuilder job <br>
#args3: output directory for Normalize job <br>
#args4: output directory for Multiplication job <br>
#args5: output directory for Sum job <br>

