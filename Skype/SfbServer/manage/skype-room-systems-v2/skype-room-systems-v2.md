---
title: Introducción a la administración de salas de equipos de Microsoft
ms.author: jambirk
author: jambirk
ms.reviewer: davgroom
manager: serdars
ms.date: 5/10/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 39d7dc65-22c3-400f-91f1-87ed2fd792b6
ms.collection: M365-voice
description: Introducción a la administración de salas de equipos de Microsoft.
ms.openlocfilehash: a06ffc6bb0aa69b493c95a516946c322034913f8
ms.sourcegitcommit: 4266c1fbd8557bf2bf65447557ee8d597f90ccd3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/30/2019
ms.locfileid: "31012496"
---
# <a name="management-overview"></a><span data-ttu-id="64c79-103">Introducción a la administración</span><span class="sxs-lookup"><span data-stu-id="64c79-103">Management overview</span></span> 

<span data-ttu-id="64c79-104">Es esencial que desarrollar y ejecutar el mantenimiento continuado y operaciones para asegurarse de que los sistemas de salas de equipos de Microsoft están disponibles para los usuarios y ofrecen a un usuario excelente experimentan.</span><span class="sxs-lookup"><span data-stu-id="64c79-104">It’s essential that you develop and execute ongoing maintenance and operations to ensure that your Microsoft Teams Rooms systems are available for your users and deliver a great user experience.</span></span> 

## <a name="monitoring"></a><span data-ttu-id="64c79-105">Supervisión</span><span class="sxs-lookup"><span data-stu-id="64c79-105">Monitoring</span></span> 

<span data-ttu-id="64c79-106">Supervisión de sistemas de salas de equipos de Microsoft consta de dos actividades clave:</span><span class="sxs-lookup"><span data-stu-id="64c79-106">Monitoring Microsoft Teams Rooms systems consists of two key activities:</span></span>

-  <span data-ttu-id="64c79-107">Dispositivo, la aplicación y la supervisión de dispositivos periféricos</span><span class="sxs-lookup"><span data-stu-id="64c79-107">Device, application, and peripheral device monitoring</span></span>

-  <span data-ttu-id="64c79-108">Calidad y confiabilidad de supervisión (CQD)</span><span class="sxs-lookup"><span data-stu-id="64c79-108">Quality and reliability monitoring (CQD)</span></span>

### <a name="microsoft-teams-rooms-device-application-and-peripheral-device-monitoring"></a><span data-ttu-id="64c79-109">Dispositivo de salas de equipos de Microsoft, la aplicación y la supervisión de dispositivos periféricos</span><span class="sxs-lookup"><span data-stu-id="64c79-109">Microsoft Teams Rooms device, application, and peripheral device monitoring</span></span>

<span data-ttu-id="64c79-110">Para asegurarse de que los usuarios podrán utilizar las unidades locales de los equipos de Microsoft, las unidades deben estar en, conectado a la red con la aplicación de salas de equipos de Microsoft configurada correctamente y estar conectadas a dispositivos periféricos funcionamiento.</span><span class="sxs-lookup"><span data-stu-id="64c79-110">To ensure that users are able to use the Microsoft Teams Rooms units, the units must be on, connected to the network with the Microsoft Teams Rooms application correctly configured, and be connected to functioning peripheral devices.</span></span> 


