---
title: 'Lync Server 2013: Update-CsAddressBook para la administración de la libreta de direcciones'
description: 'Lync Server 2013: Update-CsAddressBook para la administración de la libreta de direcciones.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Update-CsAddressBook for Address Book management
ms:assetid: 0ffd2ef8-201c-44aa-8c64-1c7b0eaa7d48
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429695(v=OCS.15)
ms:contentKeyID: 48183428
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4adc7f94e2f31f64f6517b8cdf9bbcb0649f6c8b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48546246"
---
# <a name="update-csaddressbook-for-address-book-management-in-lync-server-2013"></a>Update-CsAddressBook para la administración de la libreta de direcciones en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-11-01_

Quién puede ejecutar este cmdlet: De forma predeterminada, los miembros de los siguientes grupos están autorizados a ejecutar el cmdlet Update-CsAddressBook de forma local: RTCUniversalUserAdmins, RTCUniversalServerAdmins. Para devolver una lista de todos los roles de control de acceso basado en roles (RBAC) a los que se ha asignado este cmdlet (incluido cualquier otro rol RBAC personalizado que usted mismo haya creado), ejecute el siguiente comando en el símbolo del sistema de Windows PowerShell:

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Update-CsAddressBook"}

El cmdlet Update-CsAddressBook sustituye al comando **abserver.exe –syncNow** de Office Communications Server. El objetivo del cmdlet es iniciar una sincronización inmediata, en lugar de esperar a la hora programada. El primer comando de ejemplo actualiza todas las libretas de direcciones de la organización. El segundo actualiza solo la libreta de direcciones asociada con el servidor definido.

<div>


> [!NOTE]  
> En Lync Server 2013, el replicador de usuarios de Lync Server tomará los cambios de Active Directory y actualizará la base de datos de usuarios de Lync Server en función de un intervalo configurado. El replicador de usuarios de Lync Server también propagará los cambios rápidamente a la base de datos de RTCab sin que el Administrador tenga que ejecutar Update-CSAddressBook. Los administradores solo tendrán que ejecutar Update-CSAddressBook si está habilitada la descarga del archivo de la libreta de direcciones.



</div>

Por ejemplo:

   ```PowerShell
    Update-CsAddressBook
   ```

   ```PowerShell
    Update-CsAddressBook -Fqdn atl-abs-001.contoso.com
   ```

<div>

## <a name="see-also"></a>Vea también


[Update-CsAddressBook](https://docs.microsoft.com/powershell/module/skype/Update-CsAddressBook)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

