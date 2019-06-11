---
title: 'Lync Server 2013: importación de los módulos de administración de Lync Server 2013'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Importing the Lync Server 2013 management packs
ms:assetid: 846287e1-660f-453f-bdba-b2137b5f0ea1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205052(v=OCS.15)
ms:contentKeyID: 48184690
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 70c753334ea9a046c6081a73ce70e4de00de9188
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34835022"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="importing-the-lync-server-2013-management-packs"></a><span data-ttu-id="6bf3f-102">Importar los módulos de administración de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6bf3f-102">Importing the Lync Server 2013 management packs</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6bf3f-103">_**Última modificación del tema:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="6bf3f-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="6bf3f-104">Puede ampliar las capacidades de System Center Operations Manager mediante la instalación de paquetes de administración, es decir, el software que determina qué elementos puede supervisar System Center Operations Manager y cómo se deben supervisar esos elementos y cómo se deben desencadenar alertas y registrados.</span><span class="sxs-lookup"><span data-stu-id="6bf3f-104">You can extend the capabilities of System Center Operations Manager by installing management packs—software that dictates which items System Center Operations Manager can monitor, and how those items should be monitored and how alerts should be triggered and reported.</span></span> <span data-ttu-id="6bf3f-105">Lync Server 2013 incluye dos módulos de administración de System Center Operations Manager que proporcionan las siguientes características:</span><span class="sxs-lookup"><span data-stu-id="6bf3f-105">Lync Server 2013 includes two System Center Operations Manager management packs that provide the following capabilities:</span></span>

  - <span data-ttu-id="6bf3f-106">El componente y el paquete de administración de usuario (Microsoft.LS.2013.Monitoring.ComponentAndUser.mp) realiza un seguimiento de los problemas de Lync Server registrados en registros de eventos, registrados por contadores de rendimiento o registrados en los registros de detalles de llamadas (CDR) o la calidad de la experiencia (QoE). bases.</span><span class="sxs-lookup"><span data-stu-id="6bf3f-106">The Component and User Management Pack (Microsoft.LS.2013.Monitoring.ComponentAndUser.mp) tracks Lync Server issues recorded in event logs, registered by performance counters, or logged in the call detail records (CDR) or the Quality of Experience (QoE) databases.</span></span> <span data-ttu-id="6bf3f-107">En el caso de problemas críticos, System Center Operations Manager se puede configurar para que notifiquen inmediatamente a los administradores a través de mensajes de correo electrónico, mensajes instantáneos o mensajes SMS.</span><span class="sxs-lookup"><span data-stu-id="6bf3f-107">For critical problems, System Center Operations Manager can be configured to immediately notify administrators via email, instant message, or Short Message Service (SMS) messaging.</span></span> <span data-ttu-id="6bf3f-108">SMS es la tecnología que se usa para enviar mensajes de texto desde un dispositivo móvil a otro.)</span><span class="sxs-lookup"><span data-stu-id="6bf3f-108">SMS is the technology used to send text messages from one mobile device to another.)</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="6bf3f-109">Para obtener más información sobre cómo configurar las notificaciones de Operations Manager, consulte la <A href="http://go.microsoft.com/fwlink/p/?linkid=268785">http://go.microsoft.com/fwlink/p/?LinkId=268785</A>notificación de configuración en la biblioteca de TechNet en.</span><span class="sxs-lookup"><span data-stu-id="6bf3f-109">For details about configuring Operations Manager notification, see the Configuring Notification in the TechNet Library at <A href="http://go.microsoft.com/fwlink/p/?linkid=268785">http://go.microsoft.com/fwlink/p/?LinkId=268785</A>.</span></span>

    
    </div>

  - <span data-ttu-id="6bf3f-110">El módulo de administración de supervisión activa (Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp) prueba de forma proactiva componentes de Lync Server clave como iniciar sesión en el sistema, intercambiar mensajes instantáneos o hacer llamadas a un teléfono que se encuentra en la conmutación pública red telefónica (RTC).</span><span class="sxs-lookup"><span data-stu-id="6bf3f-110">The Active Monitoring Management Pack (Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp) proactively tests key Lync Server components such as signing into to the system, exchanging instant messages, or making calls to a phone located on the public switched telephone network (PSTN).</span></span> <span data-ttu-id="6bf3f-111">Estas pruebas se realizan mediante los cmdlets de transacciones sintéticas de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="6bf3f-111">These tests are conducted using the Lync Server synthetic transaction cmdlets.</span></span> <span data-ttu-id="6bf3f-112">Por ejemplo, puede usar el cmdlet **Test-CsIM** para simular una conversación de mensajería instantánea (mi) entre dos usuarios de prueba.</span><span class="sxs-lookup"><span data-stu-id="6bf3f-112">For example, you can use the **Test-CsIM** cmdlet to simulate an instant messaging (IM) conversation between a pair of test users.</span></span> <span data-ttu-id="6bf3f-113">Si se produce un error en esta conversación de mensajería simulada, se genera una alerta.</span><span class="sxs-lookup"><span data-stu-id="6bf3f-113">If this simulated messaging conversation fails an alert is generated.</span></span>

