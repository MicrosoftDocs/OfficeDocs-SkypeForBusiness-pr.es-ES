---
title: Activar y usar paneles de calidad de llamadas
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.reviewer: mikedav, siunies, gageames
ms.topic: article
ms.assetid: 553fa13c-92d2-4d5c-a3d5-41a073cb047c
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
search.appverid: MET150
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords:
- ms.lync.lac.ToolsCallQualityDashboard
- ms.teamsadmincenter.directrouting.cqd
ms.custom:
- Reporting
description: 'Vea cómo activar y usar el Skype para profesionales Online panel calidad de llamadas y obtener informes de resumen de calidad de las llamadas. '
ms.openlocfilehash: bfbca275afb6da9dbe0f809906e6053f87e960e8
ms.sourcegitcommit: ee3f79ce1b6da0885e1096f9fba894bcff1814da
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/25/2019
ms.locfileid: "33298671"
---
# <a name="turning-on-and-using-call-quality-dashboard-for-microsoft-teams-and-skype-for-business-online"></a>Activar y con el panel de calidad de llamadas para Microsoft Teams y Skype para profesionales en línea

Obtenga información sobre cómo configurar la organización de Office 365 para usar el panel de calidad de llamadas para supervisar la calidad de la llamada.
  
El panel de calidad de llamadas (CQD) para Microsoft Teams y Skype para profesionales en línea permite obtener entendimiento de la calidad de las llamadas realizadas mediante Microsoft Teams y Skype para servicios de negocios. En este tema se describe los pasos que necesitará para llevar a cabo para iniciar la recopilación de datos.
  
> [!NOTE]
> El CQD detallado informes actualmente están disponibles como Tech Preview pero disponibles para todos los clientes. 
  
## <a name="latest-changes-and-updates"></a>Los cambios más recientes y actualizaciones

Los cambios más recientes a CQD son los siguientes:
  
- Incluye los datos de Microsoft Teams además de Skype para datos profesionales en línea.
    
- Informes de resumen de incluyen un filtro de producto para seleccionar todos los datos, los datos de Microsoft Teams o Skype para datos profesionales en línea.

- Se ha actualizado la lógica de clasificación de calidad de secuencia vídeo y VBSS. Hacer referencia a la [Clasificación de la secuencia en el panel de calidad de llamadas](stream-classification-in-call-quality-dashboard.md) para las definiciones de clasificador más recientes.

Hacer referencia a este artículo para obtener una lista de [las dimensiones y medidas disponibles en el panel de calidad de llamadas](dimensions-and-measures-available-in-call-quality-dashboard.md).
  
> [!NOTE]
> Puede encontrar información acerca de las actualizaciones y los cambios realizados en el panel haciendo clic en el vínculo en la **buenas noticias!** Pancarta cuando se muestra en el panel.
  
## <a name="activate-microsoft-call-quality-dashboard-cqd-summary-reports"></a>Activar los informes de resumen del panel (CQD) de calidad de llamada de Microsoft

Antes de empezar a usar el CQD, debe activarlo para su organización de Office 365.
 
![logotipo-sfb-30x30.png](media/sfb-logo-30x30.png) **utilizando el Skype para el centro de administración de negocio**
 
1. Inicie sesión en la organización de Office 365 con una cuenta de administrador y, a continuación, seleccione el icono de **administración** para abrir el centro de administración.
    
2. En el panel izquierdo, en **centros de administración**, seleccione Abrir el Skype para el centro de administración de negocio de **Skype para la empresa** .
    
3. En Skype para el centro de administración de negocio, seleccione **Herramientas** en el panel izquierdo y, a continuación, seleccione **Skype para profesionales Online panel calidad de llamadas**.
    
     ![Skype para herramientas de negocio](media/6cc7f80f-b8e2-4a9b-aab8-ac871d07a261.png)
  
4. En la página que se abre, inicie sesión con su cuenta de administrador Global y, a continuación, proporcione las credenciales para la cuenta cuando se le solicite.
    
     ![Inicio de sesión de CQD](media/ac4c1699-d8c1-4bda-af30-0fec35b5fd22.png)
  
