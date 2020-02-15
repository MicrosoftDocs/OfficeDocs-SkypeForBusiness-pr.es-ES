---
title: 'Lync Server 2013: eliminar un objeto de contacto de teléfono de área común'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete a common area phone Contact object
ms:assetid: f4c139dc-f07c-4c75-9345-e291aea41173
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994087(v=OCS.15)
ms:contentKeyID: 51803999
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 98702f392020586b546d2db89fe6355923b47f67
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42042972"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-a-common-area-phone-contact-object-in-lync-server-2013"></a><span data-ttu-id="1b857-102">Eliminar un objeto de contacto de teléfono de área común en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1b857-102">Delete a common area phone Contact object in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1b857-103">_**Última modificación del tema:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="1b857-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="1b857-104">Es posible que desee eliminar el objeto de contacto asociado con un teléfono de área común.</span><span class="sxs-lookup"><span data-stu-id="1b857-104">You might want to delete the contact object associated with a common area phone.</span></span> <span data-ttu-id="1b857-105">Por ejemplo, si quita el teléfono de una sala de empleados, no es necesario que tenga un objeto de contacto asociado con ese teléfono.</span><span class="sxs-lookup"><span data-stu-id="1b857-105">For example, if you remove the phone from an employee lounge, there’s no need to have a contact object associated with that phone.</span></span> <span data-ttu-id="1b857-106">El cmdlet **Remove-CsCommonAreaPhone** proporciona una forma de eliminar cuentas de teléfono de área común.</span><span class="sxs-lookup"><span data-stu-id="1b857-106">The **Remove-CsCommonAreaPhone** cmdlet provides a way for you to delete common area phone accounts.</span></span> <span data-ttu-id="1b857-107">Cuando se ejecuta este cmdlet, el teléfono se elimina de la lista de teléfonos de área común devuelta por **Get-CsCommonAreaPhone**.</span><span class="sxs-lookup"><span data-stu-id="1b857-107">When you run this cmdlet, the phone is deleted from the list of common area phones returned by **Get-CsCommonAreaPhone**.</span></span> <span data-ttu-id="1b857-108">Además, el objeto de contacto asociado con ese teléfono se elimina de servicios de dominio de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="1b857-108">In addition, the contact object associated with that phone is deleted from Active Directory Domain Services.</span></span>

<span data-ttu-id="1b857-109">Use **Remove-CsCommonAreaPhone** para quitar un teléfono de área común o todos los teléfonos de área común que tengan un elemento común, como un nombre para mostrar o un país y un código de área.</span><span class="sxs-lookup"><span data-stu-id="1b857-109">Use **Remove-CsCommonAreaPhone** to remove one common area phone or all common area phones that have a common element, such as a display name or country and area code.</span></span> <span data-ttu-id="1b857-110">Puede ejecutar este cmdlet desde el shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1b857-110">You can run this cmdlet from either the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="1b857-111">Para obtener información detallada sobre cómo usar Windows PowerShell remoto para conectarse a Lync Server, consulte el artículo del blog de Lync Server Windows PowerShell "Inicio rápido: administración de Microsoft Lync Server [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)2010 mediante PowerShell remoto" en.</span><span class="sxs-lookup"><span data-stu-id="1b857-111">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>


<div>

## <a name="removing-a-specified-common-area-phone"></a><span data-ttu-id="1b857-112">Quitar un teléfono de área común especificado</span><span class="sxs-lookup"><span data-stu-id="1b857-112">Removing a Specified Common Area Phone</span></span>

  - <span data-ttu-id="1b857-113">El siguiente comando quita el teléfono de área común con la dirección SIP sip:mainlobby@litwareinc.com:</span><span class="sxs-lookup"><span data-stu-id="1b857-113">The following command removes the common area phone with the SIP address sip:mainlobby@litwareinc.com:</span></span>
    
        Remove-CsCommonAreaPhone -Identity "sip:mainlobby@litwareinc.com"

</div>

<div>

## <a name="removing-common-area-phones-based-on-their-display-name"></a><span data-ttu-id="1b857-114">Eliminación de teléfonos de área común en función de su nombre para mostrar</span><span class="sxs-lookup"><span data-stu-id="1b857-114">Removing Common Area Phones Based on Their Display Name</span></span>

  - <span data-ttu-id="1b857-115">Este comando quita todos los teléfonos de área común donde el nombre para mostrar incluye el valor de cadena "Building 14":</span><span class="sxs-lookup"><span data-stu-id="1b857-115">This command removes all the common area phones where the display name includes the string value "Building 14":</span></span>
    
        Get-CsCommonAreaPhone | Where-Object {$_.DisplayName -match "Building 14"} | Remove-CsCommonAreaPhone

</div>

<div>

## <a name="removing-common-area-phones-based-on-their-country-and-area-codes"></a><span data-ttu-id="1b857-116">Quitar los teléfonos de área común en función de sus códigos de área y país</span><span class="sxs-lookup"><span data-stu-id="1b857-116">Removing Common Area Phones Based on Their Country and Area Codes</span></span>

  - <span data-ttu-id="1b857-117">Este comando quita todos los teléfonos de área común de los Estados Unidos (código de país 1) y el código de área 425:</span><span class="sxs-lookup"><span data-stu-id="1b857-117">This command removes all the common area phones for the United States (country code 1) and the area code 425:</span></span>
    
        Get-CsCommonAreaPhone | Where-Object {$_.LineUri  -match "^tel:\+1425"} | Remove-CsCommonAreaPhone

</div>

<span data-ttu-id="1b857-118">Para obtener más información, consulte el tema de ayuda del cmdlet [Remove-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/Remove-CsCommonAreaPhone) .</span><span class="sxs-lookup"><span data-stu-id="1b857-118">For details, see the Help topic for the [Remove-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/Remove-CsCommonAreaPhone) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="1b857-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="1b857-119">See Also</span></span>


[<span data-ttu-id="1b857-120">Get-CsCommonAreaPhone</span><span class="sxs-lookup"><span data-stu-id="1b857-120">Get-CsCommonAreaPhone</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsCommonAreaPhone)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

