---
title: Plan para el parque de llamadas en Skype empresarial
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 985dc326-0aef-4308-b98b-c1d0069311e7
description: Planificación del parque de llamadas en Skype empresarial Server Enterprise Voice, que permite poner llamadas en espera y transferir llamadas a departamentos. Incluye el planeamiento de capacidad, llamadas admitidas y clientes admitidos.
ms.openlocfilehash: 3effeab4afef60fb7a5021206d9fc3cd0227ceb1
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41803200"
---
# <a name="plan-for-call-park-in-skype-for-business"></a><span data-ttu-id="bc251-104">Plan para el parque de llamadas en Skype empresarial</span><span class="sxs-lookup"><span data-stu-id="bc251-104">Plan for Call Park in Skype for Business</span></span>
 
<span data-ttu-id="bc251-105">Planificación del parque de llamadas en Skype empresarial Server Enterprise Voice, que permite poner llamadas en espera y transferir llamadas a departamentos.</span><span class="sxs-lookup"><span data-stu-id="bc251-105">Planning for call park in Skype for Business Server Enterprise Voice, which enables putting calls on hold and transferring calls to departments.</span></span> <span data-ttu-id="bc251-106">Incluye el planeamiento de capacidad, llamadas admitidas y clientes admitidos.</span><span class="sxs-lookup"><span data-stu-id="bc251-106">Includes capacity planning, supported calls, and supported clients.</span></span>
  
<span data-ttu-id="bc251-107">La aplicación de estacionamiento de llamadas permite a los usuarios de telefonía empresarial hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="bc251-107">The Call Park application enables Enterprise Voice users to do the following:</span></span>
  
- <span data-ttu-id="bc251-108">Poner una llamada en espera y recuperar la llamada desde el mismo teléfono o desde otro.</span><span class="sxs-lookup"><span data-stu-id="bc251-108">Put a call on hold and then retrieve the call from the same phone or another phone.</span></span>
    
- <span data-ttu-id="bc251-109">Poner una llamada en espera para transferirla a un departamento o área general, por ejemplo, a un departamento de ventas o a un almacén donde hay un teléfono de área común.</span><span class="sxs-lookup"><span data-stu-id="bc251-109">Put a call on hold to transfer it to a department or general area (for example, to a sales department or a warehouse where there is a common area phone).</span></span>
    
- <span data-ttu-id="bc251-110">Poner una llamada en espera y conservar el teléfono original que ha respondido disponible para recibir otras llamadas.</span><span class="sxs-lookup"><span data-stu-id="bc251-110">Put a call on hold and keep the original answering phone free for other calls.</span></span>
    
<span data-ttu-id="bc251-111">Cuando un usuario detiene una llamada, Skype empresarial Server transfiere la llamada a un número temporal, denominado órbita, en el que se mantiene la llamada hasta que se recupera o se agota el tiempo de espera. Skype empresarial Server envía la órbita al usuario que ha detenido la llamada.</span><span class="sxs-lookup"><span data-stu-id="bc251-111">When a user parks a call, Skype for Business Server transfers the call to a temporary number, called an orbit, where the call is held until it is retrieved or it times out. Skype for Business Server sends the orbit to the user who parked the call.</span></span> <span data-ttu-id="bc251-112">Para recuperar la llamada estacionada, el usuario puede marcar el número de órbita o hacer clic en el botón o vínculo de órbita de la ventana Conversación.</span><span class="sxs-lookup"><span data-stu-id="bc251-112">To retrieve the parked call, the user can dial the orbit number or click the orbit link or button in the Conversation window.</span></span> 
  
<span data-ttu-id="bc251-p104">El usuario que estacionó una llamada puede notificar a alguien que recupere la llamada usando un mecanismo externo, como la mensajería instantánea (MI) o un sistema de localización, para comunicar el número de órbita a otro usuario. El usuario que estacionó la llamada puede dejar la ventana Conversación abierta para recibir una notificación cuando se recupere la llamada.</span><span class="sxs-lookup"><span data-stu-id="bc251-p104">The user who parked a call can notify someone to retrieve the call by using an external mechanism, such as instant messaging (IM) or a paging system, to communicate the orbit number to someone else. The user who parked the call can leave the Conversation window open to receive notification when the call is retrieved.</span></span>
  
<span data-ttu-id="bc251-115">Dado que los intervalos de órbita son únicos globalmente, es posible recuperar las llamadas desde cualquier sitio de Skype empresarial Server o PBX si el enrutamiento está configurado correctamente.</span><span class="sxs-lookup"><span data-stu-id="bc251-115">Because orbit ranges are globally unique, it is possible to retrieve calls from any Skype for Business Server site or PBX phone if routing is configured appropriately.</span></span> <span data-ttu-id="bc251-116">Si nadie recupera la llamada en un período de tiempo configurable, la llamada volverá a sonar para la persona que la estacionó.</span><span class="sxs-lookup"><span data-stu-id="bc251-116">If no one retrieves the call within a configurable amount of time, the call rings back to the person who parked it.</span></span> <span data-ttu-id="bc251-117">Si dicha persona no responde esta vez, la llamada se transferirá a un destino de conmutación por error, como un operador, si se ha configurado así.</span><span class="sxs-lookup"><span data-stu-id="bc251-117">If that person does not answer the ringback, the call is transferred to a fallback destination, such as to an operator, if so configured.</span></span> <span data-ttu-id="bc251-118">Puedes configurar el número de veces que deseas que suene la llamada antes de ser transferida de una a diez veces.</span><span class="sxs-lookup"><span data-stu-id="bc251-118">You can configure the number of times the call rings back before being transferred from one to ten times.</span></span> <span data-ttu-id="bc251-119">Si nadie responde a una llamada transferida, la llamada se desconectará.</span><span class="sxs-lookup"><span data-stu-id="bc251-119">If no one answers a transferred call, the call is disconnected.</span></span> <span data-ttu-id="bc251-120">La órbita se libera cuando se recupera la llamada o se desconecta.</span><span class="sxs-lookup"><span data-stu-id="bc251-120">The orbit is freed when the call is retrieved or disconnected.</span></span>
  
<span data-ttu-id="bc251-121">Al implementar el estacionamiento de llamadas, necesitarás reservar intervalos de números de extensión para estacionar llamadas.</span><span class="sxs-lookup"><span data-stu-id="bc251-121">When you deploy Call Park, you need to reserve ranges of extension numbers for parking calls.</span></span> <span data-ttu-id="bc251-122">Estas extensiones necesitan ser extensiones virtuales: extensiones que no tienen ningún usuario o teléfono asignado.</span><span class="sxs-lookup"><span data-stu-id="bc251-122">These extensions need to be virtual extensions: extensions that have no user or phone assigned to them.</span></span> <span data-ttu-id="bc251-123">Luego, necesitarás configurar la tabla de órbitas de estacionamiento de llamadas con los intervalos de números de extensión y especificar qué servicio de aplicaciones hospeda la aplicación Estacionamiento de llamadas que administra cada intervalo.</span><span class="sxs-lookup"><span data-stu-id="bc251-123">You then configure the call park orbit table with the ranges of extension numbers and specify which Application service hosts the Call Park application that handles each range.</span></span> <span data-ttu-id="bc251-124">Cada grupo de servidores front-end tiene una tabla de estacionamiento de llamadas en el servidor back end correspondiente que se usa para administrar las llamadas que se aparcarán en el grupo.</span><span class="sxs-lookup"><span data-stu-id="bc251-124">Each Front End pool has a Call Park table on the corresponding Back End Server that is used to manage calls that are parked on the pool.</span></span> <span data-ttu-id="bc251-125">La lista de intervalos de órbita se almacena en el almacén de administración central y se usa para enrutar órbitas hasta el grupo de destino.</span><span class="sxs-lookup"><span data-stu-id="bc251-125">The list of orbit ranges is stored in Central Management store and is used to route orbits to the destination pool.</span></span> <span data-ttu-id="bc251-126">Cada grupo de servidores de Skype empresarial en el que se implementa y configura la aplicación de estacionamiento de llamadas puede tener uno o más intervalos orbitales.</span><span class="sxs-lookup"><span data-stu-id="bc251-126">Each Skype for Business Server pool where the Call Park application is deployed and configured can have one or more orbit ranges.</span></span> <span data-ttu-id="bc251-127">Los intervalos de órbita deben ser únicos globalmente en toda la implementación de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="bc251-127">Orbit ranges must be globally unique across the Skype for Business Server deployment.</span></span> 
  
<span data-ttu-id="bc251-p107">También configuras otras opciones de estacionamiento de llamadas, como, por ejemplo, el lugar al que se redirigirán las llamadas si transcurre el tiempo de espera y si la persona que está al teléfono oirá música mientras la llamada está estacionada. Asimismo, puedes especificar el archivo de música que deseas que se reproduzca mientras la llamada está en espera.</span><span class="sxs-lookup"><span data-stu-id="bc251-p107">You also configure other Call Park settings, such as where calls are redirected if they time out and whether the person on the phone hears music while parked. You can also specify the music file to play while the call is on hold.</span></span>
  
> [!NOTE]
> <span data-ttu-id="bc251-130">No se realiza una copia de seguridad de los archivos de música hospedada personalizada para el servicio de recuperación de desastres de Skype empresarial y se perderán si los archivos cargados en el grupo están dañados, dañados o borrados.</span><span class="sxs-lookup"><span data-stu-id="bc251-130">Customized music-on-hold files for Call Park are not backed up as part of the Skype for Business Server disaster recovery process and will be lost if the files uploaded to the pool are damaged, corrupted, or erased.</span></span> <span data-ttu-id="bc251-131">Guarda siempre una copia de seguridad independiente de los archivos de música en espera personalizados que haya cargado para el estacionamiento de llamadas.</span><span class="sxs-lookup"><span data-stu-id="bc251-131">Always keep a separate backup copy of the customized music-on-hold files that you have uploaded for Call Park.</span></span> 
  
<span data-ttu-id="bc251-132">La aplicación Estacionamiento de llamadas es un componente de la telefonía IP empresarial.</span><span class="sxs-lookup"><span data-stu-id="bc251-132">The Call Park application is a component of Enterprise Voice.</span></span> <span data-ttu-id="bc251-133">Al implementar la telefonía IP empresarial, la aplicación de estacionamiento de llamadas se instala y activa automáticamente.</span><span class="sxs-lookup"><span data-stu-id="bc251-133">When you deploy Enterprise Voice, the Call Park application is installed and activated automatically.</span></span> <span data-ttu-id="bc251-134">Sin embargo, antes de poder usar el parque de llamadas, el administrador de telefonía IP debe configurarlo y habilitarlo para los usuarios mediante la Directiva de voz.</span><span class="sxs-lookup"><span data-stu-id="bc251-134">Before you can use Call Park, however, the Enterprise Voice administrator must configure it and enable it for users through voice policy.</span></span>
  
## <a name="deployment-and-requirements"></a><span data-ttu-id="bc251-135">Requisitos e implementación</span><span class="sxs-lookup"><span data-stu-id="bc251-135">Deployment and requirements</span></span>

<span data-ttu-id="bc251-136">La aplicación de estacionamiento de llamadas se instala automáticamente al implementar la telefonía IP empresarial.</span><span class="sxs-lookup"><span data-stu-id="bc251-136">The Call Park application is automatically installed when you deploy Enterprise Voice.</span></span> <span data-ttu-id="bc251-137">Para habilitar el parque de llamadas, configure la Directiva de voz.</span><span class="sxs-lookup"><span data-stu-id="bc251-137">You enable Call Park by configuring voice policy.</span></span>
  
### <a name="software-requirements"></a><span data-ttu-id="bc251-138">Requisitos de software</span><span class="sxs-lookup"><span data-stu-id="bc251-138">Software requirements</span></span>

<span data-ttu-id="bc251-139">Todos los servidores front-end y los servidores Standard Edition en los que se implemente el parque de llamadas deben tener instalado el Windows Media Format Runtime para servidores que ejecuten Windows Server 2008 R2 o Microsoft Media Foundation para servidores que ejecuten Windows Server 2012 o Windows Server 2012 R2.</span><span class="sxs-lookup"><span data-stu-id="bc251-139">All Front End Servers and Standard Edition servers where Call Park is deployed must have the Windows Media Format Runtime installed for servers running Windows Server 2008 R2, or Microsoft Media Foundation for servers running Windows Server 2012 or Windows Server 2012 R2.</span></span> <span data-ttu-id="bc251-140">Para Windows Server 2008 R2, Windows Media Format Runtime se instala como parte de la experiencia de escritorio de Windows.</span><span class="sxs-lookup"><span data-stu-id="bc251-140">For Windows Server 2008 R2, Windows Media Format Runtime is installed as part of Windows Desktop Experience.</span></span> <span data-ttu-id="bc251-141">Se necesita Windows Media Format Runtime o Microsoft Media Foundation para los archivos de audio de Windows Media (. WMA) que llaman a reproducciones de estacionamiento para música en espera.</span><span class="sxs-lookup"><span data-stu-id="bc251-141">Windows Media Format Runtime or Microsoft Media Foundation is required for Windows Media Audio (.wma) files that Call Park plays for music on hold.</span></span>
  
### <a name="port-requirements"></a><span data-ttu-id="bc251-142">Requisitos de los puertos</span><span class="sxs-lookup"><span data-stu-id="bc251-142">Port requirements</span></span>

<span data-ttu-id="bc251-143">La aplicación de estacionamiento de llamadas usa el **puerto 5075** para solicitudes de escucha de SIP.</span><span class="sxs-lookup"><span data-stu-id="bc251-143">The Call Park application uses **Port 5075**  for SIP listening requests.</span></span>
    
> [!NOTE]
> <span data-ttu-id="bc251-144">Este puerto es una configuración predeterminada que puedes cambiar con el cmdlet **Set-CsApplicationServer**.</span><span class="sxs-lookup"><span data-stu-id="bc251-144">This port is a default setting that you can change by using the **Set-CsApplicationServer** cmdlet.</span></span> <span data-ttu-id="bc251-145">Para obtener más información sobre este cmdlet, consulte la documentación del shell de administración de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="bc251-145">For details about this cmdlet, see the Lync Server Management Shell documentation.</span></span>
  
### <a name="audio-file-requirements"></a><span data-ttu-id="bc251-146">Requisitos de archivos de audio</span><span class="sxs-lookup"><span data-stu-id="bc251-146">Audio File requirements</span></span>

