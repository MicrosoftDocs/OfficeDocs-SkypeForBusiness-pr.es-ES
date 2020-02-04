---
title: 'Lync Server 2013: Configurar números de conferencia de acceso telefónico'
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
ms.openlocfilehash: e19d594b8d1661a314b834e6c2e92d8668490ad7
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757914"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-dial-in-conferencing-access-numbers-in-lync-server-2013"></a><span data-ttu-id="6aa10-102">Configurar números de conferencia de acceso telefónico en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6aa10-102">Configure dial-in conferencing access numbers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6aa10-103">_**Última modificación del tema:** 2011-07-17_</span><span class="sxs-lookup"><span data-stu-id="6aa10-103">_**Topic Last Modified:** 2011-07-17_</span></span>

<span data-ttu-id="6aa10-104">Cuando se implementa la característica de conferencia de acceso telefónico local, es necesario establecer números de teléfono que los usuarios puedan marcar desde la red telefónica conmutada (RTC) para unirse a la parte de audio de las conferencias.</span><span class="sxs-lookup"><span data-stu-id="6aa10-104">When you deploy dial-in conferencing, you need to set up phone numbers that users can dial from the public switched telephone network (PSTN) to join the audio portion of conferences.</span></span> <span data-ttu-id="6aa10-105">Estos números de acceso telefónico se muestran en invitaciones a reuniones y en la página web de configuración de conferencia de acceso telefónico local.</span><span class="sxs-lookup"><span data-stu-id="6aa10-105">These dial-in access numbers appear in meeting invitations and on the Dial-in Conferencing Settings webpage.</span></span>

<span data-ttu-id="6aa10-106">Antes de poder crear números de acceso telefónico local, necesita planear las regiones de conferencia de acceso telefónico local y luego configurar planes de marcado con las regiones.</span><span class="sxs-lookup"><span data-stu-id="6aa10-106">Before you can create dial-in access numbers, you must first plan your dial-in conferencing regions and then configure dial plans with the regions.</span></span> <span data-ttu-id="6aa10-107">Para obtener más información sobre las regiones, consulte requisitos de las [conferencias de acceso telefónico local en Lync Server 2013](lync-server-2013-dial-in-conferencing-requirements.md) en la documentación de planeación.</span><span class="sxs-lookup"><span data-stu-id="6aa10-107">For details about regions, see [Dial-in conferencing requirements in Lync Server 2013](lync-server-2013-dial-in-conferencing-requirements.md) in the Planning documentation.</span></span> <span data-ttu-id="6aa10-108">Para obtener más información sobre cómo configurar planes de marcado para conferencias de acceso telefónico local, consulte [configurar planes de marcado para conferencias de acceso telefónico local en Lync Server 2013](lync-server-2013-configure-dial-plans-for-dial-in-conferencing.md).</span><span class="sxs-lookup"><span data-stu-id="6aa10-108">For details about configuring dial plans for dial-in conferencing, see [Configure dial plans for dial-in conferencing in Lync Server 2013](lync-server-2013-configure-dial-plans-for-dial-in-conferencing.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="6aa10-109">No puede usar un nuevo número de acceso telefónico local hasta que se complete la replicación de&nbsp;servicios de dominio de Active Directory (AD DS) de ese número de acceso.</span><span class="sxs-lookup"><span data-stu-id="6aa10-109">You cannot use a new dial-in access number until Active Directory Domain Services (AD&nbsp;DS) replication of that access number is complete.</span></span> <span data-ttu-id="6aa10-110">La replicación puede prolongarse durante varias horas.</span><span class="sxs-lookup"><span data-stu-id="6aa10-110">Replication can take several hours to complete.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="6aa10-111">Una vez creados los números de acceso telefónico local, puede modificar el nombre para mostrar de los objetos de contacto de Active Directory, de modo que los usuarios puedan identificar con mayor facilidad el número de acceso correcto.</span><span class="sxs-lookup"><span data-stu-id="6aa10-111">After you create dial-in access numbers, you can modify the display name for the Active Directory contact objects so that users can more easily identify the correct access number.</span></span> <span data-ttu-id="6aa10-112">Use el cmdlet <STRONG>set-CsDialInConferencingAccessNumber</STRONG> para modificar el nombre para mostrar.</span><span class="sxs-lookup"><span data-stu-id="6aa10-112">Use the <STRONG>Set-CsDialInConferencingAccessNumber</STRONG> cmdlet to modify the display name.</span></span> <span data-ttu-id="6aa10-113">No modifique los objetos de Active Directory manualmente.</span><span class="sxs-lookup"><span data-stu-id="6aa10-113">You should not modify Active Directory objects manually.</span></span> <span data-ttu-id="6aa10-114">Para obtener detalles sobre cómo modificar un número de acceso, consulte la documentación del shell de administración de Lync Server para el cmdlet <STRONG>set-CsDialInConferencingAccessNumber</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="6aa10-114">For details about modifying an access number, see Lync Server Management Shell documentation for the <STRONG>Set-CsDialInConferencingAccessNumber</STRONG> cmdlet.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="6aa10-115">En esta sección</span><span class="sxs-lookup"><span data-stu-id="6aa10-115">In This Section</span></span>

[<span data-ttu-id="6aa10-116">Crear o modificar un número de acceso para conferencias de acceso telefónico local en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6aa10-116">Create or modify a dial-in conferencing access number in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-dial-in-conferencing-access-number.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="6aa10-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="6aa10-117">See Also</span></span>


[<span data-ttu-id="6aa10-118">Requisitos de las conferencias de acceso telefónico local en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6aa10-118">Dial-in conferencing requirements in Lync Server 2013</span></span>](lync-server-2013-dial-in-conferencing-requirements.md)  


[<span data-ttu-id="6aa10-119">Configurar planes de marcado para las conferencias de acceso telefónico local en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6aa10-119">Configure dial plans for dial-in conferencing in Lync Server 2013</span></span>](lync-server-2013-configure-dial-plans-for-dial-in-conferencing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

