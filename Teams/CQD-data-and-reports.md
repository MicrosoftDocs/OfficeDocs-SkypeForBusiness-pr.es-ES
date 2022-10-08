---
title: Datos e informes en el Panel de calidad de llamadas (CQD)
author: CarolynRowe
ms.author: crowe
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
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Reporting
- ms.lync.lac.ToolsCallQualityDashboard
- seo-marvel-apr2020
description: Obtenga información sobre los datos e informes disponibles en el Panel de calidad de llamadas (CQD) de Microsoft.
ms.openlocfilehash: 7d89c17f299302f39e00e6aebcfd9309ead3eaae
ms.sourcegitcommit: 021cfac01a38282a8cde6e913d74be2d54c39162
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2022
ms.locfileid: "68218519"
---
# <a name="data-and-reports-in-call-quality-dashboard-cqd"></a>Datos e informes en el Panel de calidad de llamadas (CQD)

El Panel de calidad de llamadas de Microsoft (CQD) usa una fuente de datos casi en tiempo real (NRT). Los registros de llamadas están disponibles en el CQD en un plazo de 30 minutos desde el final de una llamada. Los registros de llamadas de la canalización de NRT solo están disponibles durante unos meses antes de que se quiten del conjunto de datos.

## <a name="many-ways-to-access-cqd-data"></a>Muchas formas de acceder a los datos del CQD

Puede acceder a los datos del CQD por varias vías diferentes. Elige el que mejor se adapte a tus necesidades:

