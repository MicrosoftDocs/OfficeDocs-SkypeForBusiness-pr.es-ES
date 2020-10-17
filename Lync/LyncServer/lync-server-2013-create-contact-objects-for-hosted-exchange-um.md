---
title: 'Lync Server 2013: crear objetos de contacto para la mensajería unificada de Exchange hospedada'
description: 'Lync Server 2013: crear objetos de contacto para la mensajería unificada de Exchange hospedada.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create contact objects for hosted Exchange UM
ms:assetid: a39be52f-488a-4523-ad5f-ce1f0d681959
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412765(v=OCS.15)
ms:contentKeyID: 48185045
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c9760e2a39b5182f9b5194e364e059bddc6a63d2
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48562306"
---
# <a name="create-contact-objects-for-hosted-exchange-um-in-lync-server-2013"></a><span data-ttu-id="6c282-103">Crear objetos de contacto para la mensajería unificada de Exchange hospedada en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6c282-103">Create contact objects for hosted Exchange UM in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6c282-104">_**Última modificación del tema:** 2012-09-24_</span><span class="sxs-lookup"><span data-stu-id="6c282-104">_**Topic Last Modified:** 2012-09-24_</span></span>

<span data-ttu-id="6c282-105">El siguiente procedimiento explica cómo crear objetos de contacto de operador automático (AA) o de acceso de suscriptor (SA) para mensajería unificada (UM) hospedada de Exchange.</span><span class="sxs-lookup"><span data-stu-id="6c282-105">The following procedure explains how to create Auto Attendant (AA) or Subscriber Access (SA) contact objects for hosted Exchange Unified Messaging (UM).</span></span>

<span data-ttu-id="6c282-106">Para obtener más información, consulte [Hosted Exchange Contact Object Management in Lync Server 2013](lync-server-2013-hosted-exchange-contact-object-management.md) en la documentación referente a la planeación.</span><span class="sxs-lookup"><span data-stu-id="6c282-106">For details, see [Hosted Exchange Contact object management in Lync Server 2013](lync-server-2013-hosted-exchange-contact-object-management.md) in the Planning documentation.</span></span>

<span data-ttu-id="6c282-107">Para obtener más información acerca de la configuración de objetos de contacto, consulte la documentación del shell de administración de Lync Server para los siguientes cmdlets:</span><span class="sxs-lookup"><span data-stu-id="6c282-107">For details about configuring contact objects, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - [<span data-ttu-id="6c282-108">New-CsExUmContact</span><span class="sxs-lookup"><span data-stu-id="6c282-108">New-CsExUmContact</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsExUmContact)

  - [<span data-ttu-id="6c282-109">Set-CsExUmContact</span><span class="sxs-lookup"><span data-stu-id="6c282-109">Set-CsExUmContact</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsExUmContact)

<div class=" ">


> [!IMPORTANT]  
> <span data-ttu-id="6c282-110">Antes de que Lync Server 2013 los objetos de contacto se puedan habilitar para la mensajería unificada de Exchange hospedada, debe implementarse una directiva de correo de voz hospedada que se les aplique.</span><span class="sxs-lookup"><span data-stu-id="6c282-110">Before Lync Server 2013 contact objects can be enabled for hosted Exchange UM, a hosted voice mail policy that applies to them must be deployed.</span></span> <span data-ttu-id="6c282-111">Para obtener más información, consulte <A href="lync-server-2013-hosted-voice-mail-policies.md">directivas de correo de voz hospedado en Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="6c282-111">For details, see <A href="lync-server-2013-hosted-voice-mail-policies.md">Hosted voice mail policies in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-create-aa-or-sa-contact-objects-for-hosted-exchange-um"></a><span data-ttu-id="6c282-112">Para crear objetos de contacto AA o SA para la mensajería unificada de Exchange hospedada</span><span class="sxs-lookup"><span data-stu-id="6c282-112">To create AA or SA contact objects for hosted Exchange UM</span></span>

