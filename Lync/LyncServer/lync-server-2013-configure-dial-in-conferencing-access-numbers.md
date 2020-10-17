---
title: 'Lync Server 2013: configurar los números de acceso de conferencia de acceso telefónico local'
description: 'Lync Server 2013: configurar los números de acceso de conferencia de acceso telefónico local.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure dial-in conferencing access numbers
ms:assetid: d8a18030-f318-43dd-834d-70e5014b5e8a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398952(v=OCS.15)
ms:contentKeyID: 48185623
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0edb3492c243b36b69c4b48df8c22adc4ece7999
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48565086"
---
# <a name="configure-dial-in-conferencing-access-numbers-in-lync-server-2013"></a><span data-ttu-id="fb475-103">Configurar los números de acceso de conferencia de acceso telefónico local en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fb475-103">Configure dial-in conferencing access numbers in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fb475-104">_**Última modificación del tema:** 2011-07-17_</span><span class="sxs-lookup"><span data-stu-id="fb475-104">_**Topic Last Modified:** 2011-07-17_</span></span>

<span data-ttu-id="fb475-105">Al implementar la Conferencia de acceso telefónico local, debe configurar los números de teléfono que los usuarios pueden marcar desde la red telefónica conmutada (RTC) para unirse a la parte de audio de las conferencias.</span><span class="sxs-lookup"><span data-stu-id="fb475-105">When you deploy dial-in conferencing, you need to set up phone numbers that users can dial from the public switched telephone network (PSTN) to join the audio portion of conferences.</span></span> <span data-ttu-id="fb475-106">Estos números de acceso telefónico aparecen en las invitaciones a reuniones y en la Página Web de configuración de conferencia de acceso telefónico local.</span><span class="sxs-lookup"><span data-stu-id="fb475-106">These dial-in access numbers appear in meeting invitations and on the Dial-in Conferencing Settings webpage.</span></span>

<span data-ttu-id="fb475-107">Antes de poder crear números de acceso telefónico local, primero debe planear las regiones de conferencia de acceso telefónico local y, a continuación, configurar los planes de marcado con las regiones.</span><span class="sxs-lookup"><span data-stu-id="fb475-107">Before you can create dial-in access numbers, you must first plan your dial-in conferencing regions and then configure dial plans with the regions.</span></span> <span data-ttu-id="fb475-108">Para obtener más información sobre las regiones, consulte [requisitos de conferencias de acceso telefónico local en Lync Server 2013](lync-server-2013-dial-in-conferencing-requirements.md) en la documentación referente a la planeación.</span><span class="sxs-lookup"><span data-stu-id="fb475-108">For details about regions, see [Dial-in conferencing requirements in Lync Server 2013](lync-server-2013-dial-in-conferencing-requirements.md) in the Planning documentation.</span></span> <span data-ttu-id="fb475-109">Para obtener más información sobre cómo configurar planes de marcado para las conferencias de acceso telefónico local, consulte [configurar planes de marcado para las conferencias de acceso telefónico local en Lync Server 2013](lync-server-2013-configure-dial-plans-for-dial-in-conferencing.md).</span><span class="sxs-lookup"><span data-stu-id="fb475-109">For details about configuring dial plans for dial-in conferencing, see [Configure dial plans for dial-in conferencing in Lync Server 2013](lync-server-2013-configure-dial-plans-for-dial-in-conferencing.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="fb475-110">No se puede usar un nuevo número de acceso telefónico hasta que se complete la replicación de servicios de dominio de Active Directory (AD &nbsp; DS) de ese número de acceso.</span><span class="sxs-lookup"><span data-stu-id="fb475-110">You cannot use a new dial-in access number until Active Directory Domain Services (AD&nbsp;DS) replication of that access number is complete.</span></span> <span data-ttu-id="fb475-111">La replicación puede tardar varias horas en completarse.</span><span class="sxs-lookup"><span data-stu-id="fb475-111">Replication can take several hours to complete.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="fb475-112">Después de crear los números de acceso telefónico local, puede modificar el nombre para mostrar de los objetos de contacto de Active Directory para que los usuarios puedan identificar más fácilmente el número de acceso correcto.</span><span class="sxs-lookup"><span data-stu-id="fb475-112">After you create dial-in access numbers, you can modify the display name for the Active Directory contact objects so that users can more easily identify the correct access number.</span></span> <span data-ttu-id="fb475-113">Use el cmdlet <STRONG>set-CsDialInConferencingAccessNumber</STRONG> para modificar el nombre para mostrar.</span><span class="sxs-lookup"><span data-stu-id="fb475-113">Use the <STRONG>Set-CsDialInConferencingAccessNumber</STRONG> cmdlet to modify the display name.</span></span> <span data-ttu-id="fb475-114">No debe modificar los objetos de Active Directory de forma manual.</span><span class="sxs-lookup"><span data-stu-id="fb475-114">You should not modify Active Directory objects manually.</span></span> <span data-ttu-id="fb475-115">Para obtener información detallada sobre cómo modificar un número de acceso, consulte Lync Server Management Shell Documentation for the <STRONG>set-CsDialInConferencingAccessNumber</STRONG> cmdlet.</span><span class="sxs-lookup"><span data-stu-id="fb475-115">For details about modifying an access number, see Lync Server Management Shell documentation for the <STRONG>Set-CsDialInConferencingAccessNumber</STRONG> cmdlet.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="fb475-116">En esta sección</span><span class="sxs-lookup"><span data-stu-id="fb475-116">In This Section</span></span>

[<span data-ttu-id="fb475-117">Crear o modificar un número de acceso de conferencia de acceso telefónico local en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fb475-117">Create or modify a dial-in conferencing access number in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-dial-in-conferencing-access-number.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="fb475-118">Consulte también</span><span class="sxs-lookup"><span data-stu-id="fb475-118">See Also</span></span>


[<span data-ttu-id="fb475-119">Requisitos de conferencia de acceso telefónico local en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fb475-119">Dial-in conferencing requirements in Lync Server 2013</span></span>](lync-server-2013-dial-in-conferencing-requirements.md)  


[<span data-ttu-id="fb475-120">Configurar planes de marcado para las conferencias de acceso telefónico local en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fb475-120">Configure dial plans for dial-in conferencing in Lync Server 2013</span></span>](lync-server-2013-configure-dial-plans-for-dial-in-conferencing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

