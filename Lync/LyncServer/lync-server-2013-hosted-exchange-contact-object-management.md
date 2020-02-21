---
title: 'Lync Server 2013: administración de objetos de contacto de Exchange hospedado'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Hosted Exchange Contact object management
ms:assetid: eead9d76-bc4f-4c1c-9779-683cb7a88410
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412978(v=OCS.15)
ms:contentKeyID: 48185748
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2ede940e1126660aaae89fe6552f050632f841b8
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42198733"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="hosted-exchange-contact-object-management-in-lync-server-2013"></a><span data-ttu-id="3b956-102">Administración de objetos de contacto de Exchange hospedado en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3b956-102">Hosted Exchange Contact object management in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3b956-103">_**Última modificación del tema:** 2012-09-25_</span><span class="sxs-lookup"><span data-stu-id="3b956-103">_**Topic Last Modified:** 2012-09-25_</span></span>

<span data-ttu-id="3b956-104">Es preciso configurar un objeto de contacto para cada número de operador automático y número de acceso de suscriptor en la implementación local.</span><span class="sxs-lookup"><span data-stu-id="3b956-104">You need to configure a Contact object for each auto-attendant number and subscriber access number in your cross-premises deployment.</span></span>

<span data-ttu-id="3b956-105">Para la integración con mensajería unificada hospedada de Exchange, ocsumutil.exe no es válido para administrar objetos de contacto, ya que depende de la configuración de mensajería unificada de Exchange de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="3b956-105">For integration with hosted Exchange UM, ocsumutil.exe cannot be used to manage Contact objects, because it depends on Active Directory Exchange UM settings.</span></span> <span data-ttu-id="3b956-106">En una implementación entre entornos, Lync Server 2013 y la mensajería unificada de Exchange hospedada se instalan en bosques independientes que no tienen confianza entre ellos.</span><span class="sxs-lookup"><span data-stu-id="3b956-106">In a cross-premises deployment, Lync Server 2013 and hosted Exchange UM are installed in separate forests with no trust between them.</span></span> <span data-ttu-id="3b956-107">Por motivos de seguridad, los administradores de Lync Server 2013 no tienen acceso directo a la configuración de Active Directory de mensajería unificada de Exchange.</span><span class="sxs-lookup"><span data-stu-id="3b956-107">For security reasons, Lync Server 2013 administrators have no direct access to Exchange UM Active Directory settings.</span></span> <span data-ttu-id="3b956-108">Como resultado, Lync Server 2013 proporciona un modelo diferente para administrar objetos de contacto en un *espacio de direcciones SIP compartido* que es accesible tanto para Lync Server 2013 como para el servicio de mensajería unificada de Exchange hospedado.</span><span class="sxs-lookup"><span data-stu-id="3b956-108">As a result, Lync Server 2013 provides a different model for managing Contact objects in a *shared SIP address space* that is accessible to both Lync Server 2013 and the hosted Exchange UM service.</span></span>

<div>

## <a name="hosted-contact-object-workflow"></a><span data-ttu-id="3b956-109">Flujo de trabajo de objetos de contacto hospedados</span><span class="sxs-lookup"><span data-stu-id="3b956-109">Hosted Contact Object Workflow</span></span>

<span data-ttu-id="3b956-110">A continuación, se exponen los pasos generales para trabajar con el administrador de arrendatarios de Exchange hospedado para administrar objetos de contacto:</span><span class="sxs-lookup"><span data-stu-id="3b956-110">The following are the general steps for working with your hosted Exchange tenant administrator to manage contact objects:</span></span>

1.  <span data-ttu-id="3b956-111">El administrador de Exchange solicita números de teléfono para el acceso de objetos de contacto del operador automático y del suscriptor de mensajería unificada de Exchange.</span><span class="sxs-lookup"><span data-stu-id="3b956-111">The Exchange administrator requests phone numbers for the Exchange UM subscriber access and auto-attendant Contact objects.</span></span>

2.  <span data-ttu-id="3b956-112">El administrador de Lync Server 2013 crea un objeto de contacto para cada número de teléfono y asigna una directiva de correo de voz hospedado a cada objeto de contacto.</span><span class="sxs-lookup"><span data-stu-id="3b956-112">The Lync Server 2013 administrator creates a Contact object for each phone number and assigns a hosted voice mail policy to each Contact object.</span></span>

3.  <span data-ttu-id="3b956-113">El administrador de Lync Server 2013 proporciona los números de teléfono al administrador de Exchange.</span><span class="sxs-lookup"><span data-stu-id="3b956-113">The Lync Server 2013 administrator provides the phone numbers to the Exchange administrator.</span></span>

4.  <span data-ttu-id="3b956-114">El administrador de Exchange asigna los números de teléfono a los planes de marcado de mensajería unificada de Exchange para el acceso de suscriptores y operadores automáticos.</span><span class="sxs-lookup"><span data-stu-id="3b956-114">The Exchange administrator assigns the phone numbers to appropriate Exchange UM dial plans for auto attendants and subscriber access.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="3b956-115">No es necesario configurar ninguna configuración de plan de marcado de Lync Server 2013 en los objetos de contacto, como lo haría con las implementaciones locales.</span><span class="sxs-lookup"><span data-stu-id="3b956-115">There is no need to configure any Lync Server 2013 dial plan settings on the Contact objects as there is with on-premises deployments.</span></span>



