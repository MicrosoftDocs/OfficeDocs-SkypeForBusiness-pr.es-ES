---
title: 'Lync Server 2013: Habilitar a los usuarios para el correo de voz hospedado'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enable users for hosted voice mail
ms:assetid: fa559f8f-ef99-43a1-b580-9e998b95efb8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413062(v=OCS.15)
ms:contentKeyID: 48185919
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 45872df26989d8d264ce77406bfbce86f321ccf8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34835274"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-users-for-hosted-voice-mail-in-lync-server-2013"></a><span data-ttu-id="496c1-102">Habilitar a los usuarios para el correo de voz hospedado en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="496c1-102">Enable users for hosted voice mail in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="496c1-103">_**Última modificación del tema:** 2012-09-24_</span><span class="sxs-lookup"><span data-stu-id="496c1-103">_**Topic Last Modified:** 2012-09-24_</span></span>

<span data-ttu-id="496c1-104">Siga el procedimiento para habilitar a los usuarios de Lync Server 2013 para el correo de voz en un servicio de mensajería unificada (UM) hospedada de Exchange.</span><span class="sxs-lookup"><span data-stu-id="496c1-104">Follow the procedure to enable Lync Server 2013 users for voice mail on a hosted Exchange Unified Messaging (UM) service.</span></span>

<span data-ttu-id="496c1-105">Para obtener más información, vea [Administración de usuarios de Exchange hospedado en Lync Server 2013](lync-server-2013-hosted-exchange-user-management.md) en la documentación de planeación.</span><span class="sxs-lookup"><span data-stu-id="496c1-105">For details, see [Hosted Exchange user management in Lync Server 2013](lync-server-2013-hosted-exchange-user-management.md) in the Planning documentation.</span></span>

<span data-ttu-id="496c1-106">Para obtener más información sobre el cmdlet [set-CsUser](https://docs.microsoft.com/powershell/module/skype/Set-CsUser) , consulte la documentación del shell de administración de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="496c1-106">For details about the [Set-CsUser](https://docs.microsoft.com/powershell/module/skype/Set-CsUser) cmdlet, see the Lync Server Management Shell documentation.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="496c1-107">Para que un usuario de Lync Server 2013 pueda estar habilitado para el correo de voz hospedado, debe implementarse una directiva de correo de voz hospedada que se aplique a su cuenta de usuario.</span><span class="sxs-lookup"><span data-stu-id="496c1-107">Before a Lync Server 2013 user can be enabled for hosted voice mail, a hosted voice mail policy that applies to their user account must be deployed.</span></span> <span data-ttu-id="496c1-108">Para obtener más información, consulte <A href="lync-server-2013-hosted-voice-mail-policies.md">directivas de correo de voz hospedado en Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="496c1-108">For details, see <A href="lync-server-2013-hosted-voice-mail-policies.md">Hosted voice mail policies in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-enable-users-for-hosted-voice-mail"></a><span data-ttu-id="496c1-109">Para habilitar a los usuarios para el correo de voz hospedado</span><span class="sxs-lookup"><span data-stu-id="496c1-109">To enable users for hosted voice mail</span></span>

1.  <span data-ttu-id="496c1-110">Inicie el shell de administración de Lync Server: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **Shell de administración de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="496c1-110">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="496c1-111">Ejecute el cmdlet Set-CsUser para configurar la cuenta de usuario para el correo de voz hospedado.</span><span class="sxs-lookup"><span data-stu-id="496c1-111">Run the Set-CsUser cmdlet to configure the user account for hosted voice mail.</span></span> <span data-ttu-id="496c1-112">Por ejemplo, ejecute lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="496c1-112">For example, run:</span></span>
    
        Set-CsUser -HostedVoiceMail $True -Identity "contoso\kenmyer"
    
    <span data-ttu-id="496c1-113">En el ejemplo anterior se definen los parámetros siguientes:</span><span class="sxs-lookup"><span data-stu-id="496c1-113">The preceding example sets the following parameters:</span></span>
    
      - <span data-ttu-id="496c1-114">**HostedVoiceMail** permite enrutar las llamadas de correo de voz de un usuario a la mensajería unificada de Exchange hospedada.</span><span class="sxs-lookup"><span data-stu-id="496c1-114">**HostedVoiceMail** enables a user’s voice mail calls to be routed to hosted Exchange UM.</span></span> <span data-ttu-id="496c1-115">También indica a Microsoft Lync 2013 que ilumine el indicador "llamar al correo de voz".</span><span class="sxs-lookup"><span data-stu-id="496c1-115">It also signals Microsoft Lync 2013 to light up the “call voice mail” indicator.</span></span>
    
      - <span data-ttu-id="496c1-116">**Identity** especifica la cuenta de usuario que se va a modificar.</span><span class="sxs-lookup"><span data-stu-id="496c1-116">**Identity** specifies the user account to be modified.</span></span> <span data-ttu-id="496c1-117">El valor de identidad puede especificarse con cualquiera de los siguientes formatos:</span><span class="sxs-lookup"><span data-stu-id="496c1-117">The Identity value can be specified using any of the following formats:</span></span>
        
          - <span data-ttu-id="496c1-118">Dirección SIP del usuario</span><span class="sxs-lookup"><span data-stu-id="496c1-118">The user's SIP address</span></span>
        
          - <span data-ttu-id="496c1-119">Nombre principal de usuario de Active Directory del usuario</span><span class="sxs-lookup"><span data-stu-id="496c1-119">The user's Active Directory User-Principal-Name</span></span>
        
          - <span data-ttu-id="496c1-120">Nombre de inicio de\\sesión de dominio del usuario (por\\ejemplo, contoso kenmyer)</span><span class="sxs-lookup"><span data-stu-id="496c1-120">The user's domain\\logon name (for example, contoso\\kenmyer)</span></span>
        
          - <span data-ttu-id="496c1-121">El nombre para mostrar de los servicios de dominio de Active Directory del usuario (por ejemplo, Ken Myer).</span><span class="sxs-lookup"><span data-stu-id="496c1-121">The user's Active Directory Domain Services Display-Name (for example, Ken Myer).</span></span> <span data-ttu-id="496c1-122">Si usa el nombre para mostrar como valor de identidad, puede usar el carácter comodín asterisco\*().</span><span class="sxs-lookup"><span data-stu-id="496c1-122">If using the Display-Name as the Identity value, you can use the asterisk (\*) wildcard character.</span></span> <span data-ttu-id="496c1-123">Por ejemplo, la identidad "\* Smith" devuelve todos los usuarios que tienen un nombre para mostrar que termina con el valor de cadena "Smith".</span><span class="sxs-lookup"><span data-stu-id="496c1-123">For example, the Identity "\* Smith" returns all the users who have a Display-Name that ends with the string value "Smith".</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="496c1-124">El nombre de cuenta SAM del usuario de Active Directory no se puede usar como valor de identidad porque el nombre de cuenta SAM no es necesariamente único en el bosque.</span><span class="sxs-lookup"><span data-stu-id="496c1-124">The user’s Active Directory SAM-Account-Name cannot be used as the Identity value because the SAM-Account-Name is not necessarily unique in the forest.</span></span>

        
        </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

