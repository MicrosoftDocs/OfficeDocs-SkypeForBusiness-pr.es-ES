---
title: 'Lync Server 2013: usar el registro enriquecido para transacciones sintéticas'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using rich logging for synthetic transactions
ms:assetid: 32714a71-9f42-4d5b-a508-e176d8f08bbf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204798(v=OCS.15)
ms:contentKeyID: 48183812
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b1fd1cfd26e1b5d56a6043e13d348e73e3c2b108
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42212726"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="using-rich-logging-for-synthetic-transactions-in-lync-server-2013"></a><span data-ttu-id="3c3e8-102">Uso del registro enriquecido para transacciones sintéticas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3c3e8-102">Using rich logging for synthetic transactions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3c3e8-103">_**Última modificación del tema:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="3c3e8-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="3c3e8-104">Las transacciones sintéticas (incluidas en Microsoft Lync Server 2010) proporcionan una manera para que los administradores comprueben que los usuarios pueden completar correctamente tareas comunes como iniciar sesión en el sistema, intercambiar mensajes instantáneos o realizar llamadas a un teléfono ubicado en la red telefónica conmutada (RTC).</span><span class="sxs-lookup"><span data-stu-id="3c3e8-104">Synthetic transactions (introduced in Microsoft Lync Server 2010) provide a way for administrators to verify that users are able to successfully complete common tasks such as logging on to the system, exchanging instant messages, or making calls to a phone located on the public switched telephone network (PSTN).</span></span> <span data-ttu-id="3c3e8-105">Estas pruebas (que se empaquetan como un conjunto de cmdlets de Windows PowerShell de Lync Server) pueden ser realizadas manualmente por un administrador o pueden ser ejecutadas automáticamente por una aplicación como System Center Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="3c3e8-105">These tests (which are packaged as a set of Lync Server Windows PowerShell cmdlets) can be conducted manually by an administrator, or they can be automatically run by an application such as System Center Operations Manager.</span></span>

<span data-ttu-id="3c3e8-106">En Lync Server 2010, las transacciones sintéticas resultaban muy útiles para ayudar a los administradores a identificar problemas en el sistema.</span><span class="sxs-lookup"><span data-stu-id="3c3e8-106">In Lync Server 2010, synthetic transactions proved extremely useful in helping administrators to identify problems with the system.</span></span> <span data-ttu-id="3c3e8-107">Por ejemplo, el cmdlet **Test-CsRegistration** podría avisar a los administradores del hecho de que algunos usuarios tenían problemas para registrarse en Lync Server.</span><span class="sxs-lookup"><span data-stu-id="3c3e8-107">For example, the **Test-CsRegistration** cmdlet could alert administrators to the fact that some users were having difficulty registering with Lync Server.</span></span> <span data-ttu-id="3c3e8-108">Sin embargo, las transacciones sintéticas eran algo menos útiles para ayudar a los administradores a determinar por qué estos usuarios tenían problemas para registrarse con Lync Server.</span><span class="sxs-lookup"><span data-stu-id="3c3e8-108">However, the synthetic transactions were somewhat less useful in helping administrators determine why these users were having difficulty registering with Lync Server.</span></span> <span data-ttu-id="3c3e8-109">Esto se debe a que las transacciones sintéticas no proporcionaban información de registro detallada que podría ayudar a los administradores a solucionar problemas con Lync Server.</span><span class="sxs-lookup"><span data-stu-id="3c3e8-109">This was due to the fact that the synthetic transactions did not provide detailed logging information that could help administrators troubleshoot problems with Lync Server.</span></span> <span data-ttu-id="3c3e8-110">En el mejor de los casos, los resultados detallados de las transacciones sintéticas proporcionaban información detallada que podían ayudar al administrador a suponer dónde se podía encontrar el problema.</span><span class="sxs-lookup"><span data-stu-id="3c3e8-110">At best, the verbose output from a synthetic transaction provided step-by-step information that might enable an administrator to make an educated guess as to where a problem likely occurred.</span></span>

