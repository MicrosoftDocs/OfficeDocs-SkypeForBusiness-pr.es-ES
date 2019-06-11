---
title: 'Lync Server 2013: Crear objetos de contacto para la mensajería unificada de Exchange hospedada'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create contact objects for hosted Exchange UM
ms:assetid: a39be52f-488a-4523-ad5f-ce1f0d681959
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412765(v=OCS.15)
ms:contentKeyID: 48185045
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c0ce65ed39e67068fcd57aba1177ecb72f553ccf
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34835848"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-contact-objects-for-hosted-exchange-um-in-lync-server-2013"></a><span data-ttu-id="c29f6-102">Crear objetos de contacto para la mensajería unificada de Exchange hospedada en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c29f6-102">Create contact objects for hosted Exchange UM in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c29f6-103">_**Última modificación del tema:** 2012-09-24_</span><span class="sxs-lookup"><span data-stu-id="c29f6-103">_**Topic Last Modified:** 2012-09-24_</span></span>

<span data-ttu-id="c29f6-104">El procedimiento siguiente explica cómo crear objetos de contacto de acceso de suscriptor automático (AA) o de acceso de suscriptor (SA) para mensajería unificada de Exchange hospedado (UM).</span><span class="sxs-lookup"><span data-stu-id="c29f6-104">The following procedure explains how to create Auto Attendant (AA) or Subscriber Access (SA) contact objects for hosted Exchange Unified Messaging (UM).</span></span>

<span data-ttu-id="c29f6-105">Para obtener más información, consulte [Administración de objetos de contactos hospedados de Exchange en Lync Server 2013](lync-server-2013-hosted-exchange-contact-object-management.md) en la documentación de planeación.</span><span class="sxs-lookup"><span data-stu-id="c29f6-105">For details, see [Hosted Exchange Contact object management in Lync Server 2013](lync-server-2013-hosted-exchange-contact-object-management.md) in the Planning documentation.</span></span>

<span data-ttu-id="c29f6-106">Para obtener detalles sobre la configuración de objetos de contacto, consulte la documentación del shell de administración de Lync Server para los siguientes cmdlets:</span><span class="sxs-lookup"><span data-stu-id="c29f6-106">For details about configuring contact objects, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - [<span data-ttu-id="c29f6-107">New-CsExUmContact</span><span class="sxs-lookup"><span data-stu-id="c29f6-107">New-CsExUmContact</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsExUmContact)

  - [<span data-ttu-id="c29f6-108">Set-CsExUmContact</span><span class="sxs-lookup"><span data-stu-id="c29f6-108">Set-CsExUmContact</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsExUmContact)

<div class=" ">


> [!IMPORTANT]  
> <span data-ttu-id="c29f6-109">Antes de que los objetos de contacto de Lync Server 2013 se puedan habilitar para la mensajería unificada de Exchange hospedada, se debe implementar una directiva de correo de voz hospedada que se aplica.</span><span class="sxs-lookup"><span data-stu-id="c29f6-109">Before Lync Server 2013 contact objects can be enabled for hosted Exchange UM, a hosted voice mail policy that applies to them must be deployed.</span></span> <span data-ttu-id="c29f6-110">Para obtener más información, consulte <A href="lync-server-2013-hosted-voice-mail-policies.md">directivas de correo de voz hospedado en Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="c29f6-110">For details, see <A href="lync-server-2013-hosted-voice-mail-policies.md">Hosted voice mail policies in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-create-aa-or-sa-contact-objects-for-hosted-exchange-um"></a><span data-ttu-id="c29f6-111">Para crear objetos de contacto AA o SA para una mensajería unificada de Exchange hospedado</span><span class="sxs-lookup"><span data-stu-id="c29f6-111">To create AA or SA contact objects for hosted Exchange UM</span></span>

