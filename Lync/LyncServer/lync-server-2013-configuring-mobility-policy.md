---
title: 'Lync Server 2013: Configuración de la directiva de movilidad'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring mobility policy
ms:assetid: 595536e0-9bb3-49a3-8d13-1a77351ebc62
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690018(v=OCS.15)
ms:contentKeyID: 48184204
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 39a7f0791def99e0b42a57b1f13aae88abbfafa4
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763404"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-mobility-policy-in-lync-server-2013"></a><span data-ttu-id="7772e-102">Configuración de la directiva de movilidad en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7772e-102">Configuring mobility policy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7772e-103">_**Última modificación del tema:** 2013-02-13_</span><span class="sxs-lookup"><span data-stu-id="7772e-103">_**Topic Last Modified:** 2013-02-13_</span></span>

    Some information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

<span data-ttu-id="7772e-104">Lync Server 2013 proporciona directivas de movilidad que determinan quién puede usar las características de movilidad, llamar a través del trabajo, voz sobre IP (VoIP) o vídeo, y si se necesitará WiFi para VoIP o video.</span><span class="sxs-lookup"><span data-stu-id="7772e-104">Lync Server 2013 provides mobility policies that determine who can use mobility features, Call via Work, voice over IP (VoIP) or video, and whether WiFi will be required for either VoIP or video.</span></span> <span data-ttu-id="7772e-105">La característica llamar a través del trabajo permite a un usuario móvil realizar y recibir llamadas en un teléfono móvil con un número de teléfono del trabajo en lugar del número de teléfono móvil.</span><span class="sxs-lookup"><span data-stu-id="7772e-105">The Call via Work feature enables a mobile user to make and receive calls on a mobile phone by using a work phone number instead of the mobile phone number.</span></span> <span data-ttu-id="7772e-106">Esta característica impide que la persona llamada Vea el número de teléfono móvil de la persona que llama y permite a un usuario evitar cargos por llamadas salientes.</span><span class="sxs-lookup"><span data-stu-id="7772e-106">This feature prevents the called party from seeing the caller's mobile phone number and enables a user to avoid outbound calling charges.</span></span> <span data-ttu-id="7772e-107">La configuración de VoIP y vídeo permite que los usuarios reciban y realicen llamadas y videollamadas con VoIP.</span><span class="sxs-lookup"><span data-stu-id="7772e-107">Configuring VoIP and video makes it possible for users to receive and make VoIP calls and video.</span></span> <span data-ttu-id="7772e-108">Configuración para uso de WiFi defina si el dispositivo de un usuario necesita usar una red WiFi a través de una red de datos móviles.</span><span class="sxs-lookup"><span data-stu-id="7772e-108">Settings for WiFi usage define if a user’s device will be required to use a WiFi network over a cellular data network.</span></span>

<span data-ttu-id="7772e-109">De forma predeterminada, la movilidad, la llamada a través del trabajo y las características de VoIP y vídeo están habilitadas.</span><span class="sxs-lookup"><span data-stu-id="7772e-109">By default, mobility, Call via Work, and the VoIP and video features are enabled.</span></span> <span data-ttu-id="7772e-110">La configuración para requerir WiFi para VoIp y vídeo está deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="7772e-110">The settings to require WiFi for VoIp and video are disabled.</span></span> <span data-ttu-id="7772e-111">Los administradores pueden determinar quién tiene acceso a estas características ejecutando un cmdlet.</span><span class="sxs-lookup"><span data-stu-id="7772e-111">Administrators can determine who has access to these features by running a cmdlet.</span></span> <span data-ttu-id="7772e-112">Puede desactivar las opciones globalmente, por sitio o por usuario.</span><span class="sxs-lookup"><span data-stu-id="7772e-112">You can turn options off globally, by site, or by user.</span></span>

