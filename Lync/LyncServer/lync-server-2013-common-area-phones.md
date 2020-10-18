---
title: 'Lync Server 2013: teléfonos de área común'
description: 'Lync Server 2013: teléfonos de área común.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Common area phones
ms:assetid: d63bb3de-154e-4347-9251-9fa94e7d593a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994076(v=OCS.15)
ms:contentKeyID: 51803987
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: af8a68f875bba1d43a91e5a252259841d7a6bbda
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48577036"
---
# <a name="common-area-phones-in-lync-server-2013"></a><span data-ttu-id="440a9-103">Teléfonos de área común en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="440a9-103">Common area phones in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="440a9-104">_**Última modificación del tema:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="440a9-104">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="440a9-105">Los teléfonos de área común son teléfonos IP que no están asociados a un usuario individual.</span><span class="sxs-lookup"><span data-stu-id="440a9-105">Common area phones are IP phones that are not associated with an individual user.</span></span> <span data-ttu-id="440a9-106">En lugar de estar ubicado en la oficina de alguien, los teléfonos de área común suelen encontrarse en la creación de salas, cafeterías, salas de reuniones de los empleados, salas de reuniones y otras ubicaciones en las que es probable que un gran número de personas recopilen.</span><span class="sxs-lookup"><span data-stu-id="440a9-106">Instead of being located in someone’s office, common area phones are typically located in building lobbies, cafeterias, employee lounges, meeting rooms, and other locations where a large number of people are likely to gather.</span></span> <span data-ttu-id="440a9-107">A diferencia de otros teléfonos en Lync Server, que se suelen mantener mediante directivas de voz y planes de marcado asignados a usuarios individuales, los teléfonos de área común no tienen asignados usuarios individuales.</span><span class="sxs-lookup"><span data-stu-id="440a9-107">Unlike other phones in Lync Server, which are typically maintained by using voice policies and dial plans that are assigned to individual users, common area phones do not have individual users assigned to them.</span></span> <span data-ttu-id="440a9-108">Esto significa que deben administrarse de forma diferente a la de los otros teléfonos.</span><span class="sxs-lookup"><span data-stu-id="440a9-108">This means that they must be managed differently than your other phones.</span></span>

<span data-ttu-id="440a9-109">Para administrar teléfonos de área común, puede crear objetos de contacto de servicios de dominio de Active Directory para todos los teléfonos de área común que, al igual que las cuentas de usuario, se les puede asignar directivas y planes de voz.</span><span class="sxs-lookup"><span data-stu-id="440a9-109">To manage common area phones, you create Active Directory Domain Services contact objects for all your common area phones that, like user accounts, can be assigned policies and voice plans.</span></span> <span data-ttu-id="440a9-110">Este enfoque permite mantener el control sobre los teléfonos de área común, aunque estos teléfonos no estén asociados con un usuario individual.</span><span class="sxs-lookup"><span data-stu-id="440a9-110">This approach enables you to maintain control over common area phones, even though those phones are not associated with an individual user.</span></span>

<span data-ttu-id="440a9-111">Use los temas de esta sección para obtener información sobre cómo crear objetos de contacto para teléfonos de área común, modificarlos y eliminarlos, y cómo configurar y ver la información de configuración de los teléfonos de área común en su implementación.</span><span class="sxs-lookup"><span data-stu-id="440a9-111">Use the topics in this section to learn how to create contact objects for common area phones, modify and delete them, and configure and view configuration information about the common area phones in your deployment.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="440a9-112">Tiene tres opciones para teléfonos de área común: el teléfono de área común Aastra 6721ip, el teléfono IP HP 4110 y el teléfono de área común Polycom CX500 IP.</span><span class="sxs-lookup"><span data-stu-id="440a9-112">You have three options for common area phones: the Aastra 6721ip common area phone, the HP 4110 IP Phone, and the Polycom CX500 IP common area phone.</span></span> <span data-ttu-id="440a9-113">El teléfono de conferencia IP Polycom CX3000 es otro número de teléfono común de área común.</span><span class="sxs-lookup"><span data-stu-id="440a9-113">The Polycom CX3000 IP conferencing phone is another variant common area phone.</span></span> <span data-ttu-id="440a9-114">Sin embargo, está pensada para su uso en salas de conferencias.</span><span class="sxs-lookup"><span data-stu-id="440a9-114">However, it is intended for use in conference rooms.</span></span> <span data-ttu-id="440a9-115">Para obtener más información sobre los teléfonos de área común, consulte la sección teléfonos de área común de <A href="https://technet.microsoft.com/library/gg398958(v=ocs.14).aspx">elegir nuevos dispositivos</A>.</span><span class="sxs-lookup"><span data-stu-id="440a9-115">For details about common area phones, see the Common Area Phones section of <A href="https://technet.microsoft.com/library/gg398958(v=ocs.14).aspx">Choosing New Devices</A>.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="440a9-116">En esta sección</span><span class="sxs-lookup"><span data-stu-id="440a9-116">In This Section</span></span>

  - [<span data-ttu-id="440a9-117">Ver información de teléfono de área común en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="440a9-117">View common area phone information in Lync Server 2013</span></span>](lync-server-2013-view-common-area-phone-information.md)

  - [<span data-ttu-id="440a9-118">Crear o modificar un objeto de contacto telefónico de área común en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="440a9-118">Create or modify a common area phone Contact object in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-common-area-phone-contact-object.md)

  - [<span data-ttu-id="440a9-119">Habilitar o deshabilitar la entrada manuscrita activa en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="440a9-119">Enable or disable hot desking in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-hot-desking.md)

  - [<span data-ttu-id="440a9-120">Eliminar un objeto de contacto de teléfono de área común en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="440a9-120">Delete a common area phone Contact object in Lync Server 2013</span></span>](lync-server-2013-delete-a-common-area-phone-contact-object.md)

  - [<span data-ttu-id="440a9-121">Asignar directivas en Lync Server 2013 a un teléfono de área común</span><span class="sxs-lookup"><span data-stu-id="440a9-121">Assign policies in Lync Server 2013 to a common area phone</span></span>](lync-server-2013-assign-policies-to-a-common-area-phone.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

