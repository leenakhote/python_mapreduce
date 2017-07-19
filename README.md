# python_mapreduce
mapreduce task using python 


mapper.py and reducer.py file 
change mode by chmod +x filename

testing 

cat UN.txt | python mapper.py
cat UN.txt | python mapper.py | sort -k1,1 | python reducer.py

put text file to hdfs 
hadoop streaming jar path is imp 

hadoop jar /opt/cloudera/parcels/CDH-5.11.1-1.cdh5.11.1.p0.4/lib/hadoop-mapreduce/hadoop-streaming.jar -file mapper.py reducer.py  -mapper "python mapper.py" -reducer "python reducer.py" -input /user/leenakhote23/UN.txt -output /user/leenakhote23/output

hadoop fs -cat output/part-00000 == to see output 
