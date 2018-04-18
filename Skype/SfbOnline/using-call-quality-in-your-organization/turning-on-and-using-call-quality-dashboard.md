---
title: Encendiendo y usando llame al panel de control de calidad
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.reviewer: mikedav, wlooney
ms.topic: article
ms.assetid: 553fa13c-92d2-4d5c-a3d5-41a073cb047c
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords:
- ms.lync.lac.ToolsCallQualityDashboard
ms.custom:
- Reporting
description: 'Consulte cómo activar y usar el Skype para negocios en línea panel calidad llamar y obtener informes de resumen de la calidad de las llamadas. '
ms.openlocfilehash: 10826d22d2110d73b5233c36837fc5d20d34e382
ms.sourcegitcommit: a0d3e7a177fcd0667ab0d7d0e904f4053b09a92d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2018
---
# <a name="turning-on-and-using-call-quality-dashboard-for-microsoft-teams-and-skype-for-business-online"></a>Activar y utilizar llamar al panel de calidad para Teams de Microsoft y Skype para los negocios en línea

Obtenga información sobre cómo configurar la organización de Office 365 para utilizar el panel de calidad llame para supervisar la calidad de las llamadas.
  
El tablero de mandos de calidad llamar (CQD) para Teams de Microsoft y Skype para los negocios en línea le permite obtener información sobre la calidad de las llamadas realizadas mediante Skype y Teams de Microsoft para servicios de negocios. Este tema describe los pasos que debe realizar para iniciar la recopilación de datos.
  
> [!NOTE]
> El CQD detallado informes están actualmente disponible como Tech Preview pero están disponibles para todos los clientes. 
  
## <a name="latest-changes-and-updates"></a>Actualizaciones y cambios más recientes

Los cambios más recientes a CQD son los siguientes:
  
- Incluye datos de Teams de Microsoft además de Skype para los datos de los negocios en línea.
    
- Informes de resumen incluyen un filtro de productos para seleccionar todos los datos, los datos de Microsoft Teams o Skype para datos empresariales en línea.
    
Consulte este artículo para obtener una lista de [dimensiones y medidas disponibles en llamar al panel de calidad](dimensions-and-measures-available-in-call-quality-dashboard.md).
  
> [!NOTE]
> Encontrará información acerca de actualizaciones y cambios en el escritorio haciendo clic en el vínculo de la **buenas noticias!** Pancarta cuando se muestra en el tablero de mandos.
  
## <a name="activate-microsoft-call-quality-dashboard-cqd-summary-reports"></a>Activar los informes de resumen de Microsoft llamada calidad Dashboard (CQD)

Antes de que puede empezar a utilizar el CQD, debe activarlo para su organización de Office 365.
  
1. Iniciar sesión la organización de Office 365 con una cuenta de administrador y, a continuación, seleccione el azulejo **Admin** para abrir el centro de administración.
    
2. En el panel izquierdo, en **centros de administración**, seleccione **Skype para empresas** para abrir el Skype para el centro de administración de negocios.
    
3. En Skype para el centro de administración de negocios, seleccione **Herramientas** en el panel izquierdo y seleccione **Skype para negocios en línea panel calidad llamar**.
    
     ![Skype para herramientas profesionales](../images/6cc7f80f-b8e2-4a9b-aab8-ac871d07a261.png)
  
4. En la página que se abre, inicie sesión con su cuenta de administrador Global y, a continuación, proporcione las credenciales de la cuenta cuando se le pida.
    
     ![Inicio de sesión CQD](../images/ac4c1699-d8c1-4bda-af30-0fec35b5fd22.png)
  
Después de iniciar sesión, una vez activado, el CQD empezará a recopilar y procesar datos.
  
> [!NOTE]
> Puede tardar un par de horas para procesar datos suficientes para mostrar resultados significativos en los informes. 
  
## <a name="features-of-the-call-quality-dashboard-for-skype-for-business-online"></a>Características del panel de calidad llamada de Skype para el negocio en línea
<a name="BKMKFeaturesOfTheCQD"> </a>

