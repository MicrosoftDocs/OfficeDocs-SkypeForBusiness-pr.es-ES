---
title: Plan for Busy Options for Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 5f85c6bc-a962-4283-971c-4380d83b3a66
description: Lea acerca de la característica Opciones de disponibilidad en Skype Empresarial Server.
ms.openlocfilehash: 558d7486ca7aaa794c3114f5c210702a54e02fc4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813700"
---
# <a name="plan-for-busy-options-for-skype-for-business-server"></a><span data-ttu-id="b083f-103">Plan for Busy Options for Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="b083f-103">Plan for Busy Options for Skype for Business Server</span></span>
 
<span data-ttu-id="b083f-104">Lea acerca de la característica Opciones de disponibilidad en Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="b083f-104">Read about the Busy Options feature in Skype for Business Server.</span></span>
  
<span data-ttu-id="b083f-105">Opciones de disponibilidad es una nueva directiva de voz introducida en la actualización acumulativa de julio de 2016 que le permite configurar cómo se administran las llamadas entrantes cuando un usuario ya está en una llamada o conferencia, o tiene una llamada en espera.</span><span class="sxs-lookup"><span data-stu-id="b083f-105">Busy Options is a new voice policy introduced in the July 2016 Cumulative Update that allows you to configure how incoming calls are handled when a user is already in a call or conference, or has a call placed on hold.</span></span> <span data-ttu-id="b083f-106">Las llamadas nuevas o entrantes se pueden rechazar con una señal de disponibilidad o reenviarse al correo de voz.</span><span class="sxs-lookup"><span data-stu-id="b083f-106">New or incoming calls can be rejected with a busy signal or forwarded to voice mail.</span></span> 
  
<span data-ttu-id="b083f-107">La directiva Opciones de disponibilidad es compatible con la conmutación por error y la recuperación ante desastres en grupos de servidores front-end emparejados y servidores de sucursal con funciones de supervivencia (SBS).</span><span class="sxs-lookup"><span data-stu-id="b083f-107">The Busy Options policy is supported for failover and disaster recovery on paired Front End Pools and Survivable Branch Servers (SBS).</span></span>
  
<span data-ttu-id="b083f-108">En este tema se describen las características de Opciones de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="b083f-108">This topic describes the features of Busy Options.</span></span> <span data-ttu-id="b083f-109">Para obtener información sobre cómo instalar y configurar Opciones de disponibilidad, consulte Instalar y configurar opciones de disponibilidad [para Skype Empresarial Server.](../../deploy/deploy-enterprise-voice/install-and-configure-busy-options.md)</span><span class="sxs-lookup"><span data-stu-id="b083f-109">For information about how to install and configure Busy Options, see [Install and configure Busy Options for Skype for Business Server](../../deploy/deploy-enterprise-voice/install-and-configure-busy-options.md).</span></span>
  
## <a name="configuration-options"></a><span data-ttu-id="b083f-110">Opciones de configuración</span><span class="sxs-lookup"><span data-stu-id="b083f-110">Configuration options</span></span>

<span data-ttu-id="b083f-111">Si Opciones de disponibilidad está habilitada para la organización, todos los usuarios de la organización, tanto los Telefonía IP empresarial como los que no Telefonía IP empresarial, pueden usar las siguientes características:</span><span class="sxs-lookup"><span data-stu-id="b083f-111">If Busy Options is enabled for the organization, all users in your organization, both Enterprise Voice and non-Enterprise Voice users, can use the following features:</span></span>
  
- <span data-ttu-id="b083f-112">Ocupado en Ocupado: en el que se rechazarán las nuevas llamadas entrantes con una señal de ocupado si el usuario está ocupado.</span><span class="sxs-lookup"><span data-stu-id="b083f-112">Busy on Busy - In which new incoming calls will be rejected with a busy signal if the user is busy.</span></span>
    
- <span data-ttu-id="b083f-113">Correo de voz en Ocupado: en el que las nuevas llamadas entrantes se reenviarán al correo de voz si el usuario está ocupado.</span><span class="sxs-lookup"><span data-stu-id="b083f-113">Voicemail on Busy - In which new incoming calls will be forwarded to voice mail if the user is busy.</span></span>
    
