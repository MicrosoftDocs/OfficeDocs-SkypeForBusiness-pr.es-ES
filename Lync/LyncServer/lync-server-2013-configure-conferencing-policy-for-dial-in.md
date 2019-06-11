---
title: 'Lync Server 2013: Configurar la directiva de conferencias para el acceso telefónico local'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure conferencing policy for dial-in
ms:assetid: 9bf926d6-0248-4352-98c3-9c5a333debbc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398810(v=OCS.15)
ms:contentKeyID: 48184979
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 74621fee97a1e6721f8772b265761b62b1b9f266
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842406"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-conferencing-policy-for-dial-in-in-lync-server-2013"></a><span data-ttu-id="bb97e-102">Configurar la directiva de conferencias para el acceso telefónico local en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bb97e-102">Configure conferencing policy for dial-in in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bb97e-103">_**Última modificación del tema:** 2014-03-21_</span><span class="sxs-lookup"><span data-stu-id="bb97e-103">_**Topic Last Modified:** 2014-03-21_</span></span>

<span data-ttu-id="bb97e-p101">Las directivas de conferencias son una opción de cuenta de usuario que especifica la experiencia de conferencia de los participantes. Puede crear directivas de conferencia cuyo ámbito sea de sitio o de usuario. La configuración de directiva de conferencias abarca muchos aspectos de la programación de conferencias y de la participación en ellas. Varias configuraciones de directiva de conferencias admiten las conferencias de acceso telefónico local para los participantes. Cuando configure la característica de conferencia de acceso telefónico local, debe comprobar que estos campos estén definidos de la forma apropiada para su organización, y modificarlos según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="bb97e-p101">Conferencing policy is a user account setting that specifies the conferencing experience for participants. You can create conferencing policies with a site scope or a user scope. Conferencing policy settings encompass many aspects of conference scheduling and participation. Several conferencing policy settings support dial-in conferencing for participants. When you configure dial-in conferencing, you should verify that these fields are set appropriately for your organization, and modify them as necessary.</span></span>

