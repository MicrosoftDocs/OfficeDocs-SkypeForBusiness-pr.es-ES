---
title: 'Lync Server 2013: configuración de la vista de Galería'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring Gallery View
ms:assetid: 4a609178-47d8-4682-ac8d-29f882801924
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204871(v=OCS.15)
ms:contentKeyID: 48184069
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7333c1928bd92dbe6145f238d828e81bbeb3d868
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842245"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-gallery-view-in-lync-server-2013"></a><span data-ttu-id="0d496-102">Configuración de la vista de galería en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0d496-102">Configuring Gallery View in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0d496-103">_**Última modificación del tema:** 2012-10-30_</span><span class="sxs-lookup"><span data-stu-id="0d496-103">_**Topic Last Modified:** 2012-10-30_</span></span>

<span data-ttu-id="0d496-104">En Lync Server 2013, se configura la vista Galería de videoconferencias en Directiva de conferencia.</span><span class="sxs-lookup"><span data-stu-id="0d496-104">In Lync Server 2013, you configure Gallery View video conferencing in conferencing policy.</span></span> <span data-ttu-id="0d496-105">La vista Galería está activada de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="0d496-105">Gallery View is turned on by default.</span></span> <span data-ttu-id="0d496-106">Si no desea permitir la vista Galería, o desea permitir solo a algunos usuarios, debe desactivar la característica en Directiva de conferencia.</span><span class="sxs-lookup"><span data-stu-id="0d496-106">If you do not want to allow Gallery View, or want to allow it for only some users, you need to turn off the feature in conferencing policy.</span></span>

<span data-ttu-id="0d496-107">Cuando el vídeo de un participante de la Conferencia no está disponible, la experiencia de la vista de galería de los usuarios puede mejorarse si implementa fotos de alta resolución, una nueva característica de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="0d496-107">When a conference participant's video is not available, the users' Gallery View experience can be enhanced if you deploy high-resolution photos, a new feature in Lync Server 2013.</span></span> <span data-ttu-id="0d496-108">Las fotos de alta resolución proporcionan una alternativa a las fotos de contacto de menor tamaño y limitada almacenadas en servicios de dominio de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="0d496-108">High-resolution photos provide an alternative to the smaller, limited resolution contact photos stored in Active Directory Domain Services.</span></span> <span data-ttu-id="0d496-109">Las fotos de alta resolución se almacenan en el buzón de correo de Exchange 2013 de un usuario y, por lo tanto, requieren la integración de Lync Server 2013 con Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="0d496-109">High-resolution photos are stored in a user's Exchange 2013 mailbox, and, therefore, require you to integrate Lync Server 2013 with Exchange 2013.</span></span> <span data-ttu-id="0d496-110">Para obtener más información, vea el artículo del blog de NextHop, "integración de Exchange 2013 y Lync [http://go.microsoft.com/fwlink/p/?LinkId=260987](http://go.microsoft.com/fwlink/p/?linkid=260987)Server 2013" en.</span><span class="sxs-lookup"><span data-stu-id="0d496-110">For details, see the NextHop blog article, "Integrating Exchange 2013 and Lync Server 2013," at [http://go.microsoft.com/fwlink/p/?LinkId=260987](http://go.microsoft.com/fwlink/p/?linkid=260987).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="0d496-111">El contenido de los blogs y sus URL están sujetos a cambios sin previo aviso.</span><span class="sxs-lookup"><span data-stu-id="0d496-111">The content of each blog and its URL are subject to change without notice.</span></span>



</div>

<span data-ttu-id="0d496-112">Puede ver o modificar los parámetros de la vista de galería mediante el panel de control de Lync Server 2013 o mediante uno de los siguientes cmdlets:</span><span class="sxs-lookup"><span data-stu-id="0d496-112">You can view or modify the Gallery View parameters by using Lync Server 2013 Control Panel or by using one of the following cmdlets:</span></span>

  - <span data-ttu-id="0d496-113">**Get-CsConferencingPolicy**</span><span class="sxs-lookup"><span data-stu-id="0d496-113">**Get-CsConferencingPolicy**</span></span>

  - <span data-ttu-id="0d496-114">**Set-CsConferencingPolicy**</span><span class="sxs-lookup"><span data-stu-id="0d496-114">**Set-CsConferencingPolicy**</span></span>

  - <span data-ttu-id="0d496-115">**New-CsConferencingPolicy**</span><span class="sxs-lookup"><span data-stu-id="0d496-115">**New-CsConferencingPolicy**</span></span>