<span data-ttu-id="6bf3f-114">Debe importar los paquetes de administración.</span><span class="sxs-lookup"><span data-stu-id="6bf3f-114">You need to import the management packs.</span></span> <span data-ttu-id="6bf3f-115">Si no importa los paquetes de administración, no puede usar Operations Manager para supervisar los eventos de Lync Server o ejecutar transacciones sintéticas de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="6bf3f-115">If you do not import the management packs, you cannot use Operations Manager to monitor Lync Server events or run Lync Server synthetic transactions.</span></span>

<span data-ttu-id="6bf3f-116">El paquete de administración de componentes y usuarios solo se usa para supervisar Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6bf3f-116">The Component and User Management Pack is only used to monitor Lync Server 2013.</span></span> <span data-ttu-id="6bf3f-117">Si se encuentran en un escenario de coexistencia, donde tiene instalado Lync Server 2013 y Lync Server 2010, debe seguir usando los paquetes de administración de Lync Server 2010 para sus equipos de Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="6bf3f-117">If you are in a coexistence scenario, where you have both Lync Server 2013 and Lync Server 2010 installed, you should continue to use the Lync Server 2010 management packs for your Lync Server 2010 computers.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="6bf3f-118">Los módulos de administración para Lync Server 2010 incluyen el módulo de administración de supervisión de Lync Server 2010 y el módulo de administración de supervisión de chat de Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="6bf3f-118">Management packs for Lync Server 2010 include the Lync Server 2010 Monitoring Management Pack and the Lync Server 2010 Group Chat Monitoring Management Pack.</span></span>



</div>

<span data-ttu-id="6bf3f-119">Puede usar una de las siguientes herramientas para importar los paquetes de administración:</span><span class="sxs-lookup"><span data-stu-id="6bf3f-119">You can use one of the following tools to import management packs:</span></span>

  - <span data-ttu-id="6bf3f-120">**System Center Operations Manager**   con este método, se usa el Operations Manager para agregar la supervisión de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="6bf3f-120">**System Center Operations Manager**   With this method, you use the Operations Manager to add monitoring for Lync Server.</span></span>

  - <span data-ttu-id="6bf3f-121">**Shell de Operations Manager**   puede usar el shell de Operations Manager para importar directamente o para solucionar cualquier problema que encuentre al importar paquetes de administración mediante la consola de System Center Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="6bf3f-121">**Operations Manager Shell**   You can use the Operations Manager Shell to import directly or to troubleshoot any issues you encounter when you import management packs by using the System Center Operations Manager console.</span></span>

<div>

## <a name="importing-the-management-packs-by-using-system-center-operations-manager"></a><span data-ttu-id="6bf3f-122">Importación de los módulos de administración mediante System Center Operations Manager</span><span class="sxs-lookup"><span data-stu-id="6bf3f-122">Importing the Management Packs by Using System Center Operations Manager</span></span>

1.  <span data-ttu-id="6bf3f-123">Descargue los archivos Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp y Microsoft.LS.2013.Monitoring.ComponentAndUser.mp.</span><span class="sxs-lookup"><span data-stu-id="6bf3f-123">Download the files Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp and Microsoft.LS.2013.Monitoring.ComponentAndUser.mp.</span></span>

2.  <span data-ttu-id="6bf3f-124">En System Center Operations Manager, haga clic en **Administración**.</span><span class="sxs-lookup"><span data-stu-id="6bf3f-124">In System Center Operations Manager, click **Administration**.</span></span>

3.  <span data-ttu-id="6bf3f-125">En el panel **Administración** , haga clic con el botón secundario en **módulos**de administración y luego haga clic en **importar módulos de administración**.</span><span class="sxs-lookup"><span data-stu-id="6bf3f-125">In the **Administration** pane, right-click **Management Packs**, and then click **Import Management Packs**.</span></span>