<span data-ttu-id="bb97e-109">Compruebe los siguientes campos de su Directiva de Conferencia:</span><span class="sxs-lookup"><span data-stu-id="bb97e-109">Verify the following fields in your conferencing policy:</span></span>

  - <span data-ttu-id="bb97e-110">**Permitir a los participantes invitar a usuarios anónimos**   esta configuración permite a los organizadores de reuniones invitar a reuniones anónimos (es decir, no autenticados).</span><span class="sxs-lookup"><span data-stu-id="bb97e-110">**Allow participants to invite anonymous users**   This setting allows meeting organizers to invite anonymous (that is, unauthenticated) participants to meetings.</span></span> <span data-ttu-id="bb97e-111">Esta configuración es opcional para las conferencias de acceso telefónico local.</span><span class="sxs-lookup"><span data-stu-id="bb97e-111">This setting is optional for dial-in conferencing.</span></span> <span data-ttu-id="bb97e-112">Esta opción está seleccionada de forma predeterminada en la Directiva de conferencia global predeterminada.</span><span class="sxs-lookup"><span data-stu-id="bb97e-112">This setting is selected by default in the default global conferencing policy.</span></span>

  - <span data-ttu-id="bb97e-113">**Habilitar Conferencia**   de acceso telefónico PSTN esta configuración permite a los usuarios unirse a la parte de audio de una conferencia mediante el marcado desde la RTC.</span><span class="sxs-lookup"><span data-stu-id="bb97e-113">**Enable PSTN dial-in conferencing**   This setting allows users to join the audio portion of a conference by dialing in from the PSTN.</span></span> <span data-ttu-id="bb97e-114">Esta configuración es necesaria para las conferencias de acceso telefónico local.</span><span class="sxs-lookup"><span data-stu-id="bb97e-114">This setting is required for dial-in conferencing.</span></span> <span data-ttu-id="bb97e-115">Esta opción está seleccionada de forma predeterminada en la Directiva de conferencia global predeterminada.</span><span class="sxs-lookup"><span data-stu-id="bb97e-115">This setting is selected by default in the default global conferencing policy.</span></span>

  - <span data-ttu-id="bb97e-116">**Permitir a los participantes anónimos marcar**   esta configuración permite que los usuarios anónimos que ya se hayan unido a la reunión llamen a un número de teléfono para unirse a la parte de audio de la Conferencia.</span><span class="sxs-lookup"><span data-stu-id="bb97e-116">**Allow anonymous participants to dial out**   This setting allows anonymous users who are already joined to the meeting to dial out to a phone number to join the audio portion of the conference.</span></span> <span data-ttu-id="bb97e-117">Esta configuración es opcional para las conferencias de acceso telefónico local.</span><span class="sxs-lookup"><span data-stu-id="bb97e-117">This setting is optional for dial-in conferencing.</span></span> <span data-ttu-id="bb97e-118">Esta opción no está seleccionada de forma predeterminada en la Directiva de conferencia global predeterminada.</span><span class="sxs-lookup"><span data-stu-id="bb97e-118">This setting is not selected by default in the default global conferencing policy.</span></span>

  - <span data-ttu-id="bb97e-119">**Permitir**   que los participantes que no están habilitados para la telefonía IP empresarial Marque esta configuración permite a los participantes de la reunión y los organizadores que no están habilitados para la telefonía IP empresarial llamar a un número de teléfono para unirse a la parte de audio de la Conferencia.</span><span class="sxs-lookup"><span data-stu-id="bb97e-119">**Allow participants not enabled for Enterprise Voice to dial out**   This setting allows meeting participants and organizers that are not enabled for Enterprise Voice to dial out to a phone number to join the audio portion of the conference.</span></span> <span data-ttu-id="bb97e-120">La llamada de acceso telefónico es autorizada en función de la Directiva de voz asignada al organizador.</span><span class="sxs-lookup"><span data-stu-id="bb97e-120">The dial-out call is authorized based on the organizer’s assigned voice policy.</span></span> <span data-ttu-id="bb97e-121">Esta opción no está seleccionada de forma predeterminada en la Directiva de conferencia global predeterminada.</span><span class="sxs-lookup"><span data-stu-id="bb97e-121">This setting is not selected by default in the default global conferencing policy.</span></span> <span data-ttu-id="bb97e-122">El valor predeterminado de configuración es deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="bb97e-122">The setting default value is disabled.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="bb97e-123">Para habilitar esta función, un organizador de la reunión que no está habilitado para Enterprise Voice debe tener asignada una directiva de voz adecuada para autorizar cualquier acceso telefónico desde una conferencia organizada por dicho usuario.</span><span class="sxs-lookup"><span data-stu-id="bb97e-123">To enable this capability, a meeting organizer that is not enabled for Enterprise Voice should have an appropriate voice policy assigned to them to authorize any dial-out from a conference organized by that user.</span></span> <span data-ttu-id="bb97e-124">Se puede asignar una directiva de voz a un usuario que no está habilitado para telefonía IP empresarial desde el shell de administración de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="bb97e-124">A voice policy can be assigned to a user that is not enabled for Enterprise Voice from the Lync Server Management Shell.</span></span> <span data-ttu-id="bb97e-125">Si el usuario no tiene una política de voz asignada explícitamente, la Directiva de voz del sitio se usará para autorizar la solicitud de aceptación de llamada.</span><span class="sxs-lookup"><span data-stu-id="bb97e-125">If the user does not have a voice policy explicitly assigned to him, the site voice policy will be used to authorize the dial-out request.</span></span> <span data-ttu-id="bb97e-126">Si no hay ninguna directiva de voz del sitio, se usará la política de voz global.&nbsp;</span><span class="sxs-lookup"><span data-stu-id="bb97e-126">If there is no site voice policy, the global voice policy will be used.&nbsp;</span></span>

    
    </div>

