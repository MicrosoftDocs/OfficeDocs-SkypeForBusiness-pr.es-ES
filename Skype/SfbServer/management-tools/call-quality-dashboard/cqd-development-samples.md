---
title: Ejemplos de desarrollo de CQD
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/18/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 8ca9bf7a-2d6f-48d5-a821-531009726525
description: 'Resumen: revise un tutorial y muestras de desarrollo para el Panel de calidad de la llamada. El panel de calidad de la llamada es una herramienta Skype Empresarial Server 2015.'
ms.openlocfilehash: 6bd6031e1d7fc94ed463c53efb068fd1e2e51378
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/04/2018
ms.locfileid: "25375326"
---
# <a name="cqd-development-samples"></a>Ejemplos de desarrollo de CQD

**Resumen:** revise un tutorial y muestras de desarrollo para el Panel de calidad de la llamada. El panel de calidad de la llamada es una herramienta Skype Empresarial Server 2015.

En este artículo se proporcionan un tutorial y ejemplos sobre el desarrollo del panel de calidad de llamada (CQD).

## <a name="call-quality-dashboard-cqd-development-samples"></a>Ejemplos de desarrollo del panel de calidad de llamadas (CQD)

Tutorial: crear presentaciones de informes personalizadas con el servicio de datos y los API del servicio de repositorio del CQD.

### <a name="introduction-to-cqd"></a>Introducción al CQD

El CQD ofrece acceso rápido y fácil a la información agregada de calidad de la llamada para las implementaciones de Skype Empresarial Server locales. El CQD consta de tres componentes: la base de datos de QoE, el cubo y el portal. El portal es el nivel de presentación principal y se puede dividir en los siguientes tres componentes:

1. Servicio de datos, que está accesible para los usuarios autenticados a través de la [API de datos para panel de calidad de llamadas (CQD) en Skype para Business Server 2015](data-api.md).

2. Servicio de repositorio, que está accesible para los usuarios autenticados a través de la [API de repositorio de panel para calidad de llamadas (CQD) en Skype para Business Server 2015](repository-api.md).

3. Portal web, que es la interfaz basada en HTML5 que los usuarios del CQD ven y con la que interactúan. Es accesible para los usuarios autenticados.

Los informes que se muestra en el portal web se agrupan en "conjuntos de informe". La ilustración muestra un conjunto de informes con dos informes. Cada informe en el siguiente panel muestra los resultados de la consulta del número de llamadas buenas, llamadas deficientes y el porcentaje de llamadas deficientes durante varios meses, con varios filtros aplicados. 

![Informe de muestra de CQD](../../media/9e0723f7-f850-4d11-9ecd-7e8e013a8bed.png)

El CQD se crea según la Metodología de calidad de llamadas (CQM), de modo que el conjunto predeterminado de informes se diseña para alinearse con el flujo de investigación introducido por el CQM. Los usuarios también tienen la flexibilidad necesaria para editar o crear informes personalizados para satisfacer sus necesidades. Pero, ya que hay varias formas para visualizar los datos, la visualización proporcionada por el CQD puede no satisfacer por completo las necesidades de cada usuario. En estas situaciones, un usuario puede sacar provecho de los API de datos y de repositorio para crear páginas de informes personalizadas. En este tutorial se verán varios ejemplos.

### <a name="how-the-dashboard-consumes-the-data-service"></a>Cómo consume el panel el servicio de datos

