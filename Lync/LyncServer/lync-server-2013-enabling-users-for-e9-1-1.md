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
ms.openlocfilehash: 5550ec608b34b66a3e47ceb4535dd23ca7c9a7f1
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146353"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="enabling-users-for-e9-1-1-in-lync-server-2013"></a><span data-ttu-id="2788c-102">Habilitación de usuarios para E9-1-1 en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2788c-102">Enabling users for E9-1-1 in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2788c-103">_**Última modificación del tema:** 2012-06-06_</span><span class="sxs-lookup"><span data-stu-id="2788c-103">_**Topic Last Modified:** 2012-06-06_</span></span>

<span data-ttu-id="2788c-104">Durante el registro de clientes, Lync Server usa una directiva de ubicación para configurar las propiedades de E9-1-1 para los usuarios habilitados para Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="2788c-104">During client registration, Lync Server uses a location policy to configure the E9-1-1 properties for Enterprise Voice-enabled users.</span></span> <span data-ttu-id="2788c-105">Esta directiva contiene la configuración que define cómo se implementa E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="2788c-105">This policy contains the settings that define how E9-1-1 is implemented.</span></span> <span data-ttu-id="2788c-106">Por ejemplo, la Directiva de ubicación contiene información como la cadena de marcado de emergencia y si un usuario debe o no especificar manualmente una ubicación si el servicio de información de ubicación no proporciona uno automáticamente.</span><span class="sxs-lookup"><span data-stu-id="2788c-106">For example, the location policy contains information such as the emergency dial string, and whether or not a user is required to manually enter a location if the Location Information service does not automatically provide one.</span></span> <span data-ttu-id="2788c-107">Para obtener una definición completa de una directiva de ubicación, consulte [Defining The location Policy for Lync Server 2013](lync-server-2013-defining-the-location-policy.md).</span><span class="sxs-lookup"><span data-stu-id="2788c-107">For a complete definition of a location policy, see [Defining the location policy for Lync Server 2013](lync-server-2013-defining-the-location-policy.md).</span></span>

<span data-ttu-id="2788c-108">Lync Server puede asignar una directiva de ubicación a los clientes en función de la subred o a los usuarios en función de una directiva global, por sitio o por usuario.</span><span class="sxs-lookup"><span data-stu-id="2788c-108">Lync Server can assign a location policy to clients based on subnet, or to users based on a global, per-site, or per-user policy.</span></span> <span data-ttu-id="2788c-109">Para ayudarle a decidir cómo habilitará los usuarios, debe responder en primer lugar las siguientes preguntas.</span><span class="sxs-lookup"><span data-stu-id="2788c-109">To help decide how you will enable users, you should first answer the following questions.</span></span>

  - <span data-ttu-id="2788c-110">**¿Piensa habilitar todos los usuarios o limitar la compatibilidad a zonas geográficas específicas de la empresa?**</span><span class="sxs-lookup"><span data-stu-id="2788c-110">**Do you plan to enable all users, or limit support to specific geographic areas of the enterprise?**</span></span>  
    <span data-ttu-id="2788c-111">Puede asignar una ubicación a todos los usuarios de la empresa mediante una directiva de ubicación global.</span><span class="sxs-lookup"><span data-stu-id="2788c-111">You can assign a location to all users in your enterprise by using a global location policy.</span></span> <span data-ttu-id="2788c-112">Sin embargo, al asignar una directiva de ubicación a un sitio de red de Lync Server y, a continuación, agregar subredes al sitio, puede limitar la compatibilidad con E9-1-1 a ubicaciones seleccionadas dentro de la empresa y especificar el comportamiento de enrutamiento E9-1-1 en cada sitio.</span><span class="sxs-lookup"><span data-stu-id="2788c-112">However, by assigning a location policy to a Lync Server network site and then adding subnets to the site, you can limit E9-1-1 support to selected locations within the enterprise and specify E9-1-1 routing behavior on a per-site basis.</span></span>

<!-- end list -->

  - <span data-ttu-id="2788c-113">**¿Piensa habilitar usuarios individuales a través de una directiva de usuario?**</span><span class="sxs-lookup"><span data-stu-id="2788c-113">**Do you plan to enable individual users through a user policy?**</span></span>  
    <span data-ttu-id="2788c-114">Puede asignar directivas de ubicación directamente a usuarios específicos u objetos de contactos telefónicos de un área común si desea personalizar la compatibilidad con E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="2788c-114">You can assign location policies directly to specific users or common area phone contact objects if you want to customize their E9-1-1 support.</span></span>

<!-- end list -->

  - <span data-ttu-id="2788c-115">**Cuando los clientes se desplazan fuera de la red o se encuentran en una subred no definida en la red, ¿deben los clientes seguir habilitados en E9-1-1?**</span><span class="sxs-lookup"><span data-stu-id="2788c-115">**When clients roam outside the network or connect from an undefined subnet, should the clients still be enabled for E9-1-1?**</span></span>  
    <span data-ttu-id="2788c-116">Si los usuarios tienen asignada una directiva de ubicación global, de sitio o por usuario, se les puede requerir especificar manualmente una ubicación en el cliente si el cliente no se encuentra en una subred definida o si el servicio de información de ubicación no ha encontrado ninguna ubicación.</span><span class="sxs-lookup"><span data-stu-id="2788c-116">If users are assigned a global, site, or per-user location policy, they can be required to manually enter a location into the client if the client is not located within a defined subnet or no location has been found by the Location Information service.</span></span> <span data-ttu-id="2788c-117">Para obtener más información, consulte [definir la experiencia de usuario para adquirir manualmente una ubicación en Lync Server 2013](lync-server-2013-defining-the-user-experience-for-manually-acquiring-a-location.md).</span><span class="sxs-lookup"><span data-stu-id="2788c-117">For details, see [Defining the user experience for manually acquiring a location in Lync Server 2013](lync-server-2013-defining-the-user-experience-for-manually-acquiring-a-location.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

