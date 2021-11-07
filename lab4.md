---
title: "R Lab 4"
output: html_notebook
---

1. Які назви стовпців файлу даних?
```{r}
data <- read.csv("hw1_data.csv")
names(data)
```

2. Виведіть перші 6 строк фрейму даних.
```{r}

data[1:6, 1:6]
```
3. Скільки спостерігань (строк) в дата фреймі?
```{r}

nrow(data)
```

4. Виведіть останні 10 строк дата фрейму.
```{r}

tail(data, 10)
```
5. Як багато значень «NA» в стовпці «Ozone»?

```{r}
data
sum(is.na(data[1]))

```

6. Яке середнє (mean) стовпця «Ozone». Виключити «NA» значення
```{r}

good <- na.omit(data)
ozon <- good[, 1]
mean(ozon)
```

7. Виведіть частину набору даних (subset) зі значенням «Ozone» > 31 та
«Temp» > 90. Яке середнє (mean) значень «Solar.R» в цьому наборі даних
(subset)?
```{r}
my_data <- data[data$Ozone > 31 & data$Temp > 90, ]
good_data <- na.omit(my_data)
mean(good_data$Solar.R)
```

8. Яке середнє значення (mean) для «Temp» для червня («Month» дорівнює
6)?

```{r}
month <- na.omit(data[data$Month == 6, ])
mean(month$Temp)
```

9. Яке максимальне значення «Ozone» для травня («Month» дорівнює 5)?

```{r}
month <- na.omit(data[data$Month == 5, ])
max(month$Temp)
```

