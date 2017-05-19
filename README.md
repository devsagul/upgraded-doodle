# Проект менеджера календаря для Python+GTK

## DOCX

## Исходные данные

Для формирования отчёта, необходимо найти описание и математическую модель измерительного инструмента и эффекта, выбор которых выполняется согласно согласно (см. assignment.pdf). Ограничение проведённое в задании не используется при генерации модели погрешности, но накладывает ограничения на математические модели, которые целесообразно учитывать в том или ином сценарии.

Для последующего автоматического составления документа в формате DocX или LaTeX, эти данные помещаются в файл db.xml.

(за неимением конкретики, используйте линейные модели: Y = a*X + b -- выходная характеристика Y зависит от входной величины X, масштабного коэффициента a и коэффициента смещения b)

## DocX

Необходимые библиотеки для формирования отчёта в docx моно установить одной командой:

pip install python-docx, lxml, pillow, qrcode

Чтобы сформировать отчёт, нужно поместить в одну папку 3 файла:

* db.xml -- ваше задание
* parser_docx.py -- программа формирования отчёта
* template.docx -- шаблон документа, который программа будет заполнять
* mml2omml.xsl -- XSL-трансформация MML уравнений в MS OMML

Локальный запуск программы осуществляется обычной командой python parser.py

## LaTeX

Для отчёта в LaTeX, исполняемый файл будет называться parser_latex.py.

В системе должен быть установлен компилятор LaTeX (http://www.tug.org/texlive/), либо выходной файл result... .tex можно скомпилировать при помощи онлайн-сервиса (https://ru.sharelatex.com/).