Después de iniciar sesión, una vez activada, la CQD comenzará el procesamiento y recopilación de datos.

![los equipos-logotipo-30x30.png](media/teams-logo-30x30.png) **desde el centro de administración de equipos de Microsoft**
 
1. Inicie sesión en la organización de Office 365 con la cuenta de administrador del servicio de Microsoft Teams y, a continuación, seleccione el icono de **administración** para abrir el centro de administración.
    
2. En el panel izquierdo, en **centros de administración**, seleccione **Los equipos de Microsoft** para abrir el centro de administración de Microsoft Teams.
    
3. En el centro de administración de Microsoft Teams, seleccione **panel de calidad de llamadas** en el panel izquierdo.
    
  
4. En la página que se abre, inicie sesión con su cuenta de administrador Global o la cuenta de administrador de servicio de los equipos de Microsoft y, a continuación, proporcione las credenciales para la cuenta cuando se le solicite.
    
     ![Inicio de sesión de CQD](media/ac4c1699-d8c1-4bda-af30-0fec35b5fd22.png)
  
Después de iniciar sesión, una vez activada, la CQD comenzará el procesamiento y recopilación de datos.  
> [!NOTE]
> Puede tardar un par de horas para procesar datos suficientes para mostrar resultados significativos en los informes. 
  
## <a name="features-of-the-call-quality-dashboard-for-microsoft-teams-and-skype-for-business-online"></a>Características del panel de calidad de llamada para los equipos de Microsoft y Skype para la empresa en línea 
<a name="BKMKFeaturesOfTheCQD"> </a>

Informes de resumen de CQD proporcionan un subconjunto de las características planeadas para informes detallados. Las diferencias entre las dos ediciones se resumen a continuación:
  
|**Característica**|**Informes de resumen**|**Informes detallados**|
|:-----|:-----|:-----|
|Métrica de uso compartido de aplicaciones  <br/> |No  <br/> |Sí  <br/> |
|Crear la compatibilidad de información del cliente  <br/> |Sí  <br/> |Sí  <br/> |
|Compatibilidad con información de extremo de cliente  <br/> |Sólo en cqd.teams.microsoft.com  <br/> |Sólo en cqd.teams.microsoft.com  <br/> |
|Soporte de análisis en profundidad  <br/> |No  <br/> |Sí  <br/> |
|Métricas de confiabilidad de medios  <br/> |No  <br/> |Sí  <br/> |
|Informes de fábrica  <br/> |Sí  <br/> |Sí  <br/> |
|Información general sobre informes  <br/> |Sí  <br/> |Sí  <br/> |
|Conjunto de informes por usuario  <br/> |No  <br/> |Sí  <br/> |
|Informe de establece personalización (agregar, eliminar, modificar informes)  <br/> |No  <br/> |Sí  <br/> |
|Uso compartido de las métricas de pantalla basados en vídeo  <br/> |No  <br/> |Sí  <br/> |
|Métricas de vídeo  <br/> |No  <br/> |Sí  <br/> |
|Cantidad de datos disponibles  <br/> |6 últimos meses  <br/> |6 últimos meses  <br/> |
|Datos de Microsoft Teams  <br/> |Sí  <br/> |Sí  <br/> |
   
### <a name="out-of-the-box-reports"></a>Informes de fábrica

Ambas ediciones de CQD proporcionan un-de-fábrica experiencia, que confiere llamar métricas de calidad sin necesidad de crear todos los nuevos informes. Una vez que los datos se procesan en el servidor back-end, puede empezar a ver los datos de calidad de llamadas en los informes.
  
### <a name="overview-reports"></a>Información general sobre informes

Ambas ediciones de la CQD proporcionan un punto de entrada de alto nivel a la información general de calidad de llamada, pero la forma se presenta información en los informes de resumen es distinta de informes detallados.
  
Informes de resumen proporcionan una vista de informe de página con fichas simplificada que permite a los usuarios examinar y comprender el estado de calidad de llamada y las tendencias generales de rápidamente.
  
Incluyen las cuatro fichas:
  
- **Calidad de llamada general** - proporciona información sobre todas las secuencias, que es una suma de las secuencias de cliente a servidor y secuencias de cliente a cliente, así como cliente de servidor independiente y secuencias de cliente a cliente, con el formato de las tendencias mensuales y diarias de.
    
