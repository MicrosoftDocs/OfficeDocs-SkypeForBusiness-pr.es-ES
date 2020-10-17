---
title: 'Lync Server 2013: configurar las opciones de seguridad para Lync Phone Edition'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure security settings for Lync Phone Edition
ms:assetid: 6e7cec17-8a79-4428-9300-8821256c46cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521014(v=OCS.15)
ms:contentKeyID: 48184464
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4c06a4daac2fe78ba8d631890ab1f02ca5efe932
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48520397"
---
# <a name="configure-security-settings-for-lync-phone-edition-in-lync-server-2013"></a><span data-ttu-id="465da-102">Configurar las opciones de seguridad de Lync Phone Edition en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="465da-102">Configure security settings for Lync Phone Edition in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="465da-103">_**Última modificación del tema:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="465da-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="465da-104">Ayude a mejorar la seguridad de los dispositivos que ejecutan Lync Phone Edition a través de la configuración de seguridad SIP y las opciones de bloqueo de teléfono.</span><span class="sxs-lookup"><span data-stu-id="465da-104">Help improve the security of devices running Lync Phone Edition via your SIP security setting and phone lock settings.</span></span>

<div>

## <a name="to-configure-security-settings-for-lync-phone-edition"></a><span data-ttu-id="465da-105">Para establecer la configuración de seguridad de Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="465da-105">To configure security settings for Lync Phone Edition</span></span>

1.  <span data-ttu-id="465da-106">Desde una cuenta de usuario asignada al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.</span><span class="sxs-lookup"><span data-stu-id="465da-106">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="465da-107">Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="465da-107">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="465da-108">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="465da-108">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="465da-109">En la barra de navegación izquierda, haga clic en **Clientes** y, a continuación, en **Configuración de dispositivo**.</span><span class="sxs-lookup"><span data-stu-id="465da-109">In the left navigation bar, click **Clients**, and then click **Device Configuration**.</span></span>

4.  <span data-ttu-id="465da-110">En la página **Configuración de dispositivo**, en la lista de configuraciones de dispositivos, haga doble clic en la configuración en la que desea cambiar los parámetros de seguridad.</span><span class="sxs-lookup"><span data-stu-id="465da-110">On the **Device Configuration** page, in the list of device configurations, double-click the configuration for which you want to change security settings.</span></span>

5.  <span data-ttu-id="465da-p102">En **Editar configuración de dispositivo**, en **Seguridad SIP**, especifique el nivel de seguridad SIP. El nivel predeterminado, que recomendamos utilizar, es **Alto**.</span><span class="sxs-lookup"><span data-stu-id="465da-p102">In **Edit Device Configuration**, in **SIP security**, specify the SIP security level. The default level is **High**, which we recommend using.</span></span>

6.  <span data-ttu-id="465da-p103">En **Editar configuración de dispositivo**, en **Bloqueo del teléfono**, active o desactive la casilla **Forzar bloqueo del dispositivo** (activada de forma predeterminada) y especifique la longitud mínima del PIN (6 caracteres de forma predeterminada) y el tiempo de espera (10 minutos de forma predeterminada). Recomendamos que se utilicen los valores predeterminados o bien que se incremente la longitud del PIN y se disminuya el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="465da-p103">In **Edit Device Configuration**, under **Phone Lock**, select or clear the **Enforce device locking** check box (selected by default) and specify the minimum PIN length (6 characters by default) and timeout period (10 minutes by default). We recommend using these defaults or increasing the PIN length and/or decreasing the timeout period.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="465da-115">Para obtener más información, consulte <A href="lync-server-2013-enforce-phone-locking.md">forzar el bloqueo del teléfono en Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="465da-115">For details, see <A href="lync-server-2013-enforce-phone-locking.md">Enforce phone locking in Lync Server 2013</A>.</span></span>

    
    </div>

</div>

<div>

## <a name="configuring-security-settings-for-lync-phone-edition-phones-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="465da-116">Configuración de las opciones de seguridad para teléfonos con Lync Phone Edition mediante cmdlets de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="465da-116">Configuring Security Settings for Lync Phone Edition Phones by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="465da-117">La configuración de seguridad se puede administrar mediante el shell de administración de Lync Server y el cmdlet **Get-CsUCPhoneConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="465da-117">Security settings can be managed by using Lync Server Management Shell and the **Get-CsUCPhoneConfiguration** cmdlet.</span></span> <span data-ttu-id="465da-118">Este cmdlet se puede ejecutar desde el shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="465da-118">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="465da-119">Para obtener información detallada sobre cómo usar Windows PowerShell remoto para conectarse a Lync Server, consulte el artículo del blog de Lync Server Windows PowerShell "Inicio rápido: administración de Microsoft Lync Server 2010 mediante PowerShell remoto" en [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .</span><span class="sxs-lookup"><span data-stu-id="465da-119">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-modify-the-sip-security-mode"></a><span data-ttu-id="465da-120">Para modificar el modo de seguridad SIP</span><span class="sxs-lookup"><span data-stu-id="465da-120">To modify the SIP security mode</span></span>

  - <span data-ttu-id="465da-p105">Este comando establece como Medio el modo SIPSecurityMode para la colección global de ajustes de los teléfonos para UC. El nivel de seguridad SIP también se puede definir como Bajo o Alto (valor predeterminado).</span><span class="sxs-lookup"><span data-stu-id="465da-p105">This command sets the SIPSecurityMode for the global collection of UC phone settings to Medium. SIP security could also be set to Low or High (the default value).</span></span>
    
        Set-CsUCPhoneConfiguration -Identity global -SIPSecurityMode "Medium"

</div>

<div>

## <a name="to-modify-the-minimum-pin-length"></a><span data-ttu-id="465da-123">Para modificar la longitud mínima del PIN</span><span class="sxs-lookup"><span data-stu-id="465da-123">To modify the minimum PIN length</span></span>

  - <span data-ttu-id="465da-124">En este ejemplo, se modifican todos los ajustes de los teléfonos para UC de modo que se establece la longitud mínima del PIN en 7 dígitos.</span><span class="sxs-lookup"><span data-stu-id="465da-124">In this example, all the UC phone settings are modified to require a minimum PIN length of 7 digits.</span></span>
    
        Get-CsUCPhoneConfiguration | Set-CsUCPhoneConfiguration -MinPhonePinLength 7

</div>

<span data-ttu-id="465da-125">Para obtener más información, consulte [Get-CsUCPhoneConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsUCPhoneConfiguration).</span><span class="sxs-lookup"><span data-stu-id="465da-125">For details, see [Get-CsUCPhoneConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsUCPhoneConfiguration).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="465da-126">Consulte también</span><span class="sxs-lookup"><span data-stu-id="465da-126">See Also</span></span>


[<span data-ttu-id="465da-127">Administración de la autenticación de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="465da-127">Managing Lync Server 2013 authentication</span></span>](lync-server-2013-managing-lync-server-authentication.md)  


[<span data-ttu-id="465da-128">Administración de dispositivos, teléfonos y aplicaciones cliente en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="465da-128">Managing devices, phones, and client applications in Lync Server 2013</span></span>](lync-server-2013-managing-devices-phones-and-client-applications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

