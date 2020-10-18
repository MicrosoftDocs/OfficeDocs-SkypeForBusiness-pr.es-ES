---
title: 'Lync Server 2013: usar informes de supervisión'
description: 'Lync Server 2013: usar informes de supervisión.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using Monitoring Reports
ms:assetid: 733577d0-c70f-4c70-ab7b-59b89fb495a8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558662(v=OCS.15)
ms:contentKeyID: 48184480
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6e19b266e0580a89b814e80982c5f4ff2146ec01
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48580316"
---
# <a name="using-monitoring-reports-in-lync-server-2013"></a><span data-ttu-id="a2f74-103">Uso de informes de supervisión en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a2f74-103">Using Monitoring Reports in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a2f74-104">_**Última modificación del tema:** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="a2f74-104">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="a2f74-105">Lync Server 2013 incluye un conjunto de informes estándar que publica Microsoft SQL Server Reporting Service.</span><span class="sxs-lookup"><span data-stu-id="a2f74-105">Lync Server 2013 includes a set of standard reports that are published by Microsoft SQL Server Reporting Service.</span></span> <span data-ttu-id="a2f74-106">Estos informes, a los que se puede acceder con un explorador web, proporcionan información de uso, diagnóstico de llamadas y calidad de medios, basada en la información del registro detallado de llamadas (CDR) y la calidad de la experiencia (QoE) almacenada en las bases de datos de CDR y QoE.</span><span class="sxs-lookup"><span data-stu-id="a2f74-106">These reports, which are accessible by using a web browser, provide usage, call diagnostic information, and media quality information, all based on call detail recording (CDR) and Quality of Experience (QoE) records stored in the CDR and QoE databases.</span></span>

<span data-ttu-id="a2f74-107">Para poder usar estos informes, debe instalar los informes de supervisión en un equipo que ejecute una instancia de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="a2f74-107">In order to use these reports, you must install Monitoring Reports on a computer that is running an instance of the SQL Server.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="a2f74-108">En esta sección</span><span class="sxs-lookup"><span data-stu-id="a2f74-108">In This Section</span></span>

  - <span data-ttu-id="a2f74-109">[Uso del panel de supervisión en Lync Server 2013](lync-server-2013-using-the-monitoring-dashboard.md)     Proporciona a los administradores una introducción rápida de la salud del sistema y el uso del sistema.</span><span class="sxs-lookup"><span data-stu-id="a2f74-109">[Using the Monitoring Dashboard in Lync Server 2013](lync-server-2013-using-the-monitoring-dashboard.md)   Provides administrators with a quick overview of their system health and system usage.</span></span>

  - <span data-ttu-id="a2f74-110">[Informes de uso del sistema en Lync Server 2013](lync-server-2013-system-usage-reports.md)     Proporciona información sobre el uso del sistema según los datos CDR recopilados por Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a2f74-110">[System usage reports in Lync Server 2013](lync-server-2013-system-usage-reports.md)   Provides system usage information based on CDR data collected by Lync Server.</span></span>

  - <span data-ttu-id="a2f74-111">[Informes de diagnósticos de llamadas (por usuario) en Lync Server 2013](lync-server-2013-call-diagnostic-reports-per-user.md)     Proporciona información por usuario sobre sesiones de conferencia y de punto a punto con errores.</span><span class="sxs-lookup"><span data-stu-id="a2f74-111">[Call Diagnostic Reports (per user) in Lync Server 2013](lync-server-2013-call-diagnostic-reports-per-user.md)   Provides per-user information about failed peer-to-peer and conferencing sessions.</span></span>

  - <span data-ttu-id="a2f74-112">[Informes de diagnósticos de llamadas en Lync Server 2013](lync-server-2013-call-diagnostic-reports.md)     Proporciona información de Resumen y datos de diagnóstico para sesiones de punto a punto y de conferencia en las que se han producido errores.</span><span class="sxs-lookup"><span data-stu-id="a2f74-112">[Call Diagnostic Reports in Lync Server 2013](lync-server-2013-call-diagnostic-reports.md)   Provides summary information and diagnostic data for failed peer-to-peer and conferencing sessions.</span></span>

  - <span data-ttu-id="a2f74-113">[Informes de diagnóstico de calidad de medios en Lync Server 2013](lync-server-2013-media-quality-diagnostic-reports.md)     Proporciona información sobre la calidad de las llamadas, así como información de diagnóstico y solución de problemas para las llamadas fallidas.</span><span class="sxs-lookup"><span data-stu-id="a2f74-113">[Media Quality Diagnostic Reports in Lync Server 2013](lync-server-2013-media-quality-diagnostic-reports.md)   Provides information about call quality as well as diagnostic and troubleshooting information for failed calls.</span></span>

</div>

<div>

## <a name="locating-records"></a><span data-ttu-id="a2f74-114">Localización de registros</span><span class="sxs-lookup"><span data-stu-id="a2f74-114">Locating Records</span></span>