Al navegar a la página principal de CQD (por ejemplo, http://localhost/cqd), Establece el informe y los informes correspondientes para un usuario autenticado y autorizado se recuperan desde el servicio del repositorio. Se creará una dirección URL completa desde el identificador de conjunto de informes y el mes de año (identificador de conjunto de informes es el número entero después de la sección '/ #/' en la dirección URL y, de forma predeterminada, el mes de año actual se anexa al final del identificador de conjunto de informes de después de la barra diagonal). Las definiciones del informe se almacenan en formato JSON y al recuperarlas desde el servicio de repositorios, se usarán como entrada para el servicio de datos. El servicio de datos genera consultas de expresiones multidimensionales (MDX) basadas en la entrada y, luego, ejecuta estas consultas de MDX contra el cubo para recuperar los datos para cada informe. 

### <a name="building-customized-reports"></a>Crear informes personalizados

El CQD ya tiene mucha flexibilidad para personalizar informes, pero podría haber situaciones en las que los usuarios deseen agregar los datos en varios informes creados en el CQD. Por ejemplo, es posible que necesite crear un informe que muestre el porcentaje de llamadas deficientes de todas las combinaciones posibles de llamadas por cable en una tabla (un resultado como la ilustración):

![Tabla de CQD](../../media/ef19d535-5da6-44a9-91f6-1ed3f30b96f1.png)

Al usar el portal proporcionado por el CQD, el usuario tendría que ir a varios informes para extraer y registrar el % de llamadas deficientes de cada uno, que puede ser difícil si hay que recopilar muchos puntos de datos. Los API de datos ofrecen a los usuarios una forma programática para llevar a cabo esta tarea, al recuperar los datos del servicio de datos (por ejemplo, por medio de las llamadas AJAX). 

 **Ejemplo 1: ejemplo de informe simple**

Veremos un ejemplo sencillo primero. Si desea mostrar el recuento de secuencias de buen audio y de mal audio de febrero de 2015 en una página web como la de la ilustración:

![Informe de ejemplo de CQD](../../media/f0e4e61f-1fa5-4d69-b192-f19e9612bf1c.png)

Lo que necesitamos es enviar una llamada al servicio de datos con los parámetros adecuados y mostrar los resultados de la consulta en una tabla HTML. A continuación se muestra un ejemplo del código JavaScript:

```        
$($.fn.freeFormReport = function (queries, urlApi, presentation) {
            var query = {
                Dimensions: [{ DataModelName: '[StartDate].[Month]' }],
                Filters: [{
                    DataModelName: '[StartDate].[Month]',
                    Value: '[2015-02-01T00:00:00]',
                    Operand: 0
                }],
                Measurements:
                    [{ DataModelName: '[Measures].[Audio Good Streams JPDR Count]' },
                     { DataModelName: '[Measures].[Audio Poor Streams JPDR Count]' },]
            };            

            $.ajax({
                url: 'http://localhost/QoEDataService/RunQuery',
                data: JSON.stringify(query),
                type: 'POST',
                async: true,
                contentType: 'application/json;charset=utf-8',
                success: function (data) {
                    //This is the jQuery syntax for document.GetElementById()
                    $('#AudioGoodStreamsJPDRCount').html(data.DataResult[0][1]);
                    $('#AudioPoorStreamsJPDRCount').html(data.DataResult[0][2]);
                }
                error: function (error) {
                    alert('Error getting data, check that the data service is running and that the URL is correct.');
           }
            });
        });
```

Este ejemplo se puede deconstruir en tres pasos:

1. Construir la consulta (en el ejemplo se define en la variable 'query'). La consulta se define como un objeto JSON, que incluye los siguientes datos:

   a. Cero o más dimensiones. Cada dimensión se indica con un DataModelName.

   b. Cero o más filtros. Cada filtro tiene:

   - DataModelName (la dimensión que tendrá el conjunto de filtros).

   - Valor (el valor que comparará el operando).

   - Operando (tipo de comparación, 0 significa "Igual a").

     c. Una o más medidas.

2. Enviar la consulta al servicio de datos por medio de llamadas AJAX. Hay que proporcionar los siguientes parámetros de solicitud:

   a. dirección URL (que necesita ser http://[NombreDelServidor]/QoEDataService/RunQuery).

   b. datos (Esto es la representación de cadena del objeto JSON definida en la variable 'query'). El servicio de datos devolverá los resultados de la consulta como un parámetro de la función de devolución de llamada correcta.

   c. Escriba (para QoEDataService, RunQuery sólo acepta ' POST' solicitudes).

   d. asincrónico (una marca que indica si la llamada AJAX tendría que ser sincrónica o asincrónica).

   e. contentType (debe ser "application/json").

   f. correcto (función de devolución de llamadas para cuando la llamada AJAX finaliza correctamente).

   g. error (función de control de errores para cuando la llamada AJAX produce un error).

3. Colocar datos en elementos div en el código HTML (en el ejemplo en el código, este paso se realiza a través de la llamada de función anónima una vez que la solicitud de AJAX se ha completado correctamente).

Enmarcar el código JavaScript en una página HTML y la página mostrará un informe como el que se muestra en la ilustración. El HTML completo es el siguiente:

```
<!DOCTYPE html>
<html xmlns="http://www.w3.org/1999/xhtml">
<head>
</head>
<body>
    <script src="OpenSourceSoftware/Scripts/jquery-2.1.1.js"></script>

    <script>
        $($.fn.freeFormReport = function (queries, urlApi, presentation) {

            var query = {
                Dimensions: [{ DataModelName: '[StartDate].[Month]' }],
                Filters: [{
                    DataModelName: '[StartDate].[Month]',
                    Value: '[2015-02-01T00:00:00]',
                    Operand: 0
                }],
                Measurements:
                    [{ DataModelName: '[Measures].[Audio Good Streams JPDR Count]' },
                     { DataModelName: '[Measures].[Audio Poor Streams JPDR Count]' },]
            };            

            $.ajax({
                url: 'http://localhost/QoEDataService/RunQuery',
                data: JSON.stringify(query),
                type: 'POST',
                async: true,
                contentType: 'application/json;charset=utf-8',
                success: function (data) {
                    //This is the jQuery syntax for document.GetElementById()
                    $('#AudioGoodStreamsJPDRCount').html(data.DataResult[0][1]);
                    $('#AudioPoorStreamsJPDRCount').html(data.DataResult[0][2]);
                }
                error: function (error) {
                    alert('Error getting data, check that the data service is running and that the URL is correct.');
           }

            });
        });
    </script>
    <table border="1">
        <tr>
            <td></td>
            <td><div>Audio Good Streams JPDR Count</div></td>
            <td><div>Audio Poor Streams JPDR Count</div></td>
        </tr>
        <tr>
            <td>February</td>
            <td><div id="AudioGoodStreamsJPDRCount"></div></td>
            <td><div id="AudioPoorStreamsJPDRCount"></div></td>
        </tr>
    </table>
</body>
</html>
```

Hasta el momento, el informe es todavía muy simple. El usuario puede agregar más medidas, dimensiones, o filtros para personalizar el informe. Por ejemplo, si desea mostrar el porcentaje de llamadas deficientes de AppSharing, hay que agregar una nueva medida relacionada con AppSharing. Si desea mostrar todas las llamadas TCP frente a las llamadas UDP, tendría que agregar una nueva dimensión relacionada con el tipo de transporte. Si desea mostrar el número de llamadas deficientes dentro de un edificio determinado, tendría que agregar un nuevo filtro para seleccionar las llamadas a y desde ese edificio.

 **Ejemplo 2: ejemplo de definición de informe**

Podría ser difícil averiguar cómo escribir la lista completa de medidas/dimensiones/filtros y sus valores correspondientes al construir una consulta. En este caso, puede ir al Portal, crear un informe con el editor de informes y ver la cadena JSON de la definición de informe y, luego, copiar la definición en un informe personalizado. 

En este ejemplo, vamos a crear una página web como la que se muestra en la ilustración en la que el usuario puede especificar el id. de cualquier conjunto de informes existente (o del informe) y mostrar la definición del conjunto de informes o del informe en la página web. Luego, el usuario puede conectar la cadena JSON de cada informe a un código similar al que se muestra en el Ejemplo 1 y construir cualquier informe personalizado que desee el usuario. 

![Ejemplo de CQD](../../media/01c45c23-c4d2-47b8-819f-0888cf71260f.png)

Para crear la herramienta del visor de definición de informe, es necesario enviar llamadas al servicio de repositorio para recuperar las representaciones de cadena JSON de las definiciones de cada conjunto de informes que queremos. El API de repositorio devolverá definiciones del conjunto de informes en función de un id. de conjunto de informes determinado. 

Un ejemplo rápido es el siguiente, el código contiene un bloque que es un ejemplo sencillo para enviar una consulta al servicio de repositorio para obtener el contenido de un elemento del repositorio basado en su identificador. Y la siguiente parte de código (método processReportSetData) envía las llamadas AJAX para obtener la definición de cada informe dentro de ese conjunto de informes. Debido a que el id. en el portal web CQD es el id. de un conjunto de informes, la llamada AJAX devolverá un elemento del conjunto de informes. Obtener más detalles acerca de la API de repositorio y en concreto, GetItems, pueden encontrarse en los [Elementos de obtener](get-items.md). 

```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="utf-8" />
    <meta http-equiv='cache-control' content='no-cache'>
    <meta http-equiv='expires' content='0'>
    <meta http-equiv='pragma' content='no-cache'>
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta http-equiv="x-content-type-options" content="nosniff">
    <title>CQD Report definition viewer</title>
</head>
<body>    
    <div style="font-size:32pt">CQD Report definition viewer</div>
        <p>ReportSet Id: <input id="reportSetId" /></p>
        <button onclick='loadReportSet()'>Load</button>
        <div id="Report"></div>
    <!-- Third party Libraries -->
    <script src="OpenSourceSoftware/Scripts/jquery-2.1.1.js"></script>

    <script>
        var urlRepositoryApi = 'http://localhost/QoERepositoryService/repository/item/';

        var loadReportSet = function ()
        {
            var reportSetId = document.getElementById('reportSetId').value;

            $.ajax({
                url: urlRepositoryApi + reportSetId,
                data: '',
                type: 'GET',
                async: false,
                contentType: 'application/json;charset=utf-8',
                success: function (data) {
                    var reportSetDiv = document.getElementById('Report');
                    reportSetDiv.innerHTML = '';
                    processReportSetData(reportSetDiv, data);
                },
                error: function (error) {
                    alert('Error getting Report, check that the qoe data service is running and url is correct.');
                }
            });
        };

        var processReportSetData = function (divReportSet, reportSetDef) {
             //show the report set definition like Title, Description, etc
            showReportSetDefinition(divReportSet, reportSetDef);

            //for each Report in the Reportset, get the Report definition from the Repository Service
            for (var i = 0; i < reportSetDef.subItemIds.length; i++)
            {
                //the reportId is in the subItemIds array.  This is not shown in the CQD UI at all
                var reportId = reportSetDef.subItemIds[i];

                var divReport = document.createElement('div');
                divReport.style.margin = '12px';                
                divReportSet.appendChild(divReport);

                //retrieve the report definition with the reportId
                $.ajax({
                    url: urlRepositoryApi + reportId,
                    data: '',
                    type: 'GET',
                    async: false,
                    contentType: 'application/json;charset=utf-8',
                    success: function (reportData) {
                        processReportData(divReport, reportData, reportId);
                    },
                    error: function (error) {
                        alert('Error getting Report ' + reportId.toString() + ', check that the qoe data service is running and url is correct.');
                    }
                });
            }
        };

        //helper function to render the ReportSet definition
        var showReportSetDefinition = function (divReportSet, reportSetDef) {
            var div = document.createElement('div');
            ReportSetDefinition = reportSetDef.content;
            txt = document.createTextNode(ReportSetDefinition);
            div.style.margin = '12px';
            div.appendChild(txt);
            divReportSet.appendChild(div);
        };

        //show the report definition
        var processReportData = function (divReport, reportData, itemId) {
            if (divReport != undefined &amp;&amp; reportData.content != undefined) {
                var Report = JSON.parse(reportData.content);

                var divReportId = document.createElement('div');
                var subItemId = reportData.subItemIds.length > 0 ? reportData.subItemIds[0].toString() : 'none';
                divReportId.innerHTML = 'ItemId: ' + itemId.toString() + ' (' + Report.Title + ') [subItemId:' + subItemId + ']';
                divReport.appendChild(divReportId);

                var divReportDef = document.createElement('div');
                txt = document.createTextNode(JSON.stringify(Report));
                divReportDef.style.margin = '12px';
                divReportDef.appendChild(txt);                            
                divReport.appendChild(divReportDef);
            }
        };
    </script>
</body>
</html>
```

Este ejemplo dará como resultado una página web como la de la ilustración (sin la definición de informe tras la visita inicial). Obtenga el identificador de conjunto de informe desde el portal CQD (es una vez / #/ iniciar sesión en el portal CQD dirección URL (por ejemplo, en la primera ilustración el informe de identificador de conjunto es 3024) y poner este identificador de conjunto de informe en la sección de entrada de esta página web. Presione el botón "cargar" y vea la definición completa del conjunto de informe (medidas, dimensiones, las listas de filtros).

En resumen, para obtener de forma rápida la definición completa de un informe o conjunto de informes. Los pasos son:

1. Vaya al Portal y usar el editor de consultas para personalizar un informe (haga clic en "Editar" situado sobre un informe para editar, agregar, quitar las medidas, dimensiones o filtros y, a continuación, guarda el informe).

2. Obtenga el identificador de conjunto de informe desde la dirección URL (el número entero después / #/ iniciar sesión en la dirección URL).

3. Inicie esta página web de definición de informes creada en el Ejemplo 2, escriba el id. de conjunto de informes y recupere la definición completa de un conjunto de informes (para usar en las llamadas de API de datos).

   **Ejemplo 3: ejemplo de cuadro de mandos**

Es hora de una tarea más complicada. ¿Qué ocurre si desea crear una página web como la de la ilustración? Hay que actualizar el Ejemplo 1, (con la ayuda de la página web generada en el Ejemplo 2 para recuperar la definición completa de cualquier informe) de modo que podamos controlar más cantidad de datos.

En este caso, hay que actualizar la lista de medidas y dimensiones. La forma de averiguar cómo agregar/editar una medida o una dimensión es seguir las instrucciones en el Ejemplo 2 y recuperar la definición completa del informe, incluidas las listas de medidas y dimensiones completas. Conecte la definición completa del informe en el código de ejemplo. 

Estos son los pasos detallados para ir a la página del cuadro de mandos en la ilustración del ejemplo proporcionado en el Ejemplo 1:

1. Actualice las medidas en la variable 'query' en `[Measures].[Audio Good Streams JPDR Count]` y `[Measures].[Audio Poor Streams JPDR Count]` a `[Measures].[AudioPoorJPDRPercentage]`. 

2. Actualice los filtros. Los datos JSON para filtros en el ejemplo 1 tienen un filtro, que se establece en la dimensión `[StartDate].[Month]`. Puesto que los filtros son una matriz JSON, se pueden agregar dimensiones adicionales a la lista de filtros. Por ejemplo, para obtener al cliente de servidor dentro de llamadas por cable para la "currentMonth", deberíamos tener los siguientes filtros:

   ```
   Filters: [
     { DataModelName: '[StartDate].[Month]', Value: currentMonth, Operand: 0 },
    {
        "DataModelName": "[Scenarios].[ScenarioPair]",
         "Caption": " Server-Inside-wired,Client-Inside-wired",
         "Value": "[1]&amp;[0]&amp;[1]&amp;[1]&amp;[Wired]&amp;[Wired]",
         "Operand": 0,
         "UnionGroup": ""
     },

     { DataModelName: '[StreamType].[StreamType]', Caption: "Valid", Value: "[False]", Operand: 0, UnionGroup: "" }
   ],
   ```

   Aquí tiene la dimensión `[Scenarios].[ScenarioPair]` está establecida sea igual a `[1]&amp;[0]&amp;[1]&amp;[1]&amp;[Wired]&amp;[Wired]`. El `[Scenario.][ScenarioPair]` es una dimensión especial creada para simplificar el proceso de creación de informes. Tiene seis valores que se corresponden con `[FirstIsServer], [SecondIsServer], [FirstInside], [SecondIsServer], [FirstConnectionType], [SecondConnectionType]`. Por lo tanto, en lugar de usar una combinación de 6 filtros para definir un escenario, solo tiene que usar 1 filtro. En nuestro ejemplo, el valor `[1]&amp;[0]&amp;[1]&amp;[1]&amp;[Wired]&amp;[Wired]` se traduce en el escenario donde: en primer lugar es servidor, en segundo lugar no es servidor, en primer lugar se encuentra dentro de, en segundo lugar está dentro, primer tipo de conexión es con cable y segundo tipo de conexión es cableada, que es la definición exacta de " Server-Client-Inside con cable".

3. Cree un conjunto de filtros para cada escenario. Cada fila en el cuadro de mandos, en la ilustración, representa un escenario diferente, que será un filtro diferente (mientras que las dimensiones y medidas son las mismas). 

4. Analice los resultados de las llamadas AJAX y colóquelos en la posición correcta de la tabla. Puesto que se trata principalmente de manipulación del HTML y del JavaScript, no entraremos en detalles. En su lugar, se proporciona el código en el Apéndice A.

    > [!NOTE]
    >  Si está habilitado el uso compartido de recursos de origen cruzado (CORS), los usuarios pueden producirse errores como "encabezado 'Access-Control-permitir-origen' no está presente en el recurso solicitado. Origen 'null', por tanto, no se permite el acceso". Para resolver el problema, coloque el archivo HTML en la carpeta en la que está instalado el Portal (de forma predeterminada, necesita ser `%SystemDrive%\Program Files\Skype for Business 2015 CQD\CQD)`. A continuación, obtener acceso el código html a través de cualquier explorador con la dirección URL `http://<servername>/cqd/<html_file_name>`. (Es la dirección URL predeterminada para el panel CQD local de `http://<servername>/cqd.`) 

### <a name="appendix-a"></a>Apéndice A

Código HTML para el Ejemplo 3 (ejemplo de cuadro de mandos):

```
<!DOCTYPE html>
<html xmlns="http://www.w3.org/1999/xhtml">
<head>
    <meta charset="utf-8" />
    <meta http-equiv='cache-control' content='no-cache'>
    <meta http-equiv='expires' content='0'>
    <meta http-equiv='pragma' content='no-cache'>
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <title>Scoreboard Sample</title>

    <style>
        .row {
            margin-right: -15px;
            margin-left: -15px;
            display: table-row;
        }
        .col-md-3 {
            width: 25%;
            display: table-cell;
        }
        .col-md-2 {
            width: 16.66666667%;
            display: table-cell;
        }
        .col-md-1 {
            width: 8.33333333%;
            display: table-cell;
        }

    </style>
</head>
<body>    

    <!-- Third party Libraries -->
    <script src="OpenSourceSoftware/Scripts/jquery-2.1.1.js"></script>

    <table id="ScoreCardTable" style="margin:100px">
        <tr>
            <td width="250px" style="text-align: center; font-size: 24px; font-family: 'Segoe UI'; font-weight: lighter; color: white; background-color: #505050">
                <div style="margin:10px">Scoreboard Sample</div>
            </td>
            <td width="1200px">
                <div style="margin:10px;background-color:#D9D9D9" >
                    <div class="row" id="Header" style="font-size:24px;font-family:'Segoe UI';font-weight:lighter;color:white;background-color:#505050">
                        <div class="col-md-3">Poor Call %</div>
                        <div class="col-md-1">Month1</div>
                        <div class="col-md-1">Month2</div>
                        <div class="col-md-1">Month3</div>
                        <div class="col-md-1">Month4</div>
                        <div class="col-md-1">Month5</div>
                        <div class="col-md-1">Month6</div>
                    </div>                    
                    <div class="row"><div class="col-md-3" style="font-weight:bold">Wired</div></div>
                    <div class="row" id="SS"><div class="col-md-3">Server-Server</div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div></div>
                    <div class="row" id="SWI"><div class="col-md-3">Server-Client (inside)</div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div></div>
                    <div class="row" id="SWO"><div class="col-md-3">Server-Client (outside)</div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div></div>
                    <div class="row" id="WWI"><div class="col-md-3">Client-Client (inside)</div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div></div>
                    <div class="row" id="WIWO"><div class="col-md-3">Client-Client (outside)</div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div></div>
                    <div class="row"><div class="col-md-3" style="font-weight:bold">Wireless</div></div>
                    <div class="row" id="SWFI"><div class="col-md-3">Server-Client (inside)</div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div></div>
                    <div class="row" id="SWFO"><div class="col-md-3">Server-Client (outside)</div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div></div>
                    <div class="row" id="WFIWFI"><div class="col-md-3">Client-Client (inside)</div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div></div>
                    <div class="row" id="WFOWFO"><div class="col-md-3">Client-Client (outside)</div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div></div>
                    <div class="row"><div class="col-md-3" style="font-weight:bold">Mobile/Broadband</div></div>
                    <div class="row" id="SMP"><div class="col-md-3">Server-MobilePhone</div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div></div>
                    <div class="row" id="SMBB"><div class="col-md-3">Server-MobileBroadBand</div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div></div>
                    <div class="row"><div class="col-md-3" style="font-weight:bold">Lync Web App</div></div>
                    <div class="row" id="SLWA"><div class="col-md-3">Server-Client (inside &amp; outside)</div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div></div>
                </div>
            </td>
        </tr>
        <tr>
            <td><br /></td>
        </tr>
    </table>

    <script>

        $(function () {
            var month_names_short = ['NAM', 'Jan', 'Feb', 'Mar', 'Apr', 'May', 'Jun', 'Jul', 'Aug', 'Sep', 'Oct', 'Nov', 'Dec'];
            var currentMonth = '2015-3';

            //update the header with the month names
            var row = document.getElementById('Header');
            var numMonthsToShow = 6;
            for (var m = numMonthsToShow-1; m >= 0; m--) {
                var dateSplit = currentMonth.split('-');
                var monthInt = parseInt(dateSplit[1]);
                var yearInt = parseInt(dateSplit[0]);
                monthInt = monthInt - m;
                if (monthInt < 1)
                {
                    monthInt += 12;
                    yearInt--;
                }
                row.children[numMonthsToShow-m].innerHTML = month_names_short[monthInt];
            }

            var queries = [
            {
                Label: "Server-Server",
                ID: "SS",
                Query:
                {
                  Dimensions: [{ DataModelName: '[StartDate].[Month]'}],
                  Filters: [
                      {
                          "DataModelName": "[Scenarios].[ScenarioPair]",
                          "Caption": " Server-Inside-wired,Server-Inside-wired",
                          "Value": "[1]&amp;[1]&amp;[1]&amp;[1]&amp;[Wired]&amp;[Wired]",
                          "Operand": 0,
                          "UnionGroup": ""
                      },
                      { DataModelName: '[StartDate].[Month]', Value: currentMonth, Operand: 0 },
                      { DataModelName: '[StreamType].[StreamType]', Caption: "Valid", Value: "[False]", Operand: 0, UnionGroup: ""}
                  ],
                  Measurements: [{ DataModelName: '[Measures].[AudioPoorJPDRPercentage]'}],
                  Trend: { EnableTrend: true, SpanCount: numMonthsToShow, TrendDate: currentMonth, Type: 0 }
                 }
            },
            {
                Label: "Server-Client (inside)",
                ID: "SWI",
                Query:
                {
                  Dimensions: [{ DataModelName: '[StartDate].[Month]' }],
                  Filters: [
                      {
                          "DataModelName": "[Scenarios].[ScenarioPair]",
                          "Caption": " Server-Inside-wired,Client-Inside-wired",
                          "Value": "[1]&amp;[0]&amp;[1]&amp;[1]&amp;[Wired]&amp;[Wired]",
                          "Operand": 0,
                          "UnionGroup": ""
                      },
                      { DataModelName: '[StartDate].[Month]', Value: currentMonth, Operand: 0 },
                      { DataModelName: '[StreamType].[StreamType]', Caption: "Valid", Value: "[False]", Operand: 0, UnionGroup: "" }
                  ],
                  Measurements: [{ DataModelName: '[Measures].[AudioPoorJPDRPercentage]' }],
                  Trend: { EnableTrend: true, SpanCount: numMonthsToShow, TrendDate: currentMonth, Type: 0 }
                }
            },
            {
                Label: "Server-Client (outside)",
                ID: "SWO",
                Query:
                {
                  Dimensions: [{ DataModelName: '[StartDate].[Month]' }],
                  Filters: [
                      {
                          "DataModelName": "[Scenarios].[ScenarioPair]",
                          "Caption": " Server-Inside-wired,Client-Outside-wired",
                          "Value": "[1]&amp;[0]&amp;[1]&amp;[0]&amp;[Wired]&amp;[Wired]",
                          "Operand": 0,
                          "UnionGroup": ""
                      },
                      { DataModelName: '[StartDate].[Month]', Value: currentMonth, Operand: 0 },
                      { DataModelName: '[StreamType].[StreamType]', Caption: "Valid", Value: "[False]", Operand: 0, UnionGroup: "" }
                  ],
                  Measurements: [{ DataModelName: '[Measures].[AudioPoorJPDRPercentage]' }],
                  Trend: { EnableTrend: true, SpanCount: numMonthsToShow, TrendDate: currentMonth, Type: 0 }
                 }
            },
            {
                Label: "Client-Client (inside)",
                ID: "WWI",
                Query:
                {
                    Dimensions: [{ DataModelName: '[StartDate].[Month]' }],
                    Filters: [
                        {
                            "DataModelName": "[Scenarios].[ScenarioPair]",
                            "Caption": " Client-Inside-wired,Client-Inside-wired",
                            "Value": "[0]&amp;[0]&amp;[1]&amp;[1]&amp;[Wired]&amp;[Wired]",
                            "Operand": 0,
                            "UnionGroup": ""
                        },
                        { DataModelName: '[StartDate].[Month]', Value: currentMonth, Operand: 0 },
                        { DataModelName: '[StreamType].[StreamType]', Caption: "Valid", Value: "[False]", Operand: 0, UnionGroup: "" }
                    ],
                    Measurements: [{ DataModelName: '[Measures].[AudioPoorJPDRPercentage]' }],
                    Trend: { EnableTrend: true, SpanCount: numMonthsToShow, TrendDate: currentMonth, Type: 0 }
                }
            }
            ,
            {
                Label: "Client-Client (outside)",
                ID: "WIWO",
                Query:
                {
                    Dimensions: [{ DataModelName: '[StartDate].[Month]' }],
                    Filters: [
                        {
                          "DataModelName": "[Scenarios].[ScenarioPair]",
                          "Caption": "Client-Outside-Wired,Client-Outside-Wired",
                          "Value": "[0]&amp;[0]&amp;[0]&amp;[0]&amp;[Wired]&amp;[Wired]",
                          "Operand": 0,
                          "UnionGroup": ""
                        },
                        { DataModelName: '[StartDate].[Month]', Value: currentMonth, Operand: 0 },
                        { DataModelName: '[StreamType].[StreamType]', Caption: "Valid", Value: "[False]", Operand: 0, UnionGroup: "" }
                    ],
                    Measurements: [{ DataModelName: '[Measures].[AudioPoorJPDRPercentage]' }],
                    Trend: { EnableTrend: true, SpanCount: numMonthsToShow, TrendDate: currentMonth, Type: 0 }
                }
            },
            {
                Label: "Server-Client (inside)",
                ID: "SWFI",
                Query:
                {
                    Dimensions: [{ DataModelName: '[StartDate].[Month]' }],
                    Filters: [
                        {
                            "DataModelName": "[Scenarios].[ScenarioPair]",
                            "Caption": " Server-Inside-wired,Client-Inside-wifi",
                            "Value": "[1]&amp;[0]&amp;[1]&amp;[1]&amp;[Wired]&amp;[Wifi]",
                            "Operand": 0,
                            "UnionGroup": ""
                        },
                        { DataModelName: '[StartDate].[Month]', Value: currentMonth, Operand: 0 },
                        { DataModelName: '[StreamType].[StreamType]', Caption: "Valid", Value: "[False]", Operand: 0, UnionGroup: "" }
                    ],
                    Measurements: [{ DataModelName: '[Measures].[AudioPoorJPDRPercentage]' }],
                    Trend: { EnableTrend: true, SpanCount: numMonthsToShow, TrendDate: currentMonth, Type: 0 }
                }
            },
            {
                Label: "Server-Client (outside)",
                ID: "SWFO",
                Query:
                {
                    Dimensions: [{ DataModelName: '[StartDate].[Month]' }],
                    Filters: [
                         {
                             "DataModelName": "[Scenarios].[ScenarioPair]",
                             "Caption": " Server-Inside-wired,Client-Outside-wifi",
                             "Value": "[1]&amp;[0]&amp;[1]&amp;[0]&amp;[Wired]&amp;[Wifi]",
                             "Operand": 0,
                             "UnionGroup": ""
                         },
                        { DataModelName: '[StartDate].[Month]', Value: currentMonth, Operand: 0 },
                        { DataModelName: '[StreamType].[StreamType]', Caption: "Valid", Value: "[False]", Operand: 0, UnionGroup: "" }
                    ],
                    Measurements: [{ DataModelName: '[Measures].[AudioPoorJPDRPercentage]' }],
                    Trend: { EnableTrend: true, SpanCount: numMonthsToShow, TrendDate: currentMonth, Type: 0 }
                }
            },
            {
                Label: "Client-Client (inside)",
                ID: "WFIWFI",
                Query:
                {
                    Dimensions: [{ DataModelName: '[StartDate].[Month]' }],
                    Filters: [
                        {
                            "DataModelName": "[Scenarios].[ScenarioPair]",
                            "Caption": " Client-Inside-Wifi,Client-Inside-Wifi",
                            "Value": "[0]&amp;[0]&amp;[1]&amp;[1]&amp;[Wifi]&amp;[Wifi]",
                            "Operand": 0,
                            "UnionGroup": ""
                        },
                        { DataModelName: '[StartDate].[Month]', Value: currentMonth, Operand: 0 },
                        { DataModelName: '[StreamType].[StreamType]', Caption: "Valid", Value: "[False]", Operand: 0, UnionGroup: "" }
                    ],
                    Measurements: [{ DataModelName: '[Measures].[AudioPoorJPDRPercentage]' }],
                    Trend: { EnableTrend: true, SpanCount: numMonthsToShow, TrendDate: currentMonth, Type: 0 }
                }
            },
            {
                Label: "Client-Client (outside)",
                ID: "WFOWFO",
                Query:
                {
                    Dimensions: [{ DataModelName: '[StartDate].[Month]' }],
                    Filters: [
                        {
                          "DataModelName": "[Scenarios].[ScenarioPair]",
                          "Caption": "Client-Outside-Wifi,Client-Outside-Wifi",
                          "Value": "[0]&amp;[0]&amp;[0]&amp;[0]&amp;[Wifi]&amp;[Wifi]",
                          "Operand": 0,
                          "UnionGroup": ""
                        },
                        { DataModelName: '[StartDate].[Month]', Value: currentMonth, Operand: 0 },
                        { DataModelName: '[StreamType].[StreamType]', Caption: "Valid", Value: "[False]", Operand: 0, UnionGroup: "" }
                    ],
                    Measurements: [{ DataModelName: '[Measures].[AudioPoorJPDRPercentage]' }],
                    Trend: { EnableTrend: true, SpanCount: numMonthsToShow, TrendDate: currentMonth, Type: 0 }
                }
            },
            {
                Label: "Server-MobilePhone",
                ID: "SMP",
                Query:
                {
                    Dimensions: [{ DataModelName: '[StartDate].[Month]' }],
                    Filters: [
                        {"DataModelName": "[First Is Server].[Agent]","Caption": "Server","Value": "[1]","Operand": 0,"UnionGroup": ""},
                        {"DataModelName": "[Second User Agent].[User Agent Type]","Caption": "AndroidLync | iPhoneLync | WPLync","Value": "[AndroidLync],[iPhoneLync],[WPLync]","Operand": 0,"UnionGroup": ""},
                        { DataModelName: '[StartDate].[Month]', Value: currentMonth, Operand: 0 },
                    ],
                    Measurements: [{ DataModelName: '[Measures].[AudioPoorJPDRPercentage]' }],
                    Trend: { EnableTrend: true, SpanCount: numMonthsToShow, TrendDate: currentMonth, Type: 0 }
                }
            },
            {
                Label: "Server-MobileBroadBand",
                ID: "SMBB",
                Query:
                {
                    Dimensions: [{ DataModelName: '[StartDate].[Month]' }],
                    Filters: [
                        {"DataModelName": "[Second Network Connection Type].[Network Connection Detail]","Caption": "MobileBB","Value": "[MobileBB]","Operand": 0,"UnionGroup": ""},
                        {"DataModelName": "[First Is Server].[Agent]","Caption": "Server","Value": "[1]","Operand": 0,"UnionGroup": ""},
                        {"DataModelName": "[Second Is Server].[Agent]","Caption": "Client ","Value": "[0]","Operand": 0,"UnionGroup": ""},
                        { DataModelName: '[StartDate].[Month]', Value: currentMonth, Operand: 0 }                       
                    ],
                    Measurements: [{ DataModelName: '[Measures].[AudioPoorJPDRPercentage]' }],
                    Trend: { EnableTrend: true, SpanCount: numMonthsToShow, TrendDate: currentMonth, Type: 0 }
                }
            },
            {
                Label: "Server-LWA",
                ID: "SLWA",
                Query:
                {
                    Dimensions: [{ DataModelName: '[StartDate].[Month]' }],
                    Filters: [
                        {"DataModelName": "[First Is Server].[Agent]","Caption": "Server","Value": "[1]","Operand": 0,"UnionGroup": ""},
                        {"DataModelName": "[Second User Agent].[User Agent Type]","Caption": "LWA","Value": "[LWA]","Operand": 0,"UnionGroup": ""},
                        { DataModelName: '[StartDate].[Month]', Value: currentMonth, Operand: 0 }                       
                    ],
                    Measurements: [{ DataModelName: '[Measures].[AudioPoorJPDRPercentage]' }],
                    Trend: { EnableTrend: true, SpanCount: numMonthsToShow, TrendDate: currentMonth, Type: 0 }
                }
            }

            ];

            //get the overall corpnet data
            for (var i = 0; i < queries.length; i++) {
                $.ajax({

                    url: 'http://localhost/QoEDataService/RunQuery',
                    data: JSON.stringify(queries[i].Query),
                    type: 'POST',
                    async: false,
                    withCredentials: true,
                    contentType: 'application/json;charset=utf-8',
                    success: function (data) {

                        //find the table row corresponding to the name of this query
                        var row = document.getElementById(queries[i].ID);

                        //update the values for each month
                        for (var m = 0; m < data.DataResult.length; m++)
                        {
                            row.children[m + 1].innerHTML = data.DataResult[m][1].toFixed(2).toString();
                        }

                    },
                    error: function (error) {
                        var row = document.getElementById(queries[i].ID);
                        row.children[1].innerHTML = 'error';
                    }
                });
            }
        });
    </script>
</body>
</html>
```