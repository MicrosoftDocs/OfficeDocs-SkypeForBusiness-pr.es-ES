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

# <a name="address-book-server-cmdlets-in-lync-server-2013"></a><span data-ttu-id="82890-102">Cmdlets del servidor de la libreta de direcciones en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="82890-102">Address Book Server cmdlets in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="82890-103">_**Última modificación del tema:** 2012-06-26_</span><span class="sxs-lookup"><span data-stu-id="82890-103">_**Topic Last Modified:** 2012-06-26_</span></span>

<span data-ttu-id="82890-104">Los servidores de la libreta de direcciones son intermediarios entre los servicios de dominio de Active Directory y Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="82890-104">Address Book servers are intermediaries between Active Directory Domain Services and Microsoft Lync Server 2013.</span></span> <span data-ttu-id="82890-105">El servidor de la libreta de direcciones garantiza que la información del usuario almacenada en Lync Server 2013 está sincronizada con la información de usuario almacenada en Active Directory.</span><span class="sxs-lookup"><span data-stu-id="82890-105">The Address Book server ensures that the user information stored in Lync Server 2013 is in synch with the user information stored in Active Directory.</span></span> <span data-ttu-id="82890-106">Esto se realiza mediante la sincronización periódica de archivos de libreta de direcciones con información almacenada en la base de datos de usuario.</span><span class="sxs-lookup"><span data-stu-id="82890-106">This is done by periodically synching Address Book files with information stored in the User database.</span></span> <span data-ttu-id="82890-107">A su vez, Lync Server incluye varios cmdlets para administrar servidores de libreta de direcciones.</span><span class="sxs-lookup"><span data-stu-id="82890-107">In turn, Lync Server includes a number of cmdlets for managing Address Book servers.</span></span>

<div>

## <a name="address-book-server-cmdlets"></a><span data-ttu-id="82890-108">Cmdlets del servidor de la libreta de direcciones</span><span class="sxs-lookup"><span data-stu-id="82890-108">Address Book Server Cmdlets</span></span>

<span data-ttu-id="82890-109">No puede configurar la configuración del servidor de la libreta de direcciones en el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="82890-109">You cannot configure the Address Book Server settings in Lync Server Control Panel.</span></span> <span data-ttu-id="82890-110">Windows PowerShell es la herramienta principal para administrar esta configuración.</span><span class="sxs-lookup"><span data-stu-id="82890-110">Windows PowerShell is the primary tool for managing these settings.</span></span> <span data-ttu-id="82890-111">A continuación se muestra una lista de cmdlets que se relacionan directamente con la administración del servidor de la libreta de direcciones:</span><span class="sxs-lookup"><span data-stu-id="82890-111">The following is a list of cmdlets that relate directly to managing the Address Book Server:</span></span>

<span data-ttu-id="82890-112">**Servidor de libreta de direcciones**</span><span class="sxs-lookup"><span data-stu-id="82890-112">**Address Book Server**</span></span>

  - <span></span>  
    <span data-ttu-id="82890-113">[Get-CsAddressBookConfiguration](https://technet.microsoft.com/en-us/library/Gg398132(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="82890-113">[Get-CsAddressBookConfiguration](https://technet.microsoft.com/en-us/library/Gg398132(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="82890-114">[Nuevo: CsAddressBookConfiguration](https://technet.microsoft.com/en-us/library/Gg398395(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="82890-114">[New-CsAddressBookConfiguration](https://technet.microsoft.com/en-us/library/Gg398395(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="82890-115">[Remove-CsAddressBookConfiguration](https://technet.microsoft.com/en-us/library/Gg398934(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="82890-115">[Remove-CsAddressBookConfiguration](https://technet.microsoft.com/en-us/library/Gg398934(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="82890-116">[Set-CsAddressBookConfiguration](https://technet.microsoft.com/en-us/library/Gg412784(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="82890-116">[Set-CsAddressBookConfiguration](https://technet.microsoft.com/en-us/library/Gg412784(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="82890-117">[Update-CsAddressBook](https://technet.microsoft.com/en-us/library/Gg398194(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="82890-117">[Update-CsAddressBook](https://technet.microsoft.com/en-us/library/Gg398194(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="82890-118">[Debug-CsAddressBookReplication](https://technet.microsoft.com/en-us/library/JJ205232(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="82890-118">[Debug-CsAddressBookReplication](https://technet.microsoft.com/en-us/library/JJ205232(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="82890-119">[Prueba-CsAddressBookService](https://technet.microsoft.com/en-us/library/Gg398661(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="82890-119">[Test-CsAddressBookService](https://technet.microsoft.com/en-us/library/Gg398661(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="82890-120">[Test-CsAddressBookWebQuery](https://technet.microsoft.com/en-us/library/Gg398773(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="82890-120">[Test-CsAddressBookWebQuery](https://technet.microsoft.com/en-us/library/Gg398773(v=OCS.15))</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="82890-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="82890-121">See Also</span></span>


[<span data-ttu-id="82890-122">Blog de Lync Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="82890-122">Lync Server PowerShell Blog</span></span>](http://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

