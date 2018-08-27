# MovieRecommenderSystem

This movie recommender use User-based Collaborative Filtering algorithm to find similar films.
Implement a recommender algorithm -- Item Collaborative Filtering ( Item CF ), with Mapper-reducer

## Features

- Build rating matrix and co-occurence matrix, multiplied these two matrix computation to generate recommender list
- Implemented 4 Map-Reduce jobs to finish the algorithm Item Collaborative Filter(Item CF)

## Setting up development environment

This program is build with maven, and could run it on Hadoop. Use Docker would simplify the environment setting

- Setup Docker
- Setup Hadoop on a Docker image
- Build the Mapper-Reducer jobs with IDE like Intellij
- Run jobs on Hadoop

### How to run:
- cd RecommenderSystem <br> 
- hdfs dfs -mkdir /input <br> 
- hdfs dfs -put input/* /input  <br> 
- hdfs dfs -rm -r /dataDividedByUser <br> 
- hdfs dfs -rm -r /coOccurrenceMatrix <br> 
- hdfs dfs -rm -r /Normalize <br> 
- hdfs dfs -rm -r /Multiplication <br> 
- hdfs dfs -rm -r /Sum <br> 
- cd src/main/java/ <br> 
- hadoop com.sun.tools.javac.Main *.java <br> 
- jar cf recommender.jar *.class <br> 
- hadoop jar recommender.jar Driver /input /dataDividedByUser /coOccurrenceMatrix /Normalize /Multiplication /Sum <br> 
- hdfs dfs -cat /Sum/*  <br>
- #args0: original dataset <br>
- #args1: output directory for DividerByUser job <br>
- #args2: output directory for coOccurrenceMatrixBuilder job <br>
- #args3: output directory for Normalize job <br>
- #args4: output directory for Multiplication job <br>
- #args5: output directory for Sum job <br>

