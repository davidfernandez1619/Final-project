# Análisis de empleabilidad Alumni Universidad CEU San Pablo

## Introducción:

Desde que empecé a trabajar como asesor laboral en la [Universidad CEU San Pablo](https://www.uspceu.com/) llevando la Facultad de Humanidades y CC. de la Comunicación, tenía interés en explorar las experiencias laborales de los alumnos egresados, de cara a hacer un estudio de empleabilidad que me sirviera en mi trabajo, tanto en la prospección comercial como en el asesoramiento a alumnos. 

En base a esto, obtuve el listado de los alumnos graduados desde 2015 a 2023, obteniendo sus nombres completos, grado estudiado y fecha de graduación. 

Tomé los siguientes pasos: 

### Paso 1: limpieza de datos: 

Partía de varios excels con los nombres completos de los alumnos, grado que estudiaron, y más datos personales. 

Tuve que hacer una limpieza de los datos, cambiando y eliminando columnas, cambiando el tipo de datos, etc. Puedes ver el proceso completo [aquí](https://github.com/davidfernandez1619/Final-project/blob/main/Notebooks/1-Cleaning.ipynb). 

### Paso 2: extracción de las URLs de LinkedIn: 

Dado que sólo tenía como información el nombre completo de los alumnos, los grados que estudiaron, y su fecha de graduación, de cara a poder obtener datos de sus experiencias, tenía que escrapearme sus datos de LinkedIn. 

Usando el [buscador de alumni del CEU de LinkedIn](https://www.linkedin.com/school/universidad-san-pablo-ceu/people/), fui iterando por cada nombre completo de los alumnos, y extrayendo, usando Selenium, sus URLs de sus perfiles de LinkedIn. Con cada una de las iteraciones, añadía el link de cada alumno en una nueva columna. Puedes ver el proceso completo [aquí](https://github.com/davidfernandez1619/Final-project/blob/main/Notebooks/2-URL%20scraping.ipynb). 

### Paso 3: extracción de los datos de la experiencia de cada alumno: 

Usando una función que escrapeaba los datos de LinkedIn de un usuario, saqué los datos de experiencia de cada uno de los alumnos a partir de sus URLs. 

A continuación, me quedé con sus datos de la experiencia: puesto ocupado, empresa en la que trabajó o ha trabajado, fecha de inicio y fecha fin. A partir de estos datos, pude calcular la duración de cada una de las experiencias. 

Una vez hecho todo esto, limpié todos los datos y reestructuré mi dataframe, e hice algunas labores extra de limpieza antes de cargar los datos a Tableau. **Puedes ver el proceso completo [aquí](https://github.com/davidfernandez1619/Final-project/blob/main/Notebooks/3-%20Scraping%20experience%20data.ipynb)**. 

### Paso 4: carga de datos a Tableau y visualización: 

Una vez terminada mi extracción y limpieza de datos, realicé la visualización con Tableau. 

Puedes [visitar el dashboard aquí](https://public.tableau.com/app/profile/david.fern.ndez6995/viz/Proyectoempleabilidad/Dashboard1?publish=yes)

## Conclusiones en base a los datos: 


**- Número de alumnos graduados:** de 2015 a 2020, el número de alumnos graduados por año se mantiene entre los 150 y 200. No obstante, en el año 2020 sufre un bajón. Podría ser debido a la pandemia, pero sería interesante explorarlo en el futuro:

<img width="587" alt="Captura de pantalla 2023-10-21 a las 0 47 55" src="https://github.com/davidfernandez1619/Final-project/assets/38441372/fe619c2a-9b8b-42a9-9c42-48162a079dfd">


Puede observarse también cómo hay muchos más graduados de grados de CC. de la Comunicación (Periodismo, Publicidad y RRPP, Comunicación Audiovisual y Comunicación Digital) que de grados de Humanidades (Historia, Historia del Arte y Humanidades): 

<img width="775" alt="Captura de pantalla 2023-10-21 a las 0 53 41" src="https://github.com/davidfernandez1619/Final-project/assets/38441372/417d6d6e-397e-463b-8cf5-cec5af73b283">


Algo parecido ocurre con los graduados de los grados individuales. El número de alumnos graduados por año que han estudiado sólo un grado es mucho mayor que aquellos que han cursado un doble grado: 


<img width="776" alt="Captura de pantalla 2023-10-21 a las 0 57 00" src="https://github.com/davidfernandez1619/Final-project/assets/38441372/01bd896c-68a3-4eed-b2eb-41c72ca4325b">


**- Localizaciones:** claramente, de los alumnos egresados de la universidad, la gran mayoría trabajan en Madrid. Tiene todo el sentido, al ser una ciudad situada en la propia ciudad de Madrid (que, además, al ser la capital de España, cuenta con mucha más oferta laboral) y que cuenta con alumnos mayoritariamente españoles. No obstante, se puede observar también que hay varias otras ciudades españolas en las que, como mínimo, un alumno ha trabajado:

<img width="238" alt="Captura de pantalla 2023-10-21 a las 0 51 46" src="https://github.com/davidfernandez1619/Final-project/assets/38441372/cfc1c62b-dc28-4f98-8573-95d0dd0a69e3">


**- Empresas que más contratan:** curiosamente, es la propia universidad CEU San Pablo la que más veces sale en la experiencia de los alumnos egresados (experiencias con fecha de inicio a partir de 2015), con un total de 118, siendo muchos de ellos alumnos que han escrito 'estudiante' como experiencia laboral, y también varios profesores: 

<img width="527" alt="Captura de pantalla 2023-10-21 a las 1 30 11" src="https://github.com/davidfernandez1619/Final-project/assets/38441372/ce20b0ce-28cf-4981-b91d-5b5145a2f932">


Las empresas que más contratan, seguidas del CEU, son medios de comunicación principalmente (Cadena COPE, Antena 3, Mediaset, etc.). 


**-Grados con mejor empleabilidad:** en línea con el apartado anterior, tiene sentido que los grados con mayor número de alumnos contratados (con fechas de inicio de experiencia a partir de 2015) sean aquellos que pertenecen a las Ciencias de la Comunicación: 


<img width="517" alt="Captura de pantalla 2023-10-21 a las 1 54 08" src="https://github.com/davidfernandez1619/Final-project/assets/38441372/5199e2bd-3e30-462f-af6c-42d553508550">


Observamos también que los grados de la rama de Humanidades cuentan con muchos menos alumnos contratados. 


**-Grados con mayor promedio de duración por cada experiencia laboral:** no obstante, a pesar de los resultados obtenidos en el apartado anterior, observamos en el siguiente gráfico cómo, los alumnos que han estudiado un grado de la rama de Humanidades duran en promedio bastante más en sus experiencias que los alumnos que han estudiado un grado de CC. de la Comunicación. Esto sugiere que, a pesar de ser el sector de las CC. de la Comunicación un área con mejor empleabilidad, parece que existe un mayor índice de rotación: 


<img width="649" alt="Captura de pantalla 2023-10-21 a las 1 58 57" src="https://github.com/davidfernandez1619/Final-project/assets/38441372/4d5c58b7-c2e3-4808-b12c-02a669d0b0b5">


## Próximos pasos: 

Cómo acciones de mejora próximas, sería interesante: 

- Seguir escrapeando datos de formación, y comparar las experiencias laborales de aquellos alumnos que no han hecho máster, vs aquellos que sí han seguido estudiando.
  
- Obtener datos de salarios. Esto nos permitirá observar si, esos saltos en el sector de las CC. de la Comunicación incluye una mejora salarial, o si se trata de un sector con mucha rotación pero poca mejora de condiciones.
  
- Observar diferencias de empleabilidad entre sexos.
  
- Estudiar la empleabilidad por sectores.

## Herramientas empleadas: 

-[Python](https://www.python.org/)

-[Pandas](https://pandas.pydata.org/)

-[Numpy](https://numpy.org/)

-[Selenium](https://www.selenium.dev/)

-[Tableau](https://www.tableau.com/es-es)