<span data-ttu-id="0d496-116">Configurar la vista de galería con la siguiente configuración de directiva de Conferencia:</span><span class="sxs-lookup"><span data-stu-id="0d496-116">Configure Gallery View with the following conferencing policy settings:</span></span>

  - <span data-ttu-id="0d496-117">**AllowMultiview**   este parámetro controla si un usuario puede organizar las videoconferencias en la galería de imágenes.</span><span class="sxs-lookup"><span data-stu-id="0d496-117">**AllowMultiview**   This parameter controls whether a user is allowed to organize Gallery View video conferences.</span></span> <span data-ttu-id="0d496-118">Este parámetro se aplica a las reuniones programadas y ad hoc creadas por el usuario.</span><span class="sxs-lookup"><span data-stu-id="0d496-118">This parameter applies to scheduled and ad-hoc meetings created by the user.</span></span>
    
    <span data-ttu-id="0d496-119">Acerca</span><span class="sxs-lookup"><span data-stu-id="0d496-119">Examples:</span></span>
    
      - <span data-ttu-id="0d496-120">Este parámetro se establece en true para el usuario A, que está alojado en un grupo de servidores de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="0d496-120">This parameter is set to True for User A, who is homed on a Lync Server 2013 pool.</span></span> <span data-ttu-id="0d496-121">Las reuniones organizadas por el usuario a permiten a los usuarios unirse y recibir varias transmisiones de vídeo.</span><span class="sxs-lookup"><span data-stu-id="0d496-121">Meetings organized by User A enable users to join and receive multiple video streams.</span></span>
    
      - <span data-ttu-id="0d496-122">Este parámetro se establece en false para el usuario B, que está alojado en un grupo de servidores de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="0d496-122">This parameter is set to False for User B, who is homed on a Lync Server 2013 pool.</span></span> <span data-ttu-id="0d496-123">Las reuniones organizadas por el usuario B tienen una sola secuencia de vídeo similar a la de la videoconferencia proporcionada por Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="0d496-123">Meetings organized by User B have a single video stream that is similar to the video conference experience provided by Lync Server 2010.</span></span>
    
    <span data-ttu-id="0d496-124">Este parámetro determina quién puede organizar reuniones que permitan varias secuencias de vídeo.</span><span class="sxs-lookup"><span data-stu-id="0d496-124">This parameter determines who can organize meetings that allow multiple video streams.</span></span> <span data-ttu-id="0d496-125">Los participantes de las reuniones que permitan varias transmisiones de vídeo pueden o no pueden recibir varias secuencias de vídeo, en función de sus permisos individuales (consulte la descripción del parámetro EnableMultiviewJoin).</span><span class="sxs-lookup"><span data-stu-id="0d496-125">Participants in meetings that allow multiple video streams may or may not be allowed to receive multiple video streams, based on their individual permissions (see the description for the EnableMultiviewJoin parameter).</span></span>

  - <span data-ttu-id="0d496-126">**EnableMultiviewJoin**   este parámetro controla si un participante de una reunión recibe la experiencia de vídeo de la vista de galería en las reuniones que lo permiten.</span><span class="sxs-lookup"><span data-stu-id="0d496-126">**EnableMultiviewJoin**   This parameter controls whether a participant in a meeting receives the Gallery View video experience in meetings that allow it.</span></span> <span data-ttu-id="0d496-127">Este parámetro controla la experiencia del usuario en cualquier reunión en la que participe.</span><span class="sxs-lookup"><span data-stu-id="0d496-127">This parameter controls the user's experience in any meeting in which he or she participates.</span></span>
    
    <span data-ttu-id="0d496-128">Acerca</span><span class="sxs-lookup"><span data-stu-id="0d496-128">Examples:</span></span>
    
      - <span data-ttu-id="0d496-129">Este parámetro se establece en true para el usuario C. el usuario C puede recibir varias transmisiones de vídeo al participar en una reunión organizada o iniciada por el usuario A. el usuario C recibe una única secuencia de vídeo que es similar a la experiencia en videoconferencias proporcionada por Lync Server 2010 cuando participar en una reunión organizada o iniciada por el usuario B.</span><span class="sxs-lookup"><span data-stu-id="0d496-129">This parameter is set to True for User C. User C can receive multiple video streams when participating in a meeting organized or started by User A. User C receives a single video stream that is similar to the video conference experience provided by Lync Server 2010 when participating in a meeting organized or started by User B.</span></span>
    
      - <span data-ttu-id="0d496-130">Este parámetro se establece en false para el usuario D. el usuario D recibe una única secuencia de vídeo que es similar a la experiencia en videoconferencias proporcionada por Lync Server 2010 cuando participa en una reunión organizada por el usuario A o el usuario B.</span><span class="sxs-lookup"><span data-stu-id="0d496-130">This parameter is set to False for User D. User D receives single video stream that is similar to the video conference experience provided by Lync Server 2010 when participating in any meeting organized by User A or User B.</span></span>

<span data-ttu-id="0d496-131">El siguiente procedimiento es un ejemplo del uso del shell de administración de Lync Server para habilitar las videoconferencias en la galería.</span><span class="sxs-lookup"><span data-stu-id="0d496-131">The following procedure is an example of using Lync Server Management Shell to enable Gallery View video conferencing.</span></span>

<div>

## <a name="to-modify-conferencing-policy-for-gallery-view-video-conferencing"></a><span data-ttu-id="0d496-132">Para modificar la Directiva de conferencia de la Galería ver videoconferencias</span><span class="sxs-lookup"><span data-stu-id="0d496-132">To modify conferencing policy for Gallery View video conferencing</span></span>

1.  <span data-ttu-id="0d496-133">Inicie el shell de administración de Lync Server: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **Shell de administración de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="0d496-133">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="0d496-134">En la línea de comandos, ejecute el cmdlet siguiente para editar la Directiva de Conferencia:</span><span class="sxs-lookup"><span data-stu-id="0d496-134">At the command line, run the following cmdlet to edit conferencing policy:</span></span>
    
        Set-CsConferencingPolicy -Identity Pool01ConferencingPolicy -AllowMultiview $true -EnableMultiviewJoin $true 

</div>

</div>

<span> </span>

</div>

</div>

</div>

