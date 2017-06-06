# Генератор DocX/LaTeX отчётов по практике

## Результаты сдачи

| 3О-207Б       | Сдача | 3О-208Б       | Сдача | 3О-209Б       | Сдача | 3О-210Б       | Сдача |
|:-------------:|:-----:|:-------------:|:-----:|:-------------:|:-----:|:-------------:|:-----:|
| Абрамов       |       | Авраменко     |   +   | Андреев       |       | Белова        |       |
| Арсёнов       |       | Благовещенская|   +   | Архангельский |       | Варганов      |       |
| Волков        |       | Васина        |   +   | Афанасьева    |       | Викулов       |       |
| Гилзов        |       | Власов        |   +   | Боронкинов    |       | Вишкарёв      |       |
| Иванов        |   +   | Гуреев        |   +   | Букреев       |   +   | Волков        |       |
| Качнов        |   +   | Изотов        |   +   | Дудинская     |       | Гугава        |       |
| Коноков       |       | Каленюк       |   +   | Киясов        |       | Ефременков    |       |
| Кулага        |       | Колмыков      |   +   | Молчанов      |       | Задоя         |       |
| Марценюк      |   +   | Костицин      |   +   | Оберган       |       | Затевалова    |       |
| Романько      |       | Макаров       |   +   | Огнивенко     |       | Ильясов       |       |
| Силантьева    |       | Павлов        |   +   | Петухов       |       | Максимов      |       |
| Телегин       |   +   | Пашков        |   +   | Савельев      |       | Маласай       |       |
| Фролов        |       | Пожитько      |   +   | Скалозубов    |       | Николаев      |       |
| Хадиева       |   +   | Сафронова     |   +   | Смирнов       |       | Овчиников     |       |
| Шибин         |       | Храпов        |   +   | Телятников    |   +   | Туруснова     |       |
|               |       | Шингалова     |       | Третьякова    |       | Уварова       |       |
|               |       |               |       |               |       | Холоянц       |       |
|               |       |               |       |               |       | Ярцев         |       |

## Как скомпилировать отчёт без локальной установки?

Служба [pythonanywhere](https://www.pythonanywhere.com) предоставляет файловое хранилище и возможность запускать проекта в Unix-окружении.

Чтобы сгенерировать отчёт, после регистрации будет необходимо:

1. Открыть Bash-консоль (Start new console -> Bash)
2. Проверить, что все зависимости установлены, либо установить: `pip install --user lxml pil qrcode sympy python-docx`
3. Клонировать репозиторий: `git clone https://github.com/nkapyrin/upgraded-doodle` (название случайно)
4. Перейти в папку с проектом : `cd upgraded-doodle`
5. Отредактировать файл с заданием
    1. Либо при помощи `nano db.xml` (выйти из программы можно нажатием `Ctrl+X`)
    2. Либо при помощи онлайн-редактора текстовых файлов, можно открыть xml-файл в `Files/upgraded-doodle/db.xml` и вписать свои изменения
6. Выполнить сборку docx-документа: `python parser_docx.py`
7. Выполнить сборку LaTeX-документа: `python parser_docx.py` (да, сайт предоставляет работающий LaTeX-компилятор)
8. С главного экрана сайта, скачать файлы `Files/upgraded-doodle/result_ВашаФамилия.docx` и/или `Files/upgraded-doodle/tex/result.pdf` и отправить их на nikolay.kapyrin@gmail.com.


## Исходные данные

Для формирования отчёта, нужно привести описание и математическую модель измерительного инструмента и эффектов, выбор которых выполняется согласно [заданию](assignment.pdf). Ограничение проведённое в задании пока только накладывает ограничения на поиск математических моделей, которые целесообразно учитывать в измерительном сценарии.

Для последующего автоматического составления документа в формате DocX или LaTeX, эти данные помещаются в файл [db.xml](assignment.pdf).

За неимением конкретики, используйте линейные модели: `Y = a*X + b` - выходная характеристика Y зависит от входной величины X, масштабного коэффициента a и коэффициента смещения b.

## DocX

Для запуска скрипта рекомендуется установить Python в составе дистрибутива [Anaconda](https://www.continuum.io/downloads), который кроме компилятора поставляет много нужных инструментов и библиотек функций. Дополнительные библиотеки можно установить одной командой:

`pip install python-docx, lxml, pillow, qrcode`

Чтобы сформировать отчёт, нужно поместить в одну папку 3 файла:

* `db.xml` - ваше задание
* `parser_docx.py` - программа формирования отчёта
* `template.docx` - шаблон документа, который программа будет заполнять
* `mml2omml.xsl` - XSL-трансформация MML уравнений в MS OMML

Локальный запуск программы осуществляется обычной командой

`python parser_docx.py`

## LaTeX

Для отчёта в LaTeX, исполняемый файл будет называться parser_latex.py.

`python parser_latex.py`

В системе должен быть установлен [компилятор LaTeX](http://www.tug.org/texlive/), либо выходной файл result... .tex можно скомпилировать при помощи онлайн-сервиса [ShareLatex](https://ru.sharelatex.com/).
