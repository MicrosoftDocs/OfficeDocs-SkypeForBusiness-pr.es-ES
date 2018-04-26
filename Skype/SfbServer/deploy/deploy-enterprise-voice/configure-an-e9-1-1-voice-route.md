---
title: Configurar una ruta de voz de E9-1-1 en Skype Empresarial Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/7/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 6933b840-0e7b-4509-ae43-bc9065677547
description: Configurar rutas de voz E9-1-1 en Skype para Telefonía IP empresarial de Business Server.
ms.openlocfilehash: 17614a4daedfdfe437a09858649972ca1c3e779d
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="configure-an-e9-1-1-voice-route-in-skype-for-business-server-2015"></a><span data-ttu-id="54ede-103">Configurar una ruta de voz de E9-1-1 en Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="54ede-103">Configure an E9-1-1 voice route in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="54ede-104">Configurar rutas de voz E9-1-1 en Skype para Telefonía IP empresarial de Business Server.</span><span class="sxs-lookup"><span data-stu-id="54ede-104">Configure E9-1-1 voice routes in Skype for Business Server Enterprise Voice.</span></span> 
  
<span data-ttu-id="54ede-105">Para implementar E9-1-1, deberá configurar primero una ruta de voz para llamadas de emergencia.</span><span class="sxs-lookup"><span data-stu-id="54ede-105">To deploy E9-1-1, you first need to configure an emergency call voice route.</span></span> <span data-ttu-id="54ede-106">Para obtener más información acerca de cómo crear rutas de voz, consulte [crear o modificar una ruta de voz de Skype para el año 2015 Business](create-or-modify-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="54ede-106">For details about creating voice routes, see [Create or modify a voice route in Skype for Business 2015](create-or-modify-a-voice-route.md).</span></span> <span data-ttu-id="54ede-107">Puede definir más de una ruta si, por ejemplo, su implementación incluye un tronco SIP principal y otro secundario.</span><span class="sxs-lookup"><span data-stu-id="54ede-107">You may define more than one route if, for example, your deployment includes a primary SIP trunk and a secondary SIP trunk.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="54ede-108">Para incluir información de ubicación en un invitar E9-1-1, necesitará configurar el tronco SIP que conecta con el proveedor de servicios de E9-1-1 para enrutar las llamadas de emergencia a través de la puerta de enlace.</span><span class="sxs-lookup"><span data-stu-id="54ede-108">To include location information in an E9-1-1 INVITE, you need to configure the SIP trunk that connects to the E9-1-1 service provider to route emergency calls through the gateway.</span></span> <span data-ttu-id="54ede-109">Para ello, establezca el indicador EnablePIDFLOSupport en el cmdlet **Set-CsTrunkConfiguration** en True.</span><span class="sxs-lookup"><span data-stu-id="54ede-109">To do this, set the EnablePIDFLOSupport flag on the **Set-CsTrunkConfiguration** cmdlet to True.</span></span> <span data-ttu-id="54ede-110">El valor predeterminado de EnablePIDFLOSupport es False.</span><span class="sxs-lookup"><span data-stu-id="54ede-110">The default value for EnablePIDFLOSupport is False.</span></span> <span data-ttu-id="54ede-111">Por ejemplo: `Set-CsTrunkConfiguration Service:PstnGateway:192.168.0.241 -EnablePIDFLOSupport $true.` no es necesario habilitar las ubicaciones de recepción para reserva pública conmutada puertas de enlace de teléfono red (conmutada PSTN) y las puertas de enlace de número de identificación de ubicación de emergencia (ELIN).</span><span class="sxs-lookup"><span data-stu-id="54ede-111">For example: `Set-CsTrunkConfiguration Service:PstnGateway:192.168.0.241 -EnablePIDFLOSupport $true.` It is not necessary to enable receiving locations for fallback public switched telephone network (PSTN) gateways and Emergency Location Identification Number (ELIN) gateways.</span></span>
  
### <a name="to-configure-an-e9-1-1-voice-route"></a><span data-ttu-id="54ede-112">Para configurar una ruta de voz de E9-1-1</span><span class="sxs-lookup"><span data-stu-id="54ede-112">To configure an E9-1-1 voice route</span></span>

1. <span data-ttu-id="54ede-113">Inicie sesión en el equipo con una cuenta que sea miembro de los grupos RTCUniversalServerAdmins o del rol administrativo CsVoiceAdministrator.</span><span class="sxs-lookup"><span data-stu-id="54ede-113">Log on to the computer with an account that is a member of the RTCUniversalServerAdmins groups, or a member of the CsVoiceAdministrator administrative role.</span></span>
    
2.  <span data-ttu-id="54ede-114">Inicie el Shell de administración de Skype Empresarial Server: haga clic en **Inicio**, **Todos los programas**, **Skype Empresarial Server 2015** y, después, en **Shell de administración de Skype Empresarial Server**.</span><span class="sxs-lookup"><span data-stu-id="54ede-114">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="54ede-115">Ejecute el siguiente cmdlet para crear un nuevo registro de uso de RTC.</span><span class="sxs-lookup"><span data-stu-id="54ede-115">Run the following cmdlet to create a new PSTN usage record.</span></span> 
    
    <span data-ttu-id="54ede-116">Debe ser el mismo nombre que vaya a usar para la configuración de **RTC** en la directiva de ubicación.</span><span class="sxs-lookup"><span data-stu-id="54ede-116">This must be the same name that you will use for the **PSTN** setting in the location policy.</span></span> <span data-ttu-id="54ede-117">Aunque la implementación va a tener varios registros de uso telefónico, en el siguiente ejemplo se agrega “Uso para emergencias” a la lista actual de usos de de RTC disponibles.</span><span class="sxs-lookup"><span data-stu-id="54ede-117">Although your deployment will have multiple phone usage records, the following example adds "Emergency Usage" to the current list of available PSTN usages.</span></span> <span data-ttu-id="54ede-118">Para obtener más información, consulte [Configurar directivas de voz, registros de uso PSTN y rutas de voz de Skype para negocios 2015](voice-and-pstn.md).</span><span class="sxs-lookup"><span data-stu-id="54ede-118">For details, see [Configure voice policies, PSTN usage records, and voice routes in Skype for Business 2015](voice-and-pstn.md).</span></span>
    
   ```
   Set-CsPstnUsage -Usage @{add='EmergencyUsage'}
   ```

4. <span data-ttu-id="54ede-119">Ejecute el siguiente cmdlet para crear una nueva ruta de voz usando el registro de uso de RTC creado en el paso anterior.</span><span class="sxs-lookup"><span data-stu-id="54ede-119">Run the following cmdlet to create a new voice route by using the PSTN usage record that you created in the previous step.</span></span>
    
    <span data-ttu-id="54ede-120">El patrón numérico debe coincidir con el patrón numérico que se usa en la configuración de **Cadena de marcado de emergencia** en la directiva de ubicación.</span><span class="sxs-lookup"><span data-stu-id="54ede-120">The number pattern must be the same number pattern that is used in the **Emergency Dial String** setting in the location policy.</span></span> <span data-ttu-id="54ede-121">Un signo "+" es necesaria porque Skype para empresas agrega "+" para llamadas de emergencia.</span><span class="sxs-lookup"><span data-stu-id="54ede-121">A "+" sign is needed because Skype for Business adds "+" to emergency calls.</span></span> <span data-ttu-id="54ede-122">"Co1-pstngateway-1" es el identificador del servicio de tronco SIP del proveedor de servicios E9-11.</span><span class="sxs-lookup"><span data-stu-id="54ede-122">"Co1-pstngateway-1" is the SIP trunk service ID for the E9-1-1 service provider or for the ELIN gateway service ID.</span></span> <span data-ttu-id="54ede-123">En el siguiente ejemplo se usa “EmergencyRoute” como nombre de la ruta de voz.</span><span class="sxs-lookup"><span data-stu-id="54ede-123">The following example uses "EmergencyRoute" as the name of the voice route.</span></span>
    
   ```
   New-CsVoiceRoute -Name "EmergencyRoute" -NumberPattern "^\+911$" -PstnUsages @{add="EmergencyUsage"} -PstnGatewayList @{add="co1-pstngateway-1"}

   ```

5. <span data-ttu-id="54ede-124">Opcionalmente, para las conexiones de troncal SIP, recomendamos que ejecute el siguiente cmdlet para crear una ruta local para las llamadas que no son controladas por el tronco SIP del proveedor de servicios de E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="54ede-124">Optionally, for SIP trunk connections, we recommend that you run the following cmdlet to create a local route for calls that are not handled by the E9-1-1 service provider's SIP trunk.</span></span> <span data-ttu-id="54ede-125">Esta ruta se usará en el caso de que la conexión con el proveedor de servicios de E9-11 no esté disponible.</span><span class="sxs-lookup"><span data-stu-id="54ede-125">This route will be used if the connection to the E9-1-1 service provider is not available.</span></span> 
    
    <span data-ttu-id="54ede-126">En el siguiente ejemplo se da por hecho que el usuario tiene un uso “Local” en su directiva de voz.</span><span class="sxs-lookup"><span data-stu-id="54ede-126">The following example assumes that user has "Local" usage in their voice policy.</span></span>
    
   ```
   New-CsVoiceRoute -Name "LocalEmergencyRoute" -NumberPattern "^\+911$" -PstnUsages @{add="Local"} -PstnGatewayList @{add="co1-pstngateway-2"}
   ```


