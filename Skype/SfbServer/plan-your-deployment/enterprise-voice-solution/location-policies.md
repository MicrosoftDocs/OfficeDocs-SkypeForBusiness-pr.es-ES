---
title: Planear directivas de ubicación para Skype Empresarial Server
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
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: da3cca7f-f6e5-4b6f-90a1-2008e3dd1ebd
description: Lea este tema para obtener información sobre cómo planear directivas de ubicación para una implementación mejorada de servicios de emergencia (E9-1-1) en Skype Empresarial Server Telefonía IP empresarial.
ms.openlocfilehash: 3d9c574d18351594d9773f02770e960c993ae401
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51101456"
---
# <a name="plan-location-policies-for-skype-for-business-server"></a><span data-ttu-id="ff4d4-103">Planear directivas de ubicación para Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="ff4d4-103">Plan location policies for Skype for Business Server</span></span>
 
<span data-ttu-id="ff4d4-104">Lea este tema para obtener información sobre cómo planear directivas de ubicación para una implementación mejorada de servicios de emergencia (E9-1-1) en Skype Empresarial Server Telefonía IP empresarial.</span><span class="sxs-lookup"><span data-stu-id="ff4d4-104">Read this topic to learn how to plan location policies for an enhanced emergency services (E9-1-1) deployment in Skype for Business Server Enterprise Voice.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="ff4d4-105">Skype Empresarial Server ahora admite la configuración de varios números de emergencia para un cliente.</span><span class="sxs-lookup"><span data-stu-id="ff4d4-105">Skype for Business Server now supports the configuration of multiple emergency numbers for a client.</span></span> <span data-ttu-id="ff4d4-106">Si desea configurar varios números de emergencia, debe seguir la información de [Plan for multiple emergency numbers in Skype for Business Server](multiple-emergency-numbers.md) y Configure multiple emergency numbers in Skype for [Business](../../deploy/deploy-enterprise-voice/configure-multiple-emergency-numbers.md).</span><span class="sxs-lookup"><span data-stu-id="ff4d4-106">If you want to configure multiple emergency numbers, you must follow the information in [Plan for multiple emergency numbers in Skype for Business Server](multiple-emergency-numbers.md) and [Configure multiple emergency numbers in Skype for Business](../../deploy/deploy-enterprise-voice/configure-multiple-emergency-numbers.md).</span></span> 
  
