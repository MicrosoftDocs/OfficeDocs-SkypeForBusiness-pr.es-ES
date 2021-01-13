---
title: Configurar el servidor de administración principal
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: c7e21cce-1dd2-489a-a2eb-f632799f7523
description: 'Resumen: configure el servidor de administración principal, instale System Center Operations Manager e importe paquetes de administración para Skype Empresarial Server 2015.'
ms.openlocfilehash: be7e484814e241b4aebb042a23497ed4806693e0
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814870"
---
# <a name="configure-the-primary-management-server"></a><span data-ttu-id="d598d-103">Configurar el servidor de administración principal</span><span class="sxs-lookup"><span data-stu-id="d598d-103">Configure the Primary Management Server</span></span>

<span data-ttu-id="d598d-104">**Resumen:** Configure el servidor de administración principal, instale System Center Operations Manager e importe paquetes de administración para Skype Empresarial Server 2015.</span><span class="sxs-lookup"><span data-stu-id="d598d-104">**Summary:** Configure your primary management server, install System Center Operations Manager, and import management packs for Skype for Business Server 2015.</span></span>

<span data-ttu-id="d598d-105">Para aprovechar al máximo las nuevas capacidades de supervisión de estado incluidas en Skype Empresarial Server 2015, primero debe designar un equipo para que actúe como servidor de administración principal.</span><span class="sxs-lookup"><span data-stu-id="d598d-105">To take full advantage of the new health monitoring capabilities included in Skype for Business Server 2015, you must first designate a computer to act as your primary management server.</span></span> <span data-ttu-id="d598d-106">A continuación, debe instalar System Center Operations Manager 2012 SP1 o R2 o System Center Operations Manager 2007 R2 en ese equipo.</span><span class="sxs-lookup"><span data-stu-id="d598d-106">You must then install System Center Operations Manager 2012 SP1 or R2 or System Center Operations Manager 2007 R2 on that computer.</span></span> <span data-ttu-id="d598d-107">Además, primero debe instalar una versión compatible de SQL Server para que funcione como base de datos back-end de Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="d598d-107">In addition, you must first install a supported version of SQL Server to function as your Operations Manager back-end database.</span></span>

<span data-ttu-id="d598d-108">Al instalar System Center Operations Manager, deberá instalar todos los componentes de ese producto, incluidos:</span><span class="sxs-lookup"><span data-stu-id="d598d-108">When you install System Center Operations Manager, you will need to install all the components of that product, including:</span></span>

- <span data-ttu-id="d598d-109">Base de datos operativa</span><span class="sxs-lookup"><span data-stu-id="d598d-109">Operational database</span></span>

- <span data-ttu-id="d598d-110">Servidor</span><span class="sxs-lookup"><span data-stu-id="d598d-110">Server</span></span>

- <span data-ttu-id="d598d-111">Consola</span><span class="sxs-lookup"><span data-stu-id="d598d-111">Console</span></span>

- <span data-ttu-id="d598d-112">Cmdlets de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="d598d-112">Windows PowerShell cmdlets</span></span>

- <span data-ttu-id="d598d-113">Consola web</span><span class="sxs-lookup"><span data-stu-id="d598d-113">Web console</span></span>

- <span data-ttu-id="d598d-114">Generación de informes</span><span class="sxs-lookup"><span data-stu-id="d598d-114">Reporting</span></span>

