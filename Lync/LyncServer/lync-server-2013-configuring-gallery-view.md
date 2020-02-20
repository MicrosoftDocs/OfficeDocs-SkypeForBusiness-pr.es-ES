---
title: 'Lync Server 2013: configuración de la vista de Galería'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Gallery View
ms:assetid: 4a609178-47d8-4682-ac8d-29f882801924
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204871(v=OCS.15)
ms:contentKeyID: 48184069
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 02c13f2b1fa312394edfaba01ecd05179f86a0c9
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151430"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-gallery-view-in-lync-server-2013"></a><span data-ttu-id="e9352-102">Configuración de la vista de galería en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e9352-102">Configuring Gallery View in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e9352-103">_**Última modificación del tema:** 2012-10-30_</span><span class="sxs-lookup"><span data-stu-id="e9352-103">_**Topic Last Modified:** 2012-10-30_</span></span>

<span data-ttu-id="e9352-104">En Lync Server 2013, se configura la Conferencia de vídeo de vista de galería en la Directiva de conferencia.</span><span class="sxs-lookup"><span data-stu-id="e9352-104">In Lync Server 2013, you configure Gallery View video conferencing in conferencing policy.</span></span> <span data-ttu-id="e9352-105">La Vista Galería se activa de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="e9352-105">Gallery View is turned on by default.</span></span> <span data-ttu-id="e9352-106">Si no desea permitir la Vista Galería o desea permitirla solo para algunos usuarios, deberá desactivar la función en la directiva de conferencias.</span><span class="sxs-lookup"><span data-stu-id="e9352-106">If you do not want to allow Gallery View, or want to allow it for only some users, you need to turn off the feature in conferencing policy.</span></span>

