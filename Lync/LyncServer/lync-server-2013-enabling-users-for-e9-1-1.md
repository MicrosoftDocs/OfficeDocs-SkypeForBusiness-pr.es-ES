---
title: 'Lync Server 2013: habilitar usuarios para E9-1-1'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enabling users for E9-1-1
ms:assetid: 3cc64f5b-492e-4c47-9713-3c376f2aad02
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425892(v=OCS.15)
ms:contentKeyID: 48183884
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 86d5032defc7322e96662dcfe6357bd30c598e45
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735610"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enabling-users-for-e9-1-1-in-lync-server-2013"></a><span data-ttu-id="e22e7-102">Habilitar usuarios para E9-1-1 en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e22e7-102">Enabling users for E9-1-1 in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e22e7-103">_**Última modificación del tema:** 2012-06-06_</span><span class="sxs-lookup"><span data-stu-id="e22e7-103">_**Topic Last Modified:** 2012-06-06_</span></span>

<span data-ttu-id="e22e7-104">Durante el registro del cliente, Lync Server usa una directiva de ubicación para configurar las E9-1-1 para los usuarios habilitados para voz empresarial.</span><span class="sxs-lookup"><span data-stu-id="e22e7-104">During client registration, Lync Server uses a location policy to configure the E9-1-1 properties for Enterprise Voice-enabled users.</span></span> <span data-ttu-id="e22e7-105">Esta directiva contiene la configuración que define cómo se implementa E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="e22e7-105">This policy contains the settings that define how E9-1-1 is implemented.</span></span> <span data-ttu-id="e22e7-106">Por ejemplo, la Directiva de ubicación contiene información como, por ejemplo, la cadena de marcado de emergencia y si un usuario debe o no especificar manualmente una ubicación si el servicio de información de ubicación no proporciona una automáticamente.</span><span class="sxs-lookup"><span data-stu-id="e22e7-106">For example, the location policy contains information such as the emergency dial string, and whether or not a user is required to manually enter a location if the Location Information service does not automatically provide one.</span></span> <span data-ttu-id="e22e7-107">Para obtener una definición completa de una directiva de ubicación, consulte [definir la Directiva de ubicación de Lync Server 2013](lync-server-2013-defining-the-location-policy.md).</span><span class="sxs-lookup"><span data-stu-id="e22e7-107">For a complete definition of a location policy, see [Defining the location policy for Lync Server 2013](lync-server-2013-defining-the-location-policy.md).</span></span>

<span data-ttu-id="e22e7-108">Lync Server puede asignar una directiva de ubicación a los clientes en función de la subred o a los usuarios en función de una directiva global, por sitio o por usuario.</span><span class="sxs-lookup"><span data-stu-id="e22e7-108">Lync Server can assign a location policy to clients based on subnet, or to users based on a global, per-site, or per-user policy.</span></span> <span data-ttu-id="e22e7-109">Para ayudarte a decidir cómo habilitarás los usuarios, necesitas responder primero las siguientes preguntas.</span><span class="sxs-lookup"><span data-stu-id="e22e7-109">To help decide how you will enable users, you should first answer the following questions.</span></span>

  - <span data-ttu-id="e22e7-110">**¿Piensa habilitar todos los usuarios o limitar la compatibilidad a zonas geográficas específicas de la empresa?**</span><span class="sxs-lookup"><span data-stu-id="e22e7-110">**Do you plan to enable all users, or limit support to specific geographic areas of the enterprise?**</span></span>  
    <span data-ttu-id="e22e7-111">Puede asignar una ubicación a todos los usuarios de su empresa mediante una directiva de ubicación global.</span><span class="sxs-lookup"><span data-stu-id="e22e7-111">You can assign a location to all users in your enterprise by using a global location policy.</span></span> <span data-ttu-id="e22e7-112">Sin embargo, si asigna una directiva de ubicación a un sitio de red de Lync Server y luego agrega subredes al sitio, puede limitar la compatibilidad de E9-1-1 a ubicaciones seleccionadas dentro de la empresa y especificar el comportamiento de enrutamiento de E9-1-1 en cada sitio.</span><span class="sxs-lookup"><span data-stu-id="e22e7-112">However, by assigning a location policy to a Lync Server network site and then adding subnets to the site, you can limit E9-1-1 support to selected locations within the enterprise and specify E9-1-1 routing behavior on a per-site basis.</span></span>

<!-- end list -->

  - <span data-ttu-id="e22e7-113">**¿Piensa habilitar usuarios individuales a través de una directiva de usuario?**</span><span class="sxs-lookup"><span data-stu-id="e22e7-113">**Do you plan to enable individual users through a user policy?**</span></span>  
    <span data-ttu-id="e22e7-114">Si deseas personalizar la asistencia de E9-1-1, puedes asignar directivas de ubicación directamente a usuarios o a objetos de contactos telefónicos de un área común específicos.</span><span class="sxs-lookup"><span data-stu-id="e22e7-114">You can assign location policies directly to specific users or common area phone contact objects if you want to customize their E9-1-1 support.</span></span>

<!-- end list -->

  - <span data-ttu-id="e22e7-115">**Cuando los clientes se desplazan fuera de la red o se encuentran en una subred no definida en la red, ¿tienen los clientes que seguir habilitados en E9-1-1?**</span><span class="sxs-lookup"><span data-stu-id="e22e7-115">**When clients roam outside the network or connect from an undefined subnet, should the clients still be enabled for E9-1-1?**</span></span>  
    <span data-ttu-id="e22e7-116">Si se asigna a los usuarios una directiva de ubicación global, de sitio o por usuario, se les puede requerir introducir manualmente una ubicación en el cliente si el cliente no se encuentra en una subred definida o si el servicio de información de ubicación no ha encontrado ninguna ubicación.</span><span class="sxs-lookup"><span data-stu-id="e22e7-116">If users are assigned a global, site, or per-user location policy, they can be required to manually enter a location into the client if the client is not located within a defined subnet or no location has been found by the Location Information service.</span></span> <span data-ttu-id="e22e7-117">Para obtener más información, vea [definir la experiencia de usuario para adquirir una ubicación de forma manual en Lync Server 2013](lync-server-2013-defining-the-user-experience-for-manually-acquiring-a-location.md).</span><span class="sxs-lookup"><span data-stu-id="e22e7-117">For details, see [Defining the user experience for manually acquiring a location in Lync Server 2013](lync-server-2013-defining-the-user-experience-for-manually-acquiring-a-location.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

