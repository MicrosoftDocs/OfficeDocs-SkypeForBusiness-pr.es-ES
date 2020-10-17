---
title: 'Lync Server 2013: Descripción de los informes creados por el analizador de procedimientos recomendados'
description: 'Lync Server 2013: Descripción de los informes creados por el analizador de procedimientos recomendados.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Understanding reports created by Best Practices Analyzer
ms:assetid: 1386dd6c-7f3e-4da9-905b-cef1468bf14a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg591344(v=OCS.15)
ms:contentKeyID: 48183471
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5fbb84cdffe6e6e6f079c2d72aba4799f5538776
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542376"
---
# <a name="understanding-reports-created-by-best-practices-analyzer-in-lync-server-2013"></a><span data-ttu-id="8a60c-103">Información sobre los informes creados por el analizador de procedimientos recomendados en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8a60c-103">Understanding reports created by Best Practices Analyzer in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8a60c-104">_**Última modificación del tema:** 2012-10-10_</span><span class="sxs-lookup"><span data-stu-id="8a60c-104">_**Topic Last Modified:** 2012-10-10_</span></span>

<span data-ttu-id="8a60c-p101">El Analizador de procedimientos recomendados ofrece varios tipos de informes organizados que se organizan para facilitar el análisis y la resolución de problemas. El Analizador de procedimientos recomendados identifica problemas como, por ejemplo, errores o advertencias, entre otros.</span><span class="sxs-lookup"><span data-stu-id="8a60c-p101">Best Practices Analyzer provides multiple types of reports that are organized to facilitate the analysis and resolution of issues. Best Practices Analyzer identifies issues such as errors, warnings, and other information.</span></span>

<div>

## <a name="reports"></a><span data-ttu-id="8a60c-107">Informes</span><span class="sxs-lookup"><span data-stu-id="8a60c-107">Reports</span></span>

<span data-ttu-id="8a60c-108">Puede tener acceso a los resultados del análisis viendo consultando cada uno de los informes siguientes:</span><span class="sxs-lookup"><span data-stu-id="8a60c-108">You can access the results of a scan by viewing each of the following reports:</span></span>

  - <span data-ttu-id="8a60c-109">**Enumerar informes**     Los informes de lista se organizan según criterios específicos.</span><span class="sxs-lookup"><span data-stu-id="8a60c-109">**List reports**   List reports are organized by specific criteria.</span></span> <span data-ttu-id="8a60c-110">Puede organizar los resultados por clase, gravedad o problema.</span><span class="sxs-lookup"><span data-stu-id="8a60c-110">You can arrange the results by class, severity, or issue.</span></span> <span data-ttu-id="8a60c-111">Por ejemplo, si organiza los resultados por clase, los problemas relacionados con los Directivos se incluyen en la sección Directivos del informe.</span><span class="sxs-lookup"><span data-stu-id="8a60c-111">For example, if you organize results by class, issues related to Directors are included under the Directors section of the report.</span></span> <span data-ttu-id="8a60c-112">Puede ver todos los problemas o solo los elementos informativos.</span><span class="sxs-lookup"><span data-stu-id="8a60c-112">You can view all of the issues, or just the informational items.</span></span> <span data-ttu-id="8a60c-113">Puede ver un informe de la lista con elementos específicos como, por ejemplo, la memoria.</span><span class="sxs-lookup"><span data-stu-id="8a60c-113">You can search a list report for specific items, such as memory.</span></span> <span data-ttu-id="8a60c-114">También puede imprimir el informe o exportarlo.</span><span class="sxs-lookup"><span data-stu-id="8a60c-114">You can also print the report or export it.</span></span>

  - <span data-ttu-id="8a60c-115">**Informes**     de árbol Los informes de árbol están organizados por las reglas que se usan para ejecutar el análisis y otras opciones especificadas en el momento en que se ejecutó el análisis.</span><span class="sxs-lookup"><span data-stu-id="8a60c-115">**Tree reports**   Tree reports are organized by the rules that are used to run the scan and other options that you specified at the time the scan was run.</span></span> <span data-ttu-id="8a60c-116">Por ejemplo, los problemas relacionados con la topología de pruebas se incluyen en la sección Topología de pruebas del informe.</span><span class="sxs-lookup"><span data-stu-id="8a60c-116">For example, issues related to the Test Topology rules are included under the Test Topology section of the report.</span></span> <span data-ttu-id="8a60c-117">Puede ver los detalles de todos los problemas o solo un resumen de los problemas.</span><span class="sxs-lookup"><span data-stu-id="8a60c-117">You can view the details of all the issues, or just a summary of the issues.</span></span> <span data-ttu-id="8a60c-118">Puede buscar un informe ramificado con elementos específicos como, por ejemplo, la memoria.</span><span class="sxs-lookup"><span data-stu-id="8a60c-118">You can search a tree report for specific items, such as memory.</span></span> <span data-ttu-id="8a60c-119">También puede imprimir el informe o exportarlo.</span><span class="sxs-lookup"><span data-stu-id="8a60c-119">You can also print the report or export it.</span></span>

  - <span data-ttu-id="8a60c-120">**Otros informes**     Los elementos de otros informes incluyen el registro en tiempo de ejecución de las tareas incluidas en el examen.</span><span class="sxs-lookup"><span data-stu-id="8a60c-120">**Other reports**   Items in other reports include the run-time log of tasks that were included in the scan.</span></span> <span data-ttu-id="8a60c-121">Puede buscar elementos específicos de otros informes como, por ejemplo, la memoria.</span><span class="sxs-lookup"><span data-stu-id="8a60c-121">You can search the items in other reports for specific items, such as memory.</span></span> <span data-ttu-id="8a60c-122">También puede imprimir el informe o exportarlo.</span><span class="sxs-lookup"><span data-stu-id="8a60c-122">You can also print the report or export it.</span></span>

