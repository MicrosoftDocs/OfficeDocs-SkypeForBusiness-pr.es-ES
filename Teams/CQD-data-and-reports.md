---
title: Datos e informes en el panel de calidad de llamadas
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.reviewer: mikedav, siunies, gageames
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
search.appverid: MET150
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Reporting
- ms.lync.lac.ToolsCallQualityDashboard
- seo-marvel-apr2020
description: Obtenga información sobre los datos y los informes disponibles en el Panel de calidad de llamadas de Microsoft.
ms.openlocfilehash: 4b96f64f7f182c0d4c95796358b20b38d8c726b4
ms.sourcegitcommit: c1aaf1f81c07c0956095b5bd4cb241b1de67b189
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/26/2020
ms.locfileid: "46897850"
---
# <a name="data-and-reports-in-call-quality-dashboard-cqd"></a>Datos e informes en el panel de calidad de llamadas

El panel de calidad de llamadas (CQD) de Microsoft usa una fuente de datos en tiempo casi real (NRT). Los registros de llamadas están disponibles en el CQD en un plazo de 30 minutos desde el final de una llamada. Los registros de llamadas de la canalización NRT solo están disponibles durante unos meses antes de que se quiten del conjunto de datos. 


## <a name="many-ways-to-access-cqd-data"></a>Muchas maneras de obtener acceso a los datos del CQD

Puede acceder a los datos del CQD por diferentes lugares. Elija el que se adapte mejor a sus necesidades:

