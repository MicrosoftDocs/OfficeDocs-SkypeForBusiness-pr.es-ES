---
title: 'Lync Server 2013: visualización de informes desde Best Practices Analyzer'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Viewing reports from Best Practices Analyzer
ms:assetid: 7217a47b-36b1-4923-81ea-df754cff29bb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg607690(v=OCS.15)
ms:contentKeyID: 48184465
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fb2c229d683ecd0dcf4fee94b456514527226152
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34850059"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="viewing-reports-from-best-practices-analyzer-in-lync-server-2013"></a><span data-ttu-id="8cadc-102">Ver informes de Best Practices Analyzer en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8cadc-102">Viewing reports from Best Practices Analyzer in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8cadc-103">_**Última modificación del tema:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="8cadc-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="8cadc-104">Al usar el analizador de procedimientos recomendados para explorar su entorno, especifica un nombre para el examen.</span><span class="sxs-lookup"><span data-stu-id="8cadc-104">When you use Best Practices Analyzer to scan your environment, you specify a name for the scan.</span></span> <span data-ttu-id="8cadc-105">Después de que el analizador de procedimientos recomendados complete un examen, almacena los resultados del análisis en informes y los guarda bajo el nombre de la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="8cadc-105">After Best Practices Analyzer completes a scan, it stores the scan results in reports and saves them under the name of the scan.</span></span> <span data-ttu-id="8cadc-106">Una vez finalizado el análisis, puede ver los informes generados para ese análisis haciendo clic en **ver un informe de este examen de procedimientos recomendados** directamente desde la página **análisis finalizado** .</span><span class="sxs-lookup"><span data-stu-id="8cadc-106">Upon completion of the scan, you can view the reports generated for that scan by clicking **View a report of this Best Practices scan** directly from the **Scanning Completed** page.</span></span> <span data-ttu-id="8cadc-107">También puede ver los informes de ese análisis o análisis anteriores más adelante.</span><span class="sxs-lookup"><span data-stu-id="8cadc-107">You can also view the reports from that scan or previous scans at a later time.</span></span> <span data-ttu-id="8cadc-108">Puede ver informes en el equipo local en el que se ejecutó el examen, importar resultados del examen de otro equipo o exportar resultados del examen para ver los informes en otro equipo en el que está instalado Best Practices Analyzer.</span><span class="sxs-lookup"><span data-stu-id="8cadc-108">You can view reports on the local computer on which the scan was run, import scan results from another computer, or export scan results to view the reports on another computer on which Best Practices Analyzer is installed.</span></span>

<span data-ttu-id="8cadc-109">Los resultados del examen se presentan en los siguientes tipos de informes:</span><span class="sxs-lookup"><span data-stu-id="8cadc-109">Scan results are presented in the following types of reports:</span></span>

  - <span data-ttu-id="8cadc-110">Informes de listas</span><span class="sxs-lookup"><span data-stu-id="8cadc-110">List reports</span></span>

  - <span data-ttu-id="8cadc-111">Informes de árbol</span><span class="sxs-lookup"><span data-stu-id="8cadc-111">Tree reports</span></span>

  - <span data-ttu-id="8cadc-112">Otros informes</span><span class="sxs-lookup"><span data-stu-id="8cadc-112">Other reports</span></span>

<span data-ttu-id="8cadc-113">Estos informes incluyen errores, advertencias y otra información.</span><span class="sxs-lookup"><span data-stu-id="8cadc-113">These reports include errors, warnings, and other information.</span></span> <span data-ttu-id="8cadc-114">Para obtener más información sobre cada uno de estos tipos de informes y problemas, vea información sobre los [informes creados por Best Practices Analyzer en Lync Server 2013](lync-server-2013-understanding-reports-created-by-best-practices-analyzer.md).</span><span class="sxs-lookup"><span data-stu-id="8cadc-114">For details about each of these types of reports and issues, see [Understanding reports created by Best Practices Analyzer in Lync Server 2013](lync-server-2013-understanding-reports-created-by-best-practices-analyzer.md).</span></span>

<span data-ttu-id="8cadc-115">Use el procedimiento siguiente para ver los resultados del examen generados previamente por el analizador de procedimientos recomendados.</span><span class="sxs-lookup"><span data-stu-id="8cadc-115">Use the following procedure to view scan results previously generated by Best Practices Analyzer.</span></span>

<div>

## <a name="to-view-reports-from-a-previous-scan"></a><span data-ttu-id="8cadc-116">Para ver los informes de un examen anterior</span><span class="sxs-lookup"><span data-stu-id="8cadc-116">To view reports from a previous scan</span></span>

1.  <span data-ttu-id="8cadc-117">Inicie sesión en un equipo en el que se instale Best Practices Analyzer con una cuenta que sea miembro de la cuenta de usuario local.</span><span class="sxs-lookup"><span data-stu-id="8cadc-117">Log on to a computer on which Best Practices Analyzer is installed using an account that is a member of the local User account.</span></span>
    
    > [!NOTE]  
    > <span data-ttu-id="8cadc-118">Puede ver los resultados de un análisis con una cuenta que sea miembro del grupo de administradores locales, pero no puede ejecutar un examen a menos que tenga los derechos de usuario y permisos adecuados.</span><span class="sxs-lookup"><span data-stu-id="8cadc-118">You can view the results of a scan using an account that is a member of the local Administrators group, but you cannot run a scan unless you have appropriate user rights and permissions.</span></span> <span data-ttu-id="8cadc-119">Para obtener más información, consulte pertenencias <A href="lync-server-2013-group-memberships-and-user-rights-requirements-for-best-practices-analyzer.md">a grupos y requisitos de derechos de usuario para Best Practices Analyzer en Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="8cadc-119">For details, see <A href="lync-server-2013-group-memberships-and-user-rights-requirements-for-best-practices-analyzer.md">Group memberships and user rights requirements for Best Practices Analyzer in Lync Server 2013</A>.</span></span>

