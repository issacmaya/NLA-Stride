<a href="images/NLA-Stride_LOGO2.png"><img src="images/NLA-Stride_LOGO2.png" width="250"></a>  

# Manual de usuario (Español)

> Este manual presenta las funciones y consejos para el complemento NLA-Stride de Blender, así como respuestas a algunos problemas comunes conocidos.

---

## 📘 Contenido

1. [Inicio rápido](#-inicio-rápido)  
2. [Novedades de la versión](#-novedades-de-la-versión)
3. [Descripción general de funciones](#-descripción-general-de-funciones)      
4. [Preguntas frecuentes](#-preguntas-frecuentes) 
5. [Otros consejos](#-otros-consejos) 
6. [Referencia técnica](#-referencia-técnica)

---

## 🚀 Inicio rápido

### 1. Instalación del complemento

1. Siga los pasos oficiales de instalación de Blender ( **[Guía general de instalación](https://docs.blender.org/manual/en/latest/editors/preferences/addons.html)** )

2. Después de la instalación, puede encontrar **NLA Stride Tool** en la vista 3D de Blender, pestaña **Barra lateral → Animación**. 
<br>![alt text](images/img_1001.png)



---

### 2. Seleccionar objetos con animación  
<a href="images/img_1002.png">
  <img src="images/img_1002.png" width="650">
</a>  

Seleccione uno o más objetos que contengan datos de animación. Si utiliza animaciones estándar en lugar de clips NLA, consulte las instrucciones de "Envío masivo a NLA".

---

### 3. Añadir a la lista

![alt text](images/img_1003.png)

⚠️ Nota: El complemento funciona basándose en la lista, independientemente de los objetos seleccionados actualmente en la escena.

---

### 4. Operaciones de Alineación / Desplazamiento de NLA


<a href="images/img_1004.png"><img src="images/img_1004.png" width="650"></a>  

<a href="images/img_1005.png"><img src="images/img_1005.png" width="650"></a>  

<a href="images/img_1006.png"><img src="images/img_1006.png" width="650"></a>  


Los diagramas anteriores ilustran las funciones de alineación y desplazamiento de NLA.

---

### 5. Disfrute de la animación

<a href="images/DEMO_01.mp4">
  <img src="images/DEMO_01.gif" width="720">
</a>  

<a href="images/DEMO_02.mp4">
  <img src="images/DEMO_02.gif" width="720">
</a>  

<a href="images/DEM3_03.mp4">
  <img src="images/DEMO_03.gif" width="720">
</a>  

<a href="images/DEM3_04.mp4">
  <img src="images/DEMO_04.gif" width="720">
</a>  

Modelo de ejemplo gracias a [SANSUI Taiwan](https://www.sansuitw.com/?gad_source=1&gad_campaignid=23085773952&gbraid=0AAAAAoXC59ENhboAZDO-y0zK4yQpidtXM&gclid=CjwKCAiAybfLBhAjEiwAI0mBBscjnZOEYBBY127EypNMfnL1h_Vqm_HACczeJBOqMK-euDJFPb1iAxoC7rkQAvD_BwE) por su provisión.

---
## 🌟 Novedades de la versión
#### v1.0.0 Novedades
- Exportar / Importar / Añadir lista  
  ![alt text](images/v100_001.png)  
  1. Se agregaron tres funciones dentro de las operaciones de lista.
  2. La exportación e importación utilizan el formato *.json.
  3. "Añadir" agregará elementos al final de la lista.
  4. Si hay nombres duplicados, el primero encontrado tendrá prioridad.
#### v0.9.8 Novedades  
- Lanzamiento público inicial  
---
## 🧰 Descripción general de funciones

#### 1. Herramienta de inicialización de lista 

![alt text](images/img_2001.png)

- A : Inicializar y añadir seleccionados    
  Limpia los datos de la lista y luego añade los objetos seleccionados actualmente en la escena.
  <br>
- B : Limpiar lista  
  Borra todos los datos dentro de la lista.
  <br>
- C : Fuente de animación  
    Actualmente admite tres tipos:
    - Animación de objeto  
    - Animación de Shape Key (Formas)  
    - Animación de material
  <br>
- D : Añadir / Eliminar objetos de la lista  
  Añadir **no** limpiará los elementos existentes; los objetos se añaden al final **en el orden de selección**. Eliminar aquí es diferente de 1-J.
  <br>

- E : Operaciones de lista (Menú desplegable)  
  Ver [1-1 Operaciones de lista](#1-1-operaciones-de-lista) para más detalles.
  <br>

- F : Mover elemento seleccionado Arriba / Abajo  
  Ajuste manualmente el orden. Si se ajusta el orden, el resultado se define como el **"Orden original"**.
  <br>

- G : Enviar animación a NLA (Menú desplegable)  
  Convierte animaciones en clips NLA solo para los objetos de la lista.
  <br>  
  
-  PD. [3. Leyenda de iconos de la lista](#3-leyenda-de-iconos-de-la-lista)

#### 1-1. Operaciones de lista

![alt text](images/img_2002.png)

- H : Inicializar y añadir seleccionados   
  Limpia los datos de la lista y añade los objetos seleccionados actualmente.
  <br>

- I : Modos de ordenación    
  Incluye **Orden original** (que el complemento rastrea) y otros tres métodos de ordenación.
  <br>

- J : Eliminar seleccionados en la escena   
  Elimina de la lista los objetos seleccionados actualmente en la escena.
  <br>

#### 2. Especificar clips de desplazamiento

![alt text](images/img_2003.png)

- K : Modo de clip  
  - Clip único: Se dirige solo a un clip específico.
  - Pista única: Trata todos los clips de una pista como una sola unidad (mantiene las posiciones relativas).
  - Todas las pistas: Todas las pistas del objeto cambian juntas (mantiene las posiciones relativas).
  <br>

- L : Posicionamiento de Ranura/Pista/Clip  
  - Ranura: Solo modo de material, se calcula de **arriba a abajo** en la interfaz.
  - Pista: Se calcula de **abajo hacia arriba** en el editor NLA.
  - Clip: Se calcula de **izquierda a derecha** en el editor NLA.
  <br>

  **!! Nota: Si el objetivo no está correctamente localizado, NLA Stride no podrá funcionar.**

#### 3. Herramientas de alineación NLA (Valores iniciales)
![alt text](images/img_2004.png)

- M : Modo de alineación objetivo  
  - Por fotograma de inicio máx.: Se alinea al **inicio** del clip que empieza más **tarde** en la lista.
  - Por fotograma de inicio mín.: Se alinea al **inicio** del clip que empieza más **temprano** en la lista (Común).
  - Por fotograma final máx.: Se alinea al **final** del clip que termina más **tarde** en la lista (Común).
  - Por fotograma final mín.: Se alinea al **final** del clip que termina más **temprano** en la lista.
  - Por tiempo actual: Se alinea a la posición actual del cabezal de reproducción (Más común).
  <br>

- N : Posición de alineación  
  - Alinear al inicio: Alinea el lado izquierdo con el objetivo.
  - Alinear al centro: Alinea el centro con el objetivo.
  - Alinear al final: Alinea el lado derecho con el objetivo.
  <br>

- O : Restablecer escala  
  Restablece la escala de todos los clips NLA especificados en la lista a 1.
  <br>


#### 4. Modo simple

![alt text](images/img_2005.png)  
- P : Atenuación (Falloff) [(Descripción detallada)](#2-descripción-del-desplazamiento)  
  Cuatro fórmulas de cálculo: 1. Lineal / 2. Ease In / 3. Ease Out / 4. Ease In Out.
  <br>

- Q : Cantidad de desplazamiento (Unidad: **Fotogramas**)  
  No es el espacio equidistante entre clips, sino la diferencia total entre el primer y el último objeto de la lista (permite valores negativos).
  <br>

- R : Escala  
  No es el escalado equidistante, sino la diferencia de escala entre el primer y el último objeto (0 ~ 1).
  <br>

- S : Ejecutar NLA Stride simple (Los valores se acumulan si se presiona repetidamente).
  <br>

#### 5. Modo profesional
![alt text](images/img_2006.png)  
  **>> La característica principal: defina los puntos de inicio y fin, y los clips se desplazarán y escalarán automáticamente. <<**

- T : Atenuación de inicio Pro [(Descripción detallada)](#2-descripción-del-desplazamiento)  
  Fórmula de cálculo de desplazamiento: Lineal, Ease In, Ease Out o Ease In Out.
  <br>

- U : Establecer fotograma de inicio  
  Establece el tiempo de **Inicio** global para toda la secuencia de animación en la lista.
  <br>

- V : Relación de desplazamiento  
  La cantidad de desplazamiento multiplicada por el modo de atenuación (T), utilizada para automatizar el posicionamiento del fotograma de inicio.
  <br>

- W : Atenuación de fin Pro [(Descripción detallada)](#2-descripción-del-desplazamiento)    
  Fórmula de cálculo de desplazamiento: Lineal, Ease In, Ease Out o Ease In Out.
  <br>

- X : Establecer fotograma final    
  Establece el tiempo de **Fin** global para toda la secuencia de animación en la lista.
  <br>

- Y : Relación de desplazamiento    
  Diferencia entre los fotogramas finales del primer y último objeto (permite valores negativos).
  <br>

- Z : Ejecutar NLA Stride profesional (Los valores **no** se acumulan).
  <br>


---

## ❓ Preguntas frecuentes


#### 1. ⚠️ Atención a los detalles de "Datos instanciados (Instanced Data)"

Este complemento se dirige a los clips NLA en sí mismos para el desplazamiento y la alineación,  
**no** gestiona automáticamente las relaciones de "Datos instanciados" de Blender.

#### ¿Qué son los datos instanciados?

Cuando **múltiples objetos comparten el mismo bloque de datos**, esos datos están "Instanciados".

- Por ejemplo:  
  - Dos objetos que comparten el mismo Material.  
  - Compartir la misma Acción, Malla u otros bloques de datos.  

En el editor NLA, parecen dos clips independientes, pero en realidad **apuntan a los mismos datos entre bastidores**.
Como resultado, al usar **NLA Stride para desplazar**, el complemento mueve los clips, pero dado que influyen en los mismos datos subyacentes, **no se logrará el efecto de desplazamiento esperado**.


#### ✅ Solución (Siga la captura de pantalla a continuación)

> 💡 **Práctica clave: Independizar los datos antes de desplazar**

Pasos:

1. Seleccione los objetos en la vista 3D.  
2. Vaya a **Objeto → Relaciones (Relations)**.  
3. Haga clic en **Hacer usuario único (Make Single User)**.  
4. Seleccione los tipos de datos que deben ser independientes.
5. Una vez que los datos sean independientes, use **NLA Stride** para desplazar.  



![alt text](images/img_3001.png)

> Una vez que los datos son independientes, cada objeto tiene sus propios "Datos NLA verdaderamente únicos".
> NLA Stride podrá entonces **desplazar los clips NLA de forma normal y predecible**.
---


#### 2. ⚠️ Envío masivo a NLA

Este complemento funciona específicamente sobre clips NLA. Los datos de animación que no se hayan enviado a NLA no se verán afectados.

#### ✅ Solución: Herramienta de conversión masiva

El complemento proporciona una herramienta para enviar animaciones a NLA para todos los objetos **en la lista** (flecha verde abajo). Nota: esto se dirige a la lista, no solo a la selección 3D.

![alt text](images/img_3002.png)

---



## 📖 Otros consejos


#### 1. Estrategia de alineación y desplazamiento

- Puede presionar **Alt A** en la vista 3D para deseleccionar todo, luego use la función **Seleccionar objetos de la lista** para verificar exactamente qué objetos están en su lista.  
<br>

- Debido a que el **Orden** es crucial (afecta directamente al resultado del desplazamiento), intente usar nombres para determinar el orden. Si tiene muchos objetos, procéselos por lotes.  
<br>

- Si las cosas se complican, use la herramienta de alineación para restablecer todo a un punto de inicio unificado.  
<br>

- Dado que desplazar se vuelve fácil, concéntrese primero en crear un **movimiento dinámico perfecto**.  
<br>

- Si su animación involucra la **Posición (Location)**, los duplicados podrían volver a la misma posición. Use **Ctrl A** para aplicar transformaciones a los datos de **Delta Transform**.  
  <br>![alt text](images/img_4001.png)  

---

#### 2. Descripción del desplazamiento
- Modo de atenuación lineal:  
  - Modo simple:   
  <a href="images/img_4002.png"><img src="images/img_4002.png" width="650"></a>  
  El modo simple calcula basándose en el estado original (izquierda). Por ejemplo: Desplazamiento 100, Escala 1.5. El inicio y la longitud del último clip coincidirán con los ajustes, pero los clips intermedios variarán según el modo de atenuación.

    ---
  - Modo profesional:    
  <a href="images/img_4003.png"><img src="images/img_4003.png" width="650"></a>  
  A diferencia del modo simple, el modo profesional controla tanto el inicio (Head) como el final (Tail), permitiendo modos de atenuación separados para cada uno.  
  
    ---
  - **Nota**:   
  <a href="images/img_4004.png"><img src="images/img_4004.png" width="650"></a>  
  Si los modos de atenuación de inicio y fin son **diferentes**, tenga cuidado de que los clips no se vuelvan demasiado cortos o desaparezcan.
---

#### 3. Leyenda de iconos de la lista

![alt text](images/img_3003.gif)

Icono A: Modo de fuente de animación
Icono B: La Acción representa datos de animación generales (Aún no en NLA)
Icono C: Datos NLA disponibles

- Los símbolos en B y C cambian según el modo de fuente (A):
  - ✔ : Contiene datos **Correctos** que coinciden con el Modo A.
  - ・: Contiene datos, pero **NO** coinciden con el Modo A.
  - ✕ : No se encontraron datos.

Datos en el ejemplo:
| Elemento | Anim. Objeto | Anim. Material | Anim. Shape Key |
|------|------|------|--------|
| **Clip NLA** | cube.049 | cube.050 | cube.051 | 
| **Acción activa** | cube.027 | cube.037 | cube.038 | 

- Otros: cube.000 (Tiene NLA para los 3 tipos) / cube.039 (Sin datos de animación)

---




## 🔧 Referencia técnica

  [Manual oficial de NLA de Blender](https://docs.blender.org/manual/en/latest/editors/nla/index.html)

  [Manual oficial de la API de Blender](https://docs.blender.org/api/current/bpy.ops.nla.html)

  


## 📘 Contenido

1. [Inicio rápido](#-inicio-rápido) 
2. [Novedades de la versión](#-novedades-de-la-versión) 
3. [Descripción general de funciones](#-descripción-general-de-funciones)      
4. [Preguntas frecuentes](#-preguntas-frecuentes) 
5. [Otros consejos](#-otros-consejos) 
6. [Referencia técnica](#-referencia-técnica)