---
title: 'Lync Server 2013: importación de los módulos de administración de Lync Server 2013'
description: 'Lync Server 2013: importación de los paquetes de administración de Lync Server 2013.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Importing the Lync Server 2013 management packs
ms:assetid: 846287e1-660f-453f-bdba-b2137b5f0ea1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205052(v=OCS.15)
ms:contentKeyID: 48184690
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c9615e559baf2f1c8b99015f1e407230559ff770
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547786"
---
# <a name="importing-the-lync-server-2013-management-packs"></a><span data-ttu-id="5f1c9-103">Importación de los paquetes de administración de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5f1c9-103">Importing the Lync Server 2013 management packs</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5f1c9-104">_**Última modificación del tema:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="5f1c9-104">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="5f1c9-105">Puede ampliar las capacidades de System Center Operations Manager mediante la instalación de paquetes de administración: software que determina qué elementos puede supervisar System Center Operations Manager y cómo se deben supervisar esos elementos y cómo se deben desencadenar y notificar las alertas.</span><span class="sxs-lookup"><span data-stu-id="5f1c9-105">You can extend the capabilities of System Center Operations Manager by installing management packs—software that dictates which items System Center Operations Manager can monitor, and how those items should be monitored and how alerts should be triggered and reported.</span></span> <span data-ttu-id="5f1c9-106">Lync Server 2013 incluye dos paquetes de administración de System Center Operations Manager que proporcionan las siguientes capacidades:</span><span class="sxs-lookup"><span data-stu-id="5f1c9-106">Lync Server 2013 includes two System Center Operations Manager management packs that provide the following capabilities:</span></span>

  - <span data-ttu-id="5f1c9-107">El componente y el módulo de administración de usuarios (Microsoft.LS.2013.Monitoring.ComponentAndUser.mp) realiza un seguimiento de los problemas de Lync Server registrados en registros de eventos, registrados por los contadores de rendimiento o registrados en las bases de datos de registros de detalles de llamadas (CDR) o de calidad de la experiencia (QoE).</span><span class="sxs-lookup"><span data-stu-id="5f1c9-107">The Component and User Management Pack (Microsoft.LS.2013.Monitoring.ComponentAndUser.mp) tracks Lync Server issues recorded in event logs, registered by performance counters, or logged in the call detail records (CDR) or the Quality of Experience (QoE) databases.</span></span> <span data-ttu-id="5f1c9-108">Para los problemas críticos, System Center Operations Manager se puede configurar para que notifique inmediatamente a los administradores a través de mensajes de correo electrónico, mensajes instantáneos o servicio de mensajes cortos (SMS).</span><span class="sxs-lookup"><span data-stu-id="5f1c9-108">For critical problems, System Center Operations Manager can be configured to immediately notify administrators via email, instant message, or Short Message Service (SMS) messaging.</span></span> <span data-ttu-id="5f1c9-109">SMS es la tecnología usada para enviar mensajes de texto desde un dispositivo móvil a otro).</span><span class="sxs-lookup"><span data-stu-id="5f1c9-109">SMS is the technology used to send text messages from one mobile device to another.)</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="5f1c9-110">Para obtener más información sobre cómo configurar la notificación de Operations Manager, vea la notificación de configuración en la biblioteca de TechNet en <A href="https://go.microsoft.com/fwlink/p/?linkid=268785">https://go.microsoft.com/fwlink/p/?LinkId=268785</A> .</span><span class="sxs-lookup"><span data-stu-id="5f1c9-110">For details about configuring Operations Manager notification, see the Configuring Notification in the TechNet Library at <A href="https://go.microsoft.com/fwlink/p/?linkid=268785">https://go.microsoft.com/fwlink/p/?LinkId=268785</A>.</span></span>

    
    </div>

  - <span data-ttu-id="5f1c9-111">El módulo de administración de supervisión activa (Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp) comprueba proactivamente los componentes clave de Lync Server, como iniciar sesión en el sistema, intercambiar mensajes instantáneos o realizar llamadas a un teléfono ubicado en la red telefónica conmutada (RTC).</span><span class="sxs-lookup"><span data-stu-id="5f1c9-111">The Active Monitoring Management Pack (Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp) proactively tests key Lync Server components such as signing into to the system, exchanging instant messages, or making calls to a phone located on the public switched telephone network (PSTN).</span></span> <span data-ttu-id="5f1c9-112">Estas pruebas se llevan a cabo con los cmdlets de transacciones sintéticas de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="5f1c9-112">These tests are conducted using the Lync Server synthetic transaction cmdlets.</span></span> <span data-ttu-id="5f1c9-113">Por ejemplo, puede usar el cmdlet **Test-CsIM** para simular una conversación por mensaje instantáneo (IM) entre un par de usuarios de prueba.</span><span class="sxs-lookup"><span data-stu-id="5f1c9-113">For example, you can use the **Test-CsIM** cmdlet to simulate an instant messaging (IM) conversation between a pair of test users.</span></span> <span data-ttu-id="5f1c9-114">Si esta conversación de mensajes simulados falla, se genera una alerta.</span><span class="sxs-lookup"><span data-stu-id="5f1c9-114">If this simulated messaging conversation fails an alert is generated.</span></span>

