---
title: Uso del analizador de procedimientos recomendados para analizar la implementación en busca de posibles problemas
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using Best Practices Analyzer to scan your deployment for potential issues
ms:assetid: 09c84509-dc91-4e7b-882b-3c467b6b026d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg591343(v=OCS.15)
ms:contentKeyID: 48183359
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f620712404fffe8e46f8f2a6f066c6ffa7b77d74
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42212896"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="using-best-practices-analyzer-to-scan-your-lync-server-2013-deployment-for-potential-issues"></a><span data-ttu-id="7ba5d-102">Uso del analizador de procedimientos recomendados para examinar la implementación de Lync Server 2013 para detectar posibles problemas</span><span class="sxs-lookup"><span data-stu-id="7ba5d-102">Using Best Practices Analyzer to scan your Lync Server 2013 deployment for potential issues</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7ba5d-103">_**Última modificación del tema:** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="7ba5d-103">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="7ba5d-104">Para ejecutar un examen del Analizador de procedimientos recomendados, debe especificar lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="7ba5d-104">To run a Best Practices Analyzer scan, you must specify the following:</span></span>

  - <span data-ttu-id="7ba5d-105">**Credenciales**   para ejecutar un examen, debe iniciar sesión en un equipo en el que se haya instalado el analizador de procedimientos recomendados con una cuenta que sea miembro del grupo de administradores locales.</span><span class="sxs-lookup"><span data-stu-id="7ba5d-105">**Credentials**   To run a scan, you must log on to a computer on which Best Practices Analyzer is installed by using an account that is a member of the local Administrators group.</span></span> <span data-ttu-id="7ba5d-106">Además, tiene que iniciar sesión usando una cuenta de usuario que tenga los derechos de usuario y los permisos necesarios para ejecutar los exámenes adecuados o bien, debe especificar credenciales que tengan los derechos de usuario y permisos adecuados al ejecutar el Analizador de procedimientos recomendados.</span><span class="sxs-lookup"><span data-stu-id="7ba5d-106">Additionally, you need to log on by using a user account that has the user rights and permissions required to run the appropriate scans, or you must specify credentials that have the appropriate user rights and permissions when you run Best Practices Analyzer.</span></span> <span data-ttu-id="7ba5d-107">Para obtener más información, consulte [pertenencias a grupos y requisitos de derechos de usuario para el analizador de procedimientos recomendados en Lync Server 2013](lync-server-2013-group-memberships-and-user-rights-requirements-for-best-practices-analyzer.md).</span><span class="sxs-lookup"><span data-stu-id="7ba5d-107">For details, see [Group memberships and user rights requirements for Best Practices Analyzer in Lync Server 2013](lync-server-2013-group-memberships-and-user-rights-requirements-for-best-practices-analyzer.md).</span></span>

  - <span data-ttu-id="7ba5d-108">**Ámbito del análisis**   para especificar el ámbito del análisis, seleccione las categorías y los servidores que desee analizar.</span><span class="sxs-lookup"><span data-stu-id="7ba5d-108">**Scope of scan**   To specify the scope of the scan, select the categories and servers that you want to scan.</span></span> <span data-ttu-id="7ba5d-109">Puede seleccionar todas las categorías, una o varias categorías, o uno o más servidores dentro de una categoría específica en su entorno de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="7ba5d-109">You can select all categories, one or more categories, or one or more servers within a specific category in your Lync Server environment.</span></span>

  - <span data-ttu-id="7ba5d-110">**Tipo de análisis**   actualmente, el análisis de comprobación de estado es el único tipo de examen disponible (opción predeterminada).</span><span class="sxs-lookup"><span data-stu-id="7ba5d-110">**Type of scan**   Currently, the Health Check scan is the only type of scan available (selected by default).</span></span> <span data-ttu-id="7ba5d-111">El análisis de comprobación de estado genera un informe que incluye errores, advertencias y otra información para todos los servidores especificados en el ámbito.</span><span class="sxs-lookup"><span data-stu-id="7ba5d-111">The Health Check scan generates a report that includes errors, warnings, and other information for all servers specified in the scope.</span></span>

  - <span data-ttu-id="7ba5d-112">**Velocidad de red**   las opciones de velocidad de red incluyen Fast LAN (100 Mbps o más), LAN (10 Mbps), WAN rápida (1,5 Mbps) o WAN (64 kbps).</span><span class="sxs-lookup"><span data-stu-id="7ba5d-112">**Network speed**   Network speed options include Fast LAN (100 Mbps or more), LAN (10 Mbps), Fast WAN (1.5 Mbps), or WAN (64 kbps).</span></span> <span data-ttu-id="7ba5d-113">El tiempo estimado para completar el análisis se basa en esta configuración.</span><span class="sxs-lookup"><span data-stu-id="7ba5d-113">The estimated time to complete the scan is based on this setting.</span></span> <span data-ttu-id="7ba5d-114">Esta configuración también se usa para establecer el período de tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="7ba5d-114">This setting is also used to set the time-out period.</span></span> <span data-ttu-id="7ba5d-115">Durante el análisis, el Analizador de procedimientos recomendados espera una respuesta de un servidor durante un tiempo especificado.</span><span class="sxs-lookup"><span data-stu-id="7ba5d-115">During the scan, the Best Practices Analyzer waits for a response from a server for a specified time.</span></span> <span data-ttu-id="7ba5d-116">Si no recibe una respuesta dentro del período de tiempo de espera especificado, pasa al siguiente servidor en el examen.</span><span class="sxs-lookup"><span data-stu-id="7ba5d-116">If it does not receive a response within the specified time-out period, it moves to the next server in the scan.</span></span> <span data-ttu-id="7ba5d-117">En redes más lentas, este período de tiempo especificado es superior para latencias de red de mayor duración.</span><span class="sxs-lookup"><span data-stu-id="7ba5d-117">On slower networks, this specified time-out period is longer to account for longer network latencies.</span></span> <span data-ttu-id="7ba5d-118">Se recomienda que seleccione el vínculo más lento en su topología para este parámetro de manera que la herramienta no supere el tiempo de espera tan rápidamente.</span><span class="sxs-lookup"><span data-stu-id="7ba5d-118">We recommend that you select the slowest link in your topology for this parameter so that the tool does not time out too quickly.</span></span>

