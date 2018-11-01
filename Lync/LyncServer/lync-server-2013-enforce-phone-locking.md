---
title: Exigir el bloqueo del teléfono
TOCTitle: Exigir el bloqueo del teléfono
ms:assetid: 1f89298b-aea9-4952-93ca-0270b565792b
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg520963(v=OCS.15)
ms:contentKeyID: 48274652
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Exigir el bloqueo del teléfono

 

_**Última modificación del tema:** 2013-02-23_

Los dispositivos de Lync Phone Edition se pueden bloquear por razones de seguridad. Si aplica el bloqueo del teléfono, el dispositivo que ejecuta Lync Phone Edition se bloquea una vez transcurrido el período de tiempo que se configure. Cuando el teléfono está bloqueado, el usuario puede realizar llamadas, pero no puede acceder a la información de contactos y del calendario, al correo de voz ni a los registros de llamadas, y tampoco puede usar la búsqueda. Para desbloquear el teléfono, el usuario debe especificar un PIN.

Para aplicar el bloqueo del teléfono, habilítelo y configúrelo mediante el Panel de control de Lync Server o los cmdlets de PowerShell de Lync Server. Puede aplicar el bloqueo del teléfono de forma global o solo dentro del sitio para el cual está configurado.

## Para configurar y aplicar el bloqueo del teléfono

1.  Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y después introduzca la dirección URL de administración para abrir el panel de control de Lync Server. Para más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Abrir las herramientas administrativas de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Haga clic en **Clientes** y después en **Configuración de dispositivo**.

4.  En la pestaña **Configuración de dispositivo**, en la lista de configuraciones de dispositivos, haga doble clic en la configuración en la que desea cambiar los parámetros de bloqueo del teléfono.

5.  En el cuadro de diálogo **Editar configuración de dispositivo**, compruebe que la casilla **Exigir bloqueo de dispositivo** esté activada.

6.  En **Longitud mínima de PIN**, acepte el valor predeterminado para el número mínimo de dígitos que debe contener el PIN de desbloqueo o especifique un valor nuevo. La longitud del PIN puede oscilar entre 4 y 15 dígitos, y el valor predeterminado es 6.

7.  En **Tiempo de espera de bloqueo de teléfono**, acepte el valor predeterminado para el tiempo mínimo que trascurre hasta que el teléfono se bloquea o especifique un valor nuevo. El intervalo para el tiempo de espera oscila entre 0 y 60 minutos, y el valor predeterminado es 10. Especifique el valor en el formato HH:MM:SS.

8.  Haga clic en **Confirmar**.

## Aplicar el bloqueo del teléfono mediante cmdlets de Windows PowerShell

El bloqueo del teléfono puede aplicarse mediante el cmdlet Set-CsUCPhoneConfiguration. Este cmdlet puede ejecutarse desde el Shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell. Para más información sobre el uso de una conexión remota de Windows PowerShell a Lync Server, consulte el artículo del blog sobre Windows PowerShell de Lync Server "Inicio rápido: Administración de Microsoft Lync Server 2010 con PowerShell remoto" en [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## Para habilitar el bloqueo del teléfono

  - El siguiente comando habilita el bloqueo del teléfono para el sitio de Redmond. Para deshabilitar el bloqueo del teléfono, configure la propiedad EnforcePhoneLock como False ($False).
    
        Set-CsUCPhoneConfiguration -Identity" site:Redmond" -EnforcePhoneLock $True

## Para habilitar el bloqueo del teléfono y modificar el tiempo de espera de bloqueo del teléfono

  - Este comando permite el bloqueo del teléfono y también define el tiempo de espera para el bloqueo del teléfono en 30 minutos.
    
        Set-CsUCPhoneConfiguration -Identity" site:Redmond" -EnforcePhoneLock $True -PhoneLockTimeout "00:30:00"

## Para habilitar el bloqueo del teléfono en toda la organización

  - En este ejemplo, el bloqueo del teléfono está habilitado en todas las opciones de configuración del teléfono de comunicaciones unificadas (UC) en uso en la organización.
    
        Get-CsUCPhoneConfiguration | Set-CsUCPhoneConfiguration  -EnforcePhoneLock $True

Para obtener más información, consulte el tema de ayuda del cmdlet [Set-CsUCPhoneConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsUCPhoneConfiguration).

## Vea también

#### Conceptos

[Administrar la autenticación de Lync Server 2013](lync-server-2013-managing-lync-server-authentication.md)  

#### Otros recursos

[Administrar dispositivos, teléfonos y aplicaciones cliente en Lync Server 2013](lync-server-2013-managing-devices-phones-and-client-applications.md)

