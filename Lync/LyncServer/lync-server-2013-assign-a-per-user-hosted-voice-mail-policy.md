---
title: 'Lync Server 2013: asignar una directiva de correo de voz hospedado por usuario'
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
ms.openlocfilehash: 95413733a9b23ce1f749ebb16521a3349b00165d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41722960"
---
# <a name="assign-a-per-user-hosted-voice-mail-policy-in-lync-server-2013"></a><span data-ttu-id="0daf1-102">Asignar una directiva de correo de voz hospedado por usuario en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0daf1-102">Assign a per-user hosted voice mail policy in Lync Server 2013</span></span>

 


<span data-ttu-id="0daf1-103">Implementar una o más directivas de correo de voz hospedado por cada usuario es opcional.</span><span class="sxs-lookup"><span data-stu-id="0daf1-103">Deploying one or more per-user hosted voice mail policies is optional.</span></span> <span data-ttu-id="0daf1-104">Si implementa directivas por usuario, debe asignarlas explícitamente a usuarios, grupos o objetos de contacto.</span><span class="sxs-lookup"><span data-stu-id="0daf1-104">If you do deploy per-user policies, you must explicitly assign them to users, groups, or contact objects.</span></span>

<span data-ttu-id="0daf1-105">Para obtener más información sobre cómo asignar o quitar la asignación de directivas de correo de voz hospedado por usuario, consulte la documentación del shell de administración de Lync Server para los siguientes cmdlets:</span><span class="sxs-lookup"><span data-stu-id="0daf1-105">For details about assigning or removing the assignment of per-user hosted voice mail policies, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - <span data-ttu-id="0daf1-106">Grant-CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="0daf1-106">Grant-CsHostedVoicemailPolicy</span></span>

  - <span data-ttu-id="0daf1-107">Remove-CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="0daf1-107">Remove-CsHostedVoicemailPolicy</span></span>

## <a name="to-assign-a-per-user-hosted-voice-mail-policy"></a><span data-ttu-id="0daf1-108">Para asignar una directiva de correo de voz hospedado por usuario</span><span class="sxs-lookup"><span data-stu-id="0daf1-108">To assign a per-user hosted voice mail policy</span></span>

1.  <span data-ttu-id="0daf1-109">Inicie el shell de administración de Lync Server: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **Shell de administración de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="0daf1-109">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="0daf1-110">Ejecute el cmdlet Grant-CsHostedVoicemailPolicy para asignar la Directiva de correo de voz hospedado por usuario a usuarios individuales, grupos y objetos de contacto.</span><span class="sxs-lookup"><span data-stu-id="0daf1-110">Run the Grant-CsHostedVoicemailPolicy cmdlet to assign the per-user hosted voice mail policy to individual users, groups, and contact objects.</span></span> <span data-ttu-id="0daf1-111">Por ejemplo, ejecute lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="0daf1-111">For example, run:</span></span>
    
        Grant-CsHostedVoicemailPolicy -Identity "Ken Myer" -PolicyName ExRedmond
    
    <span data-ttu-id="0daf1-112">Este ejemplo asigna la Directiva de correo de voz hospedada de exredmond a usuario Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="0daf1-112">This example assigned the ExRedmond hosted voice mail policy to user Ken Myer.</span></span>
    
    <span data-ttu-id="0daf1-113">**Identity** especifica la cuenta de usuario que se va a modificar.</span><span class="sxs-lookup"><span data-stu-id="0daf1-113">**Identity** specifies the user account to be modified.</span></span> <span data-ttu-id="0daf1-114">El valor de identidad puede especificarse con cualquiera de los siguientes formatos:</span><span class="sxs-lookup"><span data-stu-id="0daf1-114">The Identity value can be specified using any of the following formats:</span></span>
    
      - <span data-ttu-id="0daf1-115">Dirección SIP del usuario</span><span class="sxs-lookup"><span data-stu-id="0daf1-115">The user's SIP address</span></span>
    
      - <span data-ttu-id="0daf1-116">Nombre principal de usuario de Active Directory del usuario</span><span class="sxs-lookup"><span data-stu-id="0daf1-116">The user's Active Directory User-Principal-Name</span></span>
    
      - <span data-ttu-id="0daf1-117">Nombre de inicio de\\sesión de dominio del usuario (por\\ejemplo, contoso kenmyer)</span><span class="sxs-lookup"><span data-stu-id="0daf1-117">The user's domain\\logon name (for example, contoso\\kenmyer)</span></span>
    
      - <span data-ttu-id="0daf1-118">El nombre para mostrar de los servicios de dominio de Active Directory del usuario (por ejemplo, Ken Myer).</span><span class="sxs-lookup"><span data-stu-id="0daf1-118">The user's Active Directory Domain Services Display-Name (for example, Ken Myer).</span></span> <span data-ttu-id="0daf1-119">Si usa el nombre para mostrar como valor de identidad, puede usar el carácter comodín asterisco\*().</span><span class="sxs-lookup"><span data-stu-id="0daf1-119">If using the Display-Name as the Identity value, you can use the asterisk (\*) wildcard character.</span></span> <span data-ttu-id="0daf1-120">Por ejemplo, la identidad "\* Smith" devuelve todos los usuarios que tienen un nombre para mostrar que termina con el valor de cadena "Smith".</span><span class="sxs-lookup"><span data-stu-id="0daf1-120">For example, the Identity "\* Smith" returns all the users who have a Display-Name that ends with the string value "Smith".</span></span>
    

    > [!NOTE]  
    > <span data-ttu-id="0daf1-121">El nombre de cuenta SAM del usuario de Active Directory no se puede usar como valor de identidad porque el nombre de cuenta SAM no es necesariamente único en el bosque.</span><span class="sxs-lookup"><span data-stu-id="0daf1-121">The user’s Active Directory SAM-Account-Name cannot be used as the Identity value because the SAM-Account-Name is not necessarily unique in the forest.</span></span>


