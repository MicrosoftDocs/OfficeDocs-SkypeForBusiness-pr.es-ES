---
title: Datos e informes en el panel de calidad de llamadas (CQD)
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
description: Obtenga más información sobre los datos y los informes disponibles en el panel de calidad de llamadas de Microsoft (CQD).
ms.openlocfilehash: ec9714e0eae187bc82edf01809b50d8512d04e01
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/06/2020
ms.locfileid: "46583097"
---
# <a name="data-and-reports-in-call-quality-dashboard-cqd"></a>Datos e informes en el panel de calidad de llamadas (CQD)

El panel de calidad de llamadas de Microsoft (CQD) usa una fuente de datos casi en tiempo real (NRT). Los registros de llamadas están disponibles en el CQD en un plazo de 30 minutos a partir de la finalización de una llamada. Los registros de llamadas de la canalización de NRT solo están disponibles durante unos meses antes de que se eliminen del conjunto de datos. 


## <a name="many-ways-to-access-cqd-data"></a>Muchas formas de obtener acceso a datos CQD

Puede acceder a los datos de CQD con varias formas diferentes. Elige el que mejor se adapte a tus necesidades:

|  |  |
|---------|---------|
|Centro de administración de Teams [( https://admin.teams.microsoft.com) ](https://admin.teams.microsoft.com)    | Los datos del CQD se incluyen en la página **usuarios** del centro de administración de equipos, que muestra los datos más comunes que necesita en un formato fácil de leer. No se pueden personalizar los datos del CQD que se encuentran en **usuarios**.  |
|Portal de [CQD https://cqd.teams.microsoft.com) (](https://cqd.teams.microsoft.com)     | Sólidos informes de Resumen y detallados que se ajustan a la mayoría de las necesidades, con filtrado detallado. También puede personalizar informes en el portal de CQD. <br><br>Obtenga dos [plantillas de informes de CQD](#import-the-cqd-report-templates) para ayudarle a analizar datos en el portal de CQD.       |
|Power BI     | Use consultas directas para ver los datos del CQD en Power BI con [plantillas de Power BI personalizables](CQD-Power-BI-query-templates.md). [Descargue las plantillas de consulta de Power BI para el CQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true).<br><br>También puede [usar la API de REST para obtener acceso a los datos de CQD](https://docs.microsoft.com/skypeforbusiness/management-tools/call-quality-dashboard/data-api) a través de Power BI. Use este método si desea descargar los datos del CQD para poder trabajar en él sin conexión. La ventaja de usar este método es un mejor rendimiento, especialmente útil para conjuntos de datos grandes que perjudican a Power BI cuando está conectado.       |
|API de Graph     | Accede a los datos de calidad de las llamadas usted mismo usando la [API Graph](https://docs.microsoft.com/graph/api/resources/callrecords-api-overview?view=graph-rest-beta). Este es el método más complejo, pero proporciona el mayor control y flexibilidad para analizar los datos de calidad de las llamadas. Por ejemplo, si necesita unirse a él con otros datos de su organización, puede usar la API Graph para crear un modelo de datos e incorporar datos de calidad de llamadas.        |

## <a name="import-the-cqd-report-templates"></a>Importar plantillas de informes de CQD

Descargue [dos plantillas de informe de CQD de protegida](https://aka.ms/qertemplates) (todas las redes y las redes administradas) para ayudarle a ponerse al día rápidamente con el CQD. La plantilla todas las redes, aunque optimizada para trabajar con un archivo de datos de creación, se puede usar mientras trabaja para recopilar y cargar información de compilación en el CQD, como se describe en la siguiente sección.

**Para importar las plantillas (. CQDX) en CQD**

1. En el CQD, seleccione **informes detallados** en el menú de la parte superior de la página.

2. En el panel izquierdo, seleccione **importar**. Vaya a la primera plantilla de CQDX y seleccione **abrir**.

3. Una vez que se cargue la plantilla, aparecerá una ventana emergente en la que se muestra el mensaje "la importación del informe se realizó correctamente". 

4. Repita los pasos 2 y 3 para la segunda plantilla de CQD.

> [!NOTE]
> Cada usuario debe importar las plantillas del CQD a su instancia de CQD. 



## <a name="euii-data"></a>Datos de EUII

Por razones de cumplimiento, los datos de información identificable (EUII) de los usuarios finales (también conocidos como información de identificación personal o PII) solo se conservan durante 30 días. A medida que los datos NRT cruzan la marca de 30 días, los campos que contienen EUII se borran, lo que da como resultado datos NRT de EUII gratuitos. Los campos que contienen datos de EUII son los siguientes:

- Dirección IP completa
- Dirección de control de acceso de medios (MAC)
- Identificador de conjunto de servicios (BSSID) básico
- URI del Protocolo de inicio de sesión (SIP) (solo para Skype empresarial)
- Nombre principal de usuario (UPN)
- Nombre del punto final del equipo
- Comentarios literales de usuario
- IDENTIFICADOR de objeto (el identificador de objeto de Active Directory del usuario del punto de conexión)

### <a name="admin-roles-with-and-without-euii-access"></a>Roles de administrador con y sin acceso de EUII

Estos [RBAC](https://docs.microsoft.com/azure/role-based-access-control/overview) roles RBAC **DO** tienen acceso EUII:
- Administrador global
- Administración de servicios de Teams
- Administración de comunicaciones de Teams
- Ingeniero de soporte en comunicaciones de Teams
- Lector global
- Administrador de Skype empresarial

Estos roles de RBAC **no** tienen acceso de EUII:
- Lector de informes
- Especialista de soporte técnico de comunicaciones de Teams


## <a name="date-controls"></a>Controles de fecha

CQD es compatible con los siguientes tipos de tendencia gradual:

- 5 días
- 7 días
- 30 días
- 60 día
- 90 día

El parámetro de fecha de dirección URL acepta un campo de día. Los informes de día rodante usan fechas especificadas en el formato AAAA-MM-DD como el último día de la tendencia. El parámetro de fecha de dirección URL "00" indica "hoy".

|Dirección URL| Fecha de finalización del día de rodadura|
|:---|:---|
|<span>https:// <cqdv3> /SPD/#/Dashboard/ <reportid> /2019-02/</span>   |Día actual del Feb 2019|
|<span>https:// <cqdv3> /SPD/#/Dashboard/ <reportid> /2019-02-15/</span>|15 de febrero de 2019|
|<span>https:// <cqdv3> /SPD/#/Dashboard/ <reportid> /00/</span>        |Día actual|
|||

De forma predeterminada, el día actual del mes se usa como el último día de la tendencia del día acumulado.


## <a name="data-available-in-cqd-reports"></a>Datos disponibles en los informes de CQD

El resumen predeterminado y los informes detallados del CQD pueden ser todo lo que necesitas para administrar la calidad de las llamadas de tu organización. Si es necesario, puede [crear informes personalizados](#create-custom-detailed-reports). 

Si quiere usar Power BI para analizar los datos del CQD, lea [usar Power BI para analizar los datos del CQD de los equipos](CQD-Power-BI-query-templates.md).

|Característica|Informes de Resumen|Informes detallados|
|:--- |:--- |:--- |
|Métrica de uso compartido de aplicaciones | No | Sí |
|Soporte de información de creación de clientes | Sí | Sí |
|Asistencia para la información del extremo del cliente | Solo en <span> CQD.Teams.Microsoft.com<span/> | Solo en <span> CQD.Teams.Microsoft.com<span/> |
|Compatibilidad con análisis detallado   | No   | Sí   |
|Métricas de confiabilidad de multimedia   | No   | Sí   |
|Informes listos para su servicio   | Sí   | Sí   |
|Informes de información general   | Sí   | Sí   |
|Conjunto de informes por usuario   | No   | Sí   |
|Personalización del conjunto de informes (agregar, eliminar, modificar informes)   | No   | Sí   |
|Métricas de pantalla compartida basada en vídeo   | No   | Sí   |
|Métricas de video   | No   | Sí   |
|Cantidad de datos disponibles   | Últimos 12 meses   | Últimos 12 meses   |
|Datos de Microsoft Teams   | Sí   | Sí   |
| | | |


 
### <a name="select-product-data-to-see-in-reports"></a>Seleccionar datos de producto para ver en los informes

En los informes de Resumen y ubicación mejorada, puede usar el menú desplegable **filtro de producto** para mostrar todos los datos de productos, solo los datos de Microsoft Teams o solo los datos de Skype empresarial online.
  
![Captura de pantalla: muestra las opciones de control de filtro de producto](media/206ad818-0f72-4c8e-b25e-3cc8fcfbef05.png)
  
En los informes detallados, puede usar la dimensión **es equipos** para filtrar los datos a Microsoft Teams o a los datos de Skype empresarial online.

## <a name="summary-reports"></a>Informes de Resumen

Estos son los informes que verá en el panel del CQD cuando inicie sesión por primera vez en el CQD. Proporcionan una visión rápida de las tendencias de calidad con informes diarios, mensuales y de tablas para ayudarle a identificar las subredes que tienen una mala calidad. 

|Limitado  |  |
|---------|---------|
|Calidad general de las llamadas     | Agregar las otras 3 pestañas        |
|Servidor: cliente     |Detalles de las transmisiones entre los puntos de conexión de servidor y cliente         |
|Cliente: cliente     |Detalles de las transmisiones entre dos puntos de conexión cliente         |
|SLA de calidad de voz     |Información sobre las llamadas incluidas en el [SLA](https://go.microsoft.com/fwlink/p/?linkid=846252) de calidad de voz de Skype empresarial         |

### <a name="overall-call-quality-tab"></a>Ficha calidad general de las llamadas

Use los datos de esta pestaña para evaluar el estado de la calidad de la llamada y las tendencias en función de los recuentos de flujo y los porcentajes deficientes. La leyenda de la esquina superior derecha muestra el color y los elementos visuales que representan estas métricas.
  
![Captura de pantalla: Mostrar la pestaña calidad de la llamada](media/c8d183b1-6592-49b0-a81d-35cc0568d5f0.png)
  
Las transmisiones se clasifican en tres grupos: buenos, deficientes y no clasificados. También se calculan valores *deficientes de%* que le dan la proporción de las transmisiones clasificadas como *malas* para el número total de streams clasificados. Debido a la mala transferencia de *% = secuencias defectuosas/(secuencias deficientes, secuencias muy buenas) * 100*, el *mal porcentaje* no se ve afectado por la presencia de varias secuencias sin *clasificar* . Para ver qué clasifica una secuencia como mala o buena, consulte [clasificación de secuencias en el panel de calidad de llamadas](stream-classification-in-call-quality-dashboard.md).
  
Use la escala de la izquierda para medir los valores de recuento de transmisiones.
  
![Captura de pantalla: muestra valores de recuento de secuencias](media/850bd25d-d9b2-4df4-8ca6-526a528897c2.png)
  
Use la escala de la derecha para medir los valores de% deficiente.
  
![Captura de pantalla: muestra valores de% deficientes](media/29795f71-ca96-4763-a76c-b4bb7c0e5828.png)
  
También puede obtener los valores numéricos reales colocando el cursor sobre una barra.
  
> [!NOTE]
> El ejemplo siguiente es de un conjunto de datos de ejemplo muy pequeño, y los valores no son realistas para una implementación real.
  
![Captura de pantalla: muestra el mouse usado para obtener acceso a datos](media/8724b016-1a50-4d19-b48a-3b1aae4eb895.png)
  
El volumen de transmisión general permite determinar la relevancia de los porcentajes bajos calculados. Cuanto menor sea el volumen de las transmisiones generales, menos confiable serán los valores de porcentajes deficientes.
  
### <a name="server-client-tab-and-client-client-tabs"></a>Pestaña servidor-cliente y cliente-cliente

Estas dos pestañas proporcionan detalles para las transmisiones que se realizaron en los escenarios de extremo a punto de conexión. La pestaña servidor-cliente tiene cuatro secciones contraíbles que representan cuatro escenarios en los que fluyen las transmisiones multimedia.
  
- Cableado interno
- Cableado fuera
- WiFi Inside
- WiFi fuera

De forma similar, la ficha cliente-cliente tiene cinco secciones contraíbles:

- Cableado interno: cableado interno
- Cableado interno: cableado externo
- Cableado externo: cableado fuera
- Conectado: WiFi Inside
- Cableado interno: WiFi fuera

#### <a name="inside-versus-outside"></a>Dentro frente a fuera

El CQD clasifica una secuencia como *dentro* o *fuera* mediante la información de compilación, si existe. Los puntos de conexión de cada secuencia están asociados con una dirección de subred. Si la subred está en la lista de subredes marcada como InsideCorp en la información de la compilación cargada, se considera *dentro*. Si aún no se ha cargado la generación de información, la prueba dentro de siempre clasifica las transmisiones como *externas*. 

La prueba de dentro para un escenario de cliente de servidor solo tiene en cuenta el punto de conexión de cliente. Como los servidores siempre están fuera del punto de vista del usuario, esto no se tiene en cuenta en la prueba.
  
#### <a name="wired-versus-wifi"></a>Con cable frente a WiFi

Como indican los nombres, los criterios de clasificación se basan en el tipo de conexiones de cliente. El servidor está siempre cableado y no está incluido en el cálculo. En una transmisión determinada, si uno de los dos puntos de conexión está conectado a una red WiFi, el CQD lo clasifica como WiFi.
> [!NOTE]
> Dada una transmisión por secuencias, si uno de los dos puntos de conexión está conectado a una red WiFi, se clasifica como WiFi en el CQD.
  
  
## <a name="tenant-data-information"></a>Información de datos de inquilino

El panel informes de resumen del CQD incluye una página de **carga de datos de inquilino** , a la que se accede seleccionando carga de datos de **inquilino** en el menú configuración en la esquina superior derecha. Esta página se usa para que los administradores carguen su propia información, por ejemplo:

- Mapa de dirección IP e información geográfica
- Un mapa de cada punto de conexión inalámbrico y su dirección MAC
- Un mapa de punto final para la marca, modelo o tipo de extremo, etc.
  
Le recomendamos que cargue los datos de espacio empresarial, creación y ubicación para que el CQD pueda incluir esta información en los informes. Si aún no ha cargado estos datos, lea el [espacio empresarial de carga y los datos de compilación](CQD-upload-tenant-building-data.md). 


## <a name="detailed-reports"></a>Informes detallados

|Nombre  |  |
|---------|---------|
|Informes de ubicación mejorada     |Muestra tendencias de calidad en función de la información de ubicación. Este informe solo aparece si ha [cargado los datos de su espacio empresarial](CQD-upload-tenant-building-data.md).        |
|Informes de confiabilidad     |Incluye informes de audio, vídeo, uso compartido de pantalla basado en vídeo (VBSS) y uso compartido de aplicaciones         |
|Informes sobre la calidad de la experiencia     |Calidad de audio y confiabilidad para todos los clientes y dispositivos, incluidas las salas de reuniones. Estos informes son una versión "Slimmed" de las [plantillas de CQD](https://aka.ms/QERtemplates)descargables, centrándose en las áreas clave para analizar la calidad y la fiabilidad del audio.         |
|Informes de calidad desglosada     | Explorar en profundidad: fecha por región, ubicaciones, subredes, hora y usuarios         |
|Informes de error de análisis detallado     | Explorar en profundidad: fecha por región, ubicaciones, subredes, hora y usuarios        |
|Clasifica mis informes de llamadas     |Analizar la clasificación de llamadas de usuario por región, ubicación o usuario. Incluye comentarios literales.         |
|Informes del Departamento de soporte técnico     |Los informes de asistencia ayudan a consultar los datos de las llamadas y las reuniones de usuarios individuales, grupos de usuarios o todos los usuarios. Con la incorporación de datos de construcción y EUII, estos informes le ayudan a identificar posibles problemas del sistema basados en la ubicación de la red, detalles de la Conferencia, dispositivos o firmware.         |
|Informes de versión de cliente     |Resumen de la versión del cliente: ver las sesiones y los recuentos de usuarios de cada versión de la aplicación cliente<br><br>Versión del cliente por usuario: ver los nombres de usuario de cada versión de la aplicación cliente <br><br>Los filtros predefinidos para el tipo de producto y cliente ayudan a centrar las versiones en clientes específicos.         |
|Informes de extremo     |Muestra la calidad de las llamadas por punto de conexión de máquina (marca de equipo y modelo). Estos informes incluyen la creación de datos, si la ha cargado.         |


## <a name="create-custom-detailed-reports"></a>Crear informes detallados personalizados

Si los informes predeterminados del CQD no satisfacen sus necesidades, siga estas instrucciones para crear un informe personalizado. O (a partir de enero de 2020) [use Power BI para informes de CQD ](cqd-power-bi-query-templates.md).

En la lista desplegable de informes, en la parte superior de la pantalla, que se muestra al inicio de sesión \( la pantalla **informes de Resumen** \) , seleccione **informes detallados** y, a continuación, **nuevo**. Haga clic en **Editar** en un informe para ver el editor de consultas. Cada informe está respaldado por una consulta dentro del cubo. Un informe es una visualización de los datos devueltos por su consulta. El editor de consultas le ayuda a editar estas consultas y las opciones de presentación del informe.
> [!IMPORTANT]
> El intervalo de red se puede usar para representar una superred (combinación de varias subredes con un único prefijo de enrutamiento). Todas las nuevas cargas de creación se marcarán para todos los intervalos superpuestos. Si ha cargado previamente un archivo de compilación, debe descargar el archivo actual y volver a cargarlo para identificar cualquier solapamiento y corregir el problema antes de volver a cargar. Cualquier solapamiento de los archivos cargados previamente puede dar lugar a asignaciones erróneas de subredes a edificios de los informes. Ciertas implementaciones de VPN no informan con precisión de la información de subred. Se recomienda que al agregar una subred VPN al archivo de creación, en lugar de una entrada para la subred, se agreguen entradas independientes para cada dirección de la subred VPN como una red de 32 bits independiente. Cada fila puede tener los mismos metadatos de compilación. Por ejemplo, en lugar de una fila para 172.16.18.0/24, debe tener 256 filas, con una fila por cada dirección entre 172.16.18.0/32 y 172.16.18.255/32, ambos incluidos.
>
> La columna VPN es opcional y se establecerá de forma predeterminada en 0.  Si el valor de la columna VPN se establece en 1, la subred representada por esa fila se expandirá completamente para coincidir con todas las direcciones IP de la subred.  Use esto con moderación y solo para las subredes VPN, ya que la expansión de estas subredes tendrá un impacto negativo en los tiempos de las consultas para las consultas que impliquen datos de compilación.

Seleccione gráficos de barras y líneas de tendencia en el informe para mostrar valores detallados. El informe que tiene el foco mostrará el menú de acciones: **Editar**, **clonar**, **eliminar**, **Descargar**y **exportar árbol de informes**.



## <a name="query-filters"></a>Filtros de consulta

Los filtros de consultas se implementan mediante el editor de consultas del CQD. Estos filtros se usan para reducir el número de registros devueltos por el CQD, lo que minimiza el tamaño global y los tiempos de consulta del informe. Esto es especialmente útil para filtrar las redes no administradas. Los filtros que se muestran en la tabla siguiente usan expresiones regulares (RegEx).


| Filtro         | Descripción          | Ejemplo de filtro de consulta de CQD      |
|----------------|----------------------|-------------------------------|
| No hay valores en blanco   | Algunos filtros no tienen la opción de filtrar por valores en blanco. Para filtrar los valores en blanco manualmente, use la expresión en blanco y establezca el filtro en es igual a o no es igual, en función de sus necesidades.      | Nombre del segundo edificio \<\> \^ \\ s\*\$                       |
| Excluir subredes comunes | Sin un archivo de compilación válido para separar administrado de redes no administradas, las redes domésticas se incluirán en los informes. Estas subredes domésticas están fuera del alcance de su control y se pueden excluir rápidamente de un informe. Las subredes comunes, según se define en esta guía, son 10.0.0.0, 192.168.1.0 y 192.168.0.0. | Segunda subred \<\> 10.0.0.0 \| 192.168.0.0 \| 192.168.1.0 |
| Ver solo dentro de  | Se usa para filtrar un informe por administrado (interno) o no administrado (externo). La plantilla de CQD administrada ya está preconfigurada con estos filtros.       | En el segundo Corp = Inside        |

## <a name="report-filters"></a>Filtros de informe

Use los filtros del informe de CQD para limitar el foco de sus investigaciones. Use los filtros de informe agregando un filtro al informe representado en el editor de consultas o directamente en el informe. Los siguientes filtros de informe se usan en las [plantillas del CQD](https://aka.ms/QERtemplates).


| Filtro     | Descripción                            | Ejemplo de filtro de informe de CQD         |
|------------|----------------------------------------|-----------------------------------|
| Month      | Empiece por el primer año y luego por el mes. | 2017-10                           |
| Alfabético | Filtra cualquier carácter alfabético. | [a-z]                             |
| Alfanumérico    | Filtra por cualquier carácter numérico.    | [0-9]                             |
| Porcentaje | Filtra por un porcentaje.              | ([3-9] \\ ) \| . ([3-9]) \| ([1-9] [0-9]) |


### <a name="drill-down-filters"></a>Filtros de desglose

Los informes de CQD incluyen varios filtros de obtención de detalles, que son herramientas eficaces para limitar el foco de las investigaciones de calidad de la llamada. Si selecciona un campo de obtención de detalles, el informe abre automáticamente la pestaña correspondiente y los filtros en el valor seleccionado. Si la pestaña tiene sus propios campos de detalle y está seleccionado uno, se aplican ambos conjuntos de filtros, lo que reduce progresivamente el conjunto de datos resultante.

![Diagrama que ilustra el flujo de informe detallado](media/qerguide-image-drillthrureportflow.png)


#### <a name="adding-and-editing-drill-down-fields"></a>Agregar y editar campos de obtención de detalles

Al editar un informe, tiene la opción de especificar su propio campo de detalle mediante el editor de consultas.

Para empezar, haga clic en **...** para el informe que desea editar y, a continuación, seleccione **Editar**.

![Captura de pantalla de la edición de un campo de obtención de detalles](media/qerguide-image-addeditdrilldownfields.png)

Seleccione una dimensión de la lista en el lado izquierdo del editor de consultas. Después, haga clic en la lista desplegable que hay debajo de **ir a** la etiqueta y seleccione la pestaña y el grupo de expansión con los que desea obtener detalles. Nota: Actualmente, la funcionalidad de desglose solo funciona desplazándose a otras pestañas. La compatibilidad para desplazarse por un expansor específico se agregará más adelante. Por último, haga clic en **cerrar** para guardar los cambios en la dimensión y, a continuación, haga clic en **Guardar** para guardar y cerrar el editor de consultas.

![Captura de pantalla de selección de una dimensión en el editor de consultas](media/qerguide-image-selectquerydimension.png)

### <a name="multi-select-filters"></a>Filtros de selección múltiple

Además de la funcionalidad de obtención de detalles, el CQD también admite la especificación de filtros con varios valores (o filtros).

Para seleccionar varios valores de filtro, empiece agregando un filtro nuevo al informe. Haga clic **+** junto a la etiqueta **filtros** , escriba el nombre de la dimensión que desea usar y haga clic en **Agregar**.

![Captura de pantalla de la adición de un filtro de selección múltiple](media/qerguide-image-addmultiselectfilter.png)

Después, haga clic en **Buscar** (un icono de lupa junto al nuevo filtro). Verá un campo de texto y varias opciones, entre las que se incluyen **seleccionar todo** e **invertir**. Escriba un valor y haga clic en **Buscar** , junto a ese campo, para buscar. Como alternativa, deje el campo de texto en blanco y haga clic en **Buscar** para ver hasta las primeras 100 opciones.

```PowerShell
/filter/[AllStreams].[Second Tenant Id]\|[YOUR TENANT ID HERE]
```

Ejemplo  

![Captura de pantalla de adición de un filtro de consulta](media/qerguide-image-addfilter.png)

### <a name="dashboard-level-filters"></a>Filtros de nivel de panel
Ciertos informes de CQD tienen los filtros de nivel de panel agregados, lo que facilita la tarea de filtrar por parámetros comunes. Estos filtros aparecen fuera de las pestañas del informe normal y directamente debajo del filtro de producto, y se aplican a todos los filtros del panel.

![Captura de pantalla de un filtro de panel](media/qerguide-image-dashboardfilters.png)
```PowerShell
/filter/[AllStreams].[Is Teams]|[TRUE | FALSE]
```

### <a name="url-filters"></a>Filtros de URL

El CQD admite la adición de filtros a la dirección URL. Esto facilita la tarea de compartir o marcar una consulta de CQD. Puede definir parámetros en la dirección URL, como el mes de tendencias, el identificador de inquilino o el idioma. También puede Agregar filtros de nivel de producto o de panel a la dirección URL.
La exclusión de datos federados de informes de CQD es útil cuando se corrigen edificios administrados o redes en las que los puntos de conexión federados pueden influir en los informes.

Para agregar un filtro, anexe lo siguiente al final de la dirección URL:

```
/filter/[AllStreams].[Second Tenant Id]\|[YOUR TENANT ID HERE]
```

Ejemplo  

```https://cqd.teams.microsoft.com/cqd/#/1234567/2018-08/filter/[AllStreams].[Second Tenant Id]|[TENANTID]```

Para agregar un filtro de nivel de panel a una dirección URL, ese filtro debe existir en el CQD como filtro de nivel de panel o producto. Agregue estos filtros a la dirección URL después del mes de tendencia y antes de los parámetros de la dirección URL:

```filter/DATA_MODEL_NAME|VALUE```

Por ejemplo, para aplicar un valor de filtro de producto de Microsoft Teams, debe agregar lo siguiente:

```filter/[AllStreams].[Is%20Teams]|[True]```

La dirección URL completa tendría un aspecto similar a este:

```https://cqd.teams.microsoft.com/spd/#/Dashboard/2624085/2018-9/filter/[AllStreams].[Is%20Teams]|[True]```

Para aplicar filtros de URL con valores de selección múltiple, separe cada valor con un carácter de barra vertical (|). Por ejemplo:

```filter/[AllStreams].[Media%20Type]|[Video]|[Audio]|[VBSS]```

Si especifica un nombre o valor no válido, no se aplicará el filtro de dirección URL.


Puede usar un filtro de URL para filtrar cada informe para una dimensión específica. Los filtros de URL más comunes se usan para filtrar los informes con el fin de excluir la telemetría de participantes federados, o centrarse en solo equipos o Skype empresarial online. La exclusión de datos federados de informes de CQD es útil cuando se corrigen edificios administrados o redes en las que los puntos de conexión federados pueden influir en los informes.

| Filtro         | Descripción          | Ejemplo de filtro de consulta de CQD      |
|----------------|----------------------|-------------------------------|
| No hay valores en blanco   | Algunos filtros no tienen la opción de filtrar por valores en blanco. Para filtrar los valores en blanco manualmente, use la expresión en blanco y establezca el filtro en es igual a o no es igual, en función de sus necesidades.      | Nombre del segundo edificio \<\> \^ \\ s\*\$                       |
| Excluir subredes comunes | Sin un archivo de compilación válido para separar administrado de redes no administradas, las redes domésticas se incluirán en los informes. Estas subredes domésticas están fuera del alcance de su control y se pueden excluir rápidamente de un informe. Las subredes comunes, según se define en este artículo, son 10.0.0.0, 192.168.1.0 y 192.168.0.0. | Segunda subred \<\> 10.0.0.0 \| 192.168.0.0 \| 192.168.1.0 |
| Ver solo dentro de  | Se usa para filtrar un informe por administrado (interno) o no administrado (externo). La plantilla de CQD administrada ya está preconfigurada con estos filtros.       | En el segundo Corp = Inside        |


#### <a name="how-to-find-your-tenant-id"></a>Cómo encontrar su identificador de inquilino

El identificador de inquilino de CQD corresponde al identificador de directorio de Azure. Si no conoce el identificador de su directorio, puede encontrarlo en el portal de Azure:

1.  Inicie sesión en el portal de Microsoft Azure:<https://portal.azure.com>

2.  Seleccione **Azure Active Directory**.

3.  En **administrar**, seleccione **propiedades**. Su identificador de inquilino se encuentra en el cuadro **identificador de directorio** .

También puede encontrar su identificador de inquilino con PowerShell: 
  ```
  Login-AzureRmAccount
  ```



## <a name="comparing-teams-and-skype-for-business-cqd-data"></a>Comparación de equipos y datos del CQD de Skype empresarial

Incluso dentro del último CQD (cqd.teams.microsoft.com), verá diferencias en los datos entre los equipos y Skype empresarial. Algunas razones:
- Diferencias en los mecanismos para garantizar el rendimiento y la confiabilidad
  - Teams tiene la reconexión automática y la itinerancia rápida. Skype para empresas no lo hace.
  - Teams tiene administración dinámica de ancho de banda. Skype para empresas no lo hace.
- Diferencias en los [intervalos de direcciones IP](Office-365-URLs-IP-address-ranges.md) entre Teams y Skype empresarial. Los intervalos IP de Teams son más recientes, lo que puede provocar problemas de conectividad en el firewall.

## <a name="open-cqd-from-the-skype-for-business-legacy-portal"></a>Abrir CQD desde el portal heredado de Skype empresarial

![Un icono del logotipo de Skype empresarial ](media/sfb-logo-30x30.png) **con el portal heredado de Skype empresarial**

1. Inicie sesión en su organización de Office 365 con una cuenta de administrador y, a continuación, seleccione el icono **Administrador** para abrir el centro de administración.
2. En el panel izquierdo, en **centros de administración**, seleccione **Microsoft Teams** para abrir el centro de administración de Teams.
3. En el centro de administración de Teams, seleccione **portal heredado** en el panel izquierdo, seleccione **herramientas**y, a continuación, seleccione **Panel de calidad de llamadas de Skype empresarial online**.

     ![Captura de pantalla: seleccionar el panel de calidad de llamadas](media/6cc7f80f-b8e2-4a9b-aab8-ac871d07a261.png)

4. En la página que se abre, inicie sesión con su cuenta de administrador global y, a continuación, proporcione las credenciales de la cuenta cuando se le solicite.

Después de iniciar sesión por primera vez, el CQD comenzará a recopilar y procesar datos. 

> [!IMPORTANT]
> A partir del 2019 de diciembre, aún puede acceder a la versión anterior del CQD (cqd.lync.com), aunque el portal heredado le ofrece un vínculo al último CQD (cqd.teams.microsoft.com). Finalmente, la versión anterior del CQD se recargará. A partir del 1 de julio de 2020, la versión anterior del CQD accede a los datos desde el nuevo CQD ( https://CQD.teams.microsoft.com) y ya no puede exportar datos de compilación ni de informes. Durante el 2020 de tarde, desactivaremos el CQD antiguo y ya no podrá acceder a él.


## <a name="related-topics"></a>Temas relacionados

[Mejorar y supervisar la calidad de las llamadas de los equipos](monitor-call-quality-qos.md)

[¿Qué es el CQD?](CQD-what-is-call-quality-dashboard.md)

[Configurar el panel de calidad de llamadas (CQD)](turning-on-and-using-call-quality-dashboard.md)

[Cargar inquilino y datos de compilación](CQD-upload-tenant-building-data.md)

[Usar el CQD para administrar la calidad de las llamadas y reuniones](quality-of-experience-review-guide.md)

[Dimensiones y medidas disponibles en el CQD](dimensions-and-measures-available-in-call-quality-dashboard.md)

[Clasificación de flujo en el CQD](stream-classification-in-call-quality-dashboard.md)

[Usar Power BI para analizar los datos del CQD](CQD-Power-BI-query-templates.md)
