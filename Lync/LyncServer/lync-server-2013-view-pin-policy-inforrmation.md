---
title: 'Lync Server 2013: ver directivas de directiva de inforrmation'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: View PIN policy inforrmation
ms:assetid: 1d48b060-d77f-44ee-b70f-3ce128aedac4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687985(v=OCS.15)
ms:contentKeyID: 49733575
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ad912c4442a243beaaa4410d8931f0940d743177
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34850100"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-pin-policy-inforrmation-in-lync-server-2013"></a>Ver inforrmation de directiva de PIN en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-23_

Puede usar la pestaña **Directiva de PIN** para ver la autenticación del número de identificación personal (PIN) de los usuarios que se conectan a Lync 2013 con teléfonos IP. Para utilizar la autenticación de PIN, asegúrese de que la opción **Habilitar autenticación PIN** esté seleccionada en la configuración del servicio web. Para obtener más información, vea modificar la configuración [de un servicio web existente en Lync Server 2013](lync-server-2013-modify-existing-web-service-configuration-settings.md).

Siga estos pasos para modificar una directiva de PIN de nivel de usuario o de sitio.

<div>

## <a name="to-view-information-about-a-pin-policy-in-lync-server-control-panel"></a>Para ver información sobre una directiva de PIN en el panel de control de Lync Server

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o asignada al rol CsServerAdministrator o CsAdministrator, inicie sesión en cualquier equipo de la red en el que haya implementado Lync Server 2013.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Seguridad** y, a continuación, en **Directiva de PIN**.

4.  En la página **Directiva de PIN**, haga clic en **Editar** y, a continuación, haga clic en **Mostrar detalles**.

</div>

<div>

## <a name="viewing-pin-policies-by-using-windows-powershell-cmdlets"></a>Visualización de directivas de PIN con cmdlets de Windows PowerShell

También puede ver directivas de PIN con Windows PowerShell y el cmdlet Get-CsPinPolicy. Este cmdlet se puede ejecutar desde el shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell. Para obtener más información sobre cómo usar Windows PowerShell remoto para conectarse a Lync Server, consulte el artículo del blog de Lync Server de Windows PowerShell "Inicio rápido: administrar Microsoft Lync Server [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)2010 mediante PowerShell remoto" en.

<div>

## <a name="to-view-pin-policies"></a>Para ver las directivas de PIN

  - Para ver información sobre todas las directivas de PIN, escriba el siguiente comando en el shell de administración de Lync Server y, a continuación, presione ENTRAR:
    
        Get-CsPinPolicy
    
    Devolverá información similar a la siguiente:
    
        Identity             : Global
        Description          :
        MinPasswordLength    : 5
        PINHistoryCount      : 0
        AllowCommonPatterns  : False
        PINLifetime          : 0
        MaximumLogonAttempts :

</div>

Para obtener más información, consulte el tema de ayuda para el cmdlet [Get-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsPinPolicy) .

</div>

<div>

## <a name="see-also"></a>Vea también


[Modificar las opciones de configuración de un servicio web existente en Lync Server 2013](lync-server-2013-modify-existing-web-service-configuration-settings.md)  
[Crear una nueva Directiva de PIN en Lync Server 2013](lync-server-2013-create-a-new-pin-policy.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

