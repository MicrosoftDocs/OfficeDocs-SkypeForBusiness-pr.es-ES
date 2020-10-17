---
title: 'Lync Server 2013: Test-CsAddressBookWebQuery para la administración de la libreta de direcciones'
description: 'Lync Server 2013: Test-CsAddressBookWebQuery para la administración de la libreta de direcciones.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test-CsAddressBookWebQuery for Address Book management
ms:assetid: 977a9c1f-5f4e-4539-9a26-8748b61a57d8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429716(v=OCS.15)
ms:contentKeyID: 48184865
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c7448733ed1477d36b887648154d66c96f9e6d0b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547446"
---
# <a name="test-csaddressbookwebquery-for-address-book-management-in-lync-server-2013"></a>Test-CsAddressBookWebQuery para la administración de la libreta de direcciones en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-11-01_

Quién puede ejecutar este cmdlet: de forma predeterminada, los miembros de los siguientes grupos tienen autorización para ejecutar el cmdlet Test-CsAddressBookWebQuery: RTCUniversalServerAdmins. Para devolver una lista de todos los roles de control de acceso basado en roles (RBAC) a los que se asignó este cmdlet (incluido cualquier otro rol RBAC personalizado que usted mismo haya creado), inicie el siguiente comando en el símbolo del sistema de Windows PowerShell:

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Test-CsAddressBookService"}

De forma similar a la transacción sintética Test-CsAddressBookService, Test-CsAddressBookWebQuery realiza una consulta en la consulta Web de la libreta de direcciones para asegurarse de que funciona correctamente. El cmdlet se conectará a la autenticación del vale web y presentará las credenciales especificadas en – UserCredential. Si se autentica, el cmdlet presenta la información – TargetSipAddress. El cmdlet debe informar de que se ha realizado correctamente si pudo recuperar la información sobre el contacto.

Por ejemplo:

    Test-CsAddressBookWebQuery -TargetFqdn atl-cs-001.contoso.com -UserCredential contoso\bob -UserSipAddress "sip:bob@contoso.com" -TargetSipAddress "sip:bob@contoso.com"

<div>

## <a name="see-also"></a>Vea también


[Test-CsAddressBookWebQuery](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookWebQuery)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

