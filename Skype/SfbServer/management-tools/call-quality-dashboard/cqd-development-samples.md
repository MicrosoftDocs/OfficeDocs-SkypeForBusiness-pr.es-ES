---
title: Ejemplos de desarrollo del Panel de calidad de llamadas
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 8ca9bf7a-2d6f-48d5-a821-531009726525
description: 'Resumen: revise un tutorial y ejemplos de desarrollo para el Panel de calidad de llamadas. El Panel de calidad de llamadas es una herramienta para Skype Empresarial Server.'
ms.openlocfilehash: 193a03662d6f771b19c57017d909cc6574a755ef
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832730"
---
# <a name="cqd-development-samples"></a><span data-ttu-id="e5ead-104">Ejemplos de desarrollo del Panel de calidad de llamadas</span><span class="sxs-lookup"><span data-stu-id="e5ead-104">CQD Development Samples</span></span>

<span data-ttu-id="e5ead-105">**Resumen:** Revise un tutorial y ejemplos de desarrollo para el Panel de calidad de llamadas.</span><span class="sxs-lookup"><span data-stu-id="e5ead-105">**Summary:** Review a tutorial and development samples for Call Quality Dashboard.</span></span> <span data-ttu-id="e5ead-106">El Panel de calidad de llamadas es una herramienta para Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="e5ead-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>

<span data-ttu-id="e5ead-107">En este artículo se proporciona un tutorial y ejemplos sobre el desarrollo del Panel de calidad de llamadas (CQD).</span><span class="sxs-lookup"><span data-stu-id="e5ead-107">This article provides a tutorial and samples on development for Call Quality Dashboard (CQD).</span></span>

## <a name="call-quality-dashboard-cqd-development-samples"></a><span data-ttu-id="e5ead-108">Ejemplos de desarrollo del Panel de calidad de llamadas (CQD)</span><span class="sxs-lookup"><span data-stu-id="e5ead-108">Call Quality Dashboard (CQD) Development Samples</span></span>

<span data-ttu-id="e5ead-109">Tutorial: Creación de una presentación de informes personalizada con las API del servicio de datos de CQD y del servicio de repositorio.</span><span class="sxs-lookup"><span data-stu-id="e5ead-109">Tutorial: Building Customized Report Presentation using the CQD Data Service and Repository Service API's.</span></span>

### <a name="introduction-to-cqd"></a><span data-ttu-id="e5ead-110">Introducción al CQD</span><span class="sxs-lookup"><span data-stu-id="e5ead-110">Introduction to CQD</span></span>

<span data-ttu-id="e5ead-111">El CQD ofrece un acceso rápido y fácil a la información de calidad de llamadas agregada para las implementaciones locales de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="e5ead-111">CQD offers quick and easy access to aggregated call quality information for on-premise Skype for Business Server deployments.</span></span> <span data-ttu-id="e5ead-112">El CQD consta de tres componentes: la base de datos de archivo qoE, el cubo y el portal.</span><span class="sxs-lookup"><span data-stu-id="e5ead-112">CQD consists of three components: the QoE Archive database, the Cube, and the Portal.</span></span> <span data-ttu-id="e5ead-113">El portal es la capa de presentación principal y se puede dividir en los tres componentes siguientes:</span><span class="sxs-lookup"><span data-stu-id="e5ead-113">The Portal is the main presentation layer and can be further divided into the following three components:</span></span>

1. <span data-ttu-id="e5ead-114">Servicio de datos, que es accesible para los usuarios autenticados a través de la API de datos para el Panel de calidad de llamadas [(CQD) en Skype Empresarial Server.](data-api.md)</span><span class="sxs-lookup"><span data-stu-id="e5ead-114">Data Service, which is accessible for authenticated users through the [Data API for Call Quality Dashboard (CQD) in Skype for Business Server](data-api.md).</span></span>

2. <span data-ttu-id="e5ead-115">Servicio de repositorio, que es accesible para los usuarios autenticados a través de la API de repositorio para el Panel de calidad de llamadas [(CQD) en Skype Empresarial Server.](repository-api.md)</span><span class="sxs-lookup"><span data-stu-id="e5ead-115">Repository Service, which is accessible for authenticated users through the [Repository API for Call Quality Dashboard (CQD) in Skype for Business Server](repository-api.md).</span></span>

3. <span data-ttu-id="e5ead-116">Portal web, que es la interfaz basada en HTML5 con la que los usuarios del CQD ven e interactúan.</span><span class="sxs-lookup"><span data-stu-id="e5ead-116">Web portal, which is the HTML5 based interface that CQD users see and interact with.</span></span> <span data-ttu-id="e5ead-117">Esto es accesible para los usuarios autenticados.</span><span class="sxs-lookup"><span data-stu-id="e5ead-117">This is accessible for authenticated users.</span></span>

