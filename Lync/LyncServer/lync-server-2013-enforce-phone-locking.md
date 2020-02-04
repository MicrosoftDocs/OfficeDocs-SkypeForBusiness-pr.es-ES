---
title: 'Lync Server 2013: exigir bloqueo de teléfono'
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
ms.openlocfilehash: 9c781c09db1834d85a1df4532d1484e43d74ca48
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735480"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enforce-phone-locking-in-lync-server-2013"></a><span data-ttu-id="69fe4-102">Exigir el bloqueo de teléfono en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="69fe4-102">Enforce phone locking in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="69fe4-103">_**Última modificación del tema:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="69fe4-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="69fe4-104">Los dispositivos Lync Phone Edition se pueden bloquear por razones de seguridad.</span><span class="sxs-lookup"><span data-stu-id="69fe4-104">Lync Phone Edition devices can be locked for security purposes.</span></span> <span data-ttu-id="69fe4-105">Si aplica el bloqueo de teléfono, el dispositivo que ejecuta Lync Phone Edition se bloquea después de un período de tiempo configurado.</span><span class="sxs-lookup"><span data-stu-id="69fe4-105">If you enforce phone lock, the device running Lync Phone Edition locks after a period of time that you configure.</span></span> <span data-ttu-id="69fe4-106">Cuando un teléfono está bloqueado, un usuario puede hacer llamadas pero no puede acceder a la información del calendario y los contactos, al correo de voz o a los registros de llamadas o al usar la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="69fe4-106">When a phone is locked, a user can make calls but cannot access calendar and contact information, voice mail, or call logs or use search.</span></span> <span data-ttu-id="69fe4-107">Para desbloquear el teléfono, el usuario escribe un PIN.</span><span class="sxs-lookup"><span data-stu-id="69fe4-107">To unlock the phone, the user enters a PIN.</span></span>

<span data-ttu-id="69fe4-108">Para aplicar el bloqueo de teléfono, habilítelo y configúrelo con el panel de control de Lync Server o los cmdlets de PowerShell de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="69fe4-108">To enforce phone lock, enable and configure it by using Lync Server Control Panel or Lync Server PowerShell cmdlets.</span></span> <span data-ttu-id="69fe4-109">Puede exigir el bloqueo de teléfono en todo el mundo o solo en el sitio para el que está configurado.</span><span class="sxs-lookup"><span data-stu-id="69fe4-109">You can enforce phone lock globally or only within the site for which it is configured.</span></span>

<div>

## <a name="to-configure-and-enforce-the-phone-lock"></a><span data-ttu-id="69fe4-110">Para configurar y exigir el bloqueo de teléfono</span><span class="sxs-lookup"><span data-stu-id="69fe4-110">To configure and enforce the phone lock</span></span>

1.  <span data-ttu-id="69fe4-111">Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="69fe4-111">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="69fe4-112">Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="69fe4-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="69fe4-113">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="69fe4-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="69fe4-114">Haga clic en **clientes**y, a continuación, en **configuración del dispositivo**.</span><span class="sxs-lookup"><span data-stu-id="69fe4-114">Click **Clients**, and then click **Device Configuration**.</span></span>

4.  <span data-ttu-id="69fe4-115">En la pestaña **configuración de dispositivo** , en la lista de configuraciones de dispositivos, haga doble clic en la configuración para la que desea cambiar la configuración de bloqueo de teléfono.</span><span class="sxs-lookup"><span data-stu-id="69fe4-115">On the **Device Configuration** tab, in the list of device configurations, double-click the configuration for which you want to change the phone lock settings.</span></span>

5.  <span data-ttu-id="69fe4-116">En el cuadro de diálogo **Editar configuración de dispositivo** , compruebe que la casilla **exigir bloqueo de dispositivo** está activada.</span><span class="sxs-lookup"><span data-stu-id="69fe4-116">In the **Edit Device Configuration** dialog box, verify that the **Enforce device locking** check box is selected.</span></span>

6.  <span data-ttu-id="69fe4-117">En **longitud mínima de PIN**, acepte el valor predeterminado para el número mínimo de dígitos que el PIN de desbloqueo debe contener o especifique un nuevo valor.</span><span class="sxs-lookup"><span data-stu-id="69fe4-117">In **Minimum PIN length**, accept the default value for the minimum number of digits that the unlock PIN must contain or specify a new value.</span></span> <span data-ttu-id="69fe4-118">El intervalo para la longitud del PIN es de cuatro a 15 dígitos, y el valor predeterminado es seis.</span><span class="sxs-lookup"><span data-stu-id="69fe4-118">The range for the PIN length is four to 15 digits, and the default is six.</span></span>

