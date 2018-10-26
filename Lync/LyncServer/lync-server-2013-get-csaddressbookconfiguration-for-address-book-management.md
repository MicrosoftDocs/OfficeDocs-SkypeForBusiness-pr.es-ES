---
title: Get-CsAddressBookConfiguration para la administración de la libreta de direcciones
TOCTitle: Get-CsAddressBookConfiguration para la administración de la libreta de direcciones
ms:assetid: bd62f916-caf3-4e10-ada4-631bbb331ef1
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg429721(v=OCS.15)
ms:contentKeyID: 48276502
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Get-CsAddressBookConfiguration para la administración de la libreta de direcciones

 

_**Última modificación del tema:** 2012-11-01_

Quién puede ejecutar este cmdlet: De forma predeterminada, los miembros de los siguientes grupos están autorizados a ejecutar el cmdlet Get-CsAddressBookConfiguration de forma local: RTCUniversalServerAdmins. Para devolver una lista de todos los roles de control de acceso basado en roles (RBAC) a los que se ha asignado este cmdlet (incluido cualquier otro rol RBAC personalizado que usted mismo haya creado), ejecute el siguiente comando en el símbolo del sistema de Windows PowerShell:

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Get-CsAddressBookConfiguration"}

El cmdlet Get-CsAddressBookConfiguration devuelve información sobre una configuración que ya existe.

Por ejemplo:

    Get-CsAddressBookConfiguration -Identity site:Redmond

Si se combina la funcionalidad de Get-CsAddressBookConfiguration y de Set-CsAddressBookConfiguration, el administrador puede definir qué configuraciones se van modificar y, posteriormente, aplicar estas modificaciones. Por ejemplo, si se combina:

    Get-CsAddressBookConfiguration -Filter site:* | Set-CsAddressBookConfiguration -RunTimeOfDay 23:00

Se obtienen todas las configuraciones en todos los sitios y se aplica el RunTimeOfDay de 23:00 horas a las configuraciones.

Para obtener una descripción detallada del comando íntegro, remítase a lo siguiente en la referencia principal de RTCCmdlets de Windows PowerShell de Lync Server.

## Vea también

#### Otros recursos

[Get-CsAddressBookConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsAddressBookConfiguration)