</div>

<div>

## <a name="issues"></a><span data-ttu-id="8a60c-123">Problemas</span><span class="sxs-lookup"><span data-stu-id="8a60c-123">Issues</span></span>

<span data-ttu-id="8a60c-124">Los informes que genera el Analizador de procedimientos recomendados indican que existen problemas específicos identificados durante el análisis del entorno, entre los que se incluyen los siguientes:</span><span class="sxs-lookup"><span data-stu-id="8a60c-124">The reports generated by Best Practices Analyzer indicate specific issues that are identified during the scan of your environment, including following types of issues:</span></span>

  - <span data-ttu-id="8a60c-125">**Errores**     Problemas críticos que requieren que se realice un cambio en el entorno.</span><span class="sxs-lookup"><span data-stu-id="8a60c-125">**Errors**   Critical issues that require you to make a change in your environment.</span></span> <span data-ttu-id="8a60c-126">Por ejemplo, si los componentes principales de Lync Server 2013 no están instalados, se registra un error.</span><span class="sxs-lookup"><span data-stu-id="8a60c-126">For example, if Lync Server 2013 Core Components are not installed, an error is logged.</span></span>

    <span data-ttu-id="8a60c-p106">Los problemas clasificados como errores se identifican en el informe con una X de color rojo. Los errores se muestran en la pestaña **Todos los problemas** de la vista **Informes de la lista** y en la pestaña **Vista detallada** y **Vista reducida** de la vista **Informes ramificados**. Si desea que no se muestre un error específico en un informe, puede especificar que no se muestre una instancia o todas las instancias de dicho error en el informe. De este modo, el error solo se mostrará en la pestaña **Elementos ocultos** de la vista **Otros informes** a menos que modifique la configuración y especifique que se muestre el error en el informe.</span><span class="sxs-lookup"><span data-stu-id="8a60c-p106">Issues that are classified as errors are identified in the report by a red X symbol. Errors are displayed on the **All Issues** tab of the **List Reports** view, and on the **Detailed View** tab and the **Summary View** tab of the **Tree Reports** view. If you do not want to see a specific error in a report, you can specify that the error not be shown for a single instance or for all instances of that error in the report. The error is then displayed only on the **Hidden Items** tab of the **Other Reports** view, unless you change the setting and specify that the error be displayed in the report.</span></span>

  - <span data-ttu-id="8a60c-131">**Advertencias**     Problemas que no son coherentes con la implementación de un procedimiento recomendado.</span><span class="sxs-lookup"><span data-stu-id="8a60c-131">**Warnings**   Issues that are not consistent with the implementation of a best practice.</span></span> <span data-ttu-id="8a60c-132">Esto puede indicar que es necesario realizar un cambio en el entorno, o no.</span><span class="sxs-lookup"><span data-stu-id="8a60c-132">This may or may not indicate the need for a change in your environment.</span></span> <span data-ttu-id="8a60c-133">El problema puede ser un problema conocido con una configuración específica que no es necesario cambiar.</span><span class="sxs-lookup"><span data-stu-id="8a60c-133">The issue could be a known issue with a specific setting that you do not need to change.</span></span> <span data-ttu-id="8a60c-134">Por ejemplo, los servicios que no se inician en un servidor se registran como advertencias.</span><span class="sxs-lookup"><span data-stu-id="8a60c-134">For example, services that are not started on a server are logged as warnings.</span></span>

    <span data-ttu-id="8a60c-p108">Los problemas clasificados como advertencias se identifican en el informe con un signo de advertencia triangular de color amarillo. Las advertencias se muestran en la pestaña **Todos los problemas** de la vista **Informes de la lista**, así como en la pestaña **Vista detallada** y **Vista reducida** de la vista **Informes ramificados**. Si desea que no se muestre un error específico en un informe, puede especificar que no se muestre una instancia o todas las instancias de dicho error en el informe. De este modo, la advertencia solo se mostrará en la pestaña **Elementos ocultos** de la vista **Otros informes** a menos que modifique la configuración y especifique que se muestre el error en el informe.</span><span class="sxs-lookup"><span data-stu-id="8a60c-p108">Issues that are classified as warnings are identified in the report by a triangular yellow warning symbol. Warnings are displayed on the **All Issues** tab of the **List Reports** view, as well as on the **Detailed View** tab and the **Summary View** tab of the **Tree Reports** view. If you do not want to see a specific error in a report, you can specify that the error not be shown for a single instance or for all instances of that error in the report. The warning is then displayed only on the **Hidden Items** tab of the **Other Reports** view, unless you change the setting and specify that the warning be displayed in the report.</span></span>

  - <span data-ttu-id="8a60c-139">**Información sobre**     Incluye todos los problemas que no se clasifican como errores o advertencias.</span><span class="sxs-lookup"><span data-stu-id="8a60c-139">**Information**   Includes all issues that are not classified as errors or warnings.</span></span> <span data-ttu-id="8a60c-140">Por ejemplo, el número de objetos de servidor de Lync Server 2013 Standard Edition en servicios de dominio de Active Directory se clasifica como un problema de información.</span><span class="sxs-lookup"><span data-stu-id="8a60c-140">For example, the number of Lync Server 2013 Standard Edition server objects in Active Directory Domain Services is classified as an information issue.</span></span>

    <span data-ttu-id="8a60c-141">Los problemas informativos se muestran en la pestaña **Todos los problemas** de la vista **Informes de la lista** y en la pestaña **Vista detallada** de la vista **Informes ramificados**.</span><span class="sxs-lookup"><span data-stu-id="8a60c-141">Information issues are displayed on the **All Issues** tab of the **List Reports** view, and on the **Detailed View** tab of the **Tree Reports** view.</span></span>

