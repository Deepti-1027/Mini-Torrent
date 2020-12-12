# Mini-Torrent
Developed peer to peer multimedia file sharing network using TCP that allows uploading and downloading file using custom .mtorrent file from multiple available seeders.

### compile project
1. go to client directory
   * ```make```
2. go to tracker directory
   * ```make```
3. To clean solution 
   * ```make clean```
   
#### run the Tracker

```
./tracker <my_tracker_ip>:<my_tracker_port> <other_tracker_ip>:<other_tracker_port>  <seederlist_file>  < tracker_log_file>
```

#### run the Client

```
./client <CLIENT_IP>:<UPLOAD_PORT> <TRACKER_IP_1>:<TRACKER_PORT_1> <TRACKER_IP_2>:<TRACKER_PORT_2> <client_log_file>
```
#### Command/Functionality on Clinent side 
 
 1. **To Share the file over network :** <br/>
 ```
  share <local_file_path> <filename>.<file_extension>.mtorrent
  Eg : share /home/darshan/movie.mp4 movie.mp4.mtorrent.
  ```
 * It will generate .mtorrent file and send data to tracker that I(clinet/seeder) have this file. Now other client/leecher can download this file using .mtorrent file.
  
 2. **To Download the file :** <br/>
 ```
  get <path_to_.mtorrent_file> <destination_path>
  Eg : get movie.mp4.mtorrent newmovie.mp4
  ```
 * It will send request to tracker to know about available seeders and then randomly choose one seeder and make connection with it to get chunk of data. 
  
 3. **Show Downloading status** <br/>
 ```
 show_downloads
 ```
 * It will list out files which are downloading(D), successfully downloaded(S). 
 
4. **To Stop sharing of file over network :** <br/>
 ```
 remove <filename.mtorrent>
 Eg : remove movie.mp4.mtorrent
 ```
 * It will stop sharing of that file over network by removing .mtorrent file and metadata of that file from tracker.

5. **close client :** <br/>
 ```
 close
 ```
 * It will shutdown client and  remove all metadata of files which have been shared by this client from tracker. 

 
   
