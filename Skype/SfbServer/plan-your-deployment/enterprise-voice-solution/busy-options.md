---
title: Plan para Opciones de disponibilidad para Skype Empresarial Server
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 5f85c6bc-a962-4283-971c-4380d83b3a66
description: Lea acerca de la característica de opciones de disponibilidad de Skype para Business Server.
ms.openlocfilehash: 42e970defa9535a8ae51ec52b0f9033009e58258
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2018
ms.locfileid: "20974119"
---
# <a name="plan-for-busy-options-for-skype-for-business-server"></a><span data-ttu-id="cbe0e-103">Plan para Opciones de disponibilidad para Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="cbe0e-103">Plan for Busy Options for Skype for Business Server</span></span>
 
<span data-ttu-id="cbe0e-104">Lea acerca de la característica de opciones de disponibilidad de Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="cbe0e-104">Read about the Busy Options feature in Skype for Business Server.</span></span>
  
<span data-ttu-id="cbe0e-105">Opciones de disponibilidad es una nueva directiva de voz introducida en la actualización acumulativa de julio de 2016 que permite configurar el tratamiento dado a las llamadas entrantes cuando un usuario ya está al teléfono o en una conferencia, o tiene una llamada en espera.</span><span class="sxs-lookup"><span data-stu-id="cbe0e-105">Busy Options is a new voice policy introduced in the July 2016 Cumulative Update that allows you to configure how incoming calls are handled when a user is already in a call or conference, or has a call placed on hold.</span></span> <span data-ttu-id="cbe0e-106">Las llamadas nuevas o entrantes pueden rechazarse con una señal de línea ocupada o desviarse al correo de voz.</span><span class="sxs-lookup"><span data-stu-id="cbe0e-106">New or incoming calls can be rejected with a busy signal or forwarded to voice mail.</span></span> 
  
<span data-ttu-id="cbe0e-107">La directiva de opciones de disponibilidad se admite para la recuperación ante desastres y la conmutación por error en grupos de servidores front-end emparejados y servidores de sucursal con funciones de supervivencia (SBS).</span><span class="sxs-lookup"><span data-stu-id="cbe0e-107">The Busy Options policy is supported for failover and disaster recovery on paired Front End Pools and Survivable Branch Servers (SBS).</span></span>
  
<span data-ttu-id="cbe0e-108">En este tema se describen las características de Opciones de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="cbe0e-108">This topic describes the features of Busy Options.</span></span> <span data-ttu-id="cbe0e-109">Para obtener información acerca de cómo instalar y configurar las opciones de disponibilidad, vea [instalar y configurar las opciones de disponibilidad de Skype para Business Server](../../deploy/deploy-enterprise-voice/install-and-configure-busy-options.md).</span><span class="sxs-lookup"><span data-stu-id="cbe0e-109">For information about how to install and configure Busy Options, see [Install and configure Busy Options for Skype for Business Server](../../deploy/deploy-enterprise-voice/install-and-configure-busy-options.md).</span></span>
  
## <a name="configuration-options"></a><span data-ttu-id="cbe0e-110">Opciones de configuración</span><span class="sxs-lookup"><span data-stu-id="cbe0e-110">Configuration options</span></span>

<span data-ttu-id="cbe0e-111">Si Opciones de disponibilidad está habilitada para la organización, todos los usuarios que formen parte de esta, tanto los que usen la telefonía IP empresarial como los que no la usen, pueden utilizar las siguientes características:</span><span class="sxs-lookup"><span data-stu-id="cbe0e-111">If Busy Options is enabled for the organization, all users in your organization, both Enterprise Voice and non-Enterprise Voice users, can use the following features:</span></span>
  
- <span data-ttu-id="cbe0e-112">Ocupado cuando ocupado: en la cual se rechazan las llamadas entrantes nuevas con una señal de línea ocupada si el usuario está ocupado.</span><span class="sxs-lookup"><span data-stu-id="cbe0e-112">Busy on Busy - In which new incoming calls will be rejected with a busy signal if the user is busy.</span></span>
    
- <span data-ttu-id="cbe0e-113">Correo de voz cuando ocupado: en la cual se desvían al correo de voz las llamadas entrantes nuevas si el usuario está ocupado.</span><span class="sxs-lookup"><span data-stu-id="cbe0e-113">Voicemail on Busy - In which new incoming calls will be forwarded to voice mail if the user is busy.</span></span>
    