</div>

</div>

<div>

## <a name="configuring-hosted-contact-objects"></a><span data-ttu-id="3b956-116">Configuración de objetos de contacto hospedados</span><span class="sxs-lookup"><span data-stu-id="3b956-116">Configuring Hosted Contact Objects</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="3b956-117">Antes de que Lync Server 2013 los objetos de contacto se puedan habilitar para la mensajería unificada de Exchange hospedada, debe implementarse una directiva de correo de voz hospedada que se les aplique.</span><span class="sxs-lookup"><span data-stu-id="3b956-117">Before Lync Server 2013 Contact objects can be enabled for hosted Exchange UM, a hosted voice mail policy that applies to them must be deployed.</span></span> <span data-ttu-id="3b956-118">La directiva puede ser de ámbito global, de nivel de sitio o de ámbito de usuario, siempre y cuando se aplique al objeto de contacto que desea habilitar.</span><span class="sxs-lookup"><span data-stu-id="3b956-118">The policy can be of global, site-level, or per-user scope, as long as it applies to the contact object you want to enable.</span></span> <span data-ttu-id="3b956-119">Para obtener más información, consulte <A href="lync-server-2013-hosted-voice-mail-policies.md">directivas de correo de voz hospedado en Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="3b956-119">For details, see <A href="lync-server-2013-hosted-voice-mail-policies.md">Hosted voice mail policies in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="3b956-120">Para configurar objetos de contacto de acceso de suscriptor y operador automático en una implementación local, debe usar los cmdlets siguientes:</span><span class="sxs-lookup"><span data-stu-id="3b956-120">To configure hosted auto-attendant and subscriber access Contact objects in a cross-premises deployment, you must use the following cmdlets:</span></span>

  - <span data-ttu-id="3b956-121">**New-CsExUmContact** crea un objeto de contacto para mensajería unificada hospedada.</span><span class="sxs-lookup"><span data-stu-id="3b956-121">**New-CsExUmContact** creates a new Contact object for hosted UM.</span></span>

  - <span data-ttu-id="3b956-122">**Set-CsExUmContact** modifica un objeto de contacto ya creado para mensajería unificada hospedada.</span><span class="sxs-lookup"><span data-stu-id="3b956-122">**Set-CsExUmContact** modifies an existing Contact object for hosted Exchange UM.</span></span>

<span data-ttu-id="3b956-123">El ejemplo siguiente crea un objeto de contacto de operador automático.</span><span class="sxs-lookup"><span data-stu-id="3b956-123">The following example creates an auto-attendant Contact object:</span></span>

    New-CsExUmContact -SipAddress sip:exumaa1@fabrikam.com -RegistrarPool RedmondPool.litwareinc.com -OU "OU=ExUmContacts,DC=litwareinc,DC=com" -DisplayNumber 2065559876 -AutoAttendant $True

<span data-ttu-id="3b956-124">Este ejemplo crea un objeto de contacto de mensajería unificada de Exchange con la dirección SIP sip:exumaa1@fabrikam.com.</span><span class="sxs-lookup"><span data-stu-id="3b956-124">This example creates a new Exchange UM Contact object with the SIP address sip:exumaa1@fabrikam.com.</span></span> <span data-ttu-id="3b956-125">El nombre del grupo de servidores en el que se ejecuta el servicio de registro 2013 de Lync Server es RedmondPool.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="3b956-125">The name of the pool where the Lync Server 2013 Registrar service is running is RedmondPool.litwareinc.com.</span></span> <span data-ttu-id="3b956-126">La unidad organizativa de Active Directory donde se guardará esta información es OU=ExUmContacts,DC=litwareinc,DC=com.</span><span class="sxs-lookup"><span data-stu-id="3b956-126">The Active Directory organizational unit where this information will be stored is OU=ExUmContacts,DC=litwareinc,DC=com.</span></span> <span data-ttu-id="3b956-127">El número de teléfono del objeto de contacto es 2065554567.</span><span class="sxs-lookup"><span data-stu-id="3b956-127">The phone number of the Contact object is 2065554567.</span></span> <span data-ttu-id="3b956-128">El parámetro opcional -AutoAttendant $True especifica que se trata de un objeto de contacto de operador automático.</span><span class="sxs-lookup"><span data-stu-id="3b956-128">The optional -AutoAttendant $True parameter specifies that this object is an auto-attendant Contact object.</span></span> <span data-ttu-id="3b956-129">Si el parámetro -AutoAttendant se establece en False (valor predeterminado), se especifica un objeto de contacto con acceso de suscriptor.</span><span class="sxs-lookup"><span data-stu-id="3b956-129">Setting the -AutoAttendant parameter to False (the default) specifies a subscriber access Contact object.</span></span>

<span data-ttu-id="3b956-130">Para obtener más información sobre los cmdlets New-CsExUmContact y set-CsExUmContact, consulte la documentación del shell de administración de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="3b956-130">For details about the New-CsExUmContact and Set-CsExUmContact cmdlets, see the Lync Server Management Shell documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

