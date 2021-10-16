Репозиторий содержит диаграмму распределения власти в Российской Федереции в машиночитаемом виде.

Человекочитаемые версии доступны как [pdf-версия](vlast.pdf) (373 KB) и [png-версия](vlast.png) (3.8 MB) в высоком качестве.
[![preview](vlast_m.png)](vlast.png)



# Структура власти Российской Федерации

*2021 г. А.А. Формозов* [^1]

[^1]: Корреспонденция: formozoff [at] gmail.com

*Структура демократических институтов и базовые механизмы их взаимодействия закреплены в основных законах Российской Федерации,
Конституции и Федеральных Законах, и являются публично доступной информацией. Однако, данная информация представлена исключительно
в виде текста, что затрудняет целосное понимание и интерпретацию политической системы, в особенности для неспециалистов. 
Использование визуальных средств представления, в том числе взаимосвязанных диаграмм (графов), может позволить существенно
продвинуться в преодолении данных трудностей. Также, представление диаграммы в машиночитаемом виде позволяет не только
обеспечить возможность её постоянного обновления, но и значительно расширить область её применения, например для построения и анализа полной модели её работы. Данная статья описывает процесс построения полной диаграммы распределения власти в Российской Федерации, опубликованной в виде открытого кода. Методология рассмотренная в статье может быть также применена для анализа правовых систем других государств.*

**Ключевые слова:** Российская Федерация, Правительство, Конституционное право, Власть, Демократия, Визуальное представление, Диаграмма, Открытая наука, Трансдисциплинарность

*The structure of the main democratic institutions of Russia and the mechanisms of their interaction are publicly available information.
However, this information is presented as interlinked text, mainly in the form of the laws of the state, which significantly hampers
understanding and comprehensive analysis of the model of the political system. The use of visual representations, including interconnected
diagrams (graphs), can make significant progress in overcoming these difficulties. This article describes the process of constructing a diagram
of power distribution in the Russian Federation, published as open source code. Representation of the diagram in machine-readable form allows
not only to provide the possibility to update it, but also to significantly expand its field of application. The methodology discussed in this
article can also be applied to the analysis of the legal systems of other states.*

**Key-words:** Russian Federation, Government, Constitutional law, Power, Democracy, Visual representation, Diagram, Open science, Transdisciplinarity

В данной статье я привожу построение диаграммы, наиболее полно описывающей структуру и взаимодействие основных демократических
и других важных общественных институтов Российской Федерации. Диаграмма представляет собой связный ориентированный граф,
в котором вершинами являются основные источники и институты власти, а линии и стрелки соединяющие вершины играют роль взаимосвязями
и направления распределения власти, соответственно.

Структура основных демократических институтов и механизмы их взаимодействия являются публично доступной информацией,
публикуемой в виде основных законов государства: Конституции Российской Федерации (КРФ), Федеральных Конституционных Законов (ФКЗ) и Федеральных Законов (ФЗ).
Данная информация представлена исключительно в форме текста, что существенно ограничивает понимание и интерпретацию системы, 
а также разнообразие методов, которые могут быть использованы для её анализа. Визуальное представление информации, например в форме
вышеописанной диаграммы, имеет серьезное преимущество перед текстом, поскольку является подспорьем для построения целостной модели
государства и анализа динамики его работы. В дополнение к этому оно также несет в себе образовательную и просветительскую функцию.
Подобное построение полной структуры связей системы широко зарекомендовало себя в нейробиологии, где оно носит название коннектома (connectome)
([Анохин](https://elibrary.ru/item.asp?id=26456573), [Сеунг](https://www.health-source.ru/wp-content/uploads/2018/12/sebastyan-seung.pdf), [Sporns](https://behavioralhealth2000.com/wp-content/uploads/2017/05/The-human-connectome-a-complex-network.pdf)) и является базовым шагом для последующих исследований функциональной работы системы ([Bargmann](https://www.nature.com/articles/nmeth.2451)). Таким образом, с методологической точки зрения описание полной структуры государства являться мостом между общественными, с одной стороны, и биологическими науками с другой.
В последних был разработан и опробован широкий ряд методов для анализа связных систем ([Bargmann](https://www.nature.com/articles/nmeth.2451), [Kaiser](https://www.sciencedirect.com/science/article/pii/S1053811911005131?casa_token=lJthTB8UHywAAAAA:YBn02gvQeSOBIe9am3EDSOceDfwDsgGnzZIeYVYtXR8qznZcG1i3E4R9x8ciEVSn6uuqM3W-), [Fornito](https://doi.org/10.1016/j.neuroimage.2013.04.087)). 
 
Стоит отметить ряд монографий по конституционному праву ([Нудненко](), [Енгибарян](), [Козлова](), [Аглеева](), [Безуглов](), [Чиркин](), [Габричидзе](), [Эбзеев](), [Григонис]() и др.) и особенно пособие [Костериной Э. В.](), выполненное в виде диаграмм и таблиц. В данном пособии впервые была предпринята попытка систематического изложения и представления структуры государства в виде ряда диаграмм. В отличии от данного пособия в текущей работе власть не разделена на отдельные части, а представлена в виде единой взаимосвязанной диаграммы. Интересным историческим примером подобного подхода является диаграмма Федерального устройства Соединенных Штатов Америки, датируемая 1862 годом [Shafer](https://www.loc.gov/resource/pga.03686/).



Для построения полной диаграммы, рассматриваемой в этой работе, понятие власти было существенно расширено. Помимо “классических” трех ветвей власти
также были включены контрольно-надзорная ветвь (Генеральная прокуратура РФ, Уполномоченный по правам человека в РФ, Центральная избирательная комиссия РФ,
Счетная палата РФ, Центральный банк РФ)([Кравцова](), [Солдатова](), [Яблонская](), [Пожарский]()). Следственный комитет также часто выделяют в отдельную независимую структуру, отдельную от исполнительной власти структуру, хотя данная классификация является спорной ([Романовский]()). Средства массовой информации часто выделяются в отдельную "четвертую власть" ([Сафарян]()). Поскольку права и свободы гражданина гарантированы Конституцией (ст. 17 КРФ)
и являются фундаментом реализации народовластия , они также включены в диаграмму в качестве её элементов. Конституция Российской федерации также
гарантирует непосредственную реализацию власти гражданами Российской Федерации, свободу собраний, митингов и шествий, проведение пикетов, что является
признаками народовластия ([Нудненко]()). Данный список не является исчерпывающим, так как существуют и другие формы формирования и распределения власти,
в том числе противозаконные и противоконституционные (такие как, например, “телефонное право”, [Леденева]()). Они не являются первостепенным предметом данного
исследования, но могут быть включены в дальнейшем. Органы местного самоуправления (муниципальная власть) ([Пешин]()) не входят в структуру органов государственной
власти и самостоятельно в пределах своих полномочий (ст. 12 КРФ) ([Пешин]()). Муниципальная власть имеет существенное значение для демократических институтов
и правозащитной деятельности ([Булатов]()), и она также была включена в структуру диаграммы.

Интересно отметить, что ряд муниципальных форм организаций на текущий момент реализуют институты непосредственной (прямой) демократии ([Нуденко]()). 
Стоит также обратить внимание на важность региональных особенностей, существенных при более детальном рассмотрении системы на региональном уровне,
например в национальных республиках с преобладающем населением, исповедующим ислам ([Lugo]()). Важным остается вопрос о роли организаций с широким региональным
представительством (например, церкви) и *de facto* существенным политическим весом, не являющиеся политическими партиями. Вопросы роли этих организаций
в рассматриваемой модели политической системы являются предметом дальнейших исследований.

Диаграмма распределения власти выполнена с помощью сервиса [draw.io]() и опубликована на сервисе контроля версий [Github]() с возможностью внесения правок,
исправлений и модификаций, и доступна по адресу https://github.com/formozov/vlast.  Изменения диаграммы возможны как с помощью отправки запроса автору (*Issue*), так и с помощью копирования репозитория (*Fork*) c последующем изменением копии и запросом на слияние с оригиналом (*Pull request*). Лицензия распространения CC BY 4.0 (с указанием авторства). 
Работа выполнена *pro bono*.


## Литература


Анохин, К. В. "Коннектом и когнитом: заполнение разрыва между мозгом и разумом." *The Seventh International Conference on cognitive science*, 2016.

Сеунг, С. "Коннектом. Как мозг делает нас тем, что мы есть." *БИНОМ. Лаборатория знаний*

Sporns, O. "The human connectome: a complex network." *Annals of the new York Academy of Sciences* **1224.1** (2011): 109-125.

Bargmann, C.I., and Marder, E. "From the connectome to brain function." *Nature methods* **10.6** (2013): 483-490.

Kaiser, M. "A tutorial in connectome analysis: topological and spatial features of brain networks." *Neuroimage* **57.3** (2011): 892-907.

Fornito, A. et al. "Graph analysis of the human connectome: promise, progress, and pitfalls." *Neuroimage* **80** (2013): 426-444.

Shafer, N. M., Diagram of the Federal Government and American Union by N. Mendal Shafer, attorney and counseller at law, office no. 5 Masonic Temple, Cincinnati / lith. by Ehrgott, Forbriger & Co.

Нудненко, Лидия Алексеевна. "Конституционное право России." учебное пособие (2011).

Енгибарян, Р. В., and Э. В. Тадевосян. "Конституционное право." *Юристъ* (2000): 333-350.

Козлова, Екатерина Ивановна, and Олег Емельянович Кутафин. Конституционное право России. Учебник. 5-е издание. *Издательство Проспекm*, 2013.

Аглеева, Л. Т., et al. "Конституционное право России." (2012).

Безуглов, Анатолий Алексеевич, and Сергей Александрович Солдатов. "Конституционное право России." (2003).



Нудненко, Лидия Алексеевна. Институты непосредственной демократии в системе местного самоуправления (проблемы теории и практики). *Diss. Московский государственный университет им. МВ Ломоносова*, 2001.

Чиркин, В. Е. "Конституционное право: Россия и зарубежный опыт." (1998).

Габричидзе, Борис Николаевич, et al. Конституционное право современной России. Дело и сервис, 2001.

Эбзеев, Борис Сафарович. Конституционное право России. Учебник. *Издательство Проспект*, 2019.

Григонис, Валериюс Пранович, and Андрей Николаевич Тулаев. "Конституционное право России." (2018): 312-312.

Сафарян, Арег Вартанович. "СМИ как «четвертая власть» и институт социализации." *Власть* **5** (2008).

Яблонская, Алла Борисовна. "Контрольно-надзорная функция государственной власти в Российской Федерации (теоретико-правовое исследование)" (2009).

Пожарский, Дмитрий Владимирович. Контрольно-надзорная функция современного государства. *Diss. Акад. упр. МВД России*, 2004.

Э. В. Костерина: Конституционное право России в схемах и таблицах. Учебное пособие

Кравцова, Е. А. "О целесообразности выделения контрольно-надзорной ветви власти при формировании постиндустриального общества." *Вестник Белгородского юридического института МВД России* **2-1** (2014).

Солдатова, Виктория Андреевна. "ПРОКУРАТУРА РОССИЙСКОЙ ФЕДЕРАЦИИ В СИСТЕМЕ КОНТРОЛЬНО-НАДЗОРНЫХ ОРГАНОВ." **302**.

Романовский, Георгий Борисович. "Правовой статус Следственного комитета Российской Федерации." *наука. общество. государство* **1 (1)** (2013).

Леденева, Алена. "Телефонное право в России." *Вестник общественного мнения. Данные. Анализ.* **Дискуссии 3** (2008).

Булатов, Рашид Борисович, Петр Петрович Глущенко, and Е. А. Орловский. "Муниципальная власть и правозащитная деятельность: актуальность проблемы и некоторые итоги размышлений." *Правовое поле современной экономики* **5** (2016): 51-58.

Пешин, Николай Леонидович. "Муниципальная власть: понятие и содержание." *Конституционное и муниципальное право* **9** (2011): 14-17.

Lugo L, Cooperman A, Bell J, O’Connell E, Stencel S. The world’s Muslims: Religion, politics and society. *World* 2013 Apr 30