<span data-ttu-id="e9352-107">Cuando el vídeo de un participante de la Conferencia no está disponible, la experiencia de visualización de la galería de los usuarios se puede mejorar si implementa fotos de alta resolución, una nueva característica en Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e9352-107">When a conference participant's video is not available, the users' Gallery View experience can be enhanced if you deploy high-resolution photos, a new feature in Lync Server 2013.</span></span> <span data-ttu-id="e9352-108">Las fotos de alta resolución proporcionan una alternativa a las fotos de contacto de resolución limitada más pequeñas y de menor tamaño almacenadas en los servicios de dominio de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="e9352-108">High-resolution photos provide an alternative to the smaller, limited resolution contact photos stored in Active Directory Domain Services.</span></span> <span data-ttu-id="e9352-109">Las fotos de alta resolución se almacenan en el buzón de correo de Exchange 2013 del usuario y, por lo tanto, requieren la integración de Lync Server 2013 con Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="e9352-109">High-resolution photos are stored in a user's Exchange 2013 mailbox, and, therefore, require you to integrate Lync Server 2013 with Exchange 2013.</span></span> <span data-ttu-id="e9352-110">Para obtener información detallada, consulte el artículo del blog NextHop, "integración de Exchange 2013 y Lync Server [https://go.microsoft.com/fwlink/p/?LinkId=260987](https://go.microsoft.com/fwlink/p/?linkid=260987)2013", en.</span><span class="sxs-lookup"><span data-stu-id="e9352-110">For details, see the NextHop blog article, "Integrating Exchange 2013 and Lync Server 2013," at [https://go.microsoft.com/fwlink/p/?LinkId=260987](https://go.microsoft.com/fwlink/p/?linkid=260987).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e9352-111">El contenido de cada blog y su dirección URL están sujetos a cambio sin previo aviso.</span><span class="sxs-lookup"><span data-stu-id="e9352-111">The content of each blog and its URL are subject to change without notice.</span></span>



</div>

<span data-ttu-id="e9352-112">Puede ver o modificar los parámetros de la vista de galería mediante el panel de control de Lync Server 2013 o mediante uno de los siguientes cmdlets:</span><span class="sxs-lookup"><span data-stu-id="e9352-112">You can view or modify the Gallery View parameters by using Lync Server 2013 Control Panel or by using one of the following cmdlets:</span></span>

  - <span data-ttu-id="e9352-113">**Get-CsConferencingPolicy**</span><span class="sxs-lookup"><span data-stu-id="e9352-113">**Get-CsConferencingPolicy**</span></span>

  - <span data-ttu-id="e9352-114">**Set-CsConferencingPolicy**</span><span class="sxs-lookup"><span data-stu-id="e9352-114">**Set-CsConferencingPolicy**</span></span>

  - <span data-ttu-id="e9352-115">**New-CsConferencingPolicy**</span><span class="sxs-lookup"><span data-stu-id="e9352-115">**New-CsConferencingPolicy**</span></span>

<span data-ttu-id="e9352-116">Configure Vista Galería con los siguientes parámetros de directiva de conferencia:</span><span class="sxs-lookup"><span data-stu-id="e9352-116">Configure Gallery View with the following conferencing policy settings:</span></span>

  - <span data-ttu-id="e9352-117">**AllowMultiview**   este parámetro controla si un usuario puede organizar las videoconferencias de vista de galería.</span><span class="sxs-lookup"><span data-stu-id="e9352-117">**AllowMultiview**   This parameter controls whether a user is allowed to organize Gallery View video conferences.</span></span> <span data-ttu-id="e9352-118">Este parámetro se aplica a reuniones programadas y ad-hoc creadas por el usuario.</span><span class="sxs-lookup"><span data-stu-id="e9352-118">This parameter applies to scheduled and ad-hoc meetings created by the user.</span></span>
    
    <span data-ttu-id="e9352-119">Ejemplos:</span><span class="sxs-lookup"><span data-stu-id="e9352-119">Examples:</span></span>
    
      - <span data-ttu-id="e9352-120">Este parámetro se establece en true para el usuario A, que está hospedado en un grupo de servidores de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e9352-120">This parameter is set to True for User A, who is homed on a Lync Server 2013 pool.</span></span> <span data-ttu-id="e9352-121">Las reuniones organizadas por el usuario A permiten a los usuarios unirse y recibir múltiples secuencias de vídeo.</span><span class="sxs-lookup"><span data-stu-id="e9352-121">Meetings organized by User A enable users to join and receive multiple video streams.</span></span>
    
      - <span data-ttu-id="e9352-122">Este parámetro se establece en false para el usuario B, que está hospedado en un grupo de servidores de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e9352-122">This parameter is set to False for User B, who is homed on a Lync Server 2013 pool.</span></span> <span data-ttu-id="e9352-123">Las reuniones organizadas por el usuario B tienen una única secuencia de vídeo similar a la experiencia de conferencia de vídeo que proporciona Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="e9352-123">Meetings organized by User B have a single video stream that is similar to the video conference experience provided by Lync Server 2010.</span></span>
    
    <span data-ttu-id="e9352-p106">Este parámetro determina quién puede organizar reuniones que permiten múltiples secuencias de vídeo. Los participantes en las reuniones que permiten múltiples secuencias de vídeo pueden o no puede recibir múltiples secuencias de vídeo, basándose en sus permisos individuales (vea la descripción del parámetro EnableMultiviewJoin).</span><span class="sxs-lookup"><span data-stu-id="e9352-p106">This parameter determines who can organize meetings that allow multiple video streams. Participants in meetings that allow multiple video streams may or may not be allowed to receive multiple video streams, based on their individual permissions (see the description for the EnableMultiviewJoin parameter).</span></span>

  - <span data-ttu-id="e9352-126">**EnableMultiviewJoin**   este parámetro controla si un participante de una reunión recibe la experiencia de vídeo de la vista de galería en las reuniones que la permiten.</span><span class="sxs-lookup"><span data-stu-id="e9352-126">**EnableMultiviewJoin**   This parameter controls whether a participant in a meeting receives the Gallery View video experience in meetings that allow it.</span></span> <span data-ttu-id="e9352-127">Este parámetro controla la experiencia del usuario en cualquier reunión en la que él o ella participe.</span><span class="sxs-lookup"><span data-stu-id="e9352-127">This parameter controls the user's experience in any meeting in which he or she participates.</span></span>
    
    <span data-ttu-id="e9352-128">Ejemplos:</span><span class="sxs-lookup"><span data-stu-id="e9352-128">Examples:</span></span>
    
      - <span data-ttu-id="e9352-129">Este parámetro se establece en true para el usuario C. el usuario c puede recibir varias secuencias de vídeo cuando participa en una reunión organizada o iniciada por el usuario A. el usuario C recibe una única secuencia de vídeo que es similar a la experiencia de la Conferencia de vídeo que proporciona Lync Server 2010 cuando participar en una reunión organizada o iniciada por el usuario B.</span><span class="sxs-lookup"><span data-stu-id="e9352-129">This parameter is set to True for User C. User C can receive multiple video streams when participating in a meeting organized or started by User A. User C receives a single video stream that is similar to the video conference experience provided by Lync Server 2010 when participating in a meeting organized or started by User B.</span></span>
    
      - <span data-ttu-id="e9352-130">Este parámetro se establece en false para el usuario D. el usuario D recibe una única secuencia de vídeo similar a la experiencia de videoconferencia que proporciona Lync Server 2010 cuando participa en cualquier reunión organizada por el usuario A o el usuario B.</span><span class="sxs-lookup"><span data-stu-id="e9352-130">This parameter is set to False for User D. User D receives single video stream that is similar to the video conference experience provided by Lync Server 2010 when participating in any meeting organized by User A or User B.</span></span>

<span data-ttu-id="e9352-131">El siguiente procedimiento es un ejemplo del uso del shell de administración de Lync Server para habilitar la Conferencia de vídeo de vista de galería.</span><span class="sxs-lookup"><span data-stu-id="e9352-131">The following procedure is an example of using Lync Server Management Shell to enable Gallery View video conferencing.</span></span>

<div>

## <a name="to-modify-conferencing-policy-for-gallery-view-video-conferencing"></a><span data-ttu-id="e9352-132">Para modificar la directiva de conferencias para conferencias de de vídeo de Vista Galería</span><span class="sxs-lookup"><span data-stu-id="e9352-132">To modify conferencing policy for Gallery View video conferencing</span></span>

1.  <span data-ttu-id="e9352-133">Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="e9352-133">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="e9352-134">En la línea de comandos, ejecute el cmdlet siguiente para cambiar la directiva de conferencia:</span><span class="sxs-lookup"><span data-stu-id="e9352-134">At the command line, run the following cmdlet to edit conferencing policy:</span></span>
    
        Set-CsConferencingPolicy -Identity Pool01ConferencingPolicy -AllowMultiview $true -EnableMultiviewJoin $true 

</div>

</div>

<span> </span>

</div>

</div>

</div>