<span data-ttu-id="8a60c-142">El analizador de procedimientos recomendados de Lync Server 2013 no realiza cambios en el entorno para resolver problemas.</span><span class="sxs-lookup"><span data-stu-id="8a60c-142">The Lync Server 2013, Best Practices Analyzer does not make changes to your environment to resolve issues.</span></span> <span data-ttu-id="8a60c-143">El análisis solo detecta problemas potenciales y ofrece informes que contienen información sobre cómo resolver cada uno de los problemas.</span><span class="sxs-lookup"><span data-stu-id="8a60c-143">The scan only detects potential issues and provides reports that contain information about how to resolve each issue.</span></span>

<span data-ttu-id="8a60c-p111">Si hace clic en un problema, se mostrarán explicaciones y opciones para dicho problema. A continuación, podrá llevar a cabo uno de los procedimientos siguientes:</span><span class="sxs-lookup"><span data-stu-id="8a60c-p111">If you click an issue, an explanation and some options are displayed for specific issues. Then, you can do any of the following:</span></span>

  - <span data-ttu-id="8a60c-146">Buscar información detallada sobre el problema y sobre cómo resolverlo.</span><span class="sxs-lookup"><span data-stu-id="8a60c-146">Find more detailed information about the issue, and how to resolve it.</span></span>

  - <span data-ttu-id="8a60c-147">Detener la visualización de problemas en los informes:</span><span class="sxs-lookup"><span data-stu-id="8a60c-147">Stop showing issues in reports:</span></span>

      - <span data-ttu-id="8a60c-148">Detener la visualización de problemas para la instancia seleccionada.</span><span class="sxs-lookup"><span data-stu-id="8a60c-148">Stop showing issues for the selected instance.</span></span>

      - <span data-ttu-id="8a60c-149">Detener la visualización de problemas para todas las instancias del problema.</span><span class="sxs-lookup"><span data-stu-id="8a60c-149">Stop showing issues for all instances of that issue.</span></span>

    <span data-ttu-id="8a60c-p112">Para ver los problemas cuya visualización en los informes haya detenido, vaya a la pestaña **Elementos ocultos** de la vista **Otros informes**. Desde ahí podrá especificar que se vuelvan a mostrar dichos problemas en los informes.</span><span class="sxs-lookup"><span data-stu-id="8a60c-p112">To see the issues you have stopped showing in reports, go to the **Hidden Items** tab of the **Other Reports** view. From there, you can specify to start showing issues in reports again.</span></span>

<span data-ttu-id="8a60c-152">Para obtener más información sobre cómo resolver problemas específicos, consulte [análisis y resolución de problemas identificados por Best Practices Analyzer en Lync Server 2013](lync-server-2013-analyzing-and-resolving-issues-identified-by-best-practices-analyzer.md).</span><span class="sxs-lookup"><span data-stu-id="8a60c-152">For details about resolving specific issues, see [Analyzing and resolving issues identified by Best Practices Analyzer in Lync Server 2013](lync-server-2013-analyzing-and-resolving-issues-identified-by-best-practices-analyzer.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>
