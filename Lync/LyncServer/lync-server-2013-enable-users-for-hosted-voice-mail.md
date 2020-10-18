---
title: 'Lync Server 2013: habilitar usuarios para correo de voz hospedado'
description: 'Lync Server 2013: habilite a los usuarios para el correo de voz hospedado.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable users for hosted voice mail
ms:assetid: fa559f8f-ef99-43a1-b580-9e998b95efb8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413062(v=OCS.15)
ms:contentKeyID: 48185919
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3853a70d433c09029a02f2ca6256b5988defdcb2
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48572746"
---
# <a name="enable-users-for-hosted-voice-mail-in-lync-server-2013"></a><span data-ttu-id="c8317-103">Habilitar a los usuarios para el correo de voz hospedado en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c8317-103">Enable users for hosted voice mail in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c8317-104">_**Última modificación del tema:** 2012-09-24_</span><span class="sxs-lookup"><span data-stu-id="c8317-104">_**Topic Last Modified:** 2012-09-24_</span></span>

<span data-ttu-id="c8317-105">Siga el procedimiento para habilitar a los usuarios de Lync Server 2013 para el correo de voz en un servicio de mensajería unificada (UM) de Exchange hospedado.</span><span class="sxs-lookup"><span data-stu-id="c8317-105">Follow the procedure to enable Lync Server 2013 users for voice mail on a hosted Exchange Unified Messaging (UM) service.</span></span>

<span data-ttu-id="c8317-106">Para obtener más información, consulte [Hosted Exchange User Management in Lync Server 2013](lync-server-2013-hosted-exchange-user-management.md) en la documentación referente a la planeación.</span><span class="sxs-lookup"><span data-stu-id="c8317-106">For details, see [Hosted Exchange user management in Lync Server 2013](lync-server-2013-hosted-exchange-user-management.md) in the Planning documentation.</span></span>

<span data-ttu-id="c8317-107">Para obtener más información sobre el cmdlet [set-CsUser](https://docs.microsoft.com/powershell/module/skype/Set-CsUser) , consulte la documentación del shell de administración de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c8317-107">For details about the [Set-CsUser](https://docs.microsoft.com/powershell/module/skype/Set-CsUser) cmdlet, see the Lync Server Management Shell documentation.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="c8317-108">Antes de que un usuario de Lync Server 2013 pueda estar habilitado para el correo de voz hospedado, debe implementarse una directiva de correo de voz hospedada que se aplique a su cuenta de usuario.</span><span class="sxs-lookup"><span data-stu-id="c8317-108">Before a Lync Server 2013 user can be enabled for hosted voice mail, a hosted voice mail policy that applies to their user account must be deployed.</span></span> <span data-ttu-id="c8317-109">Para obtener más información, consulte <A href="lync-server-2013-hosted-voice-mail-policies.md">directivas de correo de voz hospedado en Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="c8317-109">For details, see <A href="lync-server-2013-hosted-voice-mail-policies.md">Hosted voice mail policies in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-enable-users-for-hosted-voice-mail"></a><span data-ttu-id="c8317-110">Para habilitar a los usuarios para correo de voz hospedado.</span><span class="sxs-lookup"><span data-stu-id="c8317-110">To enable users for hosted voice mail</span></span>

1.  <span data-ttu-id="c8317-111">Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="c8317-111">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="c8317-p102">Ejecute el cmdlet Set-CsUser para configurar la cuenta del usuario para correo de voz hospedado. Por ejemplo, ejecute lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="c8317-p102">Run the Set-CsUser cmdlet to configure the user account for hosted voice mail. For example, run:</span></span>
    
        Set-CsUser -HostedVoiceMail $True -Identity "contoso\kenmyer"
    
    <span data-ttu-id="c8317-114">En el ejemplo anterior se definen los parámetros siguientes:</span><span class="sxs-lookup"><span data-stu-id="c8317-114">The preceding example sets the following parameters:</span></span>
    
      - <span data-ttu-id="c8317-115">**HostedVoiceMail** permite que las llamadas de correo de voz de un usuario se enruten a una versión hospedada de mensajería instantánea de Exchange.</span><span class="sxs-lookup"><span data-stu-id="c8317-115">**HostedVoiceMail** enables a user’s voice mail calls to be routed to hosted Exchange UM.</span></span> <span data-ttu-id="c8317-116">También indica a Microsoft Lync 2013 que ilumine el indicador "llamar al correo de voz".</span><span class="sxs-lookup"><span data-stu-id="c8317-116">It also signals Microsoft Lync 2013 to light up the “call voice mail” indicator.</span></span>
    
      - <span data-ttu-id="c8317-p104">**Identity** especifica la cuenta de usuario que modificar. El valor de Identity puede especificarse con cualquiera de los formatos a continuación:</span><span class="sxs-lookup"><span data-stu-id="c8317-p104">**Identity** specifies the user account to be modified. The Identity value can be specified using any of the following formats:</span></span>
        
          - <span data-ttu-id="c8317-119">La dirección SIP del usuario</span><span class="sxs-lookup"><span data-stu-id="c8317-119">The user's SIP address</span></span>
        
          - <span data-ttu-id="c8317-120">El nombre principal de usuario de Active Directory del usuario</span><span class="sxs-lookup"><span data-stu-id="c8317-120">The user's Active Directory User-Principal-Name</span></span>
        
          - <span data-ttu-id="c8317-121">El nombre de inicio de sesión del dominio del usuario \\ (por ejemplo, contoso \\ kenmyer)</span><span class="sxs-lookup"><span data-stu-id="c8317-121">The user's domain\\logon name (for example, contoso\\kenmyer)</span></span>
        
          - <span data-ttu-id="c8317-122">El nombre para mostrar de Servicios de dominio de Active Directory (por ejemplo, Ken Myer).</span><span class="sxs-lookup"><span data-stu-id="c8317-122">The user's Active Directory Domain Services Display-Name (for example, Ken Myer).</span></span> <span data-ttu-id="c8317-123">Si usa el Display-Name como valor de identidad, puede usar el \* carácter comodín asterisco ().</span><span class="sxs-lookup"><span data-stu-id="c8317-123">If using the Display-Name as the Identity value, you can use the asterisk (\*) wildcard character.</span></span> <span data-ttu-id="c8317-124">Por ejemplo, la identidad " \* Smith" devuelve todos los usuarios que tienen una Display-Name que termina con el valor de cadena "Smith".</span><span class="sxs-lookup"><span data-stu-id="c8317-124">For example, the Identity "\* Smith" returns all the users who have a Display-Name that ends with the string value "Smith".</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="c8317-125">El nombre de cuenta SAM de Active Directory del usuario no se puede usar como valor de Identity porque puede que no sea único en el bosque.</span><span class="sxs-lookup"><span data-stu-id="c8317-125">The user’s Active Directory SAM-Account-Name cannot be used as the Identity value because the SAM-Account-Name is not necessarily unique in the forest.</span></span>

        
        </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

