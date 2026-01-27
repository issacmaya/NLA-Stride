<a href="images/NLA-Stride_LOGO2.png"><img src="images/NLA-Stride_LOGO2.png" width="250"></a>  

# Manual de Usuario

> Este manual presenta las funciones y técnicas del complemento NLA-Stride para Blender, además de respuestas a algunos problemas conocidos comunes.

---

## 📘 Contenido

1. [Inicio Rápido](#Quick_Start)  
2. [Actualizaciones de Versión](#Version_Updates)
3. [Descripción de Funciones](#Feature_Overview)      
4. [Preguntas Frecuentes (FAQ)](#FAQ) 
5. [Otros](#Others) 
6. [Referencia Técnica](#Technical_Reference)

---

## 🚀 Inicio Rápido
<a id="Quick_Start"></a>

### 1. Instalación del Complemento

1. Siga los pasos oficiales de instalación de Blender ( **[Guía General de Instalación](https://docs.blender.org/manual/en/latest/editors/preferences/addons.html)** )

2. Después de la instalación, encontrará **NLA Stride Tool** en la vista 3D de Blender, en la pestaña **Barra Lateral → Animación**. 
<br>![alt text](images/img_1001.png)



---

### 2. Seleccionar Objetos con Animación  
<a href="images/img_1002.png">
  <img src="images/img_1002.png" width="650">
</a>  

Seleccione uno o más objetos que contengan datos de animación. Si usa animaciones estándar en lugar de animaciones NLA, consulte las instrucciones de "Creación masiva de NLA".

---

### 3. Añadir a la Lista

![alt text](images/img_1003.png)

⚠️ Nota: El complemento funciona basándose en la lista, independientemente de la selección de objetos en tiempo real en la vista.

---

### 4. Operaciones de Alineación / Desfase NLA


<a href="images/img_1004.png"><img src="images/img_1004.png" width="650"></a>  

<a href="images/img_1005.png"><img src="images/img_1005.png" width="650"></a>  

<a href="images/img_1006.png"><img src="images/img_1006.png" width="650"></a>  


Arriba se muestran demostraciones de las funciones de alineación y desfase NLA.

---

### 5. Disfrute de la Magia de la Animación

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

Agradecimientos especiales a la marca taiwanesa [SANSUI / 山水](https://www.sansuitw.com/?gad_source=1&gad_campaignid=23085773952&gbraid=0AAAAAoXC59ENhboAZDO-y0zK4yQpidtXM&gclid=CjwKCAiAybfLBhAjEiwAI0mBBscjnZOEYBBY127EypNMfnL1h_Vqm_HACczeJBOqMK-euDJFPb1iAxoC7rkQAvD_BwE) por proporcionar los modelos de ejemplo.

---
## 🌟 Actualizaciones de Versión
<a id="Version_Updates"></a>
  
#### v1.0.0 Actualizaciones Clave
- Exportar / Importar / Añadir Lista 
  ![alt text](images/v100_001.png)  
  1. Se añadieron tres nuevas funciones a las Operaciones de Lista.
  2. La exportación e importación se realizan mediante archivos *.json.
  3. "Añadir" agrega elementos al final de la lista.
  4. En caso de nombres duplicados, el elemento existente tiene prioridad.
#### v0.9.8 Actualizaciones Clave  
- Versión inicial pública  
---
## 🧰 Descripción de Funciones
<a id="Feature_Overview"></a>
 

#### 1. Fuente de Animación 

![alt text](images/img_2001.png)

- A : Inicializar y añadir seleccionados    
  Borra los datos de la lista actual y añade los objetos seleccionados en la Escena.  
  <br>
- B : Limpiar lista  
  Borra todos los datos dentro de la lista.  
  <br>
- C : Fuente de animación  
    Actualmente soporta tres tipos:  
    -  Animación de objeto  
    -  Animación de claves de forma (Shape Key)  
    -  Animación de material
  <br>
- D : Añadir / Eliminar objetos en la lista  
  Al añadir **no** se limpia la lista; los objetos se agregan al final **según el orden de selección**. Los objetos que ya estaban en la lista se moverán al final. Esto difiere del método A. La eliminación también es diferente de 1-J.  
  <br>

- E : Operaciones de lista (Menú desplegable)  
  Vea detalles en [1-1 Operaciones de lista](#List_Functions).
  <br>

- F : Mover elemento seleccionado Arriba / Abajo  
  Ajusta manualmente el orden. Una vez ajustado, se define como el **"Orden Original en Caché"**.
  <br>

- G : Enviar a NLA (Menú desplegable)  
  Convierte solo los objetos de la lista en clips NLA.
  <br>  
  
-  PS. [3. Significado de los iconos en la lista](#List_Icon_Meanings)

#### 1-1. Operaciones de lista
<a id="List_Functions"></a>

![alt text](images/img_2002.png)

- H : Inicializar y añadir seleccionados   
  Limpia los datos de la lista y añade los objetos seleccionados en la Escena.
  <br>

- I : Cuatro estados de ordenación    
  El más importante es el **Orden original** registrado por el complemento; los otros tres son estados de ordenación temporales.
  <br>

- J : Eliminar selección de escena   
  Elimina de la lista los objetos seleccionados actualmente en la escena 3D (diferente de 1-D).
  <br>

#### 2. Especificar clips de desfase

![alt text](images/img_2003.png)

- K : Tres modos de clip (Modo de clip)  
  - Clip único : Afecta solo a un clip específico.
  - Pista única : Trata todos los clips de una pista como una sola unidad (las posiciones relativas se mantienen).
  - Todas las pistas : Todas las pistas del objeto cambian juntas (las posiciones relativas se mantienen).
  <br>

- L : Tres localizadores  
  - Qué ranura : Solo para Modo Material, se calcula de **arriba hacia abajo** en la interfaz NLA.
  - Qué pista : Se calcula de **abajo hacia arriba** en la interfaz NLA.
  - Qué clip : Se calcula de **izquierda a derecha** en la interfaz NLA.
  <br>

  **!! NOTA: Si el objetivo no se especifica correctamente, el desfase NLA no podrá ejecutarse.**

#### 3. Herramientas de alineación NLA (Valores iniciales)
![alt text](images/img_2004.png)

- M : Cinco modos de alineación (Modo alineación)  
  - Por fotograma inicial máx. : Basado en el **último** punto de inicio de los clips en la lista.
  - Por fotograma inicial mín. : Basado en el **primer** punto de inicio de los clips en la lista (Común).
  - Por fotograma final máx. : Basado en el **último** punto final de los clips en la lista (Común).
  - Por fotograma final mín. : Basado en el **primer** punto final de los clips en la lista.
  - Por tiempo actual : Basado en la posición actual del cabezal de reproducción (Más usado).
  <br>

- N : Tres métodos de alineación  
  - Alinear inicio : Alinea el lado izquierdo con el objetivo (común para puntos de inicio).
  - Alinear medio : Alinea el centro con el objetivo.
  - Alinear fin : Alinea el lado derecho con el objetivo (común para puntos finales).
  <br>

- O : Restablecer escala  
  Devuelve el valor de escala de todos los clips NLA en la lista a 1.
  <br>


#### 4. Modo Simple

![alt text](images/img_2005.png)  
- P : Atenuación en modo simple [(Descripción detallada)](#Stride_Description)  
  Hay cuatro fórmulas para el cálculo del desfase: 1. Lineal / 2. Entrada suave (Ease In) / 3. Salida suave (Ease Out) / 4. Entrada/Salida suave (Ease In Out).
  <br>

- Q : Cantidad de desfase (Unidad: **Fotogramas**)  
  Es la diferencia total entre el primer y el último objeto de la lista (admite valores negativos).
  <br>

- R : Escala  
  Es la diferencia de escala entre el primer y el último objeto de la lista (0 ~ 1).
  <br>

- S : Ejecutar Simple NLA Stride (Hacer clic repetidamente acumula el cálculo).
  <br>

#### 5. Modo Profesional
![alt text](images/img_2006.png)  
  **>> El núcleo de este complemento: con ajustes sencillos, el desfase y la escala de los clips se ajustan automáticamente <<**

- T : Atenuación inicial Pro [(Descripción detallada)](#Stride_Description)  
  Cuatro fórmulas: 1. Lineal / 2. Ease In / 3. Ease Out / 4. Ease In Out.
  <br>

- U : Ajustar fotograma inicial  
  Establece el tiempo de **inicio** de la animación total para todos los objetos de la lista.
  <br>

- V : Relación de desfase (Inicio)    
  La cantidad de desfase multiplicada por la atenuación (T), usada para configurar automáticamente los puntos de inicio de todos los clips.
  <br>

- W : Atenuación final Pro [(Descripción detallada)](#Stride_Description)    
  Cuatro fórmulas: 1. Lineal / 2. Ease In / 3. Ease Out / 4. Ease In Out.
  <br>

- X : Ajustar fotograma final    
  Establece el tiempo de **fin** de la animación total para todos los objetos de la lista.
  <br>

- Y : Relación de desfase (Fin)    
  Diferencia entre el primer y el último objeto (admite valores negativos).
  <br>

- Z : Ejecutar Profesional NLA Stride (Hacer clic repetidamente **no acumula**).
  <br>


---

## ❓ Preguntas Frecuentes (FAQ)
<a id="FAQ"></a>


#### 1. ⚠️ Atención a los detalles de "Datos Instanciados (Instanced Data)"

Este complemento se enfoca principalmente en el desplazamiento y alineación de los clips NLA mismos,  
y **no** gestiona automáticamente las relaciones de "Datos Instanciados" de Blender.

#### ¿Qué son datos instanciados?

Cuando **múltiples objetos comparten el mismo bloque de datos**, esos datos están "Instanciados".

- Por ejemplo:  
  - Dos objetos que comparten el mismo material.  
  - O comparten la misma acción (animación), malla u otros bloques de datos.  

En el Editor NLA parecen clips independientes, pero **apuntan a los mismos datos subyacentes**.
Como resultado, al usar **NLA Stride para el desfase**, el complemento parece mover los clips, pero como comparten datos, **no se logrará el efecto de desfase deseado**.


#### ✅ Solución (Siga estos pasos)

> 💡 **Clave: Haga que los datos sean "usuario único" (Single User) antes del desfase.**

Pasos (como se muestra en la imagen):

1. Seleccione los objetos en la vista 3D.  
2. Vaya a **Objeto → Relaciones (Relations)**.  
3. Haga clic en **Hacer usuario único (Make Single User)**.  
4. Seleccione el tipo de datos necesario (ej. Animación de objeto).
5. Una vez que los datos son independientes, use **NLA Stride** para el desfase.  



![alt text](images/img_3001.png)

> Una vez independientes, cada objeto tiene sus propios "datos NLA reales".
> NLA Stride puede entonces **desplazar los clips NLA de forma normal y predecible**.
---


#### 2. ⚠️ Creación masiva de NLA

Este complemento trabaja con clips NLA. Las animaciones que no se han convertido en clips NLA (Acciones activas) no se verán afectadas.

#### ✅ Solución: Herramienta de conversión masiva

El complemento ofrece una herramienta para convertir objetos de la lista a NLA de una sola vez (flecha verde abajo). Nota: esto afecta a la **Lista**, no solo a la selección 3D.

![alt text](images/img_3002.png)

---



## 📖 Otros
<a id="Others"></a>


#### 1. Consejos para estrategias de Alineación y Desfase

- Puede presionar **Alt A** en la vista 3D para deseleccionar todo y luego usar la función **Seleccionar objetos de la lista** para verificar qué hay exactamente en su lista.  
<br>

- El **orden** es crucial porque afecta directamente al estado de la animación tras el desfase. Si es posible, use nombres para determinar el orden. Para muchos objetos, considere procesar por lotes o usar la función [`Exportar / Importar`](#Version_Updates).  
<br>

- Si las cosas se complican, use las herramientas de alineación para sincronizar todo de vuelta a un punto de partida.  
<br>

- Dado que el desfase de animación ahora es muy sencillo, concéntrese en crear un **movimiento perfecto**.  
<br>

- Sobre el diseño de movimiento: Si la **Posición** tiene fotogramas clave, tenga en cuenta que al copiar, la animación puede saltar a la misma posición original. En ese caso, use **Ctrl A** (Aplicar transformación) para escribir la nueva ubicación en los datos de **Transformación Delta**.  
  <br>![alt text](images/img_4001.png)  

---

#### 2. Descripción de Stride
<a id="Stride_Description"></a>

- Modo de apilamiento lineal :  
  - Modo Simple :   
  <a href="images/img_4002.png"><img src="images/img_4002.png" width="650"></a>  
  El modo simple calcula basándose en el estado original (imagen a la izquierda). Por ejemplo, con Desfase 100 y Escala 1.5, el punto de inicio y longitud del último clip siempre serán los mismos; pero los diferentes modos de atenuación crearán diferentes puntos de inicio intermedios, dando una sensación de desfase distinta.

    ---
  - Modo Profesional :    
  <a href="images/img_4003.png"><img src="images/img_4003.png" width="650"></a>  
  A diferencia del modo simple, el modo profesional puede controlar el inicio y el fin por separado, permitiendo una atenuación distinta para cada uno.  
  
    ---
  - **Atención** :   
  <a href="images/img_4004.png"><img src="images/img_4004.png" width="650"></a>  
  Si los modos de atenuación para inicio y fin son **distintos**, preste atención a si los clips de animación se vuelven demasiado cortos o desaparecen.
---

#### 3. Significado de los iconos en la lista
<a id="List_Icon_Meanings"></a>

![alt text](images/img_3003.gif)

Icono A : Modo de datos
Icono B : Action representa datos de animación estándar (no NLA)
Icono C : Datos NLA disponibles

- El significado de los símbolos en B y C cambia según el Modo de datos seleccionado en la columna A:
  - ✔ : Contiene datos **correctos** que coinciden con el modo en A.
  - ・ : Contiene datos, pero **no** del tipo establecido en A.
  - ✕ : No contiene datos.

Datos en el ejemplo:
| Elemento | Animación objeto | Animación material | Animación Shape Key |
|------|------|------|--------|
| **Clip NLA** | cube.049 | cube.050 | cube.051 | 
| **Acción activa** | cube.027 | cube.037 | cube.038 | 

- Otros: cube.000 (Tiene los 3 tipos de NLA) / cube.039 (Sin ningún dato de animación)

---




## 🔧 Referencia Técnica
<a id="Technical_Reference"></a>

  [Manual Oficial de Blender NLA](https://docs.blender.org/manual/en/latest/editors/nla/index.html)

  [Manual Oficial de Blender API](https://docs.blender.org/api/current/bpy.ops.nla.html)

  


## 📘 Contenido

1. [Inicio Rápido](#Quick_Start) 
2. [Actualizaciones de Versión](#Version_Updates) 
3. [Descripción de Funciones](#Feature_Overview)      
4. [Preguntas Frecuentes (FAQ)](#FAQ) 
5. [Otros](#Others) 
6. [Referencia Técnica](#Technical_Reference)