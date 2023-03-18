# Microsoft Text-To-Speech (TTS)

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