<span data-ttu-id="7772e-113">Para poder usar las características de movilidad y llamar a través del trabajo, los usuarios deben cumplir los siguientes requisitos previos:</span><span class="sxs-lookup"><span data-stu-id="7772e-113">To be able to use mobility features and Call via Work, users must meet the following prerequisites:</span></span>

  - <span data-ttu-id="7772e-114">Los usuarios deben estar habilitados para Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7772e-114">Users must be enabled for Lync Server 2013.</span></span>

  - <span data-ttu-id="7772e-115">Los usuarios deben estar habilitados para telefonía IP empresarial.</span><span class="sxs-lookup"><span data-stu-id="7772e-115">Users must be enabled for Enterprise Voice.</span></span>

  - <span data-ttu-id="7772e-116">Los usuarios deben tener asignada una directiva de movilidad que tenga la opción **EnableMobility** establecida en true.</span><span class="sxs-lookup"><span data-stu-id="7772e-116">Users must be assigned a mobility policy that has the **EnableMobility** option set to True.</span></span>

<span data-ttu-id="7772e-117">Para que los usuarios puedan usar las llamadas a través del trabajo, deben cumplir los siguientes dos requisitos previos adicionales:</span><span class="sxs-lookup"><span data-stu-id="7772e-117">For users to be able to use Call via Work, they must meet the following two additional prerequisites:</span></span>

  - <span data-ttu-id="7772e-118">A los usuarios se les debe asignar una directiva de voz que tenga seleccionada la opción **Habilitar llamadas simultáneas a teléfonos** .</span><span class="sxs-lookup"><span data-stu-id="7772e-118">Users must be assigned a voice policy that has the **Enable simultaneous ringing of phones** option selected.</span></span>

  - <span data-ttu-id="7772e-119">Los usuarios deben tener asignada una directiva de movilidad que tenga la opción **EnableOutsideVoice** establecida en true.</span><span class="sxs-lookup"><span data-stu-id="7772e-119">Users must be assigned a mobility policy that has the **EnableOutsideVoice** option set to True.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="7772e-120">Los usuarios que no tienen habilitada la telefonía IP empresarial pueden usar sus dispositivos móviles para hacer llamadas de voz sobre IP (VoIP) de Lync a Lync o pueden unirse a conferencias con el vínculo haga clic para unirse en sus dispositivos móviles, si asigna a esos usuarios las opciones adecuadas para la Directiva de voz.</span><span class="sxs-lookup"><span data-stu-id="7772e-120">Users who are not enabled for Enterprise Voice can use their mobile devices to make Lync to Lync Voice over IP (VoIP) calls, or can join conferences by using the Click to Join link on their mobile devices, if you assign those users the appropriate options for voice policy.</span></span> <span data-ttu-id="7772e-121">Para obtener más información, vea <A href="lync-server-2013-defining-your-mobility-requirements.md">definir los requisitos de movilidad para Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="7772e-121">For details, see <A href="lync-server-2013-defining-your-mobility-requirements.md">Defining your mobility requirements for Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="7772e-122">Para obtener más información sobre cómo habilitar usuarios para Lync Server 2013, vea [deshabilitar o volver a habilitar la cuenta de usuario para Lync server 2013](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md).</span><span class="sxs-lookup"><span data-stu-id="7772e-122">For details about enabling users for Lync Server 2013, see [Disable or re-enable user account for Lync Server 2013](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md).</span></span> <span data-ttu-id="7772e-123">Para obtener más información sobre cómo habilitar usuarios para telefonía IP empresarial, consulte [Habilitar usuarios para telefonía IP empresarial en Lync Server 2013](lync-server-2013-enable-users-for-enterprise-voice.md).</span><span class="sxs-lookup"><span data-stu-id="7772e-123">For details about enabling users for Enterprise Voice, see [Enable users for Enterprise Voice in Lync Server 2013](lync-server-2013-enable-users-for-enterprise-voice.md).</span></span> <span data-ttu-id="7772e-124">Para obtener más información sobre cómo configurar las opciones de directiva de voz, consulte [modificar una directiva de voz y configurar los registros de uso de RTC en Lync Server 2013](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md).</span><span class="sxs-lookup"><span data-stu-id="7772e-124">For details about setting voice policy options, see [Modify a voice policy and configure PSTN usage records in Lync Server 2013](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md).</span></span>