<div>

## <a name="to-scan-your-lync-server-2013-deployment"></a><span data-ttu-id="7ba5d-119">Para examinar su implementación de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7ba5d-119">To scan your Lync Server 2013 deployment</span></span>

1.  <span data-ttu-id="7ba5d-120">Inicie sesión en un equipo en el que el Analizador de procedimientos recomendados está instalado usando una cuenta que es miembro del grupo Administradores local y tiene otros derechos de usuario y permisos requeridos.</span><span class="sxs-lookup"><span data-stu-id="7ba5d-120">Log on to a computer on which Best Practices Analyzer is installed by using an account that is a member of the local Administrators group, and has other required user rights and permissions.</span></span>

2.  <span data-ttu-id="7ba5d-121">Haga clic en **Inicio**, seleccione **todos los programas**, haga clic en **Microsoft Lync Server 2013**y, a continuación, en **analizador de procedimientos recomendados**.</span><span class="sxs-lookup"><span data-stu-id="7ba5d-121">Click **Start**, point to **All Programs**, click **Microsoft Lync Server 2013**, and then click **Best Practices Analyzer**.</span></span>

3.  <span data-ttu-id="7ba5d-122">En la pantalla de\*\*\*\* bienvenida, haga clic en **Seleccionar opciones para un nuevo análisis**.</span><span class="sxs-lookup"><span data-stu-id="7ba5d-122">On the **Welcome** screen, click **Select options for a new scan**.</span></span>