<span data-ttu-id="bc251-147">La aplicación de estacionamiento de llamadas solo admite archivos de audio de Windows Media (. WMA) para música en espera.</span><span class="sxs-lookup"><span data-stu-id="bc251-147">The Call Park application supports only Windows Media Audio (.wma) files for music on hold.</span></span> <span data-ttu-id="bc251-148">Puedes usar Microsoft Expression Encoder 4 para personalizar los archivos para la música en espera.</span><span class="sxs-lookup"><span data-stu-id="bc251-148">You can use the Microsoft Expression Encoder 4 to customize files for music on hold.</span></span> <span data-ttu-id="bc251-149">Para descargar Expression Encoder 4, consulta ["Expression Encoder 4"](https://go.microsoft.com/fwlink/p/?linkId=202843).</span><span class="sxs-lookup"><span data-stu-id="bc251-149">To download Expression Encoder 4, see   ["Expression Encoder 4"](https://go.microsoft.com/fwlink/p/?linkId=202843).</span></span> <span data-ttu-id="bc251-150">Usa la herramienta para convertir el archivo en un formato .wma.</span><span class="sxs-lookup"><span data-stu-id="bc251-150">Use the tool to convert the file to a .wma format.</span></span> <span data-ttu-id="bc251-151">El formato recomendado para los archivos de reactivar música en espera de llamadas es media audio 9, 44 kHz, 16 bits, mono, CBR, 32 kbps.</span><span class="sxs-lookup"><span data-stu-id="bc251-151">The recommended format for Call Park music-on-hold files is Media Audio 9, 44 kHz, 16 bits, Mono, CBR, 32 kbps.</span></span>
  
> [!NOTE]
> <span data-ttu-id="bc251-152">El archivo convertido se reproduce por el teléfono solo a 16 kHz, aunque se grabó a 44 kHz.</span><span class="sxs-lookup"><span data-stu-id="bc251-152">The converted file plays over the phone only at 16 kHz, even if it was recorded at 44 kHz.</span></span> 
  
## <a name="supported-clients-and-calls"></a><span data-ttu-id="bc251-153">Llamadas y clientes compatibles</span><span class="sxs-lookup"><span data-stu-id="bc251-153">Supported clients and calls</span></span>

<span data-ttu-id="bc251-154">Los siguientes clientes y tipos de llamadas son compatibles con el parque de llamadas</span><span class="sxs-lookup"><span data-stu-id="bc251-154">The following clients and types of calls are supported for Call Park</span></span>
  
### <a name="clients-supported-for-parking-calls"></a><span data-ttu-id="bc251-155">Clientes compatibles con el estacionamiento de llamadas</span><span class="sxs-lookup"><span data-stu-id="bc251-155">Clients Supported for Parking Calls</span></span>

<span data-ttu-id="bc251-156">Se pueden estacionar las llamadas de cualquier IP, central de conmutación (PBX), red telefónica conmutada (RTC) o teléfono móvil.</span><span class="sxs-lookup"><span data-stu-id="bc251-156">Calls from any IP, private branch exchange (PBX), public switched telephone network (PSTN), or mobile phone can be parked.</span></span>
  
> [!NOTE]
> <span data-ttu-id="bc251-p114">Únicamente se pueden estacionar las llamadas de audio. No se pueden estacionar los mensajes instantáneos ni las conferencias.</span><span class="sxs-lookup"><span data-stu-id="bc251-p114">Only audio calls can be parked. Instant messages and conferences cannot be parked.</span></span> 
  
<span data-ttu-id="bc251-159">Los siguientes clientes pueden usar el activador de llamadas para detener llamadas:</span><span class="sxs-lookup"><span data-stu-id="bc251-159">The following clients can use Call Park to park calls:</span></span>
  
- <span data-ttu-id="bc251-160">Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="bc251-160">Skype for Business</span></span>
    
- <span data-ttu-id="bc251-161">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="bc251-161">Lync 2013</span></span>
    
- <span data-ttu-id="bc251-162">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="bc251-162">Lync 2010</span></span>
    
- <span data-ttu-id="bc251-163">Operador de Lync 2010</span><span class="sxs-lookup"><span data-stu-id="bc251-163">Lync 2010 Attendant</span></span>
    
- <span data-ttu-id="bc251-164">Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="bc251-164">Lync Phone Edition</span></span>
    
> [!NOTE]
> <span data-ttu-id="bc251-165">Los teléfonos móviles no pueden usar el parque de llamadas para detener llamadas.</span><span class="sxs-lookup"><span data-stu-id="bc251-165">Mobile phones cannot use Call Park to park calls.</span></span> 
  
### <a name="clients-supported-for-retrieving-calls"></a><span data-ttu-id="bc251-166">Clientes compatibles con la recuperación de llamadas</span><span class="sxs-lookup"><span data-stu-id="bc251-166">Clients Supported for Retrieving Calls</span></span>

<span data-ttu-id="bc251-p115">Los intervalos de órbitas están configurados como bloques de extensiones virtuales (extensiones sin ningún usuario ni teléfono asignado). Cuando configuras órbitas como extensiones virtuales, teléfonos móviles y teléfono RTC, no puedes recuperar llamadas estacionadas.</span><span class="sxs-lookup"><span data-stu-id="bc251-p115">Orbit ranges are configured as blocks of virtual extensions (extensions without an assigned user or phone). When you configure orbits as virtual extensions, mobile phones and PSTN phones cannot retrieve parked calls.</span></span>
  
<span data-ttu-id="bc251-169">Los usuarios federados no pueden recuperar llamadas estacionadas.</span><span class="sxs-lookup"><span data-stu-id="bc251-169">Federated users cannot retrieve parked calls.</span></span>
  
<span data-ttu-id="bc251-170">Los siguientes clientes pueden recuperar llamadas estacionadas en el parque de llamadas:</span><span class="sxs-lookup"><span data-stu-id="bc251-170">The following clients can retrieve calls that are parked on Call Park:</span></span>
  
- <span data-ttu-id="bc251-171">Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="bc251-171">Skype for Business</span></span>
    
- <span data-ttu-id="bc251-172">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="bc251-172">Lync 2013</span></span>
    
- <span data-ttu-id="bc251-173">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="bc251-173">Lync 2010</span></span>
    
- <span data-ttu-id="bc251-174">Operador de Lync 2010</span><span class="sxs-lookup"><span data-stu-id="bc251-174">Lync 2010 Attendant</span></span>
    
- <span data-ttu-id="bc251-175">Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="bc251-175">Lync Phone Edition</span></span>
    
- <span data-ttu-id="bc251-176">Teléfonos IP de área común</span><span class="sxs-lookup"><span data-stu-id="bc251-176">IP common area phones</span></span>
    
- <span data-ttu-id="bc251-177">Teléfonos no basados en IP que están conectados a la infraestructura de Skype empresarial Server, incluidos teléfonos de área común y teléfonos de central de conmutación (PBX)</span><span class="sxs-lookup"><span data-stu-id="bc251-177">Non-IP phones that are connected to the Skype for Business Server infrastructure, including common area phones and private branch exchange (PBX) phones</span></span>
    
## <a name="call-park-capacity-planning"></a><span data-ttu-id="bc251-178">Planificación de la capacidad del estacionamiento de llamadas</span><span class="sxs-lookup"><span data-stu-id="bc251-178">Call Park capacity planning</span></span>

<span data-ttu-id="bc251-179">En la siguiente tabla se describe el modelo de usuario de estacionamiento de llamadas que puede usar como base para los requisitos de planes de capacidad.</span><span class="sxs-lookup"><span data-stu-id="bc251-179">The following table describes the Call Park user model that you can use as the basis for capacity planning requirements.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="bc251-180">Tenga en cuenta que, para la planeación de la capacidad de recuperación ante desastres, cada grupo de un grupo emparejado debería poder administrar las cargas de trabajo de los servicios de estacionamiento de llamadas en ambos grupos.</span><span class="sxs-lookup"><span data-stu-id="bc251-180">Keep in mind that, for disaster recovery capacity planning, each pool of a paired pool should be able to handle the workloads for Call Park services in both pools.</span></span> 
  
<span data-ttu-id="bc251-181">**Modelo de usuario de estacionamiento de llamadas**</span><span class="sxs-lookup"><span data-stu-id="bc251-181">**Call Park User Model**</span></span>

|<span data-ttu-id="bc251-182">**Métrica**</span><span class="sxs-lookup"><span data-stu-id="bc251-182">**Metric**</span></span>|<span data-ttu-id="bc251-183">**Por grupo <br/> front-end (con 8 servidores frontales)**</span><span class="sxs-lookup"><span data-stu-id="bc251-183">**Per Front End pool  <br/>  (with 8 Front End Servers)**</span></span>|<span data-ttu-id="bc251-184">**Por servidor Standard Edition**</span><span class="sxs-lookup"><span data-stu-id="bc251-184">**Per Standard Edition server**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="bc251-185">Tasa de estacionamiento</span><span class="sxs-lookup"><span data-stu-id="bc251-185">Park rate</span></span>  <br/> |<span data-ttu-id="bc251-186">8 por minuto</span><span class="sxs-lookup"><span data-stu-id="bc251-186">8 per minute</span></span>  <br/> |<span data-ttu-id="bc251-187">1 por minuto</span><span class="sxs-lookup"><span data-stu-id="bc251-187">1 per minute</span></span>  <br/> |
|<span data-ttu-id="bc251-188">Tasa de recuperación de llamadas estacionadas</span><span class="sxs-lookup"><span data-stu-id="bc251-188">Retrieve parked call rate</span></span>  <br/> |<span data-ttu-id="bc251-189">8 por minuto</span><span class="sxs-lookup"><span data-stu-id="bc251-189">8 per minute</span></span>  <br/> |<span data-ttu-id="bc251-190">1 por minuto</span><span class="sxs-lookup"><span data-stu-id="bc251-190">1 per minute</span></span>  <br/> |
|<span data-ttu-id="bc251-191">Promedio de duración del estacionamiento</span><span class="sxs-lookup"><span data-stu-id="bc251-191">Average park duration</span></span>  <br/> |<span data-ttu-id="bc251-192">60 segundos</span><span class="sxs-lookup"><span data-stu-id="bc251-192">60 seconds</span></span>  <br/> |<span data-ttu-id="bc251-193">60 segundos</span><span class="sxs-lookup"><span data-stu-id="bc251-193">60 seconds</span></span>  <br/> |
   

