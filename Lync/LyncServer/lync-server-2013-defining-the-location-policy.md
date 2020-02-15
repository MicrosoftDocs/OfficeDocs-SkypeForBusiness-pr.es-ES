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
ms.openlocfilehash: 9842b5bec4b635566288998d6e8110fcc51463d7
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42048203"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-the-location-policy-for-lync-server-2013"></a><span data-ttu-id="bebce-102">Definición de la Directiva de ubicación para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bebce-102">Defining the location policy for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bebce-103">_**Última modificación del tema:** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="bebce-103">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="bebce-104">Cada directiva de ubicación contiene la información siguiente:</span><span class="sxs-lookup"><span data-stu-id="bebce-104">Each location policy contains the following information:</span></span>

  - <span data-ttu-id="bebce-105">**Servicios de emergencia habilitados**</span><span class="sxs-lookup"><span data-stu-id="bebce-105">**Emergency Services Enabled**</span></span>  
    <span data-ttu-id="bebce-106">Si se define en **Sí**, se habilita al cliente para E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="bebce-106">When this value is **Yes**, the client is enabled for E9-1-1.</span></span> <span data-ttu-id="bebce-107">Cuando un cliente se registra, intenta adquirir una ubicación del servicio de información de ubicación e incluye la información de ubicación como parte de una llamada de emergencia.</span><span class="sxs-lookup"><span data-stu-id="bebce-107">When a client registers, it attempts to acquire a location from the Location Information service and will include the location information as part of an emergency call.</span></span>

<!-- end list -->

  - <span data-ttu-id="bebce-108">**Ubicación obligatoria**</span><span class="sxs-lookup"><span data-stu-id="bebce-108">**Location Required**</span></span>  
    <span data-ttu-id="bebce-109">Esta configuración solo se usa cuando los **servicios de emergencia habilitados** están establecidos en **sí**.</span><span class="sxs-lookup"><span data-stu-id="bebce-109">This setting is used only when **Emergence Services Enabled** is set to **Yes**.</span></span>
    
    <span data-ttu-id="bebce-p102">Configure el parámetro de **Ubicación obligatoria** para definir el comportamiento del cliente. Si se define el valor en **No**, no se pedirá al usuario una ubicación. Si se define en **Sí**, se pedirá al usuario una ubicación, pero este puede anular la solicitud. Si se define en **Declinación de responsabilidades**, el usuario deberá especificar una ubicación y no podrá anular la solicitud hasta que haya introducido una solicitud. En ambos casos el usuario puede continuar usando el cliente.</span><span class="sxs-lookup"><span data-stu-id="bebce-p102">You can configure the **Location Required** setting to define the client behavior. Setting the value to **No** means that the user will not be prompted for a location. Setting the value to **Yes** means that the user will be prompted for a location, but can dismiss the prompt. Setting the value to **Disclaimer** means that the user will be prompted for a location and also will be shown a disclaimer if they try to dismiss the prompt. In all cases, the user can continue to use the client.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="bebce-p103">El texto de declinación de responsabilidades no aparecerá si el usuario ha introducido manualmente una ubicación antes de ser habilitado para E9-1-1 y los usuarios que ya hayan visto la declinación de responsabilidades no recibirán las actualizaciones de dicho texto.</span><span class="sxs-lookup"><span data-stu-id="bebce-p103">The disclaimer text will not appear if a user manually entered a location before being enabled for E9-1-1. Updates to the disclaimer text will not be viewed by users that have already viewed the disclaimer.</span></span>

    
    </div>

<!-- end list -->

  - <span data-ttu-id="bebce-117">**Declinación de responsabilidad de servicio de emergencia mejorado**</span><span class="sxs-lookup"><span data-stu-id="bebce-117">**Enhanced Emergency Service Disclaimer**</span></span>  
    <span data-ttu-id="bebce-118">En esta configuración se especifica la declinación de responsabilidad que los usuarios ven si rechazan la solicitud de una ubicación.</span><span class="sxs-lookup"><span data-stu-id="bebce-118">This setting specifies the disclaimer that users see if they dismiss the prompt for a location.</span></span> <span data-ttu-id="bebce-119">En Lync Server 2013, puede usar la Directiva de ubicación para establecer diferentes avisos de declinación de responsabilidad para diferentes configuraciones regionales o conjuntos de usuarios diferentes.</span><span class="sxs-lookup"><span data-stu-id="bebce-119">In Lync Server 2013, you can use location policy to set different disclaimers for different locales or different sets of users.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="bebce-120">Esta configuración de directiva difiere de Lync Server 2010, donde se usa el cmdlet <STRONG>set-CsEnhancedEmergencyServiceDisclaimer</STRONG> para establecer una declinación de responsabilidades global para toda la organización.</span><span class="sxs-lookup"><span data-stu-id="bebce-120">This location policy setting differs from Lync Server 2010, where you used the <STRONG>Set-CsEnhancedEmergencyServiceDisclaimer</STRONG> cmdlet to set a global disclaimer for the entire organization.</span></span> <span data-ttu-id="bebce-121">Si ya existe una declinación de responsabilidad global, especifique la declinación de responsabilidad en la directiva de ubicación.</span><span class="sxs-lookup"><span data-stu-id="bebce-121">If a global disclaimer already exists, you need to specify that disclaimer in location policy.</span></span> <span data-ttu-id="bebce-122">Es decir, Lync Server 2013 solo usa avisos de declinación de responsabilidad especificados en la Directiva de ubicación.</span><span class="sxs-lookup"><span data-stu-id="bebce-122">That is, Lync Server 2013 uses only disclaimers specified in location policy.</span></span>

    
    </div>

