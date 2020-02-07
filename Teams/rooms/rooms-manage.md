---
title: Información general de administración para salas de Microsoft Teams
ms.author: dstrome
author: dstrome
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 39d7dc65-22c3-400f-91f1-87ed2fd792b6
ms.collection:
- M365-collaboration
description: Información general de administración para salas de Microsoft Teams.
ms.openlocfilehash: 3a56a03342ca0edb0da9dc9ed3a4cada77816bc7
ms.sourcegitcommit: bfa5b8db4e42e0480542d61fe05716c52016873c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41825888"
---
# <a name="management-overview"></a><span data-ttu-id="2f32b-103">Introducción a la administración</span><span class="sxs-lookup"><span data-stu-id="2f32b-103">Management overview</span></span>

<span data-ttu-id="2f32b-104">Es esencial que desarrolle y ejecute el mantenimiento y las operaciones constantes para asegurarse de que los sistemas de salas de Microsoft Teams estén disponibles para sus usuarios y ofrezcan una excelente experiencia de usuario.</span><span class="sxs-lookup"><span data-stu-id="2f32b-104">It’s essential that you develop and execute ongoing maintenance and operations to ensure that your Microsoft Teams Rooms systems are available for your users and deliver a great user experience.</span></span> 

## <a name="monitoring"></a><span data-ttu-id="2f32b-105">Supervisión</span><span class="sxs-lookup"><span data-stu-id="2f32b-105">Monitoring</span></span> 

<span data-ttu-id="2f32b-106">La supervisión de los sistemas de salas de Microsoft Teams consta de dos actividades clave:</span><span class="sxs-lookup"><span data-stu-id="2f32b-106">Monitoring Microsoft Teams Rooms systems consists of two key activities:</span></span>

- <span data-ttu-id="2f32b-107">Supervisión de dispositivos, aplicaciones y dispositivos periféricos</span><span class="sxs-lookup"><span data-stu-id="2f32b-107">Device, application, and peripheral device monitoring</span></span>
- <span data-ttu-id="2f32b-108">Supervisión de la calidad y la confiabilidad (CQD)</span><span class="sxs-lookup"><span data-stu-id="2f32b-108">Quality and reliability monitoring (CQD)</span></span>

### <a name="microsoft-teams-rooms-device-application-and-peripheral-device-monitoring"></a><span data-ttu-id="2f32b-109">Salas de supervisión de dispositivos, aplicaciones y dispositivos periféricos de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="2f32b-109">Microsoft Teams Rooms device, application, and peripheral device monitoring</span></span>

<span data-ttu-id="2f32b-110">Para asegurarse de que los usuarios pueden usar las unidades de salas de Microsoft Teams, las unidades deben estar conectadas a la red con la aplicación salas de Microsoft Teams configurada correctamente y estar conectadas a dispositivos periféricos en funcionamiento.</span><span class="sxs-lookup"><span data-stu-id="2f32b-110">To ensure that users are able to use the Microsoft Teams Rooms units, the units must be on, connected to the network with the Microsoft Teams Rooms application correctly configured, and be connected to functioning peripheral devices.</span></span> 

