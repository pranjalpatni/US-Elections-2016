# US-Elections-2016
Predicting US Elections from Twitter Feeds by employing a big data solution using NLP and Spark

# JAVA CODE:
- pom.xml can be used to create a Maven project, which will download all the necessary dependencies
- An external jar called "stanford-english-corenlp-2016-01-10-models.jar" needs to be downloaded
- Maven creates a jar called "electionus-jar-with-dependencies.jar"

# How To Execute:
- Run the following command on the terminal:

java -cp "electionus-jar-with-dependencies.jar;stanford-english-corenlp-2016-01-10-models.jar" com.utd.bigdata.electionus.GetTweets

This command would create a file called "tweets.txt" and will continuously keep on appending to it, the new tweets as they arrive.

# Format of "tweets.txt":
This is the format in which the text file gets generated:

"TweetNumber	userName	Tweet	Timestamp	countryName	placeName	geoLocation	sentimentValue"

# SCALA CODE:
- runCode.scala contains the scala code that can be run via the following command:

spark-shell -i runCode.scala --master local[1]

Note: The scala code can also be run with more nodes in local mode or it can also be run in yarn mode

- The runCode.scala creates a file called "merge" in HDFS. Use the bash script, fetchFile.sh, to get the file to localhost and compile the output present in the "merge" folder into a single file called "output.txt", which can be directly used as input to Tableau for graphical representation of the result

- How to run the bash script in terminal:

./fetchFile.sh

Note:
Do not forget to make the script executable by using the following command:

chmod +x fetchFile.sh OR chmod 755 fetchFile.sh