<span data-ttu-id="5f1c9-115">Debe importar los paquetes de administración.</span><span class="sxs-lookup"><span data-stu-id="5f1c9-115">You need to import the management packs.</span></span> <span data-ttu-id="5f1c9-116">Si no importa los paquetes de administración, no puede usar Operations Manager para supervisar los eventos de Lync Server ni ejecutar transacciones sintéticas de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="5f1c9-116">If you do not import the management packs, you cannot use Operations Manager to monitor Lync Server events or run Lync Server synthetic transactions.</span></span>

<span data-ttu-id="5f1c9-117">El módulo de administración de componentes y usuarios solo se usa para supervisar Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5f1c9-117">The Component and User Management Pack is only used to monitor Lync Server 2013.</span></span> <span data-ttu-id="5f1c9-118">Si está en un escenario de coexistencia, donde tiene instalados tanto Lync Server 2013 como Lync Server 2010, debe seguir usando los paquetes de administración de Lync Server 2010 para los equipos con Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="5f1c9-118">If you are in a coexistence scenario, where you have both Lync Server 2013 and Lync Server 2010 installed, you should continue to use the Lync Server 2010 management packs for your Lync Server 2010 computers.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="5f1c9-119">Los módulos de administración para Lync Server 2010 incluyen el módulo de administración de supervisión de Lync Server 2010 y el módulo de administración de supervisión de chat de grupo de Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="5f1c9-119">Management packs for Lync Server 2010 include the Lync Server 2010 Monitoring Management Pack and the Lync Server 2010 Group Chat Monitoring Management Pack.</span></span>



</div>

<span data-ttu-id="5f1c9-120">Puede usar una de las siguientes herramientas para importar los paquetes de administración:</span><span class="sxs-lookup"><span data-stu-id="5f1c9-120">You can use one of the following tools to import management packs:</span></span>

  - <span data-ttu-id="5f1c9-121">**System Center Operations Manager**     Con este método, se usa Operations Manager para agregar supervisión para Lync Server.</span><span class="sxs-lookup"><span data-stu-id="5f1c9-121">**System Center Operations Manager**   With this method, you use the Operations Manager to add monitoring for Lync Server.</span></span>

  - <span data-ttu-id="5f1c9-122">Shell de Operations **Manager**     Puede usar el shell de Operations Manager para importar directamente o para solucionar los problemas que se encuentren al importar los paquetes de administración mediante la consola de System Center Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="5f1c9-122">**Operations Manager Shell**   You can use the Operations Manager Shell to import directly or to troubleshoot any issues you encounter when you import management packs by using the System Center Operations Manager console.</span></span>

<div>

## <a name="importing-the-management-packs-by-using-system-center-operations-manager"></a><span data-ttu-id="5f1c9-123">Importación de los paquetes de administración mediante System Center Operations Manager</span><span class="sxs-lookup"><span data-stu-id="5f1c9-123">Importing the Management Packs by Using System Center Operations Manager</span></span>

1.  <span data-ttu-id="5f1c9-124">Descargue los archivos Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp y Microsoft.LS.2013.Monitoring.ComponentAndUser.mp.</span><span class="sxs-lookup"><span data-stu-id="5f1c9-124">Download the files Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp and Microsoft.LS.2013.Monitoring.ComponentAndUser.mp.</span></span>

2.  <span data-ttu-id="5f1c9-125">En System Center Operations Manager, haga clic en **Administración**.</span><span class="sxs-lookup"><span data-stu-id="5f1c9-125">In System Center Operations Manager, click **Administration**.</span></span>

