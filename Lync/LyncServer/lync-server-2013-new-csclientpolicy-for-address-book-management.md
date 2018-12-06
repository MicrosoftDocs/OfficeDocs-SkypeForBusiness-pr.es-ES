---
title: New-CsClientPolicy para la administración de la libreta de direcciones
TOCTitle: New-CsClientPolicy para la administración de la libreta de direcciones
ms:assetid: ef4415fc-82c4-4dc8-97d1-37a084553343
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg429726(v=OCS.15)
ms:contentKeyID: 48277097
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# New-CsClientPolicy para la administración de la libreta de direcciones

 

_**Última modificación del tema:** 2012-11-01_

Quién puede ejecutar este cmdlet: Generalmente, los miembros de los siguientes grupos tienen autorización para ejecutar el cmdlet New-CsClientPolicy: RTCUniversalServerAdmins. Para devolver una lista de todos los roles de control de acceso basado en roles (RBAC) a los que se ha asignado este cmdlet (incluido cualquier otro rol RBAC personalizado que usted mismo haya creado), ejecute el siguiente comando en el símbolo del sistema de Windows PowerShell:

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "New-CsClientPolicy"}

El cmdlet New-CsClientPolicy define una gran cantidad de configuraciones para el aprovisionamiento de clientes con funciones disponibles en Lync Server 2013. El parámetro AddressBookAvailability es relevante para el servicio de Libreta de direcciones. Este parámetro, que repercute directamente en las opciones disponibles para los clientes, presenta tres opciones:

  - WebSearchAndFileDownload

  - WebSearchOnly

  - FileDownloadOnly

Cuando se define, determina cómo acceden los clientes a la Libreta de direcciones. Si define este parámetro, defina una de las opciones. Si no modifica esta configuración, permanecerá en vigor la opción predeterminada, WebSearchAndFileDownload.

Por ejemplo:

    New-CsClientPolicy -Identity RedmondClientPolicy -DisableCalendarPresence $True -DisablePhonePresence $True -DisplayPhoto "PhotosFromADOnly" -AddressBookAvailability "WebSearchOnly"

## Vea también

#### Otros recursos

[New-CsClientPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsClientPolicy)

