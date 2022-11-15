# Proyecto ETL Eurovision🎙️
## CONTENIDO 📑
[1 - Objetivo 🎯](#O)<br />
[2 - Extracción ⛏️](#EX) <br />
[3 - Transformación 🔁](#TR)<br />
[4 - Carga ⤴️](#CA)<br />


## 1 - OBJETIVO 🎯<a name="O"/>  
💥 Realizar el proceso de extracción, transformación y carga de datos sobre Eurovisión, provenientes de diferentes fuentes y a partir de 3 métodos distintos de extracción con un deadline de 3 días.

💥 Crear una pequeña estructura relacional entre las diferentes tablas obtenidas formando una base de datos incial para el buen tratamiento de los datos y el correcto funcionamiento de las consultas y futuros análisis. 

## 2 - EXTRACCIÓN ⛏️<a name="EX"/>  
🎵 Spotify: Obtenemos una tabla Año_Canción_Cantante_Duración desde 2002 a 2022<br />

🌐 Wikipedia: Obtenemos una tabla Orden_País_Cantante_Canción_Idioma_Lugar_Año<br />

📑 Kaggle: Obtenemos JSON de las letras de toda la historia del festival (1965-2022).<br />

&emsp; &emsp; • Utilizamos MongoDB para leer el archivo y quedarnos con los últimos 20 años

🪙 Kaggle: Obtenemos CSV del PIB de los países participantes desde 1999 a 2022.<br />


## 3 - TRANSFORMACIÓN 🔁<a name="TR"/> 
🧹 Limpieza:<br />

&emsp; &emsp; • Limpiamos algunos errores en tabla Spotify (paréntesis, anotaciones innecesarias, etc.).<br />
&emsp; &emsp; • Corregimos valores inconsistentes con los datos.<br />
&emsp; &emsp; • Eliminamos duplicados en tabla de Spotify (nos quedamos con 791 canciones).<br />
&emsp; &emsp; • Unificamos tablas de Puntos en una sola tabla de puntos.<br />
&emsp; &emsp; • Limpiamos errores en tabla Puntos (números como string, países duplicados, anotaciones etc.).<br />

🤔 Nuevas variables:<br />

&emsp; &emsp; • Creamos claves para cruce Canción-Año en las diferentes tablas.<br />
&emsp; &emsp; • Creamos claves para cruce de letras<br />
&emsp; &emsp; • Creamos nuevas variables con conteo de carácteres y palabras únicas en tabla Letras. 

✅ Tablas:<br />

&emsp; &emsp; • Obtenemos tabla Spotify:<br />

&emsp; &emsp;&emsp; &emsp;![image](https://user-images.githubusercontent.com/109532909/188490210-7c9f05ba-4322-4e58-ae0d-59de99b0c9f7.png)<br />

&emsp; &emsp; • Obtenemos tabla Puntos:<br />

&emsp; &emsp;&emsp; &emsp;![image](https://user-images.githubusercontent.com/109532909/188490665-a6142d68-4fb1-4893-b284-dee78ebf2109.png)<br />

&emsp; &emsp; • Obtenemos tabla Letras:<br />

&emsp; &emsp;&emsp; &emsp;![image](https://user-images.githubusercontent.com/109532909/188493802-2ce82f1b-49df-47d3-b82e-889d8fbc85f9.png)<br />

&emsp; &emsp; • Obtenemos tabla GDP (PIB):<br />

&emsp; &emsp;&emsp; &emsp;![image](https://user-images.githubusercontent.com/109532909/188494239-87b95486-669a-4dca-be97-3639c0553050.png)<br />

## 4 - CARGA ⤴️<a name="CA"/> 
&emsp; &emsp; • Usamos mongoDB para el JSON de Letras<br />

&emsp; &emsp;&emsp; &emsp;<img src="https://user-images.githubusercontent.com/109532909/188491630-a944208f-cf93-4d28-a01e-3b76dbcb9263.png" width="800"><br />

&emsp; &emsp; • Exportamos a SQL Workbench las tablas limpias.<br />

&emsp; &emsp; • Creamos relaciones entre las distintas tablas.<br />

&emsp; &emsp; • Lanzamos queries con SQL para comprobar el buen funcionamiento de la BBDD.<br />
