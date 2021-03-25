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
description: 'Summary: Configure your primary management server, install System Center Operations Manager, and import management packs for Skype for Business Server 2019.'
ms.openlocfilehash: 02a174fb5c5fd6f06188553d8b2647c7162966e3
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120471"
---
# <a name="configure-the-primary-management-server"></a><span data-ttu-id="c73bc-103">Configurar el servidor de administración principal</span><span class="sxs-lookup"><span data-stu-id="c73bc-103">Configure the Primary Management Server</span></span>

<span data-ttu-id="c73bc-104">**Resumen:** Configure el servidor de administración principal, instale System Center Operations Manager e importe paquetes de administración para Skype Empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="c73bc-104">**Summary:** Configure your primary management server, install System Center Operations Manager, and import management packs for Skype for Business Server 2019.</span></span>

<span data-ttu-id="c73bc-105">Para aprovechar al máximo las nuevas funcionalidades de supervisión de estado incluidas en Skype Empresarial Server 2019, primero debe designar un equipo para que actúe como su servidor de administración principal.</span><span class="sxs-lookup"><span data-stu-id="c73bc-105">To take full advantage of the new health monitoring capabilities included in Skype for Business Server 2019, you must first designate a computer to act as your primary management server.</span></span> <span data-ttu-id="c73bc-106">A continuación, debe instalar System Center Operations Manager 2012 SP1 o R2 o System Center Operations Manager 2007 R2 en ese equipo.</span><span class="sxs-lookup"><span data-stu-id="c73bc-106">You must then install System Center Operations Manager 2012 SP1 or R2 or System Center Operations Manager 2007 R2 on that computer.</span></span> <span data-ttu-id="c73bc-107">Además, primero debe instalar una versión compatible de SQL Server para funcionar como la base de datos back-end de Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="c73bc-107">In addition, you must first install a supported version of SQL Server to function as your Operations Manager back-end database.</span></span>

<span data-ttu-id="c73bc-108">Al instalar System Center Operations Manager, deberá instalar todos los componentes de ese producto, incluidos:</span><span class="sxs-lookup"><span data-stu-id="c73bc-108">When you install System Center Operations Manager, you will need to install all the components of that product, including:</span></span>

- <span data-ttu-id="c73bc-109">Base de datos operativa</span><span class="sxs-lookup"><span data-stu-id="c73bc-109">Operational database</span></span>

- <span data-ttu-id="c73bc-110">Servidor</span><span class="sxs-lookup"><span data-stu-id="c73bc-110">Server</span></span>

- <span data-ttu-id="c73bc-111">Consola</span><span class="sxs-lookup"><span data-stu-id="c73bc-111">Console</span></span>

- <span data-ttu-id="c73bc-112">Cmdlets de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="c73bc-112">Windows PowerShell cmdlets</span></span>

- <span data-ttu-id="c73bc-113">Consola web</span><span class="sxs-lookup"><span data-stu-id="c73bc-113">Web console</span></span>

- <span data-ttu-id="c73bc-114">Reporting</span><span class="sxs-lookup"><span data-stu-id="c73bc-114">Reporting</span></span>

