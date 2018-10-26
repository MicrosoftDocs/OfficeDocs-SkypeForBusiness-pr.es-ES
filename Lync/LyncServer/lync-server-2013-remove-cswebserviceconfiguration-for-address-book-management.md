---
title: Remove-CsWebServiceConfiguration para la administración de la libreta de direcciones
TOCTitle: Remove-CsWebServiceConfiguration para la administración de la libreta de direcciones
ms:assetid: 91947cad-5cdd-41b9-83e1-650703c55879
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg429713(v=OCS.15)
ms:contentKeyID: 48276016
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Remove-CsWebServiceConfiguration para la administración de la libreta de direcciones

 

_**Última modificación del tema:** 2012-11-01_

Quién puede ejecutar este cmdlet: De manera predeterminada, los miembros de los siguientes grupos están autorizados para ejecutar el cmdlet Remove-CsWebServiceConfiguration en forma local: RTCUniversalServerAdmins. Para devolver una lista de todos los roles de control de acceso basado en roles (RBAC) a los que se ha asignado este cmdlet (incluido cualquier otro rol RBAC personalizado que usted mismo haya creado), ejecute el siguiente comando en el símbolo del sistema de Windows PowerShell:

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Remove-CsWebServiceConfiguration"}

Con el cmdlet Remove-CsWebServiceConfiguration, los administradores pueden quitar una configuración de servicios web que se hubiera creado anteriormente. El cmdlet no puede quitar la configuración global de servicios web.

Por ejemplo:

    Remove-CsWebServiceConfiguration -Identity site:Redmond

Para obtener una descripción detallada del comando íntegro, remítase a lo siguiente en la referencia principal de RTCCmdlets de Windows PowerShell de Lync Server.

## Vea también

#### Otros recursos

[Remove-CsWebServiceConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsWebServiceConfiguration)