<span data-ttu-id="a2f74-p102">Los informes de supervisión muestran únicamente un número limitado de registros en pantalla de cada vez. El número de registros que aparece en una pantalla varía en función del informe. Para ver los registros no reflejados en pantalla en un momento dado, se pueden usar los controles habituales para ir hacia delante o hacia atrás, que encontrará en la barra de herramientas de todos los informes y que le permitirán avanzar por los datos de página en página. También se puede ir rápidamente a la primera o a la última página del conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="a2f74-p102">Monitoring Reports only show a limited number of records on the screen at any one time. The actual number of records displayed on a screen varies depending on the report. To view the records that are not currently shown on the screen you can use the standard forward and backward control (found on each report’s toolbar) that enable you to page through the data. You can also quickly jump to the first page or the last page of the dataset.</span></span>

<span data-ttu-id="a2f74-119">Además de estos controles, también se puede ir a cualquier página del conjunto de datos escribiendo el número de página en el cuadro **Página actual** y presionando la tecla ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="a2f74-119">In addition to using the forward and backward controls, you can also jump to any page in the dataset simply by typing the page number in the **Current Page** box, and then press ENTER.</span></span>

<span data-ttu-id="a2f74-p103">Además de poder avanzar por los datos de página en página, todos los informes incluyen también la capacidad limitada de buscar registros. Para buscar registros según un valor determinado, escriba dicho valor en el cuadro **Buscar** y haga clic en **Buscar**. El informe empieza a buscar en los datos y se detiene la primera vez que aparezca el valor escrito en **Buscar**. Para encontrar el siguiente registro que cumpla con los criterios de búsqueda, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="a2f74-p103">In addition to providing the ability to page through the data, each report also includes the limited ability to find records. To find records based on a given value, type that value into the **Find** box, and then click **Find**. The report begins searching through the data and stops on the first instance of the value that you entered in the **Find** box. To find the next record that meets the search criteria, click **Next**.</span></span>

<span data-ttu-id="a2f74-p104">Tal y como se ha mencionado, los informes de supervisión ofrecen únicamente las funciones de búsqueda más básicas; así, por ejemplo, no se puede especificar el campo en el que buscar el valor, sino que se buscan automáticamente los valores coincidentes en todos los campos de todos los registros. Tampoco se pueden usar caracteres comodín en las búsquedas y en todos los casos se buscarán valores parciales. Esto quiere decir que, si se busca 111, la búsqueda detectará no solo el valor 111, sino también los valores 11100, 811, 3112, 611A5B y cualquier otro campo que incluya el valor 111.</span><span class="sxs-lookup"><span data-stu-id="a2f74-p104">As noted, the Monitoring Reports provide only the most basic search functions. For example, you cannot specify which field the value should be found in. The search mechanism automatically searches for matching values in every field in every record. You cannot use wildcards in your searches, and all searches look for partial values. That means that if you search for 111 the search returns the value 111 along with the values 11100, 811, 3112, 611A5B, and any other fields that include the value 111 anywhere within that field.</span></span>

<span data-ttu-id="a2f74-p105">Cada informe está configurado para mostrar un número de registros predeterminado. Por ejemplo, el informe de registro de usuario refleja de manera predeterminada las actividades de registro del usuario de la última semana. Algunas veces esto se traduce en un informe que no muestra registros, lo que significa que no se han producido registros de usuario en la última semana. Si se muestra el mensaje “Ningún resultado coincide con los filtros del informe”, pruebe a cambiar los valores de filtro (por ejemplo, cambie el período de tiempo al mes pasado, en lugar de a la semana pasada) y vuelva a ejecutar la consulta. Para obtener información detallada, consulte "Filtrar datos" más adelante en esta sección.</span><span class="sxs-lookup"><span data-stu-id="a2f74-p105">Each report is configured to show a default set of records. For example, by default the User Registration Report shows user registration activities for the past week. In some cases, this might result in a report that returns no records. In this case, it means that no user registrations have taken place in the past week. If you see the message “No results match the report filters,” try changing the filter values (for example, change the time period to the past month rather than the past week) and rerun the query. For details, see the "Filtering Data" section later in this topic.</span></span>

</div>

<div>

## <a name="filtering-data"></a><span data-ttu-id="a2f74-135">Filtrado de datos</span><span class="sxs-lookup"><span data-stu-id="a2f74-135">Filtering Data</span></span>

