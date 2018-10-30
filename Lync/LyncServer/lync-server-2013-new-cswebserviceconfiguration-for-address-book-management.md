---
title: new-cswebserviceconfiguration para la administración de la libreta de direcciones
TOCTitle: New-CsWebServiceConfiguration para la administración de la libreta de direcciones
ms:assetid: 49e4ecc5-aa3e-4dd4-a32c-b0dea3758fab
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg429703(v=OCS.15)
ms:contentKeyID: 48275185
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# New-CsWebServiceConfiguration para la administración de la libreta de direcciones

 

_**Última modificación del tema:** 2012-11-01_

Quién puede ejecutar este cmdlet: De forma predeterminada, los miembros de los siguientes grupos tienen autorización para ejecutar el cmdlet New-CsWebServiceConfiguration localmente: RTCUniversalServerAdmins. Para devolver una lista de todos los roles de control de acceso basado en roles (RBAC) a los que se ha asignado este cmdlet (incluido cualquier otro rol RBAC personalizado que usted mismo haya creado), ejecute el siguiente comando en el símbolo del sistema de Windows PowerShell:

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "New-CsWebServiceConfiguration"}

El cmdlet New-CsWebServiceConfiguration define una nueva configuración de los servicios web de su organización. El ámbito de la configuración de los servicios web solo puede ser de nivel de sitio o de nivel de servicio. No puede crear una configuración de servicios web de nivel global. El atributo EnableGroupExansion resulta de especial interés para la libreta de direcciones. Si se establece en True, los servicios web pueden responder a solicitudes de expansión de grupo.

Por ejemplo:

    New-CsWebServiceConfiguration -Identity site:Redmond -EnableGroupExpansion $False -UseCertificateAuth $True

Para obtener una descripción detallada del comando íntegro, remítase a lo siguiente en la referencia principal de RTCCmdlets de Windows PowerShell de Lync Server.

## Vea también

#### Otros recursos

[New-CsWebServiceConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsWebServiceConfiguration)

