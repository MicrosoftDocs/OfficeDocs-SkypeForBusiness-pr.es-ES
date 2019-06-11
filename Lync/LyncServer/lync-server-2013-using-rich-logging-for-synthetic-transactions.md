---
title: 'Lync Server 2013: uso del registro completo para transacciones sintéticas'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Using rich logging for synthetic transactions
ms:assetid: 32714a71-9f42-4d5b-a508-e176d8f08bbf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204798(v=OCS.15)
ms:contentKeyID: 48183812
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 455d7bcdc14dd4d701d749407759cead0834906f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34850182"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-rich-logging-for-synthetic-transactions-in-lync-server-2013"></a><span data-ttu-id="f89f0-102">Usar el registro avanzado para transacciones sintéticas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f89f0-102">Using rich logging for synthetic transactions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f89f0-103">_**Última modificación del tema:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="f89f0-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="f89f0-104">Las transacciones sintéticas (presentadas en Microsoft Lync Server 2010) permiten a los administradores comprobar que los usuarios pueden completar correctamente tareas comunes como iniciar sesión en el sistema, intercambiar mensajes instantáneos o hacer llamadas a un teléfono ubicado en la red de telefonía pública conmutada (RTC).</span><span class="sxs-lookup"><span data-stu-id="f89f0-104">Synthetic transactions (introduced in Microsoft Lync Server 2010) provide a way for administrators to verify that users are able to successfully complete common tasks such as logging on to the system, exchanging instant messages, or making calls to a phone located on the public switched telephone network (PSTN).</span></span> <span data-ttu-id="f89f0-105">Estas pruebas (que se empaquetan como un conjunto de cmdlets de Windows PowerShell de Lync Server) pueden realizarse manualmente por un administrador o una aplicación, como System Center Operations Manager, las puede ejecutar automáticamente.</span><span class="sxs-lookup"><span data-stu-id="f89f0-105">These tests (which are packaged as a set of Lync Server Windows PowerShell cmdlets) can be conducted manually by an administrator, or they can be automatically run by an application such as System Center Operations Manager.</span></span>

<span data-ttu-id="f89f0-106">En Lync Server 2010, las transacciones sintéticas se demostraron muy útiles para ayudar a los administradores a identificar problemas con el sistema.</span><span class="sxs-lookup"><span data-stu-id="f89f0-106">In Lync Server 2010, synthetic transactions proved extremely useful in helping administrators to identify problems with the system.</span></span> <span data-ttu-id="f89f0-107">Por ejemplo, el cmdlet **Test-CsRegistration** puede avisar a los administradores de que algunos usuarios tienen problemas para registrarse en Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f89f0-107">For example, the **Test-CsRegistration** cmdlet could alert administrators to the fact that some users were having difficulty registering with Lync Server.</span></span> <span data-ttu-id="f89f0-108">Sin embargo, las transacciones sintéticas eran menos útiles para ayudar a los administradores a determinar por qué estos usuarios tenían problemas para registrarse en Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f89f0-108">However, the synthetic transactions were somewhat less useful in helping administrators determine why these users were having difficulty registering with Lync Server.</span></span> <span data-ttu-id="f89f0-109">Esto se debía a que las transacciones sintéticas no proporcionaban información de registro detallada que pudiera ayudar a los administradores a solucionar problemas con Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f89f0-109">This was due to the fact that the synthetic transactions did not provide detailed logging information that could help administrators troubleshoot problems with Lync Server.</span></span> <span data-ttu-id="f89f0-110">En el mejor de los casos, la salida detallada de una transacción sintética proporcionaba información paso a paso que podría permitir a un administrador hacer una estimación educada sobre dónde se produjo un problema.</span><span class="sxs-lookup"><span data-stu-id="f89f0-110">At best, the verbose output from a synthetic transaction provided step-by-step information that might enable an administrator to make an educated guess as to where a problem likely occurred.</span></span>

