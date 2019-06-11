---
title: 'Lync Server 2013: Administración de objetos de contactos de Hosted Exchange'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Hosted Exchange Contact object management
ms:assetid: eead9d76-bc4f-4c1c-9779-683cb7a88410
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412978(v=OCS.15)
ms:contentKeyID: 48185748
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c67438745ee7cbb9de0ccfdef1d5d8959bb4679c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34835061"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="hosted-exchange-contact-object-management-in-lync-server-2013"></a><span data-ttu-id="4ffb3-102">Administración de objetos de contactos de Hosted Exchange en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4ffb3-102">Hosted Exchange Contact object management in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4ffb3-103">_**Última modificación del tema:** 2012-09-25_</span><span class="sxs-lookup"><span data-stu-id="4ffb3-103">_**Topic Last Modified:** 2012-09-25_</span></span>

<span data-ttu-id="4ffb3-104">Debe configurar un objeto de contacto para cada número de acceso de número de operador automático y de suscriptor en la implementación entre locales.</span><span class="sxs-lookup"><span data-stu-id="4ffb3-104">You need to configure a Contact object for each auto-attendant number and subscriber access number in your cross-premises deployment.</span></span>

<span data-ttu-id="4ffb3-105">Para la integración con la mensajería unificada de Exchange hospedada, OCSUMUtil. exe no se puede usar para administrar objetos de contacto, porque depende de la configuración de MU de Exchange Active Directory.</span><span class="sxs-lookup"><span data-stu-id="4ffb3-105">For integration with hosted Exchange UM, ocsumutil.exe cannot be used to manage Contact objects, because it depends on Active Directory Exchange UM settings.</span></span> <span data-ttu-id="4ffb3-106">En una implementación entre instalaciones, Lync Server 2013 y mensajería unificada de Exchange hospedado se instalan en bosques independientes sin confianza entre ellos.</span><span class="sxs-lookup"><span data-stu-id="4ffb3-106">In a cross-premises deployment, Lync Server 2013 and hosted Exchange UM are installed in separate forests with no trust between them.</span></span> <span data-ttu-id="4ffb3-107">Por razones de seguridad, los administradores de Lync Server 2013 no tienen acceso directo a la configuración de Active Directory de mensajería unificada de Exchange.</span><span class="sxs-lookup"><span data-stu-id="4ffb3-107">For security reasons, Lync Server 2013 administrators have no direct access to Exchange UM Active Directory settings.</span></span> <span data-ttu-id="4ffb3-108">Como resultado, Lync Server 2013 proporciona un modelo diferente para administrar los objetos de contacto en un *espacio de direcciones SIP compartido* que sea accesible tanto para Lync Server 2013 como para el servicio hospedado de mensajería unificada de Exchange.</span><span class="sxs-lookup"><span data-stu-id="4ffb3-108">As a result, Lync Server 2013 provides a different model for managing Contact objects in a *shared SIP address space* that is accessible to both Lync Server 2013 and the hosted Exchange UM service.</span></span>

<div>

## <a name="hosted-contact-object-workflow"></a><span data-ttu-id="4ffb3-109">Flujo de objeto de contacto hospedado</span><span class="sxs-lookup"><span data-stu-id="4ffb3-109">Hosted Contact Object Workflow</span></span>

<span data-ttu-id="4ffb3-110">Estos son los pasos generales para trabajar con el administrador de inquilinos de Exchange hospedado para administrar los objetos de contacto:</span><span class="sxs-lookup"><span data-stu-id="4ffb3-110">The following are the general steps for working with your hosted Exchange tenant administrator to manage contact objects:</span></span>

1.  <span data-ttu-id="4ffb3-111">El administrador de Exchange solicita números de teléfono para los objetos de contacto de acceso de suscriptor de mensajería unificada de Exchange y operador automático.</span><span class="sxs-lookup"><span data-stu-id="4ffb3-111">The Exchange administrator requests phone numbers for the Exchange UM subscriber access and auto-attendant Contact objects.</span></span>

2.  <span data-ttu-id="4ffb3-112">El administrador de Lync Server 2013 crea un objeto de contacto para cada número de teléfono y asigna una directiva de correo de voz hospedado a cada objeto de contacto.</span><span class="sxs-lookup"><span data-stu-id="4ffb3-112">The Lync Server 2013 administrator creates a Contact object for each phone number and assigns a hosted voice mail policy to each Contact object.</span></span>

3.  <span data-ttu-id="4ffb3-113">El administrador de Lync Server 2013 proporciona los números de teléfono para el administrador de Exchange.</span><span class="sxs-lookup"><span data-stu-id="4ffb3-113">The Lync Server 2013 administrator provides the phone numbers to the Exchange administrator.</span></span>

4.  <span data-ttu-id="4ffb3-114">El administrador de Exchange asigna los números de teléfono a los planes de marcado correctos de MU de Exchange para los operadores automáticos y el acceso de suscriptor.</span><span class="sxs-lookup"><span data-stu-id="4ffb3-114">The Exchange administrator assigns the phone numbers to appropriate Exchange UM dial plans for auto attendants and subscriber access.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="4ffb3-115">No es necesario configurar ninguna configuración del plan de marcado de Lync Server 2013 en los objetos de contacto, tal y como lo hace en las implementaciones locales.</span><span class="sxs-lookup"><span data-stu-id="4ffb3-115">There is no need to configure any Lync Server 2013 dial plan settings on the Contact objects as there is with on-premises deployments.</span></span>



