---
title: Planificar directivas de ubicación para Skype Empresarial Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/17/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: da3cca7f-f6e5-4b6f-90a1-2008e3dd1ebd
description: Lea este tema para aprender a planear las políticas de ubicación para una implementación de los servicios de emergencia mejorada (E9-1-1) en Skype para Telefonía IP empresarial de Business Server.
ms.openlocfilehash: 246a4bcddece986d9488c5e2bccbbece5f1a2cc9
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="plan-location-policies-for-skype-for-business-server-2015"></a><span data-ttu-id="76c23-103">Planificar directivas de ubicación para Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="76c23-103">Plan location policies for Skype for Business Server 2015</span></span>
 
<span data-ttu-id="76c23-104">Lea este tema para aprender a planear las políticas de ubicación para una implementación de los servicios de emergencia mejorada (E9-1-1) en Skype para Telefonía IP empresarial de Business Server.</span><span class="sxs-lookup"><span data-stu-id="76c23-104">Read this topic to learn how to plan location policies for an enhanced emergency services (E9-1-1) deployment in Skype for Business Server Enterprise Voice.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="76c23-105">Skype para Business Server ahora admite la configuración de varios números de emergencia para un cliente.</span><span class="sxs-lookup"><span data-stu-id="76c23-105">Skype for Business Server now supports the configuration of multiple emergency numbers for a client.</span></span> <span data-ttu-id="76c23-106">Si desea configurar varios números de emergencia, debe seguir la información en el [Plan para varios números de emergencia en Skype para Business Server 2015](multiple-emergency-numbers.md) y [configurar varios números de emergencia en Skype para negocios 2015](../../deploy/deploy-enterprise-voice/configure-multiple-emergency-numbers.md).</span><span class="sxs-lookup"><span data-stu-id="76c23-106">If you want to configure multiple emergency numbers, you must follow the information in [Plan for multiple emergency numbers in Skype for Business Server 2015](multiple-emergency-numbers.md) and [Configure multiple emergency numbers in Skype for Business 2015](../../deploy/deploy-enterprise-voice/configure-multiple-emergency-numbers.md).</span></span> 
  
