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
description: 'Resumen: Revisar un tutorial y desarrollo ejemplos para llamar al panel de calidad. Panel de calidad de la llamada es una herramienta de Skype para Business Server 2015.'
ms.openlocfilehash: 40e6defd85cc9e8dd86956a3539b51e1846b6da5
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="cqd-development-samples"></a><span data-ttu-id="446d8-104">Ejemplos de desarrollo de CQD</span><span class="sxs-lookup"><span data-stu-id="446d8-104">CQD Development Samples</span></span>
 
<span data-ttu-id="446d8-p102">**Resumen:** revise un tutorial y muestras de desarrollo para el Panel de calidad de la llamada. El panel de calidad de la llamada es una herramienta Skype Empresarial Server 2015.</span><span class="sxs-lookup"><span data-stu-id="446d8-p102">**Summary:** Review a tutorial and development samples for Call Quality Dashboard. Call Quality Dashboard is a tool for Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="446d8-107">En este artículo se proporcionan un tutorial y ejemplos sobre el desarrollo del panel de calidad de llamada (CQD).</span><span class="sxs-lookup"><span data-stu-id="446d8-107">This article provides a tutorial and samples on development for Call Quality Dashboard (CQD).</span></span>
  
## <a name="call-quality-dashboard-cqd-development-samples"></a><span data-ttu-id="446d8-108">Ejemplos de desarrollo del panel de calidad de llamadas (CQD)</span><span class="sxs-lookup"><span data-stu-id="446d8-108">Call Quality Dashboard (CQD) Development Samples</span></span>

<span data-ttu-id="446d8-109">Tutorial: crear presentaciones de informes personalizadas con el servicio de datos y los API del servicio de repositorio del CQD.</span><span class="sxs-lookup"><span data-stu-id="446d8-109">Tutorial: Building Customized Report Presentation using the CQD Data Service and Repository Service API's.</span></span>
  
### <a name="introduction-to-cqd"></a><span data-ttu-id="446d8-110">Introducción al CQD</span><span class="sxs-lookup"><span data-stu-id="446d8-110">Introduction to CQD</span></span>

<span data-ttu-id="446d8-111">El CQD ofrece acceso rápido y fácil a la información agregada de calidad de la llamada para las implementaciones de Skype Empresarial Server locales.</span><span class="sxs-lookup"><span data-stu-id="446d8-111">CQD offers quick and easy access to aggregated call quality information for on-premise Skype for Business Server deployments.</span></span> <span data-ttu-id="446d8-112">El CQD consta de tres componentes: la base de datos de QoE, el cubo y el portal.</span><span class="sxs-lookup"><span data-stu-id="446d8-112">CQD consists of three components: the QoE Archive database, the Cube, and the Portal.</span></span> <span data-ttu-id="446d8-113">El portal es el nivel de presentación principal y se puede dividir en los siguientes tres componentes:</span><span class="sxs-lookup"><span data-stu-id="446d8-113">The Portal is the main presentation layer and can be further divided into the following three components:</span></span>
  
1. <span data-ttu-id="446d8-114">Servicio de datos, que es accesible para los usuarios autenticados a través de la [API de datos para llamar a calidad Dashboard (CQD) en Skype para Business Server 2015](data-api.md).</span><span class="sxs-lookup"><span data-stu-id="446d8-114">Data Service, which is accessible for authenticated users through the [Data API for Call Quality Dashboard (CQD) in Skype for Business Server 2015](data-api.md).</span></span>
    
2. <span data-ttu-id="446d8-115">Servicio de repositorio, que es accesible para los usuarios autenticados a través de la [API de repositorio para llamar a calidad Dashboard (CQD) en Skype para Business Server 2015](repository-api.md).</span><span class="sxs-lookup"><span data-stu-id="446d8-115">Repository Service, which is accessible for authenticated users through the [Repository API for Call Quality Dashboard (CQD) in Skype for Business Server 2015](repository-api.md).</span></span>
    
3. <span data-ttu-id="446d8-p104">Portal web, que es la interfaz basada en HTML5 que los usuarios del CQD ven y con la que interactúan. Es accesible para los usuarios autenticados.</span><span class="sxs-lookup"><span data-stu-id="446d8-p104">Web portal, which is the HTML5 based interface that CQD users see and interact with. This is accessible for authenticated users.</span></span>
    
