# Cells classification to cancer and healthy ones by their SERS spectra

## Contents
1. [Project description](Project-description)
2. [Data description](#Data description)
3. [Зависимости](#Зависимости)
4. [Установка проекта](#Установка-проекта)
5. [Использование проекта](#Использование-проекта)
6. [Авторы](#Авторы)
7. [Выводы](Использование-проекта)

## Project description

A problem of early-stage cancer detection is currently one of hot topics in early diagnostics. Raman spectroscopy is one of methods of noninvasive analysis of substance contents, inter alia cell analysis. However, Raman signal is usually too low, therefore special enhancing gold or silver nanoparticles may be used that dramatically enhance the signal; such approach is called SERS, Surface-Enhanced Raman Spectroscopy. The obtained spectra represent data with thousand of dimensions (features) that are difficult to be classified by eye due to complex contents of cells. Therefore, methods of data science are used to classify cancer and healthy cells. There is a bunch of papers researching this topic, but too few of them provide data in open access. 

On the paper [Erzina et al](https://doi.org/10.1016/j.snb.2020.127660) , the authors use:
* a convolutional neural network to differentiate a set of cell types;
* cell types include both known cell cultures grown in vitro and cells derived from human;
* spectra of cells with 3 types of enhancing gold nanoparticles (AuNPs): with (COOH)2, COOH and NH2 residues, providing catching cells by different molecules on their surface.

I used the data from this article aiming:
* to focus on just 2 cell types, that are derived from human: heallthy and cancer skin fibroblasts, that makes more sense. Therefore, the task from a multiclass classification becomes a binary classification;
* to explore opportunities to build a much simple model, without neural networks.
* 

## Data description
В этом проекте используются данные с соревнования [Sberbank Russian Housing Market](https://www.kaggle.com/c/sberbank-russian-housing-market/data) от Сбера (бывш. Сбербанк).

Требования Сбера состояли в построении модели, которая бы прогнозировала цены на жильё в Москве, опираясь на параметры самого жилья, а также состояние экономики и финансового сектора в стране.

Исходный датасет представляет собой набор данных из таблицы с информацией о параметрах жилья в Москве и Московской области, а также таблицы, в которой содержатся 292 признака о состоянии экономики России на момент продажи недвижимости. 

Для упрощения демонстрации техники очистки данных мы будем отрабатывать на урезанном датасете. 