4.  <span data-ttu-id="6bf3f-126">En el cuadro de diálogo **Seleccionar módulos de administración**, haga clic en **Agregar** y luego en **Agregar desde el disco**.</span><span class="sxs-lookup"><span data-stu-id="6bf3f-126">In the **Select Management Packs** dialog box, click **Add**, and then click **Add from disk**.</span></span>

5.  <span data-ttu-id="6bf3f-127">En el cuadro de diálogo **conexión al catálogo en línea** , haga clic en **Cancelar** para evitar que Operations Manager se conecte para ver si hay alguna dependencia para los paquetes de administración de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="6bf3f-127">In the **Online Catalog Connection** dialog box, click **Cancel** to prevent Operations Manager from going online to see if any dependencies exist for the Lync Server management packs.</span></span> <span data-ttu-id="6bf3f-128">Si está usando System Center Operations Manager 2012, haga clic en **no**.</span><span class="sxs-lookup"><span data-stu-id="6bf3f-128">If you are using System Center Operations Manager 2012, click **No**.</span></span>

6.  <span data-ttu-id="6bf3f-129">En el cuadro de diálogo **seleccionar módulos de administración para importar** , busque y seleccione los archivos **Microsoft.LS.2013.Monitoring.ActiveMonitoring.MP** y **Microsoft.LS.2013.Monitoring.ComponentAndUser.MP** y, a continuación, haga clic en **abrir**.</span><span class="sxs-lookup"><span data-stu-id="6bf3f-129">In the **Select Management Packs to import** dialog box, locate and select the files **Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp** and **Microsoft.LS.2013.Monitoring.ComponentAndUser.mp** and then click **Open**.</span></span> <span data-ttu-id="6bf3f-130">Para seleccionar varios archivos en el cuadro de diálogo, haga clic en el primer archivo, mantenga presionada la tecla Ctrl y, a continuación, haga clic en el segundo archivo.</span><span class="sxs-lookup"><span data-stu-id="6bf3f-130">To select multiple files in the dialog box, click the first file, hold down the Ctrl key and then click the second file.</span></span>

7.  <span data-ttu-id="6bf3f-131">En el cuadro de diálogo **Seleccionar módulos de administración**, haga clic en **Instalar**.</span><span class="sxs-lookup"><span data-stu-id="6bf3f-131">In the **Select Management Packs** dialog box, click **Install**.</span></span> <span data-ttu-id="6bf3f-132">Si obtiene un mensaje de error y no se puede realizar la instalación, generalmente significa que los archivos del módulo de administración se encuentran en una carpeta protegida por el control de cuentas de usuario de Windows.</span><span class="sxs-lookup"><span data-stu-id="6bf3f-132">If you get an error message and installation fails, that typically means that the management pack files are in a folder protected by the Windows User Account Control.</span></span> <span data-ttu-id="6bf3f-133">Si esto sucede, copie los archivos en una carpeta diferente y, a continuación, reinicie el proceso de importación e instalación.</span><span class="sxs-lookup"><span data-stu-id="6bf3f-133">If this occurs, copy the files to a different folder and then restart the import and installation process.</span></span>

8.  <span data-ttu-id="6bf3f-134">En el cuadro de diálogo **Seleccionar módulos de administración**, haga clic en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="6bf3f-134">In the **Select Management Packs** dialog box, click **Close**.</span></span> <span data-ttu-id="6bf3f-135">Tenga en cuenta que el proceso de importación e instalación puede tardar varios minutos en completarse.</span><span class="sxs-lookup"><span data-stu-id="6bf3f-135">Note that the import and installation process might require several minutes to complete.</span></span>

</div>

<div>

## <a name="importing-management-packs-by-using-the-operations-manager-shell"></a><span data-ttu-id="6bf3f-136">Importar paquetes de administración mediante el shell de Operations Manager</span><span class="sxs-lookup"><span data-stu-id="6bf3f-136">Importing Management Packs by Using the Operations Manager Shell</span></span>