3.  <span data-ttu-id="5f1c9-126">En el panel **Administración**, haga clic con el botón secundario en **Paquetes de administración** y luego haga clic en **Importar paquetes de administración**.</span><span class="sxs-lookup"><span data-stu-id="5f1c9-126">In the **Administration** pane, right-click **Management Packs**, and then click **Import Management Packs**.</span></span>

4.  <span data-ttu-id="5f1c9-127">En el cuadro de diálogo **Seleccionar paquetes de administración**, haga clic en **Agregar** y luego en **Agregar desde el disco**.</span><span class="sxs-lookup"><span data-stu-id="5f1c9-127">In the **Select Management Packs** dialog box, click **Add**, and then click **Add from disk**.</span></span>

5.  <span data-ttu-id="5f1c9-128">En el cuadro de diálogo **conexión al catálogo en línea** , haga clic en **Cancelar** para evitar que Operations Manager se conecte para ver si existe alguna dependencia para los paquetes de administración de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="5f1c9-128">In the **Online Catalog Connection** dialog box, click **Cancel** to prevent Operations Manager from going online to see if any dependencies exist for the Lync Server management packs.</span></span> <span data-ttu-id="5f1c9-129">Si usa System Center Operations Manager 2012, haga clic en **no**.</span><span class="sxs-lookup"><span data-stu-id="5f1c9-129">If you are using System Center Operations Manager 2012, click **No**.</span></span>

6.  <span data-ttu-id="5f1c9-p107">En el cuadro de diálogo **Seleccionar paquetes de administración a importar**, encuentre y seleccione los archivos **Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp** y **Microsoft.LS.2013.Monitoring.ComponentAndUser.mp** y luego haga clic en **Abrir**. para seleccionar varios archivos en el cuadro de diálogo haga clic en el primer archivo, mantenga presionada la tecla Ctrl y haga clic en el segundo archivo.</span><span class="sxs-lookup"><span data-stu-id="5f1c9-p107">In the **Select Management Packs to import** dialog box, locate and select the files **Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp** and **Microsoft.LS.2013.Monitoring.ComponentAndUser.mp** and then click **Open**. To select multiple files in the dialog box, click the first file, hold down the Ctrl key and then click the second file.</span></span>

7.  <span data-ttu-id="5f1c9-p108">En el cuadro de diálogo **Seleccionar paquetes de administración**, haga clic en **Instalar**. Si obtiene un mensaje de error y no se puede producir la instalación, que generalmente significa que los archivos del paquete de administración se encuentran en una carpeta protegida por el control de cuentas de usuario de Windows. Si esto sucede, copie los archivos a una carpeta diferente y luego reinicie el proceso de importación e instalación.</span><span class="sxs-lookup"><span data-stu-id="5f1c9-p108">In the **Select Management Packs** dialog box, click **Install**. If you get an error message and installation fails, that typically means that the management pack files are in a folder protected by the Windows User Account Control. If this occurs, copy the files to a different folder and then restart the import and installation process.</span></span>

8.  <span data-ttu-id="5f1c9-p109">En el cuadro de diálogo **Seleccionar paquetes de administración**, haga clic en **Cerrar**. Tenga en cuenta que el proceso de instalación e importación puede requerir algunos minutos para completarse.</span><span class="sxs-lookup"><span data-stu-id="5f1c9-p109">In the **Select Management Packs** dialog box, click **Close**. Note that the import and installation process might require several minutes to complete.</span></span>

</div>

<div>

## <a name="importing-management-packs-by-using-the-operations-manager-shell"></a><span data-ttu-id="5f1c9-137">Importación de paquetes de administración mediante el shell de Operations Manager</span><span class="sxs-lookup"><span data-stu-id="5f1c9-137">Importing Management Packs by Using the Operations Manager Shell</span></span>

<span data-ttu-id="5f1c9-138">En general, es más fácil importar los paquetes de administración mediante Operations Manager. sin embargo, si se produce un error y se produce un error en la importación, la consola no siempre proporciona los informes de error adecuados.</span><span class="sxs-lookup"><span data-stu-id="5f1c9-138">In general it is easier to import the management packs by using the Operations Manager.However, if an error occurs and the import fails, the console does not always provide adequate error reports.</span></span> <span data-ttu-id="5f1c9-139">Por comparación, el shell de Operations Manager proporciona información detallada.</span><span class="sxs-lookup"><span data-stu-id="5f1c9-139">By comparison, the Operations Manager Shell, provides detailed information.</span></span> <span data-ttu-id="5f1c9-140">Si está usando Operations Manager y tiene problemas para importar un módulo de administración, importe el paquete mediante el shell de Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="5f1c9-140">If you are using Operations Manager and you run into problems importing a management pack, import the pack by using the Operations Manager Shell .</span></span> <span data-ttu-id="5f1c9-141">El shell de Operations Manager proporciona más información que puede ayudarle a determinar por qué se produjo un error en la importación.</span><span class="sxs-lookup"><span data-stu-id="5f1c9-141">The Operations Manager Shell provides more information that might help you determine why the import failed.</span></span>

