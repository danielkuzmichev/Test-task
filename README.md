# Sber test-task 

На планете с бесконечной поверхностью стоит робот. 

Пусть он стоит в своей первоначальной точке (0, 0) и смотрит на север. Заметим, что:

Направление на север находится на положительной оси Y

Направление на юг находится на отрицательной оси Y

Направление на восток на положительной оси X

На запад на отрицательной ее части.

Робот может получать на вход одну из трех команд:

 

"G": идти вперед на 1 клетку/деление.

"L": повернуться на 90 градусов влево (в направлении против часовой стрелки)

"R": повернуться на 90 градусов вправо 

 

Робот исполняет команды данные ему в по порядку и повторяет их бесконечно.

 

Верните true тогда и только тогда, когда существует замкнутая траектория пути робота, которую можно повторять бесконечно. При этом робот не покидает границ данной замкнутой траектории.

 

Дополнительные требования со звездочкой* (за корректную реализацию каждого из них отдельный +):


1) (почти обязательная доп задачка) код логики должен быть покрыт unit тестами

2) программа должна быть реализована с использованием фреймворка Spring.

Для взаимодействия с пользователем при этом использовать REST API, реализовав REST-сервис 

POST { }   /robot/reset   -  сбрасывает текущее положение робота в (0, 0)
POST { commang: "G" }  /robot/command  - отправляет роботу на исполнение одну команду
GET /robot/position - вернуть json с текущим положением робота
GET /robot/route - вернуть json с описанием текущего пройденного маршрута робота, а также circular: true/false по вопросу исходной задачи:

{
     route: { {0, 0}, {0, 1}, {0, 2}, {0, 1}, {0, 0} },
     circular: true
}    
3) хранить текущий маршрут робота и историю выполнения его команд в базе, т.е. персистить текущее состояние программы (требований по субд нет, используйте ту, которая быстрее всего у вас может быть развернута, либо базы в духе sqlite - не важно)