<span data-ttu-id="a2f74-p106">Probablemente en alguna ocasión quiera buscar en un subconjunto de registros únicamente (por ejemplo, solo las sesiones punto a punto frente a las sesiones punto a punto y las sesiones de conferencia juntas). De igual forma, otras veces necesitará reducir el número de registros que la búsqueda devuelve. Un informe solo puede mostrar 1.000 registros en un conjunto de datos de manera predeterminada. Para abordar esta situación, la mayoría de los informes incluye una serie de opciones de filtrado. Por ejemplo, si quiere ver únicamente los registros correspondientes al período de tiempo comprendido entre el 1 y el 15 de de enero de 2011, puede especificar la fecha 1 de enero de 2011 en el cuadro **Desde** y la fecha 15 de enero de 2011 en el cuadro **Hasta**. Si después hace clic en **Ver informe**, los datos obtenidos se limitarán a las actividades que ocurrieron entre el 1 y el 15 de enero de 2011.</span><span class="sxs-lookup"><span data-stu-id="a2f74-p106">There will likely be times when you want to look at only a subset of records. For example, only peer-to-peer sessions as opposed to both peer-to-peer sessions and conference sessions. Likewise, there will be times when you need to reduce the number of records that are returned. By default, a report can only display the first 1,000 records in a data set. To address these issues, most reports include a number of filtering options. For example, if you want to view only records for the time period January 1, 2011 through January 15, 2011, you can enter January 1, 2011 in the **From** box and January 15, 2011 in the **To** box. If you then click **View Report**, the returned data will be limited to activities that took place between January 1, 2011 and January 15, 2011.</span></span>

<span data-ttu-id="a2f74-p107">Los filtros de que disponga variarán en función del informe que esté viendo. Para obtener información detallada sobre un informe en particular, consulte el tema de ayuda correspondiente.</span><span class="sxs-lookup"><span data-stu-id="a2f74-p107">The filters available to you vary depending on the report that you are viewing. For details about a specific report, see the help topic for that report.</span></span>

</div>

<div>

## <a name="exporting-data"></a><span data-ttu-id="a2f74-145">Exportación de datos</span><span class="sxs-lookup"><span data-stu-id="a2f74-145">Exporting Data</span></span>

<span data-ttu-id="a2f74-p108">Los informes de supervisión ofrecen al menos dos modos distintos de exportar los datos de un informe. Puede usar la opción **Exportar** de la barra de herramientas que aparece en la parte superior de cada informe. Para usar esta opción, seleccione el formato de exportación que desee de la lista desplegable **Seleccionar un formato**, en la que verá los siguientes formatos:</span><span class="sxs-lookup"><span data-stu-id="a2f74-p108">The Monitoring Reports provide at least two different ways to export the data included in a report. You can use the **Export** option in the toolbar that appears at the top of each report. To use this option, select the desired export format from the **Select a format** drop-down list. The following formats are available to you:</span></span>

  - <span data-ttu-id="a2f74-150">Archivo XML con datos de informe</span><span class="sxs-lookup"><span data-stu-id="a2f74-150">XML file with report data</span></span>

  - <span data-ttu-id="a2f74-151">Archivo CSV (delimitado por comas)</span><span class="sxs-lookup"><span data-stu-id="a2f74-151">CSV (comma delimited)</span></span>

  - <span data-ttu-id="a2f74-152">Archivo de Acrobat (PDF)</span><span class="sxs-lookup"><span data-stu-id="a2f74-152">Acrobat (PDF) file</span></span>

  - <span data-ttu-id="a2f74-153">Archivo MHTML (archivo web)</span><span class="sxs-lookup"><span data-stu-id="a2f74-153">MHTML (web archive)</span></span>

  - <span data-ttu-id="a2f74-154">Excel</span><span class="sxs-lookup"><span data-stu-id="a2f74-154">Excel</span></span>

  - <span data-ttu-id="a2f74-155">Archivo TIFF</span><span class="sxs-lookup"><span data-stu-id="a2f74-155">TIFF file</span></span>

  - <span data-ttu-id="a2f74-156">Word</span><span class="sxs-lookup"><span data-stu-id="a2f74-156">Word</span></span>

<span data-ttu-id="a2f74-p109">Una vez seleccionado el formato, haga clic en **Exportar**. Cuando se abra el cuadro de diálogo **Descarga de archivos**, haga clic en **Guardar**. En el cuadro de diálogo **Guardar como**, seleccione una carpeta de destino, escriba un nombre de archivo y haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="a2f74-p109">After selecting a format, click **Export**. When the **File Download** dialog box appears, click **Save**. In the **Save As** dialog box, select a destination folder, enter a file name, and then click **Save**.</span></span>

<span data-ttu-id="a2f74-p110">Si tiene Microsoft OneNote instalado, también puede optar por copiar los datos del informe a OneNote. Para ello, haga clic con el botón secundario en el botón **Ver informe** en la barra de tareas. En el cuadro de diálogo **Seleccionar la ubicación en OneNote**, seleccione la sección de OneNote en la que quiera copiar los datos y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a2f74-p110">If you have Microsoft OneNote installed, you can also copy the report data to OneNote. To do this, right-click the **View Report** button on the toolbar. In the **Select Location in OneNote** dialog box select the section in OneNote where you want to copy the data, and then click **OK**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

