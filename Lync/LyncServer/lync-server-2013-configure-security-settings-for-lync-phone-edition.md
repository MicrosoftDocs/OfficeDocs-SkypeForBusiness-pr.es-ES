---
title: 'Lync Server 2013: configuración de seguridad para Lync Phone Edition'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure security settings for Lync Phone Edition
ms:assetid: 6e7cec17-8a79-4428-9300-8821256c46cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521014(v=OCS.15)
ms:contentKeyID: 48184464
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b7bd44b5d3f466728ac1dbe928c08b1f4786f8fe
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842332"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-security-settings-for-lync-phone-edition-in-lync-server-2013"></a><span data-ttu-id="7cbbd-102">Establecer la configuración de seguridad de Lync Phone Edition en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7cbbd-102">Configure security settings for Lync Phone Edition in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7cbbd-103">_**Última modificación del tema:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="7cbbd-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="7cbbd-104">Ayude a mejorar la seguridad de los dispositivos que ejecutan Lync Phone Edition a través de la configuración de seguridad SIP y el bloqueo de teléfono.</span><span class="sxs-lookup"><span data-stu-id="7cbbd-104">Help improve the security of devices running Lync Phone Edition via your SIP security setting and phone lock settings.</span></span>

<div>

## <a name="to-configure-security-settings-for-lync-phone-edition"></a><span data-ttu-id="7cbbd-105">Para establecer la configuración de seguridad de Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="7cbbd-105">To configure security settings for Lync Phone Edition</span></span>

1.  <span data-ttu-id="7cbbd-106">Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="7cbbd-106">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="7cbbd-107">Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="7cbbd-107">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="7cbbd-108">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="7cbbd-108">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="7cbbd-109">En la barra de navegación izquierda, haga clic en **clientes**y, después, en **configuración de dispositivo**.</span><span class="sxs-lookup"><span data-stu-id="7cbbd-109">In the left navigation bar, click **Clients**, and then click **Device Configuration**.</span></span>

4.  <span data-ttu-id="7cbbd-110">En la página **configuración de dispositivo** , en la lista de configuraciones de dispositivos, haga doble clic en la configuración para la que desea cambiar la configuración de seguridad.</span><span class="sxs-lookup"><span data-stu-id="7cbbd-110">On the **Device Configuration** page, in the list of device configurations, double-click the configuration for which you want to change security settings.</span></span>

5.  <span data-ttu-id="7cbbd-111">En **Editar configuración del dispositivo**, en **seguridad SIP**, especifique el nivel de seguridad SIP.</span><span class="sxs-lookup"><span data-stu-id="7cbbd-111">In **Edit Device Configuration**, in **SIP security**, specify the SIP security level.</span></span> <span data-ttu-id="7cbbd-112">El nivel predeterminado es **alto**, que se recomienda usar.</span><span class="sxs-lookup"><span data-stu-id="7cbbd-112">The default level is **High**, which we recommend using.</span></span>

6.  <span data-ttu-id="7cbbd-113">En **Editar configuración del dispositivo**, en **bloqueo de teléfono**, Active o desactive la casilla exigir bloqueo del **dispositivo** (activada de forma predeterminada) y especifique la longitud mínima del PIN (6 caracteres de forma predeterminada) y el período de tiempo de espera (10 minutos de forma predeterminada).</span><span class="sxs-lookup"><span data-stu-id="7cbbd-113">In **Edit Device Configuration**, under **Phone Lock**, select or clear the **Enforce device locking** check box (selected by default) and specify the minimum PIN length (6 characters by default) and timeout period (10 minutes by default).</span></span> <span data-ttu-id="7cbbd-114">Le recomendamos que use estos valores predeterminados o que aumente la longitud del PIN o reduzca el período de tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="7cbbd-114">We recommend using these defaults or increasing the PIN length and/or decreasing the timeout period.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="7cbbd-115">Para obtener más información, consulte exigir el <A href="lync-server-2013-enforce-phone-locking.md">bloqueo de teléfono en Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="7cbbd-115">For details, see <A href="lync-server-2013-enforce-phone-locking.md">Enforce phone locking in Lync Server 2013</A>.</span></span>

    
    </div>

