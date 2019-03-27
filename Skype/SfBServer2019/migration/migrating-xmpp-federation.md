---
title: Migrar la federación XMPP
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'Las versiones anteriores proporcionan una extensible de mensajería y presencia (XMPP) de protocolo puerta de enlace que se pueden implementar como una función de servidor distinta para permitir la federación con las implementaciones de XMPP. La funcionalidad XMPP ya no está disponible & en desuso en Skype para Business Server 2019. Si desea continuar con la funcionalidad XMPP, que puede optado en el entorno de coexitence con la versión heredada (Skype para Business Server 2015 / Lync Server 2013). Funcionalidad XMPP está instalada en dos partes: como un XMPP proxy que se ejecuta en el heredado servidor perimetral y la puerta de enlace XMPP que se ejecuta en el servidor de Front-End heredado.'
ms.openlocfilehash: fa91741c1be8d80443363caba7c840b1d985d8f4
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30879331"
---
# <a name="migrating-xmpp-federation"></a><span data-ttu-id="01030-106">Migrar la federación XMPP</span><span class="sxs-lookup"><span data-stu-id="01030-106">Migrating XMPP federation</span></span>

<span data-ttu-id="01030-107">Las versiones anteriores proporcionan una extensible de mensajería y presencia (XMPP) de protocolo puerta de enlace que se pueden implementar como una función de servidor distinta para permitir la federación con las implementaciones de XMPP.</span><span class="sxs-lookup"><span data-stu-id="01030-107">Previous versions provided an extensible messaging and presence protocol (XMPP) gateway that could be deployed as a separate server role to allow federating with XMPP deployments.</span></span> <span data-ttu-id="01030-108">La funcionalidad XMPP ya no está disponible y está en desuso en Skype para Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="01030-108">The XMPP functionality is no longer available and is deprecated in Skype for Business Server 2019.</span></span> <span data-ttu-id="01030-109">Si desea continuar con la funcionalidad XMPP, puede hacerlo en un entorno de coexistencia con una versión heredada (Skype para Business Server 2015 o Lync Server 2013).</span><span class="sxs-lookup"><span data-stu-id="01030-109">If you want to continue with the XMPP functionality, you can do so in a coexistence environment with a legacy version (Skype for Business Server 2015 or Lync Server 2013).</span></span> <span data-ttu-id="01030-110">Funcionalidad XMPP está instalada en dos partes: como un XMPP proxy que se ejecuta en el heredado servidor perimetral y la puerta de enlace XMPP que se ejecuta en el servidor de Front-End heredado.</span><span class="sxs-lookup"><span data-stu-id="01030-110">XMPP functionality is installed in two parts: as an XMPP proxy that runs on the legacy Edge Server, and the XMPP Gateway that runs on the legacy Front End Server.</span></span> 
  
<span data-ttu-id="01030-111">Desde una perspectiva de migración, los usuarios que deseen recurrir a la característica XMPP deben permanecer en el servidor heredado y no se mueven a un Skype para el grupo de servidores de Business Server 2019 pero seguirán usando la puerta de enlace XMPP heredado.</span><span class="sxs-lookup"><span data-stu-id="01030-111">From a migration perspective, users who want to avail the XMPP feature should remain in the legacy server and should not be moved to a Skype for Business Server 2019 pool but continue to use the legacy XMPP gateway.</span></span> <span data-ttu-id="01030-112">Esto es posible sólo cuando el socio federado XMPP está configurado en Skype para Business Server 2015 o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="01030-112">This is possible only when the XMPP federated partner is configured in Skype for Business Server 2015 or Lync Server 2013.</span></span> <span data-ttu-id="01030-113">No se debe migrar el servidor perimetral heredado a Skype para Business Server 2019 si desea continuar con la funcionalidad de XMPP.</span><span class="sxs-lookup"><span data-stu-id="01030-113">You should not migrate the legacy Edge Server to Skype for Business Server 2019 if you want to continue with XMPP functionality.</span></span> <span data-ttu-id="01030-114">Sin embargo, puede tener la coexistencia del servidor perimetral heredado (con Proxy XMPP) y la Skype para servidor perimetral de negocio 2019.</span><span class="sxs-lookup"><span data-stu-id="01030-114">However, you can have coexistence of the legacy Edge Server (with XMPP Proxy) and the Skype for Business 2019 Edge Server.</span></span>
  

    

