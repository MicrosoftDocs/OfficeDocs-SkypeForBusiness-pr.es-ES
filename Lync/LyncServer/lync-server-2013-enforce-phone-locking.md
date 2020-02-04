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

# <a name="enforce-phone-locking-in-lync-server-2013"></a>Exigir el bloqueo de teléfono en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-23_

Los dispositivos Lync Phone Edition se pueden bloquear por razones de seguridad. Si aplica el bloqueo de teléfono, el dispositivo que ejecuta Lync Phone Edition se bloquea después de un período de tiempo configurado. Cuando un teléfono está bloqueado, un usuario puede hacer llamadas pero no puede acceder a la información del calendario y los contactos, al correo de voz o a los registros de llamadas o al usar la búsqueda. Para desbloquear el teléfono, el usuario escribe un PIN.

Para aplicar el bloqueo de teléfono, habilítelo y configúrelo con el panel de control de Lync Server o los cmdlets de PowerShell de Lync Server. Puede exigir el bloqueo de teléfono en todo el mundo o solo en el sitio para el que está configurado.

<div>

## <a name="to-configure-and-enforce-the-phone-lock"></a>Para configurar y exigir el bloqueo de teléfono

1.  Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Haga clic en **clientes**y, a continuación, en **configuración del dispositivo**.

4.  En la pestaña **configuración de dispositivo** , en la lista de configuraciones de dispositivos, haga doble clic en la configuración para la que desea cambiar la configuración de bloqueo de teléfono.

5.  En el cuadro de diálogo **Editar configuración de dispositivo** , compruebe que la casilla **exigir bloqueo de dispositivo** está activada.

6.  En **longitud mínima de PIN**, acepte el valor predeterminado para el número mínimo de dígitos que el PIN de desbloqueo debe contener o especifique un nuevo valor. El intervalo para la longitud del PIN es de cuatro a 15 dígitos, y el valor predeterminado es seis.

7.  En el **tiempo de espera de bloqueo telefónico**, acepte el valor predeterminado de la cantidad mínima de tiempo antes de que el teléfono se bloquee por sí mismo o especifique un nuevo valor. El intervalo para el tiempo de espera es de 0 a 60 minutos y el valor predeterminado es 10. Especifique el valor con el formato HH:MM:SS.

8.  Haga clic en **Confirmar**.

</div>

<div>

## <a name="enforcing-phone-locking-by-using-windows-powershell-cmdlets"></a>Exigir el bloqueo de teléfono con los cmdlets de Windows PowerShell

El bloqueo de teléfono se puede exigir mediante el cmdlet Set-CsUCPhoneConfiguration. Este cmdlet se puede ejecutar desde el shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell. Para obtener más información sobre cómo usar Windows PowerShell remoto para conectarse a Lync Server, consulte el artículo del blog de Lync Server de Windows PowerShell "Inicio rápido: administrar Microsoft Lync Server [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)2010 mediante PowerShell remoto" en.

<div>

## <a name="to-enable-phone-locking"></a>Para habilitar el bloqueo de teléfono

  - El siguiente comando habilita el bloqueo de teléfono para el sitio de Redmond. Para deshabilitar el bloqueo de teléfono, establece la propiedad EnforcePhoneLock en false ($False).
    
        Set-CsUCPhoneConfiguration -Identity" site:Redmond" -EnforcePhoneLock $True

</div>

<div>

## <a name="to-enable-phone-locking-and-modify-the-phone-lock-timeout"></a>Para habilitar el bloqueo de teléfono y modificar el tiempo de espera de bloqueo de teléfono

  - Este comando habilita el bloqueo de teléfono y también establece el tiempo de espera de bloqueo telefónico en 30 minutos.
    
        Set-CsUCPhoneConfiguration -Identity" site:Redmond" -EnforcePhoneLock $True -PhoneLockTimeout "00:30:00"

</div>

<div>

## <a name="to-enable-phone-locking-throughout-the-organization"></a>Para habilitar el bloqueo de teléfono en toda la organización

  - En este ejemplo, el bloqueo de teléfono está habilitado en todas las opciones de configuración de teléfono UC en uso en la organización.
    
        Get-CsUCPhoneConfiguration | Set-CsUCPhoneConfiguration  -EnforcePhoneLock $True

</div>

Para obtener más información, consulte el tema de ayuda para el cmdlet [set-CsUCPhoneConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsUCPhoneConfiguration) .

</div>

<div>

## <a name="see-also"></a>Vea también


[Administración de la autenticación de Lync Server 2013](lync-server-2013-managing-lync-server-authentication.md)  


[Administrar dispositivos, teléfonos y aplicaciones cliente en Lync Server 2013](lync-server-2013-managing-devices-phones-and-client-applications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

