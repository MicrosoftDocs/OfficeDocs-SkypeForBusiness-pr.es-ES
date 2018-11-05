---
title: Set-CsClientPolicy para la administración de la libreta de direcciones
TOCTitle: Set-CsClientPolicy para la administración de la libreta de direcciones
ms:assetid: e7788bea-606f-481a-a3a4-1855ac028493
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg429723(v=OCS.15)
ms:contentKeyID: 48277023
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Set-CsClientPolicy para la administración de la libreta de direcciones

 

_**Última modificación del tema:** 2012-11-01_

Quién puede ejecutar este cmdlet: de forma predeterminada, los miembros de los siguientes grupos están autorizados para ejecutar localmente el cmdlet Set-CsClientPolicy: RTCUniversalServerAdmins. Para devolver una lista de todos los roles de control de acceso basado en roles (RBAC) a los que se ha asignado este cmdlet (incluido cualquier otro rol RBAC personalizado que usted mismo haya creado), ejecute el siguiente comando en el símbolo del sistema de Windows PowerShell:

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClientPolicy"}

Similar a New-CsClientPolicy, el cmdlet Set-CsClientPolicy permite modificar configuraciones del cliente ya existentes.

Por ejemplo:

    Set-CsClientPolicy -Identity RedmondClientPolicy -WebServicePollInterval "00:15:00" -AddressBookAvailability "WebSearchAndFileDownload"

Para ver una descripción detallada del comando íntegro, consulte lo siguiente en la referencia principal a los RTCCmdlets de Windows PowerShell de Lync Server.

## Vea también

#### Otros recursos

[Set-CsClientPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsClientPolicy)

