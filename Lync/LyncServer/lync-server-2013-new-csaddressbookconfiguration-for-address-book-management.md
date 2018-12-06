---
title: new-csaddressbookconfiguration para la administración de la libreta de direcciones
TOCTitle: New-CsAddressBookConfiguration para la administración de la libreta de direcciones
ms:assetid: a58ddc8c-ae04-4141-b69e-e45374a67d72
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg429718(v=OCS.15)
ms:contentKeyID: 48276192
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# New-CsAddressBookConfiguration para la administración de la libreta de direcciones

 

_**Última modificación del tema:** 2012-11-01_

Quién puede ejecutar este cmdlet: De forma predeterminada, los miembros de los siguientes grupos tienen autorización para ejecutar el cmdlet New-CsAddressBookConfiguration localmente: RTCUniversalServerAdmins. Para devolver una lista de todos los roles de control de acceso basado en roles (RBAC) a los que se ha asignado este cmdlet (incluido cualquier otro rol RBAC personalizado que usted mismo haya creado), ejecute el siguiente comando en el símbolo del sistema de Windows PowerShell:

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "New-CsAddressBookConfiguration"}

El cmdlet New-CsAddressBookConfiguration crea una configuración nueva para administrar el comportamiento de la libreta de direcciones. Una característica específica de este cmdlet es la capacidad de definir si el servicio de libreta de direcciones crea los archivos de descarga del cliente, cómo se crean las reglas de normalización y si se deben usar, durante cuánto tiempo se conservarán los archivos delta y archivos delta compactos, a qué hora del día se creará la libreta de direcciones completa del archivo y cuál será la información interna para la sincronización de la información en la base de datos del usuario.

Por ejemplo:

    New-CsAddressBookConfiguration -Identity site:Redmond -KeepDuration 15 -SynchronizePollingInterval 00:10:00

Para obtener una descripción detallada del comando íntegro, remítase a lo siguiente en la referencia principal de RTCCmdlets de Windows PowerShell de Lync Server.

## Vea también

#### Otros recursos

[New-CsAddressBookConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsAddressBookConfiguration)

