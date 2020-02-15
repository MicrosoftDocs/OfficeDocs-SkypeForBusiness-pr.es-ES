---
title: 'Lync Server 2013: configurar la Directiva de conferencias para el acceso telefónico local'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure conferencing policy for dial-in
ms:assetid: 9bf926d6-0248-4352-98c3-9c5a333debbc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398810(v=OCS.15)
ms:contentKeyID: 48184979
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 56faf9cb55312beec0714eb84757d92989b1b3ad
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42028661"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-conferencing-policy-for-dial-in-in-lync-server-2013"></a><span data-ttu-id="3c949-102">Configurar la Directiva de conferencias para el acceso telefónico en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3c949-102">Configure conferencing policy for dial-in in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3c949-103">_**Última modificación del tema:** 2014-03-21_</span><span class="sxs-lookup"><span data-stu-id="3c949-103">_**Topic Last Modified:** 2014-03-21_</span></span>

<span data-ttu-id="3c949-p101">Las directivas de conferencias son una opción de cuenta de usuario que especifica la experiencia de conferencia de los participantes. Puede crear directivas de conferencia cuyo ámbito sea de sitio o de usuario. La configuración de directiva de conferencias abarca muchos aspectos de la programación de conferencias y de la participación en ellas. Varias configuraciones de directiva de conferencias admiten las conferencias de acceso telefónico local para los participantes. Cuando configure la característica de conferencia de acceso telefónico local, debe comprobar que estos campos estén definidos de la forma apropiada para su organización, y modificarlos según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="3c949-p101">Conferencing policy is a user account setting that specifies the conferencing experience for participants. You can create conferencing policies with a site scope or a user scope. Conferencing policy settings encompass many aspects of conference scheduling and participation. Several conferencing policy settings support dial-in conferencing for participants. When you configure dial-in conferencing, you should verify that these fields are set appropriately for your organization, and modify them as necessary.</span></span>

<span data-ttu-id="3c949-109">Compruebe los campos siguientes en la directiva de conferencias:</span><span class="sxs-lookup"><span data-stu-id="3c949-109">Verify the following fields in your conferencing policy:</span></span>

  - <span data-ttu-id="3c949-110">**Permitir a los participantes invitar a usuarios anónimos**   esta configuración permite a los organizadores de reuniones invitar a las reuniones a los participantes anónimos (es decir, no autenticados).</span><span class="sxs-lookup"><span data-stu-id="3c949-110">**Allow participants to invite anonymous users**   This setting allows meeting organizers to invite anonymous (that is, unauthenticated) participants to meetings.</span></span> <span data-ttu-id="3c949-111">No es obligatoria para las conferencias de acceso telefónico local.</span><span class="sxs-lookup"><span data-stu-id="3c949-111">This setting is optional for dial-in conferencing.</span></span> <span data-ttu-id="3c949-112">Esta opción está seleccionada de forma predeterminada en la directiva de conferencias global predeterminada.</span><span class="sxs-lookup"><span data-stu-id="3c949-112">This setting is selected by default in the default global conferencing policy.</span></span>

  - <span data-ttu-id="3c949-113">**Habilitar Conferencia**   de acceso telefónico local RTC esta configuración permite a los usuarios unirse a la parte de audio de una conferencia mediante el marcado desde la RTC.</span><span class="sxs-lookup"><span data-stu-id="3c949-113">**Enable PSTN dial-in conferencing**   This setting allows users to join the audio portion of a conference by dialing in from the PSTN.</span></span> <span data-ttu-id="3c949-114">Esta opción es obligatoria para las conferencias de acceso telefónico local.</span><span class="sxs-lookup"><span data-stu-id="3c949-114">This setting is required for dial-in conferencing.</span></span> <span data-ttu-id="3c949-115">Esta opción está seleccionada de forma predeterminada en la directiva de conferencias global predeterminada.</span><span class="sxs-lookup"><span data-stu-id="3c949-115">This setting is selected by default in the default global conferencing policy.</span></span>

  - <span data-ttu-id="3c949-116">**Permitir que los participantes anónimos marquen**   esta configuración permite a los usuarios anónimos que ya están Unidos a la reunión llamar a un número de teléfono para unirse a la parte de audio de la Conferencia.</span><span class="sxs-lookup"><span data-stu-id="3c949-116">**Allow anonymous participants to dial out**   This setting allows anonymous users who are already joined to the meeting to dial out to a phone number to join the audio portion of the conference.</span></span> <span data-ttu-id="3c949-117">No es obligatoria para las conferencias de acceso telefónico local.</span><span class="sxs-lookup"><span data-stu-id="3c949-117">This setting is optional for dial-in conferencing.</span></span> <span data-ttu-id="3c949-118">Esta opción no está seleccionada de forma predeterminada en la directiva de conferencias global predeterminada.</span><span class="sxs-lookup"><span data-stu-id="3c949-118">This setting is not selected by default in the default global conferencing policy.</span></span>

  - <span data-ttu-id="3c949-119">**Permitir que los participantes no habilitados para telefonía IP empresarial marquen**   esta configuración permite a los participantes de la reunión y los organizadores que no están habilitados para telefonía IP empresarial llamar a un número de teléfono para unirse a la parte de audio de la Conferencia.</span><span class="sxs-lookup"><span data-stu-id="3c949-119">**Allow participants not enabled for Enterprise Voice to dial out**   This setting allows meeting participants and organizers that are not enabled for Enterprise Voice to dial out to a phone number to join the audio portion of the conference.</span></span> <span data-ttu-id="3c949-120">La llamada de salida se autoriza según la directiva de voz asignada por el organizador.</span><span class="sxs-lookup"><span data-stu-id="3c949-120">The dial-out call is authorized based on the organizer’s assigned voice policy.</span></span> <span data-ttu-id="3c949-121">Esta opción no está seleccionada de forma predeterminada en la directiva de conferencias global predeterminada.</span><span class="sxs-lookup"><span data-stu-id="3c949-121">This setting is not selected by default in the default global conferencing policy.</span></span> <span data-ttu-id="3c949-122">El valor predeterminado está deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="3c949-122">The setting default value is disabled.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="3c949-123">Para habilitar esta función, un organizador de la reunión que no está habilitado para Enterprise Voice debe tener asignada una directiva de voz adecuada para autorizar cualquier aceptación de llamada desde una conferencia organizada por dicho usuario.</span><span class="sxs-lookup"><span data-stu-id="3c949-123">To enable this capability, a meeting organizer that is not enabled for Enterprise Voice should have an appropriate voice policy assigned to them to authorize any dial-out from a conference organized by that user.</span></span> <span data-ttu-id="3c949-124">Se puede asignar una directiva de voz a un usuario que no está habilitado para telefonía IP empresarial desde el shell de administración de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="3c949-124">A voice policy can be assigned to a user that is not enabled for Enterprise Voice from the Lync Server Management Shell.</span></span> <span data-ttu-id="3c949-125">Si el usuario no tiene una directiva de voz asignada explícitamente, se usará la Directiva de voz del sitio para autorizar la solicitud de acceso telefónico.</span><span class="sxs-lookup"><span data-stu-id="3c949-125">If the user does not have a voice policy explicitly assigned to him, the site voice policy will be used to authorize the dial-out request.</span></span> <span data-ttu-id="3c949-126">Si no hay ninguna directiva de voz de sitio, se usará la Directiva de voz global.&nbsp;</span><span class="sxs-lookup"><span data-stu-id="3c949-126">If there is no site voice policy, the global voice policy will be used.&nbsp;</span></span>

    
    </div>

