---
title: 'Lync Server 2013: definir la Directiva de ubicación'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining the location policy
ms:assetid: da3cca7f-f6e5-4b6f-90a1-2008e3dd1ebd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398962(v=OCS.15)
ms:contentKeyID: 48185553
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: feb7550412fa6cdcda3a8fc4dd9b7913912c34e1
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728360"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-the-location-policy-for-lync-server-2013"></a><span data-ttu-id="a2e4a-102">Definir la Directiva de ubicación de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a2e4a-102">Defining the location policy for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a2e4a-103">_**Última modificación del tema:** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="a2e4a-103">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="a2e4a-104">Cada directiva de ubicación contiene la información siguiente:</span><span class="sxs-lookup"><span data-stu-id="a2e4a-104">Each location policy contains the following information:</span></span>

  - <span data-ttu-id="a2e4a-105">**Servicios de emergencia habilitados**</span><span class="sxs-lookup"><span data-stu-id="a2e4a-105">**Emergency Services Enabled**</span></span>  
    <span data-ttu-id="a2e4a-106">Cuando este valor es **sí**, el cliente está habilitado para E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="a2e4a-106">When this value is **Yes**, the client is enabled for E9-1-1.</span></span> <span data-ttu-id="a2e4a-107">Cuando un cliente se registra, intenta adquirir una ubicación desde el servicio de información de ubicación e incluirá la información de ubicación como parte de una llamada de emergencia.</span><span class="sxs-lookup"><span data-stu-id="a2e4a-107">When a client registers, it attempts to acquire a location from the Location Information service and will include the location information as part of an emergency call.</span></span>

<!-- end list -->

  - <span data-ttu-id="a2e4a-108">**Ubicación requerida**</span><span class="sxs-lookup"><span data-stu-id="a2e4a-108">**Location Required**</span></span>  
    <span data-ttu-id="a2e4a-109">Esta configuración solo se usa cuando los **servicios de emergencia habilitados** están establecidos en **sí**.</span><span class="sxs-lookup"><span data-stu-id="a2e4a-109">This setting is used only when **Emergence Services Enabled** is set to **Yes**.</span></span>
    
    <span data-ttu-id="a2e4a-110">Puede configurar la configuración de **Ubicación requerida** para definir el comportamiento del cliente.</span><span class="sxs-lookup"><span data-stu-id="a2e4a-110">You can configure the **Location Required** setting to define the client behavior.</span></span> <span data-ttu-id="a2e4a-111">Si se define el valor en **No**, no se pedirá al usuario una ubicación.</span><span class="sxs-lookup"><span data-stu-id="a2e4a-111">Setting the value to **No** means that the user will not be prompted for a location.</span></span> <span data-ttu-id="a2e4a-112">Si se define en **Sí**, se pedirá al usuario una ubicación, pero este puede anular la solicitud.</span><span class="sxs-lookup"><span data-stu-id="a2e4a-112">Setting the value to **Yes** means that the user will be prompted for a location, but can dismiss the prompt.</span></span> <span data-ttu-id="a2e4a-113">Si se define en **Declinación de responsabilidades**, el usuario deberá especificar una ubicación y se le mostrará una declinación de responsabilidades si intenta anular la solicitud.</span><span class="sxs-lookup"><span data-stu-id="a2e4a-113">Setting the value to **Disclaimer** means that the user will be prompted for a location and also will be shown a disclaimer if they try to dismiss the prompt.</span></span> <span data-ttu-id="a2e4a-114">En todos los casos, el usuario puede seguir utilizando el cliente.</span><span class="sxs-lookup"><span data-stu-id="a2e4a-114">In all cases, the user can continue to use the client.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a2e4a-p103">El texto de declinación de responsabilidades no aparecerá si el usuario ha introducido manualmente una ubicación antes de ser habilitado para E9-1-1 y los usuarios que ya hayan visto la declinación de responsabilidades no recibirán las actualizaciones de dicho texto. </span><span class="sxs-lookup"><span data-stu-id="a2e4a-p103">The disclaimer text will not appear if a user manually entered a location before being enabled for E9-1-1. Updates to the disclaimer text will not be viewed by users that have already viewed the disclaimer.</span></span>

    
    </div>