- **Servidor - Client** - proporciona detalles adicionales para las secuencias entre los extremos de cliente y servidor.
    
- **Cliente - cliente** - proporciona detalles adicionales para las secuencias entre dos extremos de cliente.
    
- **SLA de calidad de voz** - proporciona información sobre las llamadas que se incluyen en la Skype para profesionales SLA de calidad de voz en línea.
    
### <a name="overall-call-quality-tab"></a>Ficha general de calidad de llamada

Usar los datos de esta ficha para evaluar el estado de calidad de llamada y las tendencias observando los recuentos de secuencia y porcentajes deficientes. La leyenda en la esquina superior derecha muestra qué color y elementos visuales representan estas métricas.
  
![Clave de datos de CQD](media/c8d183b1-6592-49b0-a81d-35cc0568d5f0.png)
  
Las secuencias se clasifican en tres grupos: Bueno, deficiente y sin clasificar. Hay también se calculan *% deficiente* valores que proporcionan que la proporción de secuencias de clasificó como *deficiente* que el recuento total de secuencia clasificados. Puesto que *deficiente % = deficientes secuencias / (deficiente secuencias + secuencias de buena) * 100* , esto hace que el *% deficiente* que no afectado por la presencia con varias secuencias de *no clasificados* . Para que se usa para la clasificación de un objeto stream como buena o mala, hacer referencia a la [Clasificación de la secuencia en el panel de calidad de llamadas](stream-classification-in-call-quality-dashboard.md).
  
Utilice la escala a la izquierda para medir los valores de número de secuencia.
  
![Recuento de datos CQD](media/850bd25d-d9b2-4df4-8ca6-526a528897c2.png)
  
Utilice la escala de la derecha para medir los valores de % deficiente.
  
![Datos CQD por ciento](media/29795f71-ca96-4763-a76c-b4bb7c0e5828.png)
  
También puede obtener los valores numéricos reales desplazando el mouse sobre una barra.
  
> [!NOTE]
> En el siguiente ejemplo es de un conjunto de datos de ejemplo muy pequeño, y los valores no son realistas para una implementación real. 
  
![Numérico de datos CQD](media/8724b016-1a50-4d19-b48a-3b1aae4eb895.png)
  
El volumen total de secuencia es un factor importante para determinar cómo relevantes los porcentajes calculados deficientes son. Menor el volumen de secuencias generales, menos confiables son los valores de porcentaje deficiente informado.
  
### <a name="server-client-tab-and-client-client-tabs"></a>Ficha de cliente a servidor y las fichas de cliente a cliente

Estos dos fichas proporcionan detalles adicionales para las secuencias que tuvieron lugar en sus escenarios de extremo a extremo. Ambas fichas tienen cuatro secciones contraíbles, que representa los cuatro situaciones en las que sería flujo de las secuencias multimedia.
  
- Con cable dentro de
    
- Con cable fuera
    
- Inside WiFi
    
- WiFi exteriores
    
#### <a name="inside-test"></a>Prueba interior

Durante el procesamiento, el back-end de CQD clasifica una secuencia como *dentro* o *fuera* con información de creación, si existe. Los extremos de cada secuencia están asociados con una dirección de subred. Si la subred se encuentra en la lista de las subredes marcadas InsideCorp en la información de creación que se cargan, se considera *dentro*. Si la información de compilación que no todavía se haya cargado, a continuación, dentro de la prueba se siempre clasificar las secuencias como *externa*. Tenga en cuenta que dentro de pruebas para el escenario de cliente a servidor sólo considera el extremo de cliente. Debido a que los servidores están siempre fuera desde la perspectiva de un usuario, esto no se contabilizan en la prueba.
  
#### <a name="wired-vs-wifi"></a>Con cable frente a wifi

Como los nombres indican, esto es un criterio de clasificación en función del tipo de conexiones de cliente. Una vez más, siempre se conecta el servidor y no se incluye en el cálculo.
  
> [!NOTE]
> Dado un objeto stream, si uno de los dos extremos está conectado a una red Wifi, a continuación, se clasifica como Wifi en CQD. 
  
