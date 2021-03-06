# Глава 7 Динамическая реконфигурация

К настоящему времени мы уже достаточно хорошо знакомы с настройкой параметров риска в файлах запуска и считыванием их значений в наших узлах с помощью функции **rospy.get\_param\(\)**. Но возможность изменять параметры ROS на лету часто бывает полезна для настройки и отладки запущенного приложения. В первом томе  мы иногда использовали графический интерфейс ROS **rqt\_reconfigure** для изменения параметров работающего узла. Например, если мы используем камеру Kinect или Xtion Pro, мы можем изменить разрешение камеры, не выключая драйвер, предварительно вызвав графический интерфейс **rqt\_reconfigure** следующим образом:

```text
$ rosrun rqt_reconfigure rqt_reconfigure
```

После небольшой задержки должно появиться окно, похожее на следующее:

![](.gitbook/assets/image%20%284%29.png)

В дополнение к **rqt\_reconfigure**, мы можем также использовать динамическую перенастройку утилит командной строки для изменения параметров. Однако в обоих случаях есть загвоздка: таким образом можно обновить только те узлы,которые были запрограммированы с помощью API динамической реконфигурации.

\(На самом деле, другие узлы даже не появятся в графическом интерфейсе **rqt\_reconfigure**.\) К счастью, большинство узлов в ключевых стеках ROS и пакетах, таких как Navigation, поддерживают динамическую реконфигурацию, но многие сторонние узлы этого не делают и поэтому могут быть изменены только путем редактирования файлов запуска и перезапуска или с помощью инструмента командной строки rosparam с последующим перезапуском узла.

  


