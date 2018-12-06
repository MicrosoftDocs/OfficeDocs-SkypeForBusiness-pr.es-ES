---
title: Test-CsAddressBookService para la administración de la libreta de direcciones
TOCTitle: Test-CsAddressBookService para la administración de la libreta de direcciones
ms:assetid: b88cea74-41fd-4c0e-9284-7135bff27a27
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg429720(v=OCS.15)
ms:contentKeyID: 48276449
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Test-CsAddressBookService para la administración de la libreta de direcciones

 

_**Última modificación del tema:** 2012-11-01_

Quién puede ejecutar este cmdlet: De forma predeterminada, los miembros de los siguientes grupos tienen autorización para ejecutar el cmdlet Test-CsAddressBookService de forma local: RTCUniversalServerAdmins. Para devolver una lista de todos los roles de control de acceso basado en roles (RBAC) a los que se ha asignado este cmdlet (incluido cualquier otro rol RBAC personalizado que usted mismo haya creado), ejecute el siguiente comando en el símbolo del sistema de Windows PowerShell:

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Test-CsAddressBookService"}

Lync Server 2013 incluye una cantidad de cmdlets que inician comandos sintéticos para confirmar que una función o característica específicas funcionan correctamente. Test-CsAddressBookService confirma que un usuario determinado puede conectarse y solicitar archivos locales desde el servicio web de la libreta de direcciones.

Por ejemplo:

    Test-CsAddressBookService -TargetFqdn atl-cs-001.contoso.com -UserCredential contoso\bob -UserSipAddress "sip:bob@contoso.com"

## Vea también

#### Otros recursos

[Test-CsAddressBookService](https://docs.microsoft.com/en-us/powershell/module/skype/Test-CsAddressBookService)