<span data-ttu-id="cbe0e-114">La característica Opciones de disponibilidad ofrece una capacidad de conmutación por error.</span><span class="sxs-lookup"><span data-stu-id="cbe0e-114">The Busy Options feature provides failover capability.</span></span> <span data-ttu-id="cbe0e-115">Si se produce un problema y los usuarios conmuten por error a otro servidor Front-End o a otro grupo de servidores en Skype para Business Server, se conservarán su configuración de opciones de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="cbe0e-115">If a problem occurs and users fail over to another Front End Server or to another pool in Skype for Business Server, their Busy Options settings will be preserved.</span></span>
  
<span data-ttu-id="cbe0e-116">Independientemente de cómo esté configurada Opciones de disponibilidad, los usuarios que estén al teléfono o en una conferencia, o bien aquellos que tengan una llamada en espera, podrán iniciar nuevas llamadas o conferencias.  </span><span class="sxs-lookup"><span data-stu-id="cbe0e-116">Regardless of how their busy options are configured, users in a call or conference, or those with a call on hold, are not prevented from initiating new calls or conferences.</span></span> 
  
<span data-ttu-id="cbe0e-117">Después de la configuración, la configuración de opciones de disponibilidad es en vigor para Skype todos los del usuario para clientes y dispositivos de llamada de negocio.</span><span class="sxs-lookup"><span data-stu-id="cbe0e-117">After configuration, the Busy Options setting is in effect for all the user's Skype for Business call devices and clients.</span></span> <span data-ttu-id="cbe0e-118">En función de la configuración de Opciones de disponibilidad del usuario, la llamada que se rechace o se envíe al correo de voz no sonará en ninguno de los dispositivos de llamada del usuario (entre ellos, Macintosh, el escritorio de Windows, clientes móviles o teléfonos IP) en los que el usuario haya iniciado sesión.</span><span class="sxs-lookup"><span data-stu-id="cbe0e-118">Based on the user's Busy Options settings, the call that is rejected or sent to voice mail would not ring on any of the user's call devices--including Macintosh, Windows Desktop, mobile clients, or IP phones--on which the user is signed in.</span></span> 
  
<span data-ttu-id="cbe0e-119">Los usuarios verán las notificaciones de llamadas perdidas en su Skype para clientes empresariales y dispositivos, y se les notifique por correo electrónico también.</span><span class="sxs-lookup"><span data-stu-id="cbe0e-119">Users will see missed-call notifications on their Skype for Business clients and devices, and they will be notified by email as well.</span></span> <span data-ttu-id="cbe0e-120">A quienes se les haya rechazado una llamada por Ocupado cuando ocupado verán una notificación en el cliente de Skype Empresarial que indicará que el usuario al que intentaron contactar está ocupado en otra llamada.</span><span class="sxs-lookup"><span data-stu-id="cbe0e-120">Callers whose call was rejected due to Busy on Busy will see a notification in their Skype for Business client stating that the user they attempted to reach is busy on another call.</span></span>
  
<span data-ttu-id="cbe0e-121">Puede configurar la característica de opciones ocupado mediante Skype para cmdlets de PowerShell de negocio para:</span><span class="sxs-lookup"><span data-stu-id="cbe0e-121">You can configure the Busy Options feature by using Skype for Business PowerShell cmdlets to:</span></span>
  
- <span data-ttu-id="cbe0e-122">Habilitar o deshabilitar la directiva de voz de Opciones de disponibilidad para la empresa.</span><span class="sxs-lookup"><span data-stu-id="cbe0e-122">Enable or disable Busy Options Voice policy for the Enterprise.</span></span>
    
- <span data-ttu-id="cbe0e-123">Administrar Ocupado cuando ocupado o Correo de voz cuando ocupado para todos los usuarios de la empresa.</span><span class="sxs-lookup"><span data-stu-id="cbe0e-123">Administer Busy on Busy or Voicemail on Busy for all the users in the Enterprise.</span></span>
    
- <span data-ttu-id="cbe0e-124">Administrar Ocupado cuando ocupado o Correo de voz cuando ocupado para todos los usuarios alojados en un grupo de servidores front-end particular.</span><span class="sxs-lookup"><span data-stu-id="cbe0e-124">Administer Busy on Busy or Voicemail on Busy for all the users homed in a particular Front End pool.</span></span>
    
- <span data-ttu-id="cbe0e-125">Administrar Ocupado cuando ocupado o Correo de voz cuando ocupado para una lista de usuarios.</span><span class="sxs-lookup"><span data-stu-id="cbe0e-125">Administer Busy on Busy or Voicemail on Busy for a list of users.</span></span>
    