<span data-ttu-id="3c3e8-111">En Microsoft Lync Server 2013, las transacciones sintéticas se han vuelto a diseñar para proporcionar un registro enriquecido.</span><span class="sxs-lookup"><span data-stu-id="3c3e8-111">In Microsoft Lync Server 2013, synthetic transactions have been re-architected to provide rich logging.</span></span> <span data-ttu-id="3c3e8-112">El concepto "registro enriquecido" implica que se registra información detallada para cada una de las transacciones sintéticas llevadas a cabo:</span><span class="sxs-lookup"><span data-stu-id="3c3e8-112">"Rich logging" means that, for each activity that a synthetic transaction undertakes, information such as this will be recorded:</span></span>

  - <span data-ttu-id="3c3e8-113">La hora a la que se inició la actividad</span><span class="sxs-lookup"><span data-stu-id="3c3e8-113">The time that the activity started</span></span>

  - <span data-ttu-id="3c3e8-114">La hora a la que finalizó la actividad</span><span class="sxs-lookup"><span data-stu-id="3c3e8-114">The time that the activity finished</span></span>

  - <span data-ttu-id="3c3e8-115">La acción que se ha realizado (por ejemplo, crear, unirse o abandonar una conferencia; iniciar sesión en Lync Server; enviar un mensaje instantáneo, etc.)</span><span class="sxs-lookup"><span data-stu-id="3c3e8-115">The action that was performed (for example, creating, joining, or leaving a conference; signing on to Lync Server; sending an instant message; and so on)</span></span>

  - <span data-ttu-id="3c3e8-116">Mensajes de error o advertencias detalladas o informativas generadas cuando se ejecutó la actividad</span><span class="sxs-lookup"><span data-stu-id="3c3e8-116">Informational, verbose, warning, or error messages generated when the activity ran</span></span>

  - <span data-ttu-id="3c3e8-117">Mensajes de registro SIP</span><span class="sxs-lookup"><span data-stu-id="3c3e8-117">SIP registration messages</span></span>

  - <span data-ttu-id="3c3e8-118">Códigos de diagnóstico o registros de excepción generados cuando se ejecutó la actividad</span><span class="sxs-lookup"><span data-stu-id="3c3e8-118">Exception records or diagnostic codes generated when the activity ran</span></span>

  - <span data-ttu-id="3c3e8-119">Resultado neto de la ejecución de la actividad</span><span class="sxs-lookup"><span data-stu-id="3c3e8-119">The net result of running the activity</span></span>

<span data-ttu-id="3c3e8-120">Esta información se genera automáticamente cada vez que se ejecuta una transacción sintética.</span><span class="sxs-lookup"><span data-stu-id="3c3e8-120">This information is automatically generated each time a synthetic transaction is run.</span></span> <span data-ttu-id="3c3e8-121">Sin embargo, la información no se muestra automáticamente ni se guarda en un archivo de registro.</span><span class="sxs-lookup"><span data-stu-id="3c3e8-121">However, the information is not automatically displayed or saved to a log file.</span></span> <span data-ttu-id="3c3e8-122">En su lugar, los administradores que ejecutan manualmente una transacción sintética pueden usar el parámetro OutLoggerVariable para especificar una variable de Windows PowerShell en la que se almacenará la información.</span><span class="sxs-lookup"><span data-stu-id="3c3e8-122">Instead, administrators who are manually running a synthetic transaction can use the OutLoggerVariable parameter to specify a Windows PowerShell variable in which the information will be stored.</span></span> <span data-ttu-id="3c3e8-123">Desde ahí, los administradores pueden usar un par de métodos que permiten guardar y ver los registros enriquecidos en formato XML o HTML.</span><span class="sxs-lookup"><span data-stu-id="3c3e8-123">From there, administrators can then use a pair of methods that enable them to save and/or view the rich log in either XML or HTML format.</span></span>

<span data-ttu-id="3c3e8-124">Por ejemplo, los administradores de Lync Server 2010 pueden ejecutar el cmdlet **Test-CsRegistration** con un comando similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="3c3e8-124">For example, Lync Server 2010 administrators might run the **Test-CsRegistration** cmdlet by using a command similar to the following:</span></span>

    Test-CsRegistration -TargetFqdn atl-cs-001.litwareinc.com

