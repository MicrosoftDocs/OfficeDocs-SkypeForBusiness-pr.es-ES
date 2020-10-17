---
title: 'Lync Server 2013: Get-CsAddressBookConfiguration para la administración de la libreta de direcciones'
description: 'Lync Server 2013: Get-CsAddressBookConfiguration para la administración de la libreta de direcciones.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Get-CsAddressBookConfiguration for Address Book management
ms:assetid: bd62f916-caf3-4e10-ada4-631bbb331ef1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429721(v=OCS.15)
ms:contentKeyID: 48185264
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 91b96aead7b7038464f3166691a5952b9ff850dc
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48567006"
---
# <a name="get-csaddressbookconfiguration-for-address-book-management-in-lync-server-2013"></a>Get-CsAddressBookConfiguration para la administración de la libreta de direcciones en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-11-01_

Quién puede ejecutar este cmdlet: De forma predeterminada, los miembros de los siguientes grupos están autorizados a ejecutar el cmdlet Get-CsAddressBookConfiguration de forma local: RTCUniversalServerAdmins. Para devolver una lista de todos los roles de control de acceso basado en roles (RBAC) a los que se ha asignado este cmdlet (incluido cualquier otro rol RBAC personalizado que usted mismo haya creado), ejecute el siguiente comando en el símbolo del sistema de Windows PowerShell:

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Get-CsAddressBookConfiguration"}

El cmdlet Get-CsAddressBookConfiguration devuelve información sobre una configuración que ya existe.

Por ejemplo:

    Get-CsAddressBookConfiguration -Identity site:Redmond

Si se combina la funcionalidad de Get-CsAddressBookConfiguration y de Set-CsAddressBookConfiguration, el administrador puede definir qué configuraciones se van modificar y, posteriormente, aplicar estas modificaciones. Por ejemplo, si se combina:

    Get-CsAddressBookConfiguration -Filter site:* | Set-CsAddressBookConfiguration -RunTimeOfDay 23:00

Se obtienen todas las configuraciones en todos los sitios y se aplica el RunTimeOfDay de 23:00 horas a las configuraciones.

<div>

## <a name="see-also"></a>Consulte también


[Get-CsAddressBookConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsAddressBookConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

