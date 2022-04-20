<img src="/samples/Odin_squared.png" width="200">

# Odin
### Pose estimation-based tracking and counting of people in videos

## Demo
<img src="/samples/sample_results.gif" width="600">  

[Demo on YouTube](http://www.youtube.com/watch?v=5lSUhCjgD7g)  
[Paper Abstract](https://github.com/PJunhyuk/people-counting-pose/blob/master/samples/Pose%20estimation-based%20tracking%20and%20counting%20of%20people%20in%20videos.pdf)

## Usage

ВАЖНО: Данное пособие составлено для Windows 10 с включенной возсожностью виртуализации.
### Установка Docker Destop
1.* Перейдите по ссылке и скачайте Docker Desktop, после чего проследуйте инструкции установки и запустите программу (пропустите туториал)
	1.1 https://desktop.docker.com/win/main/amd64/Docker%20Desktop%20Installer.exe?utm_source=docker&utm_medium=webreferral&utm_campaign=dd-smartbutton&utm_location=module
### Скачивание образа докера
2. Нажать сочетание клавиш Win+R, ввести cmd и нажать 'ОК',Выполнить команду docker pull jgravity/tensorflow-opencv:odin
### Подготовка репозитория с выводом
3.** Создать папку для вывода видеофайла. (Если вы хотите запустить программу на своем видео, необходимо разместить его в этой папке.

### Работа с Docker
4. Открыть Docker Desktop
5. Перейти во вкладку Images и у строки jgravity/tensorflow-opencv нажать кнопку Run.

### Настройка и создание контейнера
6. В открывшемся окне развернуть Optional Settings. 
```
	6.1 В поле Host Path вставить абсолютный путь до папки, которую вы создали в формате < C:\Something\Something\TargetFolder >. 
	6.2 В поле Container path вставить < /test >.
   	6.3 Нажать кнпоку Run.
	6.4 Назовите контейнер Test_1 (к примеру)
```
### Работа с контейнером
7. Во вкладке Containers / Apps, на открывшемся контейнере Test нажать кнпоку CLI
#### Запуск на тестовом видео (тест работоспособности)
8. В открывшейся командной строке поочередно выполнить следующие команды - 
```
	8.1 git clone https://github.com/DrXlor/people-counting-pose
	8.2 cd people-counting-pose
	8.3 chmod u+x ./compile.sh && ./compile.sh && cd models/coco && chmod u+x download_models_wget.sh && ./download_models_wget.sh && cd -
	8.5 python video_pose_test.py'
	8.6 mv testset/people_pose.mp4 ../test
```
### Запуск на вашем видео
9. В открывшейся командной строке поочередно выполнить следующие команды - 
```
	9.1 git clone https://github.com/DrXlor/people-counting-pose
	9.2 cd people-counting-pose
	9.3 chmod u+x ./compile.sh && ./compile.sh && cd models/coco && chmod u+x download_models_wget.sh && ./download_models_wget.sh && cd -
	9.4 mv ../test/YOUR_VIDE_NAME.mp4 testset
	9.5*** python video_tracking.py -f 'YOUR_VIDE_NAME.mp4'
	9.6 mv testset/people_tracking.mp4 ../test
```
###
10. В созданной ранее папке вы найдете видео под названием people_tracking.mp4 , которое будет результатом работы программы.

### Примечания:
	* Если данное ПО уже есть у вас, данный шаг можно пропустить.
	** Можно использовать любой видеофайл на ваш выбор, достпные форматы - .MOV, .MP4 
	*** Для получения ТОЛЬКО позы людей на видео, используйте команду - python video_pose.py -f 'people.mp4' 


## Reference

### Test dataset
- testset/test_video_01: [Pedestrian overpass - original video (sample) - BriefCam Syndex](https://www.youtube.com/watch?v=aUdKzb4LGJI)
- testset/test_video_02: [Pedestrian Walking and Traffic Exit,Human Activity Recognition Video ,DataSet By UET Peshawar](https://www.youtube.com/watch?v=eZRLm7KK8HA)

### Citation
    @inproceedings{insafutdinov2017cvpr,
	    title = {ArtTrack: Articulated Multi-person Tracking in the Wild},
	    booktitle = {CVPR'17},
	    url = {http://arxiv.org/abs/1612.01465},
	    author = {Eldar Insafutdinov and Mykhaylo Andriluka and Leonid Pishchulin and Siyu Tang and Evgeny Levinkov and Bjoern Andres and Bernt Schiele}
    }

    @article{insafutdinov2016eccv,
        title = {DeeperCut: A Deeper, Stronger, and Faster Multi-Person Pose Estimation Model},
	    booktitle = {ECCV'16},
        url = {http://arxiv.org/abs/1605.03170},
        author = {Eldar Insafutdinov and Leonid Pishchulin and Bjoern Andres and Mykhaylo Andriluka and Bernt Schiele}
    }

### Code
[pose-tensorflow](https://github.com/eldar/pose-tensorflow) - Human Pose estimation with TensorFlow framework  
[object-tracker](https://github.com/bikz05/object-tracker) - Object Tracker written in Python using dlib and OpenCV

## LICENCE
[Apache License 2.0](https://github.com/PJunhyuk/people-counting-pose/blob/master/LICENSE)