|&nbsp;|&nbsp;|
|---|---|
|Centro de administración de Teams [(https://admin.teams.microsoft.com)](https://admin.teams.microsoft.com)|Los datos del CQD se incluyen en la página **Usuarios** del Centro de administración de Teams, que muestra los datos más comunes que necesita en un formato fácil de leer. No puede personalizar los datos del CQD que encuentre en **Usuarios**.|
|Portal del CQD [(https://cqd.teams.microsoft.com)](https://cqd.teams.microsoft.com)|Informes resumidos y detallados robustos que satisfacen la mayoría de las necesidades, con filtrado detallado. También puede personalizar los informes en el portal del CQD. <br><br>Obtenga dos [plantillas de informes del CQD](#import-the-cqd-report-templates) para ayudarle a analizar datos en el portal del CQD.|
|Power BI|Use consultas directas para ver los datos del CQD en Power BI con [plantillas de Power BI personalizables](CQD-Power-BI-query-templates.md). [Descargue plantillas de consulta de Power BI para el CQD](https://www.microsoft.com/download/details.aspx?id=102291).<br><br>También puede [usar la API de REST para acceder a los datos del CQD](/skypeforbusiness/management-tools/call-quality-dashboard/data-api) a través de Power BI. Use este método si desea descargar los datos del CQD para poder trabajar en ellos sin conexión. La ventaja de usar este método es un mejor rendimiento, especialmente útil para conjuntos de datos de gran tamaño que se inundan de Power BI cuando está en línea.|
|API de Graph|Acceda a los datos de calidad de llamada usted mismo con la [Graph API](/graph/api/resources/callrecords-api-overview). Este es el método más complejo, pero le ofrece el mayor control y flexibilidad para analizar los datos de calidad de las llamadas. Por ejemplo, si necesita combinarlos con otros datos de su organización, puede usar la Graph API para crear un modelo de datos e incorporar datos de calidad de llamadas.|

## <a name="import-the-cqd-report-templates"></a>Importar las plantillas de informes del CQD

Descargue [dos plantillas de informes del CQD protegidas](https://aka.ms/qertemplates) (Todas las redes y redes administradas) para ayudarle a ponerse al día rápidamente con el CQD. La plantilla Todas las redes, aunque optimizada para trabajar con un archivo de datos de compilación, se puede usar mientras trabaja para recopilar y cargar información de compilación en el CQD, como se describe en la sección siguiente.

**Para importar las plantillas (. CQDX) en el CQD**:

1. En el CQD, seleccione **Informes detallados** en el menú de la parte superior de la página.

2. En el panel izquierdo, selecciona **Importar**. Vaya a la primera plantilla CQDX y seleccione **Abrir**.

3. Después de cargar la plantilla, se mostrará el mensaje "Informe de importación correcta".

4. Repita los pasos 2 y 3 para la segunda plantilla del CQD.

   > [!NOTE]
   > Cada usuario debe importar las plantillas del CQD a su instancia de CQD.

## <a name="euii-data"></a>Datos DE LA UEII

Por motivos de cumplimiento, los datos de información de identificación del usuario final (EUII) (también conocidos como información de identificación personal o PII) solo se conservan durante 28 días. A medida que los datos NRT cruzan la marca de 28 días, los campos que contienen EUII se borran, lo que da lugar a datos NRT sin EUII. Los campos que contienen datos EUII son:

- Dirección IP completa
- Dirección de Access Control multimedia (MAC)
- Identificador del conjunto de servicios básicos (BSSID)
- URI del Protocolo de inicio de sesión (SIP) (solo Skype Empresarial)
- Nombre principal de usuario (UPN)
- Nombre del extremo de máquina
- Comentarios textuales del usuario
- Id. de objeto (el id. de objeto de Active Directory del usuario del punto de conexión)
- Número de teléfono
- Identidad del operador automático
- Identidad de la cola de llamadas
- Nombre del dispositivo de Video Teleconferencing (VTC)
- Detalle del dispositivo de teleconferencia de vídeo (VTC)

### <a name="admin-roles-with-and-without-euii-access"></a>Administración funciones con y sin acceso a LA UEII

Estos roles [RBAC](/azure/role-based-access-control/overview) **DO** tienen acceso EUII:

- Administración global
- Administración de servicio de Teams
- Administración de comunicaciones de Teams
- Ingeniero de soporte en comunicaciones de Teams
- Lector global
- Skype Empresarial Administración

Estos roles RBAC **NO** tienen acceso EUII:

- Lector de informes
- Especialista en soporte técnico de comunicaciones de Teams

## <a name="date-controls"></a>Controles de fecha

El CQD admite los siguientes tipos de tendencias graduales:

- 5 días
- 7 días
- 30 días
- 60 días
- 90 días

El parámetro Url Date acepta un campo Day. Los informes de días graduales usan las fechas especificadas en el formato AAAA-MM-DD como el último día de la tendencia. El parámetro de fecha de la dirección URL "00" indica "hoy".

|Dirección URL|Fecha de finalización de la tendencia del día móvil|
|:---|:---|
|<span>\<cqdv3>https:///spd/#/Dashboard/\<reportid>/2019-02/</span>|Día actual de febrero de 2019|
|<span>\<cqdv3>https:///spd/#/Dashboard/\<reportid>/2019-02-15/</span>|15 de febrero de 2019|
|<span>\<cqdv3>https:///spd/#/Dashboard/\<reportid>/00/</span>|Día actual|

De forma predeterminada, el día actual del mes se usa como último día de la tendencia de día móvil.

## <a name="data-available-in-cqd-reports"></a>Datos disponibles en los informes del CQD

El resumen predeterminado y los informes detallados del CQD pueden ser todo lo que necesita para administrar la calidad de las llamadas para su organización. Si lo necesita, puede [crear informes personalizados](#create-custom-detailed-reports).

Si desea usar Power BI para analizar los datos del CQD, lea [Usar Power BI para analizar los datos del CQD para Teams](CQD-Power-BI-query-templates.md).

|Característica|Informes de resumen|Informes detallados|
|:---|:---|:---|
|Métrica de uso compartido de aplicaciones|No|Sí|
|Soporte de información de compilación del cliente|Sí|Sí|
|Soporte de información del punto de conexión del cliente|Solo en <span>cqd.teams.microsoft.com<span/>|Solo en <span>cqd.teams.microsoft.com<span/>|
|Compatibilidad con análisis de detalles|No|Sí|
|Métricas de confiabilidad de medios|No|Sí|
|Informes predefinidos|Sí|Sí|
|Informes de información general|Sí|Sí|
|Conjunto de informes por usuario|No|Sí|
|Personalización del conjunto de informes (agregar, eliminar, modificar informes)|No|Sí|
|Métricas de pantalla compartida basada en vídeo|No|Sí|
|Métricas de vídeo|No|Sí|
|Cantidad de datos disponibles|Últimos 12 meses|Últimos 12 meses|
|Datos de Microsoft Teams|Sí|Sí|

### <a name="select-product-data-to-see-in-reports"></a>Seleccionar datos de producto para ver en los informes

En los Informes de resumen y Location-Enhanced, puede usar el menú desplegable **Filtro** de producto para mostrar todos los datos del producto, solo los datos de Microsoft Teams o solo Skype Empresarial datos en línea.

> [!div class="mx-imgBorder"]
> ![Captura de pantalla: muestra las opciones de control Filtro de producto.](media/206ad818-0f72-4c8e-b25e-3cc8fcfbef05.png)

En informes detallados, puede usar la dimensión **Is Teams** para filtrar los datos a Microsoft Teams o Skype Empresarial datos en línea.

## <a name="summary-reports"></a>Informes de resumen

Estos son los informes que verá en el panel del CQD la primera vez que inicie sesión en el CQD. Le ofrecen un vistazo a las tendencias de calidad con informes diarios, mensuales y de tabla para ayudarle a identificar las subredes que tienen mala calidad.

|Pestaña|Descripción|
|---|---|
|Calidad general de las llamadas|Agregado de las otras 3 pestañas.|
|Servidor: cliente|Detalles de las transmisiones entre los puntos de conexión de servidor y cliente.|
|Cliente: cliente|Detalles de las transmisiones entre dos puntos de conexión de cliente.|
|SLA de calidad de voz|Información sobre las llamadas incluidas en el sla [de calidad de](https://go.microsoft.com/fwlink/p/?linkid=846252) voz Skype Empresarial.|

### <a name="overall-call-quality-tab"></a>Pestaña Calidad general de llamadas

Use los datos de esta pestaña para evaluar el estado y las tendencias de la calidad de las llamadas en función de los recuentos de transmisiones y los porcentajes bajos. La leyenda de la esquina superior derecha muestra qué color y elementos visuales representan estas métricas.

> [!div class="mx-imgBorder"]
> ![Captura de pantalla: mostrar la pestaña Calidad de llamada.](media/c8d183b1-6592-49b0-a81d-35cc0568d5f0.png)

Las transmisiones se clasifican en tres grupos: Buena, Mala y Sin clasificar. También se calculan valores  *% de mala*  calidad que le proporcionan la relación de transmisiones clasificadas como *Malas*  con el recuento total de transmisiones clasificadas. Dado que *% de mala calidad = Transmisiones de mala calidad/(Transmisiones de mala calidad + Transmisiones buenas) \* 100*, el % de mala *calidad* no se ve afectado por la presencia de varias transmisiones *sin clasificar*  . Para ver lo que clasifica una transmisión como mala o buena, consulte Clasificación de [Stream en el panel de calidad de llamadas](stream-classification-in-call-quality-dashboard.md).

Use la escala de la izquierda para medir los valores de recuento de transmisiones.

> [!div class="mx-imgBorder"]
> ![Captura de pantalla: muestra los valores de recuento de transmisiones.](media/850bd25d-d9b2-4df4-8ca6-526a528897c2.png)

Use la escala de la derecha para medir los valores de Porcentaje pobre.

> [!div class="mx-imgBorder"]
> ![Captura de pantalla: muestra los valores de % de mala calidad.](media/29795f71-ca96-4763-a76c-b4bb7c0e5828.png)

También puede obtener los valores numéricos reales manteniendo el mouse sobre una barra.

> [!NOTE]
> El ejemplo siguiente es de un conjunto de datos muy pequeño y los valores no son realistas para una implementación real.

> [!div class="mx-imgBorder"]
> ![Captura de pantalla: muestra el mouse usado para acceder a los datos.](media/8724b016-1a50-4d19-b48a-3b1aae4eb895.png)

El volumen general de transmisiones ayuda a determinar la relevancia de los porcentajes de mala calidad calculados. Cuanto menor sea el volumen de transmisiones en general, menos confiables son los valores de porcentaje de mala calidad notificados.

### <a name="server-client-tab-and-client-client-tabs"></a>pestaña Server-Client y pestañas de Client-Client

Estas dos pestañas proporcionan detalles para las transmisiones que tuvieron lugar en sus escenarios de punto de conexión a punto de conexión. La pestaña Server-Client tiene cuatro secciones contraíbles que representan cuatro escenarios en los que fluirían las transmisiones multimedia.

- Cableado interno
- Cableado externo
- Wi-Fi en el interior
- WiFi fuera

De forma similar, la pestaña Client-Client tiene cinco secciones contraíbles:

- Interior cableada: interior cableada
- Cableado interno: cableado externo
- Cableado externo: cableado externo
- Cableada: WiFi interior
- Cableada en el interior: WiFi fuera

#### <a name="inside-versus-outside"></a>Inside versus Outside

El CQD clasifica una transmisión como  *Interna*  o *Externa*  con información de compilación, si existe. Los puntos de conexión de cada transmisión están asociados a una dirección de subred. Si la subred está en la lista de las subredes marcadas como InsideCorp en la información de compilación cargada, se considera *Interna*. Si aún no se ha cargado la información de compilación, prueba interna siempre clasifica las transmisiones como *externas*.

La prueba interna de un escenario Server-Client solo tiene en cuenta el punto de conexión del cliente. Como los servidores siempre están fuera de la perspectiva de un usuario, esto no se tiene en cuenta en la prueba.

#### <a name="wired-versus-wifi"></a>Cableada frente a Wi-Fi

Como los nombres indican, los criterios de clasificación se basan en el tipo de conexiones de cliente. El servidor siempre está cableado y no se incluye en el cálculo. En una secuencia determinada, si uno de los dos puntos de conexión está conectado a una red Wi-Fi, el CQD lo clasifica como WiFi.

> [!NOTE]
> Dada una transmisión, si uno de los dos puntos de conexión está conectado a una red Wi-Fi, entonces se clasifica como WiFi en el CQD.

## <a name="tenant-data-information"></a>Información de datos del inquilino

El panel Informes de resumen del CQD incluye una página **Carga de datos del inquilino** , a la que se tiene acceso seleccionando Carga de datos del **inquilino** en el menú de configuración de la esquina superior derecha. Esta página se usa para que los administradores carguen su propia información, como:

- Un mapa de la dirección IP y la información geográfica.
- Un mapa de cada AP inalámbrico y su dirección MAC.
- Un mapa del punto de conexión a la marca, modelo o tipo del punto de conexión, etc.

Le recomendamos que cargue los datos de inquilino, edificio y ubicación para que el CQD pueda incluir esta información en sus informes. Si aún no ha cargado estos datos, lea [Cargar inquilino y datos de compilación](CQD-upload-tenant-building-data.md).

## <a name="detailed-reports"></a>Informes detallados

|Nombre|Descripción|
|---|---|
|Informes de Location-Enhanced|Muestra tendencias de calidad en función de la información de ubicación. Este informe solo aparece si ha cargado los [datos del espacio empresarial](CQD-upload-tenant-building-data.md).|
|Informes de confiabilidad|Incluye audio, vídeo, pantalla compartida basada en vídeo (VBSS) e informes de uso compartido de aplicaciones.|
|Informes de calidad de la experiencia|Calidad y confiabilidad de audio para todos los clientes y dispositivos, incluidas las salas de reuniones. Estos informes son una versión "reducida" de las [plantillas descargables del CQD](https://aka.ms/QERtemplates), centrándose en áreas clave para analizar la calidad y confiabilidad del audio.|
|Informes de obtención de detalles de calidad|Detalles: fecha por región, ubicaciones, subredes, hora y usuarios.|
|Informes de resumen de errores|Detalles: fecha por región, ubicaciones, subredes, hora y usuarios.|
|Calificar los informes de llamadas|Analice las clasificaciones de las llamadas de usuario por región, ubicación o por usuario. Incluye comentarios textuales.|
|Informes del departamento de soporte técnico|Los informes del departamento de soporte técnico analizan los datos de llamadas y reuniones de usuarios individuales, grupos de usuarios o de todos. Estos informes, que incorporan datos de edificios y EUII, ayudan a identificar posibles problemas del sistema en función de la ubicación de la red, los detalles de conferencia, los dispositivos o el firmware.|
|Informes de la versión del cliente|Resumen de la versión de cliente: Ver el recuento de sesiones y usuarios para cada versión de la aplicación cliente<br><br>Versión de cliente por usuario: Ver nombres de usuario para cada versión de la aplicación cliente <br><br>Los filtros predefinidos para tipo de producto y cliente ayudan a centrar las versiones en clientes específicos.|
|Informes de extremo|Muestra la calidad de la llamada por puntos de conexión de la máquina (marca y modelo del equipo). Estos informes incluyen datos de compilación, si los ha cargado.|

## <a name="create-custom-detailed-reports"></a>Crear informes detallados personalizados

Si los informes del CQD predeterminados no satisfacen sus necesidades, use estas instrucciones para crear un informe personalizado. O bien (a partir de enero de 2020) Use en su lugar [los informes de Power BI para el CQD ](cqd-power-bi-query-templates.md).

En la lista desplegable de informes en la parte superior de la pantalla que se muestra al iniciar sesión \(en la pantalla\) **Informes de resumen**, seleccione **Informes detallados** y, después, **Nuevo**. Haga clic en **Editar** en un informe para ver la Editor de Power Query. Cada informe está respaldado por una consulta dentro del cubo. Un informe es una visualización de los datos devueltos por su consulta. La Editor de Power Query le ayuda a editar estas consultas y las opciones de presentación del informe.

> [!IMPORTANT]
> El rango de red se puede utilizar para representar una superred (combinación de varias subredes con un solo prefijo de enrutamiento). Todas las nuevas cargas de compilación se comprobarán en busca de intervalos superpuestos. Si ha cargado anteriormente un archivo de compilación, debe descargar el archivo actual y volver a cargarlo para identificar cualquier solapamiento y corregir el problema antes de volver a cargarlo. Cualquier superposición en los archivos cargados anteriormente puede producir asignaciones incorrectas de subredes a edificios en los informes. Algunas implementaciones VPN no notifican con precisión la información de subred. Se recomienda que, al agregar una subred VPN al archivo de compilación, en lugar de una entrada para la subred, se agreguen entradas independientes para cada dirección de la subred VPN como una red independiente de 32 bits. Cada fila puede tener los mismos metadatos de compilación. Por ejemplo, en lugar de una fila para 172.16.18.0/24, debería tener 256 filas, con una fila para cada dirección entre 172.16.18.0/32 y 172.16.18.255/32, ambos inclusive.
>
> La columna VPN es opcional y se convertirá de forma predeterminada en 0.  Si el valor de la columna VPN se establece en 1, la subred representada por esa fila se ampliará por completo para que coincida con todas las direcciones IP dentro de la subred.  Use esto con moderación y solo para las subredes VPN, ya que la ampliación total de estas subredes tendrá un impacto negativo en los tiempos de consulta de las consultas que implican la creación de datos.

Seleccione gráficos de barras y líneas de tendencia en el informe para mostrar valores detallados. El informe que tiene el foco mostrará el menú de acciones: **Editar**, **Clonar**, **Eliminar**, **Descargar** y **Exportar árbol de informes**.

## <a name="query-filters"></a>Filtros de consulta

Los filtros de consulta se implementan con la Editor de Power Query en el CQD. Estos filtros se usan para reducir el número de registros devueltos por el CQD, minimizando así el tamaño general del informe y los tiempos de consulta. Esto es especialmente útil para filtrar redes no administradas. Los filtros enumerados en la tabla siguiente usan expresiones regulares (RegEx).

|Filtro|Descripción|Ejemplo de filtro de consulta del CQD|
|---|---|---|
|No hay valores en blanco|Algunos filtros no tienen la opción de filtrar por valores en blanco. Para filtrar los valores en blanco manualmente, use la expresión en blanco y establezca el filtro como Igual o No es igual a, según sus necesidades.|Second Building Name \<\> \^\\s\*\$|
|Excluir subredes comunes|Sin un archivo de compilación válido para separar las redes administradas de las no administradas, las redes domésticas se incluirán en los informes. Estas subredes domésticas están fuera del ámbito del control de TI y se pueden excluir rápidamente de un informe. Las subredes comunes, según se define en esta guía, son 10.0.0.0, 192.168.1.0 y 192.168.0.0.|Second Subnet \<\> 10.0.0.0 \|192.168.0.0 \|192.168.1.0|
|Solo ver en el interior|Se usa para filtrar un informe para administrar (dentro) o no administrado (fuera). La plantilla administrada del CQD ya está preconfigurada con estos filtros.|Second Inside Corp = Inside|

## <a name="report-filters"></a>Filtros de informe

Use filtros de informe del CQD para limitar el foco de las investigaciones. Use filtros de informe agregando un filtro al informe representado, ya sea en la Editor de Power Query o directamente en el informe. Los siguientes filtros de informe se usan en las [plantillas del CQD](https://aka.ms/QERtemplates).

|Filtro|Descripción|Ejemplo de filtro de informe del CQD|
|---|---|---|
|Month|Empiece por el año primero y, después, por el mes.|2017-10|
|Alfabético|Filtros para cualquier carácter alfabético.|[a-z]|
|Numérico|Filtra los caracteres numéricos.|[0-9]|
|Porcentaje|Filtros para un porcentaje.|([3-9]\\.)\| ([3-9])\| ([1-9][0-9])|

### <a name="drill-down-filters"></a>Filtros de obtención de detalles

Los informes del CQD incluyen varios filtros de obtención de detalles, que son potentes herramientas para restringir el foco de las investigaciones de calidad de llamada. Si selecciona un campo de obtención de detalles, el informe abrirá automáticamente la pestaña correspondiente y filtrará el valor seleccionado. Si esa pestaña tiene sus propios campos de obtención de detalles y uno está seleccionado, se aplican ambos conjuntos de filtros, lo que reduce progresivamente el conjunto de datos resultante.

![Diagrama que ilustra el flujo del informe de obtención de detalles.](media/qerguide-image-drillthrureportflow.png)

#### <a name="adding-and-editing-drill-down-fields"></a>Agregar y editar campos de obtención de detalles

Al editar un informe, tiene la opción de especificar campos de obtención de detalles propios con la Editor de Power Query.

Para empezar, haga clic en **...** para el informe que quiera editar y, después, seleccione **Editar**.

![Captura de pantalla de la edición de un campo de obtención de detalles.](media/qerguide-image-addeditdrilldownfields.png)

Seleccione una Cota de la lista situada en el lado izquierdo de la Editor de Power Query. Después, haga clic en la lista desplegable debajo de la etiqueta **Navegar a** y seleccione la pestaña y el grupo de expansión a los que desea que Dimension explore en profundidad. Nota: Actualmente, la funcionalidad de obtención de detalles solo funciona navegando a diferentes pestañas. La compatibilidad para perforar a través de un expansor específico se agregará más adelante. Por último, haga clic en **Cerrar** para guardar los cambios en la dimensión y, a continuación, haga clic en **Guardar** para guardar y cerrar la Editor de Power Query.

![Captura de pantalla de selección de una dimensión en el Editor de Power Query.](media/qerguide-image-selectquerydimension.png)

### <a name="multi-select-filters"></a>Filtros de selección múltiple

Además de la funcionalidad de obtención de detalles, el CQD también admite la especificación de filtros con varios valores (filtros OR).

Para seleccionar varios valores de filtro, empiece agregando un nuevo filtro al informe. Haga clic **+** junto a la etiqueta **Filtros** , escriba el nombre de la dimensión que desea usar y haga clic en **Agregar**.

![Captura de pantalla en la que se agrega un filtro de selección múltiple.](media/qerguide-image-addmultiselectfilter.png)

Después, haga clic en **Buscar** (un icono de lupa junto al nuevo filtro). Verá un campo de texto y una serie de opciones, como **Seleccionar todo** e **Invertir**. Escriba un valor y haga clic en **Buscar** junto a ese campo para buscar. Como alternativa, deje el campo de texto vacío y haga clic en **Buscar** para ver hasta las primeras 100 opciones.

```powershell
/filter/[AllStreams].[Second Tenant Id]\|[YOUR TENANT ID HERE]
```

Ejemplo:

![Captura de pantalla en la que se agrega un filtro de consulta.](media/qerguide-image-addfilter.png)

### <a name="dashboard-level-filters"></a>Filtros de nivel de panel

Algunos informes del CQD tienen filtros de nivel de panel agregados, lo que facilita filtrar por parámetros comunes. Estos filtros aparecen fuera de las pestañas de informe normales y directamente debajo del filtro Producto, y se aplican a todos los filtros del panel.

![Captura de pantalla de un filtro de panel.](media/qerguide-image-dashboardfilters.png)

```powershell
/filter/[AllStreams].[Is Teams]|[TRUE | FALSE]
```

### <a name="url-filters"></a>Filtros de dirección URL

El CQD admite la adición de filtros a la dirección URL. Esto facilita compartir o marcar una consulta del CQD. Puede definir parámetros en la dirección URL, como Trending Month, id. de espacio empresarial o idioma. También puede agregar filtros de nivel de producto o panel a la dirección URL.
Excluir los datos federados de los informes del CQD es útil cuando se corrigen edificios administrados o redes en las que los puntos de conexión federados pueden influir en los informes.

Para agregar un filtro, anexe lo siguiente al final de la dirección URL:

```console
/filter/[AllStreams].[Second Tenant Id]\|[YOUR TENANT ID HERE]
```

Ejemplo:

`https://cqd.teams.microsoft.com/cqd/#/1234567/2018-08/filter/[AllStreams].[Second Tenant Id]|[TENANTID]`

Para agregar un filtro de nivel de panel a una dirección URL, ese filtro debe existir en el CQD como filtro de nivel de producto o de panel. Agregue estos filtros a la dirección URL después del mes de tendencia y antes de los parámetros de la dirección URL:

`filter/DATA_MODEL_NAME|VALUE`

Por ejemplo, para aplicar un valor de filtro de producto de Microsoft Teams, agregue lo siguiente:

`filter/[AllStreams].[Is%20Teams]|[True]`

La dirección URL completa tendría un aspecto similar a este:

`https://cqd.teams.microsoft.com/spd/#/Dashboard/2624085/2018-9/filter/[AllStreams].[Is%20Teams]|[True]`

Para aplicar filtros de dirección URL con valores de selección múltiple, separe cada valor con un carácter de canalización ( | ). Por ejemplo:

`filter/[AllStreams].[Media%20Type]|[Video]|[Audio]|[VBSS]`

Si especifica un nombre o valor no válido, no se aplicará el filtro de dirección URL.

Puede usar un filtro de dirección URL para filtrar cada informe para una dimensión específica. Los filtros de dirección URL más comunes se usan para filtrar los informes para excluir la telemetría de participantes federados o centrarse solo en Teams o Skype Empresarial Online. Excluir los datos federados de los informes del CQD es útil cuando se corrigen edificios administrados o redes en las que los puntos de conexión federados pueden influir en los informes.

|Filtro|Descripción|Ejemplo de filtro de consulta del CQD|
|---|---|---|
|No hay valores en blanco|Algunos filtros no tienen la opción de filtrar por valores en blanco. Para filtrar los valores en blanco manualmente, use la expresión en blanco y establezca el filtro como Igual o No es igual a, según sus necesidades.|Second Building Name \<\> \^\\s\*\$|
|Excluir subredes comunes|Sin un archivo de compilación válido para separar las redes administradas de las no administradas, las redes domésticas se incluirán en los informes. Estas subredes domésticas están fuera del ámbito del control de TI y se pueden excluir rápidamente de un informe. Las subredes comunes, como se define en este artículo, son 10.0.0.0, 192.168.1.0 y 192.168.0.0.|Second Subnet \<\> 10.0.0.0 \|192.168.0.0 \|192.168.1.0|
|Solo ver en el interior|Se usa para filtrar un informe para administrar (dentro) o no administrado (fuera). La plantilla administrada del CQD ya está preconfigurada con estos filtros.|Second Inside Corp = Inside|

#### <a name="how-to-find-your-tenant-id"></a>Cómo buscar el id. de inquilino

El id. de espacio empresarial en el CQD corresponde al id. de directorio de Azure. Si no conoce su Id. de directorio, puede encontrarlo en la Azure Portal:

1. Inicia sesión en microsoft Azure Portal:<https://portal.azure.com>

2. Seleccione **Azure Active Directory**.

3. En **Administrar**, selecciona **Propiedades**. El id. de espacio empresarial se encuentra en el cuadro **Id. de directorio** .

También puede encontrar su id. de inquilino mediante PowerShell:

```powershell
Login-AzureRmAccount
```

## <a name="comparing-teams-and-skype-for-business-cqd-data"></a>Comparación de datos de Teams y Skype Empresarial CQD

Al revisar los datos, es posible que vea diferencias en los datos entre Teams y Skype Empresarial. Algunas razones:

- Diferencias en los mecanismos para garantizar el rendimiento y la fiabilidad:
  - Teams tiene una conexión automática y una itinerancia rápida. Skype Empresarial no.
  - Teams tiene administración dinámica de ancho de banda. Skype Empresarial no.
- Diferencias en los [intervalos de direcciones IP](Office-365-URLs-IP-address-ranges.md) entre Teams y Skype Empresarial. Los intervalos IP de Teams son más recientes, lo que podría causar problemas de conectividad en el firewall.

## <a name="related-topics"></a>Temas relacionados

[Mejorar y supervisar la calidad de las llamadas para Teams](monitor-call-quality-qos.md)

[¿Qué es el CQD?](CQD-what-is-call-quality-dashboard.md)

[Configurar el panel de calidad de llamadas (CQD)](turning-on-and-using-call-quality-dashboard.md)

[Cargar datos de inquilinos y compilación](CQD-upload-tenant-building-data.md)

[Usar el CQD para administrar la calidad de llamadas y reuniones](quality-of-experience-review-guide.md)

[Dimensiones y medidas disponibles en el CQD](dimensions-and-measures-available-in-call-quality-dashboard.md)

[Clasificación de transmisiones en el CQD](stream-classification-in-call-quality-dashboard.md)

[Usar Power BI para analizar datos del CQD](CQD-Power-BI-query-templates.md)
