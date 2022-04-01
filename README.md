# Data-Warehouse--Redshift

A music streaming startup has grown their user base and song database. They wanted to move their processes and data onto the cloud. Their data resides in S3, in a directory of JSON logs on user activity on the app, as well as a directory with JSON metadata on the songs in their app.
<br>
I've built an ETL pipeline that extracts their data from S3, stages it in Redshift, and transforms data into a set of dimensional tables for their analytics team to continue finding the insights.

## Datasets that reside in S3:
* <b>Song data:</b> s3://udacity-dend/song_data 
* <b>Log data:</b> s3://udacity-dend/log_data <br>
(Log data json path: s3://udacity-dend/log_json_path.json)
<hr>

### Song Dataset
The first dataset is a subset of real data from the Million Song Dataset. Each file is in JSON format and contains metadata about a song and the artist of that song. The files are partitioned by the first three letters of each song's track ID. For example, here are filepaths to two files in this dataset:<br>
song_data/A/B/C/TRABCEI128F424C983.json <br>
song_data/A/A/B/TRAABJL12903CDCF1A.json <br>
And below is an example of what a single song file, TRAABJL12903CDCF1A.json, looks like. <br>
`{"num_songs": 1, "artist_id": "ARJIE2Y1187B994AB7", "artist_latitude": null, "artist_longitude": null, "artist_location": "", "artist_name": "Line Renaud", "song_id": "SOUPIRU12A6D4FA1E1", "title": "Der Kleine Dompfaff", "duration": 152.92036, "year": 0}`
<hr>

### Log Dataset
The second dataset consists of log files in JSON format generated by this event simulator based on the songs in the dataset above. These simulate app activity logs from an imaginary music streaming app based on configuration settings.
<br>
The log files in the dataset you'll be working with are partitioned by year and month. Here are filepaths to two files in this dataset:<br>
log_data/2018/11/2018-11-12-events.json<br>
log_data/2018/11/2018-11-13-events.json<br>
And below is an example of what the data in a log file, 2018-11-12-events.json, looks like.
![image](images/log_data.png)

