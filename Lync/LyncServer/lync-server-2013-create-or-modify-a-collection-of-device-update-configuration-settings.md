---
title: "Crear o modificar grupo de opciones de configuración de actualización de dispositivos"
TOCTitle: "Créer ou mod. une collection de par. de conf. de la màj des périphériques"
ms:assetid: 3e8ce95f-a8c8-417c-b1f7-0f759a567aff
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ994029(v=OCS.15)
ms:contentKeyID: 52061657
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Crear o modificar una colección de opciones de configuración de actualización de dispositivos

 

_**Última modificación del tema:** 2016-12-08_

Los valores de configuración de actualización de dispositivos se pueden crear (solo en el ámbito del sitio) mediante Windows PowerShell y el cmdlet **New-CsDeviceUpdateConfiguration**, y se pueden modificar mediante el cmdlet **Set-CsDeviceUpdateConfiguration**. Estos cmdlets se pueden ejecutar desde el Shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell.


> [!NOTE]
> Para más información sobre el uso de una conexión remota de Windows PowerShell a Lync Server, consulte el artículo del blog sobre Windows PowerShell de Lync Server "Inicio rápido: Administración de Microsoft Lync Server 2010 con PowerShell remoto" en <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>.




## Para crear valores de configuración de actualización de dispositivos que usen los valores predeterminados

  - Este comando crea un nuevo conjunto de valores de configuración de actualización de dispositivos para el sitio Redmond:
    
        New-CsDeviceUpdateConfiguration -Identity "site:Redmond"
    
    Como no se especificó ningún parámetro (salvo el parámetro Identity obligatorio) en el comando anterior, la nueva colección de valores de configuración usará los valores predeterminados para todas sus propiedades.

## Para modificar un único valor de propiedad al crear valores de configuración de actualización de dispositivos

  - Para crear valores de configuración que usen valores de propiedad distintos, simplemente tiene que incluir el parámetro y el valor de parámetro adecuados. Por ejemplo, para crear una colección de valores de configuración de actualización de dispositivos que eliminen los archivos de registro antiguos cada 21 días de manera predeterminada, use un comando como este:
    
        New-CsDeviceUpdateConfiguration -Identity "site:Redmond" -LogCleanupInterval "21.00:00:00"

## Para cambiar varios valores de propiedad al crear valores de configuración de actualización de dispositivos

  - Se pueden modificar varios valores de propiedad incluyendo varios parámetros. Por ejemplo, este comando establece el intervalo de limpieza del registro en 21 días y el intervalo de vaciado del registro en 30 minutos:
    
        New-CsDeviceUpdateConfiguration -Identity "site:Redmond" -LogCleanupInterval "21.00:00:00" -LogFlushInterval "00:30:00"

Para obtener detalles sobre la modificación de valores de configuración de actualización de dispositivos existentes, consulte el tema de Ayuda del cmdlet [Set-CsDeviceUpdateConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsDeviceUpdateConfiguration). Para obtener detalles sobre la creación de colecciones de valores de configuración, consulte el tema de Ayuda del cmdlet [New-CsDeviceUpdateConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsDeviceUpdateConfiguration).

