---
title: 'Lync Server 2013: ver información de configuración de Lync Phone Edition'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: View Lync Phone Edition configuration settings information
ms:assetid: 15f94478-651f-4063-9918-6a059f98df16
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687976(v=OCS.15)
ms:contentKeyID: 49733564
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 213b9775b22818c34eb8f7896ea02a4872182a42
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34850107"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-lync-phone-edition-configuration-settings-information-in-lync-server-2013"></a><span data-ttu-id="bb1c1-102">Ver la información de configuración de Lync Phone Edition en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bb1c1-102">View Lync Phone Edition configuration settings information in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bb1c1-103">_**Última modificación del tema:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="bb1c1-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="bb1c1-104">Puede ver la información de configuración de los dispositivos que ejecutan Lync Phone Edition.</span><span class="sxs-lookup"><span data-stu-id="bb1c1-104">You can view configuration information about devices running Lync Phone Edition.</span></span> <span data-ttu-id="bb1c1-105">La información está organizada en colecciones.</span><span class="sxs-lookup"><span data-stu-id="bb1c1-105">The information is organized into collections.</span></span> <span data-ttu-id="bb1c1-106">Al instalar Lync Server, obtiene una colección de opciones de configuración de Lync Phone Edition que se aplican a todos los dispositivos que ejecutan Lync Phone Edition en su implementación.</span><span class="sxs-lookup"><span data-stu-id="bb1c1-106">When you install Lync Server, you get a collection of Lync Phone Edition settings that apply to all the devices running Lync Phone Edition in your deployment.</span></span> <span data-ttu-id="bb1c1-107">También puede crear nuevas colecciones de configuración para un sitio específico.</span><span class="sxs-lookup"><span data-stu-id="bb1c1-107">You can also create new collections of settings for a specific site.</span></span> <span data-ttu-id="bb1c1-108">La configuración del sitio tiene prioridad sobre la configuración global.</span><span class="sxs-lookup"><span data-stu-id="bb1c1-108">Site settings take precedence over global settings.</span></span> <span data-ttu-id="bb1c1-109">Cada conjunto de opciones de configuración consiste en un nombre, el ámbito (global o sitio), la configuración de seguridad SIP, el nivel de registro, el nivel de calidad de servicio (QoS), la configuración de bloqueo de teléfono y los detalles de bloqueo de teléfono, es decir, la longitud mínima del desbloqueo de identificación personal número (PIN) y tiempo antes de que el teléfono se bloquee por sí mismo.</span><span class="sxs-lookup"><span data-stu-id="bb1c1-109">Each collection of settings consists of a name, the scope (global or site), SIP security setting, logging level, voice quality of service (QoS) level, phone-lock setting, and phone-lock details, that is, the minimum length of the unlock personal identification number (PIN) and time before the phone locks itself.</span></span>

<div>

## <a name="to-view-configuration-information-about-devices-running-lync-phone-edition"></a><span data-ttu-id="bb1c1-110">Para ver la información de configuración de los dispositivos que ejecutan Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="bb1c1-110">To view configuration information about devices running Lync Phone Edition</span></span>

1.  <span data-ttu-id="bb1c1-111">Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="bb1c1-111">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="bb1c1-112">Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="bb1c1-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="bb1c1-113">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="bb1c1-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="bb1c1-114">En la barra de navegación izquierda, haga clic en **clientes**y, a continuación, haga clic en el botón de navegación **configuración de dispositivo** .</span><span class="sxs-lookup"><span data-stu-id="bb1c1-114">In the left navigation bar, click **Clients**, and then click the **Device Configuration** navigation button.</span></span>

4.  <span data-ttu-id="bb1c1-115">En la página **configuración de dispositivo** , haga clic en la colección de configuraciones de la que desea ver la información.</span><span class="sxs-lookup"><span data-stu-id="bb1c1-115">On the **Device Configuration** page, click the collection of settings you want to view information about.</span></span> <span data-ttu-id="bb1c1-116">El nombre, el ámbito, la configuración de seguridad SIP, el nivel de calidad de voz y la configuración de bloqueo de teléfono se muestran en la Página principal.</span><span class="sxs-lookup"><span data-stu-id="bb1c1-116">The name, scope, SIP security setting, voice quality level, and phone lock setting are listed on the main page.</span></span> <span data-ttu-id="bb1c1-117">Para ver los detalles del nivel de registro y el bloqueo de teléfono, haga clic en el menú **Editar** y, a continuación, en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="bb1c1-117">To view the logging level and phone lock details, click the **Edit** menu, and then click **Show details**.</span></span>