- <span data-ttu-id="cbe0e-126">Administrar Ocupado cuando ocupado o Correo de voz cuando ocupado para un solo usuario.</span><span class="sxs-lookup"><span data-stu-id="cbe0e-126">Administer Busy on Busy or Voicemail on Busy for a single user.</span></span>
    
## <a name="interoperability-with-voice-applications"></a><span data-ttu-id="cbe0e-127">Interoperabilidad con aplicaciones de voz</span><span class="sxs-lookup"><span data-stu-id="cbe0e-127">Interoperability with Voice applications</span></span>

<span data-ttu-id="cbe0e-128">Opciones de disponibilidad proporciona interoperabilidad con las siguientes aplicaciones de voz de Skype para la empresa:</span><span class="sxs-lookup"><span data-stu-id="cbe0e-128">Busy Options provides interoperability with the following Voice applications in Skype for Business:</span></span>
  
- <span data-ttu-id="cbe0e-129">Grupos de respuesta (RGS)</span><span class="sxs-lookup"><span data-stu-id="cbe0e-129">Response Groups (RGS)</span></span>
    
  - <span data-ttu-id="cbe0e-130">El sistema omitirá los parámetros de configuración de Opciones de disponibilidad establecidos en los números de grupos de respuesta. Se permitirán varias llamadas simultáneas. </span><span class="sxs-lookup"><span data-stu-id="cbe0e-130">Busy Options set on Response Group numbers will be ignored by the system; multiple concurrent calls will be allowed.</span></span> 
    
  - <span data-ttu-id="cbe0e-131">La experiencia de enrutamiento del operador actual en los grupos de respuesta no cambiará para los agentes con la configuración de Opciones de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="cbe0e-131">The current Attendant routing experience in Response Groups will remain unchanged for the Agents with Busy Options settings.</span></span>
    
  - <span data-ttu-id="cbe0e-132">Las llamadas que provengan de grupos de respuesta a los usuarios que sean agentes de grupos de respuesta no se verán limitadas por la configuración de Opciones de disponibilidad y se mantendrá la experiencia de RGS actual.</span><span class="sxs-lookup"><span data-stu-id="cbe0e-132">The calls coming from Response Groups to the users who are Response Groups Agents will not be throttled by Busy Options settings and the current RGS experience will be maintained.</span></span>
    
  - <span data-ttu-id="cbe0e-133">La configuración de Opciones de disponibilidad respetará las llamadas no relacionadas con RGS realizadas a los agentes.</span><span class="sxs-lookup"><span data-stu-id="cbe0e-133">The non-RGS related calls to the Agents will be honored by their Busy Options settings.</span></span>
    
- <span data-ttu-id="cbe0e-134">Llamada de equipo</span><span class="sxs-lookup"><span data-stu-id="cbe0e-134">Team Call</span></span>
    
  - <span data-ttu-id="cbe0e-135">Las llamadas entrantes a los usuarios que se han configurado para una llamada de equipo le dará prioridad para omitir no disponible en no disponible y correo de voz en la configuración de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="cbe0e-135">Incoming calls to users who are set up for a Team Call will be prioritized to ignore Busy on Busy and Voicemail on Busy settings.</span></span>
    
  - <span data-ttu-id="cbe0e-136">La experiencia actual de llamada de equipo no sufrirá cambios con los parámetros de configuración de Opciones de disponibilidad que se establezcan para los usuarios.</span><span class="sxs-lookup"><span data-stu-id="cbe0e-136">The current Team Call experience will remain unchanged with Busy Options set for the users.</span></span>
    
  - <span data-ttu-id="cbe0e-137">La configuración de Opciones de disponibilidad respetará las llamadas que no estén relacionadas con las llamadas de equipo a tales usuarios.</span><span class="sxs-lookup"><span data-stu-id="cbe0e-137">The non-Team Call related calls to such users will be honored by their Busy Options settings.</span></span>
    
