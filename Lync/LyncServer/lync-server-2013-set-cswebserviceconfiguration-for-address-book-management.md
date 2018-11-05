---
title: Set-CsWebServiceConfiguration para la administración de la libreta de direcciones
TOCTitle: Set-CsWebServiceConfiguration para la administración de la libreta de direcciones
ms:assetid: 79d0edf5-23f3-4845-a7b7-e11b5a928bab
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg429709(v=OCS.15)
ms:contentKeyID: 48275754
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Set-CsWebServiceConfiguration para la administración de la libreta de direcciones

 

_**Última modificación del tema:** 2012-11-01_

Quién puede ejecutar este cmdlet: De forma predeterminada, los miembros de los siguientes grupos tienen autorización para ejecutar el cmdlet Set-CsWebServiceConfiguration localmente: RTCUniversalServerAdmins. Para devolver una lista de todos los roles de control de acceso basado en roles (RBAC) a los que se ha asignado este cmdlet (incluido cualquier otro rol RBAC personalizado que usted mismo haya creado), ejecute el siguiente comando en el símbolo del sistema de Windows PowerShell:

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsWebServiceConfiguration"}

Con el cmdlet Set-CsWebServiceConfiguration, el administrador puede redefinir un atributo existente en la configuración de servicios web.

Por ejemplo:

    Set-CsWebServiceConfiguration -Identity site:Redmond -EnableGroupExpansion $True

Para obtener una descripción detallada del comando íntegro, remítase a lo siguiente en la referencia principal de RTCCmdlets de Windows PowerShell de Lync Server.

## Vea también

#### Otros recursos

[Set-CsWebServiceConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsWebServiceConfiguration)