<span data-ttu-id="3c949-127">El procedimiento descrito en esta sección explica cómo modificar la directiva de conferencia.</span><span class="sxs-lookup"><span data-stu-id="3c949-127">The procedure in this section explains how to modify conferencing policy.</span></span> <span data-ttu-id="3c949-128">Para obtener más información sobre cómo configurar todas las opciones que definen la experiencia del participante en la Directiva de conferencia predeterminada, vea [crear o modificar una colección de opciones de configuración de reuniones en Lync Server 2013](lync-server-2013-create-or-modify-a-collection-of-meeting-configuration-settings.md).</span><span class="sxs-lookup"><span data-stu-id="3c949-128">For details about how to configure all of the settings that define the participant experience in the default conferencing policy, see [Create or modify a collection of meeting configuration settings in Lync Server 2013](lync-server-2013-create-or-modify-a-collection-of-meeting-configuration-settings.md).</span></span> <span data-ttu-id="3c949-129">Para obtener más información sobre cómo crear una directiva de conferencia para un usuario o grupo de usuarios específico, vea [Create or Modify a Conferencing Policy in Lync Server 2013](lync-server-2013-create-or-modify-a-conferencing-policy.md).</span><span class="sxs-lookup"><span data-stu-id="3c949-129">For details about how to create a conferencing policy for a specific user or group of users, see [Create or modify a conferencing policy in Lync Server 2013](lync-server-2013-create-or-modify-a-conferencing-policy.md).</span></span> <span data-ttu-id="3c949-130">Para obtener una lista de todas las opciones de configuración de directivas de conferencia disponibles, consulte [referencia de configuración de directivas de conferencia para Lync Server 2013](lync-server-2013-conferencing-policy-settings-reference.md).</span><span class="sxs-lookup"><span data-stu-id="3c949-130">For a list of all available conferencing policy settings, see [Conferencing policy settings reference for Lync Server 2013](lync-server-2013-conferencing-policy-settings-reference.md).</span></span>

<div>

## <a name="to-modify-the-conferencing-policy-for-dial-in"></a><span data-ttu-id="3c949-131">Para modificar la directiva de conferencias para el acceso telefónico</span><span class="sxs-lookup"><span data-stu-id="3c949-131">To modify the conferencing policy for dial-in</span></span>

1.  <span data-ttu-id="3c949-132">Inicie sesión en el equipo como miembro del grupo RTCUniversalServerAdmins o como miembro del rol **Cs-ServerAdministrator** o **CsAdministrator**.</span><span class="sxs-lookup"><span data-stu-id="3c949-132">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **Cs-ServerAdministrator** or **CsAdministrator** role.</span></span>

2.  <span data-ttu-id="3c949-133">Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="3c949-133">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="3c949-134">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="3c949-134">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="3c949-135">En la barra de navegación izquierda, haga clic en **Conferencia**.</span><span class="sxs-lookup"><span data-stu-id="3c949-135">In the left navigation bar, click **Conferencing**.</span></span>

4.  <span data-ttu-id="3c949-136">En la pestaña **Directiva de conferencias**, haga doble clic en el nombre de una directiva de conferencias para abrir el cuadro de diálogo **Editar directiva de conferencia**.</span><span class="sxs-lookup"><span data-stu-id="3c949-136">On the **Conferencing Policy** tab, double-click a conferencing policy name to open the **Edit Conferencing Policy** dialog box.</span></span>

5.  <span data-ttu-id="3c949-137">Compruebe que los campos de conferencia de acceso telefónico local sean adecuados para su organización y modifique la configuración si es necesario.</span><span class="sxs-lookup"><span data-stu-id="3c949-137">Verify that the fields for dial-in conferencing are appropriate for your organization, and modify the settings if necessary.</span></span>

6.  <span data-ttu-id="3c949-138">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="3c949-138">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

