---
title: Datos e informes en panel de calidad de llamadas (CQD)
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
description: Obtenga información sobre los datos e informes disponibles en el Panel de calidad de llamadas de Microsoft (CQD).
ms.openlocfilehash: 9d13823981ced4d631ed50fe9fd964765c761a029831d630de103bdc5c43e206
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54331122"
---
# <a name="data-and-reports-in-call-quality-dashboard-cqd"></a>Datos e informes en panel de calidad de llamadas (CQD)

El Panel de calidad de llamadas (CQD) de Microsoft usa una fuente de datos en tiempo casi real (NRT). Los registros de llamadas están disponibles en CQD dentro de los 30 minutos adicionales al final de una llamada. Los registros de llamadas de la canalización NRT solo están disponibles durante unos meses antes de que se quiten del conjunto de datos. 


## <a name="many-ways-to-access-cqd-data"></a>Muchas formas de obtener acceso a los datos de CQD

Puede acceder a los datos de CQD por varias vías diferentes. Elija el que mejor se adapte a sus necesidades:

|  |  |
|---------|---------|
|Teams de administración [( https://admin.teams.microsoft.com) ](https://admin.teams.microsoft.com)    | Los datos de CQD se incluyen en la página Usuarios del centro de administración de Teams, que muestra los datos más comunes que necesita en un formato fácil de leer.  No puede personalizar los datos de CQD que encuentre en **Usuarios.**  |
|Portal CQD [( https://cqd.teams.microsoft.com) ](https://cqd.teams.microsoft.com)     | Informes detallados y de resumen sólidos que satisfacen la mayoría de las necesidades, con filtrado detallado. También puede personalizar informes en el portal de CQD. <br><br>Obtenga dos [plantillas de informe CQD](#import-the-cqd-report-templates) para ayudarle a analizar datos en el portal de CQD.       |
|Power BI     | Use consultas directas para ver los datos de CQD en Power BI con plantillas de Power BI [personalizables.](CQD-Power-BI-query-templates.md) [Descargue Power BI de consulta de CQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true).<br><br>También puede usar la API de REST para obtener acceso a los [datos de CQD](/skypeforbusiness/management-tools/call-quality-dashboard/data-api) a través de Power BI. Use este método si desea descargar los datos de CQD para poder trabajar en él sin conexión. La ventaja de usar este método es un mejor rendimiento, especialmente útil para grandes conjuntos de datos que se abate en Power BI cuando está en línea.       |
|API de Graph     | Acceda a los datos de calidad de llamadas usted mismo [con Graph API.](/graph/api/resources/callrecords-api-overview?view=graph-rest-beta) Este es el método más complejo, pero le ofrece el mayor control y flexibilidad al analizar los datos de calidad de las llamadas. Por ejemplo, si necesita unirse a otros datos de su organización, puede usar la API de Graph para crear un modelo de datos e incorporar datos de calidad de llamadas.        |

## <a name="import-the-cqd-report-templates"></a>Importar las plantillas de informe CQD

Descargue dos plantillas de informe [CQD](https://aka.ms/qertemplates) seleccionadas (Todas las redes y redes administradas) para ayudarle a estar al día rápidamente con CQD. La plantilla Todas las redes, aunque está optimizada para trabajar con un archivo de datos de creación, se puede usar mientras trabaja para recopilar y cargar información de creación en CQD, como se describe en la sección siguiente.

**Para importar las plantillas (. CQDX) en CQD**

1. En CQD, seleccione **Informes detallados** en el menú de la parte superior de la página.

2. En el panel izquierdo, seleccione **Importar**. Vaya a la primera plantilla CQDX y seleccione **Abrir.**

3. Después de cargar la plantilla, una ventana emergente mostrará el mensaje "La importación del informe se ha realizado correctamente". 

4. Repita los pasos 2 y 3 para la segunda plantilla CQD.

   > [!NOTE]
   > Cada usuario debe importar las plantillas de CQD a su instancia de CQD. 



## <a name="euii-data"></a>Datos de EUII

Por motivos de cumplimiento, los datos de información de identificación del usuario final (EUII) (también conocido como información de identificación personal o PII) solo se mantienen durante 28 días. A medida que los datos NRT cruzan la marca de 28 días, los campos que contienen EUII se borran, lo que da como resultado datos NRT sin EUII. Los campos que contienen datos EUII son:

- Dirección IP completa
- Dirección de control de acceso multimedia (MAC)
- Identificador de conjunto de servicios básico (BSSID)
- URI del Protocolo de inicio de sesión (SIP) (solo Skype Empresarial)
- Nombre principal de usuario (UPN)
- Nombre del punto de conexión del equipo
- Comentarios textuales de los usuarios
- Id. de objeto (el id. de objeto de Active Directory del usuario del punto de conexión)

### <a name="admin-roles-with-and-without-euii-access"></a>Roles de administrador con y sin acceso a EUII

Estos [roles de RBAC](/azure/role-based-access-control/overview) **DO** tienen acceso a EUII:
- Administrador global
- Teams Administrador del servicio
- Teams Administrador de comunicaciones
- Ingeniero de soporte en comunicaciones de Teams
- Lector global
- Skype Empresarial Administrador

Estos roles de RBAC **no tienen** acceso a EUII:
- Lector de informes
- Teams Especialista en soporte técnico de comunicaciones


## <a name="date-controls"></a>Controles de fecha

CQD admite los siguientes tipos de tendencia continua:

- 5 días
- 7 días
- 30 días
- 60 días
- 90 días

El parámetro Fecha url acepta un campo Día. Los informes de día completo usan fechas especificadas en el formato YYYY-MM-DD como el último día de la tendencia. El parámetro Fecha url "00" indica "hoy".

|Dirección URL| Fecha de finalización de la tendencia rolling day|
|:---|:---|
|<span>https:// <cqdv3> /spd/#/Dashboard/ <reportid> /2019-02/</span>   |Día actual de febrero de 2019|
|<span>https:// <cqdv3> /spd/#/Dashboard/ <reportid> /2019-02-15/</span>|15 de febrero de 2019|
|<span>https:// <cqdv3> /spd/#/Dashboard/ <reportid> /00/</span>        |Día actual|
|||

De forma predeterminada, el día actual del mes se usa como el último día de la Tendencia del día de laminación.


## <a name="data-available-in-cqd-reports"></a>Datos disponibles en informes CQD

El resumen predeterminado y los informes CQD detallados pueden ser todo lo que necesita para administrar la calidad de las llamadas de su organización. Si lo necesita, puede crear [informes personalizados.](#create-custom-detailed-reports) 

Si desea usar Power BI para analizar los datos de CQD, lea Usar Power BI para analizar datos [CQD para Teams](CQD-Power-BI-query-templates.md).

|Característica|Informes de resumen|Informes detallados|
|:--- |:--- |:--- |
|Métrica de uso compartido de aplicaciones | No | Sí |
|Soporte de información de creación de clientes | Sí | Sí |
|Soporte técnico de información del punto de conexión de cliente | Solo en <span> cqd.teams.microsoft.com<span/> | Solo en <span> cqd.teams.microsoft.com<span/> |
|Compatibilidad con análisis en profundidad   | No   | Sí   |
|Métricas de confiabilidad de medios   | No   | Sí   |
|Informes personalizados   | Sí   | Sí   |
|Informes de información general   | Sí   | Sí   |
|Conjunto de informes por usuario   | No   | Sí   |
|Personalización del conjunto de informes (agregar, eliminar y modificar informes)   | No   | Sí   |
|Métricas de uso compartido de pantalla basadas en vídeo   | No   | Sí   |
|Métricas de vídeo   | No   | Sí   |
|Cantidad de datos disponibles   | Últimos 12 meses   | Últimos 12 meses   |
|Microsoft Teams datos   | Sí   | Sí   |
| | | |


 
### <a name="select-product-data-to-see-in-reports"></a>Seleccionar datos de producto para verlos en informes

En los informes de resumen y Location-Enhanced,  puede usar la lista desplegable Filtro de productos para mostrar todos los datos del producto, solo Microsoft Teams datos o solo Skype Empresarial datos en línea.

> [!div class="mx-imgBorder"]
> ![Captura de pantalla: muestra las opciones de control filtro de producto](media/206ad818-0f72-4c8e-b25e-3cc8fcfbef05.png)
  
En informes detallados, puede usar la dimensión Es Teams **para** filtrar los datos Microsoft Teams o Skype Empresarial datos en línea.

## <a name="summary-reports"></a>Informes de resumen

Estos son los informes que verá en el panel de CQD cuando inicie sesión por primera vez en CQD. Le dan un vistazo a las tendencias de calidad con informes diarios, mensuales y de tabla para ayudar a identificar subredes con mala calidad. 

| Pestaña | Descripción |
|---------|---------|
|Calidad general de la llamada     | Agregado de las otras 3 pestañas.       |
|Servidor: cliente     |Detalles de las transmisiones entre los puntos de conexión de servidor y cliente.        |
|Cliente: cliente     |Detalles de las transmisiones entre dos puntos de conexión de cliente.        |
|Sla de calidad de voz     |Información sobre las llamadas incluidas en el SLA Skype Empresarial calidad de [voz.](https://go.microsoft.com/fwlink/p/?linkid=846252)        |

### <a name="overall-call-quality-tab"></a>Pestaña Calidad de llamada general

Use los datos de esta pestaña para evaluar el estado y las tendencias de calidad de las llamadas en función de los recuentos de transmisiones y los porcentajes deficientes. La leyenda de la esquina superior derecha muestra qué colores y elementos visuales representan estas métricas.

> [!div class="mx-imgBorder"]
> ![Captura de pantalla: mostrar la pestaña Calidad de llamada](media/c8d183b1-6592-49b0-a81d-35cc0568d5f0.png)
  
Secuencias se clasifican en tres grupos: Bueno, Pobre y Sin clasificar. También hay valores  *calculados de Porcentaje*  pobre que le dan la relación de transmisiones clasificadas como Mala *con*  el recuento total de transmisiones clasificadas. Puesto *que Poor % = Poor streams/ (Poor streams+ Good streams) * 100*, poor *%*  is unffected by the presence of multiple *Unclassified*  streams. Para ver qué clasifica una transmisión como mala o buena, consulte Clasificación de transmisión en panel de calidad [de llamadas.](stream-classification-in-call-quality-dashboard.md)
  
Use la escala de la izquierda para medir los valores de recuento de transmisiones.

> [!div class="mx-imgBorder"]
> ![Captura de pantalla: muestra los valores de recuento de transmisiones](media/850bd25d-d9b2-4df4-8ca6-526a528897c2.png)
  
Use la escala de la derecha para medir los valores del porcentaje de pobres.

> [!div class="mx-imgBorder"]
> ![Captura de pantalla: muestra los valores % deficientes](media/29795f71-ca96-4763-a76c-b4bb7c0e5828.png)
  
También puede obtener los valores numéricos reales si mantiene el mouse sobre una barra.
  
> [!NOTE]
> El ejemplo siguiente es de un conjunto de datos de ejemplo muy pequeño y los valores no son realistas para una implementación real.

> [!div class="mx-imgBorder"]
> ![Captura de pantalla: muestra el mouse usado para obtener acceso a los datos](media/8724b016-1a50-4d19-b48a-3b1aae4eb895.png)
  
El volumen general de transmisiones ayuda a determinar qué tan relevantes son los porcentajes de pobres calculados. Cuanto menor sea el volumen de las transmisiones generales, menos confiables son los valores de porcentaje de mala calidad notificados.
  
### <a name="server-client-tab-and-client-client-tabs"></a>Server-Client pestaña y Client-Client pestañas

Estas dos pestañas proporcionan detalles para las transmisiones que tuvieron lugar en sus escenarios de punto de conexión a punto de conexión. La pestaña Server-Client tiene cuatro secciones contraíbles que representan cuatro escenarios en los que fluiría la transmisión multimedia.
  
- Cableado dentro
- Cableado fuera
- WiFi Inside
- WiFi fuera

De forma similar, Client-Client pestaña tiene cinco secciones contraibles:

- Por cable dentro: cableado dentro
- Por cable dentro: por cable externo
- Por cable externo: por cable externo
- Por cable dentro: WiFi dentro
- Por cable dentro: WiFi fuera

#### <a name="inside-versus-outside"></a>Inside versus Outside

CQD clasifica una transmisión como  *Dentro*  o *Fuera*  con información de creación, si existe. Los puntos de conexión de cada transmisión están asociados con una dirección de subred. Si la subred está en la lista de las subredes marcadas como InsideCorp en la información de creación cargada, se considera *Dentro.* Si la información de creación aún no se ha cargado, Inside Test siempre clasifica las transmisiones como *Externas.* 

La prueba interna para un escenario Server-Client solo tiene en cuenta el punto de conexión del cliente. Como los servidores siempre están fuera de la perspectiva de un usuario, esto no se cuenta en la prueba.
  
#### <a name="wired-versus-wifi"></a>Cableada frente a WiFi

Como indican los nombres, los criterios de clasificación se basan en el tipo de conexiones de cliente. El servidor siempre está cableado y no se incluye en el cálculo. En una transmisión determinada, si uno de los dos puntos de conexión está conectado a una red WiFi, CQD lo clasifica como WiFi.

> [!NOTE]
> Dado un flujo, si uno de los dos puntos de conexión está conectado a una red WiFi, se clasifica como WiFi en CQD.
  
  
## <a name="tenant-data-information"></a>Información de datos de inquilino

El panel Informes de resumen de CQD incluye una página Datos de **inquilino Upload, a** la que se tiene acceso seleccionando Datos de **inquilino Upload** en el menú configuración de la esquina superior derecha. Esta página se usa para que los administradores carguen su propia información, como:

- Un mapa de la dirección IP y la información geográfica.
- Un mapa de cada AP inalámbrico y su dirección MAC.
- Un mapa de punto de conexión a Punto de conexión, modelo o tipo, etc.
  
Le recomendamos que cargue los datos de inquilino, edificio y ubicación para que CQD pueda incluir esta información en los informes. Si aún no ha cargado estos datos, lea Upload [inquilino y datos de creación.](CQD-upload-tenant-building-data.md) 


## <a name="detailed-reports"></a>Informes detallados

| Nombre | Descripción |
|---------|---------|
|Location-Enhanced informes     |Muestra tendencias de calidad basadas en la información de ubicación. Este informe solo aparece si ha [cargado los datos del inquilino.](CQD-upload-tenant-building-data.md)        |
|Informes de confiabilidad     |Incluye audio, vídeo, uso compartido de pantalla basado en vídeo (VBSS) e informes de uso compartido de aplicaciones.        |
|Informes de calidad de la experiencia     |Calidad de audio y confiabilidad para todos los clientes y dispositivos, incluidas las salas de reuniones. Estos informes son una versión "acodada" de las plantillas [CQD](https://aka.ms/QERtemplates)descargables, que se centra en áreas clave para analizar la calidad y la confiabilidad del audio.         |
|Informes de obtención de detalles de calidad     | Detalles: Fecha por región, ubicaciones, subredes, horas y usuarios.        |
|Informes de desglose de errores     | Detalles: Fecha por región, ubicaciones, subredes, horas y usuarios.        |
|Calificar mis informes de llamadas     |Analizar las clasificaciones de llamadas de usuario por región, ubicación o por usuario. Incluye comentarios textuales.         |
|Informes del servicio de ayuda     |Los informes del Servicio de ayuda miran los datos de llamadas y reuniones de usuarios individuales, grupos de usuarios o todos los usuarios. Al incorporar datos de creación y EUII, estos informes ayudan a identificar posibles problemas del sistema en función de la ubicación de la red, los detalles de la conferencia, los dispositivos o el firmware.         |
|Informes de versión de cliente     |Resumen de la versión del cliente: Ver los recuentos de sesiones y usuarios para cada versión de aplicación cliente<br><br>Versión de cliente por usuario: Ver nombres de usuario para cada versión de aplicación cliente <br><br>Los filtros predefinidos para tipo de cliente y producto ayudan a centrar las versiones en clientes específicos.         |
|Informes de punto de conexión     |Muestra la calidad de las llamadas por puntos de conexión de equipo (la imagen y el modelo del equipo). Estos informes incluyen la creación de datos, si los ha cargado.         |


## <a name="create-custom-detailed-reports"></a>Crear informes detallados personalizados

Si los informes CQD predeterminados no satisfacen sus necesidades, use estas instrucciones para crear un informe personalizado. O bien( a partir de enero de 2020) Use [Power BI para informes CQD en ](cqd-power-bi-query-templates.md)su lugar.

En la lista desplegable de informes en la parte superior de la pantalla que se muestra al iniciar sesión, la pantalla Informes de resumen seleccione Informes detallados y, a \( continuación,  \) **Nuevo**.  Haga **clic en** Editar en un informe para ver el Editor de consultas. Cada informe está respaldado por una consulta dentro del cubo. Un informe es una visualización de los datos devueltos por su consulta. El Editor de consultas le ayuda a editar estas consultas y las opciones de visualización del informe.

> [!IMPORTANT]
> El rango de red se puede usar para representar una supernet (combinación de varias subredes con un único prefijo de enrutamiento). Todas las cargas de edificio nuevas se comprobarán si hay rangos superpuestos. Si previamente ha cargado un archivo de creación, debe descargar el archivo actual y volver a cargarlo para identificar cualquier superposición y solucionar el problema antes de cargarlo de nuevo. Cualquier superposición de archivos cargados previamente puede dar lugar a asignaciones incorrectas de subredes a edificios en los informes. Algunas implementaciones de VPN no informan con precisión de la información de subred. Se recomienda que al agregar una subred VPN al archivo de creación, en lugar de una entrada para la subred, se agreguen entradas independientes para cada dirección de la subred VPN como una red de 32 bits independiente. Cada fila puede tener los mismos metadatos de creación. Por ejemplo, en lugar de una fila para 172.16.18.0/24, debe tener 256 filas, con una fila para cada dirección entre 172.16.18.0/32 y 172.16.18.255/32, ambos inclusive.
>
> La columna VPN es opcional y tendrá el valor predeterminado 0.  Si el valor de la columna VPN se establece en 1, la subred representada por esa fila se expandirá por completo para que coincida con todas las direcciones IP de la subred.  Use esto con moderación y solo para subredes VPN, ya que la expansión total de estas subredes tendrá un impacto negativo en los tiempos de consulta para las consultas que implican la creación de datos.

Seleccione gráficos de barras y líneas de tendencia en el informe para mostrar valores detallados. El informe que tiene el foco mostrará el menú de acciones: **Editar,** **Clonar,** **Eliminar,** **Descargar** y **Exportar árbol de informe.**



## <a name="query-filters"></a>Filtros de consulta

Los filtros de consulta se implementan con el Editor de consultas en CQD. Estos filtros se usan para reducir el número de registros devueltos por CQD, minimizando así el tamaño general del informe y los tiempos de consulta. Esto es especialmente útil para filtrar las redes no administradas. Los filtros enumerados en la tabla siguiente usan expresiones regulares (RegEx).


| Filtro         | Descripción          | Ejemplo de filtro de consulta CQD      |
|----------------|----------------------|-------------------------------|
| Sin valores en blanco   | Algunos filtros no tienen la opción de filtrar por valores en blanco. Para filtrar los valores en blanco manualmente, use la expresión en blanco y establezca el filtro en Igual o No es igual, según sus necesidades.      | Second Building Name \<\> \^ \\ s\*\$                       |
| Excluir subredes comunes | Sin un archivo de creación válido para separar las redes administradas de redes no administradas, las redes de inicio se incluirán en los informes. Estas subredes de inicio están fuera del ámbito del control de IT y se pueden excluir rápidamente de un informe. Las subredes comunes, tal como se definen en esta guía, son 10.0.0.0, 192.168.1.0 y 192.168.0.0. | Segunda subred \<\> 10.0.0.0 \| 192.168.0.0 \| 192.168.1.0 |
| Ver solo dentro  | Se usa para filtrar un informe para administrado (dentro) o no administrado (externo). La plantilla CQD administrada ya está preconfigurada con estos filtros.       | Second Inside Corp = Inside        |

## <a name="report-filters"></a>Filtros de informe

Use filtros de informe CQD para restringir el foco de las investigaciones. Use filtros de informe agregando un filtro al informe representado, ya sea en el Editor de consultas o directamente en el informe. Los siguientes filtros de informe se usan en las [plantillas CQD.](https://aka.ms/QERtemplates)


| Filtro     | Descripción                            | Ejemplo de filtro de informe CQD         |
|------------|----------------------------------------|-----------------------------------|
| Month      | Empiece por el año primero y luego por el mes. | 2017-10                           |
| Alfabético | Filtros para cualquier carácter alfabético. | [a-z]                             |
| Numérico    | Filtros para cualquier carácter numérico.    | [0-9]                             |
| Porcentaje | Filtra un porcentaje.              | ([3-9] \\ .) \| ([3-9]) \| ([1-9][0-9]) |


### <a name="drill-down-filters"></a>Filtros de obtención de detalles

Los informes de CQD incluyen varios filtros de desglose, que son herramientas eficaces para restringir el foco de las investigaciones de calidad de llamadas. Si selecciona un campo de desglose, el informe abre automáticamente la pestaña correspondiente y filtra el valor seleccionado. Si esa pestaña tiene sus propios campos de desglose y uno está seleccionado, se aplican ambos conjuntos de filtros, lo que reduce progresivamente el conjunto de datos resultante.

![Diagrama que ilustra el flujo de informes en profundidad](media/qerguide-image-drillthrureportflow.png)


#### <a name="adding-and-editing-drill-down-fields"></a>Agregar y editar campos de obtención de detalles

Al editar un informe, tiene la opción de especificar campos de desglose propios con el Editor de consultas.

Para empezar, haga clic **en ...** para el informe que desea editar y, a continuación, seleccione **Editar.**

![Captura de pantalla de edición de un campo de desglose](media/qerguide-image-addeditdrilldownfields.png)

Seleccione una dimensión de la lista en el lado izquierdo del Editor de consultas. A continuación, haga  clic en el menú desplegable debajo de la etiqueta Navegar a y seleccione la pestaña y el grupo de expansor a los que desea que Dimension explore. Nota: Actualmente, la funcionalidad de desglose solo funciona navegando a diferentes pestañas. Más adelante, se agregará compatibilidad para la exploración a un expander específico. Por último, haga clic **en** Cerrar para  guardar los cambios en la dimensión y, a continuación, haga clic en Guardar para guardar y cerrar el Editor de consultas.

![Captura de pantalla de selección de una dimensión en el Editor de consultas](media/qerguide-image-selectquerydimension.png)

### <a name="multi-select-filters"></a>Filtros de selección múltiple

Además de la funcionalidad de desglose, CQD también admite la especificación de filtros con varios valores (O filtros).

Para seleccionar varios valores de filtro, empiece agregando un nuevo filtro al informe. Haga **+** clic junto a la **etiqueta** Filtros, escriba el nombre de la dimensión que desea usar y haga clic en **Agregar.**

![Captura de pantalla de agregar un filtro de selección múltiple](media/qerguide-image-addmultiselectfilter.png)

A continuación, **haga clic en Buscar** (un icono de lupa junto al nuevo filtro). Verá un campo de texto y varias opciones, como **Seleccionar todo** e **Invertir.** Escriba un valor y haga clic **en Buscar** junto a ese campo para buscar. Como alternativa, deje el campo de texto vacío y haga clic en **Buscar** para ver hasta las primeras 100 opciones.

```powershell
/filter/[AllStreams].[Second Tenant Id]\|[YOUR TENANT ID HERE]
```

Ejemplo:  

![Captura de pantalla de agregar un filtro de consulta](media/qerguide-image-addfilter.png)

### <a name="dashboard-level-filters"></a>Filtros de nivel de panel
Algunos informes de CQD tienen filtros de nivel de panel agregados a ellos, por lo que es fácil filtrar por parámetros comunes. Estos filtros aparecen fuera de las pestañas de informe normales y directamente debajo del filtro Producto, y se aplican a todos los filtros del panel.

![Captura de pantalla de un filtro de panel](media/qerguide-image-dashboardfilters.png)
```powershell
/filter/[AllStreams].[Is Teams]|[TRUE | FALSE]
```

### <a name="url-filters"></a>Filtros de dirección URL

CQD admite la adición de filtros a la dirección URL. Esto facilita compartir o marcar una consulta CQD. Puede definir parámetros en la dirección URL, como Mes de tendencias, id. de inquilino o idioma. También puede agregar filtros de nivel de producto o panel a la dirección URL.
Excluir datos federados de informes CQD es útil al corregir edificios administrados o redes en las que los puntos de conexión federados pueden influir en los informes.

Para agregar un filtro, anexe lo siguiente al final de la dirección URL:

```console
/filter/[AllStreams].[Second Tenant Id]\|[YOUR TENANT ID HERE]
```

Ejemplo:  

`https://cqd.teams.microsoft.com/cqd/#/1234567/2018-08/filter/[AllStreams].[Second Tenant Id]|[TENANTID]`

Para agregar un filtro de nivel de panel a una dirección URL, ese filtro debe existir en CQD como filtro de nivel de producto o panel. Agregue estos filtros a la dirección URL después del mes de tendencias y antes de los parámetros de dirección URL:

`filter/DATA_MODEL_NAME|VALUE`

Por ejemplo, para aplicar un valor de filtro de producto de Microsoft Teams, agregaría lo siguiente:

`filter/[AllStreams].[Is%20Teams]|[True]`

Toda la dirección URL tendría un aspecto parecido a este:

`https://cqd.teams.microsoft.com/spd/#/Dashboard/2624085/2018-9/filter/[AllStreams].[Is%20Teams]|[True]`

Para aplicar filtros URL con valores de selección múltiple, separe cada valor con un carácter de canalización (|). Por ejemplo:

`filter/[AllStreams].[Media%20Type]|[Video]|[Audio]|[VBSS]`

Si especifica un nombre o un valor no válidos, no se aplicará el filtro de dirección URL.


Puede usar un filtro de dirección URL para filtrar cada informe para una dimensión específica. Los filtros url más comunes se usan para filtrar informes para excluir telemetría de participantes federados, o para centrarse solo en Teams o Skype Empresarial Online. Excluir datos federados de informes CQD es útil al corregir edificios administrados o redes en las que los puntos de conexión federados pueden influir en los informes.

| Filtro         | Descripción          | Ejemplo de filtro de consulta CQD      |
|----------------|----------------------|-------------------------------|
| Sin valores en blanco   | Algunos filtros no tienen la opción de filtrar por valores en blanco. Para filtrar los valores en blanco manualmente, use la expresión en blanco y establezca el filtro en Igual o No es igual, según sus necesidades.      | Second Building Name \<\> \^ \\ s\*\$                       |
| Excluir subredes comunes | Sin un archivo de creación válido para separar las redes administradas de redes no administradas, las redes de inicio se incluirán en los informes. Estas subredes de inicio están fuera del ámbito del control de IT y se pueden excluir rápidamente de un informe. Las subredes comunes, tal como se definen en este artículo, son 10.0.0.0, 192.168.1.0 y 192.168.0.0. | Segunda subred \<\> 10.0.0.0 \| 192.168.0.0 \| 192.168.1.0 |
| Ver solo dentro  | Se usa para filtrar un informe para administrado (dentro) o no administrado (externo). La plantilla CQD administrada ya está preconfigurada con estos filtros.       | Second Inside Corp = Inside        |


#### <a name="how-to-find-your-tenant-id"></a>Cómo buscar el id. de inquilino

El id. de inquilino de CQD corresponde al Id. de directorio de Azure. Si no conoce el Id. de directorio, puede encontrarlo en Azure Portal:

1.  Inicie sesión en el Microsoft Azure web:<https://portal.azure.com>

2.  Seleccione **Azure Active Directory**.

3.  En **Administrar**, seleccione **Propiedades**. El id. de inquilino se encuentra en el **cuadro Id. de** directorio.

También puede encontrar su id. de inquilino mediante PowerShell: 

```powershell
Login-AzureRmAccount
```

## <a name="comparing-teams-and-skype-for-business-cqd-data"></a>Comparación Teams datos Skype Empresarial CQD

Al revisar los datos, es posible que vea diferencias en los datos entre Teams y Skype Empresarial. Algunas razones:
- Diferencias en los mecanismos para garantizar el rendimiento y la confiabilidad:
  - Teams la conexión automática y la itinerancia rápida. Skype Empresarial no.
  - Teams administración dinámica de ancho de banda. Skype Empresarial no.
- Diferencias en [los intervalos de](Office-365-URLs-IP-address-ranges.md) direcciones IP entre Teams y Skype Empresarial. Los Teams ip son más recientes, lo que podría causar problemas de conectividad en el firewall.

> [!IMPORTANT]
> A partir del 1 de julio de 2020, la versión heredada de CQD (cqd.lync.com) tiene acceso a los datos del nuevo CQD ( y ya no puede exportar datos de creación e https://CQD.teams.microsoft.com) informe. A partir del 31 de julio de 2021, coincidiendo con la retirada de Skype Empresarial Online, desactivaremos el CQD heredado y ya no podrá acceder a él.


## <a name="related-topics"></a>Temas relacionados

[Mejorar y supervisar la calidad de las llamadas Teams](monitor-call-quality-qos.md)

[¿Qué es CQD?](CQD-what-is-call-quality-dashboard.md)

[Configurar el panel de calidad de llamadas (CQD)](turning-on-and-using-call-quality-dashboard.md)

[Upload inquilino y datos de creación](CQD-upload-tenant-building-data.md)

[Usar CQD para administrar la calidad de las llamadas y las reuniones](quality-of-experience-review-guide.md)

[Dimensiones y medidas disponibles en CQD](dimensions-and-measures-available-in-call-quality-dashboard.md)

[Clasificación de secuencias en CQD](stream-classification-in-call-quality-dashboard.md)

[Usar Power BI para analizar datos CQD](CQD-Power-BI-query-templates.md)