<span data-ttu-id="bb97e-127">En el procedimiento de esta sección se explica cómo modificar la Directiva de conferencia.</span><span class="sxs-lookup"><span data-stu-id="bb97e-127">The procedure in this section explains how to modify conferencing policy.</span></span> <span data-ttu-id="bb97e-128">Para obtener más información sobre cómo configurar todas las opciones que definen la experiencia de participante en la Directiva de conferencia predeterminada, vea [crear o modificar una colección de opciones de configuración de reuniones en Lync Server 2013](lync-server-2013-create-or-modify-a-collection-of-meeting-configuration-settings.md).</span><span class="sxs-lookup"><span data-stu-id="bb97e-128">For details about how to configure all of the settings that define the participant experience in the default conferencing policy, see [Create or modify a collection of meeting configuration settings in Lync Server 2013](lync-server-2013-create-or-modify-a-collection-of-meeting-configuration-settings.md).</span></span> <span data-ttu-id="bb97e-129">Para obtener más información sobre cómo crear una directiva de conferencia para un usuario específico o un grupo de usuarios, vea [crear o modificar una directiva de conferencia en Lync Server 2013](lync-server-2013-create-or-modify-a-conferencing-policy.md).</span><span class="sxs-lookup"><span data-stu-id="bb97e-129">For details about how to create a conferencing policy for a specific user or group of users, see [Create or modify a conferencing policy in Lync Server 2013](lync-server-2013-create-or-modify-a-conferencing-policy.md).</span></span> <span data-ttu-id="bb97e-130">Para obtener una lista de todas las configuraciones de directiva de conferencia disponibles, consulte [referencia de configuración de directiva de conferencia para Lync Server 2013](lync-server-2013-conferencing-policy-settings-reference.md).</span><span class="sxs-lookup"><span data-stu-id="bb97e-130">For a list of all available conferencing policy settings, see [Conferencing policy settings reference for Lync Server 2013](lync-server-2013-conferencing-policy-settings-reference.md).</span></span>

<div>

## <a name="to-modify-the-conferencing-policy-for-dial-in"></a><span data-ttu-id="bb97e-131">Para modificar la Directiva de conferencia para el acceso telefónico</span><span class="sxs-lookup"><span data-stu-id="bb97e-131">To modify the conferencing policy for dial-in</span></span>

1.  <span data-ttu-id="bb97e-132">Inicie sesión en el equipo como miembro del grupo RTCUniversalServerAdmins o como miembro del rol **CS-ServerAdministrator** o **CsAdministrator** .</span><span class="sxs-lookup"><span data-stu-id="bb97e-132">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **Cs-ServerAdministrator** or **CsAdministrator** role.</span></span>

2.  <span data-ttu-id="bb97e-133">Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="bb97e-133">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="bb97e-134">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="bb97e-134">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="bb97e-135">En la barra de navegación izquierda, haga clic en **Conferencia**.</span><span class="sxs-lookup"><span data-stu-id="bb97e-135">In the left navigation bar, click **Conferencing**.</span></span>

4.  <span data-ttu-id="bb97e-136">En la pestaña **Directiva de conferencia** , haga doble clic en un nombre de directiva de conferencia para abrir el cuadro de diálogo **Editar Directiva de conferencia** .</span><span class="sxs-lookup"><span data-stu-id="bb97e-136">On the **Conferencing Policy** tab, double-click a conferencing policy name to open the **Edit Conferencing Policy** dialog box.</span></span>

5.  <span data-ttu-id="bb97e-137">Compruebe que los campos de las conferencias de acceso telefónico local son adecuados para su organización y modifique la configuración si es necesario.</span><span class="sxs-lookup"><span data-stu-id="bb97e-137">Verify that the fields for dial-in conferencing are appropriate for your organization, and modify the settings if necessary.</span></span>

6.  <span data-ttu-id="bb97e-138">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="bb97e-138">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

