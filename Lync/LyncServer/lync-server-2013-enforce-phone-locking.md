---
title: 'Lync Server 2013: forzar el bloqueo del teléfono'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enforce phone locking
ms:assetid: 1f89298b-aea9-4952-93ca-0270b565792b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520963(v=OCS.15)
ms:contentKeyID: 48183594
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7f40f11f835c350b5038771f2ac9f47ab8fec0f2
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42207694"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="enforce-phone-locking-in-lync-server-2013"></a><span data-ttu-id="99db4-102">Aplicar el bloqueo de teléfono en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="99db4-102">Enforce phone locking in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="99db4-103">_**Última modificación del tema:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="99db4-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="99db4-104">Los dispositivos Lync Phone Edition pueden bloquearse por motivos de seguridad.</span><span class="sxs-lookup"><span data-stu-id="99db4-104">Lync Phone Edition devices can be locked for security purposes.</span></span> <span data-ttu-id="99db4-105">Si aplica el bloqueo telefónico, el dispositivo que ejecuta Lync Phone Edition se bloquea después de un período de tiempo que configure.</span><span class="sxs-lookup"><span data-stu-id="99db4-105">If you enforce phone lock, the device running Lync Phone Edition locks after a period of time that you configure.</span></span> <span data-ttu-id="99db4-106">Cuando un teléfono está bloqueado, un usuario puede realizar llamadas pero no puede tener acceso al calendario y a la información de contacto, el correo de voz o los registros de llamadas, ni usar la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="99db4-106">When a phone is locked, a user can make calls but cannot access calendar and contact information, voice mail, or call logs or use search.</span></span> <span data-ttu-id="99db4-107">Para desbloquear el teléfono, el usuario escribe un PIN.</span><span class="sxs-lookup"><span data-stu-id="99db4-107">To unlock the phone, the user enters a PIN.</span></span>

<span data-ttu-id="99db4-108">Para aplicar el bloqueo telefónico, habilítelo y configúrelo mediante el panel de control de Lync Server o los cmdlets de Lync Server PowerShell.</span><span class="sxs-lookup"><span data-stu-id="99db4-108">To enforce phone lock, enable and configure it by using Lync Server Control Panel or Lync Server PowerShell cmdlets.</span></span> <span data-ttu-id="99db4-109">Puede aplicar el bloqueo telefónico globalmente o solo en el sitio para el que está configurado.</span><span class="sxs-lookup"><span data-stu-id="99db4-109">You can enforce phone lock globally or only within the site for which it is configured.</span></span>

<div>

## <a name="to-configure-and-enforce-the-phone-lock"></a><span data-ttu-id="99db4-110">Para configurar y aplicar el bloqueo de teléfono</span><span class="sxs-lookup"><span data-stu-id="99db4-110">To configure and enforce the phone lock</span></span>

1.  <span data-ttu-id="99db4-111">Desde una cuenta de usuario asignada al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.</span><span class="sxs-lookup"><span data-stu-id="99db4-111">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="99db4-112">Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="99db4-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="99db4-113">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="99db4-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="99db4-114">Haga clic en **Clientes** y después en **Configuración de dispositivo**.</span><span class="sxs-lookup"><span data-stu-id="99db4-114">Click **Clients**, and then click **Device Configuration**.</span></span>

4.  <span data-ttu-id="99db4-115">En la pestaña **Configuración de dispositivo**, en la lista de configuraciones de dispositivos, haga doble clic en la configuración en la que desea cambiar los parámetros de bloqueo del teléfono.</span><span class="sxs-lookup"><span data-stu-id="99db4-115">On the **Device Configuration** tab, in the list of device configurations, double-click the configuration for which you want to change the phone lock settings.</span></span>

5.  <span data-ttu-id="99db4-116">En el cuadro de diálogo **Editar configuración de dispositivo**, compruebe que la casilla **Exigir bloqueo de dispositivo** esté activada.</span><span class="sxs-lookup"><span data-stu-id="99db4-116">In the **Edit Device Configuration** dialog box, verify that the **Enforce device locking** check box is selected.</span></span>

6.  <span data-ttu-id="99db4-117">En **longitud mínima del PIN**, acepte el valor predeterminado para el número mínimo de dígitos que el PIN de desbloqueo debe contener o especifique un nuevo valor.</span><span class="sxs-lookup"><span data-stu-id="99db4-117">In **Minimum PIN length**, accept the default value for the minimum number of digits that the unlock PIN must contain or specify a new value.</span></span> <span data-ttu-id="99db4-118">El intervalo para la longitud del PIN es de cuatro a 15 dígitos y el valor predeterminado es seis.</span><span class="sxs-lookup"><span data-stu-id="99db4-118">The range for the PIN length is four to 15 digits, and the default is six.</span></span>

