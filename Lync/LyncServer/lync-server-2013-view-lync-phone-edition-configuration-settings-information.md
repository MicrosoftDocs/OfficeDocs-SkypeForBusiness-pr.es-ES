---
title: Ver información de configuración de Lync Phone Edition
TOCTitle: Ver información de configuración de Lync Phone Edition
ms:assetid: 15f94478-651f-4063-9918-6a059f98df16
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ687976(v=OCS.15)
ms:contentKeyID: 49888899
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Ver información de configuración de Lync Phone Edition

 

_**Última modificación del tema:** 2013-02-23_

Puede ver información de configuración acerca de los dispositivos que ejecutan Lync Phone Edition. La información se organiza en colecciones. Al instalar Lync Server, obtiene una colección de valores de Lync Phone Edition que se aplican a todos los dispositivos que ejecutan Lync Phone Edition en su implementación. También puede crear nuevas colecciones de valores para un sitio específico. La configuración de sitio tiene prioridad sobre la configuración global. Cada colección de valores consta de un nombre, el ámbito (global o sitio), la configuración de seguridad SIP, el nivel de registro, el nivel de calidad de voz del servicio (QoS), la configuración de bloqueo del teléfono y los detalles de bloqueo de teléfono, es decir, la longitud mínima del número de identificación personal de desbloqueo (PIN) y el tiempo antes de que se bloquee el teléfono.

## Para ver la información de configuración acerca de dispositivos que ejecutan Lync Phone Edition

1.  Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y después introduzca la dirección URL de administración para abrir el panel de control de Lync Server. Para más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Abrir las herramientas administrativas de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Clientes** y, a continuación, en el botón de navegación **Configuración de dispositivo**.

4.  En la página **Configuración de dispositivo**, haga clic en la colección de valores de los que desea ver información. El nombre, el ámbito, la configuración de seguridad SIP, el nivel de calidad de voz y la configuración de bloqueo de teléfono se muestran en la página principal. Para ver el nivel de registro y los detalles de bloqueo de teléfono, haga clic en el menú **Editar** y, a continuación, en **Mostrar detalles**.

## Para ver la información de configuración de Lync Phone Edition mediante los cmdlets de Shell de administración de Lync Server

También puede ver los valores de configuración de Lync Phone Edition mediante el Shell de administración de Lync Server y el cmdlet **Get-CsUCPhoneConfiguration**. Puede ejecutar este cmdlet desde el Shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell. Para más información sobre el uso de una conexión remota de Windows PowerShell a Lync Server, consulte el artículo del blog sobre Windows PowerShell de Lync Server "Inicio rápido: Administración de Microsoft Lync Server 2010 con PowerShell remoto" en [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## Para ver la información de configuración de Lync Phone Edition

  - Para ver la información acerca de todos sus valores de configuración de Lync Phone Edition, escribe el siguiente comando en el Shell de administración de Lync Server y, a continuación, presione ENTRAR:
    
        Get-CsUCPhoneConfiguration
    
    El comando devuelve información similar a la siguiente:
    
        Identity             : Global
        CalendarPollInterval : 00:03:00
        EnforcePhoneLock     : True
        PhoneLockTimeout     : 00:10:00
        MinPhonePinLength    : 6
        SIPSecurityMode      : High
        VoiceDiffServTag     : 40
        Voice8021p           : 0
        LoggingLevel         : Off

Para obtener detalles, vea [Get-CsUCPhoneConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsUCPhoneConfiguration).

## Vea también

#### Tareas

[Creación o modificación de un conjunto de opciones de configuración de Lync Phone Edition](lync-server-2013-create-or-modify-a-collection-of-lync-phone-edition-configuration-settings.md)  
[Eliminación de un conjunto existente de opciones de configuración de Lync Phone Edition](lync-server-2013-delete-an-existing-collection-of-lync-phone-edition-configuration-settings.md)  
[Configuración de la seguridad para Lync Phone Edition](lync-server-2013-configure-security-settings-for-lync-phone-edition.md)  
[Exigir el bloqueo del teléfono](lync-server-2013-enforce-phone-locking.md)

