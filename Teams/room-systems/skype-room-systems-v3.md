---
title: Información general de administración para salas de Microsoft Teams
ms.author: jambirk
author: jambirk
ms.reviewer: davgroom
manager: serdars
ms.date: 5/10/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 39d7dc65-22c3-400f-91f1-87ed2fd792b6
ms.collection: M365-voice
description: Información general de administración para salas de Microsoft Teams.
ms.openlocfilehash: fd16015331273fbd5f524f571c07a1c055a0d04a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34288574"
---
# <a name="management-overview"></a><span data-ttu-id="e53a7-103">Introducción a la administración</span><span class="sxs-lookup"><span data-stu-id="e53a7-103">Management overview</span></span> 

<span data-ttu-id="e53a7-104">Es esencial que desarrolle y ejecute el mantenimiento y las operaciones constantes para asegurarse de que los sistemas de salas de Microsoft Teams estén disponibles para sus usuarios y ofrezcan una excelente experiencia de usuario.</span><span class="sxs-lookup"><span data-stu-id="e53a7-104">It’s essential that you develop and execute ongoing maintenance and operations to ensure that your Microsoft Teams Rooms systems are available for your users and deliver a great user experience.</span></span> 

## <a name="monitoring"></a><span data-ttu-id="e53a7-105">Supervisión</span><span class="sxs-lookup"><span data-stu-id="e53a7-105">Monitoring</span></span> 

<span data-ttu-id="e53a7-106">La supervisión de los sistemas de salas de Microsoft Teams consta de dos actividades clave:</span><span class="sxs-lookup"><span data-stu-id="e53a7-106">Monitoring Microsoft Teams Rooms systems consists of two key activities:</span></span>

-  <span data-ttu-id="e53a7-107">Supervisión de dispositivos, aplicaciones y dispositivos periféricos</span><span class="sxs-lookup"><span data-stu-id="e53a7-107">Device, application, and peripheral device monitoring</span></span>

-  <span data-ttu-id="e53a7-108">Supervisión de la calidad y la confiabilidad (CQD)</span><span class="sxs-lookup"><span data-stu-id="e53a7-108">Quality and reliability monitoring (CQD)</span></span>

### <a name="microsoft-teams-rooms-device-application-and-peripheral-device-monitoring"></a><span data-ttu-id="e53a7-109">Salas de supervisión de dispositivos, aplicaciones y dispositivos periféricos de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="e53a7-109">Microsoft Teams Rooms device, application, and peripheral device monitoring</span></span>

<span data-ttu-id="e53a7-110">Para asegurarse de que los usuarios pueden usar las unidades de salas de Microsoft Teams, las unidades deben estar conectadas a la red con la aplicación salas de Microsoft Teams configurada correctamente y estar conectadas a dispositivos periféricos en funcionamiento.</span><span class="sxs-lookup"><span data-stu-id="e53a7-110">To ensure that users are able to use the Microsoft Teams Rooms units, the units must be on, connected to the network with the Microsoft Teams Rooms application correctly configured, and be connected to functioning peripheral devices.</span></span> 