<span data-ttu-id="2f32b-111">La información sobre el estado de la aplicación salas de Microsoft Teams y los dispositivos periféricos conectados está escrita por la aplicación salas de Microsoft Teams en el registro de eventos de Windows y documentada en [comprender las entradas del registro](azure-monitor-manage.md#understand-the-log-entries).</span><span class="sxs-lookup"><span data-stu-id="2f32b-111">Information about the state of the Microsoft Teams Rooms application and connected peripheral devices is written by the Microsoft Teams Rooms application to the Windows event log and documented in [Understand the log entries](azure-monitor-manage.md#understand-the-log-entries).</span></span> 

|<span data-ttu-id="2f32b-112">**Al**</span><span class="sxs-lookup"><span data-stu-id="2f32b-112">**Setting**</span></span>|<span data-ttu-id="2f32b-113">**Posible**</span><span class="sxs-lookup"><span data-stu-id="2f32b-113">**Allows**</span></span>|
|:-----|:-----|
|<span data-ttu-id="2f32b-114">HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon AutoAdminLogon = (DWORD) 1</span><span class="sxs-lookup"><span data-stu-id="2f32b-114">HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon AutoAdminLogon = (dword) 1</span></span>  <br/> |<span data-ttu-id="2f32b-115">Permite arrancar las salas de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="2f32b-115">Enables Microsoft Teams Rooms to boot up</span></span>  <br/> |
|<span data-ttu-id="2f32b-116">Administración de energía\> : on AC, apagar la pantalla después de 10 minutos</span><span class="sxs-lookup"><span data-stu-id="2f32b-116">Power Management -\> On AC, turn screen off after 10 minutes</span></span>  <br/> <span data-ttu-id="2f32b-117">Administración de energía\> : on AC, no poner el sistema en suspensión</span><span class="sxs-lookup"><span data-stu-id="2f32b-117">Power Management -\> On AC, never put system to sleep</span></span>  <br/> |<span data-ttu-id="2f32b-118">Permite que las salas de Microsoft Teams desactiven las pantallas adjuntas y se reactiven automáticamente.</span><span class="sxs-lookup"><span data-stu-id="2f32b-118">Enables Microsoft Teams Rooms to turn off attached displays and wake up automatically</span></span>  <br/> |
|<span data-ttu-id="2f32b-119">net accounts /maxpwage:unlimited</span><span class="sxs-lookup"><span data-stu-id="2f32b-119">net accounts /maxpwage:unlimited</span></span>  <br/> <span data-ttu-id="2f32b-120">O medios alternativos para deshabilitar la opción de caducidad de la contraseña en la cuenta local.</span><span class="sxs-lookup"><span data-stu-id="2f32b-120">Or equivalent means of disabling password expiration on the local account.</span></span> <span data-ttu-id="2f32b-121">Si esto no se realiza, la cuenta de Skype no podrá iniciar sesión indicando que la contraseña ha caducado.</span><span class="sxs-lookup"><span data-stu-id="2f32b-121">Failure to do this will eventually cause the Skype account to fail logon complaining about an expired password.</span></span> <span data-ttu-id="2f32b-122">Tenga en cuenta que esto afectará todas las cuentas locales de la máquina y, por consiguiente, si no se configura esto, la cuenta administrativa del cuadro eventualmente también caducará.</span><span class="sxs-lookup"><span data-stu-id="2f32b-122">Note that this impacts all local accounts on the machine, and thus failure to set this will also cause the administrative account on the box to eventually expire as well.</span></span>  <br/> |<span data-ttu-id="2f32b-123">Permite que la cuenta de Skype siempre inicie sesión</span><span class="sxs-lookup"><span data-stu-id="2f32b-123">Enables Skype account to always log in</span></span>  <br/> |

<span data-ttu-id="2f32b-124">La transferencia de archivos mediante directivas de grupo se trata en [configurar un elemento de archivo](https://technet.microsoft.com/library/cc772536%28v=ws.11%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="2f32b-124">Transferring files using Group Policies is discussed in [Configure a File Item](https://technet.microsoft.com/library/cc772536%28v=ws.11%29.aspx).</span></span>
  
## <a name="remote-management-using-powershell"></a><span data-ttu-id="2f32b-125">Administración remota con PowerShell</span><span class="sxs-lookup"><span data-stu-id="2f32b-125">Remote Management using PowerShell</span></span>
<span data-ttu-id="2f32b-126"><a name="RemotePS"> </a></span><span class="sxs-lookup"><span data-stu-id="2f32b-126"><a name="RemotePS"> </a></span></span>

<span data-ttu-id="2f32b-127">Le recomendamos que use Microsoft Operations Manager suite para supervisar los sistemas de salas de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="2f32b-127">We recommend that you use Microsoft Operations Manager Suite to monitor your Microsoft Teams Rooms systems.</span></span> <span data-ttu-id="2f32b-128">Para obtener instrucciones sobre cómo configurar la supervisión y las alertas básicas, consulte [implementar la administración de salas de Microsoft Teams con Azure monitor](azure-monitor-deploy.md).</span><span class="sxs-lookup"><span data-stu-id="2f32b-128">For guidance on how to set up monitoring and basic alerting, see [Deploy Microsoft Teams Rooms management with Azure Monitor](azure-monitor-deploy.md).</span></span> 

<span data-ttu-id="2f32b-129">Con esta guía, puede crear un panel fácil de usar para identificar cualquier problema con las unidades de salas de Microsoft Teams en toda su implementación.</span><span class="sxs-lookup"><span data-stu-id="2f32b-129">Using this guidance, you can create a simple-to-use dashboard to identify any issues with your Microsoft Teams Rooms units across your deployment.</span></span> 

|    |     |
|-----------|------------|
|![](../media/audio_conferencing_image7.png) <br/><span data-ttu-id="2f32b-130">Puntos de decisión</span><span class="sxs-lookup"><span data-stu-id="2f32b-130">Decision points</span></span>|<ul><li><span data-ttu-id="2f32b-131">Confirme que va a usar Operations Management Suite para supervisar la implementación de las salas de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="2f32b-131">Confirm that you'll use Operations Management Suite to monitor your Microsoft Teams Rooms deployment.</span></span></li><li><span data-ttu-id="2f32b-132">Decida la lista de distribución de destino que usará para las alertas de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="2f32b-132">Decide the target distribution list you’ll use for email alerts.</span></span></li></ul>|
|![](../media/audio_conferencing_image9.png)<br/><span data-ttu-id="2f32b-133">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="2f32b-133">Next steps</span></span>|<ul><li><span data-ttu-id="2f32b-134">Definir el método de supervisión de la calidad y la fiabilidad.</span><span class="sxs-lookup"><span data-stu-id="2f32b-134">Define your quality and reliability monitoring approach.</span></span></li></ul>|

## <a name="quality-and-reliability-monitoring-cqd"></a><span data-ttu-id="2f32b-135">Supervisión de la calidad y la confiabilidad (CQD)</span><span class="sxs-lookup"><span data-stu-id="2f32b-135">Quality and reliability monitoring (CQD)</span></span>

<span data-ttu-id="2f32b-136">Le recomendamos que implemente procedimientos continuos de supervisión de la calidad operativa y la confiabilidad como parte de su implementación para controlar las tendencias de la calidad y la confiabilidad de las llamadas y las reuniones, identificar las áreas de preocupación y trabajar en la resolución.</span><span class="sxs-lookup"><span data-stu-id="2f32b-136">We recommend that you implement ongoing operational quality and reliability monitoring procedures as part of your deployment to monitor the trending of call and meeting quality and reliability, identifying any areas of concern and working toward a resolution.</span></span> 

<span data-ttu-id="2f32b-137">Al cargar la información de su edificio en el CQD, puede investigar tendencias de la calidad de las llamadas y de la fiabilidad en un nivel por construcción, lo que facilita la comparación de los edificios y concentra su atención en problemas específicos.</span><span class="sxs-lookup"><span data-stu-id="2f32b-137">When you upload your building information to CQD you can investigate call quality and reliability trends on a per-building level, which makes it easy to compare buildings and focus your attention on specific problems.</span></span>

<span data-ttu-id="2f32b-138">Le recomendamos que revise y siga la [Guía de revisión de la calidad de la experiencia](https://aka.ms/qerguide) para identificar tendencias de calidad y confiabilidad, y crear un plan de acción para resolverlos.</span><span class="sxs-lookup"><span data-stu-id="2f32b-138">We recommend that you review and follow the [Quality of Experience Review Guide](https://aka.ms/qerguide) to identify quality and reliability trends, and create an action plan to resolve them.</span></span> 

## <a name="updating-the-microsoft-teams-rooms-os-and-microsoft-teams-rooms-application"></a><span data-ttu-id="2f32b-139">Actualización de la aplicación Microsoft Teams Rooms OS and Microsoft Teams Rooms</span><span class="sxs-lookup"><span data-stu-id="2f32b-139">Updating the Microsoft Teams Rooms OS and Microsoft Teams Rooms application</span></span>

<span data-ttu-id="2f32b-140">Le recomendamos que actualice la aplicación Microsoft Teams Rooms OS and Microsoft Teams Rooms para beneficiarse de las actualizaciones y mejoras de productos.</span><span class="sxs-lookup"><span data-stu-id="2f32b-140">We recommend that you update the Microsoft Teams Rooms OS and Microsoft Teams Rooms application to benefit from product updates and improvements.</span></span> <span data-ttu-id="2f32b-141">Para obtener instrucciones detalladas, consulte [Manage Microsoft Teams Rooms](rooms-operations.md#software-updates).</span><span class="sxs-lookup"><span data-stu-id="2f32b-141">For detailed guidance, see [Manage Microsoft Teams Rooms](rooms-operations.md#software-updates).</span></span> 

## <a name="windows-updates"></a><span data-ttu-id="2f32b-142">Actualizaciones de Windows</span><span class="sxs-lookup"><span data-stu-id="2f32b-142">Windows Updates</span></span>

<span data-ttu-id="2f32b-143">Salas de Microsoft Teams se ejecuta en Windows 10 Enterprise IoT o Windows 10 Enterprise (VL) y recibe las mismas actualizaciones de Windows y OS que un escritorio estándar.</span><span class="sxs-lookup"><span data-stu-id="2f32b-143">Microsoft Teams Rooms runs on Windows 10 Enterprise IoT or Windows 10 Enterprise (VL) and receives the same Windows Updates and OS builds as a standard desktop.</span></span> <span data-ttu-id="2f32b-144">Para obtener más información, consulte [administrar actualizaciones de Windows](updates.md) .</span><span class="sxs-lookup"><span data-stu-id="2f32b-144">See [Manage Windows Updates](updates.md) for details.</span></span>


## <a name="troubleshooting"></a><span data-ttu-id="2f32b-145">Solución de problemas</span><span class="sxs-lookup"><span data-stu-id="2f32b-145">Troubleshooting</span></span>

<span data-ttu-id="2f32b-146">Le recomendamos que configure las alertas de Operations Management Suite como se describe en la sección anterior, de modo que el equipo de operaciones y el Departamento de soporte técnico recibirán una alerta de problemas con cualquier problema de las salas de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="2f32b-146">We recommend that you set up Operations Management Suite alerting as described in the section above so that your operations team and helpdesk will be alerted to any Microsoft Teams Rooms issues.</span></span> <span data-ttu-id="2f32b-147">Las opciones que tiene para la administración remota de PowerShell se describen en [administración remota con PowerShell](rooms-operations.md#remote-management-using-powershell).</span><span class="sxs-lookup"><span data-stu-id="2f32b-147">The options you have for PowerShell remote management are described in [Remote Management using PowerShell](rooms-operations.md#remote-management-using-powershell).</span></span> <span data-ttu-id="2f32b-148">En el caso de que se desconecte un dispositivo periférico, es posible que deba depender de las "manos inteligentes" locales o de la asistencia de TI para investigar y volver a conectar los dispositivos.</span><span class="sxs-lookup"><span data-stu-id="2f32b-148">In the event that a peripheral device is disconnected, you might need to rely on local “smart hands” or IT support to investigate and reconnect the devices.</span></span> 

<span data-ttu-id="2f32b-149">Para obtener más información sobre la solución de problemas y el modo de administración, consulte [modo de administración y administración de dispositivos](rooms-operations.md#admin-mode-and-device-management).</span><span class="sxs-lookup"><span data-stu-id="2f32b-149">For more information about troubleshooting and admin mode, see [Admin mode and device management](rooms-operations.md#admin-mode-and-device-management).</span></span> 


## <a name="see-also"></a><span data-ttu-id="2f32b-150">Vea también</span><span class="sxs-lookup"><span data-stu-id="2f32b-150">See also</span></span>

[<span data-ttu-id="2f32b-151">Ayuda de Salas de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="2f32b-151">Microsoft Teams Rooms help</span></span>](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[<span data-ttu-id="2f32b-152">Plan para salas de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="2f32b-152">Plan for Microsoft Teams Rooms</span></span>](rooms-plan.md)

[<span data-ttu-id="2f32b-153">Implementar salas de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="2f32b-153">Deploy Microsoft Teams Rooms</span></span>](rooms-deploy.md)

[<span data-ttu-id="2f32b-154">Configurar una consola de salas de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="2f32b-154">Configure a Microsoft Teams Rooms console</span></span>](console.md)

[<span data-ttu-id="2f32b-155">Administrar de forma remota la configuración de la consola de salas de Microsoft Teams con un archivo de configuración XML</span><span class="sxs-lookup"><span data-stu-id="2f32b-155">Manage a Microsoft Teams Rooms console settings remotely with an XML configuration file</span></span>](xml-config-file.md)