2.  <span data-ttu-id="8cadc-120">Haga clic en **Inicio**, seleccione **todos los programas**, haga clic en **Microsoft Lync Server 2013**y, a continuación, haga clic en **Best Practices Analyzer**.</span><span class="sxs-lookup"><span data-stu-id="8cadc-120">Click **Start**, point to **All Programs**, click **Microsoft Lync Server 2013**, and then click **Best Practices Analyzer**.</span></span>

3.  <span data-ttu-id="8cadc-121">En la pantalla de **bienvenida** , haga clic en **seleccionar los resultados del análisis que desea ver**.</span><span class="sxs-lookup"><span data-stu-id="8cadc-121">On the **Welcome** screen, click **Select the scan results to view**.</span></span>

4.  <span data-ttu-id="8cadc-122">En la página **seleccionar el examen de procedimientos recomendados para ver** , realice una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="8cadc-122">On the **Select a Best Practices Scan to View** page, do one of the following:</span></span>
    
      - <span data-ttu-id="8cadc-123">Para ver los informes de la lista de resultados de exámenes almacenados de forma local, haga clic en el nombre de la exploración y, a continuación, haga clic en **ver un informe de este examen**.</span><span class="sxs-lookup"><span data-stu-id="8cadc-123">To view reports from the list of locally stored scan results, click the name of scan, and then click **View a report of this scan**.</span></span>
        
        > [!NOTE]  
        > <span data-ttu-id="8cadc-124">El Best Practices Analyzer crea la lista de archivos locales de la &lt;carpeta&gt;\\systemDrive Documents\\&lt;and&gt;Settings usuario \Datos de Data\Microsoft\RtcBPA.</span><span class="sxs-lookup"><span data-stu-id="8cadc-124">The Best Practices Analyzer creates the list of local files from the folder &lt;systemDrive&gt;\\Documents and Settings\\&lt;user&gt;\Application Data\Microsoft\RtcBPA.</span></span>
    
      - <span data-ttu-id="8cadc-125">Para ver los informes de los resultados de un examen guardado en otra ubicación, haga clic en **importar examen**, busque el archivo que contiene los resultados del análisis y, a continuación, haga clic en **abrir**.</span><span class="sxs-lookup"><span data-stu-id="8cadc-125">To view reports for results of a scan that are stored at another location, click **Import scan**, locate the file containing the scan results, and then click **Open**.</span></span>
        
        > [!NOTE]  
        > <span data-ttu-id="8cadc-126">Si la versión del analizador de procedimientos recomendados en este equipo no coincide con la versión que se usó para recopilar los datos en el archivo importado, es posible que la herramienta del equipo vuelva a analizar el archivo después de importarlo.</span><span class="sxs-lookup"><span data-stu-id="8cadc-126">If the version of Best Practices Analyzer on this computer does not match the version that was used to collect the data in the imported file, the tool on your computer might analyze the file again, after it is imported.</span></span>

5.  <span data-ttu-id="8cadc-127">En la página **Ver informe de procedimientos recomendados** , realice una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="8cadc-127">On the **View Best Practices Report** page, do one of the following:</span></span>
    
      - <span data-ttu-id="8cadc-128">Para ver los informes en una lista organizada por componente de servidor, haga clic en **informes de lista**y, a continuación, haga clic en la pestaña **todos los problemas** o en la pestaña **elementos de información** .</span><span class="sxs-lookup"><span data-stu-id="8cadc-128">To view reports in a list organized by server component, click **List Reports**, and then click either the **All Issues** tab or the **Informational Items** tab.</span></span>
    
      - <span data-ttu-id="8cadc-129">Para ver los informes como una lista jerárquica organizada por tipos de resultados, haga clic en **informes de árbol**y, a continuación, haga clic en la pestaña **vista detallada** o en la pestaña **vista de Resumen** .</span><span class="sxs-lookup"><span data-stu-id="8cadc-129">To view reports as a hierarchical list organized by types of results, click **Tree Reports**, and then click either the **Detailed View** tab or the **Summary View** tab.</span></span>
    
      - <span data-ttu-id="8cadc-130">Para ver otros informes, haga clic en **otros informes**.</span><span class="sxs-lookup"><span data-stu-id="8cadc-130">To view other reports, click **Other Reports**.</span></span>
    
    > [!NOTE]  
    > <span data-ttu-id="8cadc-131">Para obtener más información sobre los informes del analizador de procedimientos recomendados y los problemas que identifican, consulte <A href="lync-server-2013-viewing-and-working-with-reports-created-by-best-practices-analyzer.md">ver y trabajar con informes creados por Best Practices Analyzer en Lync Server 2013</A> y <A href="lync-server-2013-analyzing-and-resolving-issues-identified-by-best-practices-analyzer.md">analizar y resolver los problemas identificados por los procedimientos recomendados. Analyzer en Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="8cadc-131">For details about the Best Practices Analyzer reports and the issues that they identify, see <A href="lync-server-2013-viewing-and-working-with-reports-created-by-best-practices-analyzer.md">Viewing and working with reports created by Best Practices Analyzer in Lync Server 2013</A> and <A href="lync-server-2013-analyzing-and-resolving-issues-identified-by-best-practices-analyzer.md">Analyzing and resolving issues identified by Best Practices Analyzer in Lync Server 2013</A>.</span></span>

</div>

</div>

</div>

</div>

</div>