<div>

## <a name="to-modify-global-mobility-policy"></a><span data-ttu-id="7772e-125">Para modificar la Directiva de movilidad global</span><span class="sxs-lookup"><span data-stu-id="7772e-125">To modify global mobility policy</span></span>

1.  <span data-ttu-id="7772e-126">Inicie sesión en cualquier equipo donde esté instalado shell de administración de Lync Server y Ocscore como miembro del rol CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="7772e-126">Log on to any computer where Lync Server Management Shell and Ocscore are installed as a member of the CsAdministrator role.</span></span>

2.  <span data-ttu-id="7772e-127">Inicie el shell de administración de Lync Server: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **Shell de administración de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="7772e-127">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="7772e-128">Desactiva el acceso a la movilidad y llama a través del trabajo de forma global.</span><span class="sxs-lookup"><span data-stu-id="7772e-128">Turn off access to mobility and Call via Work globally.</span></span> <span data-ttu-id="7772e-129">En la línea de comandos, escriba:</span><span class="sxs-lookup"><span data-stu-id="7772e-129">At the command line, type:</span></span>
    
        Set-CsMobilityPolicy -EnableMobility $False -EnableOutsideVoice $False
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="7772e-130">Puede desactivar la llamada por trabajo sin desactivar el acceso a la movilidad.</span><span class="sxs-lookup"><span data-stu-id="7772e-130">You can turn off Call via Work without turning off access to mobility.</span></span> <span data-ttu-id="7772e-131">Sin embargo, no puede desactivar la movilidad sin desactivar también la llamada a través del trabajo.</span><span class="sxs-lookup"><span data-stu-id="7772e-131">However, you cannot turn off mobility without also turning off Call via Work.</span></span>

    
    </div>

</div>

<div>

## <a name="to-modify-mobility-policy-by-site"></a><span data-ttu-id="7772e-132">Para modificar la Directiva de movilidad por sitio</span><span class="sxs-lookup"><span data-stu-id="7772e-132">To modify mobility policy by site</span></span>

1.  <span data-ttu-id="7772e-133">Inicie sesión en cualquier equipo donde esté instalado shell de administración de Lync Server y Ocscore como miembro del rol CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="7772e-133">Log on to any computer where Lync Server Management Shell and Ocscore are installed as a member of the CsAdministrator role.</span></span>

2.  <span data-ttu-id="7772e-134">Inicie el shell de administración de Lync Server: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **Shell de administración de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="7772e-134">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="7772e-135">Cree una directiva de nivel de sitio, desactive VoIP y vídeo, y habilite la opción requerir WiFi para audio IP y para video IP por sitio.</span><span class="sxs-lookup"><span data-stu-id="7772e-135">Create a site-level policy, and turn off VoIP and video, and enable Require WiFi for IP Audio and for IP Video by site.</span></span> <span data-ttu-id="7772e-136">En la línea de comandos, escriba:</span><span class="sxs-lookup"><span data-stu-id="7772e-136">At the command line, type:</span></span>
    
        New-CsMobilityPolicy -Identity site:<site identifier> -EnableIPAudioVideo $False -RequireWiFiForIPAudio $True -RequireWiFiForIPVideo $True

</div>

<div>

## <a name="to-modify-mobility-policy-by-user"></a><span data-ttu-id="7772e-137">Para modificar la Directiva de movilidad por usuario</span><span class="sxs-lookup"><span data-stu-id="7772e-137">To modify mobility policy by user</span></span>