<span data-ttu-id="e5ead-118">Los informes que se muestran en el portal web se agrupan en "conjuntos de informes".</span><span class="sxs-lookup"><span data-stu-id="e5ead-118">The reports shown on the web portal are grouped into "report sets".</span></span> <span data-ttu-id="e5ead-119">La figura muestra un conjunto de informes con dos informes.</span><span class="sxs-lookup"><span data-stu-id="e5ead-119">The figure shows a report set with two reports.</span></span> <span data-ttu-id="e5ead-120">Cada informe de este panel siguiente muestra los resultados de la consulta sobre el número de llamadas buenas, llamadas deficientes y porcentaje de llamadas deficientes durante varios meses, con varios filtros aplicados.</span><span class="sxs-lookup"><span data-stu-id="e5ead-120">Each report in this dashboard below shows query results on number of good calls, poor calls and poor call percentage for several months, with various filters applied.</span></span> 

![Informe de ejemplo de CQD](../../media/9e0723f7-f850-4d11-9ecd-7e8e013a8bed.png)

<span data-ttu-id="e5ead-122">El CQD se crea siguiendo la Metodología de calidad de llamadas (CQM), por lo que el conjunto predeterminado de informes está diseñado para alinearse con el flujo de investigación introducido por CQM.</span><span class="sxs-lookup"><span data-stu-id="e5ead-122">CQD is created following the Call Quality Methodology (CQM), so the default set of reports is designed to align with the investigation flow introduced by CQM.</span></span> <span data-ttu-id="e5ead-123">Los usuarios también tienen la flexibilidad de editar o crear informes personalizados para satisfacer sus necesidades.</span><span class="sxs-lookup"><span data-stu-id="e5ead-123">Users also have the flexibility to edit or create custom reports to meet their needs.</span></span> <span data-ttu-id="e5ead-124">Sin embargo, dado que hay varias formas de visualizar los datos, la visualización proporcionada por el CQD puede no satisfacer completamente las necesidades de cada usuario.</span><span class="sxs-lookup"><span data-stu-id="e5ead-124">However, since there are multiple ways to visualize the data, the visualization provided by CQD may not fully address the needs of every user.</span></span> <span data-ttu-id="e5ead-125">En estas situaciones, un usuario puede aprovechar las API de datos y las API de repositorio para crear páginas de informes personalizadas.</span><span class="sxs-lookup"><span data-stu-id="e5ead-125">In such situations, a user can leverage the Data APIs and Repository APIs to create custom report pages.</span></span> <span data-ttu-id="e5ead-126">Vamos a ver una serie de ejemplos en este tutorial.</span><span class="sxs-lookup"><span data-stu-id="e5ead-126">We will go through a series of examples in this tutorial.</span></span>

### <a name="how-the-dashboard-consumes-the-data-service"></a><span data-ttu-id="e5ead-127">Cómo usa el panel el servicio de datos</span><span class="sxs-lookup"><span data-stu-id="e5ead-127">How the dashboard consumes the data service</span></span>