1.  <span data-ttu-id="c29f6-112">Inicie el shell de administración de Lync Server: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **Shell de administración de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="c29f6-112">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="c29f6-113">Ejecute el cmdlet New-CsExUmContact para crear cualquier objeto de contacto necesario para su implementación.</span><span class="sxs-lookup"><span data-stu-id="c29f6-113">Run the New-CsExUmContact cmdlet to create any contact objects required for your deployment.</span></span> <span data-ttu-id="c29f6-114">Por ejemplo, ejecute lo siguiente para crear un objeto de contacto de AA y de SA:</span><span class="sxs-lookup"><span data-stu-id="c29f6-114">For example, run the following to create an AA and an SA contact object:</span></span>
    
       ```
        New-CsExUmContact -SipAddress "sip:exumaa1@fabrikam.com" -RegistrarPool "RedmondPool.litwareinc.com" -OU "HostedExUM Integration" -DisplayNumber "+14255550101" -AutoAttendant $True
       ```
    
       ```
        New-CsExUmContact -SipAddress "sip:exumsa1@fabrikam.com" -RegistrarPool "RedmondPool.litwareinc.com" -OU "HostedExUM Integration" -DisplayNumber "+14255550101"
       ```
    
    <span data-ttu-id="c29f6-115">Estos ejemplos establecen los siguientes parámetros:</span><span class="sxs-lookup"><span data-stu-id="c29f6-115">These examples set the following parameters:</span></span>
    
      - <span data-ttu-id="c29f6-116">**SipAddress** especifica la dirección SIP del objeto de contacto.</span><span class="sxs-lookup"><span data-stu-id="c29f6-116">**SipAddress** specifies the SIP address of the contact object.</span></span> <span data-ttu-id="c29f6-117">Debe ser una dirección que aún no se haya usado para configurar un objeto de usuario o contacto en los servicios de dominio de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="c29f6-117">This must be an address that has not already been used to configure a user or contact object in Active Directory Domain Services.</span></span> <span data-ttu-id="c29f6-118">Este valor debe tener el formato "SIP:\<*Dirección*\>SIP", tal y como se muestra en los ejemplos anteriores.</span><span class="sxs-lookup"><span data-stu-id="c29f6-118">This value must be in the format “sip:\<*SIP address*\>“ as shown in the previous examples.</span></span>
    
      - <span data-ttu-id="c29f6-119">**RegistrarPool** especifica el nombre de dominio completo (FQDN) del grupo en el que se está ejecutando el servicio de registro.</span><span class="sxs-lookup"><span data-stu-id="c29f6-119">**RegistrarPool** specifies the fully qualified domain name (FQDN) of the pool on which the Registrar service is running.</span></span>
        
        <div class=" ">
        

        > [!NOTE]  
        > <span data-ttu-id="c29f6-120">Los objetos de contacto de mensajería unificada de Exchange no se pueden mover a los grupos que forman parte de implementaciones de Lync Server 2013 anteriores a Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c29f6-120">Exchange UM contact objects cannot be moved to pools that are part of Lync Server 2013 deployments prior to Lync Server 2013.</span></span>

        
        </div>
    
      - <span data-ttu-id="c29f6-121">**Ou** especifica la unidad organizativa de Active Directory donde se ubicará este objeto de contacto.</span><span class="sxs-lookup"><span data-stu-id="c29f6-121">**OU** specifies the Active Directory organizational unit where this contact object will be located.</span></span>
    
      - <span data-ttu-id="c29f6-122">**DisplayNumber** especifica el número de teléfono del objeto de contacto.</span><span class="sxs-lookup"><span data-stu-id="c29f6-122">**DisplayNumber** specifies the telephone number of the contact object.</span></span> <span data-ttu-id="c29f6-123">El número de teléfono de cada objeto de contacto debe ser único.</span><span class="sxs-lookup"><span data-stu-id="c29f6-123">The phone number for each contact object must be unique.</span></span>
    
      - <span data-ttu-id="c29f6-124">**Autoattendant** especifica si el objeto Contact es un operador automático.</span><span class="sxs-lookup"><span data-stu-id="c29f6-124">**AutoAttendant** specifies whether the Contact object is an Auto Attendant.</span></span> <span data-ttu-id="c29f6-125">El operador automático proporciona un conjunto de mensajes de voz que permiten que las personas que llaman puedan navegar por el sistema telefónico y llegar a la persona con quien desean ponerse en contacto.</span><span class="sxs-lookup"><span data-stu-id="c29f6-125">Auto Attendant provides a set of voice prompts that allow callers to navigate the phone system and reach the party that they want to contact.</span></span> <span data-ttu-id="c29f6-126">Un valor de **falso** (el valor predeterminado) de este parámetro indica un objeto de contacto de acceso de suscriptor.</span><span class="sxs-lookup"><span data-stu-id="c29f6-126">A value of **False** (the default) for this parameter indicates a Subscriber Access contact object.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

