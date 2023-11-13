# Youtube

#### Upload
  - Frontend request to video uploader service for presigned url
  - Uploader service generates and returns presigned url
  - Frontend uploads file to Blob storage / S3 using presigned url
  - When uploading done, frontend acknoledge uploader service
  - Uploader service -> transcoder service
  - Transcoder service gets the file from S3 and transcode the video into different format
  - Uploader service -> metadata service
  - Metadata service stores video metadata to SQL database

#### Search

#### Stream
  - Frontend request stream to a video to streamer service
  - Streamer service gets metadata from metadata service
  - Streamer service generates presigned url and returns to frontend
  - Frontend stream the video using presigned url from CDN / S3

#### Source
  - https://www.youtube.com/watch?v=WlMTxHcm4Qs&ab_channel=ByteMonk




![image](https://github.com/SbrTa/Notes/assets/8649145/9275b49c-c12e-4f45-903b-37886f3a2561)

![image](https://github.com/SbrTa/Notes/assets/8649145/f5493c4a-27d3-4c21-8c64-bf3fe5df8ece)

![image](https://github.com/SbrTa/Notes/assets/8649145/76b91a7f-efff-4798-aaa2-70041336f5f8)