<span data-ttu-id="b083f-114">La característica Opciones de disponibilidad proporciona capacidad de conmutación por error.</span><span class="sxs-lookup"><span data-stu-id="b083f-114">The Busy Options feature provides failover capability.</span></span> <span data-ttu-id="b083f-115">Si se produce un problema y los usuarios conmutan por error a otro servidor front-end o a otro grupo en Skype Empresarial Server, se conservará la configuración de Opciones de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="b083f-115">If a problem occurs and users fail over to another Front End Server or to another pool in Skype for Business Server, their Busy Options settings will be preserved.</span></span>
  
<span data-ttu-id="b083f-116">Independientemente de cómo se configuren sus opciones de disponibilidad, los usuarios de una llamada o conferencia, o aquellos con una llamada en espera, no se les impide iniciar nuevas llamadas o conferencias.</span><span class="sxs-lookup"><span data-stu-id="b083f-116">Regardless of how their busy options are configured, users in a call or conference, or those with a call on hold, are not prevented from initiating new calls or conferences.</span></span> 
  
<span data-ttu-id="b083f-117">Después de la configuración, la opción Opciones de disponibilidad está en vigor para todos los clientes y dispositivos de llamadas de Skype Empresarial del usuario.</span><span class="sxs-lookup"><span data-stu-id="b083f-117">After configuration, the Busy Options setting is in effect for all the user's Skype for Business call devices and clients.</span></span> <span data-ttu-id="b083f-118">Según la configuración de Opciones de disponibilidad del usuario, la llamada que se rechaza o se envía al correo de voz no sonará en ninguno de los dispositivos de llamada del usuario (incluidos Macintosh, Escritorio de Windows, clientes móviles o teléfonos IP) en los que el usuario haya iniciado sesión.</span><span class="sxs-lookup"><span data-stu-id="b083f-118">Based on the user's Busy Options settings, the call that is rejected or sent to voice mail would not ring on any of the user's call devices--including Macintosh, Windows Desktop, mobile clients, or IP phones--on which the user is signed in.</span></span> 
  
<span data-ttu-id="b083f-119">Los usuarios verán notificaciones de llamadas perdidas en sus dispositivos y clientes de Skype Empresarial, y también se les notificará por correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="b083f-119">Users will see missed-call notifications on their Skype for Business clients and devices, and they will be notified by email as well.</span></span> <span data-ttu-id="b083f-120">Los autores de llamadas cuya llamada se rechazó debido a Ocupado en ocupado verán una notificación en su cliente de Skype Empresarial que indica que el usuario con el que intentaron contactar está ocupado en otra llamada.</span><span class="sxs-lookup"><span data-stu-id="b083f-120">Callers whose call was rejected due to Busy on Busy will see a notification in their Skype for Business client stating that the user they attempted to reach is busy on another call.</span></span>
  
<span data-ttu-id="b083f-121">Puede configurar la característica Opciones de disponibilidad con los cmdlets de PowerShell de Skype Empresarial para:</span><span class="sxs-lookup"><span data-stu-id="b083f-121">You can configure the Busy Options feature by using Skype for Business PowerShell cmdlets to:</span></span>
  
- <span data-ttu-id="b083f-122">Habilitar o deshabilitar la directiva de voz de opciones de disponibilidad para enterprise.</span><span class="sxs-lookup"><span data-stu-id="b083f-122">Enable or disable Busy Options Voice policy for the Enterprise.</span></span>
    
- <span data-ttu-id="b083f-123">Administrar ocupado en ocupado o correo de voz en ocupado para todos los usuarios de la empresa.</span><span class="sxs-lookup"><span data-stu-id="b083f-123">Administer Busy on Busy or Voicemail on Busy for all the users in the Enterprise.</span></span>
    
- <span data-ttu-id="b083f-124">Administrar ocupado en ocupado o correo de voz en ocupado para todos los usuarios que se alojen en un grupo de servidores front-end determinado.</span><span class="sxs-lookup"><span data-stu-id="b083f-124">Administer Busy on Busy or Voicemail on Busy for all the users homed in a particular Front End pool.</span></span>
    
- <span data-ttu-id="b083f-125">Administrar ocupado en ocupado o correo de voz en ocupado para una lista de usuarios.</span><span class="sxs-lookup"><span data-stu-id="b083f-125">Administer Busy on Busy or Voicemail on Busy for a list of users.</span></span>
    