7.  <span data-ttu-id="69fe4-119">En el **tiempo de espera de bloqueo telefónico**, acepte el valor predeterminado de la cantidad mínima de tiempo antes de que el teléfono se bloquee por sí mismo o especifique un nuevo valor.</span><span class="sxs-lookup"><span data-stu-id="69fe4-119">In **Phone lock time-out**, accept the default value for the minimum length of time before the phone locks itself or specify a new value.</span></span> <span data-ttu-id="69fe4-120">El intervalo para el tiempo de espera es de 0 a 60 minutos y el valor predeterminado es 10.</span><span class="sxs-lookup"><span data-stu-id="69fe4-120">The range for the timeout is 0 to 60 minutes, and the default is 10.</span></span> <span data-ttu-id="69fe4-121">Especifique el valor con el formato HH:MM:SS.</span><span class="sxs-lookup"><span data-stu-id="69fe4-121">Enter the value in the format HH:MM:SS.</span></span>

8.  <span data-ttu-id="69fe4-122">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="69fe4-122">Click **Commit**.</span></span>

</div>

<div>

## <a name="enforcing-phone-locking-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="69fe4-123">Exigir el bloqueo de teléfono con los cmdlets de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="69fe4-123">Enforcing Phone Locking by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="69fe4-124">El bloqueo de teléfono se puede exigir mediante el cmdlet Set-CsUCPhoneConfiguration.</span><span class="sxs-lookup"><span data-stu-id="69fe4-124">Phone locking can be enforced by using the Set-CsUCPhoneConfiguration cmdlet.</span></span> <span data-ttu-id="69fe4-125">Este cmdlet se puede ejecutar desde el shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="69fe4-125">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="69fe4-126">Para obtener más información sobre cómo usar Windows PowerShell remoto para conectarse a Lync Server, consulte el artículo del blog de Lync Server de Windows PowerShell "Inicio rápido: administrar Microsoft Lync Server [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)2010 mediante PowerShell remoto" en.</span><span class="sxs-lookup"><span data-stu-id="69fe4-126">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-enable-phone-locking"></a><span data-ttu-id="69fe4-127">Para habilitar el bloqueo de teléfono</span><span class="sxs-lookup"><span data-stu-id="69fe4-127">To enable phone locking</span></span>

  - <span data-ttu-id="69fe4-128">El siguiente comando habilita el bloqueo de teléfono para el sitio de Redmond.</span><span class="sxs-lookup"><span data-stu-id="69fe4-128">The following command enables phone locking for the Redmond site.</span></span> <span data-ttu-id="69fe4-129">Para deshabilitar el bloqueo de teléfono, establece la propiedad EnforcePhoneLock en false ($False).</span><span class="sxs-lookup"><span data-stu-id="69fe4-129">To disable phone locking, set the EnforcePhoneLock property to False ($False).</span></span>
    
        Set-CsUCPhoneConfiguration -Identity" site:Redmond" -EnforcePhoneLock $True

</div>

<div>

## <a name="to-enable-phone-locking-and-modify-the-phone-lock-timeout"></a><span data-ttu-id="69fe4-130">Para habilitar el bloqueo de teléfono y modificar el tiempo de espera de bloqueo de teléfono</span><span class="sxs-lookup"><span data-stu-id="69fe4-130">To enable phone locking and modify the phone lock timeout</span></span>

  - <span data-ttu-id="69fe4-131">Este comando habilita el bloqueo de teléfono y también establece el tiempo de espera de bloqueo telefónico en 30 minutos.</span><span class="sxs-lookup"><span data-stu-id="69fe4-131">This command enables phone locking and also sets the phone lock timeout to 30 minutes.</span></span>
    
        Set-CsUCPhoneConfiguration -Identity" site:Redmond" -EnforcePhoneLock $True -PhoneLockTimeout "00:30:00"

</div>

<div>

## <a name="to-enable-phone-locking-throughout-the-organization"></a><span data-ttu-id="69fe4-132">Para habilitar el bloqueo de teléfono en toda la organización</span><span class="sxs-lookup"><span data-stu-id="69fe4-132">To enable phone locking throughout the organization</span></span>

  - <span data-ttu-id="69fe4-133">En este ejemplo, el bloqueo de teléfono está habilitado en todas las opciones de configuración de teléfono UC en uso en la organización.</span><span class="sxs-lookup"><span data-stu-id="69fe4-133">In this example, phone locking is enabled on all the UC phone configuration settings in use in the organization.</span></span>
    
        Get-CsUCPhoneConfiguration | Set-CsUCPhoneConfiguration  -EnforcePhoneLock $True

</div>

<span data-ttu-id="69fe4-134">Para obtener más información, consulte el tema de ayuda para el cmdlet [set-CsUCPhoneConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsUCPhoneConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="69fe4-134">For more information, see the help topic for the [Set-CsUCPhoneConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsUCPhoneConfiguration) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="69fe4-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="69fe4-135">See Also</span></span>


[<span data-ttu-id="69fe4-136">Administración de la autenticación de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="69fe4-136">Managing Lync Server 2013 authentication</span></span>](lync-server-2013-managing-lync-server-authentication.md)  


[<span data-ttu-id="69fe4-137">Administrar dispositivos, teléfonos y aplicaciones cliente en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="69fe4-137">Managing devices, phones, and client applications in Lync Server 2013</span></span>](lync-server-2013-managing-devices-phones-and-client-applications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