<span data-ttu-id="76c23-107">Puede crear directivas de ubicación utilizando el Skype para el Panel de Control del negocio o mediante el cmdlet [New-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="76c23-107">You create location policies by using the Skype for Business Control Panel or by using the [New-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps) cmdlet.</span></span> <span data-ttu-id="76c23-108">Para obtener más información, vea [crear directivas de ubicación en Skype para Business Server 2015](../../deploy/deploy-enterprise-voice/create-location-policies.md).</span><span class="sxs-lookup"><span data-stu-id="76c23-108">For more information, see [Create location policies in Skype for Business Server 2015](../../deploy/deploy-enterprise-voice/create-location-policies.md).</span></span>
  
<span data-ttu-id="76c23-109">Cada directiva de ubicación contiene la información siguiente:</span><span class="sxs-lookup"><span data-stu-id="76c23-109">Each location policy contains the following information:</span></span>
  
 <span data-ttu-id="76c23-110">**Habilitar 9-1-1 mejorado**</span><span class="sxs-lookup"><span data-stu-id="76c23-110">**Enable Enhanced 9-1-1**</span></span>
  
<span data-ttu-id="76c23-111">Si este valor se habilita, se habilita también al cliente para los servicios de emergencia mejorados (E9-1-1).</span><span class="sxs-lookup"><span data-stu-id="76c23-111">When this value is enabled, the client is enabled for enhanced emergency services (E9-1-1).</span></span> <span data-ttu-id="76c23-112">Cuando un cliente se registra, intenta adquirir una ubicación desde el servicio de información de ubicación e incluirá la información de ubicación como parte de una llamada de emergencia.</span><span class="sxs-lookup"><span data-stu-id="76c23-112">When a client registers, it attempts to acquire a location from the Location Information service and will include the location information as part of an emergency call.</span></span>
  
 <span data-ttu-id="76c23-113">**Ubicación**</span><span class="sxs-lookup"><span data-stu-id="76c23-113">**Location**</span></span>
  
<span data-ttu-id="76c23-114">Esta opción sólo se utiliza cuando se habilita **Habilitar Enhanced 9-1-1** .</span><span class="sxs-lookup"><span data-stu-id="76c23-114">This setting is used only when **Enable Enhanced 9-1-1** is enabled.</span></span>
  
<span data-ttu-id="76c23-115">Puede configurar **Ubicación** para definir el comportamiento del cliente de la siguiente manera:   </span><span class="sxs-lookup"><span data-stu-id="76c23-115">You can configure the **Location** setting to define the client behavior as follows:</span></span>
  
- <span data-ttu-id="76c23-116">Si se define el valor en **No**, no se pedirá al usuario una ubicación.</span><span class="sxs-lookup"><span data-stu-id="76c23-116">Setting the value to **No** means that the user will not be prompted for a location.</span></span>
    
- <span data-ttu-id="76c23-117">Si se define en **Sí**, se pedirá al usuario una ubicación, pero este puede anular la solicitud.</span><span class="sxs-lookup"><span data-stu-id="76c23-117">Setting the value to **Yes** means that the user will be prompted for a location, but can dismiss the prompt.</span></span>
    
- <span data-ttu-id="76c23-p104">Si se define en **Declinación de responsabilidades**, el usuario deberá especificar una ubicación y se le mostrará una declinación de responsabilidades si intenta anular la solicitud. En todos los casos, el usuario puede seguir utilizando el cliente.</span><span class="sxs-lookup"><span data-stu-id="76c23-p104">Setting the value to **Disclaimer** means that the user will be prompted for a location and also will be shown a disclaimer if they try to dismiss the prompt. In all cases, the user can continue to use the client.</span></span>
    
> [!NOTE]
> <span data-ttu-id="76c23-p105">El texto de declinación de responsabilidades no aparecerá si el usuario ha introducido manualmente una ubicación antes de ser habilitado para E9-1-1 y los usuarios que ya hayan visto la declinación de responsabilidades no recibirán las actualizaciones de dicho texto. </span><span class="sxs-lookup"><span data-stu-id="76c23-p105">The disclaimer text will not appear if a user manually entered a location before being enabled for E9-1-1. Updates to the disclaimer text will not be viewed by users that have already viewed the disclaimer.</span></span> 
  
 <span data-ttu-id="76c23-122">**Declinación de responsabilidades del servicio de emergencia mejorado**</span><span class="sxs-lookup"><span data-stu-id="76c23-122">**Enhanced Emergency Service Disclaimer**</span></span>
  
<span data-ttu-id="76c23-123">En esta configuración se especifica la declinación de responsabilidad que los usuarios ven si rechazan la solicitud de una ubicación.</span><span class="sxs-lookup"><span data-stu-id="76c23-123">This setting specifies the disclaimer that users see if they dismiss the prompt for a location.</span></span> <span data-ttu-id="76c23-124">En Skype para Business Server, puede utilizar Directiva de ubicación para establecer renuncias diferentes para distintas configuraciones regionales o conjuntos de usuarios diferentes.</span><span class="sxs-lookup"><span data-stu-id="76c23-124">In Skype for Business Server, you can use location policy to set different disclaimers for different locales or different sets of users.</span></span>
  
 <span data-ttu-id="76c23-125">**Cadena de marcado de emergencia (número de marcado de E9-1-1)**</span><span class="sxs-lookup"><span data-stu-id="76c23-125">**Emergency Dial String (E9-1-1 dial number)**</span></span>
  
<span data-ttu-id="76c23-126">Esta cadena de marcado (menos el interlineado "+", pero incluyendo ninguna normalización realizada por Dial Plan el usuario) significa que la llamada es una llamada de emergencia.</span><span class="sxs-lookup"><span data-stu-id="76c23-126">This dial string (less the leading "+", but including any normalization done by the user's Dial Plan) signifies that a call is an emergency call.</span></span> <span data-ttu-id="76c23-127">La **cadena de marcado de emergencia** implica que el cliente incluya la información de la devolución de llamadas y de la ubicación con la llamada.</span><span class="sxs-lookup"><span data-stu-id="76c23-127">The **Emergency Dial String** causes the client to include location and callback information with the call.</span></span>
  
> [!NOTE]
> <span data-ttu-id="76c23-128">Si su organización no utiliza un prefijo de acceso a línea externa, no necesitará crear regla de normalización correspondiente Plan de marcado que agrega un signo "+" en la cadena 911 antes de enviar la llamada al enrutamiento de salida en un servidor que ejecuta Skype para Business Server; la voluntad de "+" se antepone automáticamente por el Skype para cliente de negocios como consecuencia de la política de ubicación.</span><span class="sxs-lookup"><span data-stu-id="76c23-128">If your organization does not use an external line access prefix, you do not need to create a corresponding Dial Plan normalization rule that adds a "+" to the 911 string prior to sending the call to Outbound Routing on a server running Skype for Business Server; the "+" will be automatically prepended by the Skype for Business client as a result of the location policy.</span></span> <span data-ttu-id="76c23-129">Sin embargo, si su sitio utiliza un prefijo de acceso externo, necesita agregar una regla de normalización a la directiva aplicable Dial Plan que elimina el prefijo de acceso externo y se agrega la "+".</span><span class="sxs-lookup"><span data-stu-id="76c23-129">However, if your site uses an external access prefix, you need to add a normalization rule to the applicable Dial Plan policy that strips the external access prefix and adds the "+".</span></span> <span data-ttu-id="76c23-130">Por ejemplo, si su ubicación utiliza un prefijo de acceso externo de 9 y un usuario marca 9 911 para realizar una llamada de emergencia, el cliente utilizará su directiva Plan de acceso telefónico para normalizar esto a +911 antes de la se evalúa el número marcado por las rutas de perfil de la ubicación del llamador.</span><span class="sxs-lookup"><span data-stu-id="76c23-130">For example, if your location uses an external access prefix of 9 and a user dials 9 911 to place an emergency call, the client will use its Dial Plan policy to normalize this to +911 before the the dialed number is evaluated by the routes in the caller's location profile.</span></span> 
  
 <span data-ttu-id="76c23-131">**Máscaras de cadena de marcado de emergencia (número de marcado de E9-1-1)**</span><span class="sxs-lookup"><span data-stu-id="76c23-131">**Emergency Dial String Masks (E9-1-1 dial mask)**</span></span>
  
<span data-ttu-id="76c23-132">Una separados por punto y coma lista de cadenas de marcado que se traduce en la **Cadena de marcado de emergencia**de especificada.</span><span class="sxs-lookup"><span data-stu-id="76c23-132">A semicolon-separated list of dial strings that is translated into the specified **Emergency Dial String**.</span></span> <span data-ttu-id="76c23-133">Por ejemplo, es aconsejable agregar 112, que es el número de servicio de emergencia para la mayor parte de Europa.</span><span class="sxs-lookup"><span data-stu-id="76c23-133">For example, you may want to add 112, which is the emergency service number for most of Europe.</span></span> <span data-ttu-id="76c23-134">Un visitante Skype para usuarios de empresa en Europa puede desconocer 911 es el número de emergencia de Estados Unidos, pero pueden marcar 112 y obtener el mismo resultado.</span><span class="sxs-lookup"><span data-stu-id="76c23-134">A visiting Skype for Business user from Europe may not know that 911 is the U.S. emergency number, but they can dial 112 and get the same result.</span></span> <span data-ttu-id="76c23-135">Como con la cadena de marcado de emergencia, no incluya un signo "+" antes de cada número, y si usa códigos de acceso a línea externa, asegúrese de que hay reglas de normalización en la directiva del usuario Dial Plan quitar los dígitos del código de acceso.</span><span class="sxs-lookup"><span data-stu-id="76c23-135">As with the Emergency Dial String, do not include a "+" before each number, and if you use external line access codes, be sure there are normalization rules in the user's Dial Plan policy to strip off the access code digit.</span></span>
  
 <span data-ttu-id="76c23-136">**Uso de RTC**</span><span class="sxs-lookup"><span data-stu-id="76c23-136">**PSTN usage**</span></span>
  
<span data-ttu-id="76c23-137">El nombre del uso de RTC que contiene las rutas de acceso de enrutamiento que determinan a qué tronco SIP, a qué puerta de enlace RTC o a qué puerta de enlace ELIN se dirigen las llamadas de emergencia.</span><span class="sxs-lookup"><span data-stu-id="76c23-137">The name of the PSTN Usage that contains the routing paths that determine which SIP trunk, PSTN gateway, or ELIN gateway emergency calls will go to.</span></span>
  
> [!NOTE]
> <span data-ttu-id="76c23-138">Solo se puede asignar un uso a una directiva de ubicación.</span><span class="sxs-lookup"><span data-stu-id="76c23-138">Only one usage can be assigned to a location policy.</span></span> <span data-ttu-id="76c23-139">Este uso de PSTN reemplaza los usos PSTN asignada a una directiva de voz del usuario, pero sólo se aplica a las llamadas efectuadas a la cadena de marcado de emergencia o a una de las máscaras de cadena de marcado de emergencia.</span><span class="sxs-lookup"><span data-stu-id="76c23-139">This PSTN Usage overrides the PSTN Usages assigned to the user's voice policy, but applies only to calls placed to the Emergency Dial String or to one of the Emergency Dial String Masks.</span></span> 
  
 <span data-ttu-id="76c23-140">**URI de notificación**</span><span class="sxs-lookup"><span data-stu-id="76c23-140">**Notification URI**</span></span>
  
<span data-ttu-id="76c23-p111">Especifica los URI de SIP del personal de seguridad para que reciban una notificación por mensajería instantánea cuando se realice una llamada de emergencia. Se admiten los grupos de distribución.</span><span class="sxs-lookup"><span data-stu-id="76c23-p111">Specifies one or more SIP URIs of the security personnel who receive an instant messaging (IM) notification when an emergency call is placed. Distribution groups are supported.</span></span>
  
 <span data-ttu-id="76c23-143">**URI de conferencia**</span><span class="sxs-lookup"><span data-stu-id="76c23-143">**Conference URI**</span></span>
  
<span data-ttu-id="76c23-144">Especifica el número de llamada directa a la extensión (DID) (normalmente un número del servicio de seguridad) que necesita incluirse en el modo de conferencia cuando se realiza una llamada de emergencia.  </span><span class="sxs-lookup"><span data-stu-id="76c23-144">Specifies a direct inward dialing (DID) number (typically, a security desk number) that should be conferenced in when an emergency call is placed.</span></span> 
  
 <span data-ttu-id="76c23-145">**Modo de conferencia**</span><span class="sxs-lookup"><span data-stu-id="76c23-145">**Conference Mode**</span></span>
  
<span data-ttu-id="76c23-146">Especifica si el URI de conferencia se incluirá en la llamada de emergencia en modo de conferencia a través de una comunicación unidireccional o bidireccional. </span><span class="sxs-lookup"><span data-stu-id="76c23-146">Specifies if the conference URI will be conferenced into the emergency call by using one-way or two-way communication.</span></span> 
  
 <span data-ttu-id="76c23-147">**Intervalo de actualización de la ubicación**</span><span class="sxs-lookup"><span data-stu-id="76c23-147">**Location Refresh Interval**</span></span>
  
<span data-ttu-id="76c23-148">Especifica la cantidad de tiempo (en horas) entre las solicitudes del cliente para una actualización de la ubicación del servicio de información de la ubicación.</span><span class="sxs-lookup"><span data-stu-id="76c23-148">Specifies the amount of time (in hours) between client requests for a location update from the Location Information service.</span></span> <span data-ttu-id="76c23-149">El valor puede ser cualquier número entre 1 y 12.</span><span class="sxs-lookup"><span data-stu-id="76c23-149">The value can be set to any value between 1 and 12.</span></span> <span data-ttu-id="76c23-150">El valor predeterminado es 4.</span><span class="sxs-lookup"><span data-stu-id="76c23-150">The default value is 4.</span></span>
  