- <span data-ttu-id="b083f-126">Administrar ocupado en ocupado o correo de voz en ocupado para un solo usuario.</span><span class="sxs-lookup"><span data-stu-id="b083f-126">Administer Busy on Busy or Voicemail on Busy for a single user.</span></span>
    
## <a name="interoperability-with-voice-applications"></a><span data-ttu-id="b083f-127">Interoperabilidad con aplicaciones de voz</span><span class="sxs-lookup"><span data-stu-id="b083f-127">Interoperability with Voice applications</span></span>

<span data-ttu-id="b083f-128">Opciones de disponibilidad proporciona interoperabilidad con las siguientes aplicaciones de voz en Skype Empresarial:</span><span class="sxs-lookup"><span data-stu-id="b083f-128">Busy Options provides interoperability with the following Voice applications in Skype for Business:</span></span>
  
- <span data-ttu-id="b083f-129">Grupos de respuesta (RGS)</span><span class="sxs-lookup"><span data-stu-id="b083f-129">Response Groups (RGS)</span></span>
    
  - <span data-ttu-id="b083f-130">El sistema omitirá las opciones de disponibilidad establecidas en los números de grupo de respuesta; se permitirán varias llamadas simultáneas.</span><span class="sxs-lookup"><span data-stu-id="b083f-130">Busy Options set on Response Group numbers will be ignored by the system; multiple concurrent calls will be allowed.</span></span> 
    
  - <span data-ttu-id="b083f-131">La experiencia de enrutamiento del operador actual en grupos de respuesta no se modificará para la configuración de Agentes con Opciones de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="b083f-131">The current Attendant routing experience in Response Groups will remain unchanged for the Agents with Busy Options settings.</span></span>
    
  - <span data-ttu-id="b083f-132">Las llamadas procedentes de grupos de respuesta a los usuarios que son agentes de grupos de respuesta no se limitarán con la configuración de Opciones de disponibilidad y se mantendrá la experiencia actual de RGS.</span><span class="sxs-lookup"><span data-stu-id="b083f-132">The calls coming from Response Groups to the users who are Response Groups Agents will not be throttled by Busy Options settings and the current RGS experience will be maintained.</span></span>
    
  - <span data-ttu-id="b083f-133">La configuración de Opciones de disponibilidad respetará las llamadas no relacionadas con RGS a los agentes.</span><span class="sxs-lookup"><span data-stu-id="b083f-133">The non-RGS related calls to the Agents will be honored by their Busy Options settings.</span></span>
    
- <span data-ttu-id="b083f-134">Llamada de equipo</span><span class="sxs-lookup"><span data-stu-id="b083f-134">Team Call</span></span>
    
  - <span data-ttu-id="b083f-135">Se dará prioridad a las llamadas entrantes a los usuarios que están configurados para una llamada de equipo para omitir la configuración ocupado en ocupado y correo de voz en ocupado.</span><span class="sxs-lookup"><span data-stu-id="b083f-135">Incoming calls to users who are set up for a Team Call will be prioritized to ignore Busy on Busy and Voicemail on Busy settings.</span></span>
    
  - <span data-ttu-id="b083f-136">La experiencia actual de llamada de equipo no cambiará con opciones de disponibilidad establecidas para los usuarios.</span><span class="sxs-lookup"><span data-stu-id="b083f-136">The current Team Call experience will remain unchanged with Busy Options set for the users.</span></span>
    
  - <span data-ttu-id="b083f-137">La configuración de Opciones de disponibilidad respetará las llamadas que no sean relacionadas con llamadas de equipo a dichos usuarios.</span><span class="sxs-lookup"><span data-stu-id="b083f-137">The non-Team Call related calls to such users will be honored by their Busy Options settings.</span></span>
    
