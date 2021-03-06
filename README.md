# FileDragger
Monitoring files and dirs in a dir from server and dragging them to client.

Download files and dirs in a designated dir in server automatically and periodically. After downloading files, all downloaded files will be deleted, and empty dirs will be also deleted after those files are deleted.

# Install
    g++ -std=c++11 ../server/*.cpp -o FileDraggerServer -lgflags -lglog -levent  -lthrift -lboost_system -lboost_filesystem -lboost_thread

# Usage
Run command in a dir, and all files and dirs will be downloaded to this dir.

Client: 

    command ip port time_interval_hour time_wait_to_download_minute chunk_size
    ip: server ip
    port: server port
    time_interval_hour: how many hours to wait to require downloading
    time_wait_to_download_minute: how many minutes to wait to download files after request
    chunk_size: how many files to be downloaded at a time
    
Run command in a dir, and all files and dirs in this dir will be dragged by client.

Server: 

    command port
    port: server port
    
Tips: This executable file should not be in the same dir with files to be dragged, otherwise it would be uploaded and removed with other files.

# Dependences:
Boost_1.59.0, gflags.2.1.2.1, glog.0.3.3.0, libevent_vc120.2.1.4.0, openssl_vc120.1.0.1.800, thrift-0.9.3.