<span data-ttu-id="e5ead-128">Al navegar a la página principal del CQD (por ejemplo, el conjunto de informes y los informes correspondientes de un usuario autenticado y autorizado se recuperarán del servicio http://localhost/cqd) de repositorio.</span><span class="sxs-lookup"><span data-stu-id="e5ead-128">When navigating to the CQD homepage (e.g. http://localhost/cqd), the report set and corresponding reports for an authenticated and authorized user will be retrieved from the Repository Service.</span></span> <span data-ttu-id="e5ead-129">Se construirá una dirección URL completa a partir del identificador del conjunto de informes y el año-mes (el identificador del conjunto de informes es el número entero después de la sección "/#/" en la dirección URL y, de forma predeterminada, el año-mes actual se anexa al final del identificador del conjunto de informes después de la barra diagonal).</span><span class="sxs-lookup"><span data-stu-id="e5ead-129">A full URL will be constructed from the report-set ID and the year-month (report-set ID is the integer number after '/#/' section in URL, and by default the current year-month is appended at the end of the report-set ID after the slash).</span></span> <span data-ttu-id="e5ead-130">Las definiciones de informe se almacenan en formato JSON y, cuando se recuperan del servicio de repositorio, se usarán como entrada para el servicio de datos.</span><span class="sxs-lookup"><span data-stu-id="e5ead-130">The report definitions are stored in JSON format and when retrieved from the Repository Service, will then be used as input to the Data Service.</span></span> <span data-ttu-id="e5ead-131">El servicio de datos genera consultas de expresiones multi dimension (MDX) basadas en la entrada y, a continuación, ejecuta estas consultas MDX en el cubo para recuperar datos para cada informe.</span><span class="sxs-lookup"><span data-stu-id="e5ead-131">The Data Service generates Multi-Dimension expressions (MDX) queries based on the input and then run these MDX queries against the Cube to retrieve data for each report.</span></span> 

### <a name="building-customized-reports"></a><span data-ttu-id="e5ead-132">Creación de informes personalizados</span><span class="sxs-lookup"><span data-stu-id="e5ead-132">Building customized reports</span></span>

<span data-ttu-id="e5ead-133">El CQD ya tiene mucha flexibilidad a la hora de personalizar informes, pero puede haber situaciones en las que los usuarios quieran agregar datos en varios informes creados en el CQD.</span><span class="sxs-lookup"><span data-stu-id="e5ead-133">CQD already has a lot of flexibility in customizing reports, but there could be situations where users may want to aggregate data across multiple reports created in CQD.</span></span> <span data-ttu-id="e5ead-134">Por ejemplo, podría ser necesario crear un informe que muestre los porcentajes de llamadas deficientes de todas las combinaciones posibles de llamadas cableadas en una tabla (un resultado como la figura):</span><span class="sxs-lookup"><span data-stu-id="e5ead-134">For example, there could be a need to create a report that shows the poor call percentages of all possible combinations of wired calls in a table (a result like the figure):</span></span>

![Tabla CQD](../../media/ef19d535-5da6-44a9-91f6-1ed3f30b96f1.png)

<span data-ttu-id="e5ead-136">Con el Portal proporcionado por el CQD, un usuario tendría que navegar a varios informes para extraer y registrar el porcentaje de llamadas deficientes para cada uno de ellos, lo que puede ser laborioso si hay muchos puntos de datos que deben recopilarse.</span><span class="sxs-lookup"><span data-stu-id="e5ead-136">Using the Portal provided by CQD, a user would have to navigate to multiple reports to extract and record the poor call % for each one, which can be laborious if there are many data points that need to be collected.</span></span> <span data-ttu-id="e5ead-137">Las API de datos proporcionan a los usuarios una forma de hacerlo mediante programación, mediante la recuperación de datos del servicio de datos (por ejemplo, a través de llamadas AJAX).</span><span class="sxs-lookup"><span data-stu-id="e5ead-137">The Data APIs provide users with a programmatic way to accomplish this, by retrieving data from the Data Service (e.g. via AJAX calls).</span></span> 

 <span data-ttu-id="e5ead-138">**Ejemplo 1: ejemplo de informe simple**</span><span class="sxs-lookup"><span data-stu-id="e5ead-138">**Example 1: Simple report sample**</span></span>

<span data-ttu-id="e5ead-139">Veamos un ejemplo sencillo en primer lugar.</span><span class="sxs-lookup"><span data-stu-id="e5ead-139">Let us take a simple example first.</span></span> <span data-ttu-id="e5ead-140">Si queremos mostrar el recuento de secuencias de audio buena y mala de audio de febrero de 2015 en una página HTML como la figura:</span><span class="sxs-lookup"><span data-stu-id="e5ead-140">If we want to show the Audio Good Stream and the Audio Bad stream count of February 2015 on an HTML page like the figure:</span></span>

![Informe de ejemplo de CQD](../../media/f0e4e61f-1fa5-4d69-b192-f19e9612bf1c.png)

<span data-ttu-id="e5ead-142">Lo que necesitamos es enviar una llamada al servicio de datos con los parámetros adecuados y mostrar los resultados de la consulta en una tabla HTML.</span><span class="sxs-lookup"><span data-stu-id="e5ead-142">What we need is to send a call to the Data Service with the proper parameters, and show the query results in an HTML table.</span></span> <span data-ttu-id="e5ead-143">A continuación se muestra un ejemplo del código JavaScript:</span><span class="sxs-lookup"><span data-stu-id="e5ead-143">The following is a sample of the JavaScript code:</span></span>

```javascript        
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

<span data-ttu-id="e5ead-144">Este ejemplo se puede desconstruir en tres pasos:</span><span class="sxs-lookup"><span data-stu-id="e5ead-144">This example can be further deconstructed into three steps:</span></span>

1. <span data-ttu-id="e5ead-145">Construya la consulta (en el ejemplo se define en la variable 'query').</span><span class="sxs-lookup"><span data-stu-id="e5ead-145">Construct the query (in the example this is defined in the variable 'query').</span></span> <span data-ttu-id="e5ead-146">La consulta se define como un objeto JSON, que incluye los siguientes datos:</span><span class="sxs-lookup"><span data-stu-id="e5ead-146">The query is defined as a JSON object, which includes the following data:</span></span>

   <span data-ttu-id="e5ead-147">a.</span><span class="sxs-lookup"><span data-stu-id="e5ead-147">a.</span></span> <span data-ttu-id="e5ead-148">Cero o más dimensiones.</span><span class="sxs-lookup"><span data-stu-id="e5ead-148">Zero or more dimensions.</span></span> <span data-ttu-id="e5ead-149">Cada dimensión se indica mediante un DataModelName.</span><span class="sxs-lookup"><span data-stu-id="e5ead-149">Each dimension is indicated by a DataModelName.</span></span>

   <span data-ttu-id="e5ead-150">b.</span><span class="sxs-lookup"><span data-stu-id="e5ead-150">b.</span></span> <span data-ttu-id="e5ead-151">Cero o más filtros.</span><span class="sxs-lookup"><span data-stu-id="e5ead-151">Zero or more filters.</span></span> <span data-ttu-id="e5ead-152">Cada filtro tiene:</span><span class="sxs-lookup"><span data-stu-id="e5ead-152">Each filter has:</span></span>

   - <span data-ttu-id="e5ead-153">DataModelName (la dimensión que tendrá el conjunto de filtros).</span><span class="sxs-lookup"><span data-stu-id="e5ead-153">DataModelName (the dimension that will have the filter set).</span></span>

   - <span data-ttu-id="e5ead-154">Valor (el valor que comparará el operando).</span><span class="sxs-lookup"><span data-stu-id="e5ead-154">Value (the value that will be compared by the operand).</span></span>

   - <span data-ttu-id="e5ead-155">Operando (tipo de comparación, 0 significa "Igual").</span><span class="sxs-lookup"><span data-stu-id="e5ead-155">Operand (comparison type, 0 means "Equal").</span></span>

     <span data-ttu-id="e5ead-156">c.</span><span class="sxs-lookup"><span data-stu-id="e5ead-156">c.</span></span> <span data-ttu-id="e5ead-157">Una o más medidas.</span><span class="sxs-lookup"><span data-stu-id="e5ead-157">One or more measurements.</span></span>

2. <span data-ttu-id="e5ead-158">Envíe la consulta al servicio de datos a través de una llamada AJAX.</span><span class="sxs-lookup"><span data-stu-id="e5ead-158">Send the query to Data Service via AJAX call.</span></span> <span data-ttu-id="e5ead-159">Deben proporcionarse los siguientes parámetros de solicitud:</span><span class="sxs-lookup"><span data-stu-id="e5ead-159">The following request parameters need to be provided:</span></span>

   <span data-ttu-id="e5ead-160">a.</span><span class="sxs-lookup"><span data-stu-id="e5ead-160">a.</span></span> <span data-ttu-id="e5ead-161">url (que debe ser http://[ServerName]/QoEDataService/RunQuery).</span><span class="sxs-lookup"><span data-stu-id="e5ead-161">url (which should be http://[ServerName]/QoEDataService/RunQuery).</span></span>

   <span data-ttu-id="e5ead-162">b.</span><span class="sxs-lookup"><span data-stu-id="e5ead-162">b.</span></span> <span data-ttu-id="e5ead-163">(esta es la representación de cadena del objeto JSON definido en la variable 'query').</span><span class="sxs-lookup"><span data-stu-id="e5ead-163">data (this is the string representation of the JSON object defined in the 'query' variable).</span></span> <span data-ttu-id="e5ead-164">El servicio de datos devolverá los resultados de la consulta como parámetro de la función de devolución de llamada para que se devuelva correctamente.</span><span class="sxs-lookup"><span data-stu-id="e5ead-164">Data Service will return the query results as a parameter of the call back function for success.</span></span>

   <span data-ttu-id="e5ead-165">c.</span><span class="sxs-lookup"><span data-stu-id="e5ead-165">c.</span></span> <span data-ttu-id="e5ead-166">(para QoEDataService, RunQuery solo acepta solicitudes "POST").</span><span class="sxs-lookup"><span data-stu-id="e5ead-166">type (for QoEDataService, RunQuery only accepts 'POST' requests).</span></span>

   <span data-ttu-id="e5ead-167">d.</span><span class="sxs-lookup"><span data-stu-id="e5ead-167">d.</span></span> <span data-ttu-id="e5ead-168">asincrónico (una marca que indica si la llamada AJAX debe ser sincrónica o asincrónica).</span><span class="sxs-lookup"><span data-stu-id="e5ead-168">async (a flag indicating whether the AJAX call should be synchronous or asynchronous).</span></span>

   <span data-ttu-id="e5ead-169">e.</span><span class="sxs-lookup"><span data-stu-id="e5ead-169">e.</span></span> <span data-ttu-id="e5ead-170">contentType (debe ser "application/json").</span><span class="sxs-lookup"><span data-stu-id="e5ead-170">contentType (should be "application/json").</span></span>

   <span data-ttu-id="e5ead-171">f.</span><span class="sxs-lookup"><span data-stu-id="e5ead-171">f.</span></span> <span data-ttu-id="e5ead-172">correcto (función de des llamada cuando la llamada AJAX finaliza correctamente).</span><span class="sxs-lookup"><span data-stu-id="e5ead-172">success (call-back function for when the AJAX call finishes successfully).</span></span>

   <span data-ttu-id="e5ead-173">g.</span><span class="sxs-lookup"><span data-stu-id="e5ead-173">g.</span></span> <span data-ttu-id="e5ead-174">error (función de control de errores cuando se produce un error en la llamada AJAX).</span><span class="sxs-lookup"><span data-stu-id="e5ead-174">error (error handling function for when AJAX call fails).</span></span>

3. <span data-ttu-id="e5ead-175">Coloque los datos en elementos div en el código HTML (en el ejemplo del código, esto se realiza a través de la llamada de función anónima después de que la solicitud AJAX se complete correctamente).</span><span class="sxs-lookup"><span data-stu-id="e5ead-175">Put data into div elements in the HTML (in the example in the code, this is done via the anonymous function call after the AJAX request is completed successfully).</span></span>

<span data-ttu-id="e5ead-176">Si se incluye el código JavaScript en una página HTML, la página mostrará un informe como el que se muestra en la figura.</span><span class="sxs-lookup"><span data-stu-id="e5ead-176">Enclosing the JavaScript code into an HTML page, and the page will show a report like the one shown in the figure.</span></span> <span data-ttu-id="e5ead-177">El html completo es el siguiente:</span><span class="sxs-lookup"><span data-stu-id="e5ead-177">The full html is as follows:</span></span>

```javascript
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

<span data-ttu-id="e5ead-178">Hasta ahora, el informe sigue siendo muy sencillo.</span><span class="sxs-lookup"><span data-stu-id="e5ead-178">So far, the report is still very simple.</span></span> <span data-ttu-id="e5ead-179">El usuario puede agregar más medidas, dimensiones o filtros para personalizar el informe.</span><span class="sxs-lookup"><span data-stu-id="e5ead-179">The user can add more measurements, dimensions, or filters to customize the report.</span></span> <span data-ttu-id="e5ead-180">Por ejemplo, si quieres mostrar el porcentaje de llamadas deficientes de AppSharing, debe agregarse una nueva medida relativa a AppSharing.</span><span class="sxs-lookup"><span data-stu-id="e5ead-180">For example, if you want to show AppSharing poor call percentage, then a new measurement regarding AppSharing needs to be added.</span></span> <span data-ttu-id="e5ead-181">Si desea mostrar todas las llamadas TCP v.s.</span><span class="sxs-lookup"><span data-stu-id="e5ead-181">If you want to show all TCP calls v.s.</span></span> <span data-ttu-id="e5ead-182">Llamadas UDP, debe agregarse una nueva dimensión en relación con el tipo de transporte.</span><span class="sxs-lookup"><span data-stu-id="e5ead-182">UDP calls, a new dimension regarding transportation type should be added.</span></span> <span data-ttu-id="e5ead-183">Si desea mostrar el número de llamadas deficientes dentro de un edificio específico, debe agregarse un nuevo filtro para seleccionar las llamadas a y desde ese edificio.</span><span class="sxs-lookup"><span data-stu-id="e5ead-183">If you want to show the number of poor calls within a specific building, then a new filter should be added to select the calls to and from that building.</span></span>

 <span data-ttu-id="e5ead-184">**Ejemplo 2: ejemplo de definición de informe**</span><span class="sxs-lookup"><span data-stu-id="e5ead-184">**Example 2: Report definition sample**</span></span>

<span data-ttu-id="e5ead-185">Puede ser difícil para alguien averiguar cómo escribir la lista completa de medidas, dimensiones/filtros y sus valores correspondientes al construir una consulta.</span><span class="sxs-lookup"><span data-stu-id="e5ead-185">It might be difficult for someone to figure out how to write the full list of measurements/dimensions/filters and their corresponding values when constructing a query.</span></span> <span data-ttu-id="e5ead-186">En este caso, puede ir al Portal, crear un informe con el editor de informes, ver la cadena JSON de la definición del informe y, a continuación, copiar la definición en un informe personalizado.</span><span class="sxs-lookup"><span data-stu-id="e5ead-186">In this case, you can go to the Portal, build a report using the report editor, and view the JSON string of the report definition, and then copy the definition into a custom report.</span></span> 

<span data-ttu-id="e5ead-187">En este ejemplo, crearemos una página web como la que se muestra en la figura donde un usuario puede escribir el identificador de cualquier conjunto de informes existente (o informe) y mostrar la definición del conjunto de informes o informe en la página web.</span><span class="sxs-lookup"><span data-stu-id="e5ead-187">In this example, we will create a web page like the one shown in the figure where a user can enter the ID of any existing report set (or report) and show the definition of the report set or report on the web page.</span></span> <span data-ttu-id="e5ead-188">A continuación, el usuario puede conectar la cadena JSON de cada informe en un código similar al que se muestra en el ejemplo 1 y crear cualquier informe personalizado que el usuario desee.</span><span class="sxs-lookup"><span data-stu-id="e5ead-188">The user can then plug the JSON string of each report into code similar to the one shown in Example 1 and construct any customized report the user desires.</span></span> 

![Ejemplo de CQD](../../media/01c45c23-c4d2-47b8-819f-0888cf71260f.png)

<span data-ttu-id="e5ead-190">Para crear la herramienta visor de definiciones de informes, necesitamos enviar llamadas al servicio de repositorio para recuperar las representaciones de cadena JSON de las definiciones de cada conjunto de informes que queremos.</span><span class="sxs-lookup"><span data-stu-id="e5ead-190">To create the report definition viewer tool, we need to send calls to Repository Service to retrieve the JSON string representations of the definitions of every report-set we want.</span></span> <span data-ttu-id="e5ead-191">La API de repositorio devolverá la definición del conjunto de informes en función de un identificador de conjunto de informes determinado.</span><span class="sxs-lookup"><span data-stu-id="e5ead-191">The Repository API will return report-set definition based on a given report set ID.</span></span> 

<span data-ttu-id="e5ead-192">Un ejemplo rápido es el siguiente, el código contiene un bloque que es un ejemplo sencillo para enviar una consulta al servicio repositorio para obtener el contenido de un elemento de repositorio en función de su identificador.</span><span class="sxs-lookup"><span data-stu-id="e5ead-192">A quick example is as follows, the code contains a block that is a simple example to send a query to the Repository service to get the contents of a repository item based on its identifier.</span></span> <span data-ttu-id="e5ead-193">Y la siguiente parte del código (método processReportSetData) es enviar llamadas AJAX para obtener la definición de cada informe dentro de ese conjunto de informes.</span><span class="sxs-lookup"><span data-stu-id="e5ead-193">And the next portion of code (processReportSetData method) is sending AJAX calls to get the definition of each report within that report set.</span></span> <span data-ttu-id="e5ead-194">Dado que el identificador del portal web de CQD es el identificador de un conjunto de informes, la llamada AJAX devolverá un elemento del conjunto de informes.</span><span class="sxs-lookup"><span data-stu-id="e5ead-194">Since the ID in the CQD web portal is the ID of a report set, the AJAX call will return a report set item.</span></span> <span data-ttu-id="e5ead-195">Encontrará más información sobre la API de repositorio y, específicamente, GetItems, en [Obtener elementos.](get-items.md)</span><span class="sxs-lookup"><span data-stu-id="e5ead-195">More detail on the Repository API and specifically, GetItems, can be found in the [Get Items](get-items.md).</span></span> 

```html
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

<span data-ttu-id="e5ead-196">Lo anterior dará como resultado una página web como la de la figura (sin la definición del informe tras la visita inicial).</span><span class="sxs-lookup"><span data-stu-id="e5ead-196">The above will result in a web page like the one in the figure (without the report definition upon initial visit).</span></span> <span data-ttu-id="e5ead-197">Obtener el identificador del conjunto de informes del portal CQD (es después del inicio de sesión "/#/" en la dirección URL del portal CQD (por ejemplo,</span><span class="sxs-lookup"><span data-stu-id="e5ead-197">Get the report set ID from CQD portal (it is after '/#/' sign in CQD portal URL (E.g.</span></span> <span data-ttu-id="e5ead-198">en la primera figura, el identificador del conjunto de informes es 3024) y coloque este identificador del conjunto de informes en la sección de entrada de esta página web.</span><span class="sxs-lookup"><span data-stu-id="e5ead-198">in the first figure the report set ID is 3024), and put this report set ID into the input section of this web page.</span></span> <span data-ttu-id="e5ead-199">Presione el botón "cargar" y vea la definición completa (medidas, dimensiones, listas de filtros) del conjunto de informes.</span><span class="sxs-lookup"><span data-stu-id="e5ead-199">Press the "load" button and see the full definition (measurements, dimensions, filters lists) of the report set.</span></span>

<span data-ttu-id="e5ead-200">En resumen, para obtener rápidamente la definición completa de un conjunto de informes o informes.</span><span class="sxs-lookup"><span data-stu-id="e5ead-200">In summary, in order to quickly get the full definition of a report/report set.</span></span> <span data-ttu-id="e5ead-201">Estos pasos son:</span><span class="sxs-lookup"><span data-stu-id="e5ead-201">The steps are:</span></span>

1. <span data-ttu-id="e5ead-202">Vaya al Portal y use el editor de consultas para personalizar un informe (haga clic en el botón "Editar" situado encima de un informe para editar, agregar, quitar medidas, dimensiones/filtros y, a continuación, guardar el informe).</span><span class="sxs-lookup"><span data-stu-id="e5ead-202">Go to the Portal and use the query editor to customize a report (click the "Edit" button above a report to edit, add, remove measurements/dimensions/filters, and then save the report).</span></span>

2. <span data-ttu-id="e5ead-203">Obtener el identificador del conjunto de informes de la dirección URL (el entero después de la dirección URL de inicio de sesión "/#/").</span><span class="sxs-lookup"><span data-stu-id="e5ead-203">Get the report set ID from URL (the integer after '/#/' sign in URL).</span></span>

3. <span data-ttu-id="e5ead-204">Inicie esta página web de definición de informe creada en el ejemplo 2 y escriba el identificador del conjunto de informes y recupere la definición completa de un conjunto de informes (para usarla en llamadas api de datos).</span><span class="sxs-lookup"><span data-stu-id="e5ead-204">Launch this Report Definition web page created in Example 2, and enter the report set ID and retrieve the full definition of a report set (to use in Data API calls).</span></span>

   <span data-ttu-id="e5ead-205">**Ejemplo 3: ejemplo de cuadro de mandos**</span><span class="sxs-lookup"><span data-stu-id="e5ead-205">**Example 3: Scorecard sample**</span></span>

<span data-ttu-id="e5ead-206">Hora de una tarea más complicada.</span><span class="sxs-lookup"><span data-stu-id="e5ead-206">Time for a more complicated task.</span></span> <span data-ttu-id="e5ead-207">¿Qué ocurre si queremos crear una página web como la figura?</span><span class="sxs-lookup"><span data-stu-id="e5ead-207">What if we want to create a web page like the figure?</span></span> <span data-ttu-id="e5ead-208">Es necesario actualizar el ejemplo 1 (con la ayuda de la página web generada en el ejemplo 2 para recuperar la definición completa de cualquier informe) para poder controlar una mayor cantidad de datos.</span><span class="sxs-lookup"><span data-stu-id="e5ead-208">We need to update Example 1, (with the help of the web page generated in Example 2 to retrieve the full definition of any report) so that we can handle larger amount of data.</span></span>

<span data-ttu-id="e5ead-209">En este caso, necesitamos actualizar la lista de medidas y dimensiones.</span><span class="sxs-lookup"><span data-stu-id="e5ead-209">In this case, we need to update the measurement and dimension list.</span></span> <span data-ttu-id="e5ead-210">La forma de averiguar cómo agregar o editar una medida o una dimensión es seguir las instrucciones del ejemplo 2 y recuperar la definición completa del informe, incluidas las listas completas de medidas y dimensiones.</span><span class="sxs-lookup"><span data-stu-id="e5ead-210">The way to figure out how to add/edit a measurement and/or a dimension is to follow the instructions in Example 2, and retrieve the full report definition, including the full measurement and dimension lists.</span></span> <span data-ttu-id="e5ead-211">Conecte la definición completa del informe en el código de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="e5ead-211">Plug the full report definition into the sample code.</span></span> 

<span data-ttu-id="e5ead-212">Estos son los pasos detallados para ir a la página del cuadro de mandos en la figura del ejemplo proporcionado en el ejemplo 1:</span><span class="sxs-lookup"><span data-stu-id="e5ead-212">Here are the detailed steps to get to the scorecard page in the figure from the sample provided in Example 1:</span></span>

1. <span data-ttu-id="e5ead-213">Actualizar medidas en la variable "consulta" de  `[Measures].[Audio Good Streams JPDR Count]` y `[Measures].[Audio Poor Streams JPDR Count]` a `[Measures].[AudioPoorJPDRPercentage]` .</span><span class="sxs-lookup"><span data-stu-id="e5ead-213">Update Measurements in the 'query' variable from  `[Measures].[Audio Good Streams JPDR Count]` and `[Measures].[Audio Poor Streams JPDR Count]` to `[Measures].[AudioPoorJPDRPercentage]`.</span></span> 

2. <span data-ttu-id="e5ead-214">Actualice los filtros.</span><span class="sxs-lookup"><span data-stu-id="e5ead-214">Update the filters.</span></span> <span data-ttu-id="e5ead-215">Los datos JSON de filtros del ejemplo 1 tienen un filtro, que se establece en la dimensión  `[StartDate].[Month]` .</span><span class="sxs-lookup"><span data-stu-id="e5ead-215">The JSON data for Filters in Example 1 has one filter, which is set on the dimension  `[StartDate].[Month]`.</span></span> <span data-ttu-id="e5ead-216">Dado que Filters es una matriz JSON, se pueden agregar dimensiones adicionales a la lista de filtros.</span><span class="sxs-lookup"><span data-stu-id="e5ead-216">Since Filters is a JSON array, additional dimensions can be added to the list of filters.</span></span> <span data-ttu-id="e5ead-217">Por ejemplo, para obtener el servidor-cliente dentro de llamadas cableadas para el "currentMonth", debemos tener los siguientes filtros:</span><span class="sxs-lookup"><span data-stu-id="e5ead-217">For example, to get the server-client inside wired calls for the "currentMonth", we should have the following filters:</span></span>

   ```javascript
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

   <span data-ttu-id="e5ead-218">Aquí la dimensión  `[Scenarios].[ScenarioPair]` se establece en igual `[1]&amp;[0]&amp;[1]&amp;[1]&amp;[Wired]&amp;[Wired]` .</span><span class="sxs-lookup"><span data-stu-id="e5ead-218">Here the dimension  `[Scenarios].[ScenarioPair]` is set to equal `[1]&amp;[0]&amp;[1]&amp;[1]&amp;[Wired]&amp;[Wired]`.</span></span> <span data-ttu-id="e5ead-219">Se  `[Scenario.][ScenarioPair]` trata de una dimensión especial creada para simplificar la creación de informes.</span><span class="sxs-lookup"><span data-stu-id="e5ead-219">The  `[Scenario.][ScenarioPair]` is a special dimension created to simplify report creation.</span></span> <span data-ttu-id="e5ead-220">Tiene seis valores correspondientes a `[FirstIsServer], [SecondIsServer], [FirstInside], [SecondIsServer], [FirstConnectionType], [SecondConnectionType]` .</span><span class="sxs-lookup"><span data-stu-id="e5ead-220">It has six values corresponding to `[FirstIsServer], [SecondIsServer], [FirstInside], [SecondIsServer], [FirstConnectionType], [SecondConnectionType]`.</span></span> <span data-ttu-id="e5ead-221">Por lo tanto, en lugar de usar una combinación de 6 filtros para definir un escenario, solo necesitamos usar 1 filtro.</span><span class="sxs-lookup"><span data-stu-id="e5ead-221">So instead of using a combination of 6 filters to define a scenario, we only need to use 1 filter.</span></span> <span data-ttu-id="e5ead-222">En nuestro ejemplo, el valor se traduce en el escenario donde: primero es el servidor, el segundo no es el servidor, el primero está dentro, el segundo está dentro, el primer tipo de conexión está cableado y el segundo tipo de conexión está cableado, que es la definición exacta de  `[1]&amp;[0]&amp;[1]&amp;[1]&amp;[Wired]&amp;[Wired]` "Server-Client-Inside Wired".</span><span class="sxs-lookup"><span data-stu-id="e5ead-222">In our example, the value  `[1]&amp;[0]&amp;[1]&amp;[1]&amp;[Wired]&amp;[Wired]` translates to the scenario where: first is server, second is not server, first is inside, second is inside, first connection type is wired, and second connection type is wired, which is the exact definition of "Server-Client-Inside Wired".</span></span>

3. <span data-ttu-id="e5ead-223">Cree un conjunto de filtros por escenario.</span><span class="sxs-lookup"><span data-stu-id="e5ead-223">Create one filter set per scenario.</span></span> <span data-ttu-id="e5ead-224">Cada fila del cuadro de mandos, en la figura, representa un escenario diferente, que será un filtro diferente (mientras que las dimensiones y medidas permanecen iguales).</span><span class="sxs-lookup"><span data-stu-id="e5ead-224">Each row in the scorecard, in the figure, represents a different scenario, which will be a different filter (while the dimensions and measurements stay the same).</span></span> 

4. <span data-ttu-id="e5ead-225">Analizar los resultados de las llamadas AJAX y colocarlos en la posición correcta de la tabla.</span><span class="sxs-lookup"><span data-stu-id="e5ead-225">Parse the results from the AJAX calls and place them in the correct position of the table.</span></span> <span data-ttu-id="e5ead-226">Dado que esto es principalmente manipulación de HTML y JavaScript, no entraremos en los detalles aquí.</span><span class="sxs-lookup"><span data-stu-id="e5ead-226">Since this is mostly HTML and JavaScript manipulation, we will not go into the details here.</span></span> <span data-ttu-id="e5ead-227">En su lugar, el código se proporciona en el Apéndice A.</span><span class="sxs-lookup"><span data-stu-id="e5ead-227">Instead, the code is provided in Appendix A.</span></span>

    > [!NOTE]
    >  <span data-ttu-id="e5ead-228">Si el uso compartido de recursos entre orígenes (CORS) está habilitado, los usuarios pueden encontrar errores como "No hay ningún encabezado "Access-Control-Allow-Origin" en el recurso solicitado.</span><span class="sxs-lookup"><span data-stu-id="e5ead-228">If Cross-Origin Resource Sharing (CORS) is enabled, users may encounter errors like "No 'Access-Control-Allow-Origin' header is present on the requested resource.</span></span> <span data-ttu-id="e5ead-229">Por lo tanto, no se permite el acceso al origen 'null'".</span><span class="sxs-lookup"><span data-stu-id="e5ead-229">Origin 'null' is therefore not allowed access".</span></span> <span data-ttu-id="e5ead-230">Para resolver el problema, coloque el archivo HTML en la carpeta donde está instalado el Portal (de forma predeterminada, debe ser `%SystemDrive%\Program Files\Skype for Business 2015 CQD\CQD)` .</span><span class="sxs-lookup"><span data-stu-id="e5ead-230">To resolve the issue, place the HTML file under the folder where the Portal is installed (by default, it should be `%SystemDrive%\Program Files\Skype for Business 2015 CQD\CQD)`.</span></span> <span data-ttu-id="e5ead-231">A continuación, obtenga acceso al html a través de cualquier explorador con la dirección  `http://<servername>/cqd/<html_file_name>` URL.</span><span class="sxs-lookup"><span data-stu-id="e5ead-231">Then access the html through any browser with the URL  `http://<servername>/cqd/<html_file_name>`.</span></span> <span data-ttu-id="e5ead-232">(La dirección URL predeterminada para el panel CQD local es  `http://<servername>/cqd.` )</span><span class="sxs-lookup"><span data-stu-id="e5ead-232">(The default URL for local CQD dashboard is  `http://<servername>/cqd.`)</span></span> 

### <a name="appendix-a"></a><span data-ttu-id="e5ead-233">Apéndice A</span><span class="sxs-lookup"><span data-stu-id="e5ead-233">Appendix A</span></span>

<span data-ttu-id="e5ead-234">Código HTML para el ejemplo 3 (ejemplo de cuadro de mandos):</span><span class="sxs-lookup"><span data-stu-id="e5ead-234">HTML code for Example 3 (Scorecard sample):</span></span>

```html
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