<span data-ttu-id="5f1c9-142">Si usa System Center Operations Manager 2007 R2, complete el siguiente procedimiento:</span><span class="sxs-lookup"><span data-stu-id="5f1c9-142">If you are using System Center Operations Manager 2007 R2, complete the following procedure:</span></span>

1.  <span data-ttu-id="5f1c9-143">Haga clic en **Inicio**, en **todos los programas**, haga clic en **System Center Operations Manager 2007 R2**y, a continuación, haga clic en **Shell de Operations Manager**.</span><span class="sxs-lookup"><span data-stu-id="5f1c9-143">Click **Start**, click **All Programs**, click **System Center Operations Manager 2007 R2**, and then click **Operations Manager Shell**.</span></span>

2.  <span data-ttu-id="5f1c9-144">En el shell de Operations Manager, escriba el siguiente comando en el símbolo del sistema, con la ruta de acceso real a su copia del archivo Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp y, a continuación, presione ENTRAR:</span><span class="sxs-lookup"><span data-stu-id="5f1c9-144">In the Operations Manager Shell, type the following command at the command prompt, using the actual path to your copy of the file Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp, and then press ENTER:</span></span>
    
        MPImport.exe D:\MP\Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp

3.  <span data-ttu-id="5f1c9-145">Después de importar el primer paquete de administración, repita el proceso usando la ruta a su copia del archivo Microsoft.LS.2013.Monitoring.ComponentAndUser.mp:</span><span class="sxs-lookup"><span data-stu-id="5f1c9-145">After you import the first management pack, repeat the process using the path to your copy of the file Microsoft.LS.2013.Monitoring.ComponentAndUser.mp:</span></span>
    
        MPImport.exe D:\MP\Microsoft.LS.2013.Monitoring.ComponentAndUser.mp

4.  <span data-ttu-id="5f1c9-146">Cierre el shell de Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="5f1c9-146">Close the Operations Manager Shell.</span></span>

<span data-ttu-id="5f1c9-147">Si usa System Center Operations Manager 2012, complete este procedimiento en su lugar:</span><span class="sxs-lookup"><span data-stu-id="5f1c9-147">If you are using System Center Operations Manager 2012, complete this procedure instead:</span></span>

1.  <span data-ttu-id="5f1c9-148">Haga clic en **Inicio**, en **todos los programas**, en **Microsoft System Center 2012**, haga clic en **Operations Manager**y, a continuación, haga clic en **Shell de Operations Manager**.</span><span class="sxs-lookup"><span data-stu-id="5f1c9-148">Click **Start**, click **All Programs**, click **Microsoft System Center 2012**, click **Operations Manager**, and then click **Operations Manager Shell**.</span></span>

2.  <span data-ttu-id="5f1c9-149">En el shell de Operations Manager, escriba el siguiente comando en el símbolo del sistema, con la ruta de acceso real a su copia del archivo Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp y, a continuación, presione ENTRAR:</span><span class="sxs-lookup"><span data-stu-id="5f1c9-149">In the Operations Manager Shell, type the following command at the command prompt, using the actual path to your copy of the file Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp, and then press ENTER:</span></span>
    
        Import-SCOMManagementPack -FullName "D:\MP\ Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp"

3.  <span data-ttu-id="5f1c9-150">Después de haber importado el primer paquete de administración, repita el proceso usando la ruta a su copia del archivo Microsoft.LS.2013.Monitoring.ComponentAndUser.mp:</span><span class="sxs-lookup"><span data-stu-id="5f1c9-150">After you have imported the first management pack, repeat the process using the path to your copy of the file Microsoft.LS.2013.Monitoring.ComponentAndUser.mp:</span></span>
    
        Import-SCOMManagementPack -FullName "D:\MP\ Microsoft.LS.2013.Monitoring.ComponentAndUser.mp"

</div>

</div>

<span> </span>

</div>

</div>

</div>

