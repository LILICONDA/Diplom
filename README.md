# Диплом. Диагностика неисправностей коробки передач

## Оглавление
[1. Описание проекта](https://github.com/LILICONDA/Diplom/tree/main/README.md#Описание-проекта)

[2. Какой кейс решаем](https://github.com/LILICONDA/Diplom/tree/main/README.md#Какой-кейс-решаем)

[3. Краткая информация о данных](https://github.com/LILICONDA/Diplom/tree/main/README.md#Краткая-информация-о-данных)

[4. Этапы работы над проектом](https://github.com/LILICONDA/Diplom/tree/main/README.md#Этапы-работы-над-проектом)

[5. Выводы](https://github.com/LILICONDA/Diplom/tree/main/README.md#Выводы)

### Описание проекта
**Бизнес-задача:** определить характеристики, по которым можно выявить дефекты зубчатых зацеплений в редукторе с помощью виброанализа.

**Техническая задача для специалиста в Data Science:** построить модель машинного обучения, которая на основе предложенных характеристик будет предсказывать, есть ли дефект на зубе или нет.

### Какой кейс решаем?
→Промышленным предприятиям очень бы помогло решение данного кейса, ведь часто бывает так, что агрегат, в котором есть зубчатые зацепления, начинает сначала сильно шуметь и иметь повышенную вибрацию, а затем и вовсе выходит из строя. Для того, чтобы не разбирать весь агрегат, но при этом определить, есть ли в конкретном зацеплении дефект зуба колеса, можно будет применить модель, которая на основе вибрационных характеристик позволит сделать предсказание о том, что именно у этой колесной пары проблемы. 

Это позволит серьёзно сэкономить на ремонтах таких агрегатов. Сейчас заводы работают по системе предупредительного планового ремонта (ППР), но часто происходит либо непридвиденные события, которые не позволяют агрегату доработать свой плановый ресурс, либо наоборот, из-за не имения стандартного количества заказов может быть простой оборудования и ппр по расписанию ему тоже не к чему. Это решение позволит заводу перейти от системы ППР к систему ремонта по фактическому состоянию (РФС).


### Краткая информация о данных
Набор данных диагностики неисправностей коробки передач включает в себя набор данных о вибрации, записанных с помощью
симулятора диагностики неисправностей коробки передач SpectraQuest.
Набор данных был записан с использованием 4 датчиков вибрации, размещенных в четырех разных направлениях, при 
изменении нагрузки от «0» до «90» процентов. Включены два разных сценария:

1) Бездефектное состояние

2) Сломанный зуб

Набор данных содержит 2 файла.
Всего было сделано 20 видов записей, 10 на "здоровую" коробку передач и 10 на сломанную. Каждый вид записи 
соответствует заданной нагрузке от 0% до 90% с шагом 10%.

Имя файла указывает на содержимое файла:
broken и healthy - соответвенно записи для коробки со сломаным зубом и для бездефектной коробки.  
Каждое имя файла на конце содержит символы «30hz». Мы можем интерпретировать это как означающее, что данные о 
вибрации были собраны с частотой данных 30 Гц. 
Это дает нам информацию о продолжительности сбора данных в каждом наборе 
(т.е. количество выборок / 30 = время в секундах), а также позволяет нам интерпретировать данные как непрерывный 
сигнал и анализировать данные не только в частотной области, но и во временной области.


### Этапы работы над проектом
Проект будет состоять из пяти частей:
1. *Анализ и обработка данных.*
В рамках этой части данные будут приводиться в нужный и удобный формат для дальнейшего анализа.

2. *Разведывательный анализ данных (EDA).*
Необходимо исследовать данные, нащупать закономерности.

3. *Решение задачи классификации: логистическая регрессия и решающие деревья.*
На данном этапе строится прогностическая модель и оценивается её качество. Также, подбираются оптимальные параметры модели для того, чтобы получить наилучший результат для конкретного алгоритма.

4. *Решение задачи классификации: ансамбли моделей и построение прогноза.*
На этом этапе дорабатывается предсказание с использованием более сложных алгоритмов и оценивается, с помощью какой модели возможно сделать более качественные прогнозы.

5. *Использование глубоких нейронных сетей.*
На заключительном этапе предсказание с использованием глубоких нейронных сетей и сравниваются результаты с ранее построенными моделями.


### Выводы:
Можно сказать, что предварительный подбор гиперпараметров для модели, определенным образом улучшает ее качество. Но даже их подбор нужно осуществлять с помощью современных методов, таких как Hyperopt или Optuna например. Это существенно уменьшает время на подборку гиперпараметров базовыми методами, такими как GridSearchCV. Впринципе, как и методы их подбора, так и виды обучаемых моделей будут для каждой задачи свои, поэтому по возможности, нужно все таки стремиться обучить как можно больше моделей разными методами, сравнивая их метрики. Только так, мы найдем как оптимальную модель, так и метод подбора гиперпараметров для этой модели. На некоторых задачах можно существенно увеличить метрику, используя глубокие нейронные сети.