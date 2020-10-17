---
title: 'Lync Server 2013: lectura de registros de captura desde el servicio de registro centralizado'
description: 'Lync Server 2013: lectura de registros de captura desde el servicio de registro centralizado.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Reading capture logs from the Centralized Logging Service
ms:assetid: c86ccf61-d86f-4ebd-b8d1-984a1b73005d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721879(v=OCS.15)
ms:contentKeyID: 49733813
ms.date: 12/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fcdd70c924b49098814e80a375ae34d2bf48dc41
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48559166"
---
# <a name="reading-capture-logs-from-the-centralized-logging-service-in-lync-server-2013"></a><span data-ttu-id="fac74-103">Lectura de registros de captura desde el servicio de registro centralizado en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fac74-103">Reading capture logs from the Centralized Logging Service in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fac74-104">_**Última modificación del tema:** 2016-12-28_</span><span class="sxs-lookup"><span data-stu-id="fac74-104">_**Topic Last Modified:** 2016-12-28_</span></span>

<span data-ttu-id="fac74-105">Tiene en cuenta las ventajas reales del servicio de registro centralizado después de ejecutar la búsqueda y tiene un archivo que puede usar para realizar un seguimiento de un problema notificado.</span><span class="sxs-lookup"><span data-stu-id="fac74-105">You realize the real benefit of the Centralized Logging Service after you run the search and you have a file that you can use to track down a reported problem.</span></span> <span data-ttu-id="fac74-106">Hay varias formas de leer el archivo.</span><span class="sxs-lookup"><span data-stu-id="fac74-106">There are a number of ways that you can read the file.</span></span> <span data-ttu-id="fac74-107">El archivo de salida está en un formato de texto estándar y puede usar Notepad.exe o cualquier otro programa que le permita abrir y leer un archivo de texto.</span><span class="sxs-lookup"><span data-stu-id="fac74-107">The output file is in a standard text format and you can use Notepad.exe or any other programs that will allow you to open and read a text file.</span></span> <span data-ttu-id="fac74-108">Para archivos más grandes y problemas más complejos, puede usar una herramienta como Snooper.exe que está diseñada para leer y analizar el resultado del registro del servicio de registro centralizado.</span><span class="sxs-lookup"><span data-stu-id="fac74-108">For larger files and more complex issues, you could use a tool like Snooper.exe that is designed to read and parse the logging output from the Centralized Logging Service.</span></span> <span data-ttu-id="fac74-109">Snooper se incluye con las herramientas de depuración de Lync Server 2013 que están disponibles como una descarga independiente.</span><span class="sxs-lookup"><span data-stu-id="fac74-109">Snooper is included with the Lync Server 2013 Debug Tools that are available as a separate download.</span></span> <span data-ttu-id="fac74-110">Puede descargar las herramientas de depuración de Lync Server 2013 aquí: [https://go.microsoft.com/fwlink/?LinkId=285257](https://go.microsoft.com/fwlink/?linkid=285257) .</span><span class="sxs-lookup"><span data-stu-id="fac74-110">You can download the Lync Server 2013 Debug Tools here: [https://go.microsoft.com/fwlink/?LinkId=285257](https://go.microsoft.com/fwlink/?linkid=285257).</span></span> <span data-ttu-id="fac74-111">Al instalar las herramientas de depuración de Lync Server 2013, los elementos de menú y los cortados no se crean.</span><span class="sxs-lookup"><span data-stu-id="fac74-111">When you install the Lync Server 2013 Debug Tools, short cuts and menu items are not created.</span></span> <span data-ttu-id="fac74-112">Después de instalar las herramientas de depuración de Lync Server 2013, abra el explorador de Windows, una ventana de línea de comandos o shell de administración de Lync Server y vaya al directorio (ubicación predeterminada) C: \\ archivos de programa \\ herramientas de depuración de Microsoft Lync Server 2013 \\ .</span><span class="sxs-lookup"><span data-stu-id="fac74-112">After you install the Lync Server 2013 Debug Tools, open Windows Explorer, a command-line window, or Lync Server Management Shell and go to the directory (default location) C:\\Program Files\\Microsoft Lync Server 2013\\Debugging Tools.</span></span> <span data-ttu-id="fac74-113">Haga doble clic en Snooper.exe o escriba Snooper.exe y, a continuación, presione Entrar si está usando la línea de comandos o el shell de administración de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="fac74-113">Double-click Snooper.exe or type Snooper.exe, and then press ENTER if you are using the command line or Lync Server Management Shell.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="fac74-114">La finalidad de este tema no es dar información detallada ni tratar las técnicas de solución de problemas.</span><span class="sxs-lookup"><span data-stu-id="fac74-114">The intent of this topic is not to detail and discuss troubleshooting techniques.</span></span> <span data-ttu-id="fac74-115">La solución de problemas y los procesos relacionados con esta son un tema muy complejo.</span><span class="sxs-lookup"><span data-stu-id="fac74-115">Troubleshooting and the processes around it is a complex subject.</span></span> <span data-ttu-id="fac74-116">Para obtener más información sobre la solución de problemas básicos y la solución de problemas de cargas de trabajo específicas, consulte el manual del kit de recursos de Microsoft Lync Server 2010 en <A href="https://go.microsoft.com/fwlink/p/?linkid=211003">https://go.microsoft.com/fwlink/p/?linkId=211003</A> .</span><span class="sxs-lookup"><span data-stu-id="fac74-116">For details about troubleshooting basics and troubleshooting specific workloads, see the Microsoft Lync Server 2010 Resource Kit book at <A href="https://go.microsoft.com/fwlink/p/?linkid=211003">https://go.microsoft.com/fwlink/p/?linkId=211003</A>.</span></span> <span data-ttu-id="fac74-117">Los procesos y procedimientos siguen siendo válidos para Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="fac74-117">The processes and procedures still apply to Lync Server 2013.</span></span>



</div>

<span data-ttu-id="fac74-118">Lync Server 2013 presenta una versión actualizada del Snoop que incluye algunas características nuevas.</span><span class="sxs-lookup"><span data-stu-id="fac74-118">Lync Server 2013 introduces an updated version of Snooper that includes some new features.</span></span> <span data-ttu-id="fac74-119">En la siguiente captura de pantalla se muestra la versión de Snoop de Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="fac74-119">The following screen shot shows the version of Snooper from Office Communications Server 2007.</span></span>

<span data-ttu-id="fac74-120">![Office Communications 2007 versión del Snooper.](images/JJ721879.129503a8-8edd-4bb0-a68f-c43f9a548b93(OCS.15).jpg "Office Communications 2007 versión del Snooper.")</span><span class="sxs-lookup"><span data-stu-id="fac74-120">![Office Communications 2007 version of Snooper.](images/JJ721879.129503a8-8edd-4bb0-a68f-c43f9a548b93(OCS.15).jpg "Office Communications 2007 version of Snooper.")</span></span>

<span data-ttu-id="fac74-121">En la siguiente captura de pantalla vemos la nueva versión del Snooper que se incluye en las herramientas de depuración de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="fac74-121">The following screen shot shows the new version of Snooper included in the Lync Server 2013 Debug Tools.</span></span>

<span data-ttu-id="fac74-122">![Lync Server 2013 versión de Snooper.](images/JJ721879.131495dd-8220-4ae4-af37-0ac5c318fd45(OCS.15).jpg "Lync Server 2013 versión de Snooper.")</span><span class="sxs-lookup"><span data-stu-id="fac74-122">![Lync Server 2013 version of Snooper.](images/JJ721879.131495dd-8220-4ae4-af37-0ac5c318fd45(OCS.15).jpg "Lync Server 2013 version of Snooper.")</span></span>

<span data-ttu-id="fac74-123">La captura de pantalla siguiente muestra la barra de herramientas con las funciones que se usan con mayor frecuencia.</span><span class="sxs-lookup"><span data-stu-id="fac74-123">The following screen shot shows the toolbar with frequently used functions.</span></span>

<span data-ttu-id="fac74-124">![Barra de herramientas de Snooper 2013.](images/JJ721879.989249c5-a33e-4251-b8b4-411019cc12b2(OCS.15).jpg "Barra de herramientas de Snooper 2013.")</span><span class="sxs-lookup"><span data-stu-id="fac74-124">![Snooper 2013 toolbar.](images/JJ721879.989249c5-a33e-4251-b8b4-411019cc12b2(OCS.15).jpg "Snooper 2013 toolbar.")</span></span>

<span data-ttu-id="fac74-p104">La característica más reciente que agrega valor es la vista de Diagrama de flujo (flujo de llamada). Se selecciona un flujo de mensaje en la pestaña **Mensaje** y se hace clic en el botón **Flujo de llamada**. A medida que avanza por los mensajes, el diagrama de flujo de llamada se actualiza con nuevos datos.</span><span class="sxs-lookup"><span data-stu-id="fac74-p104">And, the newest feature that adds value is the Flow Chart (call flow) diagram view. You select a message flow in the **Message** tab and click the **Call Flow** button. As you proceed through the messages, the call flow diagram updates with new data.</span></span>

<span data-ttu-id="fac74-128">![Diagrama de flujo de llamadas de Snooper 2013.](images/JJ721879.bb8be45d-a842-48fe-86f8-380207d70bab(OCS.15).jpg "Diagrama de flujo de llamadas de Snooper 2013.")</span><span class="sxs-lookup"><span data-stu-id="fac74-128">![Snooper 2013 call flow diagram.](images/JJ721879.bb8be45d-a842-48fe-86f8-380207d70bab(OCS.15).jpg "Snooper 2013 call flow diagram.")</span></span>

<span data-ttu-id="fac74-p105">Puede pasar el mouse por encima de la vista de diagrama y obtener detalles sobre los mensajes y el contenido de los flujos y los mensajes, así como de los elementos del servidor. Haga clic en una flecha del flujo de llamada y vaya al mensaje en la vista Mensaje.</span><span class="sxs-lookup"><span data-stu-id="fac74-p105">You can hover over the diagram view and get details about the messages and content of the flows and messages as well as the server elements. Click on any call flow arrow to go to the message in the Messages view.</span></span>

<span data-ttu-id="fac74-131">![Detalles del mensaje del diagrama de flujo de llamadas.](images/JJ721879.1147d720-38a9-4bda-8361-78f27ecde3d1(OCS.15).jpg "Detalles del mensaje del diagrama de flujo de llamadas.")</span><span class="sxs-lookup"><span data-stu-id="fac74-131">![Call flow diagram message details.](images/JJ721879.1147d720-38a9-4bda-8361-78f27ecde3d1(OCS.15).jpg "Call flow diagram message details.")</span></span>

<div>

## <a name="to-open-a-log-file-in-snooper"></a><span data-ttu-id="fac74-132">Para abrir un archivo de registro en Snooper:</span><span class="sxs-lookup"><span data-stu-id="fac74-132">To open a log file in Snooper</span></span>

1.  <span data-ttu-id="fac74-p106">Para usar Snooper y abrir archivos de registro, debe tener acceso de lectura a los archivos de registro. Para usar Snooper y tener acceso a los archivos de registro debe ser miembro de los grupos de seguridad de control de acceso basado en roles (RBAC) CsAdministrator o CsServerAdministrator, o de un rol RBAC personalizado que contenga cualquiera de estos dos grupos.</span><span class="sxs-lookup"><span data-stu-id="fac74-p106">To use Snooper and open log files, you need read access to the log files. To use Snooper and access the log files you must be a member of the CsAdministrator or the CsServerAdministrator role-based access control (RBAC) security groups, or a custom RBAC role that contains either of these two groups.</span></span>

2.  <span data-ttu-id="fac74-135">Tras la instalación de las herramientas de depuración de Lync Server (LyncDebugTools.msi), cambie el directorio a la ubicación de Snooper.exe con el explorador de Windows o desde la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="fac74-135">After the installation of the Lync Server Debugging Tools (LyncDebugTools.msi), change directory to the location of Snooper.exe using Windows Explorer or from the command line.</span></span> <span data-ttu-id="fac74-136">De forma predeterminada, las herramientas de depuración se encuentran en C: \\ archivos de programa \\ herramientas de depuración de Microsoft Lync Server 2013 \\ .</span><span class="sxs-lookup"><span data-stu-id="fac74-136">By default, the debugging tools are located in C:\\Program Files\\Microsoft Lync Server 2013\\Debugging Tools.</span></span> <span data-ttu-id="fac74-137">Haga doble clic en Snooper.exe o ejecútelo.</span><span class="sxs-lookup"><span data-stu-id="fac74-137">Double-click or run Snooper.exe.</span></span>

3.  <span data-ttu-id="fac74-138">Tras abrir Snooper, haga clic con el botón secundario en **Archivo**, haga clic en **Abrir archivo**, localice los archivos de registro, seleccione un archivo en el cuadro de diálogo **Abrir** y haga clic en **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="fac74-138">After Snooper is open, right-click **File**, click **OpenFile**, find your log files, select a file in the **Open** dialog box, and then click **Open**.</span></span>

4.  <span data-ttu-id="fac74-139">Los mensajes de **Seguimiento** del archivo de registro se muestran en la pestaña **Seguimiento**. Haga clic en la pestaña **Mensajes** para ver el contenido de los mensajes de los seguimientos recabados.</span><span class="sxs-lookup"><span data-stu-id="fac74-139">The log file’s **Trace** messages are displayed on the **Trace** tab. Click the **Messages** tab to view the message contents of the collected traces.</span></span>

</div>

<div>

## <a name="to-display-a-call-flow-diagram"></a><span data-ttu-id="fac74-140">Para mostrar un diagrama de flujo de llamada:</span><span class="sxs-lookup"><span data-stu-id="fac74-140">To display a call flow diagram</span></span>

1.  <span data-ttu-id="fac74-p108">Para usar Snooper y abrir archivos de registro, debe tener acceso de lectura a los archivos de registro. Para usar Snooper y tener acceso a los archivos de registro debe ser miembro de los grupos de seguridad de control de acceso basado en roles (RBAC) CsAdministrator o CsServerAdministrator, o de un rol RBAC personalizado que contenga cualquiera de estos dos grupos.</span><span class="sxs-lookup"><span data-stu-id="fac74-p108">To use Snooper and open log files, you need read access to the log files. To use Snooper and access the log files, you need to be a member of the CsAdministrator or the CsServerAdministrator role-based access control (RBAC) security groups, or a custom RBAC role that contains either of these two groups.</span></span>

2.  <span data-ttu-id="fac74-143">Abra el archivo de registro y haga clic en la pestaña **Mensajes**, seleccione una conversación en la vista de mensajes o seleccione un componente de seguimiento en la pestaña **Seguimiento**.</span><span class="sxs-lookup"><span data-stu-id="fac74-143">Open a log file and click the **Messages** tab, select a conversation in the messages view or select a trace component on the **Trace** tab.</span></span>

3.  <span data-ttu-id="fac74-144">Haga clic en **Flujo de llamada**.</span><span class="sxs-lookup"><span data-stu-id="fac74-144">Click **Call Flow**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="fac74-p109">Si hace clic en un mensaje o seguimiento que no forma parte de un flujo de llamada, el diagrama no aparecerá y un mensaje de estado en la parte inferior de Snooper indicará que "Este mensaje no es apto para el flujo de llamada". Elija otro mensaje o seguimiento, y el flujo de llamada aparecerá si el mensaje o seguimiento forma parte del flujo de llamada.</span><span class="sxs-lookup"><span data-stu-id="fac74-p109">If you click on a message or trace that is not part of a call flow, the diagram will not appear and a status message appears at the bottom of Snooper stating “This message is not eligible for callfow”. Choose another message or trace and the call flow will appear if the message or trace is part of a call flow.</span></span>

    
    </div>

4.  <span data-ttu-id="fac74-147">Desplácese por las líneas de mensajes o seguimientos y observe si el diagrama de flujo de llamada se actualiza o cambia para mostrar un diagrama nuevo.</span><span class="sxs-lookup"><span data-stu-id="fac74-147">Move through the Messages or the Trace lines and note whether the call flow diagram updates or changes to display a new diagram.</span></span>

5.  <span data-ttu-id="fac74-148">Pase el mouse por encima de los elementos para obtener información sobre los mensajes de llamadas, los extremos y otros componentes.</span><span class="sxs-lookup"><span data-stu-id="fac74-148">Hover over elements to get information about call messages, endpoints, and other components.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

