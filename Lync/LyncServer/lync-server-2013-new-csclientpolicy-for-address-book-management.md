---
title: 'Lync Server 2013: nuevo-ClientPolicy para la administración de libretas de direcciones'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: New-CsClientPolicy for Address Book management
ms:assetid: ef4415fc-82c4-4dc8-97d1-37a084553343
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429726(v=OCS.15)
ms:contentKeyID: 48185771
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3f68f6cfa2fde4d1e5a2bc58a36478a60060dd5e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765761"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="new-csclientpolicy-for-address-book-management-in-lync-server-2013"></a>Nuevo: ClientPolicy para la administración de libretas de direcciones en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-11-01_

¿Quién puede ejecutar este cmdlet? de forma predeterminada, los miembros de los siguientes grupos tienen autorización para ejecutar el cmdlet New-ClientPolicy: RTCUniversalServerAdmins. Para devolver una lista de todas las funciones de control de acceso basado en roles (RBAC) a las que se ha asignado este cmdlet (incluidos los roles RBAC que haya creado usted mismo), ejecute el siguiente comando desde el símbolo del sistema de Windows PowerShell:

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "New-CsClientPolicy"}

El cmdlet New-ClientPolicy define un gran número de opciones para aprovisionar los clientes de las características que están disponibles en Lync Server 2013. Para el servicio de libreta de direcciones, el parámetro AddressBookAvailability es de interés. Este parámetro, que afecta directamente a las opciones disponibles para los clientes, tiene tres opciones posibles:

  - WebSearchAndFileDownload

  - WebSearchOnly

  - FileDownloadOnly

Cuando se define, determina cómo se obtiene acceso a la libreta de direcciones por parte de los clientes. Si define este parámetro, debe definir una de las opciones. Si no modifica esta configuración, el WebSearchAndFileDownload predeterminado permanece en vigor.

Por ejemplo:

    New-CsClientPolicy -Identity RedmondClientPolicy -DisableCalendarPresence $True -DisablePhonePresence $True -DisplayPhoto "PhotosFromADOnly" -AddressBookAvailability "WebSearchOnly"

<div>

## <a name="see-also"></a>Vea también


[New-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsClientPolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