<!-- end list -->

  - <span data-ttu-id="a2e4a-117">**Declinación de responsabilidades del servicio de emergencia mejorado**</span><span class="sxs-lookup"><span data-stu-id="a2e4a-117">**Enhanced Emergency Service Disclaimer**</span></span>  
    <span data-ttu-id="a2e4a-118">En esta configuración se especifica la declinación de responsabilidad que los usuarios ven si rechazan la solicitud de una ubicación.</span><span class="sxs-lookup"><span data-stu-id="a2e4a-118">This setting specifies the disclaimer that users see if they dismiss the prompt for a location.</span></span> <span data-ttu-id="a2e4a-119">En Lync Server 2013, puede usar la Directiva de ubicación para establecer distintas renuncias para diferentes configuraciones regionales o conjuntos de usuarios diferentes.</span><span class="sxs-lookup"><span data-stu-id="a2e4a-119">In Lync Server 2013, you can use location policy to set different disclaimers for different locales or different sets of users.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a2e4a-120">Esta configuración de directiva de ubicación difiere de Lync Server 2010, donde se usaba el cmdlet <STRONG>set-CsEnhancedEmergencyServiceDisclaimer</STRONG> para establecer un aviso de declinación de responsabilidades global para toda la organización.</span><span class="sxs-lookup"><span data-stu-id="a2e4a-120">This location policy setting differs from Lync Server 2010, where you used the <STRONG>Set-CsEnhancedEmergencyServiceDisclaimer</STRONG> cmdlet to set a global disclaimer for the entire organization.</span></span> <span data-ttu-id="a2e4a-121">Si ya existe un aviso de declinación de responsabilidades global, debe especificar esa renuncia en la Directiva de ubicación.</span><span class="sxs-lookup"><span data-stu-id="a2e4a-121">If a global disclaimer already exists, you need to specify that disclaimer in location policy.</span></span> <span data-ttu-id="a2e4a-122">Es decir, Lync Server 2013 solo usa descargos de responsabilidad especificados en la Directiva de ubicación.</span><span class="sxs-lookup"><span data-stu-id="a2e4a-122">That is, Lync Server 2013 uses only disclaimers specified in location policy.</span></span>

    
    </div>

<!-- end list -->

  - <span data-ttu-id="a2e4a-123">**Cadena de marcado de emergencia**</span><span class="sxs-lookup"><span data-stu-id="a2e4a-123">**Emergency Dial String**</span></span>  
    <span data-ttu-id="a2e4a-124">Esta cadena de marcado (menos el "+" inicial, pero incluida la normalización que realiza el plan de marcado del usuario de Lync) significa que una llamada es una llamada de emergencia.</span><span class="sxs-lookup"><span data-stu-id="a2e4a-124">This dial string (less the leading “+”, but including any normalization done by the Lync user’s Dial Plan) signifies that a call is an emergency call.</span></span> <span data-ttu-id="a2e4a-125">La **cadena de marcado de emergencia** implica que el cliente incluya la información de la devolución de llamadas y de la ubicación con la llamada.</span><span class="sxs-lookup"><span data-stu-id="a2e4a-125">The **Emergency Dial String** causes the client to include location and callback information with the call.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a2e4a-126">Si su organización no usa un prefijo de acceso de línea externa, no es necesario crear una regla de normalización de plan de marcado correspondiente que agregue un signo "+" a la cadena de 911 antes de enviar la llamada al enrutamiento de salida en un servidor de grupo de Lync. el cliente de Lync agrega automáticamente el prefijo "+" como resultado de la Directiva de ubicación.</span><span class="sxs-lookup"><span data-stu-id="a2e4a-126">If your organization does not use an external line access prefix, you do not need to create a corresponding Dial Plan normalization rule that adds a “+” to the 911 string prior to sending the call to Outbound Routing on a Lync pool server; the “+” will be automatically prepended by the Lync client as a result of the location policy.</span></span> <span data-ttu-id="a2e4a-127">Sin embargo, si su sitio utiliza un prefijo de acceso externo, debe agregar una regla de normalización a la directiva de plan de marcado correspondiente que quite el prefijo de acceso externo y agregue el signo “+”.</span><span class="sxs-lookup"><span data-stu-id="a2e4a-127">However, if your site uses an external access prefix, you need to add a normalization rule to the applicable Dial Plan policy that strips the external access prefix and adds the “+”.</span></span> <span data-ttu-id="a2e4a-128">Por ejemplo, si su ubicación usa un prefijo de acceso externo de 9 y un usuario marca&nbsp;9 911 para realizar una llamada de emergencia, el cliente usará su Directiva de plan de marcado para normalizarlo a + 911 antes de que el número marcado sea evaluado por las rutas en el perfil de ubicación de la persona que llama.</span><span class="sxs-lookup"><span data-stu-id="a2e4a-128">For example, if your location uses an external access prefix of 9 and a user dials 9&nbsp;911 to place an emergency call, the client will use its Dial Plan policy to normalize this to +911 before the dialed number is evaluated by the routes in the caller’s location profile.</span></span>

    
    </div>

<!-- end list -->

  - <span data-ttu-id="a2e4a-129">**Máscaras de cadena de marcado de emergencia**</span><span class="sxs-lookup"><span data-stu-id="a2e4a-129">**Emergency Dial String Masks**</span></span>  
    <span data-ttu-id="a2e4a-130">Lista separada por punto y coma de cadenas de marcado que se traduce en la **cadena de marcado de emergencia**especificada.</span><span class="sxs-lookup"><span data-stu-id="a2e4a-130">A semicolon-separated list of dial strings that is translated into the specified **Emergency Dial String**.</span></span> <span data-ttu-id="a2e4a-131">Por ejemplo, es posible que desee agregar 112, que es el número de servicio de emergencia de la mayor parte de Europa.</span><span class="sxs-lookup"><span data-stu-id="a2e4a-131">For example, you may want to add 112, which is the emergency service number for most of Europe.</span></span> <span data-ttu-id="a2e4a-132">Es posible que un usuario de Lync que visite Europa no sepa que 911 es el número de emergencia de Estados Unidos, pero sí puede marcar 112 y obtener el mismo resultado.</span><span class="sxs-lookup"><span data-stu-id="a2e4a-132">A visiting Lync user from Europe may not know that 911 is the U.S. emergency number, but they can dial 112 and get the same result.</span></span> <span data-ttu-id="a2e4a-133">Al igual que con la cadena de marcado de emergencia, no incluya un signo "+" antes de cada número y, si usa códigos de acceso de línea externa, asegúrese de que existen reglas de normalización en la Directiva del plan de marcado del usuario para quitar el dígito de código de acceso.</span><span class="sxs-lookup"><span data-stu-id="a2e4a-133">As with the Emergency Dial String, do not include a “+” before each number, and if you use external line access codes, be sure there are normalization rules in the user’s Dial Plan policy to strip off the access code digit.</span></span>

