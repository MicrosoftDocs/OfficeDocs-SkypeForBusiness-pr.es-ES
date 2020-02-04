---
title: 'Lync Server 2013: teléfonos de área común'
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
ms.openlocfilehash: 71fa61773a4801d2050d67d4e86458eb5d37759c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742790"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="common-area-phones-in-lync-server-2013"></a><span data-ttu-id="a3d26-102">Teléfonos de área común en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a3d26-102">Common area phones in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a3d26-103">_**Última modificación del tema:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="a3d26-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="a3d26-104">Los teléfonos de área común son teléfonos IP que no están asociados a un usuario individual.</span><span class="sxs-lookup"><span data-stu-id="a3d26-104">Common area phones are IP phones that are not associated with an individual user.</span></span> <span data-ttu-id="a3d26-105">En lugar de estar ubicado en la oficina de alguien, los teléfonos de área común suelen encontrarse en la creación de salas, cafeterías, salas de reuniones de la reunión y otras ubicaciones en las que es probable que una gran cantidad de personas recopilen.</span><span class="sxs-lookup"><span data-stu-id="a3d26-105">Instead of being located in someone’s office, common area phones are typically located in building lobbies, cafeterias, employee lounges, meeting rooms, and other locations where a large number of people are likely to gather.</span></span> <span data-ttu-id="a3d26-106">A diferencia de otros teléfonos de Lync Server, que se suelen mantener con las directivas de voz y los planes de marcado que se asignan a los usuarios individuales, los teléfonos de área común no tienen usuarios individuales asignados.</span><span class="sxs-lookup"><span data-stu-id="a3d26-106">Unlike other phones in Lync Server, which are typically maintained by using voice policies and dial plans that are assigned to individual users, common area phones do not have individual users assigned to them.</span></span> <span data-ttu-id="a3d26-107">Esto significa que deben administrarse de forma diferente a los demás teléfonos.</span><span class="sxs-lookup"><span data-stu-id="a3d26-107">This means that they must be managed differently than your other phones.</span></span>

<span data-ttu-id="a3d26-108">Para administrar teléfonos de área común, puede crear objetos de contacto de los servicios de dominio de Active Directory para todos los teléfonos comunes de área que, al igual que las cuentas de usuario, pueden asignarse a directivas y planes de voz.</span><span class="sxs-lookup"><span data-stu-id="a3d26-108">To manage common area phones, you create Active Directory Domain Services contact objects for all your common area phones that, like user accounts, can be assigned policies and voice plans.</span></span> <span data-ttu-id="a3d26-109">Este enfoque te permite mantener el control sobre teléfonos comunes de área, aunque dichos teléfonos no estén asociados con un usuario individual.</span><span class="sxs-lookup"><span data-stu-id="a3d26-109">This approach enables you to maintain control over common area phones, even though those phones are not associated with an individual user.</span></span>

<span data-ttu-id="a3d26-110">Use los temas de esta sección para obtener información sobre cómo crear objetos de contacto para teléfonos de área común, modificarlos y eliminarlos, y configurar y ver la información de configuración de los teléfonos de área común de su implementación.</span><span class="sxs-lookup"><span data-stu-id="a3d26-110">Use the topics in this section to learn how to create contact objects for common area phones, modify and delete them, and configure and view configuration information about the common area phones in your deployment.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a3d26-111">Tiene tres opciones para teléfonos de área común: el teléfono de área común Aastra 6721ip, el teléfono IP HP 4110 y el teléfono de área común IP Polycom CX500.</span><span class="sxs-lookup"><span data-stu-id="a3d26-111">You have three options for common area phones: the Aastra 6721ip common area phone, the HP 4110 IP Phone, and the Polycom CX500 IP common area phone.</span></span> <span data-ttu-id="a3d26-112">El teléfono de conferencia IP Polycom CX3000 es otra variante de teléfono de área común.</span><span class="sxs-lookup"><span data-stu-id="a3d26-112">The Polycom CX3000 IP conferencing phone is another variant common area phone.</span></span> <span data-ttu-id="a3d26-113">Sin embargo, está pensada para su uso en salas de conferencia.</span><span class="sxs-lookup"><span data-stu-id="a3d26-113">However, it is intended for use in conference rooms.</span></span> <span data-ttu-id="a3d26-114">Para obtener más información sobre teléfonos de área común, consulte la sección teléfonos de área común de <A href="http://technet.microsoft.com/en-us/library/gg398958(v=ocs.14).aspx">elección de nuevos dispositivos</A>.</span><span class="sxs-lookup"><span data-stu-id="a3d26-114">For details about common area phones, see the Common Area Phones section of <A href="http://technet.microsoft.com/en-us/library/gg398958(v=ocs.14).aspx">Choosing New Devices</A>.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="a3d26-115">En esta sección</span><span class="sxs-lookup"><span data-stu-id="a3d26-115">In This Section</span></span>

  - [<span data-ttu-id="a3d26-116">Ver la información de los teléfonos comunes en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a3d26-116">View common area phone information in Lync Server 2013</span></span>](lync-server-2013-view-common-area-phone-information.md)

  - [<span data-ttu-id="a3d26-117">Crear o modificar un objeto de contacto telefónico de área común en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a3d26-117">Create or modify a common area phone Contact object in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-common-area-phone-contact-object.md)

  - [<span data-ttu-id="a3d26-118">Habilitar o deshabilitar la entrada manuscrita en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a3d26-118">Enable or disable hot desking in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-hot-desking.md)

  - [<span data-ttu-id="a3d26-119">Eliminar un objeto de contacto telefónico de área común en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a3d26-119">Delete a common area phone Contact object in Lync Server 2013</span></span>](lync-server-2013-delete-a-common-area-phone-contact-object.md)

  - [<span data-ttu-id="a3d26-120">Asignar directivas en Lync Server 2013 a un teléfono de área común</span><span class="sxs-lookup"><span data-stu-id="a3d26-120">Assign policies in Lync Server 2013 to a common area phone</span></span>](lync-server-2013-assign-policies-to-a-common-area-phone.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