<span data-ttu-id="6bf3f-137">En general, es más fácil importar los paquetes de administración mediante Operations Manager. sin embargo, si se produce un error y se produce un error en la importación, la consola no siempre proporciona los informes de errores adecuados.</span><span class="sxs-lookup"><span data-stu-id="6bf3f-137">In general it is easier to import the management packs by using the Operations Manager.However, if an error occurs and the import fails, the console does not always provide adequate error reports.</span></span> <span data-ttu-id="6bf3f-138">En comparación, el shell de Operations Manager proporciona información detallada.</span><span class="sxs-lookup"><span data-stu-id="6bf3f-138">By comparison, the Operations Manager Shell, provides detailed information.</span></span> <span data-ttu-id="6bf3f-139">Si está usando Operations Manager y tiene problemas para importar un paquete de administración, importe el paquete mediante el shell de Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="6bf3f-139">If you are using Operations Manager and you run into problems importing a management pack, import the pack by using the Operations Manager Shell .</span></span> <span data-ttu-id="6bf3f-140">El shell de Operations Manager proporciona más información que puede ayudarle a determinar por qué se produjo un error en la importación.</span><span class="sxs-lookup"><span data-stu-id="6bf3f-140">The Operations Manager Shell provides more information that might help you determine why the import failed.</span></span>

<span data-ttu-id="6bf3f-141">Si está usando System Center Operations Manager 2007 R2, complete el siguiente procedimiento:</span><span class="sxs-lookup"><span data-stu-id="6bf3f-141">If you are using System Center Operations Manager 2007 R2, complete the following procedure:</span></span>

1.  <span data-ttu-id="6bf3f-142">Haga clic en **Inicio**, en **todos los programas**, en **System Center Operations Manager 2007 R2**y, a continuación, en **Operations Manager Shell**.</span><span class="sxs-lookup"><span data-stu-id="6bf3f-142">Click **Start**, click **All Programs**, click **System Center Operations Manager 2007 R2**, and then click **Operations Manager Shell**.</span></span>

2.  <span data-ttu-id="6bf3f-143">En el shell de Operations Manager, escriba el siguiente comando en el símbolo del sistema, utilizando la ruta de acceso real a la copia del archivo Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp y, a continuación, presione ENTRAR:</span><span class="sxs-lookup"><span data-stu-id="6bf3f-143">In the Operations Manager Shell, type the following command at the command prompt, using the actual path to your copy of the file Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp, and then press ENTER:</span></span>
    
        MPImport.exe D:\MP\Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp

3.  <span data-ttu-id="6bf3f-144">Después de importar el primer módulo de administración, repita el proceso con la ruta de acceso a la copia del archivo Microsoft.LS.2013.Monitoring.ComponentAndUser.mp:</span><span class="sxs-lookup"><span data-stu-id="6bf3f-144">After you import the first management pack, repeat the process using the path to your copy of the file Microsoft.LS.2013.Monitoring.ComponentAndUser.mp:</span></span>
    
        MPImport.exe D:\MP\Microsoft.LS.2013.Monitoring.ComponentAndUser.mp

4.  <span data-ttu-id="6bf3f-145">Cierre el shell de Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="6bf3f-145">Close the Operations Manager Shell.</span></span>

<span data-ttu-id="6bf3f-146">Si está usando System Center Operations Manager 2012, realice este procedimiento en su lugar:</span><span class="sxs-lookup"><span data-stu-id="6bf3f-146">If you are using System Center Operations Manager 2012, complete this procedure instead:</span></span>

1.  <span data-ttu-id="6bf3f-147">Haga clic sucesivamente en **Inicio**, **Todos los programas**, **Microsoft System Center 2012**, **Operations Manager** y **Shell de Operations Manager**.</span><span class="sxs-lookup"><span data-stu-id="6bf3f-147">Click **Start**, click **All Programs**, click **Microsoft System Center 2012**, click **Operations Manager**, and then click **Operations Manager Shell**.</span></span>

2.  <span data-ttu-id="6bf3f-148">En el shell de Operations Manager, escriba el siguiente comando en el símbolo del sistema, utilizando la ruta de acceso real a la copia del archivo Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp y, a continuación, presione ENTRAR:</span><span class="sxs-lookup"><span data-stu-id="6bf3f-148">In the Operations Manager Shell, type the following command at the command prompt, using the actual path to your copy of the file Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp, and then press ENTER:</span></span>
    
        Import-SCOMManagementPack -FullName "D:\MP\ Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp"

3.  <span data-ttu-id="6bf3f-149">Una vez que haya importado el primer módulo de administración, repita el proceso con la ruta de acceso a la copia del archivo Microsoft.LS.2013.Monitoring.ComponentAndUser.mp:</span><span class="sxs-lookup"><span data-stu-id="6bf3f-149">After you have imported the first management pack, repeat the process using the path to your copy of the file Microsoft.LS.2013.Monitoring.ComponentAndUser.mp:</span></span>
    
        Import-SCOMManagementPack -FullName "D:\MP\ Microsoft.LS.2013.Monitoring.ComponentAndUser.mp"

</div>

</div>

<span> </span>

</div>

</div>

</div>

