# Microsoft Text-To-Speech (TTS)

## Install spx in Ubuntu 20.04

```console
wget https://packages.microsoft.com/config/ubuntu/20.04/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
rm packages-microsoft-prod.deb

sudo apt-get update && \
  sudo apt-get install -y dotnet-sdk-6.0
  
sudo apt-get update && \
  sudo apt-get install -y aspnetcore-runtime-6.0
  
dotnet tool install --global Microsoft.CognitiveServices.Speech.CLI
```

## Bootstrap the docker environment
```console
mkdir -p $HOME/spx-data

docker run -it  --entrypoint=/bin/bash -v $HOME/spx-data:/data --rm msftspeech/spx
```

## Configure the speech key and region
```console
spx config @key --set SPEECH-KEY
spx config @region --set SPEECH-REGION
```

## Run it
For example:
```console
spx synthesize --file </path/of/input/file> --voice zh-TW-HsiaoChenNeural --audio output </path/of/output/file>.mp3
```
