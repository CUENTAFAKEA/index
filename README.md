# Introcucción 
El documento que se llevara a cabo mostrara diferentes colores, olores y pero sobre todo la calidad del café entre mejor calidad a menor de diferentes países, para una mejor visualización se harán uso de paquetes en Quarto para la creación de gráficos interactivos y distintas tablas de datos, datos que son extraídos del repositorio de Fatih boyer, titulado *coffee-quality-data-CQI*(https://github.com/fatih-boyar/coffee-quality-data-CQI) la respectiva referencia la encontraras en la bibliografía.

### Instalacion de paquetes
(Estos son los packs que serán utilizados para la realización de las gráficas y diferentes códigos de datos)

1. install.packages("tidyverse")
2. install.packages("plotly")
3. install.packages("DT")
4. install.packages("ggthemes")
5. install.packages("hrbrthemes")
6. install.packages("ggplot2")


### Carga de paquetes
```{r}
#| label: carga-paquetes
#| Warning: false
#| message: false


library(tidyverse)
library(ggplot2)
library(plotly)
library(DT)
library(ggthemes)
library(hrbrthemes)
library(readr)
```

# Tabla de datos
Por medio de tablas deseo presentar los países de origen de diferentes granos de café, el datos de las tablas a sido extraído del repositorio de Mfvargas (los datos de la tabla a sido editados por el usuario Mfvargas)  titulado _calidad del café.csv_.


```{r}
#| label: carga-datos cvs-Paises de Origen
#| warning: false
#| code-fold: true


# Carga de datos de coffe-quality en Columnas selecionadas

coffee_quality <-
  read_delim(file = "coffee-quality.csv",
    col_select = c(
      "Country_of_Origin",
      "Variety",
      "Color",
      "Variety",
      "Altitude",
      "Total_Cup_Points")
  )
    
# Presentation de tabla
    
coffee_quality |>
  datatable(
    options = list(
      pageLength = 10,
      language = list(url = '//cdn.datatables.net/plug-ins/1.10.11/i18n/Spanish.json')
    )
  )

```