|  |  |
|---------|---------|
|Centro de administración de Teams [( https://admin.teams.microsoft.com) ](https://admin.teams.microsoft.com)    | Los datos del CQD se incluyen en la página Usuarios del centro de administración de Teams, que muestra los datos más comunes que necesita en un formato fácil de leer.  No puede personalizar los datos del CQD que encuentre en **Usuarios.**  |
|Portal del CQD [( https://cqd.teams.microsoft.com) ](https://cqd.teams.microsoft.com)     | Informes detallados y de resumen sólidos que satisfacen la mayoría de las necesidades, con filtrado detallado. También puede personalizar informes en el portal del CQD. <br><br>Obtenga dos [plantillas de informes del CQD](#import-the-cqd-report-templates) para ayudarle a analizar datos en el portal del CQD.       |
|Power BI     | Use consultas directas para ver los datos del CQD en Power BI con plantillas [personalizables de Power BI.](CQD-Power-BI-query-templates.md) [Descargue plantillas de consulta de Power BI para el CQD.](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true)<br><br>También puede usar la API de REST para obtener acceso a los datos [del CQD](https://docs.microsoft.com/skypeforbusiness/management-tools/call-quality-dashboard/data-api) a través de Power BI. Use este método si desea descargar los datos del CQD para poder trabajar en estos sin conexión. La ventaja de usar este método es un mejor rendimiento, especialmente útil para conjuntos de datos de gran tamaño que no usan Power BI cuando está en línea.       |
|API de Graph     | Obtenga acceso a los datos de calidad de llamadas usted mismo mediante [la API Graph.](https://docs.microsoft.com/graph/api/resources/callrecords-api-overview?view=graph-rest-beta) Se trata del método más complejo, pero le ofrece la mayor flexibilidad y control para analizar los datos de calidad de las llamadas. Por ejemplo, si necesita unirla con otros datos de su organización, puede usar la API de Graph para crear un modelo de datos e incorporar datos de calidad de llamadas.        |

## <a name="import-the-cqd-report-templates"></a>Importar las plantillas de informes del CQD

Descargue dos plantillas de informes [del CQD](https://aka.ms/qertemplates) seleccionadas (Todas las redes y redes administradas) para que le sea más fácil estar al día rápidamente con el CQD. La plantilla Todas las redes, aunque optimizada para trabajar con un archivo de datos de creación, puede usarse mientras trabaja para recopilar y cargar información de creación en el CQD, como se describe en la sección siguiente.

**Para importar las plantillas (. CQDX) en el CQD**

1. En el CQD, seleccione **Informes detallados** en el menú de la parte superior de la página.

2. En el panel izquierdo, seleccione **Importar.** Busque la primera plantilla CQDX y seleccione **Abrir.**

3. Después de cargar la plantilla, una ventana emergente mostrará el mensaje "La importación del informe se ha realizado correctamente". 

4. Repita los pasos 2 y 3 para la segunda plantilla del CQD.

   > [!NOTE]
   > Cada usuario debe importar las plantillas del CQD a su instancia del CQD. 



## <a name="euii-data"></a>Datos de la UEII

Por motivos de cumplimiento normativo, los datos de identificación (EUII) del usuario final (también conocidos como información de identificación personal o PII) solo se guardan durante 28 días. A medida que los datos NRT cruzan la marca de 28 días, los campos que contienen EUII se borran, lo que produce datos NRT sin EUII. Los campos que contienen datos EUII son:

- Dirección IP completa
- Dirección de control de acceso multimedia (MAC)
- Identificador de conjunto de servicios básico (BSSID)
- URI de Protocolo de inicio de sesión (SIP) (solo para Skype Empresarial)
- Nombre principal de usuario (UPN)
- Nombre del extremo de equipo
- Comentarios acerca de los comentarios del usuario
- Id. de objeto (el Id. de objeto de Active Directory del usuario del punto de conexión)

### <a name="admin-roles-with-and-without-euii-access"></a>Roles de administrador con y sin acceso a EUII

Estos [roles RBAC](https://docs.microsoft.com/azure/role-based-access-control/overview) **TIENEN** acceso a EUII:
- Administrador global
- Administrador del servicio de Teams
- Administrador de comunicaciones de Teams
- Ingeniero de soporte en comunicaciones de Teams
- Lector global
- Administrador de Skype Empresarial

Estos roles RBAC **no tienen** acceso a EUII:
- Lector de informes
- Especialista de soporte de comunicaciones de Teams


## <a name="date-controls"></a>Controles de fecha

El CQD admite los siguientes tipos de tendencia gradual:

- 5 días
- 7 días
- 30 días
- 60 días
- 90 días

El parámetro Fecha de la dirección URL acepta un campo Día. Los informes de resumen usan fechas especificadas en el formato YYYY-MM-DD como el último día de la tendencia. El parámetro "00" de fecha de la dirección URL indica "hoy".

|Dirección URL| Fecha final de la tendencia de los días graduales|
|:---|:---|
|<span>https:// <cqdv3> /spd/#/Dashboard/ <reportid> /2019-02/</span>   |Día actual de febrero de 2019|
|<span>https:// <cqdv3> /spd/#/Dashboard/ <reportid> /2019-02-15/</span>|15 de febrero de 2019|
|<span>https:// <cqdv3> /spd/#/Dashboard/ <reportid> /00/</span>        |Día actual|
|||

De forma predeterminada, el día actual del mes se usa como el último día de la tendencia de los días graduales.


## <a name="data-available-in-cqd-reports"></a>Datos disponibles en informes del CQD

Puede que todo lo que necesite sea un resumen predeterminado y los informes detallados del CQD para administrar la calidad de las llamadas de su organización. Si es necesario, puede crear [informes personalizados.](#create-custom-detailed-reports) 

Si desea usar Power BI para analizar los datos del CQD, lea Usar Power BI para analizar datos [del CQD para Teams.](CQD-Power-BI-query-templates.md)

|Característica|Informes de resumen|Informes detallados|
|:--- |:--- |:--- |
|Métrica de uso compartido de aplicaciones | No | Sí |
|Soporte de información sobre el edificio del cliente | Sí | Sí |
|Soporte de información de extremo de cliente | Solo en <span> cqd.teams.microsoft.com<span/> | Solo en <span> cqd.teams.microsoft.com<span/> |
|Compatibilidad con análisis de exploración en profundidad   | No   | Sí   |
|Métricas de confiabilidad de medios   | No   | Sí   |
|Informes detallados   | Sí   | Sí   |
|Informes de información general   | Sí   | Sí   |
|Conjunto de informes por usuario   | No   | Sí   |
|Personalización del conjunto de informes (agregar, eliminar, modificar informes)   | No   | Sí   |
|Métricas de pantalla compartida basada en vídeo   | No   | Sí   |
|Métricas de vídeo   | No   | Sí   |
|Cantidad de datos disponibles   | Últimos 12 meses   | Últimos 12 meses   |
|Datos de Microsoft Teams   | Sí   | Sí   |
| | | |


 
### <a name="select-product-data-to-see-in-reports"></a>Seleccionar los datos del producto para verlos en los informes

En los Informes de resumen y de  Location-Enhanced, puede usar el menú desplegable Filtro de productos para mostrar todos los datos del producto, solo los datos de Microsoft Teams o solo los datos de Skype Empresarial Online.
  
![Captura de pantalla: muestra las opciones de control de Filtro de productos](media/206ad818-0f72-4c8e-b25e-3cc8fcfbef05.png)
  
En los informes detallados, puede usar la dimensión **Is Teams** para filtrar los datos a los datos de Microsoft Teams o Skype Empresarial Online.

## <a name="summary-reports"></a>Informes de resumen

Estos son los informes que verá en el panel del CQD la primera vez que inicie sesión en el CQD. Le dan un vistazo a las tendencias de calidad de los informes diarios, mensuales y de tablas para ayudarle a identificar las subredes que tienen una calidad deficiente. 

| Tabulador | Descripción |
|---------|---------|
|Calidad general de las llamadas     | Agregado de las otras 3 pestañas.       |
|Servidor: cliente     |Detalles de las transmisiones entre los puntos de conexión del servidor y del cliente.        |
|Cliente: cliente     |Detalles de las transmisiones entre dos puntos de conexión de cliente.        |
|SLA de calidad de voz     |Información sobre las llamadas incluidas en el SLA de calidad de voz de Skype [Empresarial.](https://go.microsoft.com/fwlink/p/?linkid=846252)        |

### <a name="overall-call-quality-tab"></a>Pestaña Calidad general de las llamadas

Use los datos de esta pestaña para evaluar el estado y las tendencias de calidad de las llamadas en función de los recuentos de transmisiones y los porcentajes bajos. La leyenda de la esquina superior derecha muestra qué color y elementos visuales representan estas métricas.
  
![Captura de pantalla: mostrar la pestaña Calidad de la llamada](media/c8d183b1-6592-49b0-a81d-35cc0568d5f0.png)
  
Las transmisiones se clasifican en tres grupos: Buena, Mala y Sin clasificar. También se calculan los *valores de %* de  mala calidad que le dan la relación de transmisiones clasificadas como malas con el total clasificado del recuento de transmisiones. Since *Poor % = Poor streams/ (Poor streams + Good streams) * 100*, the Poor *%*  is unffected by the presence of multiple *Unclassified*  streams. Para ver qué clasifica una transmisión como mala o buena, consulte la Clasificación de la transmisión en [el panel de calidad de llamadas.](stream-classification-in-call-quality-dashboard.md)
  
Use la escala de la izquierda para medir los valores del recuento de transmisiones.
  
![Captura de pantalla: muestra los valores del recuento de transmisiones](media/850bd25d-d9b2-4df4-8ca6-526a528897c2.png)
  
Use la escala de la derecha para medir los valores bajos %.
  
![Captura de pantalla: muestra valores % bajos](media/29795f71-ca96-4763-a76c-b4bb7c0e5828.png)
  
También puede obtener los valores numéricos actuales colocando el mouse sobre una barra.
  
> [!NOTE]
> El ejemplo siguiente se hace a partir de un conjunto de datos de ejemplo muy pequeño y los valores no son realistas para una implementación real.
  
![Captura de pantalla: muestra el mouse usado para obtener acceso a los datos](media/8724b016-1a50-4d19-b48a-3b1aae4eb895.png)
  
El volumen general de transmisiones le ayuda a determinar la relevancia de los porcentajes de mala calidad calculados. Cuanto menor sea el volumen general de transmisiones, menos fiables son los valores de los porcentajes de mala calidad del reportado.
  
### <a name="server-client-tab-and-client-client-tabs"></a>Server-Client pestañas y Client-Client pestañas

Estas dos pestañas proporcionan detalles de las transmisiones que tuvieron lugar en sus escenarios de punto de conexión a punto de conexión. La Server-Client web tiene cuatro secciones contraíbles que representan cuatro escenarios en los que fluyen las transmisiones multimedia.
  
- Cableado interno
- Cableado externo
- WiFi en el interior
- WiFi externo

De forma similar, Client-Client pestaña tiene cinco secciones contraíbles:

- Cableado interno: cableado interno
- Cableado interno: cableado externo
- Cableado externo: cableado externo
- Cableado interno: WiFi en el interior
- Cableado interno: WiFi fuera

#### <a name="inside-versus-outside"></a>Interno frente a Externo

El CQD clasifica una transmisión  como interna *o* externa con información de creación, si existe. Los puntos de conexión de cada transmisión están asociados con una dirección de subred. Si la subred está en la lista de las subredes marcadas como InsideCorp en la información de creación cargada, se considera *interna.* Si la información de creación aún no se ha cargado, la prueba interna siempre clasifica las transmisiones como *Externas.* 

La prueba interna de un escenario Server-Client solo considera el punto de conexión del cliente. Como los servidores siempre están fuera de la perspectiva del usuario, esto no se tiene en cuenta en la prueba.
  
#### <a name="wired-versus-wifi"></a>Cableado frente a WiFi

Como el nombre indica, los criterios de clasificación se basan en el tipo de conexiones del cliente. El servidor siempre tiene cable y no se incluye en el cálculo. En una transmisión determinada, si uno de los dos puntos de conexión está conectado a una red WiFi, el CQD lo clasifica como WiFi.

> [!NOTE]
> Dada una transmisión, si uno de los dos puntos de conexión está conectado a una red WiFi, entonces se clasifica como WiFi en el CQD.
  
  
## <a name="tenant-data-information"></a>Información de datos del espacio empresarial

El panel informes de resumen  del CQD incluye una  página de carga de datos del inquilino a la que se accede seleccionando Carga de datos del inquilino en el menú de configuración de la esquina superior derecha. Los administradores usan esta página para cargar su propia información, por ejemplo:

- Un mapa de direcciones IP e información geográfica.
- Un mapa de cada AP inalámbrica y su dirección MAC.
- Un mapa de punto de conexión a la hoja de datos o el tipo del extremo, etc.
  
Le recomendamos que cargue los datos de inquilino, edificio y ubicación para que el CQD pueda incluir esta información en los informes. Si aún no ha cargado estos datos, lea Cargar inquilino [y generar datos.](CQD-upload-tenant-building-data.md) 


## <a name="detailed-reports"></a>Informes detallados

| Nombre | Descripción |
|---------|---------|
|Location-Enhanced de información     |Muestra tendencias de calidad basadas en la información de la ubicación. Este informe solo aparece si ha [cargado los datos del espacio empresarial.](CQD-upload-tenant-building-data.md)        |
|Informes de confiabilidad     |Incluye audio, vídeo, pantalla compartida basada en vídeo (VBSS) e informes de uso compartido de aplicaciones.        |
|Informes de calidad de la experiencia     |Calidad y fiabilidad del audio para todos los clientes y dispositivos, incluidas las salas de reuniones. Estos informes son una versión "delgada" de las plantillas [CQD](https://aka.ms/QERtemplates)descargables, que se centra en áreas clave para analizar la calidad del audio y la confiabilidad.         |
|Informes de nivel de detalles de calidad     | Desgloses: fecha por región, ubicaciones, subredes, hora y usuarios.        |
|Informes de obtención de detalles de errores     | Desgloses: fecha por región, ubicaciones, subredes, hora y usuarios.        |
|Calificar mis informes de llamadas     |Analice las clasificaciones de llamadas de usuario por región, ubicación o por usuario. Incluye comentarios al respecto.         |
|Informes del Servicio de ayuda     |Los informes del servicio de ayuda miran los datos de llamadas y reuniones de usuarios individuales, grupos de usuarios o todos los usuarios. La incorporación de datos de creación y de EUII ayuda a identificar posibles problemas del sistema en función de la ubicación de la red, detalles de conferencias, dispositivos o firmware.         |
|Informes de versión de cliente     |Resumen de la versión del cliente: Ver el recuento de sesiones y usuarios para cada versión de aplicación del cliente<br><br>Versión del cliente por usuario: Ver nombres de usuario para cada versión de aplicación cliente <br><br>Los filtros predefinidos para productos y tipos de cliente ayudan a centrar las versiones en clientes específicos.         |
|Informes de puntos de conexión     |Muestra la calidad de la llamada por puntos de conexión del equipo (modelos y modelos de equipo). Estos informes incluyen datos de creación, si los ha cargado.         |


## <a name="create-custom-detailed-reports"></a>Crear informes detallados personalizados

Si los informes del CQD predeterminados no satisfacen sus necesidades, use estas instrucciones para crear un informe personalizado. O bien, a partir de enero de 2020, use power BI para [informes del CQD ](cqd-power-bi-query-templates.md)en su lugar.

En la lista desplegable de informes en la parte superior de la pantalla que se muestra al iniciar sesión en la pantalla Informes de resumen, seleccione Informes detallados \(  \) y, después, **Nuevo.**  Haga **clic en** Editar en un informe para ver el Editor de consultas. Cada informe está respaldado por una consulta dentro del cubo. Un informe es una visualización de los datos devueltos por su consulta. El Editor de consultas le ayuda a editar estas consultas y las opciones de presentación del informe.

> [!IMPORTANT]
> El rango de red se puede usar para representar una supernet (combinación de varias subredes con un solo prefijo de enrutamiento). Todas las nuevas cargas de creación se comprobarán por si hay rangos superpuestos. Si previamente ha cargado un archivo de creación, debe descargar el archivo actual y volver a cargarlo para identificar cualquier solapamiento y corregir el problema antes de volver a cargarlo. Cualquier superposición en archivos cargados anteriormente puede producir errores en la asignación de subredes a edificios en los informes. Algunas implementaciones VPN no informan de forma precisa sobre la información de subred. Se recomienda que, al agregar una subred VPN al archivo de creación, en lugar de una entrada para la subred, se agreguen entradas separadas para cada dirección de la subred VPN como una red independiente de 32 bits. Cada fila puede tener los mismos metadatos de creación. Por ejemplo, en lugar de una fila para 172.16.18.0/24, debería tener 256 filas, con una fila por cada dirección entre 172.16.18.0/32 y 172.16.18.255/32, ambos incluidos.
>
> La columna VPN es opcional y tendrá el valor predeterminado 0.  Si el valor de la columna VPN está establecido en 1, la subred representada por esa fila se ampliará por completo para coincidir con todas las direcciones IP de la subred.  Use este programa con moderación y solo para las subredes VPN, ya que la ampliación completamente de estas subredes afectará negativamente a los tiempos de consulta en las consultas que impliquen generar datos.

Seleccione los gráficos de barras y las líneas de tendencia del informe para mostrar valores detallados. El informe que tiene el foco mostrará el menú de acciones: **Editar,** **Clonar,** **Eliminar,** **Descargar** y **Exportar árbol de informe.**



## <a name="query-filters"></a>Filtros de consulta

Los filtros de consulta se implementan con el Editor de consultas del CQD. Estos filtros se usan para reducir el número de registros devueltos por el CQD, minimizando así el tamaño total del informe y los tiempos de consulta. Esto es especialmente útil para filtrar redes no administradas. Los filtros enumerados en la tabla siguiente usan expresiones regulares (RegEx).


| Filtro         | Descripción          | Ejemplo de filtro de consulta del CQD      |
|----------------|----------------------|-------------------------------|
| No hay valores en blanco   | Algunos filtros no tienen la opción de filtrar por valores en blanco. Para filtrar los valores en blanco manualmente, use la expresión en blanco y establezca el filtro en Igual o No es igual, según sus necesidades.      | Second Building Name \<\> \^ \\ s\*\$                       |
| Excluir subredes comunes | Sin un archivo de creación válido que separe las redes administradas de redes no administradas, las redes locales se incluirán en los informes. Estas subredes de inicio están fuera del ámbito del control de IT y se pueden excluir rápidamente de un informe. Las subredes comunes, según se definen en esta guía, son 10.0.0.0, 192.168.1.0 y 192.168.0.0. | Second Subnet \<\> 10.0.0.0 \| 192.168.0.0 \| 192.168.1.0 |
| Ver solo dentro de  | Se usa para filtrar un informe por administrado (interno) o no administrado (externo). La plantilla del CQD administrada ya está preconfigurada con estos filtros.       | Second Inside Corp = Inside        |

## <a name="report-filters"></a>Filtros de informe

Use los filtros de informe del CQD para centrar las investigaciones. Use filtros de informe agregando un filtro al informe representado, ya sea en el Editor de consultas o directamente en el informe. Los siguientes filtros de informe se usan en todas las [plantillas del CQD.](https://aka.ms/QERtemplates)


| Filtro     | Descripción                            | Ejemplo de filtro de informe del CQD         |
|------------|----------------------------------------|-----------------------------------|
| Month      | Empiece por el año primero y, después, por el mes. | 2017-10                           |
| Alfabético | Filtros para los caracteres alfabéticos. | [a-z]                             |
| Numérico    | Filtra los caracteres numéricos.    | [0-9]                             |
| Porcentaje | Filtros para un porcentaje.              | ([3-9] \\ .) \| ([3-9]) \| ([1-9][0-9]) |


### <a name="drill-down-filters"></a>Filtros de obtención de detalles

Los informes del CQD presentan varios filtros de obtención de detalles, que son herramientas eficaces para centrar las investigaciones sobre la calidad de las llamadas. Si selecciona un campo de nivel de detalles, el informe abre automáticamente la pestaña correspondiente y filtra el valor seleccionado. Si esa pestaña tiene sus propios campos de exploración en profundidad y uno está seleccionado, se aplican ambos conjuntos de filtros, lo que reduce progresivamente el conjunto de datos resultante.

![Diagrama que ilustra el flujo de informe de exploración en profundidad](media/qerguide-image-drillthrureportflow.png)


#### <a name="adding-and-editing-drill-down-fields"></a>Agregar y editar campos de obtención de detalles

Al editar un informe, tiene la opción de especificar campos de obtención de datos personalizados con el Editor de consultas.

Para empezar, haga clic **en ...** para el informe que desea editar y, a continuación, seleccione **Editar.**

![Captura de pantalla de edición de un campo de obtención de detalles](media/qerguide-image-addeditdrilldownfields.png)

Seleccione una dimensión de la lista que se encuentra en el lado izquierdo del Editor de consultas. A continuación, haga  clic en la lista desplegable debajo de la etiqueta Navegar a y seleccione la pestaña y el grupo expandido al que desea explorar en profundidad la dimensión. Nota: Actualmente, la funcionalidad de obtención de detalles solo funciona navegando a diferentes pestañas. Más adelante, se agregará compatibilidad para la exploración en profundidad de un expandor específico. Por último, haga **clic en** Cerrar para guardar los cambios realizados en la dimensión y, a continuación, haga clic en Guardar **para** guardar y cerrar el Editor de consultas.

![Captura de pantalla de selección de una dimensión en el Editor de consultas](media/qerguide-image-selectquerydimension.png)

### <a name="multi-select-filters"></a>Filtros de selección múltiple

Además de la funcionalidad de obtención de detalles, el CQD también admite la especificación de filtros con varios valores (O filtros).

Para seleccionar varios valores de filtro, empiece por agregar un nuevo filtro al informe. Haga clic junto a la etiqueta Filtros, escriba el nombre de la **+** dimensión que desea usar y haga clic en **Agregar.** 

![Captura de pantalla de adición de un filtro de selección múltiple](media/qerguide-image-addmultiselectfilter.png)

A continuación, **haga clic en** Buscar (un icono de lupa junto al nuevo filtro). Verá un campo de texto y varias opciones, como **Seleccionar todo** e **Invertir.** Escriba un valor y haga clic **en Buscar** junto a ese campo para buscar. Como alternativa, deje el campo de texto vacío y haga clic **en** Buscar para ver las primeras 100 opciones.

```powershell
/filter/[AllStreams].[Second Tenant Id]\|[YOUR TENANT ID HERE]
```

Ejemplo:  

![Captura de pantalla de adición de un filtro de consulta](media/qerguide-image-addfilter.png)

### <a name="dashboard-level-filters"></a>Filtros de nivel de panel
Algunos informes del CQD tienen filtros a nivel de panel agregados, lo que facilita la tarea de filtrar por parámetros comunes. Estos filtros aparecen fuera de las pestañas normales del informe y directamente debajo del filtro Producto, y se aplican a todos los filtros del panel.

![Captura de pantalla de un filtro de panel](media/qerguide-image-dashboardfilters.png)
```powershell
/filter/[AllStreams].[Is Teams]|[TRUE | FALSE]
```

### <a name="url-filters"></a>Filtros de dirección URL

El CQD admite la adición de filtros a la dirección URL. Esto hace que sea más fácil compartir o agregar un marcador a una consulta del CQD. Puede definir parámetros en la dirección URL, como el mes de tendencias, el id. de inquilino o el idioma. También puede agregar filtros de nivel de producto o panel a la dirección URL.
Excluir los datos federados de los informes del CQD es útil al corregir edificios administrados o redes donde los puntos de conexión federados pueden influir en sus informes.

Para agregar un filtro, anexe lo siguiente al final de la dirección URL:

```console
/filter/[AllStreams].[Second Tenant Id]\|[YOUR TENANT ID HERE]
```

Ejemplo:  

`https://cqd.teams.microsoft.com/cqd/#/1234567/2018-08/filter/[AllStreams].[Second Tenant Id]|[TENANTID]`

Para agregar un filtro de nivel de panel a una dirección URL, este debe existir en el CQD como filtro de nivel de producto o de panel. Agregue estos filtros a la dirección URL después del Mes de tendencias y antes de los parámetros de la dirección URL:

`filter/DATA_MODEL_NAME|VALUE`

Por ejemplo, para aplicar un valor de filtro de producto de Microsoft Teams, agregue lo siguiente:

`filter/[AllStreams].[Is%20Teams]|[True]`

La dirección URL completa tendría un aspecto parecido a este:

`https://cqd.teams.microsoft.com/spd/#/Dashboard/2624085/2018-9/filter/[AllStreams].[Is%20Teams]|[True]`

Para aplicar filtros de dirección URL con valores de selección múltiple, separe cada valor con un carácter de barra vertical (|). Por ejemplo:

`filter/[AllStreams].[Media%20Type]|[Video]|[Audio]|[VBSS]`

Si especifica un nombre o un valor no válido, no se aplicará el filtro de dirección URL.


Puede usar un filtro de dirección URL para filtrar cada informe por una dimensión específica. Los filtros de URL más comunes se usan para filtrar informes para excluir la telemetría de participantes federados o para centrarse solo en Teams o Skype Empresarial Online. Excluir los datos federados de los informes del CQD es útil al corregir edificios administrados o redes donde los puntos de conexión federados pueden influir en sus informes.

| Filtro         | Descripción          | Ejemplo de filtro de consulta del CQD      |
|----------------|----------------------|-------------------------------|
| No hay valores en blanco   | Algunos filtros no tienen la opción de filtrar por valores en blanco. Para filtrar los valores en blanco manualmente, use la expresión en blanco y establezca el filtro en Igual o No es igual, según sus necesidades.      | Second Building Name \<\> \^ \\ s\*\$                       |
| Excluir subredes comunes | Sin un archivo de creación válido que separe las redes administradas de redes no administradas, las redes locales se incluirán en los informes. Estas subredes de inicio están fuera del ámbito del control de IT y se pueden excluir rápidamente de un informe. Las subredes comunes, como se definen en este artículo, son 10.0.0.0, 192.168.1.0 y 192.168.0.0. | Second Subnet \<\> 10.0.0.0 \| 192.168.0.0 \| 192.168.1.0 |
| Ver solo dentro de  | Se usa para filtrar un informe por administrado (interno) o no administrado (externo). La plantilla del CQD administrada ya está preconfigurada con estos filtros.       | Second Inside Corp = Inside        |


#### <a name="how-to-find-your-tenant-id"></a>Cómo buscar el id. de inquilino

El id. de inquilino del CQD corresponde al id. de directorio de Azure. Si no conoces el id. de directorio, puedes encontrarlo en Azure Portal:

1.  Inicia sesión en el portal de Microsoft Azure: <https://portal.azure.com>

2.  Seleccione **Azure Active Directory.**

3.  En **Administrar,** seleccione **Propiedades.** El id. de inquilino se encuentra en el **cuadro Id. de** directorio.

También puede encontrar su id. de inquilino mediante PowerShell: 

```powershell
Login-AzureRmAccount
```

## <a name="comparing-teams-and-skype-for-business-cqd-data"></a>Comparación de los datos del CQD de Teams y Skype Empresarial

Incluso dentro del último CQD (cqd.teams.microsoft.com), verá diferencias en los datos entre Teams y Skype Empresarial. Algunos motivos:
- Diferencias en los mecanismos para garantizar el rendimiento y la confiabilidad:
  - Teams dispone de conexión automática y itinerancia rápida. Skype Empresarial no lo hace.
  - Teams dispone de una administración dinámica del ancho de banda. Skype Empresarial no lo hace.
- Diferencias [entre los intervalos de direcciones IP](Office-365-URLs-IP-address-ranges.md) entre Teams y Skype Empresarial. Los intervalos IP de Teams son más recientes, lo que podría provocar problemas de conectividad en el firewall.

## <a name="open-cqd-from-the-skype-for-business-legacy-portal"></a>Abrir el CQD desde el portal heredado de Skype Empresarial

![Un icono del logotipo de Skype Empresarial ](media/sfb-logo-30x30.png) **Con el portal heredado de Skype Empresarial**

1. Inicie sesión en su organización de Office 365  con una cuenta de administrador y, a continuación, seleccione el mosaico Administrador para abrir el Centro de administración.

2. En el panel izquierdo, en Centros **de administración,** seleccione **Microsoft Teams** para abrir el Centro de administración de Teams.

3. En el Centro de administración de Teams, seleccione **Portal** heredado en el panel izquierdo, seleccione Herramientas **y,** a continuación, seleccione Panel de calidad de llamadas de Skype **Empresarial Online.**

   ![Captura de pantalla: Seleccionar el panel de calidad de llamadas](media/6cc7f80f-b8e2-4a9b-aab8-ac871d07a261.png)

4. En la página que se abre, inicie sesión con su cuenta de administrador global y, a continuación, proporcione las credenciales de la cuenta cuando se le solicite.

La primera vez que inicie sesión, el CQD empezará a recopilar y procesar datos. 

> [!IMPORTANT]
> A partir de diciembre de 2019, aún puede acceder a la versión anterior del CQD (cqd.lync.com), aunque el portal heredado le proporciona un vínculo al último CQD (cqd.teams.microsoft.com). Finalmente, se retirará la versión anterior del CQD. A partir del 1 de julio de 2020, la versión anterior del CQD accede a los datos del nuevo CQD (, y ya no puede exportar datos de creación ni de https://CQD.teams.microsoft.com) informe). A finales de 2020, desactivaremos el CQD antiguo y ya no podrá acceder a él.


## <a name="related-topics"></a>Temas relacionados

[Mejorar y supervisar la calidad de las llamadas en Teams](monitor-call-quality-qos.md)

[¿Qué es el CQD?](CQD-what-is-call-quality-dashboard.md)

[Configurar el panel de calidad de llamadas (CQD)](turning-on-and-using-call-quality-dashboard.md)

[Cargar datos de inquilino y de edificio](CQD-upload-tenant-building-data.md)

[Usar el CQD para administrar la calidad de las llamadas y las reuniones](quality-of-experience-review-guide.md)

[Dimensiones y medidas disponibles en el CQD](dimensions-and-measures-available-in-call-quality-dashboard.md)

[Clasificación de transmisiones en el CQD](stream-classification-in-call-quality-dashboard.md)

[Usar Power BI para analizar datos del CQD](CQD-Power-BI-query-templates.md)
