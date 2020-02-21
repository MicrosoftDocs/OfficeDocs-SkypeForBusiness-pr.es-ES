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

# <a name="enforce-phone-locking-in-lync-server-2013"></a>Aplicar el bloqueo de teléfono en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-23_

Los dispositivos Lync Phone Edition pueden bloquearse por motivos de seguridad. Si aplica el bloqueo telefónico, el dispositivo que ejecuta Lync Phone Edition se bloquea después de un período de tiempo que configure. Cuando un teléfono está bloqueado, un usuario puede realizar llamadas pero no puede tener acceso al calendario y a la información de contacto, el correo de voz o los registros de llamadas, ni usar la búsqueda. Para desbloquear el teléfono, el usuario escribe un PIN.

Para aplicar el bloqueo telefónico, habilítelo y configúrelo mediante el panel de control de Lync Server o los cmdlets de Lync Server PowerShell. Puede aplicar el bloqueo telefónico globalmente o solo en el sitio para el que está configurado.

<div>

## <a name="to-configure-and-enforce-the-phone-lock"></a>Para configurar y aplicar el bloqueo de teléfono

1.  Desde una cuenta de usuario asignada al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Haga clic en **Clientes** y después en **Configuración de dispositivo**.

4.  En la pestaña **Configuración de dispositivo**, en la lista de configuraciones de dispositivos, haga doble clic en la configuración en la que desea cambiar los parámetros de bloqueo del teléfono.

5.  En el cuadro de diálogo **Editar configuración de dispositivo**, compruebe que la casilla **Exigir bloqueo de dispositivo** esté activada.

6.  En **longitud mínima del PIN**, acepte el valor predeterminado para el número mínimo de dígitos que el PIN de desbloqueo debe contener o especifique un nuevo valor. El intervalo para la longitud del PIN es de cuatro a 15 dígitos y el valor predeterminado es seis.

7.  En **tiempo de espera de bloqueo por teléfono**, acepte el valor predeterminado para el período de tiempo mínimo antes de que se bloquee el teléfono o especifique un nuevo valor. El intervalo para el tiempo de espera es de 0 a 60 minutos y el valor predeterminado es 10. Especifique el valor en el formato HH:MM:SS.

8.  Haga clic en **Confirmar**.

</div>

<div>

## <a name="enforcing-phone-locking-by-using-windows-powershell-cmdlets"></a>Aplicación de bloqueo de teléfono mediante cmdlets de Windows PowerShell

El bloqueo del teléfono se puede forzar mediante el cmdlet Set-CsUCPhoneConfiguration. Este cmdlet se puede ejecutar desde el shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell. Para obtener información detallada sobre cómo usar Windows PowerShell remoto para conectarse a Lync Server, consulte el artículo del blog de Lync Server Windows PowerShell "Inicio rápido: administración de Microsoft Lync Server [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)2010 mediante PowerShell remoto" en.

<div>

## <a name="to-enable-phone-locking"></a>Para habilitar el bloqueo de teléfono

  - El siguiente comando habilita el bloqueo del teléfono para el sitio de Redmond. Para deshabilitar el bloqueo del teléfono, configure la propiedad EnforcePhoneLock como False ($False).
    
        Set-CsUCPhoneConfiguration -Identity" site:Redmond" -EnforcePhoneLock $True

</div>

<div>

## <a name="to-enable-phone-locking-and-modify-the-phone-lock-timeout"></a>Para habilitar el bloqueo del teléfono y modificar el tiempo de espera de bloqueo del teléfono

  - Este comando permite el bloqueo del teléfono y también define el tiempo de espera para el bloqueo del teléfono en 30 minutos.
    
        Set-CsUCPhoneConfiguration -Identity" site:Redmond" -EnforcePhoneLock $True -PhoneLockTimeout "00:30:00"

</div>

<div>

## <a name="to-enable-phone-locking-throughout-the-organization"></a>Para habilitar el bloqueo del teléfono en toda la organización

  - En este ejemplo, el bloqueo del teléfono está habilitado en todas las opciones de configuración del teléfono de comunicaciones unificadas (UC) en uso en la organización.
    
        Get-CsUCPhoneConfiguration | Set-CsUCPhoneConfiguration  -EnforcePhoneLock $True

</div>

Para obtener más información, consulte el tema de ayuda del cmdlet [set-CsUCPhoneConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsUCPhoneConfiguration) .

</div>

<div>

## <a name="see-also"></a>Consulta también


[Administración de la autenticación de Lync Server 2013](lync-server-2013-managing-lync-server-authentication.md)  


[Administración de dispositivos, teléfonos y aplicaciones cliente en Lync Server 2013](lync-server-2013-managing-devices-phones-and-client-applications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