7.  <span data-ttu-id="99db4-119">En **tiempo de espera de bloqueo por teléfono**, acepte el valor predeterminado para el período de tiempo mínimo antes de que se bloquee el teléfono o especifique un nuevo valor.</span><span class="sxs-lookup"><span data-stu-id="99db4-119">In **Phone lock time-out**, accept the default value for the minimum length of time before the phone locks itself or specify a new value.</span></span> <span data-ttu-id="99db4-120">El intervalo para el tiempo de espera es de 0 a 60 minutos y el valor predeterminado es 10.</span><span class="sxs-lookup"><span data-stu-id="99db4-120">The range for the timeout is 0 to 60 minutes, and the default is 10.</span></span> <span data-ttu-id="99db4-121">Especifique el valor en el formato HH:MM:SS.</span><span class="sxs-lookup"><span data-stu-id="99db4-121">Enter the value in the format HH:MM:SS.</span></span>

8.  <span data-ttu-id="99db4-122">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="99db4-122">Click **Commit**.</span></span>

</div>

<div>

## <a name="enforcing-phone-locking-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="99db4-123">Aplicación de bloqueo de teléfono mediante cmdlets de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="99db4-123">Enforcing Phone Locking by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="99db4-124">El bloqueo del teléfono se puede forzar mediante el cmdlet Set-CsUCPhoneConfiguration.</span><span class="sxs-lookup"><span data-stu-id="99db4-124">Phone locking can be enforced by using the Set-CsUCPhoneConfiguration cmdlet.</span></span> <span data-ttu-id="99db4-125">Este cmdlet se puede ejecutar desde el shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="99db4-125">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="99db4-126">Para obtener información detallada sobre cómo usar Windows PowerShell remoto para conectarse a Lync Server, consulte el artículo del blog de Lync Server Windows PowerShell "Inicio rápido: administración de Microsoft Lync Server [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)2010 mediante PowerShell remoto" en.</span><span class="sxs-lookup"><span data-stu-id="99db4-126">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-enable-phone-locking"></a><span data-ttu-id="99db4-127">Para habilitar el bloqueo de teléfono</span><span class="sxs-lookup"><span data-stu-id="99db4-127">To enable phone locking</span></span>

  - <span data-ttu-id="99db4-128">El siguiente comando habilita el bloqueo del teléfono para el sitio de Redmond.</span><span class="sxs-lookup"><span data-stu-id="99db4-128">The following command enables phone locking for the Redmond site.</span></span> <span data-ttu-id="99db4-129">Para deshabilitar el bloqueo del teléfono, configure la propiedad EnforcePhoneLock como False ($False).</span><span class="sxs-lookup"><span data-stu-id="99db4-129">To disable phone locking, set the EnforcePhoneLock property to False ($False).</span></span>
    
        Set-CsUCPhoneConfiguration -Identity" site:Redmond" -EnforcePhoneLock $True

</div>

<div>

## <a name="to-enable-phone-locking-and-modify-the-phone-lock-timeout"></a><span data-ttu-id="99db4-130">Para habilitar el bloqueo del teléfono y modificar el tiempo de espera de bloqueo del teléfono</span><span class="sxs-lookup"><span data-stu-id="99db4-130">To enable phone locking and modify the phone lock timeout</span></span>

  - <span data-ttu-id="99db4-131">Este comando permite el bloqueo del teléfono y también define el tiempo de espera para el bloqueo del teléfono en 30 minutos.</span><span class="sxs-lookup"><span data-stu-id="99db4-131">This command enables phone locking and also sets the phone lock timeout to 30 minutes.</span></span>
    
        Set-CsUCPhoneConfiguration -Identity" site:Redmond" -EnforcePhoneLock $True -PhoneLockTimeout "00:30:00"

</div>

<div>

## <a name="to-enable-phone-locking-throughout-the-organization"></a><span data-ttu-id="99db4-132">Para habilitar el bloqueo del teléfono en toda la organización</span><span class="sxs-lookup"><span data-stu-id="99db4-132">To enable phone locking throughout the organization</span></span>

  - <span data-ttu-id="99db4-133">En este ejemplo, el bloqueo del teléfono está habilitado en todas las opciones de configuración del teléfono de comunicaciones unificadas (UC) en uso en la organización.</span><span class="sxs-lookup"><span data-stu-id="99db4-133">In this example, phone locking is enabled on all the UC phone configuration settings in use in the organization.</span></span>
    
        Get-CsUCPhoneConfiguration | Set-CsUCPhoneConfiguration  -EnforcePhoneLock $True

</div>

<span data-ttu-id="99db4-134">Para obtener más información, consulte el tema de ayuda del cmdlet [set-CsUCPhoneConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsUCPhoneConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="99db4-134">For more information, see the help topic for the [Set-CsUCPhoneConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsUCPhoneConfiguration) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="99db4-135">Consulta también</span><span class="sxs-lookup"><span data-stu-id="99db4-135">See Also</span></span>


[<span data-ttu-id="99db4-136">Administración de la autenticación de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="99db4-136">Managing Lync Server 2013 authentication</span></span>](lync-server-2013-managing-lync-server-authentication.md)  


[<span data-ttu-id="99db4-137">Administración de dispositivos, teléfonos y aplicaciones cliente en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="99db4-137">Managing devices, phones, and client applications in Lync Server 2013</span></span>](lync-server-2013-managing-devices-phones-and-client-applications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