## <a name="selecting-product-data-to-see-in-reports"></a>Selección de datos de productos para ver en los informes
<a name="BKMKProductFilter"></a>

En el resumen y ubicación mejorado informes, puede usar la lista desplegable **Filtro de producto** para mostrar todos los datos del producto, sólo los datos de Microsoft Teams o sólo Skype para datos profesionales en línea.
  
![Captura de pantalla muestra el control de filtro de producto con opciones para todos, Microsoft Teams y Skype para la empresa.](media/206ad818-0f72-4c8e-b25e-3cc8fcfbef05.png)
  
En los informes detallados, puede usar la dimensión de **Los equipos es** para filtrar los datos a Microsoft Teams o Skype para datos profesionales en línea como parte de la definición del informe.
  
## <a name="upload-tenant-data-information"></a>Cargar información de datos de inquilinos
<a name="BKMKTenantDataInformationUpload"></a>

El panel de informes de resumen de CQD incluye una página **Inquilino la carga de datos** , puede tener acceso seleccionando el **Inquilino al cargar los datos** desde el menú de configuración en la esquina superior derecha. Esta página se usa para los administradores para cargar su propia información, como la asignación de dirección IP y la información geográfica, la asignación de cada punto de acceso inalámbrico y su dirección MAC, la asignación de extremo a extremo hacer / / tipo de modelo, etcetera.
  
![Panel CQD](media/839c9ab4-0246-46c9-8402-aafd83a0bc63.png)
  
1. En la página de **Carga de datos de inquilinos** , use el menú desplegable para elegir un tipo de archivo de datos para cargar. El tipo de datos de archivo denota el contenido del archivo (por ejemplo, "Building" hace referencia a la asignación de dirección IP y crear así como otra información geográfica, "Extremo" hace referencia a la asignación de nombre de extremo a extremo hacer / / tipo de modelo... información). Actualmente se admiten tipos de datos de "Extremo" y "Building" cargar para cqd.teams.microsoft.com (en la fase de vista previa y no oficialmente disponible aún), sólo es compatible con cqd.lync.com cargar el tipo de datos de "Creación". Algunos tipos de datos más se agregarán con las versiones posteriores.
    
2. Después de seleccionar el tipo de datos de archivo, haga clic en **Examinar** para elegir un archivo de datos.
    
   - El archivo de datos debe ser un .tsv (valores separados por comas) o un archivo .csv (valores separados por comas). Si usa un archivo .csv, cualquier campo que contiene una coma debe ir entre comillas o tener la coma que se ha quitado. Por ejemplo, si el nombre del edificio es Nueva York, NY, en el archivo .csv debe escribirse como "Nueva York, NY".
    
   - El archivo de datos debe ser no más de 50MB en tamaño.

   - Archivo cargado en cqd.teams.microsoft.com ha ampliado el límite de filas de 1.000.000 a acelerar el rendimiento de las consultas. Nos podremos imponer ese límite en así como cqd.lync.com.
    
   - Para cada archivo de datos, cada columna en el archivo debe coincidir con un tipo de datos predefinidos, que se trata más adelante en este tema.
    
3. Después de seleccionar un archivo de datos, especifique la **fecha de inicio** y, opcionalmente, **Especifique una fecha de finalización**.
    
4. Después de seleccionar la **fecha de inicio**, seleccione la opción **cargar** para cargar el archivo en el servidor CQD.
    
    Antes de que se carga el archivo, en primer lugar se valida. Una vez validada, se almacena en un objeto binario de Azure. Si se produce un error de validación o el archivo se produce un error deben almacenarse en un objeto binario de Azure, se muestra un mensaje de error que solicita una corrección para el archivo. En la siguiente imagen se muestra un error que se producen cuando el número de columnas en el archivo de datos es incorrecto.
    
     ![Error de validación de carga de ejemplo de CQD](media/22716a32-3d3d-4870-983c-46089e8b212a.png)
  