1.  <span data-ttu-id="6c282-113">Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="6c282-113">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="6c282-114">Ejecute el cmdlet New-CsExUmContact para crear cualquier objeto de contacto necesario para la implementación.</span><span class="sxs-lookup"><span data-stu-id="6c282-114">Run the New-CsExUmContact cmdlet to create any contact objects required for your deployment.</span></span> <span data-ttu-id="6c282-115">Por ejemplo, ejecute lo siguiente para crear un objeto de contacto de la AA y de la Asociación:</span><span class="sxs-lookup"><span data-stu-id="6c282-115">For example, run the following to create an AA and an SA contact object:</span></span>
    
       ```powershell
        New-CsExUmContact -SipAddress "sip:exumaa1@fabrikam.com" -RegistrarPool "RedmondPool.litwareinc.com" -OU "HostedExUM Integration" -DisplayNumber "+14255550101" -AutoAttendant $True
       ```
    
       ```powershell
        New-CsExUmContact -SipAddress "sip:exumsa1@fabrikam.com" -RegistrarPool "RedmondPool.litwareinc.com" -OU "HostedExUM Integration" -DisplayNumber "+14255550101"
       ```
    
    <span data-ttu-id="6c282-116">En estos ejemplos se establecen los siguientes parámetros:</span><span class="sxs-lookup"><span data-stu-id="6c282-116">These examples set the following parameters:</span></span>
    
      - <span data-ttu-id="6c282-117">**SipAddress** especifica la dirección SIP del objeto de contacto.</span><span class="sxs-lookup"><span data-stu-id="6c282-117">**SipAddress** specifies the SIP address of the contact object.</span></span> <span data-ttu-id="6c282-118">Debe tratarse de una dirección que aún no se haya usado para configurar un objeto de contacto o de usuario en servicios de dominio de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="6c282-118">This must be an address that has not already been used to configure a user or contact object in Active Directory Domain Services.</span></span> <span data-ttu-id="6c282-119">Este valor debe tener el formato "SIP: \<*SIP address*\> ", tal como se muestra en los ejemplos anteriores.</span><span class="sxs-lookup"><span data-stu-id="6c282-119">This value must be in the format “sip:\<*SIP address*\>“ as shown in the previous examples.</span></span>
    
      - <span data-ttu-id="6c282-120">**RegistrarPool** especifica el nombre de dominio completo (FQDN) del grupo en el que se está ejecutando el servicio de registrador.</span><span class="sxs-lookup"><span data-stu-id="6c282-120">**RegistrarPool** specifies the fully qualified domain name (FQDN) of the pool on which the Registrar service is running.</span></span>
        
        <div class=" ">
        

        > [!NOTE]  
        > <span data-ttu-id="6c282-121">Los objetos de contacto de mensajería unificada de Exchange no se pueden mover a los grupos que forman parte de implementaciones de Lync Server 2013 anteriores a Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6c282-121">Exchange UM contact objects cannot be moved to pools that are part of Lync Server 2013 deployments prior to Lync Server 2013.</span></span>

        
        </div>
    
      - <span data-ttu-id="6c282-122">**Ou** especifica la unidad organizativa de Active Directory donde se ubicará este objeto de contacto.</span><span class="sxs-lookup"><span data-stu-id="6c282-122">**OU** specifies the Active Directory organizational unit where this contact object will be located.</span></span>
    
      - <span data-ttu-id="6c282-123">**DisplayNumber** especifica el número de teléfono del objeto de contacto.</span><span class="sxs-lookup"><span data-stu-id="6c282-123">**DisplayNumber** specifies the telephone number of the contact object.</span></span> <span data-ttu-id="6c282-124">El número de teléfono de cada objeto de contacto debe ser único.</span><span class="sxs-lookup"><span data-stu-id="6c282-124">The phone number for each contact object must be unique.</span></span>
    
      - <span data-ttu-id="6c282-125">**Autoattendant** especifica si el objeto de contacto es un operador automático.</span><span class="sxs-lookup"><span data-stu-id="6c282-125">**AutoAttendant** specifies whether the Contact object is an Auto Attendant.</span></span> <span data-ttu-id="6c282-126">Operador automático proporciona un conjunto de mensajes de voz que permiten a los autores de llamadas navegar por el sistema telefónico y llegar a la parte de la que quieren contactar.</span><span class="sxs-lookup"><span data-stu-id="6c282-126">Auto Attendant provides a set of voice prompts that allow callers to navigate the phone system and reach the party that they want to contact.</span></span> <span data-ttu-id="6c282-127">Un valor de **false** (valor predeterminado) para este parámetro indica un objeto de contacto de acceso de suscriptor.</span><span class="sxs-lookup"><span data-stu-id="6c282-127">A value of **False** (the default) for this parameter indicates a Subscriber Access contact object.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