</div>

<div>

## <a name="viewing-lync-phone-edition-configuration-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="bb1c1-118">Ver la información de configuración de Lync Phone Edition mediante cmdlets de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="bb1c1-118">Viewing Lync Phone Edition Configuration Information by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="bb1c1-119">Puede ver las opciones de configuración de Lync Phone Edition con el shell de administración de Lync Server y el cmdlet **Get-CsUCPhoneConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="bb1c1-119">You can view Lync Phone Edition configuration settings by using Lync Server Management Shell and the **Get-CsUCPhoneConfiguration** cmdlet.</span></span> <span data-ttu-id="bb1c1-120">Puede ejecutar este cmdlet desde el shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="bb1c1-120">You can run this cmdlet can from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="bb1c1-121">Para obtener más información sobre cómo usar Windows PowerShell remoto para conectarse a Lync Server, consulte el artículo del blog de Lync Server de Windows PowerShell "Inicio rápido: administrar Microsoft Lync Server [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)2010 mediante PowerShell remoto" en.</span><span class="sxs-lookup"><span data-stu-id="bb1c1-121">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-lync-phone-edition-configuration-information"></a><span data-ttu-id="bb1c1-122">Para ver la información de configuración de Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="bb1c1-122">To view Lync Phone Edition configuration information</span></span>

  - <span data-ttu-id="bb1c1-123">Para ver información sobre todas las opciones de configuración de Lync Phone Edition, escriba el siguiente comando en el shell de administración de Lync Server y, a continuación, presione ENTRAR:</span><span class="sxs-lookup"><span data-stu-id="bb1c1-123">To view information about all your Lync Phone Edition configuration settings, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsUCPhoneConfiguration
    
    <span data-ttu-id="bb1c1-124">El comando devuelve información similar a la siguiente:</span><span class="sxs-lookup"><span data-stu-id="bb1c1-124">The command returns information similar to the following:</span></span>
    
        Identity             : Global
        CalendarPollInterval : 00:03:00
        EnforcePhoneLock     : True
        PhoneLockTimeout     : 00:10:00
        MinPhonePinLength    : 6
        SIPSecurityMode      : High
        VoiceDiffServTag     : 40
        Voice8021p           : 0
        LoggingLevel         : Off

</div>

<span data-ttu-id="bb1c1-125">Para obtener más información, vea [Get-CsUCPhoneConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsUCPhoneConfiguration).</span><span class="sxs-lookup"><span data-stu-id="bb1c1-125">For details, see [Get-CsUCPhoneConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsUCPhoneConfiguration).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="bb1c1-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="bb1c1-126">See Also</span></span>


[<span data-ttu-id="bb1c1-127">Crear o modificar una colección de opciones de configuración de Lync Phone Edition en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bb1c1-127">Create or modify a collection of Lync Phone Edition configuration settings in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-collection-of-lync-phone-edition-configuration-settings.md)  
[<span data-ttu-id="bb1c1-128">Eliminar una colección existente de opciones de configuración de Lync Phone Edition en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bb1c1-128">Delete an existing collection of Lync Phone Edition configuration settings in Lync Server 2013</span></span>](lync-server-2013-delete-an-existing-collection-of-lync-phone-edition-configuration-settings.md)  
[<span data-ttu-id="bb1c1-129">Establecer la configuración de seguridad de Lync Phone Edition en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bb1c1-129">Configure security settings for Lync Phone Edition in Lync Server 2013</span></span>](lync-server-2013-configure-security-settings-for-lync-phone-edition.md)  
[<span data-ttu-id="bb1c1-130">Exigir el bloqueo de teléfono en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bb1c1-130">Enforce phone locking in Lync Server 2013</span></span>](lync-server-2013-enforce-phone-locking.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

