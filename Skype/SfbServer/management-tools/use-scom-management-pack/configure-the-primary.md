---
title: Configurar el servidor de administración principal
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: 'Resumen: configure el servidor de administración principal, instale System Center Operations Manager e importe los paquetes de administración para Skype empresarial Server 2015.'
ms.openlocfilehash: 0492a86062577d5118860faae8beca50f9f7bed2
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816129"
---
# <a name="configure-the-primary-management-server"></a><span data-ttu-id="a8116-103">Configurar el servidor de administración principal</span><span class="sxs-lookup"><span data-stu-id="a8116-103">Configure the Primary Management Server</span></span>

<span data-ttu-id="a8116-104">**Resumen:** Configurar el servidor de administración principal, instalar System Center Operations Manager e importar paquetes de administración para Skype empresarial Server 2015.</span><span class="sxs-lookup"><span data-stu-id="a8116-104">**Summary:** Configure your primary management server, install System Center Operations Manager, and import management packs for Skype for Business Server 2015.</span></span>

<span data-ttu-id="a8116-105">Para aprovechar al máximo las nuevas capacidades de supervisión de estado incluidas en Skype empresarial Server 2015, primero debe designar un equipo que actúe como servidor de administración principal.</span><span class="sxs-lookup"><span data-stu-id="a8116-105">To take full advantage of the new health monitoring capabilities included in Skype for Business Server 2015, you must first designate a computer to act as your primary management server.</span></span> <span data-ttu-id="a8116-106">Debe instalar System Center Operations Manager 2012 SP1 o R2 o System Center Operations Manager 2007 R2 en ese equipo.</span><span class="sxs-lookup"><span data-stu-id="a8116-106">You must then install System Center Operations Manager 2012 SP1 or R2 or System Center Operations Manager 2007 R2 on that computer.</span></span> <span data-ttu-id="a8116-107">Además, primero debe instalar una versión compatible de SQL Server para que funcione como la base de datos back-end de Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="a8116-107">In addition, you must first install a supported version of SQL Server to function as your Operations Manager back-end database.</span></span>

<span data-ttu-id="a8116-108">Cuando instale System Center Operations Manager, tendrá que instalar todos los componentes de ese producto, entre los que se incluyen:</span><span class="sxs-lookup"><span data-stu-id="a8116-108">When you install System Center Operations Manager, you will need to install all the components of that product, including:</span></span>

- <span data-ttu-id="a8116-109">Base de datos operativa</span><span class="sxs-lookup"><span data-stu-id="a8116-109">Operational database</span></span>

- <span data-ttu-id="a8116-110">Servidor</span><span class="sxs-lookup"><span data-stu-id="a8116-110">Server</span></span>

- <span data-ttu-id="a8116-111">Consola</span><span class="sxs-lookup"><span data-stu-id="a8116-111">Console</span></span>

- <span data-ttu-id="a8116-112">Cmdlets de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="a8116-112">Windows PowerShell cmdlets</span></span>

- <span data-ttu-id="a8116-113">Consola web</span><span class="sxs-lookup"><span data-stu-id="a8116-113">Web console</span></span>

- <span data-ttu-id="a8116-114">Informes</span><span class="sxs-lookup"><span data-stu-id="a8116-114">Reporting</span></span>

