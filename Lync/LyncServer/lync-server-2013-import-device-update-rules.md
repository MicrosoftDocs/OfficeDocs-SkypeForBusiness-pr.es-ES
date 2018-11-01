---
title: Importar reglas de actualización de dispositivos
TOCTitle: Importar reglas de actualización de dispositivos
ms:assetid: 919e9c87-912b-4bc9-92e7-5998fc2e0bf0
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ994056(v=OCS.15)
ms:contentKeyID: 52061679
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Importar reglas de actualización de dispositivos

 

_**Última modificación del tema:** 2013-02-23_

Las reglas de actualización de dispositivos solo se pueden importar con Windows PowerShell y el cmdlet **Import-CsDeviceUpdate**. Este cmdlet se puede ejecutar desde el Shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell.


> [!NOTE]
> Para más información sobre el uso de una conexión remota de Windows PowerShell a Lync Server, consulte el artículo del blog sobre Windows PowerShell de Lync Server "Inicio rápido: Administración de Microsoft Lync Server 2010 con PowerShell remoto" en <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>.




## Para importar reglas de actualización de dispositivos a un único servidor web

  - El comando siguiente importa reglas de actualización de dispositivos al servidor web atl-cs-001.litwareinc.com:
    
        Import-CsDeviceUpdate -Identity "service:WebServer:atl-cs-001.litwareinc.com" -FileName C:\Updates\UCUpdates.cab

## Para importar reglas de actualización de dispositivos a todos los servidores web

  - En este ejemplo, las reglas de actualización de dispositivos se importan a todos los servidores web implementados en su organización. Para que este comando funcione, la carpeta \\\\atl-fs-001.litwareinc.com\\Updates debe ser compartida y estar disponible para todos los servidores web.
    
        Get-CsService -WebServer | ForEach-Object {Import-CsDeviceUpdate -Identity $_.Identity -FileName \\atl-fs-001.litwareinc.com\Updates\UCUpdates.cab}

Para más información, consulte el tema de ayuda del cmdlet [Import-CsDeviceUpdate](https://docs.microsoft.com/en-us/powershell/module/skype/Import-CsDeviceUpdate).

## Vea también

#### Tareas

[Ver información sobre las reglas de actualización de dispositivos](lync-server-2013-view-information-about-device-update-rules.md)  
[Aprobar una regla de actualización de dispositivos](lync-server-2013-approve-a-device-update-rule.md)

