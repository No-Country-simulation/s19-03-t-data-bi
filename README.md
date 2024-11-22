<h1 align='center'>
 <b> PROYECTO YELP</b>
</h1>

# <h1 align="center">**`Sistema de Recomendacion de Comercios Gastronomicos`**</h1>

<p align='center'>
<img src ="image/Yelp.jfif" width="11000px" height="450px">
<p>

# Índice

1. [Introducción](#introducción)
2. [Contexto y Rol a Desarrollar](#contexto-y-rol-a-desarrollar)
3. [Fuente de Datos](#fuente-de-datos)
4. [Diccionario](#Diccionario)
5. [ETL y EDA](#etl-y-eda)
6. [Conclusiones](#Conclusiones)
7. [Colaboradores](#Equipo)
8. [Tecnologías Utilizadas](#tecnologías-utilizadas)


## **Introducción:**
En este proyecto, desarrollamos un sistema de recomendación para usuarios interesados en explorar locales gastronómicos en Estados Unidos, utilizando información obtenida de un dataset de Yelp. Este dataset incluye datos detallados sobre negocios, usuarios y sus interacciones, como reseñas, calificaciones y opiniones.

El objetivo principal es implementar un modelo que ofrezca recomendaciones personalizadas para ayudar a los usuarios a descubrir nuevos restaurantes y locales que coincidan con sus preferencias y hábitos.

A través de un análisis exhaustivo de los datos y la aplicación de técnicas avanzadas de análisis y modelado, este proyecto busca demostrar cómo los datos pueden convertirse en una herramienta clave para mejorar la experiencia de los consumidores y optimizar la visibilidad de los negocios gastronómicos.



## **Contexto y Rol a Desarrollar**

#### **Contexto:**

El presente proyecto se centra en el análisis de datos provenientes de Yelp, una de las plataformas más importantes de reseñas y recomendaciones de negocios, particularmente en el sector gastronómico en los Estados Unidos. Los datos abarcan el periodo comprendido entre los años **2005 y 2022**, proporcionando información histórica y actualizada sobre negocios, usuarios y sus interacciones.

El conjunto de datos incluye atributos clave como:
- Información general de los negocios (nombre, ubicación, categoría, horarios).
- Opiniones y calificaciones realizadas por los usuarios.
- Tendencias y patrones en las reseñas a lo largo del tiempo.

El objetivo es aprovechar esta información para desarrollar un sistema de recomendación que ofrezca sugerencias personalizadas a los usuarios, ayudándolos a descubrir locales gastronómicos relevantes en función de sus preferencias. A la par, este análisis permitirá identificar patrones y comportamientos del mercado, brindando insights valiosos para los dueños de negocios y los interesados en la industria gastronómica.

Este proyecto se apoya en herramientas modernas de ciencia de datos para procesar y transformar los datos, analizando grandes volúmenes de información de manera eficiente. Además, se complementa con técnicas avanzadas de análisis de sentimiento para comprender las opiniones de los usuarios y su impacto en los negocios.



#### **Rol a Desarrollar:**

Somos un equipo de **Data Scientists** que asumimos la responsabilidad de todo el flujo de trabajo de datos y análisis, incluyendo:

1. **Extracción y Transformación de los Datos (ETL):** 
   - Extracción del dataset de Yelp desde Google Drive y su integración en un Data Lake.
   - Limpieza, normalización y enriquecimiento de los datos.

2. **Análisis Exploratorio de Datos (EDA):**
   - Identificación de patrones en las reseñas y calificaciones.
   - Visualización de tendencias en el sector gastronómico.

3. **Diseño de la Base de Datos:**
   - Creación de una base de datos relacional que consolide los datos procesados.
   - Uso de modelos normalizados para garantizar eficiencia y escalabilidad.

4. **Análisis de Sentimiento:**
   - Aplicación de técnicas de Procesamiento del Lenguaje Natural (NLP) para comprender las emociones y percepciones de los usuarios en sus reseñas.

5. **Desarrollo del Sistema de Recomendación:**
   - Implementación de modelos de recomendación personalizados basados en técnicas colaborativas y contenido.

6. **Creación y Deploy de una Aplicación:**
   - Desarrollo de una aplicación interactiva con **Streamlit** para que los usuarios puedan explorar recomendaciones personalizadas.
   - Visualización de métricas clave mediante un dashboard dinámico en **Power BI**.

Nuestro enfoque integra tecnología avanzada y buenas prácticas en ciencia de datos, asegurando la creación de un producto final funcional y profesional, que responda tanto a las necesidades de los usuarios como a las expectativas del mercado.


## **Fuente de Datos**

Los datos utilizados en este proyecto fueron obtenidos del **sitio oficial de Yelp**, específicamente a través de su sección de datasets públicos, diseñada para proyectos de investigación y desarrollo en el ámbito de la ciencia de datos.  


**Link:** [Yelp Dataset](https://www.yelp.com/dataset)  

Este conjunto de datos ha sido procesado y preparado para su uso, respetando las políticas de uso de datos y privacidad definidas por Yelp.

## **Diccionario**

El dataset de Yelp contiene diferentes archivos JSON que representan diversas entidades relacionadas con negocios, reseñas, usuarios y más. Cada archivo tiene un formato estructurado y sigue la especificación JSON. A continuación, se presenta una descripción detallada de cada archivo y sus atributos:


### **1. Archivo `business.json`**
Contiene información sobre los negocios registrados en Yelp.

| **Atributo**          | **Descripción**                                                                                   | **Tipo de Dato** |
|------------------------|---------------------------------------------------------------------------------------------------|------------------|
| `business_id`         | Identificador único del negocio.                                                                 | String           |
| `name`                | Nombre del negocio.                                                                              | String           |
| `address`             | Dirección completa del negocio.                                                                  | String           |
| `city`                | Ciudad donde se encuentra el negocio.                                                            | String           |
| `state`               | Estado donde se ubica el negocio (código de 2 caracteres).                                       | String           |
| `postal_code`         | Código postal del negocio.                                                                       | String           |
| `latitude`            | Latitud geográfica del negocio.                                                                  | Float            |
| `longitude`           | Longitud geográfica del negocio.                                                                 | Float            |
| `stars`               | Calificación promedio del negocio (1 a 5 estrellas).                                             | Float            |
| `review_count`        | Número total de reseñas del negocio.                                                             | Integer          |
| `is_open`             | Estado del negocio (1: Abierto, 0: Cerrado).                                                     | Integer          |
| `attributes`          | Objeto con atributos adicionales del negocio (ej., estacionamiento, menús, etc.).                | Object           |
| `categories`          | Lista de categorías asociadas al negocio (ej., Restaurantes, Cafeterías).                        | Array[String]    |
| `hours`               | Objeto con horarios de operación (día como clave, rango de horas como valor).                    | Object           |

---

### **2. Archivo `review.json`**
Incluye las reseñas completas de los usuarios sobre los negocios.

| **Atributo**          | **Descripción**                                                                                   | **Tipo de Dato** |
|------------------------|---------------------------------------------------------------------------------------------------|------------------|
| `review_id`           | Identificador único de la reseña.                                                                | String           |
| `user_id`             | Identificador único del usuario que realizó la reseña.                                           | String           |
| `business_id`         | Identificador único del negocio asociado a la reseña.                                            | String           |
| `stars`               | Calificación otorgada en la reseña (1 a 5 estrellas).                                            | Integer          |
| `date`                | Fecha en que se realizó la reseña (YYYY-MM-DD).                                                  | String           |
| `text`                | Contenido textual de la reseña.                                                                  | String           |
| `useful`              | Número de votos útiles que recibió la reseña.                                                    | Integer          |
| `funny`               | Número de votos divertidos que recibió la reseña.                                                | Integer          |
| `cool`                | Número de votos geniales que recibió la reseña.                                                  | Integer          |

---

### **3. Archivo `user.json`**
Proporciona información sobre los usuarios registrados en Yelp.

| **Atributo**          | **Descripción**                                                                                   | **Tipo de Dato** |
|------------------------|---------------------------------------------------------------------------------------------------|------------------|
| `user_id`             | Identificador único del usuario.                                                                 | String           |
| `name`                | Nombre del usuario.                                                                              | String           |
| `review_count`        | Número total de reseñas escritas por el usuario.                                                 | Integer          |
| `yelping_since`       | Fecha en que el usuario se unió a Yelp (YYYY-MM-DD).                                             | String           |
| `friends`             | Lista de identificadores de amigos del usuario.                                                  | Array[String]    |
| `useful`              | Número de votos útiles enviados por el usuario.                                                  | Integer          |
| `funny`               | Número de votos divertidos enviados por el usuario.                                              | Integer          |
| `cool`                | Número de votos geniales enviados por el usuario.                                                | Integer          |
| `fans`                | Número de fans que tiene el usuario.                                                             | Integer          |
| `elite`               | Años en los que el usuario alcanzó el estatus de "élite".                                        | Array[Integer]   |
| `average_stars`       | Promedio de estrellas otorgadas en todas las reseñas del usuario.                                | Float            |

---

### **4. Archivo `checkin.json`**
Registra los check-ins realizados por los usuarios en los negocios.

| **Atributo**          | **Descripción**                                                                                   | **Tipo de Dato** |
|------------------------|---------------------------------------------------------------------------------------------------|------------------|
| `business_id`         | Identificador único del negocio asociado al check-in.                                            | String           |
| `date`                | Lista de marcas de tiempo separadas por comas en formato (YYYY-MM-DD HH:MM:SS).                   | String           |

---

### **5. Archivo `tip.json`**
Contiene sugerencias breves escritas por los usuarios sobre los negocios.

| **Atributo**          | **Descripción**                                                                                   | **Tipo de Dato** |
|------------------------|---------------------------------------------------------------------------------------------------|------------------|
| `text`                | Texto de la sugerencia.                                                                          | String           |
| `date`                | Fecha en que se escribió la sugerencia (YYYY-MM-DD).                                             | String           |
| `compliment_count`    | Número de cumplidos que recibió la sugerencia.                                                   | Integer          |
| `business_id`         | Identificador único del negocio asociado a la sugerencia.                                        | String           |
| `user_id`             | Identificador único del usuario que escribió la sugerencia.                                      | String           |

---

### **6. Archivo `photo.json`**
Proporciona datos sobre las fotos asociadas a los negocios.

| **Atributo**          | **Descripción**                                                                                   | **Tipo de Dato** |
|------------------------|---------------------------------------------------------------------------------------------------|------------------|
| `photo_id`            | Identificador único de la foto.                                                                  | String           |
| `business_id`         | Identificador único del negocio asociado a la foto.                                              | String           |
| `caption`             | Leyenda asociada a la foto.                                                                      | String           |
| `label`               | Categoría de la foto (food, drink, menu, inside, outside).                                       | String           |




## **ETL Y EDA**

## **Conclusiones**

## **Equipo**

<table>
  <thead>
    <tr>
      <th>Nombre</th>
      <th>Correo electrónico</th>
      <th>Rol</th>
      <th>LinkedIn</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Tomás Exequiel Del Barco</td>
      <td>tomasdelbarco07@gmail.com</td>
      <td>Data Science | Data Analyst</td>
      <td><a href="https://www.linkedin.com/in/tomás-del-barco-b74337229/" target="_blank"><img src="https://cdn-icons-png.flaticon.com/512/174/174857.png" alt="LinkedIn logo" width="20" height="20"></a></td>
    </tr>
    <tr>
      <td>Leandro Cano Cas</td>
      <td>leandrocano24@gmail.com</td>
      <td>Data Science | Data Analyst</td>
      <td><a href="https://www.linkedin.com/in/leandrocanoc/" target="_blank"><img src="https://cdn-icons-png.flaticon.com/512/174/174857.png" alt="LinkedIn logo" width="20" height="20"></a></td>
    </tr>
    <tr>
      <td>Miguel Ismerio</td>
      <td>mikeismerio@gmail.com</td>
      <td>Data Science | Data Analyst</td>
      <td><a href="https://www.linkedin.com/in/miguel-ismerio/" target="_blank"><img src="https://cdn-icons-png.flaticon.com/512/174/174857.png" alt="LinkedIn logo" width="20" height="20"></a></td>
    </tr>
    <tr>
      <td>Blas Fernando Pacios</td>
      <td>blasferp@gmail.com</td>
      <td>Data Science | Data Analyst</td>
      <td><a href="https://www.linkedin.com/in/blas-fernando-pacios-14a46a280//" target="_blank"><img src="https://cdn-icons-png.flaticon.com/512/174/174857.png" alt="LinkedIn logo" width="20" height="20"></a></td>
    </tr>
  </tbody>
</table>

## **💻 Tecnologías Utilizadas**

![Static Badge](https://img.shields.io/badge/PowerBI-gray?style=flat&logo=powerbi)
![Static Badge](https://img.shields.io/badge/Python-gray?style=flat&logo=python)
![Static Badge](https://img.shields.io/badge/-Pandas-gray?style=flat&logo=pandas)
![Static Badge](https://img.shields.io/badge/-Matplotlib-gray?style=flat&logo=matplotlib)
![Static Badge](https://img.shields.io/badge/-Seaborn-gray?style=flat&logo=seaborn)
![Static Badge](https://img.shields.io/badge/-Jupyter_Notebook-gray?style=flat&logo=jupyter)
![Static Badge](https://img.shields.io/badge/Visual_Studio_Code-gray?style=flat&logo=visual%20studio%20code&logoColor=white)