<!-- end list -->

  - <span data-ttu-id="a2e4a-134">**Uso de RTC**</span><span class="sxs-lookup"><span data-stu-id="a2e4a-134">**PSTN Usage**</span></span>  
    <span data-ttu-id="a2e4a-135">El nombre del uso de RTC que contiene las rutas de acceso de enrutamiento que determinan a qué tronco SIP, a qué puerta de enlace RTC o a qué puerta de enlace ELIN se dirigen las llamadas de emergencia.</span><span class="sxs-lookup"><span data-stu-id="a2e4a-135">The name of the PSTN Usage that contains the routing paths that determine which SIP trunk, PSTN gateway, or ELIN gateway emergency calls will go to.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a2e4a-p109">Solo se puede asignar un uso a una directiva de ubicación. Este uso de RTC reemplaza los usos de RTC asignados a la directiva de voz del usuario, pero solo se aplica a llamadas realizadas a la cadena de marcado de emergencia o a una de las máscaras de la cadena de marcado de emergencia.</span><span class="sxs-lookup"><span data-stu-id="a2e4a-p109">Only one usage can be assigned to a location policy. This PSTN Usage overrides the PSTN Usages assigned to the user’s voice policy, but applies only to calls placed to the Emergency Dial String or to one of the Emergency Dial String Masks.</span></span>

    
    </div>

<!-- end list -->

  - <span data-ttu-id="a2e4a-138">**URI de notificación**</span><span class="sxs-lookup"><span data-stu-id="a2e4a-138">**Notification URI**</span></span>  
    <span data-ttu-id="a2e4a-p110">Especifica los URI de SIP del personal de seguridad para que reciban una notificación por mensajería instantánea cuando se realice una llamada de emergencia. Se admiten los grupos de distribución.</span><span class="sxs-lookup"><span data-stu-id="a2e4a-p110">Specifies one or more SIP URIs of the security personnel who receive an instant messaging (IM) notification when an emergency call is placed. Distribution groups are supported.</span></span>

<!-- end list -->

  - <span data-ttu-id="a2e4a-141">**URI de conferencia**</span><span class="sxs-lookup"><span data-stu-id="a2e4a-141">**Conference URI**</span></span>  
    <span data-ttu-id="a2e4a-142">Especifica el número de llamada directa a la extensión (DID) (normalmente un número del servicio de seguridad) que necesita incluirse en el modo de conferencia cuando se realiza una llamada de emergencia.  </span><span class="sxs-lookup"><span data-stu-id="a2e4a-142">Specifies a direct inward dialing (DID) number (typically, a security desk number) that should be conferenced in when an emergency call is placed.</span></span>

<!-- end list -->

  - <span data-ttu-id="a2e4a-143">**Modo de conferencia**</span><span class="sxs-lookup"><span data-stu-id="a2e4a-143">**Conference Mode**</span></span>  
    <span data-ttu-id="a2e4a-144">Especifica si el URI de conferencia se incluirá en la llamada de emergencia en modo de conferencia a través de una comunicación unidireccional o bidireccional. </span><span class="sxs-lookup"><span data-stu-id="a2e4a-144">Specifies if the conference URI will be conferenced into the emergency call by using one-way or two-way communication.</span></span>

<!-- end list -->

  - <span data-ttu-id="a2e4a-145">**Intervalo de actualización de la ubicación**</span><span class="sxs-lookup"><span data-stu-id="a2e4a-145">**Location Refresh Interval**</span></span>  
    <span data-ttu-id="a2e4a-146">Especifica la cantidad de tiempo (en horas) entre las solicitudes de un cliente para una actualización de ubicación desde el servicio de información de ubicación.</span><span class="sxs-lookup"><span data-stu-id="a2e4a-146">Specifies the amount of time (in hours) between client requests for a location update from the Location Information service.</span></span> <span data-ttu-id="a2e4a-147">El valor puede ser cualquier número entre 1 y 12.</span><span class="sxs-lookup"><span data-stu-id="a2e4a-147">The value can be set to any value between 1 and 12.</span></span> <span data-ttu-id="a2e4a-148">El valor predeterminado es 4.</span><span class="sxs-lookup"><span data-stu-id="a2e4a-148">The default value is 4.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

