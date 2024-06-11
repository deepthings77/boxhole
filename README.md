# boxhole

boxhole lets you use YouTube as a Infinite Cloud Storage. It embeds any files(Images, Videos, Documents, etc) into a video. The video can be uploaded to YouTube and the file can be retrieved from the video. A expansion & compression technique is used to defeat YouTube's compression algorithm. The file can be retrieved from the video without any loss of data.

## Use Dockerized CLI App ✅ ✅

You just need to have ```Docker``` installed on your system.
Install Docker on your system and go the directory where files are.

### Build Docker Image

```console
docker build -t boxhole .
```

### Run Docker Container

```console
docker run -it boxhole
```

### Run Dockerized CLI App

```console
./cli_app
```

### Copy Input Files from Host to Container

You can copy files from host to container using the following command. You can copy folders and files.
<host_path> = path of directory of input files to be encoded.
docker ps command to find container ids.

```console
docker ps
```

```console
docker cp <host_path> <container_id>:app/data/input
```

### Copy Output Files from Container to Host

The video and metadata files can be copied from container to host using the following command.
<host_path> = path of directory of output folder.

```console
docker cp <container_id>:app/data/generated <host_path>
```

### Copy Retrieved Files from Container to Host

The retrieved files can be copied from container to host using the following command.
To retrieved Orignal input files after Decoding the youtube URL.
<host_path> = path of directory of output folder.

```console
docker cp <container_id>:app/data/retrieved <host_path>
```

## Python Wrapped C++ Library

boxhole was a complete Python Implementation. Beign a very slow interpreted language it was taking too much time to process files. Later I moved some heavy task codebase to C++ and wrapped those in Python using [ctypes](https://docs.python.org/3/library/ctypes.html). This helped to process the files ~3x faster.

## Features

- Parallel Processing using multiple CPU cores is supported now.
- C++ Library is used for heavy tasks to make the process faster.

## Credits

This project is inspired by [Infinite-Storage-Glitch](https://github.com/DvorakDwarf/Infinite-Storage-Glitch) which is a Rust implementation.