Informes de resumen de CQD proporcionan un subconjunto de las características planeadas para informes detallados. Las diferencias entre las dos ediciones se resumen a continuación:
  
|**Característica**|**Informes de resumen**|**Informes detallados**|
|:-----|:-----|:-----|
|Métrica de uso compartido de aplicaciones  <br/> |No  <br/> |Sí  <br/> |
|Edificio de la información del cliente  <br/> |Sí  <br/> |Sí  <br/> |
|Soporte de análisis detallado  <br/> |No  <br/> |Sí  <br/> |
|Medidas de confiabilidad de los medios de comunicación  <br/> |No  <br/> |Sí  <br/> |
|Informes de fuera de la caja  <br/> |Sí  <br/> |Sí  <br/> |
|Informes de resumen  <br/> |Sí  <br/> |Sí  <br/> |
|Conjunto de informes por usuario  <br/> |No  <br/> |Sí  <br/> |
|Informe establece personalización (agregar, eliminar, modificar informes)  <br/> |No  <br/> |Sí  <br/> |
|Pantalla de vídeo compartiendo métrica  <br/> |No  <br/> |Sí  <br/> |
|Métricas de vídeo  <br/> |No  <br/> |Sí  <br/> |
|Cantidad de datos disponibles  <br/> |Últimos 6 meses  <br/> |Últimos 6 meses  <br/> |
|Datos de Teams de Microsoft  <br/> |Sí  <br/> |Sí  <br/> |
   
### <a name="out-of-the-box-reports"></a>Informes de fuera de la caja

Ambas ediciones de CQD proporcionan una fuera-de-la-caja experiencia, proporcionándole llamar métricas de calidad sin necesidad de crear los nuevos informes. Una vez que los datos se procesan en el servidor back-end, puede empezar a ver llamadas datos de calidad en los informes.
  
### <a name="overview-reports"></a>Informes de resumen

Ambas ediciones de la CQD proporcionan un punto de entrada de alto nivel a la información general de calidad de llamada, pero la información se presenta en los informes de resumen de forma distinta a la de informes detallados.
  
Informes de resumen proporcionan una vista de informe simplificado página con fichas que permite a los usuarios examinar rápidamente y comprender el estado de calidad de la llamada y las tendencias generales.
  
Se incluyen las cuatro fichas:
  
- **Calidad general llamar** : proporciona información acerca de todas las secuencias, que es una acumulación de streams de cliente de servidor de secuencias de cliente a cliente, así como servidor cliente independiente y secuencias de cliente a cliente, en forma de tendencias diarias y mensuales.
    
- **Servidor - cliente** : proporciona detalles adicionales para las secuencias entre los extremos de cliente y servidor.
    
- **Cliente - cliente** - proporciona detalles adicionales para las secuencias entre dos extremos de cliente.
    
- **SLA de calidad de voz** - proporciona información sobre las llamadas que se incluyen en el Skype para negocios SLA de calidad de voz en línea.
    
### <a name="overall-call-quality-tab"></a>Ficha general de llamar a calidad

Utilizar los datos de esta ficha para evaluar el estado de calidad de la llamada y tendencias mirando la secuencia recuentos y porcentajes deficientes. La leyenda en la esquina superior derecha indica qué color y elementos visuales representan estas métricas.
  
![Clave de datos de CQD](../images/c8d183b1-6592-49b0-a81d-35cc0568d5f0.png)
  
