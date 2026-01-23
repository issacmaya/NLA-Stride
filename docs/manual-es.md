<a href="images/NLA-Stride_LOGO2.png"><img src="images/NLA-Stride_LOGO2.png" width="250"></a>  

# Manual de usuario (Español)

> Este manual presenta las funciones y técnicas del complemento NLA-Stride para Blender, además de responder a algunas preguntas frecuentes sobre problemas conocidos.

---

## 📘 Índice

1. [Inicio rápido](#-inicio-rápido)  
2. [Resumen de funciones](#-resumen-de-funciones)      
3. [Preguntas frecuentes](#-preguntas-frecuentes) 
4. [Otros](#-otros) 
5. [Referencia técnica](#-referencia-técnica)

---

## 🚀 Inicio rápido

### 1. Instalación del complemento

1. Siga los pasos oficiales de instalación de Blender ( **[Guía de instalación general](https://docs.blender.org/manual/en/latest/editors/preferences/addons.html)** )

2. Después de la instalación, encontrará la herramienta **NLA Stride Tool** en la vista 3D de Blender, en la pestaña **Barra lateral → Animación**. 
<br>![alt text](images/img_1001.png)



---

### 2. Seleccionar objetos con animación  
<a href="images/img_1002.png">
  <img src="images/img_1002.png" width="650">
</a>  

Seleccione uno o más objetos que contengan datos de animación. Si contienen acciones estándar en lugar de clips NLA, consulte la sección "Envío por lotes a NLA" más adelante.  

---

### 3. Añadir a la lista  
![alt text](images/img_1003.png)  

⚠️ Nota: El complemento funciona basándose en la lista, independientemente de lo que esté seleccionado actualmente en la vista.  

---

### 4. Operaciones de alineación / desplazamiento NLA  
<a href="images/img_1004.png"><img src="images/img_1004.png" width="650"></a>  
<a href="images/img_1005.png"><img src="images/img_1005.png" width="650"></a>  
<a href="images/img_1006.png"><img src="images/img_1006.png" width="650"></a>  

Arriba se muestran demostraciones de las funciones de alineación y desplazamiento de NLA.  

---

### 5. Disfrute de la magia de la animación  
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

Agradecimiento especial a la marca taiwanesa [SANSUI](https://www.sansuitw.com/?gad_source=1&gad_campaignid=23085773952&gbraid=0AAAAAoXC59ENhboAZDO-y0zK4yQpidtXM&gclid=CjwKCAiAybfLBhAjEiwAI0mBBscjnZOEYBBY127EypNMfnL1h_Vqm_HACczeJBOqMK-euDJFPb1iAxoC7rkQAvD_BwE) por proporcionar los modelos de ejemplo.  

---

## 🧰 Resumen de funciones

#### 1. Fuente de datos 
![alt text](images/img_2001.png)  

- A : Inicializar y añadir seleccionados  
  Limpia la lista primero y luego añade los objetos seleccionados actualmente en la escena.  
<br>

- B : Limpiar lista  
  Elimina todos los datos de la lista.  
<br>

- C : Fuente de animación  
  Actualmente admite tres tipos: Animación de objeto / Animación de Shape Keys / Animación de material.  
<br>

- D : Añadir / Eliminar elementos de la lista  
  Añadir **no** limpia lo anterior; los objetos se añaden al final según el **orden de selección**. Si se selecciona un objeto que ya está en la lista, se moverá al final. La lógica de adición es diferente a la de A. La herramienta de eliminación también es distinta de 1-J.  
<br>

- E : Operaciones de lista (menú desplegable)  
  Consulte "1-1 Operaciones de lista" para más detalles.  
<br>

- F : Mover elemento hacia arriba / abajo  
  Ajusta el orden manualmente. Una vez ajustado, este resultado se define como el **"Orden original"**.  
<br>

- G : Enviar a NLA (menú desplegable)  
  Convierte la acción actual en clips NLA, solo para los objetos de la lista.  
<br>

- PS. [3. Significado de los iconos de la lista](#3-significado-de-los-iconos-de-la-lista)  

#### 1-1. Operaciones de lista
![alt text](images/img_2002.png)  

- H : Inicializar y añadir seleccionados  
  Limpia la lista primero y luego añade los objetos seleccionados actualmente en la escena.  
<br>

- I : Cuatro modos de ordenación  
  El más importante es **Restablecer orden original**, ya que este complemento registra dicha secuencia. Los otros tres son ordenaciones automáticas.  
<br>

- J : Eliminar seleccionados de la escena  
  Elimina objetos de la lista basándose en la selección actual de la vista. Esto es diferente de la herramienta de eliminación 1-D.  

#### 2. Posicionamiento de datos
![alt text](images/img_2003.png)  

- K : Tres modos de clip  
  - Clip único : Se enfoca solo en un clip específico.  
  - Pista única : Trata todos los clips de una misma pista como un grupo (las posiciones relativas no cambian).  
  - Todas las pistas : Equivale a cambiar todas las pistas del objeto simultáneamente (las posiciones relativas no cambian).  
<br>

- L : Tres puntos de posicionamiento  
  - Qué espacio : (Solo modo material) Se calcula de **arriba a abajo** en la interfaz.  
  - Qué pista : Se calcula de **abajo a arriba** en el editor NLA.  
  - Qué clip : Se calcula de **izquierda a derecha** en el editor NLA.  
<br>

  **!! Nota: Si el objetivo no está posicionado correctamente, NLA Stride no podrá ejecutar el desplazamiento.** #### 3. Herramientas de alineación NLA (Valores iniciales)
![alt text](images/img_2004.png)  

- M : Cinco objetivos de alineación  
  - Por fotograma de inicio máx : Se alinea con el punto de **inicio** del clip que comienza más **tarde** en la lista.  
  - Por fotograma de inicio mín : Se alinea con el punto de **inicio** del clip que comienza más **temprano** (uso común).  
  - Por fotograma de fin máx : Se alinea con el punto de **finalización** del clip que termina más **tarde** (uso común).  
  - Por fotograma de fin mín : Se alinea con el punto de **finalización** del clip que termina más **temprano**.  
  - Por tiempo actual : Se alinea con la posición actual del cabezal de reproducción (lo más común).  
<br>

- N : Tres modos de alineación  
  - Alinear al inicio : El lado izquierdo del clip se alinea con el objetivo. Generalmente usado para alineación de **inicio**.  
  - Alinear al centro : El centro del clip se alinea con el objetivo.  
  - Alinear al final : El lado derecho del clip se alinea con el objetivo. Generalmente usado para alineación de **final**.  
<br>

- O : Restablecer escala  
  Restaura el valor de escala de todos los clips NLA de la lista a 1.0.  


#### 4. Modo simple
![alt text](images/img_2005.png)  

- P : Modo de atenuación [(Descripción detallada)](#2-descripción-del-desplazamiento)  
  - Cuatro fórmulas de cálculo: 1. Lineal / 2. Entrada suave / 3. Salida suave / 4. Entrada y salida suaves.  
<br>

- Q : Cantidad de desplazamiento (Unidad: **fotogramas**)  
  - No se refiere al espacio entre clips individuales, sino a la diferencia total entre el primer y el último objeto de la lista (admite valores negativos).  
<br>

- R : Escala  
  - No es una escala incremental, sino la diferencia de escala entre el primer y el último objeto de la lista (0 ~ 1).  
<br>

- S : Ejecutar NLA Stride simple (hacer clic repetidamente acumula el cálculo).  
<br>

#### 5. Modo profesional
![alt text](images/img_2006.png)  
  **>> El núcleo de este complemento. Mediante ajustes sencillos, ajusta automáticamente el desplazamiento y la escala de los clips <<** - T : Modo de atenuación [(Descripción detallada)](#2-descripción-del-desplazamiento)  
  - Cuatro fórmulas de cálculo: 1. Lineal / 2. Entrada suave / 3. Salida suave / 4. Entrada y salida suaves.  
<br>

- U : Ajustar fotograma inicial  
  - Define el tiempo de **inicio** para toda la secuencia de animación de todos los objetos de la lista.  
<br>

- V : Relación de desplazamiento (Inicio)  
  - Se multiplica por el modo de atenuación (T) para calcular el valor de desviación, utilizado para posicionar automáticamente los puntos de inicio de todos los clips.  
<br>

- W : Modo de atenuación [(Descripción detallada)](#2-descripción-del-desplazamiento)  
  - Cuatro fórmulas de cálculo: 1. Lineal / 2. Entrada suave / 3. Salida suave / 4. Entrada y salida suaves.  
<br>

- X : Ajustar fotograma final  
  - Define el tiempo de **finalización** para toda la secuencia de animación de todos los objetos de la lista.  
<br>

- Y : Relación de desplazamiento (Fin)  
  - La relación de desplazamiento para los puntos finales de los clips.  
<br>

- Z : Ejecutar NLA Stride profesional (hacer clic repetidamente **no** acumula el cálculo).  
<br>


---

## ❓ Preguntas frecuentes


#### 1. ⚠️ Atención a los "Datos instanciados (Instanced Data)"

Este complemento procesa principalmente el desplazamiento y la alineación de los clips NLA en sí; **no** gestiona automáticamente las relaciones de "datos instanciados" dentro de Blender.  

#### ¿Qué son los datos instanciados?

Cuando **varios objetos comparten los mismos datos**, esos bloques de datos están "instanciados".  

- Por ejemplo:  
  - Dos objetos que comparten el mismo material.  
  - Compartir la misma acción (Action), malla (Mesh) u otros bloques de datos.  

En el editor NLA, pueden parecer dos clips independientes, pero en realidad **apuntan al mismo bloque de datos subyacente**.
Esto provoca que al usar **NLA Stride para desplazar**, el complemento parezca mover clips diferentes, pero en realidad está modificando el mismo dato, por lo que **no se logra el efecto de desplazamiento esperado**.


#### ✅ Solución (Siga los pasos de la imagen)

> 💡 **Idea central: Independizar los datos antes de realizar el desplazamiento.** Pasos (como se muestra en la imagen):  

1. Seleccione los objetos a procesar en la vista 3D.  
2. Vaya a **Objeto (Object) → Relaciones (Relations)**.  
3. Haga clic en **Hacer usuario único (Make Single User)**.  
4. Seleccione el tipo de datos que desea independizar (por ejemplo: Animación de objeto).  
5. Una vez independientes, use **NLA Stride** para realizar el desplazamiento.  



![alt text](images/img_3001.png)  

> Cuando los datos son independientes, cada objeto tendrá sus propios datos NLA exclusivos.
> Entonces NLA Stride podrá **ayudarle a desplazar los clips NLA de forma normal y previsible**.  

---


#### 2. ⚠️ Creación de NLA por lotes

El objetivo de este complemento son los clips NLA. Si los datos de animación aún no se han "enviado" (push down) para convertirse en clips NLA, no se verán afectados.  

#### ✅ Solución: Herramienta Enviar a NLA

El complemento ofrece una herramienta de conversión por lotes (indicada con flechas verdes abajo). Tenga en cuenta que afecta a los objetos **de la lista**, no a los seleccionados en la vista.  

![alt text](images/img_3002.png)  

---



## 📖 Otros


#### 1. Consejos de estrategia para alineación y desplazamiento

- Puede presionar **Alt A** en la vista 3D para deseleccionar todo y luego usar la función **Seleccionar objetos de la lista** para confirmar exactamente quiénes están en ella.  
<br>

- El **Orden** es crucial, ya que afecta directamente al estado de la animación tras el desplazamiento. Si es posible, use reglas de nomenclatura para decidir el orden. Si hay muchísimos objetos, procéselos por lotes.  
<br>

- Cuando todo se desordene, use las herramientas de alineación para unificarlos primero.  
<br>

- Como el desplazamiento de animaciones se vuelve muy sencillo, dedique su energía a crear un **movimiento perfecto**.  
<br>

- Si el diseño del movimiento incluye **Posición**, tenga cuidado al duplicar; al reproducir la animación, podría saltar de nuevo a la misma posición porque la información de ubicación está escrita en el NLA. En este caso, puede usar **Ctrl A** para aplicar transformaciones y escribir la nueva posición en los datos de **Transformaciones delta**.  
<br>![alt text](images/img_4001.png)  

---

#### 2. Descripción del desplazamiento
- Modo de superposición lineal :  
  - Modo simple :   
  <a href="images/img_4002.png"><img src="images/img_4002.png" width="650"></a>  
  El modo simple calcula con el modo de superposición basándose en el estado original (extremo izquierdo de la imagen). Como se ve, ajustando Desplazamiento 100 y Escala 1.5, el punto de inicio y la longitud (punto final) del último clip siempre serán los mismos; pero se puede ver que debido a los diferentes modos de atenuación, los puntos de inicio de los demás clips varían, creando diferentes sensaciones de desplazamiento.  

    ---
  - Modo profesional :    
  <a href="images/img_4003.png"><img src="images/img_4003.png" width="650"></a>  
  La diferencia con el modo simple es que el profesional permite configurar el control de inicio (Head) y fin (Tail), por lo que dispone de dos modos de atenuación configurables por separado.  
  
    ---
  - **Nota** :   
  <a href="images/img_4004.png"><img src="images/img_4004.png" width="650"></a>  
  Tenga en cuenta que si los dos modos de atenuación de inicio y fin son **diferentes**, debe vigilar si los clips de animación presentan problemas (se vuelven demasiado cortos o desaparecen).  

---

#### 3. Significado de los iconos de la lista

![alt text](images/img_3003.gif)  

Icono A : Modo de datos  
Icono B : Action representa datos de animación estándar (no NLA).  
Icono C : Datos NLA existentes.  

- El significado de los iconos B y C varía según el modo de datos de la columna A:  
  - ✔ : Contiene datos correctos que coinciden con el modo de la columna A.  
  - ・ : Contiene datos, pero **no** del tipo configurado en la columna A.  
  - ✕ : No se encuentran datos.  

Datos en la vista:  
| Elemento | Animación de objeto | Animación de material | Animación de Shape Keys |
|------|------|------|--------|
| **Clip NLA** | cube.049 | cube.050 | cube.051 | 
| **Acción activa** | cube.027 | cube.037 | cube.038 |  

- Otros : cube.000 (tiene los tres tipos de NLA) / cube.039 (sin ningún dato de animación).  

---

## 🔧 Referencia técnica

  [Manual oficial de Blender NLA](https://docs.blender.org/manual/en/latest/editors/nla/index.html)  

  [Manual oficial de la API de Blender](https://docs.blender.org/api/current/bpy.ops.nla.html)  

  


## 📘 Índice

1. [Inicio rápido](#-inicio-rápido)  
2. [Resumen de funciones](#-resumen-de-funciones)      
3. [Preguntas frecuentes](#-preguntas-frecuentes) 
4. [Otros](#-otros) 
5. [Referencia técnica](#-referencia-técnica)
