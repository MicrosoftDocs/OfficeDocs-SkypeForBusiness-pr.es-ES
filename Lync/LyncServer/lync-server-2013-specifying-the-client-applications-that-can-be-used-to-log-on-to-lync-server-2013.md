---
title: 'Lync Server 2013: especificación de las aplicaciones cliente que se pueden usar para iniciar sesión en Lync Server 2013'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Specifying the client applications that can be used to log on to Lync Server 2013
ms:assetid: d256a581-9a48-4d1a-82cc-2e1f520d7d2e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182591(v=OCS.15)
ms:contentKeyID: 48185450
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 788a0638dee6b9d52a5d954eafb7b4e33bdfd294
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41731880"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="specifying-the-client-applications-that-can-be-used-to-log-on-to-lync-server-2013"></a><span data-ttu-id="3c67f-102">Especificación de las aplicaciones cliente que se pueden usar para iniciar sesión en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3c67f-102">Specifying the client applications that can be used to log on to Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3c67f-103">_**Última modificación del tema:** 2012-12-11_</span><span class="sxs-lookup"><span data-stu-id="3c67f-103">_**Topic Last Modified:** 2012-12-11_</span></span>

<span data-ttu-id="3c67f-104">Lync Server 2013 le permite especificar la versión de los clientes que son compatibles con su entorno.</span><span class="sxs-lookup"><span data-stu-id="3c67f-104">Lync Server 2013 enables you to specify the version of clients that are supported in your environment.</span></span> <span data-ttu-id="3c67f-105">El uso de directivas de versión de cliente puede ayudar a reducir los costos asociados a la compatibilidad de varias versiones de cliente.</span><span class="sxs-lookup"><span data-stu-id="3c67f-105">Using client version policies can help reduce the costs associated with supporting multiple client versions.</span></span> <span data-ttu-id="3c67f-106">También puede mejorar la experiencia general del usuario, ya que cuando interactúan versiones anteriores y posteriores de los clientes, las características disponibles pueden verse limitadas por la versión anterior del cliente.</span><span class="sxs-lookup"><span data-stu-id="3c67f-106">It can also improve the overall user experience, because when earlier and later versions of clients interact, the available features can be limited by the earlier version of the client.</span></span>

<span data-ttu-id="3c67f-107">Hay tres componentes de control de versiones de cliente:</span><span class="sxs-lookup"><span data-stu-id="3c67f-107">There are three components of client version control:</span></span>

  - <span data-ttu-id="3c67f-108">La configuración de la versión del cliente se usa para activar o desactivar el control de versiones del cliente, ya sea de forma global o para sitios concretos.</span><span class="sxs-lookup"><span data-stu-id="3c67f-108">Client version configuration settings are used to turn client version control on or off, either globally or for particular sites.</span></span>

  - <span data-ttu-id="3c67f-109">Las directivas de versión de cliente se usan para asignar un conjunto de reglas globalmente o a un sitio, grupo de usuarios o grupo de usuarios en particular.</span><span class="sxs-lookup"><span data-stu-id="3c67f-109">Client version policies are used to assign a set of rules globally, or to a particular site, pool, or group of users.</span></span>

  - <span data-ttu-id="3c67f-110">Las reglas de directiva de versión de cliente constituyen una directiva de versión de cliente y se usan para definir las acciones que se deben realizar cuando los usuarios intentan iniciar sesión con clientes y versiones de cliente específicos.</span><span class="sxs-lookup"><span data-stu-id="3c67f-110">Client version policy rules make up a client version policy, and are used to define the actions that should be taken when users attempt to log on with specific clients and client versions.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="3c67f-111">Debido a que los usuarios anónimos no están asociados a un usuario, sitio o servicio, este tipo de usuarios solo se ven afectados por directivas de nivel global.</span><span class="sxs-lookup"><span data-stu-id="3c67f-111">Because anonymous users are not associated with a user, site, or service, anonymous users are affected by global-level policies only.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="3c67f-112">En esta sección</span><span class="sxs-lookup"><span data-stu-id="3c67f-112">In This Section</span></span>

  - [<span data-ttu-id="3c67f-113">Configuración de la versión de cliente en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3c67f-113">Client version configuration settings in Lync Server 2013</span></span>](lync-server-2013-client-version-configuration-settings.md)

  - [<span data-ttu-id="3c67f-114">Directivas de versión de cliente en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3c67f-114">Client version policies in Lync Server 2013</span></span>](lync-server-2013-client-version-policies.md)

  - [<span data-ttu-id="3c67f-115">Reglas de versión de cliente en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3c67f-115">Client version rules in Lync Server 2013</span></span>](lync-server-2013-client-version-rules.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="3c67f-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="3c67f-116">See Also</span></span>


[<span data-ttu-id="3c67f-117">Administrar dispositivos, teléfonos y aplicaciones cliente en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3c67f-117">Managing devices, phones, and client applications in Lync Server 2013</span></span>](lync-server-2013-managing-devices-phones-and-client-applications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

