---
title: 'Lync Server 2013: lectura de registros de captura del servicio de registro centralizado'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Reading capture logs from the Centralized Logging Service
ms:assetid: c86ccf61-d86f-4ebd-b8d1-984a1b73005d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721879(v=OCS.15)
ms:contentKeyID: 49733813
ms.date: 12/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 55bfeaa5bc9a2e89d8c52529c5d05ae7e3ee8feb
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823731"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="reading-capture-logs-from-the-centralized-logging-service-in-lync-server-2013"></a><span data-ttu-id="2bcb4-102">Lectura de registros de captura del servicio de registro centralizado en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2bcb4-102">Reading capture logs from the Centralized Logging Service in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2bcb4-103">_**Última modificación del tema:** 2016-12-28_</span><span class="sxs-lookup"><span data-stu-id="2bcb4-103">_**Topic Last Modified:** 2016-12-28_</span></span>

<span data-ttu-id="2bcb4-104">Usted se da cuenta de la ventaja real del servicio de registro centralizado después de ejecutar la búsqueda y tiene un archivo que puede usar para realizar un seguimiento de un problema que se ha notificado.</span><span class="sxs-lookup"><span data-stu-id="2bcb4-104">You realize the real benefit of the Centralized Logging Service after you run the search and you have a file that you can use to track down a reported problem.</span></span> <span data-ttu-id="2bcb4-105">Hay varias formas de leer el archivo.</span><span class="sxs-lookup"><span data-stu-id="2bcb4-105">There are a number of ways that you can read the file.</span></span> <span data-ttu-id="2bcb4-106">El archivo de salida tiene un formato de texto estándar y puede usar Notepad.exe o cualquier otro programa que permita abrir y leer un archivo de texto.</span><span class="sxs-lookup"><span data-stu-id="2bcb4-106">The output file is in a standard text format and you can use Notepad.exe or any other programs that will allow you to open and read a text file.</span></span> <span data-ttu-id="2bcb4-107">En el caso de archivos más grandes y problemas más complejos, puede usar una herramienta como Snoop. exe, que está diseñada para leer y analizar los resultados del registro desde el servicio de registro centralizado.</span><span class="sxs-lookup"><span data-stu-id="2bcb4-107">For larger files and more complex issues, you could use a tool like Snooper.exe that is designed to read and parse the logging output from the Centralized Logging Service.</span></span> <span data-ttu-id="2bcb4-108">El Snoop se incluye con las herramientas de depuración de Lync Server 2013 que están disponibles como una descarga independiente.</span><span class="sxs-lookup"><span data-stu-id="2bcb4-108">Snooper is included with the Lync Server 2013 Debug Tools that are available as a separate download.</span></span> <span data-ttu-id="2bcb4-109">Puede descargar las herramientas de depuración de Lync Server [https://go.microsoft.com/fwlink/?LinkId=285257](https://go.microsoft.com/fwlink/?linkid=285257)2013:.</span><span class="sxs-lookup"><span data-stu-id="2bcb4-109">You can download the Lync Server 2013 Debug Tools here: [https://go.microsoft.com/fwlink/?LinkId=285257](https://go.microsoft.com/fwlink/?linkid=285257).</span></span> <span data-ttu-id="2bcb4-110">Al instalar las herramientas de depuración de Lync Server 2013, no se crean los puntos cortos ni los elementos de menú.</span><span class="sxs-lookup"><span data-stu-id="2bcb4-110">When you install the Lync Server 2013 Debug Tools, short cuts and menu items are not created.</span></span> <span data-ttu-id="2bcb4-111">Después de instalar las herramientas de depuración de Lync Server 2013, abra el explorador de Windows, una ventana de línea de comandos o un shell de administración de Lync Server y vaya\\al directorio\\(ubicación predeterminada)\\C: archivos de programa herramientas de depuración de Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2bcb4-111">After you install the Lync Server 2013 Debug Tools, open Windows Explorer, a command-line window, or Lync Server Management Shell and go to the directory (default location) C:\\Program Files\\Microsoft Lync Server 2013\\Debugging Tools.</span></span> <span data-ttu-id="2bcb4-112">Haga doble clic en Snoop. exe o escriba Snoop. exe y, a continuación, presione Entrar si está usando la línea de comandos o el shell de administración de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="2bcb4-112">Double-click Snooper.exe or type Snooper.exe, and then press ENTER if you are using the command line or Lync Server Management Shell.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="2bcb4-113">La finalidad de este tema no es dar información detallada ni tratar las técnicas de solución de problemas.</span><span class="sxs-lookup"><span data-stu-id="2bcb4-113">The intent of this topic is not to detail and discuss troubleshooting techniques.</span></span> <span data-ttu-id="2bcb4-114">La solución de problemas y los procesos relacionados con esta son un tema muy complejo.</span><span class="sxs-lookup"><span data-stu-id="2bcb4-114">Troubleshooting and the processes around it is a complex subject.</span></span> <span data-ttu-id="2bcb4-115">Para obtener detalles sobre la solución de problemas básicos y la solución de problemas de cargas de trabajo específicas, consulte el libro del <A href="http://go.microsoft.com/fwlink/p/?linkid=211003">https://go.microsoft.com/fwlink/p/?linkId=211003</A>kit de recursos de 2010 de Microsoft Lync Server en.</span><span class="sxs-lookup"><span data-stu-id="2bcb4-115">For details about troubleshooting basics and troubleshooting specific workloads, see the Microsoft Lync Server 2010 Resource Kit book at <A href="http://go.microsoft.com/fwlink/p/?linkid=211003">https://go.microsoft.com/fwlink/p/?linkId=211003</A>.</span></span> <span data-ttu-id="2bcb4-116">Los procesos y procedimientos siguen aplicándose a Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2bcb4-116">The processes and procedures still apply to Lync Server 2013.</span></span>



</div>

<span data-ttu-id="2bcb4-117">Lync Server 2013 introduce una versión actualizada del Snoop que incluye algunas características nuevas.</span><span class="sxs-lookup"><span data-stu-id="2bcb4-117">Lync Server 2013 introduces an updated version of Snooper that includes some new features.</span></span> <span data-ttu-id="2bcb4-118">La siguiente captura de pantalla muestra la versión del Snoop de Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="2bcb4-118">The following screen shot shows the version of Snooper from Office Communications Server 2007.</span></span>

<span data-ttu-id="2bcb4-119">![Office Communications 2007 versión del Snoop.] (images/JJ721879.129503a8-8edd-4bb0-a68f-c43f9a548b93(OCS.15).jpg "Office Communications 2007 versión del Snoop.")</span><span class="sxs-lookup"><span data-stu-id="2bcb4-119">![Office Communications 2007 version of Snooper.](images/JJ721879.129503a8-8edd-4bb0-a68f-c43f9a548b93(OCS.15).jpg "Office Communications 2007 version of Snooper.")</span></span>

<span data-ttu-id="2bcb4-120">La siguiente captura de pantalla muestra la nueva versión de Snoop, que se incluye en las herramientas de depuración de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2bcb4-120">The following screen shot shows the new version of Snooper included in the Lync Server 2013 Debug Tools.</span></span>

<span data-ttu-id="2bcb4-121">![Lync Server 2013 versión del Snoop.] (images/JJ721879.131495dd-8220-4ae4-af37-0ac5c318fd45(OCS.15).jpg "Lync Server 2013 versión del Snoop.")</span><span class="sxs-lookup"><span data-stu-id="2bcb4-121">![Lync Server 2013 version of Snooper.](images/JJ721879.131495dd-8220-4ae4-af37-0ac5c318fd45(OCS.15).jpg "Lync Server 2013 version of Snooper.")</span></span>

<span data-ttu-id="2bcb4-122">La siguiente captura de pantalla muestra la barra de herramientas con funciones usadas con frecuencia.</span><span class="sxs-lookup"><span data-stu-id="2bcb4-122">The following screen shot shows the toolbar with frequently used functions.</span></span>

<span data-ttu-id="2bcb4-123">![Barra de herramientas del 2013.] (images/JJ721879.989249c5-a33e-4251-b8b4-411019cc12b2(OCS.15).jpg "Barra de herramientas del 2013.")</span><span class="sxs-lookup"><span data-stu-id="2bcb4-123">![Snooper 2013 toolbar.](images/JJ721879.989249c5-a33e-4251-b8b4-411019cc12b2(OCS.15).jpg "Snooper 2013 toolbar.")</span></span>

<span data-ttu-id="2bcb4-124">Y la característica más reciente que agrega valor es la vista de diagrama de diagrama de flujo (flujo de llamadas).</span><span class="sxs-lookup"><span data-stu-id="2bcb4-124">And, the newest feature that adds value is the Flow Chart (call flow) diagram view.</span></span> <span data-ttu-id="2bcb4-125">Selecciona un flujo de mensajes en la pestaña **mensaje** y haz clic en el botón **flujo de llamadas** .</span><span class="sxs-lookup"><span data-stu-id="2bcb4-125">You select a message flow in the **Message** tab and click the **Call Flow** button.</span></span> <span data-ttu-id="2bcb4-126">A medida que avance por los mensajes, el diagrama de flujo de llamadas se actualizará con datos nuevos.</span><span class="sxs-lookup"><span data-stu-id="2bcb4-126">As you proceed through the messages, the call flow diagram updates with new data.</span></span>

<span data-ttu-id="2bcb4-127">![Diagrama de flujo de llamadas del snooper 2013.] (images/JJ721879.bb8be45d-a842-48fe-86f8-380207d70bab(OCS.15).jpg "Diagrama de flujo de llamadas del snooper 2013.")</span><span class="sxs-lookup"><span data-stu-id="2bcb4-127">![Snooper 2013 call flow diagram.](images/JJ721879.bb8be45d-a842-48fe-86f8-380207d70bab(OCS.15).jpg "Snooper 2013 call flow diagram.")</span></span>

<span data-ttu-id="2bcb4-128">Puede desplazar el puntero sobre la vista de diagrama y obtener detalles sobre los mensajes y el contenido de los flujos y mensajes, así como los elementos del servidor.</span><span class="sxs-lookup"><span data-stu-id="2bcb4-128">You can hover over the diagram view and get details about the messages and content of the flows and messages as well as the server elements.</span></span> <span data-ttu-id="2bcb4-129">Haga clic en cualquier flecha de flujo de llamadas para ir al mensaje en la vista mensajes.</span><span class="sxs-lookup"><span data-stu-id="2bcb4-129">Click on any call flow arrow to go to the message in the Messages view.</span></span>

<span data-ttu-id="2bcb4-130">![Detalles del mensaje del diagrama de flujo de llamadas.] (images/JJ721879.1147d720-38a9-4bda-8361-78f27ecde3d1(OCS.15).jpg "Detalles del mensaje del diagrama de flujo de llamadas.")</span><span class="sxs-lookup"><span data-stu-id="2bcb4-130">![Call flow diagram message details.](images/JJ721879.1147d720-38a9-4bda-8361-78f27ecde3d1(OCS.15).jpg "Call flow diagram message details.")</span></span>

<div>

## <a name="to-open-a-log-file-in-snooper"></a><span data-ttu-id="2bcb4-131">Para abrir un archivo de registro en Snooper</span><span class="sxs-lookup"><span data-stu-id="2bcb4-131">To open a log file in Snooper</span></span>

1.  <span data-ttu-id="2bcb4-p106">Para usar Snooper y abrir archivos de registro, necesita tener acceso de lectura a los archivos de registro. Para usar Snooper y tener acceso a los archivos de registro tiene que ser miembro de los grupos de seguridad de control de acceso basado en roles (RBAC) CsAdministrator o CsServerAdministrator, o de un rol RBAC personalizado que contenga cualquiera de estos dos grupos.</span><span class="sxs-lookup"><span data-stu-id="2bcb4-p106">To use Snooper and open log files, you need read access to the log files. To use Snooper and access the log files you must be a member of the CsAdministrator or the CsServerAdministrator role-based access control (RBAC) security groups, or a custom RBAC role that contains either of these two groups.</span></span>

2.  <span data-ttu-id="2bcb4-134">Después de la instalación de las herramientas de depuración de Lync Server (LyncDebugTools. msi), cambie el directorio a la ubicación de Snoop. exe con el explorador de Windows o desde la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="2bcb4-134">After the installation of the Lync Server Debugging Tools (LyncDebugTools.msi), change directory to the location of Snooper.exe using Windows Explorer or from the command line.</span></span> <span data-ttu-id="2bcb4-135">De forma predeterminada, las herramientas de depuración se encuentran\\en C\\: archivos de programa\\herramientas de depuración de Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2bcb4-135">By default, the debugging tools are located in C:\\Program Files\\Microsoft Lync Server 2013\\Debugging Tools.</span></span> <span data-ttu-id="2bcb4-136">Haga doble clic en Snooper.exe o ejecútelo.</span><span class="sxs-lookup"><span data-stu-id="2bcb4-136">Double-click or run Snooper.exe.</span></span>

3.  <span data-ttu-id="2bcb4-137">Tras abrir Snooper, haga clic con el botón secundario en **Archivo**, haga clic en **Abrir archivo**, localice los archivos de registro, seleccione un archivo en el cuadro de diálogo **Abrir** y haga clic en **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="2bcb4-137">After Snooper is open, right-click **File**, click **OpenFile**, find your log files, select a file in the **Open** dialog box, and then click **Open**.</span></span>

4.  <span data-ttu-id="2bcb4-138">Los mensajes de **Seguimiento** del archivo de registro se muestran en la pestaña **Seguimiento**. Haga clic en la pestaña **Mensajes** para ver el contenido de los mensajes de los seguimientos recopilados.</span><span class="sxs-lookup"><span data-stu-id="2bcb4-138">The log file’s **Trace** messages are displayed on the **Trace** tab. Click the **Messages** tab to view the message contents of the collected traces.</span></span>

</div>

<div>

## <a name="to-display-a-call-flow-diagram"></a><span data-ttu-id="2bcb4-139">Para mostrar un diagrama de flujo de llamada</span><span class="sxs-lookup"><span data-stu-id="2bcb4-139">To display a call flow diagram</span></span>

1.  <span data-ttu-id="2bcb4-p108">Para usar Snooper y abrir archivos de registro, necesita tener acceso de lectura a los archivos de registro. Para usar Snooper y tener acceso a los archivos de registro es preciso ser miembro de los grupos de seguridad de control de acceso basado en roles (RBAC) CsAdministrator o CsServerAdministrator, o de un rol RBAC personalizado que contenga cualquiera de estos dos grupos.</span><span class="sxs-lookup"><span data-stu-id="2bcb4-p108">To use Snooper and open log files, you need read access to the log files. To use Snooper and access the log files, you need to be a member of the CsAdministrator or the CsServerAdministrator role-based access control (RBAC) security groups, or a custom RBAC role that contains either of these two groups.</span></span>

2.  <span data-ttu-id="2bcb4-142">Abra el archivo de registro y haga clic en la pestaña **Mensajes**, seleccione una conversación en la vista de mensajes o seleccione un componente de seguimiento en la pestaña **Seguimiento**.</span><span class="sxs-lookup"><span data-stu-id="2bcb4-142">Open a log file and click the **Messages** tab, select a conversation in the messages view or select a trace component on the **Trace** tab.</span></span>

3.  <span data-ttu-id="2bcb4-143">Haga clic en **Flujo de llamada**.</span><span class="sxs-lookup"><span data-stu-id="2bcb4-143">Click **Call Flow**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="2bcb4-p109">Si hace clic en un mensaje o seguimiento que no forma parte de un flujo de llamada, el diagrama no aparecerá y un mensaje de estado en la parte inferior de Snooper indicará que "Este mensaje no es apto para el flujo de llamada". Elija otro mensaje o seguimiento, y el flujo de llamada aparecerá si el mensaje o seguimiento forma parte del flujo de llamada.</span><span class="sxs-lookup"><span data-stu-id="2bcb4-p109">If you click on a message or trace that is not part of a call flow, the diagram will not appear and a status message appears at the bottom of Snooper stating “This message is not eligible for callfow”. Choose another message or trace and the call flow will appear if the message or trace is part of a call flow.</span></span>

    
    </div>

4.  <span data-ttu-id="2bcb4-146">Desplácese por las líneas de mensajes o seguimientos y observe si el diagrama de flujo de llamada se actualiza o cambia para mostrar un diagrama nuevo.</span><span class="sxs-lookup"><span data-stu-id="2bcb4-146">Move through the Messages or the Trace lines and note whether the call flow diagram updates or changes to display a new diagram.</span></span>

5.  <span data-ttu-id="2bcb4-147">Pase el mouse por encima de los elementos para obtener información sobre los mensajes de llamadas, los extremos y otros componentes.</span><span class="sxs-lookup"><span data-stu-id="2bcb4-147">Hover over elements to get information about call messages, endpoints, and other components.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

