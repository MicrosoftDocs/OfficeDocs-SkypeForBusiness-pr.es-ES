---
title: "Activar y usar el panel de calidad de llamada para Teams de Microsoft y Skype empresarial Online"
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.date: 11/17/2017
ms.audience: Admin
ms.topic: article
f1_keywords:
- ms.lync.lac.ToolsCallQualityDashboard
ms.prod: office-online-server
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.custom: Adm_O365_FullSet
ms.assetid: 553fa13c-92d2-4d5c-a3d5-41a073cb047c
description: "See how to turn on and use the Skype for Business Online Call Quality Dashboard and get summary reports of quality of calls. "
---

# Activar y usar el panel de calidad de llamada para Teams de Microsoft y Skype empresarial Online

Obtenga información sobre cómo configurar la organización de Office 365 para usar el panel de calidad de llamadas para supervisar la calidad de la llamada.
  
> [!IMPORTANT]
> Este artículo se ha traducido con traducción automática; vea la [declinación de responsabilidades](553fa13c-92d2-4d5c-a3d5-41a073cb047c.md#MT_Footer). Para su referencia, puede encontrar la versión en inglés de este artículo [aquí](https://support.office.com/en-us/article/553fa13c-92d2-4d5c-a3d5-41a073cb047c). 
  
El panel de calidad de llamadas (CQD) para Equipos de Microsoft y Skype Empresarial Online permite obtener recomendaciones sobre la calidad de llamadas realizadas mediante servicios de Equipos de Microsoft y Skype Empresarial. Este tema describe los pasos que debe realizar para iniciar la recopilación de datos.
  
> [!NOTE]
> Los informes detallados del CQD actualmente están disponibles para todos los clientes, pero solo como parte de la versión preliminar técnica. 
  
## Últimos cambios y actualizaciones

Los cambios más recientes a CQD son los siguientes:
  
- Incluye datos Equipos de Microsoft además de los datos de Skype Empresarial Online.
    
- Informes de resumen incluyen un filtro de producto para seleccionar todos los datos, Equipos de Microsoft datos o datos de Skype Empresarial Online.
    
Consulte este artículo para obtener una lista de [Dimensiones y medidas disponibles en panel de calidad de llamada para Teams de Microsoft y Skype empresarial Online](dimensions-and-measures-available-in-call-quality-dashboard-for-microsoft-teams.md).
  
> [!NOTE]
> Podrá encontrar información sobre las actualizaciones y los cambios que se han realizado en el panel haciendo clic en **¡Buenas noticias!** en el panel. También puede ir al[Panel de calidad de llamadas](https://aka.ms/CQDOnline). 
  
## Activar los informes de resumen de paneles (CQD) de calidad de llamada de Microsoft

Antes de empezar a utilizar el CQD, debe activarlo para su organización Office 365.
  
1. Inicie sesión en su organización Office 365 con una cuenta de administrador y, a continuación, seleccione el icono de **Administrador** para abrir el centro de administración.
    
2. En el panel izquierdo, en **los centros de administración**, seleccione **Skype empresarial** para abrir el centro de administración de Skype Empresarial.
    
3. En el centro de administración de Skype Empresarial, seleccione **Herramientas** en el panel izquierdo y, a continuación, seleccione **Skype para Business Online panel calidad de llamadas**.
    
     ![Skype for Business tools](../images/6cc7f80f-b8e2-4a9b-aab8-ac871d07a261.png)
  
4. En la página que se abre, inicie sesión con su cuenta de administrador Global y, a continuación, proporcione las credenciales de la cuenta cuando se le solicite.
    
     ![CQD Login](../images/ac4c1699-d8c1-4bda-af30-0fec35b5fd22.png)
  
Después de iniciar sesión, una vez activado, el CQD comenzará recopilar y procesar datos.
  
> [!NOTE]
> Puede tardar un par de horas para procesar datos suficientes para mostrar resultados significativos en los informes. 
  
## Características del panel de calidad de llamadas de Skype Empresarial Online
<a name="BKMK_FeaturesOfTheCQD"> </a>

Los informes de resumen del CQD proporcionan un subconjunto de las características planificadas para los informes detallados. Las diferencias entre las dos ediciones se resumen aquí:
  
|**Característica**|**Informes de resumen**|**Informes detallados**|
|:-----|:-----|:-----|
|Métrica de uso compartido de aplicaciones  <br/> |No  <br/> |Sí  <br/> |
|Soporte informativo del edificio de los clientes  <br/> |Sí  <br/> |Sí  <br/> |
|Soporte del análisis de exploración en profundidad  <br/> |No  <br/> |Sí  <br/> |
|Métricas de confiabilidad de medios  <br/> |No  <br/> |Sí  <br/> |
|Informes de cuadro  <br/> |Sí  <br/> |Sí  <br/> |
|Informes de información general  <br/> |Sí  <br/> |Sí  <br/> |
|Conjunto de informes por usuario  <br/> |No  <br/> |Sí  <br/> |
|Personalización del conjunto de informes (agregar, eliminar, modificar informes)  <br/> |No  <br/> |Sí  <br/> |
|Métricas de pantalla compartida basada en vídeo  <br/> |No  <br/> |Sí  <br/> |
|Métricas de vídeo  <br/> |No  <br/> |Sí  <br/> |
|Cantidad de datos disponibles  <br/> |Últimos 6 meses  <br/> |Últimos 6 meses  <br/> |
|Datos de Microsoft Teams  <br/> |Sí  <br/> |Sí  <br/> |
   
### Informes de cuadro

Ambas ediciones de CQD proporcionan un-de-predefinidas experiencia, que le da llamar métrica de calidad sin necesidad de crear los nuevos informes. Una vez que se procesan en el servidor back-end, puede empezar a ver los datos de la calidad de llamadas en los informes.
  
### Informes de información general

Ambas ediciones del CQD proporcionan un punto de entrada de alto nivel a la información general de calidad de llamadas, pero la forma en la que se presenta la información en los Informes de resumen es diferente de la de los Informes detallados.
  
Los informes de resumen proporcionan una vista simplificada del informe en una página con pestañas que permite a los usuarios buscar y entender rápidamente el estado y las tendencias generales de la calidad de las llamadas.
  
Las cuatro pestañas incluyen:
  
- **Calidad de llamada general**: proporciona información sobre todas las secuencias, que es una agregación de secuencias de cliente de servidor y secuencias de cliente de cliente, así como independiente cliente de servidor y secuencias de cliente de cliente, en el formulario de tendencias mensuales y diarias.
    
- **Servidor-Cliente**: proporciona detalles adicionales para las transmisiones entre los puntos de conexión Servidor y Cliente.
    
- **Cliente-Cliente**: proporciona detalles adicionales para las transmisiones entre dos puntos de conexión Cliente.
    
- **SLA de calidad de voz**: proporciona información sobre las llamadas que se incluyen en Skype Empresarial Online SLA de calidad de voz.
    
### Pestaña Calidad general de las llamadas

Utilice los datos en esta pestaña para evaluar el estado de calidad de llamada y tendencias consultando la secuencia recuentos y porcentajes deficiente. La leyenda en la esquina superior derecha muestra qué color y elementos visuales representan estas métricas.
  
![CQD Data key](../images/c8d183b1-6592-49b0-a81d-35cc0568d5f0.png)
  
Secuencias se clasifican en tres grupos: Bueno, deficiente y sin clasificar. Hay también se calculan que deficiente valores  *%*  que proporcionan que la relación de secuencias clasificadas como * una mala*  el recuento total de secuencia clasificados. Puesto que *una mala % = secuencias de una mala / (deficiente secuencias + secuencias de buenas) * 100*  , por ello la *mala %*  afectadas por la presencia con varias secuencias *no clasificados*  . Para qué se utiliza para la clasificación de una secuencia como buena o mala, consulte[https://aka.ms/cqd_quality_thresholds](https://aka.ms/cqd_quality_thresholds).
  
Use la escala de la izquierda para medir los valores de recuento de llamadas.
  
![CQD data count](../images/850bd25d-d9b2-4df4-8ca6-526a528897c2.png)
  
Use la escala de la derecha para medir los valores bajos %.
  
![CQD data per cent](../images/29795f71-ca96-4763-a76c-b4bb7c0e5828.png)
  
También puede obtener los valores numéricos actuales pasando el ratón por encima de una barra.
  
> [!NOTE]
> El ejemplo siguiente es de un conjunto de datos de ejemplo muy pequeña, y los valores no están realistas para una implementación real. 
  
![CQD Data numeric](../images/8724b016-1a50-4d19-b48a-3b1aae4eb895.png)
  
El volumen general de transmisiones es un factor importante a la hora de determinar la relevancia de los porcentajes de mala calidad calculados. Cuanto más pequeño es el volumen general de transmisiones, menos realistas son los valores de los porcentajes de mala calidad del informe.
  
### Ficha de cliente de servidor y las fichas de cliente de cliente

Estas dos fichas proporcionan detalles adicionales para las transmisiones que tuvieron lugar en sus escenarios de punto de conexión a punto de conexión. Ambas fichas tienen cuatro secciones plegables, que representan cuatro escenarios en los que fluyen las transiciones multimedia.
  
- Cableado interno
    
- Cableado externo
    
- WiFi interno
    
- WiFi externo
    
#### Prueba interna

Durante el proceso, el CQD back-end clasifica una secuencia como  *dentro*  o *fuera*  con información de creación, si existe. Extremos de cada secuencia están asociadas a una dirección de subred. Si la subred está en la lista de subred en la información de creación cargada, se considera dentro. Si la información de compilación no aún se ha cargado, dentro de la prueba siempre clasificará las secuencias como *fuera*  . Tenga en cuenta que dentro de la prueba de escenario de cliente de servidor sólo considera el extremo de cliente. Porque servidores siempre están fuera de la perspectiva de un usuario, esto no se contabilizan en la prueba.
  
#### Wired frente Wi-Fi

Como el nombre indica, estos son criterios de una clasificación basados en el tipo de las conexiones del cliente. De nuevo, el servidor siempre tiene cableado por lo que no se incluye en el cálculo.
  
> [!NOTE]
> Dada una secuencia, si uno de los dos extremos está conectado a una red Wi-Fi, a continuación, se clasifica como Wi-Fi en CQD. 
  
## Selección de datos de producto para ver en informes
<a name="BKMK_FeaturesOfTheCQD"> </a>

En el resumen y los informes de mejorada de ubicación, puede usar la lista desplegable de **Filtro de producto** para mostrar todos los datos de producto, solo los datos de Microsoft Teams o solo los datos de Skype Empresarial Online.
  
![Screenshot shows the Product Filter control with options for All, Microsoft Teams, and Skype for Business.](../images/206ad818-0f72-4c8e-b25e-3cc8fcfbef05.png)
  
En informes detallados, puede usar la dimensión de equipos para filtrar los datos a los datos Microsoft Teams o Skype Empresarial Online como parte de la definición del informe.
  
## Cargar información de compilación
<a name="BKMK_FeaturesOfTheCQD"> </a>

El panel de informes de resumen de CQD incluye una página **Inquilino al cargar los datos**, puede tener acceso seleccionando **Inquilino al cargar los datos** en el menú de configuración en la esquina superior derecha. Esta página se usa para administradores para cargar su propia información, como la asignación de dirección IP y la información geográfica, asignación de cada punto de acceso inalámbrico y su dirección de MAC, etcetera.
  
![CQD Dashboard](../images/839c9ab4-0246-46c9-8402-aafd83a0bc63.png)
  
1. En la página de **Carga de datos de inquilinos**, use el menú desplegable para elegir un tipo de archivo de datos para cargar. El tipo de datos de archivo indica el contenido del archivo (por ejemplo, "Crear" hace referencia a la asignación de dirección IP y la creación, así como otra información geográfica). Actualmente solo se admite el tipo de datos de "Creación". Algunos tipos de datos más se agregará con versiones posteriores.
    
2. Después de seleccionar el tipo de datos de archivo, haga clic en **Examinar** para elegir un archivo de datos.
    
  - El archivo de datos debe ser un .tsv (valores separados por comas) o un archivo .csv (valores separados por comas). Si usa un archivo .csv, cualquier campo que contenga una coma contienen comillas o debe quitar el punto y coma. Por ejemplo, si el nombre del edificio es Nueva York, Nueva York, en el archivo .csv debe escribirse como "Nueva York, Nueva York".
    
  - El archivo de datos no debe ser superior a 50 MB de tamaño.
    
  - Para cada archivo de datos, cada columna del archivo debe coincidir con un tipo de datos predefinido, que se debatirá posteriormente en este tema.
    
3. Después de seleccionar un archivo de datos, especifique la **fecha de inicio** y, opcionalmente, **Especifique una fecha de finalización**.
    
4. Después de seleccionar **Fecha de inicio**, seleccione **Cargar** para cargar el archivo al servidor CQD.
    
    Antes de que el archivo se carga, primero se valida. Una vez validada, se almacena en un blobs de Windows Azure. Si se produce un error de validación o el archivo no se puede almacenarse en una blobs de Windows Azure, se muestra un mensaje de error solicitando una corrección en el archivo. La imagen siguiente muestra un error que se producen cuando el número de columnas del archivo de datos es incorrecto.
    
     ![CQD Example upload validation error](../images/22716a32-3d3d-4870-983c-46089e8b212a.png)
  
5. Si no se produce ningún error durante la validación, el archivo se carga correctamente. A continuación, puede ver el archivo de datos cargado en la tabla **Mis cargas**, que muestra la lista completa de todos los archivos cargados para el inquilino actual en la parte inferior de la página.
    
    Cada archivo de datos de un inquilino cargados grabar programas, con el tipo de archivo, hora de última actualización, período de tiempo, descripción, quitar y un icono de descarga. Para quitar un archivo, seleccione el icono de Papelera Papelera en la tabla. Para descargar un archivo, seleccione el icono de descarga de la columna de **descarga** de la tabla.
    
     ![CQD My Uploads table](../images/4168a883-bbea-461a-80b1-42eedf2e7732.png)
  
### Formato del archivo de datos del inquilino y la estructura del archivo de datos Compilación
<a name="BKMK_TenantDataFile"> </a>

El formato del archivo de datos que cargue debe cumplir los siguientes requisitos para pasar la comprobación de validación antes de cargarlo.
  
- El archivo debe ser un archivo .tsv, lo que significa, en cada fila, las columnas están separadas por una PESTAÑA o un archivo .csv con cada columna separado por una coma.
    
- El contenido del archivo de datos no incluye los encabezados de tabla. Que significa que la primera línea del archivo de datos debe ser datos reales, los encabezados no como "Red" etcetera.
    
- Para cada columna, el tipo de datos puede ser cadena, número o Bool. Si es número, el valor debe ser un valor numérico; Si se trata de Bool, el valor debe ser 0 o 1.
    
- Para cada columna, si el tipo de datos es cadena, los datos pueden estar vacíos (pero aún deben estar separados por un adecuado delimitado por (es decir, una tabulación o una coma). Esto solo asigna ese campo un valor de cadena vacía.
    
- Debe haber 14 columnas por cada fila, cada columna debe tener el siguiente tipo de datos y las columnas deben estar en el orden que se especifica en la siguiente tabla:
    
|**Nombre de columna**|**Tipo de datos**|**Ejemplo**|
|:-----|:-----|:-----|
|Red  <br/> |Cadena  <br/> |192.168.1.0  <br/> |
|Nombre de red  <br/> |Cadena  <br/> |USA/Seattle/SEATTLE-SEA-1  <br/> |
|Rango de redes  <br/> |Número  <br/> |26  <br/> |
|Nombre de edificio  <br/> |Cadena  <br/> |SEATTLE-SEA-1  <br/> |
|Tipo de propiedad  <br/> |Cadena  <br/> |Contoso  <br/> |
|Tipo de edificio  <br/> |Cadena  <br/> |Finalización TI  <br/> |
|Tipo de oficinas del edificio  <br/> |Cadena  <br/> |Ingeniería  <br/> |
|Ciudad  <br/> |Cadena  <br/> |Seattle  <br/> |
|Código postal  <br/> |Cadena  <br/> |98001  <br/> |
|País  <br/> |Cadena  <br/> |EE.UU.  <br/> |
|Estado  <br/> |Cadena  <br/> |WA  <br/> |
|Región  <br/> |Cadena  <br/> |MSUS  <br/> |
|InsideCorp  <br/> |Booleano  <br/> |1  <br/> |
|ExpressRoute  <br/> |Booleano  <br/> |0  <br/> |
   
> [!IMPORTANT]
> El rango de red se puede utilizar para representar una superred (combinación de varias subredes con un solo prefijo de enrutamiento). Todas las nuevas cargas de compilación se comprobarán por si existen rangos solapados. Si anteriormente ha cargado un archivo de compilación, debe descargar el archivo actual y volverlo a cargar para identificar cualquier solapamiento y corregir el problema antes de repetir la carga. Los solapamientos en archivos cargados anteriormente pueden generar errores en la asignación de subredes a compilaciones en los informes. > Ciertas implementaciones VPN no proporcionar la información de subred precisa. Se recomienda que al agregar una subred VPN al archivo de creación, en lugar de una entrada de la subred independientes se agregan entradas para cada dirección de la subred VPN como una red de 32 bits independiente. Cada fila puede tener los mismos metadatos de creación. Por ejemplo, en lugar de una fila por 172.16.18.0/24, debería tener 256 filas, con una fila por cada dirección entre 172.16.18.0/32 y 172.16.18.255/32, ambos incluidos. 
  
## Selección del tipo de medio en informes detallados
<a name="BKMK_FeaturesOfTheCQD"> </a>

Los informes detallados de soporte técnico examina confiabilidad de calidad y elementos multimedia de audio, vídeo, uso compartido de aplicaciones y tipos de medios de uso compartido de pantalla basado en vídeo. Dimensiones, medidas y filtros específicos para un tipo de medio solo tienen "Audio", "Vídeo", "Compartir" o "VBSS" como prefijo.
  
![Call Quality Dashboard Dimensions.](../images/ae132202-d6dc-43bd-b8b3-ea9c24c519e8.png)
  
Si desea ver las dimensiones y medidas para un tipo de medio único, pueden ser necesario realizar la nueva dimensión de tipo de medio y el filtro. Por ejemplo, para un informe que muestra que el total de la sesión cuenta a través de los diferentes tipos de medios, incluir la dimensión de tipo de medio.
  
![Call Quality Dashboard Total Stream Count.](../images/21d5d0dc-2321-415e-8ef2-cea06165601c.png)
  
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **Declinación de responsabilidades de traducción automática**: Este artículo se ha traducido con un sistema informático sin intervención humana. Microsoft ofrece estas traducciones automáticas para que los hablantes de otros idiomas distintos del inglés puedan disfrutar del contenido sobre los productos, los servicios y las tecnologías de Microsoft. Puesto que este artículo se ha traducido con traducción automática, es posible que contenga errores de vocabulario, sintaxis o gramática. 
  