</div>

</div>

<div>

## <a name="configuring-hosted-contact-objects"></a><span data-ttu-id="4ffb3-116">Configurar objetos de contactos hospedados</span><span class="sxs-lookup"><span data-stu-id="4ffb3-116">Configuring Hosted Contact Objects</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="4ffb3-117">Antes de que los objetos de contacto de Lync Server 2013 se puedan habilitar para la mensajería unificada de Exchange hospedada, se debe implementar una directiva de correo de voz hospedada que se aplica.</span><span class="sxs-lookup"><span data-stu-id="4ffb3-117">Before Lync Server 2013 Contact objects can be enabled for hosted Exchange UM, a hosted voice mail policy that applies to them must be deployed.</span></span> <span data-ttu-id="4ffb3-118">La Directiva puede tener un ámbito global, de nivel de sitio o por usuario, siempre y cuando se aplique al objeto de contacto que desea habilitar.</span><span class="sxs-lookup"><span data-stu-id="4ffb3-118">The policy can be of global, site-level, or per-user scope, as long as it applies to the contact object you want to enable.</span></span> <span data-ttu-id="4ffb3-119">Para obtener más información, consulte <A href="lync-server-2013-hosted-voice-mail-policies.md">directivas de correo de voz hospedado en Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="4ffb3-119">For details, see <A href="lync-server-2013-hosted-voice-mail-policies.md">Hosted voice mail policies in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="4ffb3-120">Para configurar los objetos de contacto de acceso del operador automático y del suscriptor hospedados en una implementación entre locales, debe usar los siguientes cmdlets:</span><span class="sxs-lookup"><span data-stu-id="4ffb3-120">To configure hosted auto-attendant and subscriber access Contact objects in a cross-premises deployment, you must use the following cmdlets:</span></span>

  - <span data-ttu-id="4ffb3-121">**New-CsExUmContact** crea un nuevo objeto de contacto para la mensajería unificada hospedada.</span><span class="sxs-lookup"><span data-stu-id="4ffb3-121">**New-CsExUmContact** creates a new Contact object for hosted UM.</span></span>

  - <span data-ttu-id="4ffb3-122">**Set-CsExUmContact** modifica un objeto de contacto existente para la mensajería unificada de Exchange hospedada.</span><span class="sxs-lookup"><span data-stu-id="4ffb3-122">**Set-CsExUmContact** modifies an existing Contact object for hosted Exchange UM.</span></span>

<span data-ttu-id="4ffb3-123">En el ejemplo siguiente se crea un objeto de contacto de operador automático:</span><span class="sxs-lookup"><span data-stu-id="4ffb3-123">The following example creates an auto-attendant Contact object:</span></span>

    New-CsExUmContact -SipAddress sip:exumaa1@fabrikam.com -RegistrarPool RedmondPool.litwareinc.com -OU "OU=ExUmContacts,DC=litwareinc,DC=com" -DisplayNumber 2065559876 -AutoAttendant $True

<span data-ttu-id="4ffb3-124">Este ejemplo crea un nuevo objeto de contacto de mensajería unificada de Exchange con la dirección SIP sip:exumaa1@fabrikam.com.</span><span class="sxs-lookup"><span data-stu-id="4ffb3-124">This example creates a new Exchange UM Contact object with the SIP address sip:exumaa1@fabrikam.com.</span></span> <span data-ttu-id="4ffb3-125">El nombre del grupo en el que se ejecuta el servicio de registro de 2013 de Lync Server es RedmondPool.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="4ffb3-125">The name of the pool where the Lync Server 2013 Registrar service is running is RedmondPool.litwareinc.com.</span></span> <span data-ttu-id="4ffb3-126">La unidad organizativa de Active Directory donde se almacenará esta información es OU = ExUmContacts, DC = litwareinc, DC = com.</span><span class="sxs-lookup"><span data-stu-id="4ffb3-126">The Active Directory organizational unit where this information will be stored is OU=ExUmContacts,DC=litwareinc,DC=com.</span></span> <span data-ttu-id="4ffb3-127">El número de teléfono del objeto de contacto es 2065554567.</span><span class="sxs-lookup"><span data-stu-id="4ffb3-127">The phone number of the Contact object is 2065554567.</span></span> <span data-ttu-id="4ffb3-128">El parámetro opcional-autoattendant $True especifica que este objeto es un objeto de contacto de operador automático.</span><span class="sxs-lookup"><span data-stu-id="4ffb3-128">The optional -AutoAttendant $True parameter specifies that this object is an auto-attendant Contact object.</span></span> <span data-ttu-id="4ffb3-129">Establecer el parámetro-autooperador en falso (el valor predeterminado) especifica un objeto de contacto de acceso de suscriptor.</span><span class="sxs-lookup"><span data-stu-id="4ffb3-129">Setting the -AutoAttendant parameter to False (the default) specifies a subscriber access Contact object.</span></span>

<span data-ttu-id="4ffb3-130">Para obtener más información sobre los cmdlets New-CsExUmContact y set-CsExUmContact, consulte la documentación del shell de administración de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="4ffb3-130">For details about the New-CsExUmContact and Set-CsExUmContact cmdlets, see the Lync Server Management Shell documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

