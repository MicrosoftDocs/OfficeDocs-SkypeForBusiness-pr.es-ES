---
title: 'Lync Server 2013: eliminar un objeto de contacto de teléfono de área común'
description: 'Lync Server 2013: eliminar un objeto de contacto de teléfono de área común.'
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
ms.openlocfilehash: e918f7a46269f70577f28b2c3e55297959430721
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566606"
---
# <a name="delete-a-common-area-phone-contact-object-in-lync-server-2013"></a><span data-ttu-id="addd3-103">Eliminar un objeto de contacto de teléfono de área común en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="addd3-103">Delete a common area phone Contact object in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="addd3-104">_**Última modificación del tema:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="addd3-104">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="addd3-105">Es posible que desee eliminar el objeto de contacto asociado con un teléfono de área común.</span><span class="sxs-lookup"><span data-stu-id="addd3-105">You might want to delete the contact object associated with a common area phone.</span></span> <span data-ttu-id="addd3-106">Por ejemplo, si quita el teléfono de una sala de empleados, no es necesario que tenga un objeto de contacto asociado con ese teléfono.</span><span class="sxs-lookup"><span data-stu-id="addd3-106">For example, if you remove the phone from an employee lounge, there’s no need to have a contact object associated with that phone.</span></span> <span data-ttu-id="addd3-107">El cmdlet **Remove-CsCommonAreaPhone** proporciona una forma de eliminar cuentas de teléfono de área común.</span><span class="sxs-lookup"><span data-stu-id="addd3-107">The **Remove-CsCommonAreaPhone** cmdlet provides a way for you to delete common area phone accounts.</span></span> <span data-ttu-id="addd3-108">Cuando se ejecuta este cmdlet, el teléfono se elimina de la lista de teléfonos de área común devuelta por **Get-CsCommonAreaPhone**.</span><span class="sxs-lookup"><span data-stu-id="addd3-108">When you run this cmdlet, the phone is deleted from the list of common area phones returned by **Get-CsCommonAreaPhone**.</span></span> <span data-ttu-id="addd3-109">Además, el objeto de contacto asociado con ese teléfono se elimina de servicios de dominio de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="addd3-109">In addition, the contact object associated with that phone is deleted from Active Directory Domain Services.</span></span>

<span data-ttu-id="addd3-110">Use **Remove-CsCommonAreaPhone** para quitar un teléfono de área común o todos los teléfonos de área común que tengan un elemento común, como un nombre para mostrar o un país y un código de área.</span><span class="sxs-lookup"><span data-stu-id="addd3-110">Use **Remove-CsCommonAreaPhone** to remove one common area phone or all common area phones that have a common element, such as a display name or country and area code.</span></span> <span data-ttu-id="addd3-111">Puede ejecutar este cmdlet desde el shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="addd3-111">You can run this cmdlet from either the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="addd3-112">Para obtener información detallada sobre cómo usar Windows PowerShell remoto para conectarse a Lync Server, consulte el artículo del blog de Lync Server Windows PowerShell "Inicio rápido: administración de Microsoft Lync Server 2010 mediante PowerShell remoto" en [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .</span><span class="sxs-lookup"><span data-stu-id="addd3-112">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>


<div>

## <a name="removing-a-specified-common-area-phone"></a><span data-ttu-id="addd3-113">Quitar un teléfono de área común especificado</span><span class="sxs-lookup"><span data-stu-id="addd3-113">Removing a Specified Common Area Phone</span></span>

  - <span data-ttu-id="addd3-114">El siguiente comando quita el teléfono de área común con la dirección SIP sip:mainlobby@litwareinc.com:</span><span class="sxs-lookup"><span data-stu-id="addd3-114">The following command removes the common area phone with the SIP address sip:mainlobby@litwareinc.com:</span></span>
    
        Remove-CsCommonAreaPhone -Identity "sip:mainlobby@litwareinc.com"

</div>

<div>

## <a name="removing-common-area-phones-based-on-their-display-name"></a><span data-ttu-id="addd3-115">Eliminación de teléfonos de área común en función de su nombre para mostrar</span><span class="sxs-lookup"><span data-stu-id="addd3-115">Removing Common Area Phones Based on Their Display Name</span></span>

  - <span data-ttu-id="addd3-116">Este comando quita todos los teléfonos de área común donde el nombre para mostrar incluye el valor de cadena "Building 14":</span><span class="sxs-lookup"><span data-stu-id="addd3-116">This command removes all the common area phones where the display name includes the string value "Building 14":</span></span>
    
        Get-CsCommonAreaPhone | Where-Object {$_.DisplayName -match "Building 14"} | Remove-CsCommonAreaPhone

</div>

<div>

## <a name="removing-common-area-phones-based-on-their-country-and-area-codes"></a><span data-ttu-id="addd3-117">Quitar los teléfonos de área común en función de sus códigos de área y país</span><span class="sxs-lookup"><span data-stu-id="addd3-117">Removing Common Area Phones Based on Their Country and Area Codes</span></span>

  - <span data-ttu-id="addd3-118">Este comando quita todos los teléfonos de área común de los Estados Unidos (código de país 1) y el código de área 425:</span><span class="sxs-lookup"><span data-stu-id="addd3-118">This command removes all the common area phones for the United States (country code 1) and the area code 425:</span></span>
    
        Get-CsCommonAreaPhone | Where-Object {$_.LineUri  -match "^tel:\+1425"} | Remove-CsCommonAreaPhone

</div>

<span data-ttu-id="addd3-119">Para obtener más información, consulte el tema de ayuda del cmdlet [Remove-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/Remove-CsCommonAreaPhone) .</span><span class="sxs-lookup"><span data-stu-id="addd3-119">For details, see the Help topic for the [Remove-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/Remove-CsCommonAreaPhone) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="addd3-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="addd3-120">See Also</span></span>


[<span data-ttu-id="addd3-121">Get-CsCommonAreaPhone</span><span class="sxs-lookup"><span data-stu-id="addd3-121">Get-CsCommonAreaPhone</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsCommonAreaPhone)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

