---
title: 'Lync Server 2013: Ver registros de uso de la RTC'
TOCTitle: Ver registros de uso de la RTC
ms:assetid: 65025c78-c263-472c-9ff9-e170588f10b5
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398458(v=OCS.15)
ms:contentKeyID: 48275483
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Ver registros de uso de la RTC en Lync Server 2013

 

_**Última modificación del tema:** 2013-02-22_

Un registro de uso de RTC especifica la clase de llamada (por ejemplo, interna, local o de larga distancia) que pueden realizar los diversos usuarios o grupos de usuarios en una organización. Para obtener más información, consulte [Registros de uso de RTC en Lync Server 2013](lync-server-2013-pstn-usage-records.md) en la documentación de planeación.

## Para ver un registro de uso de RTC con Panel de control de Lync Server

1.  Inicie sesión en el equipo como miembro del grupo RTCUniversalServerAdmins o como miembro del rol CsVoiceAdministrator, CsServerAdministrator o CsAdministrator. Para más información, consulte [Delegar permisos de instalación en Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Abra una ventana del explorador y después introduzca la dirección URL de administración para abrir el panel de control de Lync Server. Para más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Abrir las herramientas administrativas de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Enrutamiento de voz** y, a continuación, en **Uso de RTC**.

4.  En la página **Uso de RTC**, resalte el registro de uso de RTC que desee ver, haga clic en **Editar** y, a continuación, haga clic en **Mostrar detalles**.
    

    > [!NOTE]
    > Una página de solo lectura del registro de uso de RTC seleccionado muestra las rutas y las directivas de voz asociadas.



## Visualización de información de uso de RTC con cmdlets de Windows PowerShell

Los usos de la RTC también se pueden consultar con Windows PowerShell y el cmdlet **Get-CsPstnUsage**. Este cmdlet se puede ejecutar desde el Shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell. Para más información sobre el uso de una conexión remota de Windows PowerShell a Lync Server, consulte el artículo del blog sobre Windows PowerShell de Lync Server "Inicio rápido: Administración de Microsoft Lync Server 2010 con PowerShell remoto" en [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## Para ver la información de uso de RTC con cmdlets de Windows PowerShell

  - Para ver información sobre todos los usos de la RTC, escriba el siguiente comando en el Shell de administración de Lync Server y presione ENTRAR:
    
        Get-CsPstnUsage
    
    Este comando devolverá información similar a la siguiente:
    
        Identity : Global
        Usage    : {Internal, Local, Long Distance}

Para ver información detallada, consulte [Get-CsPstnUsage](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsPstnUsage).

## Vea también

#### Tareas

[Crear una directiva de voz y configurar registros de uso de RTC en Lync Server 2013](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md)  
[Modificar una directiva de voz y configurar registros de uso de RTC en Lync Server 2013](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md)