4.  <span data-ttu-id="7ba5d-123">En la página **Conectar con Active Directory**, compruebe el nombre especificado en **Servidor de Active Directory** y, a continuación, lleve a cabo una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="7ba5d-123">On the **Connect to Active Directory** page, verify the name specified in **Active Directory Server**, and then do one of the following:</span></span>
    
      - <span data-ttu-id="7ba5d-124">Para ejecutar un examen usando las credenciales que ha usado para iniciar sesión en el equipo, haga clic en **Conectar al servidor de Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="7ba5d-124">To run a scan using the credentials that you used to log on to the computer, click **Connect to the Active Directory server**.</span></span>
    
      - <span data-ttu-id="7ba5d-125">Para especificar diferentes credenciales que desea usar para Servicios de dominio de Active Directory, servidor perimetral o Exchange Server, haga clic en **Mostrar opciones de inicio de sesión avanzadas**, active cada casilla para la que se requieren credenciales independientes, especifique las credenciales para cada casilla seleccionada y, a continuación, haga clic en **Conectar al servidor de Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="7ba5d-125">To specify different credentials that you want to use for Active Directory Domain Services, Edge Server, or Exchange Server, click **Show advanced logon options**, select each check box for which separate credentials are required, specify the credentials for each selected check box, and then click **Connect to the Active Directory server**.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="7ba5d-p105">Antes de comenzar el examen, el Analizador de procedimientos recomendados lleva a cabo una comprobación de red y permisos para asegurarse de que las credenciales de la cuenta especificada son válidos y que el Analizador de procedimientos recomendados se puede conectar a Servicios de dominio de Active Directory. Si la herramienta se ejecuta en un servidor de grupo de trabajo, la herramienta también comprueba que se puede conectar a servidores perimetrales en la red perimetral (es decir, si se incluyen en el examen).</span><span class="sxs-lookup"><span data-stu-id="7ba5d-p105">Before beginning the scan, Best Practices Analyzer performs a network and permissions check to ensure that the specified account credentials are valid and that Best Practices Analyzer can connect to Active Directory Domain Services. If the tool is running on a workgroup server, the tool also verifies that it can connect to Edge Servers in the perimeter network (that is, if they are included in the scan).</span></span>

    
    </div>

5.  <span data-ttu-id="7ba5d-128">En la página **Iniciar un nuevo análisis de Best Practices**, seleccione las opciones que desea incluir en el examen, especifique la velocidad de la red y, a continuación, haga clic en **Iniciar análisis**.</span><span class="sxs-lookup"><span data-stu-id="7ba5d-128">On the **Start a new Best Practices scan** page, select the options that you want to include in the scan, specify the network speed, and then click **Start scanning**.</span></span>

6.  <span data-ttu-id="7ba5d-129">En la página **Análisis completado**, haga clic en **Ver un informe de este análisis de Best Practices**.</span><span class="sxs-lookup"><span data-stu-id="7ba5d-129">On the **Scanning Completed** page, click **View a report of this Best Practices scan**.</span></span>

7.  <span data-ttu-id="7ba5d-130">En la página **Ver informe de Best Practices**, realice una de las operaciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="7ba5d-130">On the **View Best Practices Report** page, do one of the following:</span></span>
    
      - <span data-ttu-id="7ba5d-131">Para ver los informes en una lista organizada según el componente del servidor, haga clic en **Informes de lista** y, después, en la pestaña **Todos los problemas** o **Información detallada**.</span><span class="sxs-lookup"><span data-stu-id="7ba5d-131">To view reports in a list organized by server component, click **List Reports**, and then click either the **All Issues** tab or the **Informational Items** tab.</span></span>
    
      - <span data-ttu-id="7ba5d-132">Para ver los informes como una lista jerárquica organizada según los tipos de resultados, haga clic en **Informes ramificados** y, después, en la pestaña **Vista detallada** o **Vista de resumen**.</span><span class="sxs-lookup"><span data-stu-id="7ba5d-132">To view reports as a hierarchical list organized by types of results, click **Tree Reports**, and then click either the **Detailed View** tab or the **Summary View** tab.</span></span>
    
      - <span data-ttu-id="7ba5d-133">Para ver otro tipo de informes, haga clic en **Otros informes**.</span><span class="sxs-lookup"><span data-stu-id="7ba5d-133">To view other reports, click **Other Reports**.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="7ba5d-134">Para obtener más información sobre los informes del analizador de procedimientos recomendados y los problemas que identifican, consulte <A href="lync-server-2013-viewing-and-working-with-reports-created-by-best-practices-analyzer.md">Viewing and Working with Reports Created by Best Practices Analyzer in Lync server 2013</A> y <A href="lync-server-2013-analyzing-and-resolving-issues-identified-by-best-practices-analyzer.md">análisis y resolución de problemas identificados por Best Practices Analyzer en Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="7ba5d-134">For details about the Best Practices Analyzer reports and the issues they identify, see <A href="lync-server-2013-viewing-and-working-with-reports-created-by-best-practices-analyzer.md">Viewing and working with reports created by Best Practices Analyzer in Lync Server 2013</A> and <A href="lync-server-2013-analyzing-and-resolving-issues-identified-by-best-practices-analyzer.md">Analyzing and resolving issues identified by Best Practices Analyzer in Lync Server 2013</A>.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