<span data-ttu-id="f89f0-111">En Microsoft Lync Server 2013, las transacciones sintéticas se han diseñado para proporcionar un registro enriquecido.</span><span class="sxs-lookup"><span data-stu-id="f89f0-111">In Microsoft Lync Server 2013, synthetic transactions have been re-architected to provide rich logging.</span></span> <span data-ttu-id="f89f0-112">"Registro enriquecido" significa que, para cada actividad que se compromete con una transacción sintética, se registrará información como esta:</span><span class="sxs-lookup"><span data-stu-id="f89f0-112">"Rich logging" means that, for each activity that a synthetic transaction undertakes, information such as this will be recorded:</span></span>

  - <span data-ttu-id="f89f0-113">El momento en que comenzó la actividad</span><span class="sxs-lookup"><span data-stu-id="f89f0-113">The time that the activity started</span></span>

  - <span data-ttu-id="f89f0-114">El momento en que terminó la actividad</span><span class="sxs-lookup"><span data-stu-id="f89f0-114">The time that the activity finished</span></span>

  - <span data-ttu-id="f89f0-115">La acción que se realizó (por ejemplo, crear, unirse o salir de una conferencia; iniciar sesión en Lync Server; enviar un mensaje instantáneo, etc.)</span><span class="sxs-lookup"><span data-stu-id="f89f0-115">The action that was performed (for example, creating, joining, or leaving a conference; signing on to Lync Server; sending an instant message; and so on)</span></span>

  - <span data-ttu-id="f89f0-116">Mensajes de error o advertencias detalladas o informativas generadas cuando se ejecutó la actividad.</span><span class="sxs-lookup"><span data-stu-id="f89f0-116">Informational, verbose, warning, or error messages generated when the activity ran</span></span>

  - <span data-ttu-id="f89f0-117">Mensajes de registro SIP</span><span class="sxs-lookup"><span data-stu-id="f89f0-117">SIP registration messages</span></span>

  - <span data-ttu-id="f89f0-118">Registros de excepciones o códigos de diagnóstico generados cuando se ejecutó la actividad</span><span class="sxs-lookup"><span data-stu-id="f89f0-118">Exception records or diagnostic codes generated when the activity ran</span></span>

  - <span data-ttu-id="f89f0-119">El resultado neto de la ejecución de la actividad</span><span class="sxs-lookup"><span data-stu-id="f89f0-119">The net result of running the activity</span></span>

<span data-ttu-id="f89f0-120">Esta información se genera automáticamente cada vez que se ejecuta una transacción sintética.</span><span class="sxs-lookup"><span data-stu-id="f89f0-120">This information is automatically generated each time a synthetic transaction is run.</span></span> <span data-ttu-id="f89f0-121">Sin embargo, la información no se muestra o se guarda automáticamente en un archivo de registro.</span><span class="sxs-lookup"><span data-stu-id="f89f0-121">However, the information is not automatically displayed or saved to a log file.</span></span> <span data-ttu-id="f89f0-122">En su lugar, los administradores que ejecutan manualmente una transacción sintética pueden usar el parámetro OutLoggerVariable para especificar una variable de Windows PowerShell en la que se almacenará la información.</span><span class="sxs-lookup"><span data-stu-id="f89f0-122">Instead, administrators who are manually running a synthetic transaction can use the OutLoggerVariable parameter to specify a Windows PowerShell variable in which the information will be stored.</span></span> <span data-ttu-id="f89f0-123">Desde allí, los administradores pueden usar un par de métodos que les permitan guardar o ver el registro enriquecido en formato XML o HTML.</span><span class="sxs-lookup"><span data-stu-id="f89f0-123">From there, administrators can then use a pair of methods that enable them to save and/or view the rich log in either XML or HTML format.</span></span>

<span data-ttu-id="f89f0-124">Por ejemplo, los administradores de Lync Server 2010 pueden ejecutar el cmdlet **Test-CsRegistration** con un comando similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="f89f0-124">For example, Lync Server 2010 administrators might run the **Test-CsRegistration** cmdlet by using a command similar to the following:</span></span>

    Test-CsRegistration -TargetFqdn atl-cs-001.litwareinc.com

<span data-ttu-id="f89f0-125">Los administradores tienen la opción de incluir el parámetro OutLoggerVariable seguido de un nombre de variable de su elección:</span><span class="sxs-lookup"><span data-stu-id="f89f0-125">Administrators have the option of including the OutLoggerVariable parameter followed by a variable name of their choosing:</span></span>

    Test-CsRegistration -TargetFqdn atl-cs-001.litwareinc.com -OutLoggerVariable RegistrationTest