- <span data-ttu-id="a8116-115">Almacén de datos</span><span class="sxs-lookup"><span data-stu-id="a8116-115">Data warehouse</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a8116-116">El "[paquete redistribuible 2010 de Microsoft Report Viewer](https://www.microsoft.com/en-us/download/details.aspx?id=6442)" debe instalarse antes de instalar System Center Operations Manager 2012.</span><span class="sxs-lookup"><span data-stu-id="a8116-116">The "[Microsoft Report Viewer 2010 Redistributable Package](https://www.microsoft.com/en-us/download/details.aspx?id=6442)" needs to be installed before you install System Center Operations Manager 2012.</span></span>

<span data-ttu-id="a8116-117">Para obtener más información sobre estos productos y su instalación, consulte los siguientes vínculos:</span><span class="sxs-lookup"><span data-stu-id="a8116-117">For details about these products and their installation, see the following links:</span></span>

- [<span data-ttu-id="a8116-118">System Center Operations Manager 2012</span><span class="sxs-lookup"><span data-stu-id="a8116-118">System Center Operations Manager 2012</span></span>](https://go.microsoft.com/fwlink/p/?linkid=257527)

- [<span data-ttu-id="a8116-119">System Center Operations Manager 2007</span><span class="sxs-lookup"><span data-stu-id="a8116-119">System Center Operations Manager 2007</span></span>](https://technet.microsoft.com/en-us/library/bb735860.aspx)

<span data-ttu-id="a8116-120">Tenga en cuenta que solo puede tener un servidor de administración raíz por implementación de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="a8116-120">Keep in mind that you can have only one Root Management Server per Skype for Business Server deployment.</span></span>

## <a name="importing-the-skype-for-business-server-2015-management-packs"></a><span data-ttu-id="a8116-121">Importación de los paquetes de administración de Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="a8116-121">Importing the Skype for Business Server 2015 Management Packs</span></span>

<span data-ttu-id="a8116-122">Puede ampliar las capacidades de System Center Operations Manager mediante la instalación de paquetes de administración, es decir, el software que determina qué elementos puede supervisar System Center Operations Manager, cómo se deben supervisar esos elementos y cómo se deberían desencadenar alertas y registrados.</span><span class="sxs-lookup"><span data-stu-id="a8116-122">You can extend the capabilities of System Center Operations Manager by installing management packs—software that dictates which items System Center Operations Manager can monitor, how those items should be monitored, and how alerts should be triggered and reported.</span></span> <span data-ttu-id="a8116-123">Skype empresarial Server 2015 incluye dos módulos de administración de System Center Operations Manager que proporcionan las siguientes características:</span><span class="sxs-lookup"><span data-stu-id="a8116-123">Skype for Business Server 2015 includes two System Center Operations Manager management packs that provide the following capabilities:</span></span>

- <span data-ttu-id="a8116-124">**El componente y el paquete de administración de usuario** (Microsoft.LS.2015.Monitoring.ComponentAndUser.MP) realiza un seguimiento de los problemas de Skype empresarial Server registrados en los registros de eventos, registrados por los contadores de rendimiento o registrados en las bases de datos de registros de detalles de llamadas (CDRs) o de calidad de experiencia (QoE).</span><span class="sxs-lookup"><span data-stu-id="a8116-124">**The Component and User Management Pack** (Microsoft.LS.2015.Monitoring.ComponentAndUser.mp) tracks Skype for Business Server issues recorded in event logs, registered by performance counters, or logged in the call detail records (CDRs) or the Quality of Experience (QoE) databases.</span></span> <span data-ttu-id="a8116-125">En el caso de problemas críticos, System Center Operations Manager se puede configurar para que notifiquen inmediatamente a los administradores por correo electrónico, mensajes instantáneos o mensajes SMS.</span><span class="sxs-lookup"><span data-stu-id="a8116-125">For critical issues, System Center Operations Manager can be configured to immediately notify administrators through email, instant message, or SMS messaging.</span></span> <span data-ttu-id="a8116-126">(SMS o servicio de mensajes cortos es la tecnología que se usa para enviar mensajes de texto desde un dispositivo móvil a otro).</span><span class="sxs-lookup"><span data-stu-id="a8116-126">(SMS, or Short Message Service, is the technology used to send text messages from one mobile device to another.)</span></span>

    > [!NOTE]
    >  <span data-ttu-id="a8116-127">Para obtener más información sobre cómo configurar las notificaciones de Operations Manager, vea [configurar notificaciones](https://go.microsoft.com/fwlink/p/?LinkID=268785&amp;amp;clcid=0x409).</span><span class="sxs-lookup"><span data-stu-id="a8116-127">For details about configuring Operations Manager notification, see [Configuring Notification](https://go.microsoft.com/fwlink/p/?LinkID=268785&amp;amp;clcid=0x409).</span></span>

- <span data-ttu-id="a8116-128">**El módulo de administración de supervisión activa** (Microsoft.LS.2015.Monitoring.ActiveMonitoring.MP) prueba de forma proactiva los componentes clave de Skype empresarial, como iniciar sesión en el sistema, intercambiar mensajes instantáneos o hacer llamadas a un teléfono que se encuentra en la red de telefonía pública conmutada (RTC).</span><span class="sxs-lookup"><span data-stu-id="a8116-128">**The Active Monitoring Management Pack** (Microsoft.LS.2015.Monitoring.ActiveMonitoring.mp) proactively tests key Skype for Business Server components, such as signing into to the system, exchanging instant messages, or making calls to a phone located on the public switched telephone network (PSTN).</span></span> <span data-ttu-id="a8116-129">Estas pruebas se realizan mediante los cmdlets de transacciones sintéticas de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="a8116-129">These tests are conducted by using the Skype for Business Server synthetic transaction cmdlets.</span></span> <span data-ttu-id="a8116-130">Por ejemplo, el cmdlet **Test-CsIM** se usa para simular una conversación de mensajería instantánea entre dos usuarios de prueba.</span><span class="sxs-lookup"><span data-stu-id="a8116-130">For example, the **Test-CsIM** cmdlet is used to simulate an instant messaging conversation between a pair of test users.</span></span> <span data-ttu-id="a8116-131">Si esta conversación simulada falla, se genera una alerta.</span><span class="sxs-lookup"><span data-stu-id="a8116-131">If this simulated conversation fails, an alert is generated.</span></span>

<span data-ttu-id="a8116-p105">Importar los paquetes de administración es un paso fundamental. Si los módulos de administración no se importan, no podrá usar Operations Manager para supervisar los eventos de Skype Empresarial Server ni para ejecutar transacciones sintéticas de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="a8116-p105">Importing the management packs is a crucial step. If the management packs are not imported, you will not be able to use Operations Manager to monitor Skype for Business Server events or run Skype for Business Server synthetic transactions.</span></span>

<span data-ttu-id="a8116-p106">El módulo de componentes y administración de usuario se usa solo para supervisar Skype Empresarial Server 2015. Si se encuentra en un escenario de coexistencia en el se ha instalado Skype Empresarial Server 2015 y Lync Server 2013, debe continuar usando los paquetes de administración de Lync Server 2013 para sus equipos Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a8116-p106">The Component and User Management Pack is used to monitor only Skype for Business Server 2015. If you are in a coexistence scenario where both Skype for Business Server 2015 and Lync Server 2013 are installed, you should continue to use the Lync Server 2013 management packs for your Lync Server 2013 computers.</span></span>

> [!NOTE]
> <span data-ttu-id="a8116-136">Los módulos de administración de Skype Empresarial Server 2015 incluyen el módulo de componentes y administración de usuarios y el módulo de administración de supervisión activa.</span><span class="sxs-lookup"><span data-stu-id="a8116-136">Management packs for Skype for Business Server 2015 include the Skype for Business Server 2015 Component and User Management Pack and the Skype for Business Server 2015 Active Monitoring Management Pack.</span></span>

<span data-ttu-id="a8116-137">Puede usar una de las siguientes herramientas para importar los paquetes de administración:</span><span class="sxs-lookup"><span data-stu-id="a8116-137">You can use one of the following tools to import management packs:</span></span>

- <span data-ttu-id="a8116-138">**System Center Operations Manager** Con este método, se usa el Operations Manager para agregar la supervisión de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="a8116-138">**System Center Operations Manager** With this method, you use the Operations Manager to add monitoring for Skype for Business Server.</span></span>

- <span data-ttu-id="a8116-139">**Shell de Operations Manager** Puede usar el shell de Operations Manager para importar directamente o para solucionar cualquier problema que encuentre al importar paquetes de administración mediante la consola de System Center Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="a8116-139">**Operations Manager Shell** You can use the Operations Manager Shell to import directly, or to troubleshoot any issues that you encounter when you import management packs by using the System Center Operations Manager console.</span></span>

### <a name="importing-the-management-packs-by-using-system-center-operations-manager"></a><span data-ttu-id="a8116-140">Importación de los módulos de administración mediante System Center Operations Manager</span><span class="sxs-lookup"><span data-stu-id="a8116-140">Importing the Management Packs by Using System Center Operations Manager</span></span>

1. <span data-ttu-id="a8116-141">Descargue SkypeForBusiness2015ManagementPacks.msi desde la web de descargas de Microsoft e instala el archivo msi.</span><span class="sxs-lookup"><span data-stu-id="a8116-141">Download the SkypeForBusiness2015ManagementPacks.msi from the Microsoft Web downloads, and install the msi.</span></span>

2. <span data-ttu-id="a8116-142">En System Center Operations Manager, haga clic en **Administración**.</span><span class="sxs-lookup"><span data-stu-id="a8116-142">In System Center Operations Manager, click **Administration**.</span></span>

3. <span data-ttu-id="a8116-143">En el panel administración, haga clic con el botón secundario en **módulos**de administración y luego haga clic en **importar módulos de administración**.</span><span class="sxs-lookup"><span data-stu-id="a8116-143">In the Administration pane, right-click **Management Packs**, and then click **Import Management Packs**.</span></span>

4. <span data-ttu-id="a8116-144">En el cuadro de diálogo **Seleccionar módulos de administración**, haga clic en **Agregar** y luego en **Agregar desde el disco**.</span><span class="sxs-lookup"><span data-stu-id="a8116-144">In the **Select Management Packs** dialog box, click **Add**, and then click **Add from disk**.</span></span>

5. <span data-ttu-id="a8116-145">En el cuadro de diálogo **Conexión del catálogo en línea**, haga clic en **No**.</span><span class="sxs-lookup"><span data-stu-id="a8116-145">In the **Online Catalog Connection** dialog box, click **No**.</span></span>

6. <span data-ttu-id="a8116-p107">En el cuadro de diálogo **Seleccionar módulos de administración a importar**, localice y seleccione los archivos Microsoft.LS.2015.Monitoring.ActiveMonitoring.mp y Microsoft.LS.2015.Monitoring.ComponentAndUser.mp y, a continuación, haga clic en **Abrir**. Para seleccionar varios archivos en el cuadro de diálogo, haga clic en el primer archivo, mantenga presionada la tecla Ctrl y haga clic en el segundo archivo.</span><span class="sxs-lookup"><span data-stu-id="a8116-p107">In the **Select Management Packs to import** dialog box, locate and select the files Microsoft.LS.2015.Monitoring.ActiveMonitoring.mp and Microsoft.LS.2015.Monitoring.ComponentAndUser.mp, and then click **Open**. To select multiple files in the dialog box, click the first file, and then hold down the Ctrl key and click the subsequent files.</span></span>

7. <span data-ttu-id="a8116-p108">En el cuadro de diálogo **Seleccionar módulos de administración**, haga clic en **Instalar**. Si obtiene un mensaje de error y no se puede realizar la instalación, generalmente significa que los archivos del módulo de administración se encuentran en una carpeta protegida por el control de cuentas de usuario de Windows. En este caso, copie los archivos en otra carpeta y luego reinicie el proceso de importación e instalación.</span><span class="sxs-lookup"><span data-stu-id="a8116-p108">In the **Select Management Packs** dialog box, click **Install**. If you get an error message and installation fails, that typically means that the management pack files are in a folder protected by the Windows User Account Control. If this occurs, copy the files to a different folder, and then restart the import and installation process.</span></span>

8. <span data-ttu-id="a8116-p109">En el cuadro de diálogo **Seleccionar módulos de administración**, haga clic en **Cerrar**. Tenga en cuenta que el proceso de instalación e importación puede requerir algunos minutos para completarse.</span><span class="sxs-lookup"><span data-stu-id="a8116-p109">In the **Select Management Packs** dialog box, click **Close**. The import and installation process might require several minutes to complete.</span></span>

## <a name="importing-the-management-packs-by-using-the-operations-manager-shell"></a><span data-ttu-id="a8116-153">Importación de los módulos de administración mediante el Shell de Operations Manager</span><span class="sxs-lookup"><span data-stu-id="a8116-153">Importing the Management Packs by Using the Operations Manager Shell</span></span>

<span data-ttu-id="a8116-p110">En general, es más fácil importar los módulos de administración con la consola de Operations Manager. Sin embargo, si se produce un error y no es posible llevar a cabo la importación, la consola no siempre proporciona informes de errores adecuados. El Shell de Operations Manager, en cambio, proporciona información detallada. Si está usando Operations Manager y tiene problemas al importar un módulo de administración, importe el módulo con el Shell de Operations Manager. La información que proporciona el Shell de Operations Manager puede ayudarle a determinar el motivo del error de importación.</span><span class="sxs-lookup"><span data-stu-id="a8116-p110">In general, it is easier to import the management packs by using the Operations Manager console. However, if an error occurs and the import fails, the console does not always provide adequate error reports. By comparison, the Operations Manager Shell provides detailed information. If you are using Operations Manager and you encounter issues when importing a management pack, import the pack by using the Operations Manager Shell. The information provided by Operations Manager Shell can help you determine why the import failed.</span></span>

1. <span data-ttu-id="a8116-159">Haga clic sucesivamente en **Inicio**, **Todos los programas**, **Microsoft System Center 2012**, **Operations Manager** y **Shell de Operations Manager**.</span><span class="sxs-lookup"><span data-stu-id="a8116-159">Click **Start**, click **All Programs**, click **Microsoft System Center 2012**, click **Operations Manager**, and then click **Operations Manager Shell**.</span></span>

2. <span data-ttu-id="a8116-160">En Shell de Operations Manager, escriba el siguiente comando en el símbolo del sistema, usando la ruta de acceso real a su copia del archivo Microsoft.LS.2015.Monitoring.ActiveMonitoring.mp y, a continuación, presione ENTRAR:</span><span class="sxs-lookup"><span data-stu-id="a8116-160">In Operations Manager Shell, type the following command at the command prompt, using the actual path to your copy of the file Microsoft.LS.2015.Monitoring.ActiveMonitoring.mp, and then press ENTER:</span></span>

   ```PowerShell
   Import-SCOMManagementPack -FullName "D:\MP\Microsoft.LS.2015.Monitoring.ActiveMonitoring.mp"
   ```

3. <span data-ttu-id="a8116-161">Después de haber importado el primer módulo de administración, repita el proceso usando la ruta a su copia del archivo Microsoft.LS.2013.Monitoring.ComponentAndUser.mp:</span><span class="sxs-lookup"><span data-stu-id="a8116-161">After you have imported the first management pack, repeat the process, using the path to your copy of the file Microsoft.LS.2015.Monitoring.ComponentAndUser.mp:</span></span>

   ```PowerShell
   Import-SCOMManagementPack -FullName "D:\MP\Microsoft.LS.2015.Monitoring.ComponentAndUser.mp"
   ```