- <span data-ttu-id="c73bc-115">Almacén de datos</span><span class="sxs-lookup"><span data-stu-id="c73bc-115">Data warehouse</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c73bc-116">El " Paquete redistribuible de[Microsoft Report Viewer 2010](https://www.microsoft.com/download/details.aspx?id=6442)" debe instalarse antes de instalar System Center Operations Manager 2012.</span><span class="sxs-lookup"><span data-stu-id="c73bc-116">The "[Microsoft Report Viewer 2010 Redistributable Package](https://www.microsoft.com/download/details.aspx?id=6442)" needs to be installed before you install System Center Operations Manager 2012.</span></span>

<span data-ttu-id="c73bc-117">Para obtener más información sobre estos productos y su instalación, consulte los siguientes vínculos:</span><span class="sxs-lookup"><span data-stu-id="c73bc-117">For details about these products and their installation, see the following links:</span></span>

- <span data-ttu-id="c73bc-118">[System Center Operations Manager 2012](/previous-versions/system-center/system-center-2012-R2/hh205987(v=sc.12))</span><span class="sxs-lookup"><span data-stu-id="c73bc-118">[System Center Operations Manager 2012](/previous-versions/system-center/system-center-2012-R2/hh205987(v=sc.12))</span></span>

- [<span data-ttu-id="c73bc-119">System Center Operations Manager 2007</span><span class="sxs-lookup"><span data-stu-id="c73bc-119">System Center Operations Manager 2007</span></span>](https://technet.microsoft.com/library/bb735860.aspx)

<span data-ttu-id="c73bc-120">Tenga en cuenta que solo puede tener un servidor de administración raíz por implementación de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="c73bc-120">Keep in mind that you can have only one Root Management Server per Skype for Business Server deployment.</span></span>

## <a name="importing-the-skype-for-business-server-2019-management-packs"></a><span data-ttu-id="c73bc-121">Importar los módulos de administración de Skype Empresarial Server 2019</span><span class="sxs-lookup"><span data-stu-id="c73bc-121">Importing the Skype for Business Server 2019 Management Packs</span></span>

<span data-ttu-id="c73bc-122">Puede ampliar las capacidades de System Center Operations Manager mediante la instalación de módulos de administración, software que determina qué elementos puede supervisar System Center Operations Manager, cómo deben supervisarse esos elementos y cómo se deben activar e informar las alertas.</span><span class="sxs-lookup"><span data-stu-id="c73bc-122">You can extend the capabilities of System Center Operations Manager by installing management packs—software that dictates which items System Center Operations Manager can monitor, how those items should be monitored, and how alerts should be triggered and reported.</span></span> <span data-ttu-id="c73bc-123">Skype Empresarial Server 2019 incluye dos módulos de administración de System Center Operations Manager que proporcionan las siguientes funcionalidades:</span><span class="sxs-lookup"><span data-stu-id="c73bc-123">Skype for Business Server 2019 includes two System Center Operations Manager management packs that provide the following capabilities:</span></span>

- <span data-ttu-id="c73bc-124"> El módulo de administración de componentes y usuarios (Microsoft.LS.2019.Monitoring.ComponentAndUser.mp) realiza un seguimiento de los problemas de Skype Empresarial Server registrados en registros de eventos, registrados por contadores de rendimiento o registrados en las bases de datos de registros de detalles de llamadas (CDR) o calidad de experiencia (QoE).</span><span class="sxs-lookup"><span data-stu-id="c73bc-124">**The Component and User Management Pack** (Microsoft.LS.2019.Monitoring.ComponentAndUser.mp) tracks Skype for Business Server issues recorded in event logs, registered by performance counters, or logged in the call detail records (CDRs) or the Quality of Experience (QoE) databases.</span></span> <span data-ttu-id="c73bc-125">Para problemas críticos, System Center Operations Manager se puede configurar para notificar inmediatamente a los administradores a través del correo electrónico, el mensaje instantáneo o la mensajería SMS.</span><span class="sxs-lookup"><span data-stu-id="c73bc-125">For critical issues, System Center Operations Manager can be configured to immediately notify administrators through email, instant message, or SMS messaging.</span></span> <span data-ttu-id="c73bc-126">(SMS, o servicio de mensajes cortos, es la tecnología que se usa para enviar mensajes de texto de un dispositivo móvil a otro).</span><span class="sxs-lookup"><span data-stu-id="c73bc-126">(SMS, or Short Message Service, is the technology used to send text messages from one mobile device to another.)</span></span>

    > [!NOTE]
    >  <span data-ttu-id="c73bc-127">Para obtener más información sobre cómo configurar la notificación de Operations Manager, vea [Configuring Notification](/previous-versions/system-center/operations-manager-2007-r2/dd440890(v=technet.10)).</span><span class="sxs-lookup"><span data-stu-id="c73bc-127">For details about configuring Operations Manager notification, see [Configuring Notification](/previous-versions/system-center/operations-manager-2007-r2/dd440890(v=technet.10)).</span></span>

- <span data-ttu-id="c73bc-128">Active **Monitoring Management Pack** (Microsoft.LS.2019.Monitoring.ActiveMonitoring.mp) prueba proactivamente los componentes clave de Skype Empresarial Server, como iniciar sesión en el sistema, intercambiar mensajes instantáneos o realizar llamadas a un teléfono ubicado en la red telefónica conmutada (RTC).</span><span class="sxs-lookup"><span data-stu-id="c73bc-128">**The Active Monitoring Management Pack** (Microsoft.LS.2019.Monitoring.ActiveMonitoring.mp) proactively tests key Skype for Business Server components, such as signing into to the system, exchanging instant messages, or making calls to a phone located on the public switched telephone network (PSTN).</span></span> <span data-ttu-id="c73bc-129">Estas pruebas se llevan a cabo mediante los cmdlets de transacciones sintéticas de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="c73bc-129">These tests are conducted by using the Skype for Business Server synthetic transaction cmdlets.</span></span> <span data-ttu-id="c73bc-130">Por ejemplo, el cmdlet **Test-CsIM** se usa para simular una conversación de mensajería instantánea entre dos usuarios de prueba.</span><span class="sxs-lookup"><span data-stu-id="c73bc-130">For example, the **Test-CsIM** cmdlet is used to simulate an instant messaging conversation between a pair of test users.</span></span> <span data-ttu-id="c73bc-131">Si se produce un error en esta conversación simulada, se genera una alerta.</span><span class="sxs-lookup"><span data-stu-id="c73bc-131">If this simulated conversation fails, an alert is generated.</span></span>

<span data-ttu-id="c73bc-132">La importación de los módulos de administración es un paso fundamental.</span><span class="sxs-lookup"><span data-stu-id="c73bc-132">Importing the management packs is a crucial step.</span></span> <span data-ttu-id="c73bc-133">Si los módulos de administración no se importan, no podrá usar Operations Manager para supervisar eventos de Skype Empresarial Server ni ejecutar transacciones sintéticas de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="c73bc-133">If the management packs are not imported, you will not be able to use Operations Manager to monitor Skype for Business Server events or run Skype for Business Server synthetic transactions.</span></span>

<span data-ttu-id="c73bc-134">El módulo de administración de componentes y usuarios se usa para supervisar solo Skype Empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="c73bc-134">The Component and User Management Pack is used to monitor only Skype for Business Server 2019.</span></span> <span data-ttu-id="c73bc-135">Si se encuentra en un escenario de coexistencia en el que están instalados Skype Empresarial Server 2019 y Skype Empresarial Server 2015, debe seguir usando los módulos de administración de Skype Empresarial Server 2015 para sus equipos de Skype Empresarial Server 2015.</span><span class="sxs-lookup"><span data-stu-id="c73bc-135">If you are in a coexistence scenario where both Skype for Business Server 2019 and Skype for Business Server 2015 are installed, you should continue to use the Skype for Business Server 2015 management packs for your Skype for Business Server 2015 computers.</span></span>

> [!NOTE]
> <span data-ttu-id="c73bc-136">Los módulos de administración de Skype Empresarial Server 2019 incluyen el Módulo de administración de usuarios y componentes de Skype Empresarial Server 2019 y el Módulo de administración de supervisión activa de Skype Empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="c73bc-136">Management packs for Skype for Business Server 2019 include the Skype for Business Server 2019 Component and User Management Pack and the Skype for Business Server 2019 Active Monitoring Management Pack.</span></span>

<span data-ttu-id="c73bc-137">Puede usar una de las siguientes herramientas para importar los paquetes de administración:</span><span class="sxs-lookup"><span data-stu-id="c73bc-137">You can use one of the following tools to import management packs:</span></span>

- <span data-ttu-id="c73bc-138">**System Center Operations Manager** Con este método, se usa Operations Manager para agregar supervisión para Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="c73bc-138">**System Center Operations Manager** With this method, you use the Operations Manager to add monitoring for Skype for Business Server.</span></span>

- <span data-ttu-id="c73bc-139">**Shell de Operations Manager** Puede usar el Shell de Operations Manager para importar directamente o para solucionar cualquier problema que se encuentre al importar módulos de administración mediante la consola de System Center Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="c73bc-139">**Operations Manager Shell** You can use the Operations Manager Shell to import directly, or to troubleshoot any issues that you encounter when you import management packs by using the System Center Operations Manager console.</span></span>

### <a name="importing-the-management-packs-by-using-system-center-operations-manager"></a><span data-ttu-id="c73bc-140">Importar los módulos de administración mediante System Center Operations Manager</span><span class="sxs-lookup"><span data-stu-id="c73bc-140">Importing the Management Packs by Using System Center Operations Manager</span></span>

1. <span data-ttu-id="c73bc-141">Descargue el SkypeForBusiness2019ManagementPacks.msi de las descargas web de Microsoft e instale el msi.</span><span class="sxs-lookup"><span data-stu-id="c73bc-141">Download the SkypeForBusiness2019ManagementPacks.msi from the Microsoft Web downloads, and install the msi.</span></span>

2. <span data-ttu-id="c73bc-142">En System Center Operations Manager, haga clic en **Administración**.</span><span class="sxs-lookup"><span data-stu-id="c73bc-142">In System Center Operations Manager, click **Administration**.</span></span>

3. <span data-ttu-id="c73bc-143">En el panel Administración, haga clic con el botón secundario en **Paquetes de administración** y luego haga clic en **Importar paquetes de administración**.</span><span class="sxs-lookup"><span data-stu-id="c73bc-143">In the Administration pane, right-click **Management Packs**, and then click **Import Management Packs**.</span></span>

4. <span data-ttu-id="c73bc-144">En el cuadro de diálogo **Seleccionar paquetes de administración**, haga clic en **Agregar** y luego en **Agregar desde el disco**.</span><span class="sxs-lookup"><span data-stu-id="c73bc-144">In the **Select Management Packs** dialog box, click **Add**, and then click **Add from disk**.</span></span>

5. <span data-ttu-id="c73bc-145">En el cuadro **de diálogo Conexión** de catálogo en línea, haga clic en **No**.</span><span class="sxs-lookup"><span data-stu-id="c73bc-145">In the **Online Catalog Connection** dialog box, click **No**.</span></span>

6. <span data-ttu-id="c73bc-146">En el cuadro de diálogo Seleccionar **módulos** de administración para importar, busque y seleccione los archivos Microsoft.LS.2019.Monitoring.ActiveMonitoring.mp y Microsoft.LS.2019.Monitoring.ComponentAndUser.mp y, a continuación, haga clic en **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="c73bc-146">In the **Select Management Packs to import** dialog box, locate and select the files Microsoft.LS.2019.Monitoring.ActiveMonitoring.mp and Microsoft.LS.2019.Monitoring.ComponentAndUser.mp, and then click **Open**.</span></span> <span data-ttu-id="c73bc-147">Para seleccionar varios archivos en el cuadro de diálogo, haga clic en el primer archivo y, a continuación, mantenga presionada la tecla Ctrl y haga clic en los archivos siguientes.</span><span class="sxs-lookup"><span data-stu-id="c73bc-147">To select multiple files in the dialog box, click the first file, and then hold down the Ctrl key and click the subsequent files.</span></span>

7. <span data-ttu-id="c73bc-148">En el cuadro de diálogo **Seleccionar paquetes de administración**, haga clic en **Instalar**.</span><span class="sxs-lookup"><span data-stu-id="c73bc-148">In the **Select Management Packs** dialog box, click **Install**.</span></span> <span data-ttu-id="c73bc-149">Si obtiene un mensaje de error y no se puede producir la instalación, que generalmente significa que los archivos del paquete de administración se encuentran en una carpeta protegida por el control de cuentas de usuario de Windows.</span><span class="sxs-lookup"><span data-stu-id="c73bc-149">If you get an error message and installation fails, that typically means that the management pack files are in a folder protected by the Windows User Account Control.</span></span> <span data-ttu-id="c73bc-150">Si esto ocurre, copie los archivos en una carpeta diferente y, a continuación, reinicie el proceso de importación e instalación.</span><span class="sxs-lookup"><span data-stu-id="c73bc-150">If this occurs, copy the files to a different folder, and then restart the import and installation process.</span></span>

8. <span data-ttu-id="c73bc-151">En el cuadro de diálogo **Seleccionar paquetes de administración**, haga clic en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="c73bc-151">In the **Select Management Packs** dialog box, click **Close**.</span></span> <span data-ttu-id="c73bc-152">El proceso de importación e instalación puede requerir varios minutos para completarse.</span><span class="sxs-lookup"><span data-stu-id="c73bc-152">The import and installation process might require several minutes to complete.</span></span>

## <a name="importing-the-management-packs-by-using-the-operations-manager-shell"></a><span data-ttu-id="c73bc-153">Importar los módulos de administración mediante el Shell de Operations Manager</span><span class="sxs-lookup"><span data-stu-id="c73bc-153">Importing the Management Packs by Using the Operations Manager Shell</span></span>

<span data-ttu-id="c73bc-154">En general, es más fácil importar los módulos de administración mediante la consola de Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="c73bc-154">In general, it is easier to import the management packs by using the Operations Manager console.</span></span> <span data-ttu-id="c73bc-155">Sin embargo, si se produce un error y se produce un error en la importación, la consola no siempre proporciona informes de error adecuados.</span><span class="sxs-lookup"><span data-stu-id="c73bc-155">However, if an error occurs and the import fails, the console does not always provide adequate error reports.</span></span> <span data-ttu-id="c73bc-156">En comparación, el Shell de Operations Manager proporciona información detallada.</span><span class="sxs-lookup"><span data-stu-id="c73bc-156">By comparison, the Operations Manager Shell provides detailed information.</span></span> <span data-ttu-id="c73bc-157">Si usa Operations Manager y encuentra problemas al importar un módulo de administración, importe el paquete mediante el Shell de Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="c73bc-157">If you are using Operations Manager and you encounter issues when importing a management pack, import the pack by using the Operations Manager Shell.</span></span> <span data-ttu-id="c73bc-158">La información proporcionada por el Shell de Operations Manager puede ayudarle a determinar por qué se ha fallado la importación.</span><span class="sxs-lookup"><span data-stu-id="c73bc-158">The information provided by Operations Manager Shell can help you determine why the import failed.</span></span>

1. <span data-ttu-id="c73bc-159">Haga **clic en** Inicio , en Todos **los** programas, en **Microsoft System Center 2012,** en **Operations Manager** y, a continuación, en Shell de **Operations Manager**.</span><span class="sxs-lookup"><span data-stu-id="c73bc-159">Click **Start**, click **All Programs**, click **Microsoft System Center 2012**, click **Operations Manager**, and then click **Operations Manager Shell**.</span></span>

2. <span data-ttu-id="c73bc-160">En shell de Operations Manager, escriba el siguiente comando en el símbolo del sistema, usando la ruta de acceso real a la copia del archivo Microsoft.LS.2019.Monitoring.ActiveMonitoring.mp y, a continuación, presione ENTRAR:</span><span class="sxs-lookup"><span data-stu-id="c73bc-160">In Operations Manager Shell, type the following command at the command prompt, using the actual path to your copy of the file Microsoft.LS.2019.Monitoring.ActiveMonitoring.mp, and then press ENTER:</span></span>

   ```PowerShell
   Import-SCOMManagementPack -FullName "D:\MP\Microsoft.LS.2019.Monitoring.ActiveMonitoring.mp"
   ```

3. <span data-ttu-id="c73bc-161">Después de importar el primer módulo de administración, repita el proceso con la ruta de acceso a la copia del archivo Microsoft.LS.2019.Monitoring.ComponentAndUser.mp:</span><span class="sxs-lookup"><span data-stu-id="c73bc-161">After you have imported the first management pack, repeat the process, using the path to your copy of the file Microsoft.LS.2019.Monitoring.ComponentAndUser.mp:</span></span>

   ```PowerShell
   Import-SCOMManagementPack -FullName "D:\MP\Microsoft.LS.2019.Monitoring.ComponentAndUser.mp"
   ```