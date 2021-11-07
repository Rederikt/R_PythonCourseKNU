---
title: "R Labs 5"
output: html_notebook
---

1. Написати функцію pmean, яка обчислює середнє значення (mean)
забруднення сульфатами або нітратами серед заданого переліка
моніторів. Ця функція приймає три аргументи: «directory», «pollutant»,
«id». Directory – папка, в якій розміщені дані, pollutant – вид забруднення,
id – перелік моніторів. Аргумент id має значення за замовчуванням 1:332.
Функція повинна ігнорувати NA значення. 


```{r}


pmean <- function(directory, pollutant, id = 1:332){
  #Встановлюю директорію, дістаю файли та додаю їх в один датафрейм
  setwd(directory)
  files <- dir()
  dataf <- do.call(rbind,lapply(files,read.csv))
  #Очищаю від НАшок
  good_data <- na.omit(dataf)
  #Знахожу середнє
  mean(good_data[id, pollutant])
}
pmean("specdata", "sulfate", 1:23)


```

2. Написати функцію complete, яка виводить кількість повних спостережень
(the number of completely observed cases) для кожного файлу. Функція
приймає два аргументи: «Directory» та «id» та повертає data frame, в
якому перший стовпчик – ім’я файлу, а другий – кількість повних
спостережень.

```{r}
complete <- function(directory, id = 1:332){
  #Встановлюю директорію, дістаю файли та додаю їх в один датафрейм
  setwd(directory)
  files <- dir()
  dataf <- do.call(rbind,lapply(files,read.csv))
  #Звожу дані до їх кількості
  datafr <- data.frame(table(dataf$ID))
  #Дістаю результат
  datafr[id, 1:2]
}
complete("specdata", 10:20)

```

3. Написати функцію corr, яка приймає два аргументи: directory (папка, де
знаходяться файли спостережень) та threshold (порогове значення, за
замовчуванням дорівнює 0) та обчислює кореляцію між сульфатами та
нітратами для моніторів, кількість повних спостережень для яких більше
порогового значення. Функція повинна повернути вектор значень
кореляцій. Якщо ні один монітор не перевищує порогового значення,
функція повинна повернути numeric вектор довжиною 0. Для обчислення
кореляції між сульфатами та нітратами використовуйте вбудовану функцію 
«cor» з параметрами за замовчуванням.

corr <- function(directory, threshold){

  dataf <- do.call(rbind,lapply(files,read.csv))
  datafr <- data.frame(table(dataf$ID))
  datafr[id, 1:2]
}
complete("specdata", 10:20)

```{r}
corr <- function(directory, threshold = 0) {
    #Дістаю файли
    setwd(directory)
    files <- dir()
    corr_vect <- NULL
    #Прохожусь по кожному файлі
    for (i in 1:332) {
    
        dataf <- read.csv(files[i])
       
        data <- dataf[complete.cases(dataf),]
        #Якщо перевищує межу
        if (nrow(data) > threshold){
          corr_vect <- c(corr_vect, cor(data[,"sulfate"], data[, "nitrate"]))
        }
    }
    if(length(corr_vect) > 0) return (corr_vect)
    return (c())
}
#Відображаю результати
cr <- corr("specdata", 133); head(cr);  summary(cr)
```
