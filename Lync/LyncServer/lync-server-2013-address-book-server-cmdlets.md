---
title: 'Lync Server 2013: cmdlets del servidor de libreta de direcciones'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Address Book Server cmdlets
ms:assetid: 33da45da-3c57-4d04-9679-f0e5a0cfd37e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg415643(v=OCS.15)
ms:contentKeyID: 48183793
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 634e6ae86a68cece6472d04ba1870159dc9b866f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842920"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="address-book-server-cmdlets-in-lync-server-2013"></a>Cmdlets del servidor de la libreta de direcciones en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-06-26_

Los servidores de la libreta de direcciones son intermediarios entre los servicios de dominio de Active Directory y Microsoft Lync Server 2013. El servidor de la libreta de direcciones garantiza que la información del usuario almacenada en Lync Server 2013 está sincronizada con la información de usuario almacenada en Active Directory. Esto se realiza mediante la sincronización periódica de archivos de libreta de direcciones con información almacenada en la base de datos de usuario. A su vez, Lync Server incluye varios cmdlets para administrar servidores de libreta de direcciones.

<div>

## <a name="address-book-server-cmdlets"></a>Cmdlets del servidor de la libreta de direcciones

No puede configurar la configuración del servidor de la libreta de direcciones en el panel de control de Lync Server. Windows PowerShell es la herramienta principal para administrar esta configuración. A continuación se muestra una lista de cmdlets que se relacionan directamente con la administración del servidor de la libreta de direcciones:

**Servidor de libreta de direcciones**

  - <span></span>  
    [Get-CsAddressBookConfiguration](https://technet.microsoft.com/en-us/library/Gg398132(v=OCS.15))

  - <span></span>  
    [Nuevo: CsAddressBookConfiguration](https://technet.microsoft.com/en-us/library/Gg398395(v=OCS.15))

  - <span></span>  
    [Remove-CsAddressBookConfiguration](https://technet.microsoft.com/en-us/library/Gg398934(v=OCS.15))

  - <span></span>  
    [Set-CsAddressBookConfiguration](https://technet.microsoft.com/en-us/library/Gg412784(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Update-CsAddressBook](https://technet.microsoft.com/en-us/library/Gg398194(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Debug-CsAddressBookReplication](https://technet.microsoft.com/en-us/library/JJ205232(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Prueba-CsAddressBookService](https://technet.microsoft.com/en-us/library/Gg398661(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Test-CsAddressBookWebQuery](https://technet.microsoft.com/en-us/library/Gg398773(v=OCS.15))

</div>

<div>

## <a name="see-also"></a>Vea también


[Blog de Lync Server PowerShell](http://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