> [!NOTE]  
> <span data-ttu-id="f89f0-126">No anteponga el carácter $ al nombre de la variable.</span><span class="sxs-lookup"><span data-stu-id="f89f0-126">Do not preface the variable name with the $ character.</span></span> <span data-ttu-id="f89f0-127">Use un nombre de variable como RegistrationTest y no $RegistrationTest.</span><span class="sxs-lookup"><span data-stu-id="f89f0-127">Use a variable name like RegistrationTest and not $RegistrationTest.</span></span>

<span data-ttu-id="f89f0-128">El comando anterior genera contenido similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="f89f0-128">The preceding command outputs content similar to the following:</span></span>

    Target Fqdn   : atl-cs-001.litwareinc.com
    Result        : Failure
    Latency       : 00:00:00
    Error Message : This machine does not have any assigned certificates.
    Diagnosis     :

<span data-ttu-id="f89f0-129">Sin embargo, hay mucha más información detallada para este error que solo el mensaje de error que se muestra arriba.</span><span class="sxs-lookup"><span data-stu-id="f89f0-129">However, much more detailed information is available for this failure than just the error message shown above.</span></span> <span data-ttu-id="f89f0-130">Para tener acceso a esa información en formato HTML, use un comando similar a este para guardar la información almacenada en la variable RegistrationTest en un archivo HTML:</span><span class="sxs-lookup"><span data-stu-id="f89f0-130">To access that information in HTML format, use a command similar to this in order to save the information stored in the variable RegistrationTest to an HTML file:</span></span>

    $RegistrationTest.ToHTML() | Out-File C:\Logs\Registration.html

<span data-ttu-id="f89f0-131">Del mismo modo, puede usar el método ToXML() para guardar los datos en un archivo XML:</span><span class="sxs-lookup"><span data-stu-id="f89f0-131">Alternatively, you can use the ToXML() method to save the data to an XML file:</span></span>

    $RegistrationTest.ToXML() | Out-File C:\Logs\Registration.xml

<span data-ttu-id="f89f0-132">Estos archivos se pueden ver con Internet Explorer, Visual Studio o cualquier otra aplicación capaz de abrir archivos HTML o XML.</span><span class="sxs-lookup"><span data-stu-id="f89f0-132">These files can then be viewed using Internet Explorer, Visual Studio, or any other application capable of opening HTML/XML files.</span></span>

<span data-ttu-id="f89f0-133">Las transacciones sintéticas ejecutadas desde dentro de System Center Operations Manager generarán automáticamente estos archivos de registro por si se producen errores.</span><span class="sxs-lookup"><span data-stu-id="f89f0-133">Synthetic transactions run from inside of System Center Operations Manager will automatically generate these log files for failures.</span></span> <span data-ttu-id="f89f0-134">Sin embargo, estos registros no se generarán si se produce un error en la ejecución antes de que Windows PowerShell pueda cargar y ejecutar la transacción sintética.</span><span class="sxs-lookup"><span data-stu-id="f89f0-134">However, these logs will not be generated if the execution fails before Windows PowerShell is able to load and run the synthetic transaction.</span></span>

> [!IMPORTANT]  
> <span data-ttu-id="f89f0-135">De forma predeterminada, Lync Server 2013 guarda los archivos de registro en una carpeta que no está compartida.</span><span class="sxs-lookup"><span data-stu-id="f89f0-135">By default, Lync Server 2013 saves log files to a folder that is not shared.</span></span> <span data-ttu-id="f89f0-136">Para que estos registros sean accesibles fácilmente, debe compartir esta carpeta (por ejemplo, \\ \\ATL-Watcher-001. litwareinc. com\WatcherNode.</span><span class="sxs-lookup"><span data-stu-id="f89f0-136">To make these logs readily accessible, you should share this folder (for example, \\\\atl-watcher-001.litwareinc.com\WatcherNode.</span></span>


</div>

</div>

</div>

</div>