Secuencias se clasifican en tres grupos: Bueno, pobre y sin clasificar. Allí también se calculan los que pobres valores *%* que ofrecen es la proporción de secuencias clasificadas como *deficiente* al recuento total secuencia clasificada. Puesto que *% pobre = pobre secuencias / (pobre secuencias + buenas secuencias) * 100* , por ello, la *pobre %* afectado por la presencia con varias secuencias *no clasificados* . Para qué se utiliza para la clasificación de una secuencia como buena o mala, consulte [Llamar a umbrales de calidad](https://aka.ms/cqd_quality_thresholds).
  
Utilice la escala de la izquierda para medir los valores de número de secuencia.
  
![Recuento de datos CQD](../images/850bd25d-d9b2-4df4-8ca6-526a528897c2.png)
  
Utilice la escala de la derecha para medir los valores de % deficiente.
  
![Datos CQD por ciento](../images/29795f71-ca96-4763-a76c-b4bb7c0e5828.png)
  
También puede obtener los valores numéricos reales al situar el puntero sobre una barra.
  
> [!NOTE]
> En el siguiente ejemplo es de un conjunto de datos de muestra muy pequeña, y los valores no son realistas para una implementación real. 
  
![Numérico de datos CQD](../images/8724b016-1a50-4d19-b48a-3b1aae4eb895.png)
  
El volumen total de la secuencia es un factor importante para determinar la importancia de los porcentajes calculados deficientes. Cuanto menor sea el volumen de secuencias generales, menos fiables son los valores de porcentaje deficiente conocida.
  
### <a name="server-client-tab-and-client-client-tabs"></a>Ficha de servidor cliente y las fichas de cliente-cliente

Estas dos fichas proporcionan detalles adicionales para las secuencias que tuvieron lugar en los escenarios de extremo a extremo. Ambas fichas tienen cuatro secciones contraíbles, que representa cuatro situaciones en las que serían flujo flujos de medios.
  
- Con cable interior
    
- Wired fuera
    
- WiFi interior
    
- WiFi exterior
    
#### <a name="inside-test"></a>Prueba interior

Durante el procesamiento, el back-end CQD clasifica una secuencia como *dentro* o *fuera* utilizando información del edificio, si es que existe. Extremos de cada secuencia se asocian con una dirección de subred. Si la subred está en la lista de las subredes marcadas InsideCorp en la información de creación cargada, se considera *dentro*. Si dicha información no ha se ha cargado todavía, dentro de la prueba siempre clasificará las secuencias como *fuera*. Tenga en cuenta que dentro de la prueba para el escenario de servidor cliente sólo considera el extremo de cliente. Como los servidores están siempre fuera desde la perspectiva de un usuario, esto no representaron en la prueba.
  
#### <a name="wired-vs-wifi"></a>Cableadas y wifi

Como indican los nombres, esto es un criterio de clasificación según el tipo de conexiones de cliente. De nuevo, siempre se conecta el servidor y no se incluye en el cálculo.
  
> [!NOTE]
> Dada una secuencia, si uno de los dos extremos está conectado a una red Wifi, se clasifica como Wifi en CQD. 
  
## <a name="selecting-product-data-to-see-in-reports"></a>Selección de datos de producto para ver en los informes
<a name="BKMKFeaturesOfTheCQD"> </a>

En el resumen y los informes mejorados de ubicación, puede utilizar la lista desplegable **Filtro de productos** para mostrar todos los datos del producto, sólo los datos de Teams de Microsoft, o sólo Skype para datos empresariales en línea.
  
![Captura de pantalla muestra el control de filtro de producto con opciones para todas las Teams de Microsoft y Skype para el negocio.](../images/206ad818-0f72-4c8e-b25e-3cc8fcfbef05.png)
  
En informes detallados, puede utilizar la dimensión de **Los equipos es** para filtrar los datos a Microsoft Teams o Skype para datos empresariales en línea como parte de la definición del informe.
  
## <a name="upload-building-information"></a>Información de generación de carga
<a name="BKMKFeaturesOfTheCQD"> </a>

El tablero de mandos de los informes de resumen de CQD incluye una página de **Inquilinos al cargar los datos** , tiene acceso seleccionando el **Inquilino al cargar los datos** en el menú de configuración en la esquina superior derecha. Esta página se utiliza para los administradores para cargar su propia información, como la asignación de dirección IP y la información geográfica, asignación de cada punto de acceso inalámbrico y su dirección MAC, etcetera.
  
![Panel CQD](../images/839c9ab4-0246-46c9-8402-aafd83a0bc63.png)
  
1. En la página de **Carga de datos de inquilinos** , utilice el menú desplegable para elegir un tipo de archivo de datos para cargar. El tipo de datos de archivo denota el contenido del archivo (por ejemplo, "Crear" se refiere a la asignación de dirección IP y la creación, así como otra información geográfica). Actualmente sólo estamos apoyando el tipo de datos de "Creación". Algunos tipos de datos más se agregará con versiones posteriores.
    
2. Después de seleccionar el tipo de datos de archivo, haga clic en **Examinar** para elegir un archivo de datos.
    
  - El archivo de datos debe ser un archivo TSV (valores separados por comas) o un archivo de CSV (valores separados por comas). Si utiliza un archivo .csv, cualquier campo que contenga una coma debe ir entre comillas o quita el punto y coma. Por ejemplo, si el nombre del edificio es de Nueva York, NY, en el archivo .csv debe escribirse como "Nueva York, NY".
    
  - El archivo de datos debe ser no más de 50MB de tamaño.
    
  - Para cada archivo de datos, cada columna del archivo debe coincidir con un tipo de datos predefinido, tratado más adelante en este tema.
    
3. Después de seleccionar un archivo de datos, especifique la **fecha de inicio** y, opcionalmente, **Especifique una fecha final**.
    
4. Después de seleccionar la **fecha de inicio**, seleccione **cargar** para cargar el archivo en el servidor CQD.
    
    Antes de cargar el archivo, primero se valida. Una vez validado, se almacena en un objeto binario de Azure. Si se produce un error de validación o el archivo no se almacena en un objeto binario de Azure, se muestra un mensaje de error solicitando una corrección en el archivo. La imagen siguiente muestra un error que se produce cuando el número de columnas del archivo de datos es incorrecto.
    
     ![Error de validación de carga de ejemplo CQD](../images/22716a32-3d3d-4870-983c-46089e8b212a.png)
  
5. Si no se producen errores durante la validación, la carga de archivos se realizará correctamente. A continuación, puede ver el archivo de datos cargado en la tabla **Mis archivos** , que muestra la lista completa de todos los archivos cargados por el arrendatario en la parte inferior de la página actual.
    
    Cada registro muestra a los inquilinos cargado un archivo de datos, con el tipo de archivo, hora de última actualización, período de tiempo, descripción, un icono de eliminación y un icono de descarga. Para quitar un archivo, seleccione el icono de Papelera de basura en la tabla. Para descargar un archivo, seleccione el icono de descarga en la columna **Descargar** de la tabla.
    
     ![Tabla de carga de mi CQD](../images/4168a883-bbea-461a-80b1-42eedf2e7732.png)
  
### <a name="tenant-data-file-format-and-building-data-file-structure"></a>Formato de archivo de datos de clientes y la estructura de archivos de datos de creación
<a name="BKMKTenantDataFile"> </a>

El formato del archivo de datos que carga debe cumplir lo siguiente para pasar la comprobación de validación antes de cargar.
  
- El archivo debe ser un archivo TSV, lo que significa, en cada fila, las columnas están separadas por TABULADORES, o en un archivo .csv con cada columna separado por una coma.
    
- El contenido del archivo de datos no incluye encabezados de tabla. Eso significa que la primera línea del archivo de datos debe ser datos reales, no encabezados como "Red", etcetera.
    
- Para cada columna, el tipo de datos sólo puede ser cadena, número o Bool. Si el número es, el valor debe ser un valor numérico; Si es Bool, el valor debe ser 0 o 1.
    
- Para cada columna, si el tipo de datos es string, los datos pueden estar vacíos (pero todavía deben estar separados por un delimitador apropiado (es decir, una ficha o una coma). Esto simplemente asigna ese campo un valor de cadena vacía.
    
- Debe haber 14 columnas para cada fila, cada columna debe tener los siguientes datos de tipo y las columnas deben estar en el orden indicado en la tabla siguiente:
    
|**Nombre de la columna**|**Tipo de datos**|**Ejemplo**|
|:-----|:-----|:-----|
|Red  <br/> |Cadena  <br/> |192.168.1.0  <br/> |
|NetworkName  <br/> |Cadena  <br/> |USA/Seattle/SEATTLE-mar-1  <br/> |
|NetworkRange  <br/> |Número  <br/> |26  <br/> |
|Nombredeedificio  <br/> |Cadena  <br/> |SEATTLE-MAR-1  <br/> |
|OwnershipType  <br/> |Cadena  <br/> |Contoso  <br/> |
|BuildingType  <br/> |Cadena  <br/> |Terminación de TI  <br/> |
|BuildingOfficeType  <br/> |Cadena  <br/> |De ingeniería  <br/> |
|Ciudad  <br/> |Cadena  <br/> |Seattle  <br/> |
|Código postal  <br/> |Cadena  <br/> |98001  <br/> |
|País  <br/> |Cadena  <br/> |NOSOTROS  <br/> |
|Estado  <br/> |Cadena  <br/> |WA  <br/> |
|Region  <br/> |Cadena  <br/> |MSUS  <br/> |
|InsideCorp  <br/> |Booleano  <br/> |1  <br/> |
|ExpressRoute  <br/> |Booleano  <br/> |0  <br/> |
   
> [!IMPORTANT]
> El intervalo de red puede utilizarse para representar una supernet (combinación de varias subredes con un solo prefijo de enrutamiento). Se comprobarán todas las cargas de creación nueva para los rangos superpuestos. Si previamente se ha cargado un archivo de creación, debe descargar el archivo actual y volver a cargarla para las superposiciones de identificar y corregir el problema antes de volver a cargar. Puede producir cualquier superposición en archivos cargados previamente las asignaciones incorrectas de subredes para edificios en los informes. Ciertas implementaciones de VPN no informan con precisión de la información de subred. Se recomienda que al agregar una subred VPN para el archivo de edificio, en lugar de una entrada para la subred independientes se agregan entradas para cada dirección de la subred VPN como una red independiente de 32 bits. Cada fila puede tener los mismos metadatos de creación. Por ejemplo, en lugar de una fila de 172.16.18.0/24, debe tener filas de 256, con una fila para cada dirección entre 172.16.18.0/32 y 172.16.18.255/32, ambos inclusive. 
  
## <a name="selecting-media-type-in-detailed-reports"></a>Seleccionar tipo de medio de informes detallados
<a name="BKMKFeaturesOfTheCQD"> </a>

Los informes detallados admiten mirando confiabilidad de calidad y los medios de comunicación para audio, vídeo, uso compartido de aplicaciones y tipos de medios de uso compartido de pantalla basados en vídeo. Dimensiones, medidas y filtros que son específicos de un tipo de medio solo tienen "Audio", "Video", "Compartir" o "VBSS" como prefijo.
  
![Llame a dimensiones del panel de calidad.](../images/ae132202-d6dc-43bd-b8b3-ea9c24c519e8.png)
  
Si desea ver las dimensiones y medidas para un tipo de medio único, pueden requerirse la nueva dimensión MediaType y el filtro. Por ejemplo, para un informe que muestra que el total de la sesión cuenta a través de diferentes tipos de medios, incluir la dimensión MediaType.
  
![Llame a calidad panel secuencia Total Count.](../images/21d5d0dc-2321-415e-8ef2-cea06165601c.png)

## <a name="related-topics"></a>See also
[Configurar el análisis de llamadas de Skype Empresarial](set-up-call-analytics.md)

[Utilizar Analytics llamar a solucionar problemas de calidad de sonido deficiente](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[¿Diferencia entre análisis de llamada y llamada Quality Dashboard?](difference-between-call-analytics-and-call-quality-dashboard.md)

  
 