<h1 align="center">HeyGenClone</h1>

<p>
  Welcome to <strong>HeyGenClone</strong>, an open-source analogue of the HeyGen system.
</p>

<p>
  I am a developer from Moscow 🇷🇺 who devotes his free time to studying new technologies. The project is in an active development phase, but I hope it will help you achieve your goals!
</p>

<p align="center">
  <img src="https://i.ibb.co/9H4f46J/logo.png" width="30%" height="auto" />
</p>

## Installation
- Clone this repo
- Install requirements:
  ```
  pip install -r requirements.txt
  ```
- In config.json file change HF_TOKEN argument. It is your HuggingFace token. Visit [speaker-diarization](https://hf.co/pyannote/speaker-diarization), [segmentation](https://hf.co/pyannote/segmentation) and accept user conditions
- Download weights from [drive](https://drive.google.com/file/d/1e35OvOlWVNndkx0Gv7zc5emwnX7t3Oc4/view?usp=sharing), unzip downloaded file into <strong>weights</strong> folder
- Install [ffmpeg](https://ffmpeg.org/)

## Usage
At the root of the project there is a translate script that translates the movie you set.
```
python translate.py video_filename output_language -o output_filename
```

## How it works
1. Detecting scenes ([PySceneDetect](https://github.com/Breakthrough/PySceneDetect))
2. Face detection ([yolov8-face](https://github.com/akanametov/yolov8-face))
3. Reidentification ([deepface](https://github.com/serengil/deepface))
4. Speech enhancement ([MDXNet](https://huggingface.co/freyza/kopirekcover/blob/main/MDXNet.py))
5. Speakers transcriptions and diarization ([whisperX](https://github.com/m-bain/whisperX))
6. Text translation ([googletrans](https://pypi.org/project/googletrans/))
7. Voice cloning ([TTS](https://github.com/coqui-ai/TTS))
8. Lip sync ([lipsync](https://github.com/mowshon/lipsync))
9. [Need to fix] Search for talking faces, determining what this person is saying

## Configurations (config.json)
| Key | Description | Can modify |
|     :---:      |     :---:     |     :---:      |
|     LANGUAGES_URL      |     Url for getting available languages     |     ❌      |
|     DET_TRESH      |     Face detection treshtold [0:1]     |     ✅      |
|     DIST_TRESH      |     Face embeddings distance treshtold [0:1]     |     ✅      |
|     DB_NAME      |     Name of the database for data storage     |     ✅      |
|     HF_TOKEN      |     Your HuggingFace token (see [Installation](https://github.com/BrasD99/HeyGenClone/tree/main#installation))     |     ✅      |

## Conversion results
| Destination language | Source video | Output video |
|     :---:      |     :---:     |     :---:      |
|🇷🇺 (Russian)     | [![Watch the video](https://i.ibb.co/KD2KKnj/en.jpg)](https://youtu.be/eGFLPAQAC2Y)    | [![Watch the video](https://i.ibb.co/cbwCy8F/ru.jpg)](https://youtu.be/L2YTmfIr7aI)    |

## To-Do List
- [ ] Fully GPU support
- [ ] Multithreading support (optimizations)
- [ ] Detecting talking faces (improvement)

## Other
- Tested on macOS
- :warning: The project is under development! :warning:
