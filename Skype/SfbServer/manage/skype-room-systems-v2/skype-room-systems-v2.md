---
title: Introducción a la administración de sistemas de salón de Skype v2
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
description: Introducción a la administración de sistemas de salón de Skype v2.
ms.openlocfilehash: edd73c6ecf973d0d066b5f46d949a792bc0910c5
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30880288"
---
# <a name="management-overview"></a><span data-ttu-id="29de2-103">Introducción a la administración</span><span class="sxs-lookup"><span data-stu-id="29de2-103">Management overview</span></span> 

<span data-ttu-id="29de2-104">Es esencial que desarrollar y ejecutar el mantenimiento continuado y operaciones para asegurarse de que los sistemas de v2 de Skype salón sistemas están disponibles para los usuarios y ofrecen a un usuario excelente experimentan.</span><span class="sxs-lookup"><span data-stu-id="29de2-104">It’s essential that you develop and execute ongoing maintenance and operations to ensure that your Skype Room Systems v2 systems are available for your users and deliver a great user experience.</span></span> 

## <a name="monitoring"></a><span data-ttu-id="29de2-105">Supervisión</span><span class="sxs-lookup"><span data-stu-id="29de2-105">Monitoring</span></span> 

<span data-ttu-id="29de2-106">Sistemas de salón de Skype v2 sistemas de supervisión consta de dos actividades clave:</span><span class="sxs-lookup"><span data-stu-id="29de2-106">Monitoring Skype Room Systems v2 systems consists of two key activities:</span></span>

-  <span data-ttu-id="29de2-107">Dispositivo, la aplicación y la supervisión de dispositivos periféricos</span><span class="sxs-lookup"><span data-stu-id="29de2-107">Device, application, and peripheral device monitoring</span></span>

-  <span data-ttu-id="29de2-108">Calidad y confiabilidad de supervisión (CQD)</span><span class="sxs-lookup"><span data-stu-id="29de2-108">Quality and reliability monitoring (CQD)</span></span>

### <a name="skype-room-systems-v2-device-application-and-peripheral-device-monitoring"></a><span data-ttu-id="29de2-109">Dispositivo v2 de Skype salón sistemas, aplicaciones y supervisión de dispositivos periféricos</span><span class="sxs-lookup"><span data-stu-id="29de2-109">Skype Room Systems v2 device, application, and peripheral device monitoring</span></span>

<span data-ttu-id="29de2-110">Para asegurarse de que los usuarios podrán utilizar las unidades de sistemas de salón de Skype v2, las unidades deben estar en, conectado a la red con la aplicación de v2 de sistemas de salón de Skype configurada correctamente y estar conectadas a dispositivos periféricos funcionamiento.</span><span class="sxs-lookup"><span data-stu-id="29de2-110">To ensure that users are able to use the Skype Room Systems v2 units, the units must be on, connected to the network with the Skype Room Systems v2 application correctly configured, and be connected to functioning peripheral devices.</span></span> 


<span data-ttu-id="29de2-111">Información sobre el estado de la aplicación de v2 de Skype salón sistemas y dispositivos periféricos conectados es escrita por la aplicación de v2 de sistemas de salón de Skype para el registro de eventos de Windows y que se documentaron en [comprender las entradas del registro](azure-monitor.md#understand-the-log-entries).</span><span class="sxs-lookup"><span data-stu-id="29de2-111">Information about the state of the Skype Room Systems v2 application and connected peripheral devices is written by the Skype Room Systems v2 application to the Windows event log and documented in [Understand the log entries](azure-monitor.md#understand-the-log-entries).</span></span> 

|<span data-ttu-id="29de2-112">**Configuración**</span><span class="sxs-lookup"><span data-stu-id="29de2-112">**Setting**</span></span>|<span data-ttu-id="29de2-113">**Permite**</span><span class="sxs-lookup"><span data-stu-id="29de2-113">**Allows**</span></span>|
|:-----|:-----|
|<span data-ttu-id="29de2-114">HKLM\Software\Microsoft\Windows NT\CurrentVersion\Winlogon AutoAdminLogon = (dword) 1</span><span class="sxs-lookup"><span data-stu-id="29de2-114">HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon AutoAdminLogon = (dword) 1</span></span>  <br/> |<span data-ttu-id="29de2-115">Permite v2 de sistemas de salón de Skype iniciar copia de seguridad</span><span class="sxs-lookup"><span data-stu-id="29de2-115">Enables Skype Room Systems v2 to boot up</span></span>  <br/> |
|<span data-ttu-id="29de2-116">Administración de energía -\> en AC, desactivar pantalla después de 10 minutos</span><span class="sxs-lookup"><span data-stu-id="29de2-116">Power Management -\> On AC, turn screen off after 10 minutes</span></span>  <br/> <span data-ttu-id="29de2-117">Administración de energía -\> en AC, nunca colocar del sistema al modo de suspensión</span><span class="sxs-lookup"><span data-stu-id="29de2-117">Power Management -\> On AC, never put system to sleep</span></span>  <br/> |<span data-ttu-id="29de2-118">Permite v2 de sistemas de salón de Skype para desactivar muestra adjunto y reactivar automáticamente</span><span class="sxs-lookup"><span data-stu-id="29de2-118">Enables Skype Room Systems v2 to turn off attached displays and wake up automatically</span></span>  <br/> |
|<span data-ttu-id="29de2-119">net accounts /maxpwage:unlimited</span><span class="sxs-lookup"><span data-stu-id="29de2-119">net accounts /maxpwage:unlimited</span></span>  <br/> <span data-ttu-id="29de2-120">O medios alternativos para deshabilitar la opción de caducidad de la contraseña en la cuenta local.</span><span class="sxs-lookup"><span data-stu-id="29de2-120">Or equivalent means of disabling password expiration on the local account.</span></span> <span data-ttu-id="29de2-121">Si esto no se realiza, la cuenta de Skype no podrá iniciar sesión indicando que la contraseña ha caducado.</span><span class="sxs-lookup"><span data-stu-id="29de2-121">Failure to do this will eventually cause the Skype account to fail logon complaining about an expired password.</span></span> <span data-ttu-id="29de2-122">Tenga en cuenta que esto afectará todas las cuentas locales de la máquina y, por consiguiente, si no se configura esto, la cuenta administrativa del cuadro eventualmente también caducará.</span><span class="sxs-lookup"><span data-stu-id="29de2-122">Note that this impacts all local accounts on the machine, and thus failure to set this will also cause the administrative account on the box to eventually expire as well.</span></span>  <br/> |<span data-ttu-id="29de2-123">Permite que la cuenta de Skype siempre inicie sesión</span><span class="sxs-lookup"><span data-stu-id="29de2-123">Enables Skype account to always log in</span></span>  <br/> |
   
<span data-ttu-id="29de2-124">Transferencia de archivos mediante directivas de grupo se describe en [configurar un elemento de archivo](https://technet.microsoft.com/en-us/library/cc772536%28v=ws.11%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="29de2-124">Transferring files using Group Policies is discussed in [Configure a File Item](https://technet.microsoft.com/en-us/library/cc772536%28v=ws.11%29.aspx).</span></span>
  
## <a name="remote-management-using-powershell"></a><span data-ttu-id="29de2-125">Administración remota con PowerShell</span><span class="sxs-lookup"><span data-stu-id="29de2-125">Remote Management using PowerShell</span></span>
<span data-ttu-id="29de2-126"><a name="RemotePS"> </a></span><span class="sxs-lookup"><span data-stu-id="29de2-126"></span></span>


<span data-ttu-id="29de2-127">Se recomienda que utilice el conjunto de aplicaciones de Microsoft Operations Manager para supervisar los sistemas de v2 de sistemas de salón de Skype.</span><span class="sxs-lookup"><span data-stu-id="29de2-127">We recommend that you use Microsoft Operations Manager Suite to monitor your Skype Room Systems v2 systems.</span></span> <span data-ttu-id="29de2-128">Para obtener instrucciones acerca de cómo configurar la supervisión y alertas básicas, vea [administración de v2 de implementar sistemas de salón de Skype con el Monitor de Azure](../../deploy/deploy-clients/azure-monitor.md).</span><span class="sxs-lookup"><span data-stu-id="29de2-128">For guidance on how to set up monitoring and basic alerting, see [Deploy Skype Room Systems v2 management with Azure Monitor](../../deploy/deploy-clients/azure-monitor.md).</span></span> 

<span data-ttu-id="29de2-129">Uso de esta guía, puede crear un panel simple de usar para identificar los problemas con las unidades de v2 de sistemas de salón de Skype en toda la implementación.</span><span class="sxs-lookup"><span data-stu-id="29de2-129">Using this guidance, you can create a simple-to-use dashboard to identify any issues with your Skype Room Systems v2 units across your deployment.</span></span> 

|    |     |
|-----------|------------|
|![](../../media/audio_conferencing_image7.png) <br/><span data-ttu-id="29de2-130">Puntos de decisión</span><span class="sxs-lookup"><span data-stu-id="29de2-130">Decision points</span></span>|<ul><li><span data-ttu-id="29de2-131">Confirme que usará el conjunto de aplicaciones de las operaciones de administración para supervisar la implementación de sistemas de salón de Skype v2.</span><span class="sxs-lookup"><span data-stu-id="29de2-131">Confirm that you'll use Operations Management Suite to monitor your Skype Room Systems v2 deployment.</span></span></li><li><span data-ttu-id="29de2-132">Decidir que va a utilizar para alertas de correo electrónico de la lista de distribución de destino.</span><span class="sxs-lookup"><span data-stu-id="29de2-132">Decide the target distribution list you’ll use for email alerts.</span></span></li></ul>|
|![](../../media/audio_conferencing_image9.png)<br/><span data-ttu-id="29de2-133">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="29de2-133">Next steps</span></span>|<ul><li><span data-ttu-id="29de2-134">Definir la calidad y el enfoque de supervisión de la confiabilidad.</span><span class="sxs-lookup"><span data-stu-id="29de2-134">Define your quality and reliability monitoring approach.</span></span></li></ul>|

## <a name="quality-and-reliability-monitoring-cqd"></a><span data-ttu-id="29de2-135">Calidad y confiabilidad de supervisión (CQD)</span><span class="sxs-lookup"><span data-stu-id="29de2-135">Quality and reliability monitoring (CQD)</span></span>

<span data-ttu-id="29de2-136">Se recomienda que implemente calidad operativa continuada y confiabilidad procedimientos de supervisión como parte de su implementación para supervisar las tendencias de llamada y la calidad de la reunión y la confiabilidad, que identifica las áreas de preocupación y trabajar hacia una resolución.</span><span class="sxs-lookup"><span data-stu-id="29de2-136">We recommend that you implement ongoing operational quality and reliability monitoring procedures as part of your deployment to monitor the trending of call and meeting quality and reliability, identifying any areas of concern and working toward a resolution.</span></span> 

<span data-ttu-id="29de2-137">Cuando se carga la información de creación en CQD puede investigar las tendencias de calidad y la confiabilidad de llamadas en un nivel por edificio, lo que facilita la comparación de los edificios y centra la atención en problemas específicos.</span><span class="sxs-lookup"><span data-stu-id="29de2-137">When you upload your building information to CQD you can investigate call quality and reliability trends on a per-building level, which makes it easy to compare buildings and focus your attention on specific problems.</span></span> <span data-ttu-id="29de2-138">Para obtener más información, descargue el [Monitor-CQD de Skype para entrega en línea de negocio y la Guía de operaciones](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=6_2_0_15).</span><span class="sxs-lookup"><span data-stu-id="29de2-138">For more information, download the [Monitor-CQD for Skype for Business Online-Delivery and Operations Guide](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=6_2_0_15).</span></span> 

<span data-ttu-id="29de2-139">Se recomienda que revise y siga la [Guía de revisión de calidad de experiencia](https://aka.ms/qerguide) para identificar las tendencias de calidad y la confiabilidad y crear un plan de acción para resolverlos conflictos.</span><span class="sxs-lookup"><span data-stu-id="29de2-139">We recommend that you review and follow the [Quality of Experience Review Guide](https://aka.ms/qerguide) to identify quality and reliability trends, and create an action plan to resolve them.</span></span> 

## <a name="updating-the-skype-room-systems-v2-os-and-skype-room-systems-application"></a><span data-ttu-id="29de2-140">Actualización de la aplicación de sistema operativo y sistemas de salón de Skype de v2 sistemas de salón de Skype</span><span class="sxs-lookup"><span data-stu-id="29de2-140">Updating the Skype Room Systems v2 OS and Skype Room Systems application</span></span> 

<span data-ttu-id="29de2-141">Se recomienda que actualizar para sacar partido de las actualizaciones del producto y mejoras en la aplicación v2 de sistemas de salón de Skype v2 OS y sistemas de salón de Skype.</span><span class="sxs-lookup"><span data-stu-id="29de2-141">We recommend that you update the Skype Room Systems v2 OS and Skype Room Systems v2 application to benefit from product updates and improvements.</span></span> <span data-ttu-id="29de2-142">Para obtener instrucciones detalladas, consulte [v2 de administración de sistemas de salón de Skype](room-systems-v2-operations.md#software-updates).</span><span class="sxs-lookup"><span data-stu-id="29de2-142">For detailed guidance, see [Manage Skype Room Systems v2](room-systems-v2-operations.md#software-updates).</span></span> 

## <a name="windows-updates"></a><span data-ttu-id="29de2-143">Actualizaciones de Windows</span><span class="sxs-lookup"><span data-stu-id="29de2-143">Windows Updates</span></span>

<span data-ttu-id="29de2-144">Sistema de salas de Skype v2 (SRS v2) se ejecuta en Windows 10 Enterprise IoT o Windows 10 Enterprise (VL) y recibe las compilaciones de actualizaciones de Windows y el sistema operativo mismas como un escritorio estándar.</span><span class="sxs-lookup"><span data-stu-id="29de2-144">Skype Room System v2 (SRS v2) runs on Windows 10 Enterprise IoT or Windows 10 Enterprise (VL) and receives the same Windows Updates and OS builds as a standard desktop.</span></span> <span data-ttu-id="29de2-145">Para obtener información detallada, vea [Administrar actualizaciones de Windows](updates.md) .</span><span class="sxs-lookup"><span data-stu-id="29de2-145">See [Manage Windows Updates](updates.md) for details.</span></span>


## <a name="troubleshooting"></a><span data-ttu-id="29de2-146">Solución de problemas</span><span class="sxs-lookup"><span data-stu-id="29de2-146">Troubleshooting</span></span>

<span data-ttu-id="29de2-147">Se recomienda que configure alertas del conjunto de aplicaciones de administración de operaciones tal como se describe en la sección anterior para que su equipo de operaciones y el departamento de soporte técnico le avisará de que cualquier problema de v2 de sistemas de salón de Skype.</span><span class="sxs-lookup"><span data-stu-id="29de2-147">We recommend that you set up Operations Management Suite alerting as described in the section above so that your operations team and helpdesk will be alerted to any Skype Room Systems v2 issues.</span></span> <span data-ttu-id="29de2-148">Se describen las opciones disponibles para la administración remota de PowerShell en [PowerShell de uso de administración remota](room-systems-v2-operations.md#remote-management-using-powershell).</span><span class="sxs-lookup"><span data-stu-id="29de2-148">The options you have for PowerShell remote management are described in [Remote Management using PowerShell](room-systems-v2-operations.md#remote-management-using-powershell).</span></span> <span data-ttu-id="29de2-149">En caso de que se desconecta un dispositivo periférico, es posible que necesite se basan en locales "inteligentes manos" o soporte de TI para investigar y volver a conectar los dispositivos.</span><span class="sxs-lookup"><span data-stu-id="29de2-149">In the event that a peripheral device is disconnected, you might need to rely on local “smart hands” or IT support to investigate and reconnect the devices.</span></span> 

<span data-ttu-id="29de2-150">Para obtener más información sobre el modo de administración y solución de problemas, vea [administrar sistemas de salón de Skype v2](room-systems-v2-operations.md#admin-mode-and-device-management).</span><span class="sxs-lookup"><span data-stu-id="29de2-150">For more information about troubleshooting and admin mode, see [Manage Skype Room Systems v2](room-systems-v2-operations.md#admin-mode-and-device-management).</span></span> 


## <a name="see-also"></a><span data-ttu-id="29de2-151">Consulte también</span><span class="sxs-lookup"><span data-stu-id="29de2-151">See also</span></span>

[<span data-ttu-id="29de2-152">Ayuda de la versión 2 de sistemas de salón de Skype</span><span class="sxs-lookup"><span data-stu-id="29de2-152">Skype Room Systems version 2 help</span></span>](https://support.office.com/en-us/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[<span data-ttu-id="29de2-153">Plan for Skype Room Systems v2</span><span class="sxs-lookup"><span data-stu-id="29de2-153">Plan for Skype Room Systems v2</span></span>](../../plan-your-deployment/clients-and-devices/skype-room-systems-v2-0.md)

[<span data-ttu-id="29de2-154">Implementar Sistemas de salas de Skype v2</span><span class="sxs-lookup"><span data-stu-id="29de2-154">Deploy Skype Room Systems v2</span></span>](../../deploy/deploy-clients/room-systems-v2.md)

[<span data-ttu-id="29de2-155">Configurar una consola de Sistemas de salas de Skype v2</span><span class="sxs-lookup"><span data-stu-id="29de2-155">Configure a Skype Room Systems v2 console</span></span>](../../deploy/deploy-clients/console.md)

[<span data-ttu-id="29de2-156">Administrar la configuración de una consola de Sistemas de salas de Skype v2 de forma remota con un archivo XML de configuración</span><span class="sxs-lookup"><span data-stu-id="29de2-156">Manage a Skype Room Systems v2 console settings remotely with an XML configuration file</span></span>](xml-config-file.md)