<!-- end list -->

  - <span data-ttu-id="bebce-123">**Cadena de marcado de emergencia**</span><span class="sxs-lookup"><span data-stu-id="bebce-123">**Emergency Dial String**</span></span>  
    <span data-ttu-id="bebce-p106">La cadena de marcado que indica que la llamada en cuestión es una llamada de emergencia. La **cadena de marcado de emergencia** comporta la adición a la llamada de información de ubicación y devolución de llamada por parte del cliente.</span><span class="sxs-lookup"><span data-stu-id="bebce-p106">This dial string (less the leading “+”, but including any normalization done by the Lync user’s Dial Plan) signifies that a call is an emergency call. The **Emergency Dial String** causes the client to include location and callback information with the call.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="bebce-126">Si su organización no utiliza un prefijo de acceso de línea externo, no tendrá que crear una regla de normalización de planes de marcado correspondiente que añada un signo “+” a la cadena 911 antes de enviar la llamada al enrutamiento de salida en el servidor de grupo de Lync; el signo “+” se agregará automáticamente por parte del cliente de Lync como resultado de la directiva de ubicación.</span><span class="sxs-lookup"><span data-stu-id="bebce-126">If your organization does not use an external line access prefix, you do not need to create a corresponding Dial Plan normalization rule that adds a “+” to the 911 string prior to sending the call to Outbound Routing on a Lync pool server; the “+” will be automatically prepended by the Lync client as a result of the location policy.</span></span> <span data-ttu-id="bebce-127">Sin embargo, si su sitio utiliza un prefijo de acceso externo, agregue una regla de normalización a la directiva de plan de marcado aplicable que quite el prefijo de acceso externo y agregue el signo “+”.</span><span class="sxs-lookup"><span data-stu-id="bebce-127">However, if your site uses an external access prefix, you need to add a normalization rule to the applicable Dial Plan policy that strips the external access prefix and adds the “+”.</span></span> <span data-ttu-id="bebce-128">Por ejemplo, si su ubicación usa un prefijo de acceso externo de 9 y un usuario marca&nbsp;9 911 para realizar una llamada de emergencia, el cliente usará su Directiva de plan de marcado para normalizarlo a + 911 antes de que las rutas del perfil de ubicación del autor de la llamada evalúen el número marcado.</span><span class="sxs-lookup"><span data-stu-id="bebce-128">For example, if your location uses an external access prefix of 9 and a user dials 9&nbsp;911 to place an emergency call, the client will use its Dial Plan policy to normalize this to +911 before the dialed number is evaluated by the routes in the caller’s location profile.</span></span>

    
    </div>

<!-- end list -->

  - <span data-ttu-id="bebce-129">**Máscaras de cadena de marcado de emergencia**</span><span class="sxs-lookup"><span data-stu-id="bebce-129">**Emergency Dial String Masks**</span></span>  
    <span data-ttu-id="bebce-p108">Una lista de cadenas de marcado separadas por caracteres de punto y coma que deben convertirse a la **cadena de marcado de emergencia** especificada. Por ejemplo, es posible que desee agregar 112, que es el número del servicio de emergencia para la mayor parte de Europa. Un usuario de Lync visitante proveniente de Europa puede que no sepa que el 911 es el número de emergencia en los Estados Unidos, pero puede marcar el 112 y obtener el mismo resultado. Al igual que con la cadena de marcado de emergencia, no incluya un signo “+” antes de cada número y, si utiliza códigos de acceso de línea externa, asegúrese de que existen reglas de normalización en la directiva del plan de marcado de los usuarios para quitar el dígito del código de acceso.</span><span class="sxs-lookup"><span data-stu-id="bebce-p108">A semicolon-separated list of dial strings that is translated into the specified **Emergency Dial String**. For example, you may want to add 112, which is the emergency service number for most of Europe. A visiting Lync user from Europe may not know that 911 is the U.S. emergency number, but they can dial 112 and get the same result. As with the Emergency Dial String, do not include a “+” before each number, and if you use external line access codes, be sure there are normalization rules in the user’s Dial Plan policy to strip off the access code digit.</span></span>