<span data-ttu-id="3c3e8-125">Los administradores tienen la opción de incluir el parámetro OutLoggerVariable seguido de un nombre de variable de su elección:</span><span class="sxs-lookup"><span data-stu-id="3c3e8-125">Administrators have the option of including the OutLoggerVariable parameter followed by a variable name of their choosing:</span></span>

    Test-CsRegistration -TargetFqdn atl-cs-001.litwareinc.com -OutLoggerVariable RegistrationTest

> [!NOTE]  
> <span data-ttu-id="3c3e8-p105">Asegúrese de no anteponer el carácter $ al nombre de la variable. Utilice el nombre de variable RegistrationTest y no $RegistrationTest.</span><span class="sxs-lookup"><span data-stu-id="3c3e8-p105">Do not preface the variable name with the $ character. Use a variable name like RegistrationTest and not $RegistrationTest.</span></span>

<span data-ttu-id="3c3e8-128">El comando anterior muestra un contenido similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="3c3e8-128">The preceding command outputs content similar to the following:</span></span>

    Target Fqdn   : atl-cs-001.litwareinc.com
    Result        : Failure
    Latency       : 00:00:00
    Error Message : This machine does not have any assigned certificates.
    Diagnosis     :

<span data-ttu-id="3c3e8-p106">Sin embargo, existe información más detallada para este error que el mensaje mostrado anteriormente. Para tener acceso a dicha información en formato HTML, utilice un comando similar al siguiente. Este comando permite guardar la información almacenada en la variable RegistrationTest en un archivo HTML:</span><span class="sxs-lookup"><span data-stu-id="3c3e8-p106">However, much more detailed information is available for this failure than just the error message shown above. To access that information in HTML format, use a command similar to this in order to save the information stored in the variable RegistrationTest to an HTML file:</span></span>

    $RegistrationTest.ToHTML() | Out-File C:\Logs\Registration.html

<span data-ttu-id="3c3e8-131">Del mismo modo, puede usar el método ToXML() para guardar los datos en un archivo XML:</span><span class="sxs-lookup"><span data-stu-id="3c3e8-131">Alternatively, you can use the ToXML() method to save the data to an XML file:</span></span>

    $RegistrationTest.ToXML() | Out-File C:\Logs\Registration.xml

<span data-ttu-id="3c3e8-132">A continuación, estos archivos se pueden ver con Internet Explorer, Visual Studio o cualquier otra aplicación capaz de abrir archivos HTML/XML.</span><span class="sxs-lookup"><span data-stu-id="3c3e8-132">These files can then be viewed using Internet Explorer, Visual Studio, or any other application capable of opening HTML/XML files.</span></span>

<span data-ttu-id="3c3e8-133">Las transacciones sintéticas que se ejecutan desde dentro de System Center Operations Manager generarán automáticamente estos archivos de registro para los errores.</span><span class="sxs-lookup"><span data-stu-id="3c3e8-133">Synthetic transactions run from inside of System Center Operations Manager will automatically generate these log files for failures.</span></span> <span data-ttu-id="3c3e8-134">Sin embargo, estos registros no se generarán si se produce un error en la ejecución antes de que Windows PowerShell pueda cargar y ejecutar la transacción sintética.</span><span class="sxs-lookup"><span data-stu-id="3c3e8-134">However, these logs will not be generated if the execution fails before Windows PowerShell is able to load and run the synthetic transaction.</span></span>

> [!IMPORTANT]  
> <span data-ttu-id="3c3e8-135">De forma predeterminada, Lync Server 2013 guarda los archivos de registro en una carpeta que no está compartida.</span><span class="sxs-lookup"><span data-stu-id="3c3e8-135">By default, Lync Server 2013 saves log files to a folder that is not shared.</span></span> <span data-ttu-id="3c3e8-136">Para que estos registros sean accesibles fácilmente, debe compartir esta carpeta (por ejemplo, \\ \\ATL-monitor-001. litwareinc. com\WatcherNode.</span><span class="sxs-lookup"><span data-stu-id="3c3e8-136">To make these logs readily accessible, you should share this folder (for example, \\\\atl-watcher-001.litwareinc.com\WatcherNode.</span></span>


</div>

</div>

</div>

</div>

