# tidytuesday-dnd-spells
A mini-project for automated rendering of multiple svg spells of each magic class in DnD, divided into spell levels and magic schools. 
For the #TidyTuesday challenge.

This is a small project, an infographic poster that shows the distribution of spells and cantrips by school of magic and class in DnD.

In terms of analytics - there is almost no value here, although you can see interesting details. Although, of course, I understand that there is room for analytics there, at the very least, you could analyze the growth of damage, number and type of dice, derive sets of the most attacking spells, etc.

The original idea was to manually create the poster in Figma - I love creating infographics by hand, but the number of objects to keep track of made me turn to python for help. 

> In fact, the hardest thing about hand drawing such posters is not to start drawing if you are persistent, but to not fold your hands when you realize that everything went wrong and the objects need to be shuffled =) 

That's why this project was born. 

# What you can do 
Initially you upload data from the [tidytuesday](https://github.com/rfordatascience/tidytuesday/blob/main/data/2024/2024-12-17/readme.md) challenge. 

Then you: 
1. You can change the size of the tiles: sizew, sizeh
2. You can change the formula or set the exact value for the distance between them: marginw, marginh
3. you can change the formula or set the exact value for the distance between schools of magic (sch_marg), because spells of the same school are grouped together.
4. Change the colors of schools in the dictionary school_colors (Personally, I lovingly selected my own, as there is no official, and here even Balder's Gate III will not help)

# How it works
The code collects data on the number of available spells by class, school of magic, and spell level. It then looks separately at the total maximums - how many maximums someone has available by school - so we can draw all pictures with the same indentation =)

The code takes the starting parameters (as I found out, it's better to set indents to zero to work in Figma), and then goes through the class, then school and spell levels, and then iterates through the number of available spells: each time svgwrite draws a tile and adds the required number of pixels to the x and y axes. Eventually the script takes into account how much more indentation is needed to make the indentation between the tiles of different schools consistent across different pictures. 

Honestly, this sounds a lot like programming on Turtle. Or typewriter work =) 

***

Это маленький проект, инфографического плаката, который показывает распределение заклинаний и кантрипс по школам магии и классам в ДнД.
Для челленджа #TidyTuesday

С точки зрения аналитики — здесь практически нет ценности, хотя интересные детали увидеть можно. Хотя, конечно, я понимаю, что для аналитики там есть простор, как минимум, можно было бы проанализировать рост урона, количества и типа дайсов, вывести наборы самых атакующих заклинаний и т.д.

Изначально идея была в том, чтобы вручную создать плакат в Figma — я люблю создавать инфографику руками, однако количество объектов, за которыми надо было бы следить заставило меня обратиться к помощи питона. 

> Ведь на самом деле в ручном рисовании таких плакатов — самое сложное не начать рисовать, если вы упорный, а в том, чтобы не сложить руки, когда поймёте, что всё пошло не так и объекты надо перетасовывать =) 

Именно поэтому родился этот проект. 

# Что можно сделать 
Изначально вы загружаете данные с челленджа [tidytuesday](https://github.com/rfordatascience/tidytuesday/blob/main/data/2024/2024-12-17/readme.md). 

Затем вы: 
1. Можете сменить размер тайлов: sizew, sizeh
2. Можете изменить формулу или задать точное значение для расстояния между ними: marginw, marginh
3. Можете изменить формулу или задать точное значение для расстояния между школами магии (sch_marg), так как заклы одной школы группируются
4. Сменить цвета школам в словаре school_colors (Лично я любовно подбирал самостоятельно, так как официальных нет, и тут даже Balder's Gate III не поможет)

# Как оно работает
Код собирает данные о количестве доступных заклинаний по классу, школе магии и уровню заклинания. Затем отдельно смотрит на общие максимумы — сколько максимум кому-то доступно по школе — так мы сможем рисовать все картинки с одинаковыми отступами =)

Код принимает стартовые параметры (как я выяснил, для работы в Figma отступы лучше ставит на нулях), и затем проходит по классу, затем школе и уровням заклов и далее итерируется по ренджу количества доступных заклов: каждый раз svgwrite отрисовывет тайл и добавляет к осям x и y нужное кол-во пикселей. В конечном итоге скрипт учитывает, сколько ещё нужно отступить для того, чтобы отступы между тайлами разных школ были консистентны на разных картинках. 

Если честно, это сильно похоже на программирование на «Черепашке». Или на работу печатной машинки =) 
