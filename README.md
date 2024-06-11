# boxhole

boxhole lets you use YouTube as a Infinite Cloud Storage. It embeds any files(Images, Videos, Documents, etc) into a video. The video can be uploaded to YouTube and the file can be retrieved from the video. A expansion & compression technique is used to defeat YouTube's compression algorithm. The file can be retrieved from the video without any loss of data.

## How to Use? ✅

Wait for the app to start.

### Create video from files

- Copy all your files into ```\data\input``` directory
- Select ```Encode file to video``` option on the app
- Wait for the process to complete
- <b>Generated video (```op.mp4```)</b> & <b>Metadata (```metadata.json```)</b> will be available in ```\data\generated``` directory
- Upload the video to <b>YouTube</b> and copy-paste the contents of ```metadata.json``` in <b>description</b> of the video
- Make sure the uploaded video is ```public``` / ```unlisted```

### Retrieve files from video

- Select ```Decode file from video``` option on the app
- Enter the youtube video url (Make sure the uploaded video is ```public``` / ```unlisted```)
- Wait for the process to complete
- The files will be available in ```\data\retrieved``` directory

### Cleaning up

- Select ```Clean``` option on the app to clean data directory

### Reload Time

- Select ```Reload time``` option to set the time to wait before reloading the app

### Exit

- Select ```Exit``` option on the app to exit

## Use Dockerized CLI App ✅ ✅

You just need to have ```Docker``` installed on your system.

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

```console
docker cp <host_path> <container_id>:app/data/input
```

### Copy Output Files from Container to Host

The video and metadata files can be copied from container to host using the following command.

```console
docker cp <container_id>:app/data/generated <host_path>
```

### Copy Retrieved Files from Container to Host

The retrieved files can be copied from container to host using the following command.

```console
docker cp <container_id>:app/data/retrieved <host_path>
```

## DataProcessing Working

### Embed File Into Video

<img src="https://tomato-semantic-alligator-932.mypinata.cloud/ipfs/QmNx7xX1pn3ngduQU5n9GKC8NwfH7GRQXfGB4mFuxphtqa">

### Retrieve File From Video

<img src="https://tomato-semantic-alligator-932.mypinata.cloud/ipfs/QmUMXUJZ11mgpp8oEmGPeTenK4669uwJesUVJmK1UDQwvV">

## Expansion And Compression

<img src="https://tomato-semantic-alligator-932.mypinata.cloud/ipfs/Qma8CRjSV7Azkp3uMfda1aWDNHGNQgy1haC6fcuuWHMJ8Y">

## Python Wrapped C++ Library

boxhole was a complete Python Implementation. Beign a very slow interpreted language it was taking too much time to process files. Later I moved some heavy task codebase to C++ and wrapped those in Python using [ctypes](https://docs.python.org/3/library/ctypes.html). This helped to process the files ~3x faster.

## Features

- Parallel Processing using multiple CPU cores is supported now.
- C++ Library is used for heavy tasks to make the process faster.

## Credits

This project is inspired by [Infinite-Storage-Glitch](https://github.com/DvorakDwarf/Infinite-Storage-Glitch) which is a Rust implementation. I liked the concept and tried to implement in my favourite language Python. The working of both may not be same.