- <span data-ttu-id="cbe0e-138">Delegación Jefe/Administrador </span><span class="sxs-lookup"><span data-stu-id="cbe0e-138">Boss/Admin Delegation</span></span> 
    
  - <span data-ttu-id="cbe0e-139">Las llamadas entrantes a los usuarios que estén configurados para la delegación de directores/Admin ya sea como jefe o un administrador le dará prioridad para omitir no disponible en no disponible y correo de voz en la configuración de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="cbe0e-139">Incoming calls to users who are set up for a Boss/Admin Delegation either as Boss or an Admin will be prioritized to ignore Busy on Busy and Voicemail on Busy settings.</span></span>
    
  - <span data-ttu-id="cbe0e-140">La experiencia actual de delegación de Jefe/Administrador no sufrirá cambios con los parámetros de configuración de Opciones de disponibilidad que se establezcan para los administradores o jefes.</span><span class="sxs-lookup"><span data-stu-id="cbe0e-140">The current Boss/Admin Delegation experience will remain unchanged with Busy Options set for the Admins or Boss.</span></span>
    
  - <span data-ttu-id="cbe0e-141">La configuración de Opciones de disponibilidad respetará las llamadas que no estén relacionadas con la delegación de Jefe/Administrador a los administradores.</span><span class="sxs-lookup"><span data-stu-id="cbe0e-141">The non-Boss/Admin Delegation related calls to Admins will be honored by their Busy Options settings.</span></span>
    
- <span data-ttu-id="cbe0e-142">Apariencia de línea compartida   </span><span class="sxs-lookup"><span data-stu-id="cbe0e-142">Shared Line Appearance</span></span> 
    
  - <span data-ttu-id="cbe0e-143">Se omitirá la configuración de Opciones de disponibilidad en las cuentas de usuario configuradas para la apariencia de línea compartida. </span><span class="sxs-lookup"><span data-stu-id="cbe0e-143">Busy Options settings on user accounts set up for Shared Line Appearance will be ignored.</span></span> 
    
  - <span data-ttu-id="cbe0e-144">Ocupado nativo de la apariencia de línea compartida en no disponible y correo de voz en las opciones de disponibilidad tendrá en cuenta en su lugar.</span><span class="sxs-lookup"><span data-stu-id="cbe0e-144">Shared Line Appearance's native Busy on Busy and Voicemail on Busy options will be honored instead.</span></span>
    
- <span data-ttu-id="cbe0e-145">Servicio de estacionamiento de llamadas </span><span class="sxs-lookup"><span data-stu-id="cbe0e-145">Call Parking Service</span></span> 
    
  - <span data-ttu-id="cbe0e-146">Las llamadas estacionadas que no se han recuperado y que estén sonando nuevamente debido al agotamiento del tiempo de espera podrán sonar en los dispositivos del usuario que las estacionó a través de Opciones de disponibilidad. </span><span class="sxs-lookup"><span data-stu-id="cbe0e-146">Parked calls that were not retrieved and are ringing back due to timing out will be allowed to ring though to the user who parked the call by the Busy Options.</span></span> 
    
- <span data-ttu-id="cbe0e-147">Conferencia de llamadas</span><span class="sxs-lookup"><span data-stu-id="cbe0e-147">Call Conferencing</span></span>
    
  - <span data-ttu-id="cbe0e-148">Se considera que los usuarios que estén en llamadas de conferencia están ocupados, y se rechazarán todas las llamadas entrantes nuevas con una señal de línea ocupada o un envío al correo de voz de acuerdo con la configuración de Opciones de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="cbe0e-148">Users in conference calls are considered Busy and new incoming calls will be rejected with a busy signal or forwarded to voice mail according to their Busy Options settings.</span></span>
    
  - <span data-ttu-id="cbe0e-149">Opciones de disponibilidad no impide que los usuarios en conferencia inicien llamadas ni conferencias nuevas.</span><span class="sxs-lookup"><span data-stu-id="cbe0e-149">Users in conferences are not prevented from initiating new calls or conferences by Busy Options.</span></span>
    
  - <span data-ttu-id="cbe0e-150">Los usuarios en conferencia todavía pueden recibir invitaciones a conferencias nuevas, pero se rechazarán las llamadas de par a par nuevas de acuerdo con la configuración de Opciones de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="cbe0e-150">Users in conferences are still able to receive new conference invitations, but new peer-to-peer calls will be rejected according to their Busy Options settings.</span></span>
    
- <span data-ttu-id="cbe0e-151">Desvío de llamadas y llamadas simultáneas</span><span class="sxs-lookup"><span data-stu-id="cbe0e-151">Simultaneous Ring and Call Forwarding</span></span>
    
    <span data-ttu-id="cbe0e-152">La característica Ocupado cuando ocupado no se ha diseñado para funcionar con desvío de llamadas y llamadas simultáneas.</span><span class="sxs-lookup"><span data-stu-id="cbe0e-152">The Busy on Busy feature is not designed to work with Simultaneous Ring and Call Forwarding.</span></span>
    

