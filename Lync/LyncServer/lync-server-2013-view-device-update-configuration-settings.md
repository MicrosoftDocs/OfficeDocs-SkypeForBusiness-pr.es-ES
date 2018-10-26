---
title: "Lync Server 2013: Ver opciones de configuración de la actualización de dispositivos"
TOCTitle: Ver las opciones de configuración de la actualización de dispositivos
ms:assetid: aa6a70a9-bd77-4606-b797-ea6a3bab9cf2
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ994059(v=OCS.15)
ms:contentKeyID: 52061712
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Ver las opciones de configuración de la actualización de dispositivos en Lync Server 2013

 

_**Última modificación del tema:** 2016-12-08_

Puede ver las opciones de configuración del Servicio de actualización de dispositivos usando Shell de administración de Lync Server y el cmdlet **Get-CsDeviceUpdateConfiguration**, que puede ejecutar desde el Shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell.


> [!NOTE]
> Para más información sobre el uso de una conexión remota de Windows PowerShell a Lync Server, consulte el artículo del blog sobre Windows PowerShell de Lync Server "Inicio rápido: Administración de Microsoft Lync Server 2010 con PowerShell remoto" en <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>.





  - 
    
    Para ver información sobre todas sus rutas de voz, escriba el siguiente comando en el Shell de administración de Lync Server y presione Entrar:
    
        Get-CsDeviceUpdateConfiguration
    
    Este comando devolverá información similar a la siguiente:
    
        Identity               : Global
        ValidLogFileTypes      : {Watson, Config, Diaglog, CELog}
        ValidLogFileExtensions : {.dmp, .clg, .clg1, .clg2...}
        MaxLogFileSize         : 1024000
        MaxLogCacheLimit       : 512000
        LogCleanUpInterval     : 10.00:00:00
        LogFlushInterval       : 00:05:00
        LogCleanUpTimeOfDay    :

Si quiere detalles sobre este cmdlet, vea el tema de ayuda [Get-CsDeviceUpdateConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsDeviceUpdateConfiguration).

