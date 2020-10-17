---
title: 'Lync Server 2013: asignar una directiva de correo de voz hospedado por usuario'
description: 'Lync Server 2013: asignar una directiva de correo de voz hospedado por usuario.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign a per-user hosted voice mail policy
ms:assetid: d44c71a0-4407-4ab4-b7e0-d671dde3425f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398919(v=OCS.15)
ms:contentKeyID: 48185456
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 071d504c452b4d3adb1b636cb5c4ff8835200107
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48559896"
---
# <a name="assign-a-per-user-hosted-voice-mail-policy-in-lync-server-2013"></a><span data-ttu-id="6731c-103">Asignar una directiva de correo de voz hospedado por usuario en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6731c-103">Assign a per-user hosted voice mail policy in Lync Server 2013</span></span>

 


<span data-ttu-id="6731c-p101">Implementar una o varias directivas de correo de voz que hospeda el usuario es opcional. Si no implementa las directivas por usuario, es preciso que las asigne explícitamente a objetos de usuario, grupo o contacto.</span><span class="sxs-lookup"><span data-stu-id="6731c-p101">Deploying one or more per-user hosted voice mail policies is optional. If you do deploy per-user policies, you must explicitly assign them to users, groups, or contact objects.</span></span>

<span data-ttu-id="6731c-106">Para obtener más información sobre cómo asignar o quitar la asignación de directivas de correo de voz hospedado por usuario, consulte la documentación del shell de administración de Lync Server para los siguientes cmdlets:</span><span class="sxs-lookup"><span data-stu-id="6731c-106">For details about assigning or removing the assignment of per-user hosted voice mail policies, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - <span data-ttu-id="6731c-107">Grant-CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="6731c-107">Grant-CsHostedVoicemailPolicy</span></span>

  - <span data-ttu-id="6731c-108">Remove-CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="6731c-108">Remove-CsHostedVoicemailPolicy</span></span>

## <a name="to-assign-a-per-user-hosted-voice-mail-policy"></a><span data-ttu-id="6731c-109">Para asignar una directiva de correo de voz que hospeda el usuario:</span><span class="sxs-lookup"><span data-stu-id="6731c-109">To assign a per-user hosted voice mail policy</span></span>

1.  <span data-ttu-id="6731c-110">Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="6731c-110">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="6731c-p102">Ejecute el cmdlet Grant-CsHostedVoicemailPolicy para asignar la directiva de correo de voz que hospeda el usuario a objetos contacto, usuarios individuales y grupos. Por ejemplo, ejecute lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="6731c-p102">Run the Grant-CsHostedVoicemailPolicy cmdlet to assign the per-user hosted voice mail policy to individual users, groups, and contact objects. For example, run:</span></span>
    
        Grant-CsHostedVoicemailPolicy -Identity "Ken Myer" -PolicyName ExRedmond
    
    <span data-ttu-id="6731c-113">En este ejemplo hemos asignado la directiva de correo de voz hospedado ExRedmond al usuario Antonio Bermejo.</span><span class="sxs-lookup"><span data-stu-id="6731c-113">This example assigned the ExRedmond hosted voice mail policy to user Ken Myer.</span></span>
    
    <span data-ttu-id="6731c-p103">**Identity** especifica la cuenta de usuario que se debe modificar. El valor de Identity puede especificarse con cualquiera de los formatos siguientes:</span><span class="sxs-lookup"><span data-stu-id="6731c-p103">**Identity** specifies the user account to be modified. The Identity value can be specified using any of the following formats:</span></span>
    
      - <span data-ttu-id="6731c-116">La dirección SIP del usuario</span><span class="sxs-lookup"><span data-stu-id="6731c-116">The user's SIP address</span></span>
    
      - <span data-ttu-id="6731c-117">El nombre principal de usuario de Active Directory del usuario</span><span class="sxs-lookup"><span data-stu-id="6731c-117">The user's Active Directory User-Principal-Name</span></span>
    
      - <span data-ttu-id="6731c-118">El nombre de inicio de sesión del dominio del usuario \\ (por ejemplo, contoso \\ kenmyer)</span><span class="sxs-lookup"><span data-stu-id="6731c-118">The user's domain\\logon name (for example, contoso\\kenmyer)</span></span>
    
      - <span data-ttu-id="6731c-119">El nombre para mostrar de Servicios de dominio de Active Directory (por ejemplo, Ken Myer).</span><span class="sxs-lookup"><span data-stu-id="6731c-119">The user's Active Directory Domain Services Display-Name (for example, Ken Myer).</span></span> <span data-ttu-id="6731c-120">Si usa el Display-Name como valor de identidad, puede usar el \* carácter comodín asterisco ().</span><span class="sxs-lookup"><span data-stu-id="6731c-120">If using the Display-Name as the Identity value, you can use the asterisk (\*) wildcard character.</span></span> <span data-ttu-id="6731c-121">Por ejemplo, la identidad " \* Smith" devuelve todos los usuarios que tienen una Display-Name que termina con el valor de cadena "Smith".</span><span class="sxs-lookup"><span data-stu-id="6731c-121">For example, the Identity "\* Smith" returns all the users who have a Display-Name that ends with the string value "Smith".</span></span>
    

    > [!NOTE]  
    > <span data-ttu-id="6731c-122">El nombre de cuenta SAM de Active Directory del usuario no se puede usar como valor de Identity porque puede que no sea único en el bosque.</span><span class="sxs-lookup"><span data-stu-id="6731c-122">The user’s Active Directory SAM-Account-Name cannot be used as the Identity value because the SAM-Account-Name is not necessarily unique in the forest.</span></span>


