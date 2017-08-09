# Base system is debian
From debian

# Update and install curl bzip2
RUN apt-get update -y && apt-get upgrade -y
RUN apt-get install apt-utils -y
RUN apt-get install curl -y
RUN apt-get install bzip2 -y

# create a new user
RUN useradd teamspeak

# Set the working directory
WORKDIR /home/t3

# Download and install TeamSpeak 3
# z: uncompress the result archive with gzip command
# x: Extract to disk from the archive
# v: Produce verbose output, show progress and file names while extracting files
# f: read the archive from the specified file
RUN curl http://dl.4players.de/ts/releases/3.0.13.6/teamspeak3-server_linux_amd64-3.0.13.6.tar.bz2 > teamspeak-server.tar.bz2
RUN tar -xjvf teamspeak-server.tar.bz2

WORKDIR teamspeak3-server_linux_amd64
USER teamspeak

EXPOSE 9987/UDP
EXPOSE 30033
EXPOSE 10011

ENTRYPOINT ["sh", "ts3server_minimal_runscript.sh"]i