<!-- end list -->

  - <span data-ttu-id="bebce-134">**Uso de RTC**</span><span class="sxs-lookup"><span data-stu-id="bebce-134">**PSTN Usage**</span></span>  
    <span data-ttu-id="bebce-135">El nombre del uso de RTC que contiene las rutas de acceso que determinan en qué tronco SIP o puerta de enlace RTC se realizarán las llamadas de emergencia.</span><span class="sxs-lookup"><span data-stu-id="bebce-135">The name of the PSTN Usage that contains the routing paths that determine which SIP trunk, PSTN gateway, or ELIN gateway emergency calls will go to.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="bebce-p109">Solo se puede asignar un uso a una directiva de ubicación. Este uso de RTC reemplaza los usos de RTC asignados a la directiva de voz del usuario, pero solo se aplica a llamadas realizadas a la cadena de marcado de emergencia o a una de las máscaras de la cadena de marcado de emergencia.</span><span class="sxs-lookup"><span data-stu-id="bebce-p109">Only one usage can be assigned to a location policy. This PSTN Usage overrides the PSTN Usages assigned to the user’s voice policy, but applies only to calls placed to the Emergency Dial String or to one of the Emergency Dial String Masks.</span></span>

    
    </div>

<!-- end list -->

  - <span data-ttu-id="bebce-138">**URI de notificación**</span><span class="sxs-lookup"><span data-stu-id="bebce-138">**Notification URI**</span></span>  
    <span data-ttu-id="bebce-p110">Especifica los URI de SIP del personal de seguridad para que reciban una notificación por mensajería instantánea cuando se realice una llamada de emergencia. Se admiten los grupos de distribución.</span><span class="sxs-lookup"><span data-stu-id="bebce-p110">Specifies one or more SIP URIs of the security personnel who receive an instant messaging (IM) notification when an emergency call is placed. Distribution groups are supported.</span></span>

<!-- end list -->

  - <span data-ttu-id="bebce-141">**URI de conferencia**</span><span class="sxs-lookup"><span data-stu-id="bebce-141">**Conference URI**</span></span>  
    <span data-ttu-id="bebce-142">Especifica el número de llamada directa a la extensión (DID) (normalmente un número del departamento de seguridad) que debe incluirse en el modo de conferencia cuando se realiza una llamada de emergencia.</span><span class="sxs-lookup"><span data-stu-id="bebce-142">Specifies a direct inward dialing (DID) number (typically, a security desk number) that should be conferenced in when an emergency call is placed.</span></span>

<!-- end list -->

  - <span data-ttu-id="bebce-143">**Modo de conferencia**</span><span class="sxs-lookup"><span data-stu-id="bebce-143">**Conference Mode**</span></span>  
    <span data-ttu-id="bebce-144">Especifica si el URI de conferencia se incluirá en la llamada de emergencia en modo conferencia mediante comunicación unidireccional o bidireccional.</span><span class="sxs-lookup"><span data-stu-id="bebce-144">Specifies if the conference URI will be conferenced into the emergency call by using one-way or two-way communication.</span></span>

<!-- end list -->

  - <span data-ttu-id="bebce-145">**Intervalo de actualización de la ubicación**</span><span class="sxs-lookup"><span data-stu-id="bebce-145">**Location Refresh Interval**</span></span>  
    <span data-ttu-id="bebce-146">Especifica la cantidad de tiempo (en horas) entre las solicitudes de cliente para una actualización de ubicación desde el servicio de información de ubicación.</span><span class="sxs-lookup"><span data-stu-id="bebce-146">Specifies the amount of time (in hours) between client requests for a location update from the Location Information service.</span></span> <span data-ttu-id="bebce-147">El valor se puede definir en cualquier número incluido entre 1 y 12.</span><span class="sxs-lookup"><span data-stu-id="bebce-147">The value can be set to any value between 1 and 12.</span></span> <span data-ttu-id="bebce-148">El valor predeterminado es 4.</span><span class="sxs-lookup"><span data-stu-id="bebce-148">The default value is 4.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