- <span data-ttu-id="b083f-138">Delegación jefe/administrador</span><span class="sxs-lookup"><span data-stu-id="b083f-138">Boss/Admin Delegation</span></span> 
    
  - <span data-ttu-id="b083f-139">Se dará prioridad a las llamadas entrantes a los usuarios configurados para una delegación de jefe o administrador como jefe o administrador para omitir ocupado en ocupado y correo de voz en la configuración de ocupado.</span><span class="sxs-lookup"><span data-stu-id="b083f-139">Incoming calls to users who are set up for a Boss/Admin Delegation either as Boss or an Admin will be prioritized to ignore Busy on Busy and Voicemail on Busy settings.</span></span>
    
  - <span data-ttu-id="b083f-140">La experiencia actual de delegación jefe/administrador no cambiará con opciones de disponibilidad establecidas para los administradores o jefes.</span><span class="sxs-lookup"><span data-stu-id="b083f-140">The current Boss/Admin Delegation experience will remain unchanged with Busy Options set for the Admins or Boss.</span></span>
    
  - <span data-ttu-id="b083f-141">La configuración de Opciones de disponibilidad respetará las llamadas a administradores que no sean jefes o administradores.</span><span class="sxs-lookup"><span data-stu-id="b083f-141">The non-Boss/Admin Delegation related calls to Admins will be honored by their Busy Options settings.</span></span>
    
- <span data-ttu-id="b083f-142">Apariencia de línea compartida</span><span class="sxs-lookup"><span data-stu-id="b083f-142">Shared Line Appearance</span></span> 
    
  - <span data-ttu-id="b083f-143">Se omitirá la configuración de Opciones de disponibilidad en las cuentas de usuario configuradas para apariencia de línea compartida.</span><span class="sxs-lookup"><span data-stu-id="b083f-143">Busy Options settings on user accounts set up for Shared Line Appearance will be ignored.</span></span> 
    
  - <span data-ttu-id="b083f-144">En su lugar, se respetarán las opciones "Ocupado" nativo de apariencia de línea compartida y "Correo de voz en Ocupado".</span><span class="sxs-lookup"><span data-stu-id="b083f-144">Shared Line Appearance's native Busy on Busy and Voicemail on Busy options will be honored instead.</span></span>
    
- <span data-ttu-id="b083f-145">Servicio de estacionamiento de llamadas</span><span class="sxs-lookup"><span data-stu-id="b083f-145">Call Parking Service</span></span> 
    
  - <span data-ttu-id="b083f-146">Las llamadas estacionadas que no se recuperaron y que están sonando debido al tiempo de inacurrida podrán sonar para el usuario que estacionó la llamada mediante Opciones de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="b083f-146">Parked calls that were not retrieved and are ringing back due to timing out will be allowed to ring though to the user who parked the call by the Busy Options.</span></span> 
    
- <span data-ttu-id="b083f-147">Conferencia de llamadas</span><span class="sxs-lookup"><span data-stu-id="b083f-147">Call Conferencing</span></span>
    
  - <span data-ttu-id="b083f-148">Los usuarios de las llamadas de conferencia se consideran ocupados y las llamadas entrantes nuevas se rechazarán con una señal de ocupado o se reenviarán al correo de voz de acuerdo con la configuración de Opciones de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="b083f-148">Users in conference calls are considered Busy and new incoming calls will be rejected with a busy signal or forwarded to voice mail according to their Busy Options settings.</span></span>
    
  - <span data-ttu-id="b083f-149">Las opciones de disponibilidad no impiden que los usuarios de las conferencias inicien nuevas llamadas o conferencias.</span><span class="sxs-lookup"><span data-stu-id="b083f-149">Users in conferences are not prevented from initiating new calls or conferences by Busy Options.</span></span>
    
  - <span data-ttu-id="b083f-150">Los usuarios de las conferencias aún pueden recibir nuevas invitaciones a conferencias, pero las llamadas punto a punto nuevas se rechazarán según la configuración de Opciones de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="b083f-150">Users in conferences are still able to receive new conference invitations, but new peer-to-peer calls will be rejected according to their Busy Options settings.</span></span>
    
- <span data-ttu-id="b083f-151">Llamadas simultáneas y reenvío de llamadas</span><span class="sxs-lookup"><span data-stu-id="b083f-151">Simultaneous Ring and Call Forwarding</span></span>
    
    <span data-ttu-id="b083f-152">La característica Ocupado en ocupado no está diseñada para funcionar con llamadas simultáneas y el reenvío de llamadas.</span><span class="sxs-lookup"><span data-stu-id="b083f-152">The Busy on Busy feature is not designed to work with Simultaneous Ring and Call Forwarding.</span></span>
    

