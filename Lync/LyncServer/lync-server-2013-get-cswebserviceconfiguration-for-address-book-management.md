---
title: Get-CsWebServiceConfiguration para la administración de la libreta de direcciones
TOCTitle: Get-CsWebServiceConfiguration para la administración de la libreta de direcciones
ms:assetid: 0b223733-5224-47d1-9b47-2109e6f135c9
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg429692(v=OCS.15)
ms:contentKeyID: 48274392
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Get-CsWebServiceConfiguration para la administración de la libreta de direcciones

 

_**Última modificación del tema:** 2012-11-01_

Quién puede ejecutar este cmdlet: De forma predeterminada, los miembros de los siguientes grupos tienen autorización para ejecutar el cmdlet Get-CsWebServiceConfiguration localmente: RTCUniversalUserAdmins, RTCUniversalServerAdmins. Para devolver una lista de todos los roles de control de acceso basado en roles (RBAC) a los que se ha asignado este cmdlet (incluido cualquier otro rol RBAC personalizado que usted mismo haya creado), ejecute el siguiente comando en el símbolo del sistema de Windows PowerShell:

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Get-CsWebServiceConfiguration"}

Get-CsWebServiceConfiguration devuelve información de la configuración de los servicios web que se encuentran actualmente en uso en su organización. Para los servicios de libreta de direcciones es interesante el estado de la función de expansión de lista de distribución. Si el atributo EnableGroupExpansion es True, significa que su organización admite la expansión de grupos.

Por ejemplo:

    Get-CsWebServiceConfiguration -Identity site:Redmond

Para obtener una descripción detallada del comando íntegro, remítase a lo siguiente en la referencia principal de RTCCmdlets de Windows PowerShell de Lync Server.

## Vea también

#### Otros recursos

[Get-CsWebServiceConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsWebServiceConfiguration)