1.  <span data-ttu-id="7772e-138">Inicie sesión en cualquier equipo donde esté instalado shell de administración de Lync Server y Ocscore como miembro del rol CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="7772e-138">Log on to any computer where Lync Server Management Shell and Ocscore are installed as a member of the CsAdministrator role.</span></span>

2.  <span data-ttu-id="7772e-139">Inicie el shell de administración de Lync Server: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **Shell de administración de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="7772e-139">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="7772e-140">Crear directivas de movilidad de nivel de usuario y desactivar la movilidad y la llamada a través del trabajo por usuario.</span><span class="sxs-lookup"><span data-stu-id="7772e-140">Create user level mobility policies and turn off mobility and Call via Work by user.</span></span> <span data-ttu-id="7772e-141">En la línea de comandos, escriba:</span><span class="sxs-lookup"><span data-stu-id="7772e-141">At the command line, type:</span></span>
    
        New-CsMobilityPolicy -Identity <policy name> -EnableMobility $False -EnableOutsideVoice $False
        Grant-CsMobilityPolicy -Identity <user identifier> -PolicyName <policy name>
    
    <span data-ttu-id="7772e-142">Puede desactivar la llamada por trabajo sin desactivar el acceso a la movilidad.</span><span class="sxs-lookup"><span data-stu-id="7772e-142">You can turn off Call via Work without turning off access to mobility.</span></span> <span data-ttu-id="7772e-143">Sin embargo, no puede desactivar la movilidad sin desactivar también la llamada a través del trabajo.</span><span class="sxs-lookup"><span data-stu-id="7772e-143">However, you cannot turn off mobility without also turning off Call via Work.</span></span>
    
    <span data-ttu-id="7772e-144">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="7772e-144">For example:</span></span>
    
        New-CsMobilityPolicy "tag:disableOutsideVoice" -EnableOutsideVoice $False
        Grant-CsMobilityPolicy -Identity -MobileUser1@contoso.com -PolicyName Tag:disableOutsideVoice

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="7772e-145">Vea también</span><span class="sxs-lookup"><span data-stu-id="7772e-145">See Also</span></span>


[<span data-ttu-id="7772e-146">Deshabilitar o volver a habilitar la cuenta de usuario para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7772e-146">Disable or re-enable user account for Lync Server 2013</span></span>](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md)  
[<span data-ttu-id="7772e-147">Habilitar usuarios para telefonía IP empresarial en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7772e-147">Enable users for Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-enable-users-for-enterprise-voice.md)  
[<span data-ttu-id="7772e-148">Modificar una directiva de voz y configurar los registros de uso de RTC en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7772e-148">Modify a voice policy and configure PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md)  


[<span data-ttu-id="7772e-149">Definir los requisitos de movilidad para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7772e-149">Defining your mobility requirements for Lync Server 2013</span></span>](lync-server-2013-defining-your-mobility-requirements.md)  


[<span data-ttu-id="7772e-150">New-CsMobilityPolicy</span><span class="sxs-lookup"><span data-stu-id="7772e-150">New-CsMobilityPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsMobilityPolicy)  
[<span data-ttu-id="7772e-151">Set-CsMobilityPolicy</span><span class="sxs-lookup"><span data-stu-id="7772e-151">Set-CsMobilityPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsMobilityPolicy)  
[<span data-ttu-id="7772e-152">Get-CsMobilityPolicy</span><span class="sxs-lookup"><span data-stu-id="7772e-152">Get-CsMobilityPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsMobilityPolicy)  
[<span data-ttu-id="7772e-153">Grant-CsMobilityPolicy</span><span class="sxs-lookup"><span data-stu-id="7772e-153">Grant-CsMobilityPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Grant-CsMobilityPolicy)  
[<span data-ttu-id="7772e-154">Remove-CsMobilityPolicy</span><span class="sxs-lookup"><span data-stu-id="7772e-154">Remove-CsMobilityPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsMobilityPolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