5. Si no se producen errores durante la validación, la carga de archivos se realizará correctamente. A continuación, puede ver el archivo de datos que se cargan en la tabla **Mis cargas** , que muestra la lista completa de todos los archivos que se cargan para el inquilino actual en la parte inferior de la página.
    
    Cada registro muestra a inquilino cargado un archivo de datos, con el tipo de archivo, hora de última actualización, período de tiempo, descripción, un icono de eliminación y un icono de descarga. Para quitar un archivo, seleccione el icono de la Papelera de Papelera en la tabla. Para descargar un archivo, seleccione el icono de descarga en la columna **Descargar** de la tabla.
    
     ![Tabla CQD mi carga](media/4168a883-bbea-461a-80b1-42eedf2e7732.png)
  
### <a name="tenant-data-file-format-and-structure"></a>Estructura y el formato de archivo de datos de inquilinos
<a name="BKMKTenantDataFile"> </a>

### <a name="building-data-file"></a>Archivo de datos de creación
CQD usa creación archivo de datos por primera derivar columna subred de expansión de red + NetworkRange columna y, a continuación, columna de subred unirse a la columna de primera subred Subnet/Second del registro de llamadas para mostrar edificio, ciudad, país/región... información. El formato del archivo de datos que se carga debe cumplir lo siguiente para pasar la comprobación de validación antes de cargarlas.
  
- El archivo debe ser un archivo .tsv, lo que significa, en cada fila, columnas están separadas por una PESTAÑA o un archivo .csv con cada columna separado por una coma.
    
- El contenido del archivo de datos no incluye los encabezados de tabla. Que significa que la primera línea del archivo de datos debe ser datos reales, no a los encabezados como "Red", etcetera.
    
- Para cada columna, el tipo de datos sólo puede ser cadena, número o Bool. Si es el número, el valor debe ser un valor numérico; Si es Bool, el valor debe ser 0 o 1.
    
