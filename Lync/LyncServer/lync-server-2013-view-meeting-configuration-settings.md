---
title: 'Lync Server 2013: ver la configuración de la reunión'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View meeting configuration settings
ms:assetid: d03a4684-9d8b-4728-917d-5b5c91511e2c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721894(v=OCS.15)
ms:contentKeyID: 49733828
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5737fbba63915501bea80105ef3509511d8cb436
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765631"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-meeting-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="64244-102">Ver la configuración de la configuración de la reunión en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="64244-102">View meeting configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="64244-103">_**Última modificación del tema:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="64244-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="64244-104">En el panel de control de Lync Server 2013, use la opción Configuración de la reunión para controlar cómo se implementan las reuniones en la implementación.</span><span class="sxs-lookup"><span data-stu-id="64244-104">In Lync Server 2013 Control Panel, you use meeting configuration setting to control how meetings are implemented in your deployment.</span></span> <span data-ttu-id="64244-105">Esto incluye las siguientes configuraciones de reunión:</span><span class="sxs-lookup"><span data-stu-id="64244-105">This includes the following meeting configurations:</span></span>

  - <span data-ttu-id="64244-106">Una configuración global que se crea de forma predeterminada al implementar Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="64244-106">A global configuration that is created by default when you deploy Lync Server 2013.</span></span>

  - <span data-ttu-id="64244-107">Configuraciones opcionales de nivel de sitio y de usuario que puede crear y usar para especificar cómo se implementan las reuniones para usuarios o sitios específicos.</span><span class="sxs-lookup"><span data-stu-id="64244-107">Optional site-level and user-level configurations that you can create and use to specify how meetings are implemented for specific sites or users.</span></span>

<div>

## <a name="to-view-meeting-configuration-settings"></a><span data-ttu-id="64244-108">Para ver la configuración de la reunión</span><span class="sxs-lookup"><span data-stu-id="64244-108">To view meeting configuration settings</span></span>

1.  <span data-ttu-id="64244-109">Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="64244-109">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="64244-110">Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="64244-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="64244-111">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="64244-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="64244-112">En la barra de navegación izquierda, haga clic en **Conferencia** y, a continuación, en **configuración de reunión**.</span><span class="sxs-lookup"><span data-stu-id="64244-112">In the left navigation bar, click **Conferencing** and then click **Meeting Configuration**.</span></span>

4.  <span data-ttu-id="64244-113">En la página **Configuración de reunión**, haga clic en la configuración de reunión que desee ver.</span><span class="sxs-lookup"><span data-stu-id="64244-113">On the **Meeting Configuration** page, click the meeting configuration that you would like to view.</span></span>

5.  <span data-ttu-id="64244-114">En **Editar filtro de archivo**, seleccione **Mostrar detalles...**</span><span class="sxs-lookup"><span data-stu-id="64244-114">In **Edit File Filter**, select the **Show Details…**</span></span> <span data-ttu-id="64244-115">casilla de verificación.</span><span class="sxs-lookup"><span data-stu-id="64244-115">check box.</span></span>
    
    <span data-ttu-id="64244-116">**Editar la configuración de \<la\> reunión:** se abre la Directiva que muestra la configuración de la Directiva seleccionada.</span><span class="sxs-lookup"><span data-stu-id="64244-116">**Edit Meeting Configuration - \<policy\>** opens displaying the settings for the selected policy.</span></span> <span data-ttu-id="64244-117">Para obtener más información sobre cómo configurar las opciones, vea [crear o modificar una colección de opciones de configuración de reuniones en Lync Server 2013](lync-server-2013-create-or-modify-a-collection-of-meeting-configuration-settings.md).</span><span class="sxs-lookup"><span data-stu-id="64244-117">For details about configuring the settings, see [Create or modify a collection of meeting configuration settings in Lync Server 2013](lync-server-2013-create-or-modify-a-collection-of-meeting-configuration-settings.md).</span></span>

</div>

<div>

## <a name="viewing-meeting-configuration-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="64244-118">Visualización de la información de configuración de reuniones con cmdlets de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="64244-118">Viewing Meeting Configuration Information by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="64244-119">La configuración de la reunión se puede ver con Windows PowerShell y el cmdlet Get-CsMeetingConfiguration.</span><span class="sxs-lookup"><span data-stu-id="64244-119">Meeting configuration settings can be viewed by using Windows PowerShell and the Get-CsMeetingConfiguration cmdlet.</span></span> <span data-ttu-id="64244-120">Este cmdlet se puede ejecutar desde el shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="64244-120">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="64244-121">Para obtener más información sobre cómo usar Windows PowerShell remoto para conectarse a Lync Server, consulte el artículo del blog de Lync Server de Windows PowerShell "Inicio rápido: administrar Microsoft Lync Server [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)2010 mediante PowerShell remoto" en.</span><span class="sxs-lookup"><span data-stu-id="64244-121">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-meeting-configuration-information"></a><span data-ttu-id="64244-122">Para ver la información de configuración de reunión</span><span class="sxs-lookup"><span data-stu-id="64244-122">To view meeting configuration information</span></span>

  - <span data-ttu-id="64244-123">Para ver información sobre todas las opciones de configuración de la reunión, escriba el siguiente comando en el shell de administración de Lync Server y, a continuación, presione ENTRAR:</span><span class="sxs-lookup"><span data-stu-id="64244-123">To view information about all your meeting configuration settings, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsMeetingConfiguration
    
    <span data-ttu-id="64244-124">Devolverá información similar a la siguiente:</span><span class="sxs-lookup"><span data-stu-id="64244-124">That will return information similar to this:</span></span>
    
        Identity                        : Global
        PstnCallersBypassLobby          : True
        EnableAssignedConferenceType    : True
        DesignateAsPresenter            : Company
        AssignedConferenceTypeByDefault : True
        AdmitAnonymousUsersByDefault    : True
        RequireRoomSystemsAuthorization : False
        LogoURL                         :
        LegalURL                        :
        HelpURL                         :
        CustomFooterText                :
        AllowConferenceRecording        : True

</div>

<span data-ttu-id="64244-125">Para obtener más información, consulte el tema de ayuda para el cmdlet [Get-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsMeetingConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="64244-125">For more information, see the help topic for the [Get-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsMeetingConfiguration) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

