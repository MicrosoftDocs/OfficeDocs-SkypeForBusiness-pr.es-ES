---
title: Test-CsAddressBookWebQuery para la administración de la libreta de direcciones
TOCTitle: Test-CsAddressBookWebQuery para la administración de la libreta de direcciones
ms:assetid: 977a9c1f-5f4e-4539-9a26-8748b61a57d8
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg429716(v=OCS.15)
ms:contentKeyID: 48276092
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Test-CsAddressBookWebQuery para la administración de la libreta de direcciones

 

_**Última modificación del tema:** 2012-11-01_

Quién puede ejecutar este cmdlet: De forma predeterminada, los miembros de los siguientes grupos tienen autorización para ejecutar el cmdlet Test-CsAddressBookWebQuery de forma local: RTCUniversalServerAdmins. Para devolver una lista de todos los roles de control de acceso basado en roles (RBAC) a los que se ha asignado este cmdlet (incluido cualquier otro rol RBAC personalizado que usted mismo haya creado), ejecute el siguiente comando en el símbolo del sistema de Windows PowerShell:

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Test-CsAddressBookService"}

De forma similar a lo que ocurre con la transacción sintética Test-CsAddressBookService, Test-CsAddressBookWebQuery formula una consulta en el servicio de consultas de la libreta de direcciones para asegurarse de que funciona adecuadamente. El cmdlet se conectará a la autenticación del servicio de vales web y presentará las credenciales especificadas en –UserCredential. Si se autentica, posteriormente, el cmdlet presentará la información –TargetSipAddress. El cmdlet notificará un estado correcto si pudo recuperar la información del contacto.

Por ejemplo:

    Test-CsAddressBookWebQuery -TargetFqdn atl-cs-001.contoso.com -UserCredential contoso\bob -UserSipAddress "sip:bob@contoso.com" -TargetSipAddress "sip:bob@contoso.com"

Para obtener una descripción detallada del comando íntegro, remítase a lo siguiente en la referencia principal de RTCCmdlets de Windows PowerShell de Lync Server.

## Vea también

#### Otros recursos

[Test-CsAddressBookWebQuery](https://docs.microsoft.com/en-us/powershell/module/skype/Test-CsAddressBookWebQuery)