- Para cada columna, si el tipo de datos es la cadena, los datos pueden estar vacíos (pero aún deben estar separados por un delimitador adecuado (es decir, una tabulación o una coma). Esto sólo asigna ese campo un valor de cadena vacía.
    
- Debe haber 14 columnas para cada fila, cada columna debe tener los siguientes datos de tipo y las columnas deben estar en el orden indicado en la tabla siguiente:
    
|**Nombre de columna**|**Tipo de datos**|**Ejemplo**|
|:-----|:-----|:-----|
|Red  <br/> |String  <br/> |192.168.1.0  <br/> |
|NetworkName  <br/> |String  <br/> |Estados Unidos/Seattle/SEATTLE-mar-1  <br/> |
|NetworkRange  <br/> |Número  <br/> |26  <br/> |
|BuildingName  <br/> |String  <br/> |SEATTLE-MAR-1  <br/> |
|OwnershipType  <br/> |String  <br/> |Contoso  <br/> |
|BuildingType  <br/> |String  <br/> |Terminación de TI  <br/> |
|BuildingOfficeType  <br/> |String  <br/> |De ingeniería  <br/> |
|Ciudad  <br/> |String  <br/> |Seattle  <br/> |
|ZipCode  <br/> |String  <br/> |98001  <br/> |
|País  <br/> |String  <br/> |NOSOTROS  <br/> |
|Estado  <br/> |String  <br/> |WA  <br/> |
|Region  <br/> |String  <br/> |MSUS  <br/> |
|InsideCorp  <br/> |Booleano  <br/> |1  <br/> |
|ExpressRoute  <br/> |Booleano  <br/> |0  <br/> |
   
> [!IMPORTANT]
> El intervalo de red puede usarse para representar un supernet (combinación de varias subredes con un prefijo de enrutamiento único). Para los rangos superpuestos se comprobarán todas las cargas de creación nuevo. Si anteriormente se ha cargado un archivo de creación, debe descargar el archivo actual y volver a cargarla para identificar cualquier superposiciones y solucionar el problema antes de volver a cargar. En las asignaciones de incorrectos de subredes a edificios en los informes puede ocasionar que cualquier superposición en los archivos cargados previamente. Algunas implementaciones de VPN no informar con precisión la información de subred. Se recomienda que al agregar una subred VPN para el archivo de creación, en lugar de una entrada para la subred, separe las entradas se agregan para cada dirección de la subred VPN como una red independiente de 32 bits. Cada fila puede tener los mismos metadatos de creación. Por ejemplo, en lugar de una fila para 172.16.18.0/24, debe tener 256 filas, con una fila por cada dirección entre 172.16.18.0/32 y 172.16.18.255/32, ambos inclusive. 

### <a name="endpoint-data-file"></a>Archivo de datos de extremo
CQD usa el archivo de datos de extremo mediante la combinación de su columna EndpointName a la columna del primer nombre del extremo de cliente de cliente del extremo Name/Second del registro de la llamada para mostrar la información de marca, modelo o tipo de extremo. El formato del archivo de datos que se carga debe cumplir lo siguiente para pasar la comprobación de validación antes de cargarlas.

- El archivo debe ser un archivo .tsv, lo que significa, en cada fila, columnas están separadas por una PESTAÑA o un archivo .csv con cada columna separado por una coma.

- El contenido del archivo de datos no incluye los encabezados de tabla. Eso significa que la primera línea del archivo de datos debe ser datos reales, no los encabezados como "EndpointName", etcetera.

- Para cada columna, el tipo de datos sólo puede ser la cadena y debe tener no más de 64 caracteres, que es máxima longitud permitida.

- Para cada columna, los datos pueden estar vacíos (pero aún deben estar separados por un delimitador adecuado (es decir, una tabulación o una coma). Esto sólo asigna ese campo un valor de cadena vacía.

- Debe haber 7 columnas para cada fila y las columnas deben estar en el orden indicado en la siguiente tabla.

- EndpointName debe ser único en caso contrario, tal y como lo harán que se unen a incorrecta carga se producirá un error debido a la fila duplicada.

-  EndpointLabel1, EndpointLabel2, EndpointLable3 son etiquetas personalizable de usuario, pueden ser cadenas vacías o valor de los usuarios prefiere, como "Departamento de TI designado 2018 portátiles", "etiqueta de activos 5678"... etcetera.

|**Nombre de columna**|**Tipo de datos**|**Ejemplo**|
|:-----|:-----|:-----|
|EndpointName  <br/> |String  <br/> |1409W3534  <br/> |
|EndpointMake  <br/> |String  <br/> |Fabrikam Inc.  <br/> |
|EndpointModel  <br/> |String  <br/> |Modelo de Fabrikam 123  <br/> |
|EndpointType   <br/> |String  <br/> |Equipo portátil  <br/> |
|EndpointLabel1  <br/> |String  <br/> |TI designado 2018 portátiles  <br/> |
|EndpointLabel2  <br/> |String  <br/> |Etiqueta de activos 5678  <br/> |
|EndpointLabel3  <br/> |String  <br/> |Compra 2018   <br/> |


## <a name="selecting-media-type-in-detailed-reports"></a>Seleccionar tipo de medio en informes detallados
<a name="BKMKMediaType"></a>

Los informes detallados admiten mirar confiabilidad de medios y calidad de audio, vídeo, uso compartido de aplicaciones y tipos de medios de uso compartido de pantalla basados en vídeo. Dimensiones, las medidas y los filtros que son específicos de un tipo de medio único tienen "Audio", "Vídeo", "Uso compartido de aplicaciones" o "VBSS" como prefijo.
  
![Dimensiones del panel de calidad de llamadas.](media/ae132202-d6dc-43bd-b8b3-ea9c24c519e8.png)
  
Si desea ver las dimensiones y medidas para un tipo de medio único, la nueva dimensión MediaType y el filtro es posible que sea necesarios. Por ejemplo, para un informe que muestra que los recuentos del total de la sesión a través de diferentes tipos de medios, incluir la dimensión MediaType.
  
![Recuento de secuencia Total del panel de calidad de llamadas.](media/21d5d0dc-2321-415e-8ef2-cea06165601c.png)

## <a name="related-topics"></a>Temas relacionados
[Configurar el análisis de llamadas de Skype Empresarial](set-up-call-analytics.md)

[Análisis de uso de llamadas para solucionar problemas de calidad de la llamada deficiente](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[Análisis de llamadas y Panel de calidad de llamadas](difference-between-call-analytics-and-call-quality-dashboard.md)

  
 
