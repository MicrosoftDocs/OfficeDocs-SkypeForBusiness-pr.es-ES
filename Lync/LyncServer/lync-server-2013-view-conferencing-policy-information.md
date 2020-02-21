---
title: 'Lync Server 2013: ver información de directiva de conferencia'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View conferencing policy information
ms:assetid: e99fdc4d-926a-4e36-ac99-ab5035568847
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721918(v=OCS.15)
ms:contentKeyID: 49733852
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 664078db23ecba5d26852c2e1348935a3e4c60b0
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42211516"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="view-conferencing-policy-information-in-lync-server-2013"></a><span data-ttu-id="e2bf1-102">Ver información de directiva de conferencia en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e2bf1-102">View conferencing policy information in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e2bf1-103">_**Última modificación del tema:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="e2bf1-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="e2bf1-104">En el panel de control de Lync Server 2013, puede usar directivas de conferencia para controlar cómo se implementan las conferencias en su implementación.</span><span class="sxs-lookup"><span data-stu-id="e2bf1-104">In Lync Server 2013 Control Panel, you use conferencing policies to control how conferencing is implemented in your deployment.</span></span> <span data-ttu-id="e2bf1-105">Esto incluye las directivas de conferencia siguientes:</span><span class="sxs-lookup"><span data-stu-id="e2bf1-105">This includes the following conferencing policies:</span></span>

  - <span data-ttu-id="e2bf1-106">Una directiva global que se crea de forma predeterminada al implementar Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e2bf1-106">A global policy that is created by default when you deploy Lync Server 2013.</span></span>

  - <span data-ttu-id="e2bf1-107">Una directiva de nivel de sitio y de nivel de usuario que se crea y usa para especificar cómo se implementan las reuniones en sitios o usuarios específicos.</span><span class="sxs-lookup"><span data-stu-id="e2bf1-107">Optional site-level and user-level policy that you can create and use to specify how conferencing is implemented for specific sites or users.</span></span>

<div>

## <a name="to-view-conferencing-policy-settings"></a><span data-ttu-id="e2bf1-108">Para ver la configuración de la directiva de conferencia</span><span class="sxs-lookup"><span data-stu-id="e2bf1-108">To view conferencing policy settings</span></span>

1.  <span data-ttu-id="e2bf1-109">Desde una cuenta de usuario asignada al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.</span><span class="sxs-lookup"><span data-stu-id="e2bf1-109">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="e2bf1-110">Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e2bf1-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="e2bf1-111">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="e2bf1-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="e2bf1-112">En la barra de navegación izquierda, haga clic en **Conferencia** y después en **Directiva de Conferencia**.</span><span class="sxs-lookup"><span data-stu-id="e2bf1-112">In the left navigation bar, click **Conferencing** and then click **Conferencing Policy**.</span></span>

4.  <span data-ttu-id="e2bf1-113">En la página **Directiva de conferencia**, haga doble clic en la directiva de conferencia que desee ver.</span><span class="sxs-lookup"><span data-stu-id="e2bf1-113">On the **Conferencing Policy** page, double-click the conferencing policy that you would like to view.</span></span>

5.  <span data-ttu-id="e2bf1-p103">En **Editar filtro de archivo**, active la casilla **Mostrar detalles…**.</span><span class="sxs-lookup"><span data-stu-id="e2bf1-p103">In **Edit File Filter**, select the **Show Details…** check box.</span></span>
    
    <span data-ttu-id="e2bf1-116">\*\*Editar Directiva de conferencia \<:\> \*\* se abre la Directiva y se muestra la configuración de la Directiva seleccionada.</span><span class="sxs-lookup"><span data-stu-id="e2bf1-116">**Edit Conferencing Policy - \<policy\>** opens displaying the settings for the selected policy.</span></span> <span data-ttu-id="e2bf1-117">Para obtener más información sobre cómo configurar las opciones, consulte [crear o modificar una directiva de conferencia en Lync Server 2013](lync-server-2013-create-or-modify-a-conferencing-policy.md).</span><span class="sxs-lookup"><span data-stu-id="e2bf1-117">For details about configuring the settings, see [Create or modify a conferencing policy in Lync Server 2013](lync-server-2013-create-or-modify-a-conferencing-policy.md).</span></span>

</div>

<div>

## <a name="viewing-conferencing-policies-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="e2bf1-118">Ver directivas de conferencia con los cmdlets de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="e2bf1-118">Viewing Conferencing Policies by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="e2bf1-119">Las directivas de conferencia se pueden ver con Windows PowerShell y el cmdlet Get-CsConferencingPolicy.</span><span class="sxs-lookup"><span data-stu-id="e2bf1-119">Conferencing policies can be viewed by using Windows PowerShell and the Get-CsConferencingPolicy cmdlet.</span></span> <span data-ttu-id="e2bf1-120">Este cmdlet se puede ejecutar desde el shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e2bf1-120">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="e2bf1-121">Para obtener información detallada sobre cómo usar Windows PowerShell remoto para conectarse a Lync Server, consulte el artículo del blog de Lync Server Windows PowerShell "Inicio rápido: administración de Microsoft Lync Server [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)2010 mediante PowerShell remoto" en.</span><span class="sxs-lookup"><span data-stu-id="e2bf1-121">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-conferencing-policies"></a><span data-ttu-id="e2bf1-122">Para ver las directivas de conferencia</span><span class="sxs-lookup"><span data-stu-id="e2bf1-122">To view conferencing policies</span></span>

  - <span data-ttu-id="e2bf1-123">Para ver información sobre todas las directivas de conferencia, escriba el siguiente comando en el shell de administración de Lync Server y, a continuación, presione ENTRAR:</span><span class="sxs-lookup"><span data-stu-id="e2bf1-123">To view information about all your conferencing policies, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsConferencingPolicy
    
    <span data-ttu-id="e2bf1-124">Devolverá información similar a la siguiente:</span><span class="sxs-lookup"><span data-stu-id="e2bf1-124">That will return information similar to this:</span></span>
    
        Identity                                  : Global
        AllowIPAudio                              : True
        AllowIPVideo                              : True
        AllowMultiView                            : True
        Description                               :
        AllowParticipantControl                   : True
        AllowAnnotations                          : True
        DisablePowerPointAnnotations              : False
        AllowUserToScheduleMeetingsWithAppSharing : True
        AllowNonEnterpriseVoiceUsersToDialOut     : False
        AllowAnonymousUsersToDialOut              : False
        AllowAnonymousParticipantsInMeetings      : True
        AllowExternalUsersToSaveContent           : True
        AllowExternalUserControl                  : False
        AllowExternalUsersToRecordMeeting         : False
        AllowPolls                                : True
        AllowSharedNotes                          : True
        EnableDialInConferencing                  : True
        EnableAppDesktopSharing                   : Desktop
        AllowConferenceRecording                  : False
        EnableP2PRecording                        : False
        EnableFileTransfer                        : True
        EnableP2PFileTransfer                     : True
        EnableP2PVideo                            : True
        AllowLargeMeetings                        : False
        EnableDataCollaboration                   : True
        MaxVideoConferenceResolution              : VGA
        MaxMeetingSize                            : 250
        AudioBitRateKb                            : 200
        VideoBitRateKb                            : 50000
        AppSharingBitRateKb                       : 50000
        FileTransferBitRateKb                     : 50000
        TotalReceiveVideoBitRateKb                : 6000
        EnableMultiViewJoin                       : True

</div>

<span data-ttu-id="e2bf1-125">Para obtener más información, consulte el tema de ayuda para el cmdlet [Get-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsConferencingPolicy) .</span><span class="sxs-lookup"><span data-stu-id="e2bf1-125">For more information, see the help topic for the [Get-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsConferencingPolicy) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