<span data-ttu-id="ff4d4-107">Puede crear directivas de ubicación mediante el Panel de control de Skype Empresarial o mediante el cmdlet [New-CsLocationPolicy.](/powershell/module/skype/new-cslocationpolicy?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="ff4d4-107">You create location policies by using the Skype for Business Control Panel or by using the [New-CsLocationPolicy](/powershell/module/skype/new-cslocationpolicy?view=skype-ps) cmdlet.</span></span> <span data-ttu-id="ff4d4-108">Para obtener más información, vea [Create location policies in Skype for Business Server](../../deploy/deploy-enterprise-voice/create-location-policies.md).</span><span class="sxs-lookup"><span data-stu-id="ff4d4-108">For more information, see [Create location policies in Skype for Business Server](../../deploy/deploy-enterprise-voice/create-location-policies.md).</span></span>
  
<span data-ttu-id="ff4d4-109">Cada directiva de ubicación contiene la información siguiente:</span><span class="sxs-lookup"><span data-stu-id="ff4d4-109">Each location policy contains the following information:</span></span>
  
 <span data-ttu-id="ff4d4-110">**Habilitar 9-1-1 mejorado**</span><span class="sxs-lookup"><span data-stu-id="ff4d4-110">**Enable Enhanced 9-1-1**</span></span>
  
<span data-ttu-id="ff4d4-111">Cuando se habilita este valor, el cliente está habilitado para servicios de emergencia mejorados (E9-1-1).</span><span class="sxs-lookup"><span data-stu-id="ff4d4-111">When this value is enabled, the client is enabled for enhanced emergency services (E9-1-1).</span></span> <span data-ttu-id="ff4d4-112">Cuando un cliente se registra, intenta adquirir una ubicación del servicio de información de ubicación e incluirá la información de ubicación como parte de una llamada de emergencia.</span><span class="sxs-lookup"><span data-stu-id="ff4d4-112">When a client registers, it attempts to acquire a location from the Location Information service and will include the location information as part of an emergency call.</span></span>
  
 <span data-ttu-id="ff4d4-113">**Location**</span><span class="sxs-lookup"><span data-stu-id="ff4d4-113">**Location**</span></span>
  
<span data-ttu-id="ff4d4-114">Esta configuración solo se usa cuando **habilitar 9-1-1** mejorado está habilitado.</span><span class="sxs-lookup"><span data-stu-id="ff4d4-114">This setting is used only when **Enable Enhanced 9-1-1** is enabled.</span></span>
  
<span data-ttu-id="ff4d4-115">Puede configurar la opción **Ubicación** para definir el comportamiento del cliente de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="ff4d4-115">You can configure the **Location** setting to define the client behavior as follows:</span></span>
  
- <span data-ttu-id="ff4d4-116">Si se define el valor en **No**, no se pedirá al usuario una ubicación.</span><span class="sxs-lookup"><span data-stu-id="ff4d4-116">Setting the value to **No** means that the user will not be prompted for a location.</span></span>
    
- <span data-ttu-id="ff4d4-117">Si se define en **Sí**, se pedirá al usuario una ubicación, pero este puede anular la solicitud.</span><span class="sxs-lookup"><span data-stu-id="ff4d4-117">Setting the value to **Yes** means that the user will be prompted for a location, but can dismiss the prompt.</span></span>
    
- <span data-ttu-id="ff4d4-118">Si se define en **Declinación de responsabilidades**, el usuario deberá especificar una ubicación y no podrá anular la solicitud hasta que haya introducido una solicitud.</span><span class="sxs-lookup"><span data-stu-id="ff4d4-118">Setting the value to **Disclaimer** means that the user will be prompted for a location and also will be shown a disclaimer if they try to dismiss the prompt.</span></span> <span data-ttu-id="ff4d4-119">En ambos casos el usuario puede continuar usando el cliente.</span><span class="sxs-lookup"><span data-stu-id="ff4d4-119">In all cases, the user can continue to use the client.</span></span>
    
> [!NOTE]
> <span data-ttu-id="ff4d4-p105">El texto de declinación de responsabilidades no aparecerá si el usuario ha introducido manualmente una ubicación antes de ser habilitado para E9-1-1 y los usuarios que ya hayan visto la declinación de responsabilidades no recibirán las actualizaciones de dicho texto.</span><span class="sxs-lookup"><span data-stu-id="ff4d4-p105">The disclaimer text will not appear if a user manually entered a location before being enabled for E9-1-1. Updates to the disclaimer text will not be viewed by users that have already viewed the disclaimer.</span></span> 
  
 <span data-ttu-id="ff4d4-122">**Declinación de responsabilidad de servicio de emergencia mejorado**</span><span class="sxs-lookup"><span data-stu-id="ff4d4-122">**Enhanced Emergency Service Disclaimer**</span></span>
  
<span data-ttu-id="ff4d4-123">En esta configuración se especifica la declinación de responsabilidad que los usuarios ven si rechazan la solicitud de una ubicación.</span><span class="sxs-lookup"><span data-stu-id="ff4d4-123">This setting specifies the disclaimer that users see if they dismiss the prompt for a location.</span></span> <span data-ttu-id="ff4d4-124">En Skype Empresarial Server, puede usar la directiva de ubicación para establecer diferentes declinaciones de responsabilidades para diferentes configuraciones regionales o diferentes conjuntos de usuarios.</span><span class="sxs-lookup"><span data-stu-id="ff4d4-124">In Skype for Business Server, you can use location policy to set different disclaimers for different locales or different sets of users.</span></span>
  
 <span data-ttu-id="ff4d4-125">**Cadena de marcado de emergencia (número de marcado E9-1-1)**</span><span class="sxs-lookup"><span data-stu-id="ff4d4-125">**Emergency Dial String (E9-1-1 dial number)**</span></span>
  
<span data-ttu-id="ff4d4-126">Esta cadena de marcado (menos el "+" inicial, pero incluida cualquier normalización realizada por el Plan de marcado del usuario) significa que una llamada es una llamada de emergencia.</span><span class="sxs-lookup"><span data-stu-id="ff4d4-126">This dial string (less the leading "+", but including any normalization done by the user's Dial Plan) signifies that a call is an emergency call.</span></span> <span data-ttu-id="ff4d4-127">La **cadena de marcado de emergencia** comporta la adición a la llamada de información de ubicación y devolución de llamada por parte del cliente.</span><span class="sxs-lookup"><span data-stu-id="ff4d4-127">The **Emergency Dial String** causes the client to include location and callback information with the call.</span></span>
  
> [!NOTE]
> <span data-ttu-id="ff4d4-128">Si su organización no usa un prefijo de acceso de línea externa, no es necesario crear una regla de normalización del plan de marcado correspondiente que agrega un "+" a la cadena 911 antes de enviar la llamada al enrutamiento saliente en un servidor que ejecute Skype Empresarial Server; el cliente de Skype Empresarial antepone automáticamente el "+" como resultado de la directiva de ubicación.</span><span class="sxs-lookup"><span data-stu-id="ff4d4-128">If your organization does not use an external line access prefix, you do not need to create a corresponding Dial Plan normalization rule that adds a "+" to the 911 string prior to sending the call to Outbound Routing on a server running Skype for Business Server; the "+" will be automatically prepended by the Skype for Business client as a result of the location policy.</span></span> <span data-ttu-id="ff4d4-129">Sin embargo, si el sitio usa un prefijo de acceso externo, debe agregar una regla de normalización a la directiva de plan de marcado aplicable que elimina el prefijo de acceso externo y agrega el "+".</span><span class="sxs-lookup"><span data-stu-id="ff4d4-129">However, if your site uses an external access prefix, you need to add a normalization rule to the applicable Dial Plan policy that strips the external access prefix and adds the "+".</span></span> <span data-ttu-id="ff4d4-130">Por ejemplo, si su ubicación usa un prefijo de acceso externo de 9 y un usuario marca 9 911 para realizar una llamada de emergencia, el cliente usará su directiva de plan de marcado para normalizar esto a +911 antes de que las rutas del perfil de ubicación del autor de la llamada evalúen el número marcado.</span><span class="sxs-lookup"><span data-stu-id="ff4d4-130">For example, if your location uses an external access prefix of 9 and a user dials 9 911 to place an emergency call, the client will use its Dial Plan policy to normalize this to +911 before the dialed number is evaluated by the routes in the caller's location profile.</span></span> 
  
 <span data-ttu-id="ff4d4-131">**Máscaras de cadena de marcado de emergencia (máscara de marcado E9-1-1)**</span><span class="sxs-lookup"><span data-stu-id="ff4d4-131">**Emergency Dial String Masks (E9-1-1 dial mask)**</span></span>
  
<span data-ttu-id="ff4d4-132">Una lista de cadenas de marcado separadas por caracteres de punto y coma que deben convertirse a la **cadena de marcado de emergencia** especificada.</span><span class="sxs-lookup"><span data-stu-id="ff4d4-132">A semicolon-separated list of dial strings that is translated into the specified **Emergency Dial String**.</span></span> <span data-ttu-id="ff4d4-133">Por ejemplo, es posible que desee agregar 112, que es el número del servicio de emergencia para la mayor parte de Europa.</span><span class="sxs-lookup"><span data-stu-id="ff4d4-133">For example, you may want to add 112, which is the emergency service number for most of Europe.</span></span> <span data-ttu-id="ff4d4-134">Es posible que un usuario de Skype Empresarial visitante de Europa no sepa que 911 es el número de emergencia de Estados Unidos, pero puede marcar el 112 y obtener el mismo resultado.</span><span class="sxs-lookup"><span data-stu-id="ff4d4-134">A visiting Skype for Business user from Europe may not know that 911 is the U.S. emergency number, but they can dial 112 and get the same result.</span></span> <span data-ttu-id="ff4d4-135">Al igual que con la cadena de marcado de emergencia, no incluya un "+" antes de cada número y, si usa códigos de acceso de línea externa, asegúrese de que hay reglas de normalización en la directiva de plan de marcado del usuario para quitar el dígito del código de acceso.</span><span class="sxs-lookup"><span data-stu-id="ff4d4-135">As with the Emergency Dial String, do not include a "+" before each number, and if you use external line access codes, be sure there are normalization rules in the user's Dial Plan policy to strip off the access code digit.</span></span>
  
 <span data-ttu-id="ff4d4-136">**Uso de RTC**</span><span class="sxs-lookup"><span data-stu-id="ff4d4-136">**PSTN usage**</span></span>
  
<span data-ttu-id="ff4d4-137">El nombre del uso de RTC que contiene las rutas de acceso que determinan en qué tronco SIP o puerta de enlace RTC se realizarán las llamadas de emergencia.</span><span class="sxs-lookup"><span data-stu-id="ff4d4-137">The name of the PSTN Usage that contains the routing paths that determine which SIP trunk, PSTN gateway, or ELIN gateway emergency calls will go to.</span></span>
  
> [!NOTE]
> <span data-ttu-id="ff4d4-138">Solo se puede asignar un uso a una directiva de ubicación.</span><span class="sxs-lookup"><span data-stu-id="ff4d4-138">Only one usage can be assigned to a location policy.</span></span> <span data-ttu-id="ff4d4-139">Este uso de RTC invalida los usos de RTC asignados a la directiva de voz del usuario, pero solo se aplica a las llamadas realizadas a la cadena de marcado de emergencia o a una de las máscaras de cadena de marcado de emergencia.</span><span class="sxs-lookup"><span data-stu-id="ff4d4-139">This PSTN Usage overrides the PSTN Usages assigned to the user's voice policy, but applies only to calls placed to the Emergency Dial String or to one of the Emergency Dial String Masks.</span></span> 
  
 <span data-ttu-id="ff4d4-140">**URI de notificación**</span><span class="sxs-lookup"><span data-stu-id="ff4d4-140">**Notification URI**</span></span>
  
<span data-ttu-id="ff4d4-p111">Especifica los URI de SIP del personal de seguridad para que reciban una notificación por mensajería instantánea cuando se realice una llamada de emergencia. Se admiten los grupos de distribución.</span><span class="sxs-lookup"><span data-stu-id="ff4d4-p111">Specifies one or more SIP URIs of the security personnel who receive an instant messaging (IM) notification when an emergency call is placed. Distribution groups are supported.</span></span>
  
 <span data-ttu-id="ff4d4-143">**URI de conferencia**</span><span class="sxs-lookup"><span data-stu-id="ff4d4-143">**Conference URI**</span></span>
  
<span data-ttu-id="ff4d4-144">Especifica el número de llamada directa a la extensión (DID) (normalmente un número del departamento de seguridad) que debe incluirse en el modo de conferencia cuando se realiza una llamada de emergencia.</span><span class="sxs-lookup"><span data-stu-id="ff4d4-144">Specifies a direct inward dialing (DID) number (typically, a security desk number) that should be conferenced in when an emergency call is placed.</span></span> 
  
 <span data-ttu-id="ff4d4-145">**Modo de conferencia**</span><span class="sxs-lookup"><span data-stu-id="ff4d4-145">**Conference Mode**</span></span>
  
<span data-ttu-id="ff4d4-146">Especifica si el URI de conferencia se incluirá en la llamada de emergencia en modo conferencia mediante comunicación unidireccional o bidireccional.</span><span class="sxs-lookup"><span data-stu-id="ff4d4-146">Specifies if the conference URI will be conferenced into the emergency call by using one-way or two-way communication.</span></span> 
  
 <span data-ttu-id="ff4d4-147">**Intervalo de actualización de la ubicación**</span><span class="sxs-lookup"><span data-stu-id="ff4d4-147">**Location Refresh Interval**</span></span>
  
<span data-ttu-id="ff4d4-148">Especifica la cantidad de tiempo (en horas) entre las solicitudes de cliente para una actualización de ubicación desde el servicio de información de ubicación.</span><span class="sxs-lookup"><span data-stu-id="ff4d4-148">Specifies the amount of time (in hours) between client requests for a location update from the Location Information service.</span></span> <span data-ttu-id="ff4d4-149">El valor se puede definir en cualquier número incluido entre 1 y 12.</span><span class="sxs-lookup"><span data-stu-id="ff4d4-149">The value can be set to any value between 1 and 12.</span></span> <span data-ttu-id="ff4d4-150">El valor predeterminado es 4.</span><span class="sxs-lookup"><span data-stu-id="ff4d4-150">The default value is 4.</span></span>