</div>

<div>

## <a name="configuring-security-settings-for-lync-phone-edition-phones-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="7cbbd-116">Configuración de la seguridad de los teléfonos de Lync Phone Edition mediante cmdlets de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="7cbbd-116">Configuring Security Settings for Lync Phone Edition Phones by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="7cbbd-117">La configuración de seguridad se puede administrar mediante el shell de administración de Lync Server y el cmdlet **Get-CsUCPhoneConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="7cbbd-117">Security settings can be managed by using Lync Server Management Shell and the **Get-CsUCPhoneConfiguration** cmdlet.</span></span> <span data-ttu-id="7cbbd-118">Este cmdlet se puede ejecutar desde el shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7cbbd-118">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="7cbbd-119">Para obtener más información sobre cómo usar Windows PowerShell remoto para conectarse a Lync Server, consulte el artículo del blog de Lync Server de Windows PowerShell "Inicio rápido: administrar Microsoft Lync Server [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)2010 mediante PowerShell remoto" en.</span><span class="sxs-lookup"><span data-stu-id="7cbbd-119">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-modify-the-sip-security-mode"></a><span data-ttu-id="7cbbd-120">Para modificar el modo de seguridad SIP</span><span class="sxs-lookup"><span data-stu-id="7cbbd-120">To modify the SIP security mode</span></span>

  - <span data-ttu-id="7cbbd-121">Este comando establece la SIPSecurityMode para la colección global de configuración de teléfono UC en media.</span><span class="sxs-lookup"><span data-stu-id="7cbbd-121">This command sets the SIPSecurityMode for the global collection of UC phone settings to Medium.</span></span> <span data-ttu-id="7cbbd-122">La seguridad del SIP también se podría establecer en baja o alta (el valor predeterminado).</span><span class="sxs-lookup"><span data-stu-id="7cbbd-122">SIP security could also be set to Low or High (the default value).</span></span>
    
        Set-CsUCPhoneConfiguration -Identity global -SIPSecurityMode "Medium"

</div>

<div>

## <a name="to-modify-the-minimum-pin-length"></a><span data-ttu-id="7cbbd-123">Para modificar la longitud mínima del PIN</span><span class="sxs-lookup"><span data-stu-id="7cbbd-123">To modify the minimum PIN length</span></span>

  - <span data-ttu-id="7cbbd-124">En este ejemplo, todas las opciones de configuración del teléfono UC se modifican para que requieran una longitud mínima de PIN de 7 dígitos.</span><span class="sxs-lookup"><span data-stu-id="7cbbd-124">In this example, all the UC phone settings are modified to require a minimum PIN length of 7 digits.</span></span>
    
        Get-CsUCPhoneConfiguration | Set-CsUCPhoneConfiguration -MinPhonePinLength 7

</div>

<span data-ttu-id="7cbbd-125">Para obtener más información, vea [Get-CsUCPhoneConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsUCPhoneConfiguration).</span><span class="sxs-lookup"><span data-stu-id="7cbbd-125">For details, see [Get-CsUCPhoneConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsUCPhoneConfiguration).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="7cbbd-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="7cbbd-126">See Also</span></span>


[<span data-ttu-id="7cbbd-127">Administración de la autenticación de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7cbbd-127">Managing Lync Server 2013 authentication</span></span>](lync-server-2013-managing-lync-server-authentication.md)  


[<span data-ttu-id="7cbbd-128">Administrar dispositivos, teléfonos y aplicaciones cliente en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7cbbd-128">Managing devices, phones, and client applications in Lync Server 2013</span></span>](lync-server-2013-managing-devices-phones-and-client-applications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