<span data-ttu-id="446d8-118">Los informes que se muestra en el portal web se agrupan en "conjuntos de informe".</span><span class="sxs-lookup"><span data-stu-id="446d8-118">The reports shown on the web portal are grouped into "report sets".</span></span> <span data-ttu-id="446d8-119">La ilustración muestra un conjunto de informes con dos informes.</span><span class="sxs-lookup"><span data-stu-id="446d8-119">The figure shows a report set with two reports.</span></span> <span data-ttu-id="446d8-120">Cada informe en el siguiente panel muestra los resultados de la consulta del número de llamadas buenas, llamadas deficientes y el porcentaje de llamadas deficientes durante varios meses, con varios filtros aplicados.</span><span class="sxs-lookup"><span data-stu-id="446d8-120">Each report in this dashboard below shows query results on number of good calls, poor calls and poor call percentage for several months, with various filters applied.</span></span> 
  
![Informe de muestra de CQD](../../media/9e0723f7-f850-4d11-9ecd-7e8e013a8bed.png)
  
<span data-ttu-id="446d8-p106">El CQD se crea según la Metodología de calidad de llamadas (CQM), de modo que el conjunto predeterminado de informes se diseña para alinearse con el flujo de investigación introducido por el CQM. Los usuarios también tienen la flexibilidad necesaria para editar o crear informes personalizados para satisfacer sus necesidades. Pero, ya que hay varias formas para visualizar los datos, la visualización proporcionada por el CQD puede no satisfacer por completo las necesidades de cada usuario. En estas situaciones, un usuario puede sacar provecho de los API de datos y de repositorio para crear páginas de informes personalizadas. En este tutorial se verán varios ejemplos.</span><span class="sxs-lookup"><span data-stu-id="446d8-p106">CQD is created following the Call Quality Methodology (CQM), so the default set of reports is designed to align with the investigation flow introduced by CQM. Users also have the flexibility to edit or create custom reports to meet their needs. However, since there are multiple ways to visualize the data, the visualization provided by CQD may not fully address the needs of every user. In such situations, a user can leverage the Data APIs and Repository APIs to create custom report pages. We will go through a series of examples in this tutorial.</span></span>
  
### <a name="how-the-dashboard-consumes-the-data-service"></a><span data-ttu-id="446d8-127">Cómo consume el panel el servicio de datos</span><span class="sxs-lookup"><span data-stu-id="446d8-127">How the dashboard consumes the data service</span></span>