<span data-ttu-id="e53a7-111">La información sobre el estado de la aplicación salas de Microsoft Teams y los dispositivos periféricos conectados está escrita por la aplicación salas de Microsoft Teams en el registro de eventos de Windows y documentada en [comprender las entradas del registro](azure-monitor-manage.md#understand-the-log-entries).</span><span class="sxs-lookup"><span data-stu-id="e53a7-111">Information about the state of the Microsoft Teams Rooms application and connected peripheral devices is written by the Microsoft Teams Rooms application to the Windows event log and documented in [Understand the log entries](azure-monitor-manage.md#understand-the-log-entries).</span></span> 

|<span data-ttu-id="e53a7-112">**Al**</span><span class="sxs-lookup"><span data-stu-id="e53a7-112">**Setting**</span></span>|<span data-ttu-id="e53a7-113">**Posible**</span><span class="sxs-lookup"><span data-stu-id="e53a7-113">**Allows**</span></span>|
|:-----|:-----|
|<span data-ttu-id="e53a7-114">HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon AutoAdminLogon = (DWORD) 1</span><span class="sxs-lookup"><span data-stu-id="e53a7-114">HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon AutoAdminLogon = (dword) 1</span></span>  <br/> |<span data-ttu-id="e53a7-115">Permite arrancar las salas de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="e53a7-115">Enables Microsoft Teams Rooms to boot up</span></span>  <br/> |
|<span data-ttu-id="e53a7-116">Administración de energía\> : on AC, apagar la pantalla después de 10 minutos</span><span class="sxs-lookup"><span data-stu-id="e53a7-116">Power Management -\> On AC, turn screen off after 10 minutes</span></span>  <br/> <span data-ttu-id="e53a7-117">Administración de energía\> : on AC, no poner el sistema en suspensión</span><span class="sxs-lookup"><span data-stu-id="e53a7-117">Power Management -\> On AC, never put system to sleep</span></span>  <br/> |<span data-ttu-id="e53a7-118">Permite que las salas de Microsoft Teams desactiven las pantallas adjuntas y se reactiven automáticamente.</span><span class="sxs-lookup"><span data-stu-id="e53a7-118">Enables Microsoft Teams Rooms to turn off attached displays and wake up automatically</span></span>  <br/> |
|<span data-ttu-id="e53a7-119">net accounts /maxpwage:unlimited</span><span class="sxs-lookup"><span data-stu-id="e53a7-119">net accounts /maxpwage:unlimited</span></span>  <br/> <span data-ttu-id="e53a7-120">O medios alternativos para deshabilitar la opción de caducidad de la contraseña en la cuenta local.</span><span class="sxs-lookup"><span data-stu-id="e53a7-120">Or equivalent means of disabling password expiration on the local account.</span></span> <span data-ttu-id="e53a7-121">Si esto no se realiza, la cuenta de Skype no podrá iniciar sesión indicando que la contraseña ha caducado.</span><span class="sxs-lookup"><span data-stu-id="e53a7-121">Failure to do this will eventually cause the Skype account to fail logon complaining about an expired password.</span></span> <span data-ttu-id="e53a7-122">Tenga en cuenta que esto afectará todas las cuentas locales de la máquina y, por consiguiente, si no se configura esto, la cuenta administrativa del cuadro eventualmente también caducará.</span><span class="sxs-lookup"><span data-stu-id="e53a7-122">Note that this impacts all local accounts on the machine, and thus failure to set this will also cause the administrative account on the box to eventually expire as well.</span></span>  <br/> |<span data-ttu-id="e53a7-123">Permite que la cuenta de Skype siempre inicie sesión</span><span class="sxs-lookup"><span data-stu-id="e53a7-123">Enables Skype account to always log in</span></span>  <br/> |
   
<span data-ttu-id="e53a7-124">La transferencia de archivos mediante directivas de grupo se trata en [configurar un elemento de archivo](https://technet.microsoft.com/en-us/library/cc772536%28v=ws.11%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="e53a7-124">Transferring files using Group Policies is discussed in [Configure a File Item](https://technet.microsoft.com/en-us/library/cc772536%28v=ws.11%29.aspx).</span></span>
  
## <a name="remote-management-using-powershell"></a><span data-ttu-id="e53a7-125">Administración remota con PowerShell</span><span class="sxs-lookup"><span data-stu-id="e53a7-125">Remote Management using PowerShell</span></span>
<span data-ttu-id="e53a7-126"><a name="RemotePS"> </a></span><span class="sxs-lookup"><span data-stu-id="e53a7-126"></span></span>

<span data-ttu-id="e53a7-127">Le recomendamos que use Microsoft Operations Manager suite para supervisar los sistemas de salas de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="e53a7-127">We recommend that you use Microsoft Operations Manager Suite to monitor your Microsoft Teams Rooms systems.</span></span> <span data-ttu-id="e53a7-128">Para obtener instrucciones sobre cómo configurar la supervisión y las alertas básicas, consulte [implementar la administración de salas de Microsoft Teams con Azure monitor](azure-monitor-deploy.md).</span><span class="sxs-lookup"><span data-stu-id="e53a7-128">For guidance on how to set up monitoring and basic alerting, see [Deploy Microsoft Teams Rooms management with Azure Monitor](azure-monitor-deploy.md).</span></span> 

<span data-ttu-id="e53a7-129">Con esta guía, puede crear un panel fácil de usar para identificar cualquier problema con las unidades de salas de Microsoft Teams en toda su implementación.</span><span class="sxs-lookup"><span data-stu-id="e53a7-129">Using this guidance, you can create a simple-to-use dashboard to identify any issues with your Microsoft Teams Rooms units across your deployment.</span></span> 

|    |     |
|-----------|------------|
|![](../media/audio_conferencing_image7.png) <br/><span data-ttu-id="e53a7-130">Puntos de decisión</span><span class="sxs-lookup"><span data-stu-id="e53a7-130">Decision points</span></span>|<ul><li><span data-ttu-id="e53a7-131">Confirme que va a usar Operations Management Suite para supervisar la implementación de las salas de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="e53a7-131">Confirm that you'll use Operations Management Suite to monitor your Microsoft Teams Rooms deployment.</span></span></li><li><span data-ttu-id="e53a7-132">Decida la lista de distribución de destino que usará para las alertas de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="e53a7-132">Decide the target distribution list you’ll use for email alerts.</span></span></li></ul>|
|![](../media/audio_conferencing_image9.png)<br/><span data-ttu-id="e53a7-133">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="e53a7-133">Next steps</span></span>|<ul><li><span data-ttu-id="e53a7-134">Definir el método de supervisión de la calidad y la fiabilidad.</span><span class="sxs-lookup"><span data-stu-id="e53a7-134">Define your quality and reliability monitoring approach.</span></span></li></ul>|

## <a name="quality-and-reliability-monitoring-cqd"></a><span data-ttu-id="e53a7-135">Supervisión de la calidad y la confiabilidad (CQD)</span><span class="sxs-lookup"><span data-stu-id="e53a7-135">Quality and reliability monitoring (CQD)</span></span>

<span data-ttu-id="e53a7-136">Le recomendamos que implemente procedimientos continuos de supervisión de la calidad operativa y la confiabilidad como parte de su implementación para controlar las tendencias de la calidad y la confiabilidad de las llamadas y las reuniones, identificar las áreas de preocupación y trabajar en la resolución.</span><span class="sxs-lookup"><span data-stu-id="e53a7-136">We recommend that you implement ongoing operational quality and reliability monitoring procedures as part of your deployment to monitor the trending of call and meeting quality and reliability, identifying any areas of concern and working toward a resolution.</span></span> 

<span data-ttu-id="e53a7-137">Al cargar la información de su edificio en el CQD, puede investigar tendencias de la calidad de las llamadas y de la fiabilidad en un nivel por construcción, lo que facilita la comparación de los edificios y concentra su atención en problemas específicos.</span><span class="sxs-lookup"><span data-stu-id="e53a7-137">When you upload your building information to CQD you can investigate call quality and reliability trends on a per-building level, which makes it easy to compare buildings and focus your attention on specific problems.</span></span> <span data-ttu-id="e53a7-138">Para obtener más información, descargue el [monitor-CQD para la guía de entrega y operaciones de Skype empresarial online](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=6_2_0_15).</span><span class="sxs-lookup"><span data-stu-id="e53a7-138">For more information, download the [Monitor-CQD for Skype for Business Online-Delivery and Operations Guide](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=6_2_0_15).</span></span> 

<span data-ttu-id="e53a7-139">Le recomendamos que revise y siga la [Guía de revisión de la calidad de la experiencia](https://aka.ms/qerguide) para identificar tendencias de calidad y confiabilidad, y crear un plan de acción para resolverlos.</span><span class="sxs-lookup"><span data-stu-id="e53a7-139">We recommend that you review and follow the [Quality of Experience Review Guide](https://aka.ms/qerguide) to identify quality and reliability trends, and create an action plan to resolve them.</span></span> 

## <a name="updating-the-microsoft-teams-rooms-os-and-microsoft-teams-rooms-application"></a><span data-ttu-id="e53a7-140">Actualización de la aplicación Microsoft Teams Rooms OS and Microsoft Teams Rooms</span><span class="sxs-lookup"><span data-stu-id="e53a7-140">Updating the Microsoft Teams Rooms OS and Microsoft Teams Rooms application</span></span>

<span data-ttu-id="e53a7-141">Le recomendamos que actualice la aplicación Microsoft Teams Rooms OS and Microsoft Teams Rooms para beneficiarse de las actualizaciones y mejoras de productos.</span><span class="sxs-lookup"><span data-stu-id="e53a7-141">We recommend that you update the Microsoft Teams Rooms OS and Microsoft Teams Rooms application to benefit from product updates and improvements.</span></span> <span data-ttu-id="e53a7-142">Para obtener instrucciones detalladas, consulte [Manage Microsoft Teams Rooms](room-systems-v2-operations.md#software-updates).</span><span class="sxs-lookup"><span data-stu-id="e53a7-142">For detailed guidance, see [Manage Microsoft Teams Rooms](room-systems-v2-operations.md#software-updates).</span></span> 

## <a name="windows-updates"></a><span data-ttu-id="e53a7-143">Actualizaciones de Windows</span><span class="sxs-lookup"><span data-stu-id="e53a7-143">Windows Updates</span></span>

<span data-ttu-id="e53a7-144">Salas de Microsoft Teams se ejecuta en Windows 10 Enterprise IoT o Windows 10 Enterprise (VL) y recibe las mismas actualizaciones de Windows y OS que un escritorio estándar.</span><span class="sxs-lookup"><span data-stu-id="e53a7-144">Microsoft Teams Rooms runs on Windows 10 Enterprise IoT or Windows 10 Enterprise (VL) and receives the same Windows Updates and OS builds as a standard desktop.</span></span> <span data-ttu-id="e53a7-145">Para obtener más información, consulte [administrar actualizaciones de Windows](updates.md) .</span><span class="sxs-lookup"><span data-stu-id="e53a7-145">See [Manage Windows Updates](updates.md) for details.</span></span>


## <a name="troubleshooting"></a><span data-ttu-id="e53a7-146">Solución de problemas</span><span class="sxs-lookup"><span data-stu-id="e53a7-146">Troubleshooting</span></span>

<span data-ttu-id="e53a7-147">Le recomendamos que configure las alertas de Operations Management Suite como se describe en la sección anterior, de modo que el equipo de operaciones y el Departamento de soporte técnico recibirán una alerta de problemas con cualquier problema de las salas de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="e53a7-147">We recommend that you set up Operations Management Suite alerting as described in the section above so that your operations team and helpdesk will be alerted to any Microsoft Teams Rooms issues.</span></span> <span data-ttu-id="e53a7-148">Las opciones que tiene para la administración remota de PowerShell se describen en [administración remota con PowerShell](room-systems-v2-operations.md#remote-management-using-powershell).</span><span class="sxs-lookup"><span data-stu-id="e53a7-148">The options you have for PowerShell remote management are described in [Remote Management using PowerShell](room-systems-v2-operations.md#remote-management-using-powershell).</span></span> <span data-ttu-id="e53a7-149">En el caso de que se desconecte un dispositivo periférico, es posible que deba depender de las "manos inteligentes" locales o de la asistencia de TI para investigar y volver a conectar los dispositivos.</span><span class="sxs-lookup"><span data-stu-id="e53a7-149">In the event that a peripheral device is disconnected, you might need to rely on local “smart hands” or IT support to investigate and reconnect the devices.</span></span> 

<span data-ttu-id="e53a7-150">Para obtener más información sobre la solución de problemas y el modo de administración, consulte [administrar salas de Microsoft Teams](room-systems-v2-operations.md#admin-mode-and-device-management).</span><span class="sxs-lookup"><span data-stu-id="e53a7-150">For more information about troubleshooting and admin mode, see [Manage Microsoft Teams Rooms](room-systems-v2-operations.md#admin-mode-and-device-management).</span></span> 


## <a name="see-also"></a><span data-ttu-id="e53a7-151">Vea también</span><span class="sxs-lookup"><span data-stu-id="e53a7-151">See also</span></span>

[<span data-ttu-id="e53a7-152">Ayuda de Salas de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="e53a7-152">Microsoft Teams Rooms help</span></span>](https://support.office.com/en-us/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[<span data-ttu-id="e53a7-153">Plan para salas de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="e53a7-153">Plan for Microsoft Teams Rooms</span></span>](skype-room-systems-v2-0.md)

[<span data-ttu-id="e53a7-154">Implementar salas de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="e53a7-154">Deploy Microsoft Teams Rooms</span></span>](room-systems-v2.md)

[<span data-ttu-id="e53a7-155">Configurar una consola de salas de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="e53a7-155">Configure a Microsoft Teams Rooms console</span></span>](console.md)

[<span data-ttu-id="e53a7-156">Administrar de forma remota la configuración de la consola de salas de Microsoft Teams con un archivo de configuración XML</span><span class="sxs-lookup"><span data-stu-id="e53a7-156">Manage a Microsoft Teams Rooms console settings remotely with an XML configuration file</span></span>](xml-config-file.md)