- <span data-ttu-id="d598d-115">Almacén de datos</span><span class="sxs-lookup"><span data-stu-id="d598d-115">Data warehouse</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d598d-116">El["Paquete redistribuible de Microsoft Report Viewer 2010"](https://www.microsoft.com/download/details.aspx?id=6442)debe instalarse antes de instalar System Center Operations Manager 2012.</span><span class="sxs-lookup"><span data-stu-id="d598d-116">The "[Microsoft Report Viewer 2010 Redistributable Package](https://www.microsoft.com/download/details.aspx?id=6442)" needs to be installed before you install System Center Operations Manager 2012.</span></span>

<span data-ttu-id="d598d-117">Para obtener más información sobre estos productos y su instalación, consulte los siguientes vínculos:</span><span class="sxs-lookup"><span data-stu-id="d598d-117">For details about these products and their installation, see the following links:</span></span>

- [<span data-ttu-id="d598d-118">System Center Operations Manager 2012</span><span class="sxs-lookup"><span data-stu-id="d598d-118">System Center Operations Manager 2012</span></span>](https://go.microsoft.com/fwlink/p/?linkid=257527)

- [<span data-ttu-id="d598d-119">System Center Operations Manager 2007</span><span class="sxs-lookup"><span data-stu-id="d598d-119">System Center Operations Manager 2007</span></span>](https://technet.microsoft.com/library/bb735860.aspx)

<span data-ttu-id="d598d-120">Tenga en cuenta que solo puede tener un servidor de administración raíz por cada implementación de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="d598d-120">Keep in mind that you can have only one Root Management Server per Skype for Business Server deployment.</span></span>

## <a name="importing-the-skype-for-business-server-2015-management-packs"></a><span data-ttu-id="d598d-121">Importación de los módulos de administración de Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="d598d-121">Importing the Skype for Business Server 2015 Management Packs</span></span>

<span data-ttu-id="d598d-122">Puede ampliar las capacidades de System Center Operations Manager instalando módulos de administración, un software que determina qué elementos puede supervisar System Center Operations Manager, cómo deben supervisarse esos elementos y cómo se deben activar e informar las alertas.</span><span class="sxs-lookup"><span data-stu-id="d598d-122">You can extend the capabilities of System Center Operations Manager by installing management packs—software that dictates which items System Center Operations Manager can monitor, how those items should be monitored, and how alerts should be triggered and reported.</span></span> <span data-ttu-id="d598d-123">Skype Empresarial Server 2015 incluye dos módulos de administración de System Center Operations Manager que proporcionan las siguientes funcionalidades:</span><span class="sxs-lookup"><span data-stu-id="d598d-123">Skype for Business Server 2015 includes two System Center Operations Manager management packs that provide the following capabilities:</span></span>

- <span data-ttu-id="d598d-124"> El módulo de administración de componentes y usuarios (Microsoft.LS.2015.Monitoring.ComponentAndUser.mp) realiza un seguimiento de los problemas de Skype Empresarial Server registrados en registros de eventos, registrados por contadores de rendimiento o registrados en los registros de detalles de llamadas (CDR) o en las bases de datos de calidad de la experiencia (QoE).</span><span class="sxs-lookup"><span data-stu-id="d598d-124">**The Component and User Management Pack** (Microsoft.LS.2015.Monitoring.ComponentAndUser.mp) tracks Skype for Business Server issues recorded in event logs, registered by performance counters, or logged in the call detail records (CDRs) or the Quality of Experience (QoE) databases.</span></span> <span data-ttu-id="d598d-125">Para problemas críticos, System Center Operations Manager se puede configurar para notificar inmediatamente a los administradores a través del correo electrónico, el mensaje instantáneo o la mensajería SMS.</span><span class="sxs-lookup"><span data-stu-id="d598d-125">For critical issues, System Center Operations Manager can be configured to immediately notify administrators through email, instant message, or SMS messaging.</span></span> <span data-ttu-id="d598d-126">(SMS, o servicio de mensajes cortos, es la tecnología que se usa para enviar mensajes de texto de un dispositivo móvil a otro).</span><span class="sxs-lookup"><span data-stu-id="d598d-126">(SMS, or Short Message Service, is the technology used to send text messages from one mobile device to another.)</span></span>

    > [!NOTE]
    >  <span data-ttu-id="d598d-127">Para obtener más información acerca de la configuración de la notificación de Operations Manager, vea [Configuring Notification](https://go.microsoft.com/fwlink/p/?LinkID=268785&amp;amp;clcid=0x409).</span><span class="sxs-lookup"><span data-stu-id="d598d-127">For details about configuring Operations Manager notification, see [Configuring Notification](https://go.microsoft.com/fwlink/p/?LinkID=268785&amp;amp;clcid=0x409).</span></span>

- <span data-ttu-id="d598d-128"> El módulo de administración de supervisión activa (Microsoft.LS.2015.Monitoring.ActiveMonitoring.mp) prueba de forma proactiva los componentes clave de Skype Empresarial Server, como iniciar sesión en el sistema, intercambiar mensajes instantáneos o realizar llamadas a un teléfono ubicado en la red telefónica conmutada (RTC).</span><span class="sxs-lookup"><span data-stu-id="d598d-128">**The Active Monitoring Management Pack** (Microsoft.LS.2015.Monitoring.ActiveMonitoring.mp) proactively tests key Skype for Business Server components, such as signing into to the system, exchanging instant messages, or making calls to a phone located on the public switched telephone network (PSTN).</span></span> <span data-ttu-id="d598d-129">Estas pruebas se llevan a cabo con los cmdlets de transacción sintética de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="d598d-129">These tests are conducted by using the Skype for Business Server synthetic transaction cmdlets.</span></span> <span data-ttu-id="d598d-130">Por ejemplo, el cmdlet **Test-CsIM** se usa para simular una conversación de mensajería instantánea entre dos usuarios de prueba.</span><span class="sxs-lookup"><span data-stu-id="d598d-130">For example, the **Test-CsIM** cmdlet is used to simulate an instant messaging conversation between a pair of test users.</span></span> <span data-ttu-id="d598d-131">Si se produce un error en esta conversación simulada, se genera una alerta.</span><span class="sxs-lookup"><span data-stu-id="d598d-131">If this simulated conversation fails, an alert is generated.</span></span>

<span data-ttu-id="d598d-132">La importación de los paquetes de administración es un paso fundamental.</span><span class="sxs-lookup"><span data-stu-id="d598d-132">Importing the management packs is a crucial step.</span></span> <span data-ttu-id="d598d-133">Si los módulos de administración no se importan, no podrá usar Operations Manager para supervisar eventos de Skype Empresarial Server ni ejecutar transacciones sintéticas de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="d598d-133">If the management packs are not imported, you will not be able to use Operations Manager to monitor Skype for Business Server events or run Skype for Business Server synthetic transactions.</span></span>

<span data-ttu-id="d598d-134">El módulo de administración de componentes y usuarios se usa para supervisar solo Skype Empresarial Server 2015.</span><span class="sxs-lookup"><span data-stu-id="d598d-134">The Component and User Management Pack is used to monitor only Skype for Business Server 2015.</span></span> <span data-ttu-id="d598d-135">Si se encuentra en un escenario de coexistencia en el que están instalados Skype Empresarial Server 2015 y Lync Server 2013, debe seguir usando los módulos de administración de Lync Server 2013 para los equipos de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d598d-135">If you are in a coexistence scenario where both Skype for Business Server 2015 and Lync Server 2013 are installed, you should continue to use the Lync Server 2013 management packs for your Lync Server 2013 computers.</span></span>

> [!NOTE]
> <span data-ttu-id="d598d-136">Los módulos de administración de Skype Empresarial Server 2015 incluyen el módulo de administración de componentes y usuarios de Skype Empresarial Server 2015 y el módulo de administración de supervisión activa de Skype Empresarial Server 2015.</span><span class="sxs-lookup"><span data-stu-id="d598d-136">Management packs for Skype for Business Server 2015 include the Skype for Business Server 2015 Component and User Management Pack and the Skype for Business Server 2015 Active Monitoring Management Pack.</span></span>

<span data-ttu-id="d598d-137">Puede usar una de las siguientes herramientas para importar los paquetes de administración:</span><span class="sxs-lookup"><span data-stu-id="d598d-137">You can use one of the following tools to import management packs:</span></span>

- <span data-ttu-id="d598d-138">**System Center Operations Manager** Con este método, se usa Operations Manager para agregar supervisión para Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="d598d-138">**System Center Operations Manager** With this method, you use the Operations Manager to add monitoring for Skype for Business Server.</span></span>

- <span data-ttu-id="d598d-139">**Shell de Operations Manager** Puede usar el Shell de Operations Manager para importar directamente o para solucionar los problemas que se encuentren al importar paquetes de administración mediante la consola de System Center Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="d598d-139">**Operations Manager Shell** You can use the Operations Manager Shell to import directly, or to troubleshoot any issues that you encounter when you import management packs by using the System Center Operations Manager console.</span></span>

### <a name="importing-the-management-packs-by-using-system-center-operations-manager"></a><span data-ttu-id="d598d-140">Importación de los módulos de administración mediante System Center Operations Manager</span><span class="sxs-lookup"><span data-stu-id="d598d-140">Importing the Management Packs by Using System Center Operations Manager</span></span>

1. <span data-ttu-id="d598d-141">Descargue el SkypeForBusiness2015ManagementPacks.msi de las descargas web de Microsoft e instale el msi.</span><span class="sxs-lookup"><span data-stu-id="d598d-141">Download the SkypeForBusiness2015ManagementPacks.msi from the Microsoft Web downloads, and install the msi.</span></span>

2. <span data-ttu-id="d598d-142">En System Center Operations Manager, haga clic en **Administración.**</span><span class="sxs-lookup"><span data-stu-id="d598d-142">In System Center Operations Manager, click **Administration**.</span></span>

3. <span data-ttu-id="d598d-143">En el panel Administración, haga clic con el botón secundario en **Paquetes de administración** y luego haga clic en **Importar paquetes de administración**.</span><span class="sxs-lookup"><span data-stu-id="d598d-143">In the Administration pane, right-click **Management Packs**, and then click **Import Management Packs**.</span></span>

4. <span data-ttu-id="d598d-144">En el cuadro de diálogo **Seleccionar paquetes de administración**, haga clic en **Agregar** y luego en **Agregar desde el disco**.</span><span class="sxs-lookup"><span data-stu-id="d598d-144">In the **Select Management Packs** dialog box, click **Add**, and then click **Add from disk**.</span></span>

5. <span data-ttu-id="d598d-145">En el cuadro **de diálogo Conexión** al catálogo en línea, haga clic en **No**.</span><span class="sxs-lookup"><span data-stu-id="d598d-145">In the **Online Catalog Connection** dialog box, click **No**.</span></span>

6. <span data-ttu-id="d598d-146">En el cuadro de diálogo Seleccionar **módulos** de administración para importar, busque y seleccione los archivos Microsoft.LS.2015.Monitoring.ActiveMonitoring.mp y Microsoft.LS.2015.Monitoring.ComponentAndUser.mp y, a continuación, haga clic en **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="d598d-146">In the **Select Management Packs to import** dialog box, locate and select the files Microsoft.LS.2015.Monitoring.ActiveMonitoring.mp and Microsoft.LS.2015.Monitoring.ComponentAndUser.mp, and then click **Open**.</span></span> <span data-ttu-id="d598d-147">Para seleccionar varios archivos en el cuadro de diálogo, haga clic en el primer archivo y, a continuación, mantenga presionada la tecla Ctrl y haga clic en los archivos siguientes.</span><span class="sxs-lookup"><span data-stu-id="d598d-147">To select multiple files in the dialog box, click the first file, and then hold down the Ctrl key and click the subsequent files.</span></span>

7. <span data-ttu-id="d598d-148">En el cuadro de diálogo **Seleccionar paquetes de administración**, haga clic en **Instalar**.</span><span class="sxs-lookup"><span data-stu-id="d598d-148">In the **Select Management Packs** dialog box, click **Install**.</span></span> <span data-ttu-id="d598d-149">Si obtiene un mensaje de error y no se puede producir la instalación, que generalmente significa que los archivos del paquete de administración se encuentran en una carpeta protegida por el control de cuentas de usuario de Windows.</span><span class="sxs-lookup"><span data-stu-id="d598d-149">If you get an error message and installation fails, that typically means that the management pack files are in a folder protected by the Windows User Account Control.</span></span> <span data-ttu-id="d598d-150">Si esto ocurre, copie los archivos en una carpeta diferente y, a continuación, reinicie el proceso de importación e instalación.</span><span class="sxs-lookup"><span data-stu-id="d598d-150">If this occurs, copy the files to a different folder, and then restart the import and installation process.</span></span>

8. <span data-ttu-id="d598d-151">En el cuadro de diálogo **Seleccionar paquetes de administración**, haga clic en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="d598d-151">In the **Select Management Packs** dialog box, click **Close**.</span></span> <span data-ttu-id="d598d-152">El proceso de importación e instalación puede requerir varios minutos para completarse.</span><span class="sxs-lookup"><span data-stu-id="d598d-152">The import and installation process might require several minutes to complete.</span></span>

## <a name="importing-the-management-packs-by-using-the-operations-manager-shell"></a><span data-ttu-id="d598d-153">Importación de los módulos de administración mediante el Shell de Operations Manager</span><span class="sxs-lookup"><span data-stu-id="d598d-153">Importing the Management Packs by Using the Operations Manager Shell</span></span>

<span data-ttu-id="d598d-154">En general, es más fácil importar los módulos de administración mediante la consola de Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="d598d-154">In general, it is easier to import the management packs by using the Operations Manager console.</span></span> <span data-ttu-id="d598d-155">Sin embargo, si se produce un error y se produce un error en la importación, la consola no siempre proporciona los informes de errores adecuados.</span><span class="sxs-lookup"><span data-stu-id="d598d-155">However, if an error occurs and the import fails, the console does not always provide adequate error reports.</span></span> <span data-ttu-id="d598d-156">En comparación, el Shell de Operations Manager proporciona información detallada.</span><span class="sxs-lookup"><span data-stu-id="d598d-156">By comparison, the Operations Manager Shell provides detailed information.</span></span> <span data-ttu-id="d598d-157">Si usa Operations Manager y tiene problemas al importar un módulo de administración, importe el paquete mediante el Shell de Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="d598d-157">If you are using Operations Manager and you encounter issues when importing a management pack, import the pack by using the Operations Manager Shell.</span></span> <span data-ttu-id="d598d-158">La información proporcionada por el Shell de Operations Manager puede ayudarle a determinar por qué se ha fallado la importación.</span><span class="sxs-lookup"><span data-stu-id="d598d-158">The information provided by Operations Manager Shell can help you determine why the import failed.</span></span>

1. <span data-ttu-id="d598d-159">Haga **clic en Inicio**, en **Todos** los programas, en **Microsoft System Center 2012,** en **Operations Manager** y, a continuación, en Shell de **Operations Manager.**</span><span class="sxs-lookup"><span data-stu-id="d598d-159">Click **Start**, click **All Programs**, click **Microsoft System Center 2012**, click **Operations Manager**, and then click **Operations Manager Shell**.</span></span>

2. <span data-ttu-id="d598d-160">En el Shell de Operations Manager, escriba el siguiente comando en el símbolo del sistema, mediante la ruta de acceso real a la copia del archivo Microsoft.LS.2015.Monitoring.ActiveMonitoring.mp y, a continuación, presione ENTRAR:</span><span class="sxs-lookup"><span data-stu-id="d598d-160">In Operations Manager Shell, type the following command at the command prompt, using the actual path to your copy of the file Microsoft.LS.2015.Monitoring.ActiveMonitoring.mp, and then press ENTER:</span></span>

   ```PowerShell
   Import-SCOMManagementPack -FullName "D:\MP\Microsoft.LS.2015.Monitoring.ActiveMonitoring.mp"
   ```

3. <span data-ttu-id="d598d-161">Después de importar el primer módulo de administración, repita el proceso con la ruta de acceso a la copia del archivo Microsoft.LS.2015.Monitoring.ComponentAndUser.mp:</span><span class="sxs-lookup"><span data-stu-id="d598d-161">After you have imported the first management pack, repeat the process, using the path to your copy of the file Microsoft.LS.2015.Monitoring.ComponentAndUser.mp:</span></span>

   ```PowerShell
   Import-SCOMManagementPack -FullName "D:\MP\Microsoft.LS.2015.Monitoring.ComponentAndUser.mp"
   ```