<span data-ttu-id="446d8-128">Al navegar a la página de inicio CQD (por ejemplo, http://localhost/cqd), el informe y los informes correspondientes para un usuario autenticado y autorizado se recuperan desde el servicio de repositorio.</span><span class="sxs-lookup"><span data-stu-id="446d8-128">When navigating to the CQD homepage (e.g. http://localhost/cqd), the report set and corresponding reports for an authenticated and authorized user will be retrieved from the Repository Service.</span></span> <span data-ttu-id="446d8-129">Se construirá una dirección URL completa desde el identificador de conjunto de informes y el mes año (identificador de conjunto de informes es el número entero después de la sección '/ #/' en la dirección URL y, por defecto el mes año actual se anexa al final de la identificación del conjunto de informes después de la barra diagonal).</span><span class="sxs-lookup"><span data-stu-id="446d8-129">A full URL will be constructed from the report-set ID and the year-month (report-set ID is the integer number after '/#/' section in URL, and by default the current year-month is appended at the end of the report-set ID after the slash).</span></span> <span data-ttu-id="446d8-130">Las definiciones del informe se almacenan en formato JSON y al recuperarlas desde el servicio de repositorios, se usarán como entrada para el servicio de datos.</span><span class="sxs-lookup"><span data-stu-id="446d8-130">The report definitions are stored in JSON format and when retrieved from the Repository Service, will then be used as input to the Data Service.</span></span> <span data-ttu-id="446d8-131">El servicio de datos genera consultas de expresiones multidimensionales (MDX) basadas en la entrada y, luego, ejecuta estas consultas de MDX contra el cubo para recuperar los datos para cada informe.</span><span class="sxs-lookup"><span data-stu-id="446d8-131">The Data Service generates Multi-Dimension expressions (MDX) queries based on the input and then run these MDX queries against the Cube to retrieve data for each report.</span></span> 
  
### <a name="building-customized-reports"></a><span data-ttu-id="446d8-132">Crear informes personalizados</span><span class="sxs-lookup"><span data-stu-id="446d8-132">Building customized reports</span></span>

<span data-ttu-id="446d8-p108">El CQD ya tiene mucha flexibilidad para personalizar informes, pero podría haber situaciones en las que los usuarios deseen agregar los datos en varios informes creados en el CQD. Por ejemplo, es posible que necesite crear un informe que muestre el porcentaje de llamadas deficientes de todas las combinaciones posibles de llamadas por cable en una tabla (un resultado como la ilustración):</span><span class="sxs-lookup"><span data-stu-id="446d8-p108">CQD already has a lot of flexibility in customizing reports, but there could be situations where users may want to aggregate data across multiple reports created in CQD. For example, there could be a need to create a report that shows the poor call percentages of all possible combinations of wired calls in a table (a result like the figure):</span></span>
  
![Tabla de CQD](../../media/ef19d535-5da6-44a9-91f6-1ed3f30b96f1.png)
  
<span data-ttu-id="446d8-p109">Al usar el portal proporcionado por el CQD, el usuario tendría que ir a varios informes para extraer y registrar el % de llamadas deficientes de cada uno, que puede ser difícil si hay que recopilar muchos puntos de datos. Los API de datos ofrecen a los usuarios una forma programática para llevar a cabo esta tarea, al recuperar los datos del servicio de datos (por ejemplo, por medio de las llamadas AJAX).</span><span class="sxs-lookup"><span data-stu-id="446d8-p109">Using the Portal provided by CQD, a user would have to navigate to multiple reports to extract and record the poor call % for each one, which can be laborious if there are many data points that need to be collected. The Data APIs provide users with a programmatic way to accomplish this, by retrieving data from the Data Service (e.g. via AJAX calls).</span></span> 
  
 <span data-ttu-id="446d8-138">**Ejemplo 1: ejemplo de informe simple**</span><span class="sxs-lookup"><span data-stu-id="446d8-138">**Example 1: Simple report sample**</span></span>
  
<span data-ttu-id="446d8-p110">Veremos un ejemplo sencillo primero. Si desea mostrar el recuento de secuencias de buen audio y de mal audio de febrero de 2015 en una página web como la de la ilustración:</span><span class="sxs-lookup"><span data-stu-id="446d8-p110">Let us take a simple example first. If we want to show the Audio Good Stream and the Audio Bad stream count of February 2015 on an HTML page like the figure:</span></span>
  
![Informe de ejemplo de CQD](../../media/f0e4e61f-1fa5-4d69-b192-f19e9612bf1c.png)
  
<span data-ttu-id="446d8-p111">Lo que necesitamos es enviar una llamada al servicio de datos con los parámetros adecuados y mostrar los resultados de la consulta en una tabla HTML. A continuación se muestra un ejemplo del código JavaScript:</span><span class="sxs-lookup"><span data-stu-id="446d8-p111">What we need is to send a call to the Data Service with the proper parameters, and show the query results in an HTML table. The following is a sample of the JavaScript code:</span></span>
  
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

<span data-ttu-id="446d8-144">Este ejemplo se puede deconstruir en tres pasos:</span><span class="sxs-lookup"><span data-stu-id="446d8-144">This example can be further deconstructed into three steps:</span></span>
  
1. <span data-ttu-id="446d8-145">Construir la consulta (en el ejemplo se define en la variable 'query').</span><span class="sxs-lookup"><span data-stu-id="446d8-145">Construct the query (in the example this is defined in the variable 'query').</span></span> <span data-ttu-id="446d8-146">La consulta se define como un objeto JSON, que incluye los siguientes datos:</span><span class="sxs-lookup"><span data-stu-id="446d8-146">The query is defined as a JSON object, which includes the following data:</span></span>
    
   <span data-ttu-id="446d8-147">a.</span><span class="sxs-lookup"><span data-stu-id="446d8-147">a.</span></span> <span data-ttu-id="446d8-148">Cero o más dimensiones.</span><span class="sxs-lookup"><span data-stu-id="446d8-148">Zero or more dimensions.</span></span> <span data-ttu-id="446d8-149">Cada dimensión se indica con un DataModelName.</span><span class="sxs-lookup"><span data-stu-id="446d8-149">Each dimension is indicated by a DataModelName.</span></span>
    
   <span data-ttu-id="446d8-150">b.</span><span class="sxs-lookup"><span data-stu-id="446d8-150">b.</span></span> <span data-ttu-id="446d8-151">Cero o más filtros.</span><span class="sxs-lookup"><span data-stu-id="446d8-151">Zero or more filters.</span></span> <span data-ttu-id="446d8-152">Cada filtro tiene:</span><span class="sxs-lookup"><span data-stu-id="446d8-152">Each filter has:</span></span>
    
      - <span data-ttu-id="446d8-153">DataModelName (la dimensión que tendrá el conjunto de filtros).</span><span class="sxs-lookup"><span data-stu-id="446d8-153">DataModelName (the dimension that will have the filter set).</span></span>
    
      - <span data-ttu-id="446d8-154">Valor (el valor que comparará el operando).</span><span class="sxs-lookup"><span data-stu-id="446d8-154">Value (the value that will be compared by the operand).</span></span>
    
      - <span data-ttu-id="446d8-155">Operando (tipo de comparación, 0 significa "Igual a").</span><span class="sxs-lookup"><span data-stu-id="446d8-155">Operand (comparison type, 0 means "Equal").</span></span>
    
    <span data-ttu-id="446d8-156">c.</span><span class="sxs-lookup"><span data-stu-id="446d8-156">c.</span></span> <span data-ttu-id="446d8-157">Una o más medidas.</span><span class="sxs-lookup"><span data-stu-id="446d8-157">One or more measurements.</span></span>
    
2. <span data-ttu-id="446d8-p116">Enviar la consulta al servicio de datos por medio de llamadas AJAX. Hay que proporcionar los siguientes parámetros de solicitud:</span><span class="sxs-lookup"><span data-stu-id="446d8-p116">Send the query to Data Service via AJAX call. The following request parameters need to be provided:</span></span>
    
   <span data-ttu-id="446d8-160">a.</span><span class="sxs-lookup"><span data-stu-id="446d8-160">a.</span></span> <span data-ttu-id="446d8-161">dirección URL (que necesita ser http://[NombreDelServidor]/QoEDataService/RunQuery).</span><span class="sxs-lookup"><span data-stu-id="446d8-161">url (which should be http://[ServerName]/QoEDataService/RunQuery).</span></span>
    
   <span data-ttu-id="446d8-162">b.</span><span class="sxs-lookup"><span data-stu-id="446d8-162">b.</span></span> <span data-ttu-id="446d8-163">datos (es decir, la representación de cadena del objeto JSON definida en la variable 'query').</span><span class="sxs-lookup"><span data-stu-id="446d8-163">data (this is the string representation of the JSON object defined in the 'query' variable).</span></span> <span data-ttu-id="446d8-164">El servicio de datos devolverá los resultados de la consulta como un parámetro de la función de devolución de llamada correcta.</span><span class="sxs-lookup"><span data-stu-id="446d8-164">Data Service will return the query results as a parameter of the call back function for success.</span></span>
    
   <span data-ttu-id="446d8-165">c.</span><span class="sxs-lookup"><span data-stu-id="446d8-165">c.</span></span> <span data-ttu-id="446d8-166">tipo (para QoEDataService, RunQuery sólo acepta ' POST' solicitudes).</span><span class="sxs-lookup"><span data-stu-id="446d8-166">type (for QoEDataService, RunQuery only accepts 'POST' requests).</span></span>
    
   <span data-ttu-id="446d8-167">d.</span><span class="sxs-lookup"><span data-stu-id="446d8-167">d.</span></span> <span data-ttu-id="446d8-168">asincrónico (una marca que indica si la llamada AJAX tendría que ser sincrónica o asincrónica).</span><span class="sxs-lookup"><span data-stu-id="446d8-168">async (a flag indicating whether the AJAX call should be synchronous or asynchronous).</span></span>
    
   <span data-ttu-id="446d8-169">e.</span><span class="sxs-lookup"><span data-stu-id="446d8-169">e.</span></span> <span data-ttu-id="446d8-170">contentType (debe ser "application/json").</span><span class="sxs-lookup"><span data-stu-id="446d8-170">contentType (should be "application/json").</span></span>
    
   <span data-ttu-id="446d8-171">f.</span><span class="sxs-lookup"><span data-stu-id="446d8-171">f.</span></span> <span data-ttu-id="446d8-172">correcto (función de devolución de llamadas para cuando la llamada AJAX finaliza correctamente).</span><span class="sxs-lookup"><span data-stu-id="446d8-172">success (call-back function for when the AJAX call finishes successfully).</span></span>
    
   <span data-ttu-id="446d8-173">g.</span><span class="sxs-lookup"><span data-stu-id="446d8-173">g.</span></span> <span data-ttu-id="446d8-174">error (función de control de errores para cuando la llamada AJAX produce un error).</span><span class="sxs-lookup"><span data-stu-id="446d8-174">error (error handling function for when AJAX call fails).</span></span>
    
3. <span data-ttu-id="446d8-175">Colocar datos en elementos div en el código HTML (en el ejemplo en el código, este paso se realiza a través de la llamada de función anónima una vez que la solicitud de AJAX se ha completado correctamente).</span><span class="sxs-lookup"><span data-stu-id="446d8-175">Put data into div elements in the HTML (in the example in the code, this is done via the anonymous function call after the AJAX request is completed successfully).</span></span>
    
<span data-ttu-id="446d8-p124">Enmarcar el código JavaScript en una página HTML y la página mostrará un informe como el que se muestra en la ilustración. El HTML completo es el siguiente:</span><span class="sxs-lookup"><span data-stu-id="446d8-p124">Enclosing the JavaScript code into an HTML page, and the page will show a report like the one shown in the figure. The full html is as follows:</span></span>
  
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

<span data-ttu-id="446d8-p125">Hasta el momento, el informe es todavía muy simple. El usuario puede agregar más medidas, dimensiones, o filtros para personalizar el informe. Por ejemplo, si desea mostrar el porcentaje de llamadas deficientes de AppSharing, hay que agregar una nueva medida relacionada con AppSharing. Si desea mostrar todas las llamadas TCP frente a las llamadas UDP, tendría que agregar una nueva dimensión relacionada con el tipo de transporte. Si desea mostrar el número de llamadas deficientes dentro de un edificio determinado, tendría que agregar un nuevo filtro para seleccionar las llamadas a y desde ese edificio.</span><span class="sxs-lookup"><span data-stu-id="446d8-p125">So far, the report is still very simple. The user can add more measurements, dimensions, or filters to customize the report. For example, if you want to show AppSharing poor call percentage, then a new measurement regarding AppSharing needs to be added. If you want to show all TCP calls v.s. UDP calls, a new dimension regarding transportation type should be added. If you want to show the number of poor calls within a specific building, then a new filter should be added to select the calls to and from that building.</span></span>
  
 <span data-ttu-id="446d8-184">**Ejemplo 2: ejemplo de definición de informe**</span><span class="sxs-lookup"><span data-stu-id="446d8-184">**Example 2: Report definition sample**</span></span>
  
<span data-ttu-id="446d8-p126">Podría ser difícil averiguar cómo escribir la lista completa de medidas/dimensiones/filtros y sus valores correspondientes al construir una consulta. En este caso, puede ir al Portal, crear un informe con el editor de informes y ver la cadena JSON de la definición de informe y, luego, copiar la definición en un informe personalizado.</span><span class="sxs-lookup"><span data-stu-id="446d8-p126">It might be difficult for someone to figure out how to write the full list of measurements/dimensions/filters and their corresponding values when constructing a query. In this case, you can go to the Portal, build a report using the report editor, and view the JSON string of the report definition, and then copy the definition into a custom report.</span></span> 
  
<span data-ttu-id="446d8-p127">En este ejemplo, vamos a crear una página web como la que se muestra en la ilustración en la que el usuario puede especificar el id. de cualquier conjunto de informes existente (o del informe) y mostrar la definición del conjunto de informes o del informe en la página web. Luego, el usuario puede conectar la cadena JSON de cada informe a un código similar al que se muestra en el Ejemplo 1 y construir cualquier informe personalizado que desee el usuario.</span><span class="sxs-lookup"><span data-stu-id="446d8-p127">In this example, we will create a web page like the one shown in the figure where a user can enter the ID of any existing report set (or report) and show the definition of the report set or report on the web page. The user can then plug the JSON string of each report into code similar to the one shown in Example 1 and construct any customized report the user desires.</span></span> 
  
![Ejemplo de CQD](../../media/01c45c23-c4d2-47b8-819f-0888cf71260f.png)
  
<span data-ttu-id="446d8-p128">Para crear la herramienta del visor de definición de informe, es necesario enviar llamadas al servicio de repositorio para recuperar las representaciones de cadena JSON de las definiciones de cada conjunto de informes que queremos. El API de repositorio devolverá definiciones del conjunto de informes en función de un id. de conjunto de informes determinado.</span><span class="sxs-lookup"><span data-stu-id="446d8-p128">To create the report definition viewer tool, we need to send calls to Repository Service to retrieve the JSON string representations of the definitions of every report-set we want. The Repository API will return report-set definition based on a given report set ID.</span></span> 
  
<span data-ttu-id="446d8-192">Un ejemplo rápido es el siguiente, el código contiene un bloque que es un ejemplo sencillo para enviar una consulta al servicio de repositorio para obtener el contenido de un elemento del repositorio basado en su identificador.</span><span class="sxs-lookup"><span data-stu-id="446d8-192">A quick example is as follows, the code contains a block that is a simple example to send a query to the Repository service to get the contents of a repository item based on its identifier.</span></span> <span data-ttu-id="446d8-193">Y la siguiente parte de código (método processReportSetData) envía las llamadas AJAX para obtener la definición de cada informe dentro de ese conjunto de informes.</span><span class="sxs-lookup"><span data-stu-id="446d8-193">And the next portion of code (processReportSetData method) is sending AJAX calls to get the definition of each report within that report set.</span></span> <span data-ttu-id="446d8-194">Debido a que el id. en el portal web CQD es el id. de un conjunto de informes, la llamada AJAX devolverá un elemento del conjunto de informes.</span><span class="sxs-lookup"><span data-stu-id="446d8-194">Since the ID in the CQD web portal is the ID of a report set, the AJAX call will return a report set item.</span></span> <span data-ttu-id="446d8-195">Más detalles acerca de la API del depósito y, especialmente, GetItems, pueden encontrarse en el [Obtener elementos](get-items.md).</span><span class="sxs-lookup"><span data-stu-id="446d8-195">More detail on the Repository API and specifically, GetItems, can be found in the [Get Items](get-items.md).</span></span> 
  
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

<span data-ttu-id="446d8-196">Este ejemplo dará como resultado una página web como la de la ilustración (sin la definición de informe tras la visita inicial).</span><span class="sxs-lookup"><span data-stu-id="446d8-196">The above will result in a web page like the one in the figure (without the report definition upon initial visit).</span></span> <span data-ttu-id="446d8-197">Obtener el identificador de conjunto de informe desde el portal CQD (después / #/ iniciar sesión en el portal CQD dirección URL (por ejemplo,</span><span class="sxs-lookup"><span data-stu-id="446d8-197">Get the report set ID from CQD portal (it is after '/#/' sign in CQD portal URL (E.g.</span></span> <span data-ttu-id="446d8-198">en la primera figura el informe identificador de conjunto es 3024) y colocar este identificador de conjunto de informe en la sección de entrada de esta página web.</span><span class="sxs-lookup"><span data-stu-id="446d8-198">in the first figure the report set ID is 3024), and put this report set ID into the input section of this web page.</span></span> <span data-ttu-id="446d8-199">Pulse el botón "load" y ver la definición completa del informe (medidas, dimensiones, listas de filtros).</span><span class="sxs-lookup"><span data-stu-id="446d8-199">Press the "load" button and see the full definition (measurements, dimensions, filters lists) of the report set.</span></span>
  
<span data-ttu-id="446d8-p131">En resumen, para obtener de forma rápida la definición completa de un informe o conjunto de informes. Los pasos son:</span><span class="sxs-lookup"><span data-stu-id="446d8-p131">In summary, in order to quickly get the full definition of a report/report set. The steps are:</span></span>
  
1. <span data-ttu-id="446d8-202">Ir al Portal y utilizar el editor de consultas para personalizar un informe (haga clic en "Editar" situado sobre un informe para editar, agregar, quitar las medidas y dimensiones/filtros y, a continuación, guarde el informe).</span><span class="sxs-lookup"><span data-stu-id="446d8-202">Go to the Portal and use the query editor to customize a report (click the "Edit" button above a report to edit, add, remove measurements/dimensions/filters, and then save the report).</span></span>
    
2. <span data-ttu-id="446d8-203">Obtener el identificador de conjunto de informe desde la dirección URL (el entero después / #/ iniciar sesión en la dirección URL).</span><span class="sxs-lookup"><span data-stu-id="446d8-203">Get the report set ID from URL (the integer after '/#/' sign in URL).</span></span>
    
3. <span data-ttu-id="446d8-204">Inicie esta página web de definición de informes creada en el Ejemplo 2, escriba el id. de conjunto de informes y recupere la definición completa de un conjunto de informes (para usar en las llamadas de API de datos).</span><span class="sxs-lookup"><span data-stu-id="446d8-204">Launch this Report Definition web page created in Example 2, and enter the report set ID and retrieve the full definition of a report set (to use in Data API calls).</span></span>
    
 <span data-ttu-id="446d8-205">**Ejemplo 3: ejemplo de cuadro de mandos**</span><span class="sxs-lookup"><span data-stu-id="446d8-205">**Example 3: Scorecard sample**</span></span>
  
<span data-ttu-id="446d8-p132">Es hora de una tarea más complicada. ¿Qué ocurre si desea crear una página web como la de la ilustración? Hay que actualizar el Ejemplo 1, (con la ayuda de la página web generada en el Ejemplo 2 para recuperar la definición completa de cualquier informe) de modo que podamos controlar más cantidad de datos.</span><span class="sxs-lookup"><span data-stu-id="446d8-p132">Time for a more complicated task. What if we want to create a web page like the figure? We need to update Example 1, (with the help of the web page generated in Example 2 to retrieve the full definition of any report) so that we can handle larger amount of data.</span></span>
  
<span data-ttu-id="446d8-p133">En este caso, hay que actualizar la lista de medidas y dimensiones. La forma de averiguar cómo agregar/editar una medida o una dimensión es seguir las instrucciones en el Ejemplo 2 y recuperar la definición completa del informe, incluidas las listas de medidas y dimensiones completas. Conecte la definición completa del informe en el código de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="446d8-p133">In this case, we need to update the measurement and dimension list. The way to figure out how to add/edit a measurement and/or a dimension is to follow the instructions in Example 2, and retrieve the full report definition, including the full measurement and dimension lists. Plug the full report definition into the sample code.</span></span> 
  
<span data-ttu-id="446d8-212">Estos son los pasos detallados para ir a la página del cuadro de mandos en la ilustración del ejemplo proporcionado en el Ejemplo 1:</span><span class="sxs-lookup"><span data-stu-id="446d8-212">Here are the detailed steps to get to the scorecard page in the figure from the sample provided in Example 1:</span></span>
  
1. <span data-ttu-id="446d8-213">Actualice las medidas en la variable 'query' de `[Measures].[Audio Good Streams JPDR Count]` y `[Measures].[Audio Poor Streams JPDR Count]` a `[Measures].[AudioPoorJPDRPercentage]`.</span><span class="sxs-lookup"><span data-stu-id="446d8-213">Update Measurements in the 'query' variable from  `[Measures].[Audio Good Streams JPDR Count]` and `[Measures].[Audio Poor Streams JPDR Count]` to `[Measures].[AudioPoorJPDRPercentage]`.</span></span> 
    
2. <span data-ttu-id="446d8-214">Actualice los filtros.</span><span class="sxs-lookup"><span data-stu-id="446d8-214">Update the filters.</span></span> <span data-ttu-id="446d8-215">Los datos JSON para filtros de ejemplo 1 tienen un filtro, que se configura en la dimensión `[StartDate].[Month]`.</span><span class="sxs-lookup"><span data-stu-id="446d8-215">The JSON data for Filters in Example 1 has one filter, which is set on the dimension  `[StartDate].[Month]`.</span></span> <span data-ttu-id="446d8-216">Puesto que los filtros son una matriz JSON, se pueden agregar dimensiones adicionales a la lista de filtros.</span><span class="sxs-lookup"><span data-stu-id="446d8-216">Since Filters is a JSON array, additional dimensions can be added to the list of filters.</span></span> <span data-ttu-id="446d8-217">Por ejemplo, para obtener al cliente de servidor dentro de llamadas con cable para el "currentMonth", debemos tener los siguientes filtros:</span><span class="sxs-lookup"><span data-stu-id="446d8-217">For example, to get the server-client inside wired calls for the "currentMonth", we should have the following filters:</span></span>
    
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

  <span data-ttu-id="446d8-218">Aquí la dimensión `[Scenarios].[ScenarioPair]` se establece como igual a `[1]&amp;[0]&amp;[1]&amp;[1]&amp;[Wired]&amp;[Wired]`.</span><span class="sxs-lookup"><span data-stu-id="446d8-218">Here the dimension  `[Scenarios].[ScenarioPair]` is set to equal `[1]&amp;[0]&amp;[1]&amp;[1]&amp;[Wired]&amp;[Wired]`.</span></span> <span data-ttu-id="446d8-219">El `[Scenario.][ScenarioPair]` es una dimensión especial creada para simplificar la creación de informes.</span><span class="sxs-lookup"><span data-stu-id="446d8-219">The  `[Scenario.][ScenarioPair]` is a special dimension created to simplify report creation.</span></span> <span data-ttu-id="446d8-220">Tiene seis valores que se corresponden con `[FirstIsServer], [SecondIsServer], [FirstInside], [SecondIsServer], [FirstConnectionType], [SecondConnectionType]`.</span><span class="sxs-lookup"><span data-stu-id="446d8-220">It has six values corresponding to `[FirstIsServer], [SecondIsServer], [FirstInside], [SecondIsServer], [FirstConnectionType], [SecondConnectionType]`.</span></span> <span data-ttu-id="446d8-221">Por lo tanto, en lugar de usar una combinación de 6 filtros para definir un escenario, solo tiene que usar 1 filtro.</span><span class="sxs-lookup"><span data-stu-id="446d8-221">So instead of using a combination of 6 filters to define a scenario, we only need to use 1 filter.</span></span> <span data-ttu-id="446d8-222">En nuestro ejemplo, el valor `[1]&amp;[0]&amp;[1]&amp;[1]&amp;[Wired]&amp;[Wired]` se convierte en el escenario donde: primero es server, en segundo lugar no es servidor, primero está dentro, en segundo lugar está dentro, se conecta el primer tipo de conexión y se conecta el segundo tipo de conexión, que es la definición exacta de " Servidor-cliente-interior por cable".</span><span class="sxs-lookup"><span data-stu-id="446d8-222">In our example, the value  `[1]&amp;[0]&amp;[1]&amp;[1]&amp;[Wired]&amp;[Wired]` translates to the scenario where: first is server, second is not server, first is inside, second is inside, first connection type is wired, and second connection type is wired, which is the exact definition of "Server-Client-Inside Wired".</span></span>
    
3. <span data-ttu-id="446d8-p136">Cree un conjunto de filtros para cada escenario. Cada fila en el cuadro de mandos, en la ilustración, representa un escenario diferente, que será un filtro diferente (mientras que las dimensiones y medidas son las mismas).</span><span class="sxs-lookup"><span data-stu-id="446d8-p136">Create one filter set per scenario. Each row in the scorecard, in the figure, represents a different scenario, which will be a different filter (while the dimensions and measurements stay the same).</span></span> 
    
4. <span data-ttu-id="446d8-p137">Analice los resultados de las llamadas AJAX y colóquelos en la posición correcta de la tabla. Puesto que se trata principalmente de manipulación del HTML y del JavaScript, no entraremos en detalles. En su lugar, se proporciona el código en el Apéndice A.</span><span class="sxs-lookup"><span data-stu-id="446d8-p137">Parse the results from the AJAX calls and place them in the correct position of the table. Since this is mostly HTML and JavaScript manipulation, we will not go into the details here. Instead, the code is provided in Appendix A.</span></span>
    
    > [!NOTE]
    >  <span data-ttu-id="446d8-228">Si está habilitado el uso compartido de recursos entre origen (CORS), los usuarios pueden producirse errores como "encabezado 'Access-Control-Allow-Origin' no está presente en el recurso solicitado.</span><span class="sxs-lookup"><span data-stu-id="446d8-228">If Cross-Origin Resource Sharing (CORS) is enabled, users may encounter errors like "No 'Access-Control-Allow-Origin' header is present on the requested resource.</span></span> <span data-ttu-id="446d8-229">Origen 'null', por tanto, no se permite acceso".</span><span class="sxs-lookup"><span data-stu-id="446d8-229">Origin 'null' is therefore not allowed access".</span></span> <span data-ttu-id="446d8-230">Para resolver el problema, coloque el archivo HTML en la carpeta en la que está instalado el Portal (de forma predeterminada, necesita ser `%SystemDrive%\Program Files\Skype for Business 2015 CQD\CQD)`.</span><span class="sxs-lookup"><span data-stu-id="446d8-230">To resolve the issue, place the HTML file under the folder where the Portal is installed (by default, it should be `%SystemDrive%\Program Files\Skype for Business 2015 CQD\CQD)`.</span></span> <span data-ttu-id="446d8-231">A continuación, tener acceso el código html a través de cualquier explorador con la dirección URL `http://<servername>/cqd/<html_file_name>`.</span><span class="sxs-lookup"><span data-stu-id="446d8-231">Then access the html through any browser with the URL  `http://<servername>/cqd/<html_file_name>`.</span></span> <span data-ttu-id="446d8-232">(Es la dirección URL predeterminada para escritorio local de CQD `http://<servername>/cqd.`)</span><span class="sxs-lookup"><span data-stu-id="446d8-232">(The default URL for local CQD dashboard is  `http://<servername>/cqd.`)</span></span> 
  
### <a name="appendix-a"></a><span data-ttu-id="446d8-233">Apéndice A</span><span class="sxs-lookup"><span data-stu-id="446d8-233">Appendix A</span></span>

<span data-ttu-id="446d8-234">Código HTML para el Ejemplo 3 (ejemplo de cuadro de mandos):</span><span class="sxs-lookup"><span data-stu-id="446d8-234">HTML code for Example 3 (Scorecard sample):</span></span>
  
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