<span data-ttu-id="64c79-111">Información sobre el estado de la aplicación de Microsoft salones de los equipos y dispositivos periféricos conectados es escrita por la aplicación de salas de equipos de Microsoft para el registro de eventos de Windows y que se documentaron en [comprender las entradas del registro](azure-monitor.md#understand-the-log-entries).</span><span class="sxs-lookup"><span data-stu-id="64c79-111">Information about the state of the Microsoft Teams Rooms application and connected peripheral devices is written by the Microsoft Teams Rooms application to the Windows event log and documented in [Understand the log entries](azure-monitor.md#understand-the-log-entries).</span></span> 

|<span data-ttu-id="64c79-112">**Configuración**</span><span class="sxs-lookup"><span data-stu-id="64c79-112">**Setting**</span></span>|<span data-ttu-id="64c79-113">**Permite**</span><span class="sxs-lookup"><span data-stu-id="64c79-113">**Allows**</span></span>|
|:-----|:-----|
|<span data-ttu-id="64c79-114">HKLM\Software\Microsoft\Windows NT\CurrentVersion\Winlogon AutoAdminLogon = (dword) 1</span><span class="sxs-lookup"><span data-stu-id="64c79-114">HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon AutoAdminLogon = (dword) 1</span></span>  <br/> |<span data-ttu-id="64c79-115">Permite salones de los equipos de Microsoft para que se inicie</span><span class="sxs-lookup"><span data-stu-id="64c79-115">Enables Microsoft Teams Rooms to boot up</span></span>  <br/> |
|<span data-ttu-id="64c79-116">Administración de energía -\> en AC, desactivar pantalla después de 10 minutos</span><span class="sxs-lookup"><span data-stu-id="64c79-116">Power Management -\> On AC, turn screen off after 10 minutes</span></span>  <br/> <span data-ttu-id="64c79-117">Administración de energía -\> en AC, nunca colocar del sistema al modo de suspensión</span><span class="sxs-lookup"><span data-stu-id="64c79-117">Power Management -\> On AC, never put system to sleep</span></span>  <br/> |<span data-ttu-id="64c79-118">Permite salones de los equipos de Microsoft desactivar muestra adjunto y reactivar automáticamente</span><span class="sxs-lookup"><span data-stu-id="64c79-118">Enables Microsoft Teams Rooms to turn off attached displays and wake up automatically</span></span>  <br/> |
|<span data-ttu-id="64c79-119">net accounts /maxpwage:unlimited</span><span class="sxs-lookup"><span data-stu-id="64c79-119">net accounts /maxpwage:unlimited</span></span>  <br/> <span data-ttu-id="64c79-120">O medios alternativos para deshabilitar la opción de caducidad de la contraseña en la cuenta local.</span><span class="sxs-lookup"><span data-stu-id="64c79-120">Or equivalent means of disabling password expiration on the local account.</span></span> <span data-ttu-id="64c79-121">Si esto no se realiza, la cuenta de Skype no podrá iniciar sesión indicando que la contraseña ha caducado.</span><span class="sxs-lookup"><span data-stu-id="64c79-121">Failure to do this will eventually cause the Skype account to fail logon complaining about an expired password.</span></span> <span data-ttu-id="64c79-122">Tenga en cuenta que esto afectará todas las cuentas locales de la máquina y, por consiguiente, si no se configura esto, la cuenta administrativa del cuadro eventualmente también caducará.</span><span class="sxs-lookup"><span data-stu-id="64c79-122">Note that this impacts all local accounts on the machine, and thus failure to set this will also cause the administrative account on the box to eventually expire as well.</span></span>  <br/> |<span data-ttu-id="64c79-123">Permite que la cuenta de Skype siempre inicie sesión</span><span class="sxs-lookup"><span data-stu-id="64c79-123">Enables Skype account to always log in</span></span>  <br/> |
   
<span data-ttu-id="64c79-124">Transferencia de archivos mediante directivas de grupo se describe en [configurar un elemento de archivo](https://technet.microsoft.com/en-us/library/cc772536%28v=ws.11%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="64c79-124">Transferring files using Group Policies is discussed in [Configure a File Item](https://technet.microsoft.com/en-us/library/cc772536%28v=ws.11%29.aspx).</span></span>
  
## <a name="remote-management-using-powershell"></a><span data-ttu-id="64c79-125">Administración remota con PowerShell</span><span class="sxs-lookup"><span data-stu-id="64c79-125">Remote Management using PowerShell</span></span>
<span data-ttu-id="64c79-126"><a name="RemotePS"> </a></span><span class="sxs-lookup"><span data-stu-id="64c79-126"></span></span>

<span data-ttu-id="64c79-127">Se recomienda que utilice el conjunto de aplicaciones de Microsoft Operations Manager para supervisar los sistemas de salas de equipos de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="64c79-127">We recommend that you use Microsoft Operations Manager Suite to monitor your Microsoft Teams Rooms systems.</span></span> <span data-ttu-id="64c79-128">Para obtener instrucciones acerca de cómo configurar la supervisión y alertas básicas, vea [administración de implementación de salas de equipos de Microsoft con el Monitor de Azure](../../deploy/deploy-clients/azure-monitor.md).</span><span class="sxs-lookup"><span data-stu-id="64c79-128">For guidance on how to set up monitoring and basic alerting, see [Deploy Microsoft Teams Rooms management with Azure Monitor](../../deploy/deploy-clients/azure-monitor.md).</span></span> 

<span data-ttu-id="64c79-129">Uso de esta guía, puede crear un panel simple de usar para identificar los problemas con las unidades locales de los equipos de Microsoft a través de la implementación.</span><span class="sxs-lookup"><span data-stu-id="64c79-129">Using this guidance, you can create a simple-to-use dashboard to identify any issues with your Microsoft Teams Rooms units across your deployment.</span></span> 

|    |     |
|-----------|------------|
|![](../../media/audio_conferencing_image7.png) <br/><span data-ttu-id="64c79-130">Puntos de decisión</span><span class="sxs-lookup"><span data-stu-id="64c79-130">Decision points</span></span>|<ul><li><span data-ttu-id="64c79-131">Confirme que usará el conjunto de aplicaciones de las operaciones de administración para supervisar la implementación de salas de equipos de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="64c79-131">Confirm that you'll use Operations Management Suite to monitor your Microsoft Teams Rooms deployment.</span></span></li><li><span data-ttu-id="64c79-132">Decidir que va a utilizar para alertas de correo electrónico de la lista de distribución de destino.</span><span class="sxs-lookup"><span data-stu-id="64c79-132">Decide the target distribution list you’ll use for email alerts.</span></span></li></ul>|
|![](../../media/audio_conferencing_image9.png)<br/><span data-ttu-id="64c79-133">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="64c79-133">Next steps</span></span>|<ul><li><span data-ttu-id="64c79-134">Definir la calidad y el enfoque de supervisión de la confiabilidad.</span><span class="sxs-lookup"><span data-stu-id="64c79-134">Define your quality and reliability monitoring approach.</span></span></li></ul>|

## <a name="quality-and-reliability-monitoring-cqd"></a><span data-ttu-id="64c79-135">Calidad y confiabilidad de supervisión (CQD)</span><span class="sxs-lookup"><span data-stu-id="64c79-135">Quality and reliability monitoring (CQD)</span></span>

<span data-ttu-id="64c79-136">Se recomienda que implemente calidad operativa continuada y confiabilidad procedimientos de supervisión como parte de su implementación para supervisar las tendencias de llamada y la calidad de la reunión y la confiabilidad, que identifica las áreas de preocupación y trabajar hacia una resolución.</span><span class="sxs-lookup"><span data-stu-id="64c79-136">We recommend that you implement ongoing operational quality and reliability monitoring procedures as part of your deployment to monitor the trending of call and meeting quality and reliability, identifying any areas of concern and working toward a resolution.</span></span> 

<span data-ttu-id="64c79-137">Cuando se carga la información de creación en CQD puede investigar las tendencias de calidad y la confiabilidad de llamadas en un nivel por edificio, lo que facilita la comparación de los edificios y centra la atención en problemas específicos.</span><span class="sxs-lookup"><span data-stu-id="64c79-137">When you upload your building information to CQD you can investigate call quality and reliability trends on a per-building level, which makes it easy to compare buildings and focus your attention on specific problems.</span></span> <span data-ttu-id="64c79-138">Para obtener más información, descargue el [Monitor-CQD de Skype para entrega en línea de negocio y la Guía de operaciones](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=6_2_0_15).</span><span class="sxs-lookup"><span data-stu-id="64c79-138">For more information, download the [Monitor-CQD for Skype for Business Online-Delivery and Operations Guide](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=6_2_0_15).</span></span> 

<span data-ttu-id="64c79-139">Se recomienda que revise y siga la [Guía de revisión de calidad de experiencia](https://aka.ms/qerguide) para identificar las tendencias de calidad y la confiabilidad y crear un plan de acción para resolverlos conflictos.</span><span class="sxs-lookup"><span data-stu-id="64c79-139">We recommend that you review and follow the [Quality of Experience Review Guide](https://aka.ms/qerguide) to identify quality and reliability trends, and create an action plan to resolve them.</span></span> 

## <a name="updating-the-microsoft-teams-rooms-os-and-microsoft-teams-rooms-application"></a><span data-ttu-id="64c79-140">Actualización de la aplicación de sistema operativo de salones de los equipos de Microsoft y salas de equipos de Microsoft</span><span class="sxs-lookup"><span data-stu-id="64c79-140">Updating the Microsoft Teams Rooms OS and Microsoft Teams Rooms application</span></span>

<span data-ttu-id="64c79-141">Se recomienda que actualizar la aplicación de sistema operativo de salones de los equipos de Microsoft y salas de equipos de Microsoft para sacar partido de las actualizaciones del producto y las mejoras.</span><span class="sxs-lookup"><span data-stu-id="64c79-141">We recommend that you update the Microsoft Teams Rooms OS and Microsoft Teams Rooms application to benefit from product updates and improvements.</span></span> <span data-ttu-id="64c79-142">Para obtener instrucciones detalladas, consulte [Manage Rooms de los equipos de Microsoft](room-systems-v2-operations.md#software-updates).</span><span class="sxs-lookup"><span data-stu-id="64c79-142">For detailed guidance, see [Manage Microsoft Teams Rooms](room-systems-v2-operations.md#software-updates).</span></span> 

## <a name="windows-updates"></a><span data-ttu-id="64c79-143">Actualizaciones de Windows</span><span class="sxs-lookup"><span data-stu-id="64c79-143">Windows Updates</span></span>

<span data-ttu-id="64c79-144">Salones de los equipos de Microsoft se ejecuta en Windows 10 Enterprise IoT o Windows 10 Enterprise (VL) y recibe las compilaciones de actualizaciones de Windows y el sistema operativo mismas como un escritorio estándar.</span><span class="sxs-lookup"><span data-stu-id="64c79-144">Microsoft Teams Rooms runs on Windows 10 Enterprise IoT or Windows 10 Enterprise (VL) and receives the same Windows Updates and OS builds as a standard desktop.</span></span> <span data-ttu-id="64c79-145">Para obtener información detallada, vea [Administrar actualizaciones de Windows](updates.md) .</span><span class="sxs-lookup"><span data-stu-id="64c79-145">See [Manage Windows Updates](updates.md) for details.</span></span>


## <a name="troubleshooting"></a><span data-ttu-id="64c79-146">Solución de problemas</span><span class="sxs-lookup"><span data-stu-id="64c79-146">Troubleshooting</span></span>

<span data-ttu-id="64c79-147">Se recomienda que configure alertas del conjunto de aplicaciones de administración de operaciones tal como se describe en la sección anterior para que su equipo de operaciones y el departamento de soporte técnico le avisará de que cualquier problema de salas de equipos de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="64c79-147">We recommend that you set up Operations Management Suite alerting as described in the section above so that your operations team and helpdesk will be alerted to any Microsoft Teams Rooms issues.</span></span> <span data-ttu-id="64c79-148">Se describen las opciones disponibles para la administración remota de PowerShell en [PowerShell de uso de administración remota](room-systems-v2-operations.md#remote-management-using-powershell).</span><span class="sxs-lookup"><span data-stu-id="64c79-148">The options you have for PowerShell remote management are described in [Remote Management using PowerShell](room-systems-v2-operations.md#remote-management-using-powershell).</span></span> <span data-ttu-id="64c79-149">En caso de que se desconecta un dispositivo periférico, es posible que necesite se basan en locales "inteligentes manos" o soporte de TI para investigar y volver a conectar los dispositivos.</span><span class="sxs-lookup"><span data-stu-id="64c79-149">In the event that a peripheral device is disconnected, you might need to rely on local “smart hands” or IT support to investigate and reconnect the devices.</span></span> 

<span data-ttu-id="64c79-150">Para obtener más información sobre el modo de administración y solución de problemas, vea [Administrar salones de los equipos de Microsoft](room-systems-v2-operations.md#admin-mode-and-device-management).</span><span class="sxs-lookup"><span data-stu-id="64c79-150">For more information about troubleshooting and admin mode, see [Manage Microsoft Teams Rooms](room-systems-v2-operations.md#admin-mode-and-device-management).</span></span> 


## <a name="see-also"></a><span data-ttu-id="64c79-151">Consulte también</span><span class="sxs-lookup"><span data-stu-id="64c79-151">See also</span></span>

[<span data-ttu-id="64c79-152">Ayuda de salas de equipos de Microsoft</span><span class="sxs-lookup"><span data-stu-id="64c79-152">Microsoft Teams Rooms help</span></span>](https://support.office.com/en-us/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[<span data-ttu-id="64c79-153">Plan para salas de equipos de Microsoft</span><span class="sxs-lookup"><span data-stu-id="64c79-153">Plan for Microsoft Teams Rooms</span></span>](../../plan-your-deployment/clients-and-devices/skype-room-systems-v2-0.md)

[<span data-ttu-id="64c79-154">Implementación de salas de equipos de Microsoft</span><span class="sxs-lookup"><span data-stu-id="64c79-154">Deploy Microsoft Teams Rooms</span></span>](../../deploy/deploy-clients/room-systems-v2.md)

[<span data-ttu-id="64c79-155">Configurar una consola de salas de equipos de Microsoft</span><span class="sxs-lookup"><span data-stu-id="64c79-155">Configure a Microsoft Teams Rooms console</span></span>](../../deploy/deploy-clients/console.md)

[<span data-ttu-id="64c79-156">Administrar una configuración de la consola Microsoft salones de los equipos de forma remota con un archivo de configuración XML</span><span class="sxs-lookup"><span data-stu-id="64c79-156">Manage a Microsoft Teams Rooms console settings remotely with an XML configuration file</span></span>](xml-config-file.md)
