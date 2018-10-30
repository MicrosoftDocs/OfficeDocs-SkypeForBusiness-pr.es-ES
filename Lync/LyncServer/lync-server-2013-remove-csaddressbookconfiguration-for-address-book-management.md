---
title: 'Remove-CsAddressBookConfiguration para la administración de la libreta de direcciones'
TOCTitle: Remove-CsAddressBookConfiguration para la administración de la libreta de direcciones
ms:assetid: 5d173ebe-ec4d-4640-8432-a25071ea9cc5
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg429705(v=OCS.15)
ms:contentKeyID: 48275401
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Remove-CsAddressBookConfiguration para la administración de la libreta de direcciones

 

_**Última modificación del tema:** 2012-11-01_

Quién puede ejecutar este cmdlet: De manera predeterminada, los miembros de los siguientes grupos están autorizados para ejecutar localmente el cmdlet Remove-CsAddressBookConfiguration: RTCUniversalServerAdmins. Para devolver una lista de todos los roles de control de acceso basado en roles (RBAC) a los que se ha asignado este cmdlet (incluido cualquier otro rol RBAC personalizado que usted mismo haya creado), ejecute el siguiente comando en el símbolo del sistema de Windows PowerShell:

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Remove-CsAddressBookConfiguration"}

Como implica su nombre en inglés, el cmdlet Remove-CsAddressBookConfiguration eliminará la configuración basándose en la identidad de sitio definida.

Por ejemplo:

    Remove-CsAddressBookConfiguration -Identity site:Redmond

Para obtener una descripción detallada del comando íntegro, remítase a lo siguiente en la referencia principal de RTCCmdlets de Windows PowerShell de Lync Server.

## Vea también

#### Otros recursos

[Remove-CsAddressBookConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsAddressBookConfiguration)

