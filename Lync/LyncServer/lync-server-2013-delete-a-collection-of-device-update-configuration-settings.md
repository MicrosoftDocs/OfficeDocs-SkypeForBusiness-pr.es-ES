---
title: "Eliminar una colección de opciones de configuración de actualización de dispositivos"
TOCTitle: "Supp. une coll. de param. de conf. de la mise à jour des périphériques"
ms:assetid: 1a649136-34a9-42a7-a5b3-a78bbfe93f36
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ994019(v=OCS.15)
ms:contentKeyID: 52061602
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Eliminar una colección de opciones de configuración de actualización de dispositivos

 

_**Última modificación del tema:** 2013-02-20_

Los valores de configuración de actualización de dispositivos también se pueden eliminar usando Windows PowerShell y el cmdlet **Remove-CsdeviceUpdateConfiguration**. Este cmdlet se puede ejecutar desde el Shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell. Para más información sobre el uso de una conexión remota de Windows PowerShell a Lync Server, consulte el artículo del blog sobre Windows PowerShell de Lync Server "Inicio rápido: Administración de Microsoft Lync Server 2010 con PowerShell remoto" en [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).


## Para quitar una colección específica de valores de configuración de actualización de dispositivos

  - Este comando elimina los valores de configuración de actualización de dispositivos aplicados al sitio Redmond:
    
        Remove-CsDeviceUpdateConfiguration -Identity "site:Redmond"

## Para quitar todos los valores de configuración de actualización de dispositivos aplicados al ámbito de sitio

  - Este comando elimina todos los valores de configuración de actualización de dispositivos aplicados al ámbito de sitio:
    
        Get-CsDeviceUpdateConfiguration -Filter "site:*" | Remove-CsDeviceUpdateConfiguration

## Para quitar los valores de configuración de actualización de dispositivos en función del valor de la propiedad LogCleanUpInterval

  - Este comando elimina todos los valores de configuración de actualización de dispositivos en los que el intervalo de limpieza del registro es superior a 10 días (10.00:00:00):
    
        Get-CsDeviceUpdateConfiguration | Where-Object {$_.LogCleanUpInterval -gt "10.00:00:00" | Remove-CsDeviceUpdateConfiguration

Para obtener información detallada, consulte el tema de Ayuda acerca del cmdlet [Remove-CsDeviceUpdateConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsDeviceUpdateConfiguration).

