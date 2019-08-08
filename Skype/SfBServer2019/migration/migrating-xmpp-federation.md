---
title: Migrar la federación XMPP
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'Las versiones anteriores proporcionaban una puerta de enlace de protocolo de presencia y mensajería extensible (XMPP) que se podía implementar como un rol de servidor independiente para permitir la Federación con implementaciones de XMPP. La funcionalidad de XMPP ya no está disponible & en desuso en Skype empresarial Server 2019. Si desea continuar con la funcionalidad de XMPP, puede estar disponible en el entorno de coexitence con versión heredada (Skype empresarial Server 2015/Lync Server 2013). La funcionalidad XMPP se instala en dos partes: como un proxy XMPP que se ejecuta en el servidor perimetral heredado y la puerta de enlace XMPP que se ejecuta en el servidor front-end heredado.'
ms.openlocfilehash: 0c7c3dbb9c7cda4f6825f66326422dced85a9c3c
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/07/2019
ms.locfileid: "36237796"
---
# <a name="migrating-xmpp-federation"></a><span data-ttu-id="57436-106">Migrar la federación XMPP</span><span class="sxs-lookup"><span data-stu-id="57436-106">Migrating XMPP federation</span></span>

<span data-ttu-id="57436-107">Las versiones anteriores proporcionaban una puerta de enlace de protocolo de presencia y mensajería extensible (XMPP) que se podía implementar como un rol de servidor independiente para permitir la Federación con implementaciones de XMPP.</span><span class="sxs-lookup"><span data-stu-id="57436-107">Previous versions provided an extensible messaging and presence protocol (XMPP) gateway that could be deployed as a separate server role to allow federating with XMPP deployments.</span></span> <span data-ttu-id="57436-108">La funcionalidad de XMPP ya no está disponible y quedó obsoleta en Skype empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="57436-108">The XMPP functionality is no longer available and is deprecated in Skype for Business Server 2019.</span></span> <span data-ttu-id="57436-109">Si desea continuar con la funcionalidad de XMPP, puede hacerlo en un entorno de coexistencia con una versión heredada (Skype empresarial Server 2015 o Lync Server 2013).</span><span class="sxs-lookup"><span data-stu-id="57436-109">If you want to continue with the XMPP functionality, you can do so in a coexistence environment with a legacy version (Skype for Business Server 2015 or Lync Server 2013).</span></span> <span data-ttu-id="57436-110">La funcionalidad XMPP se instala en dos partes: como un proxy XMPP que se ejecuta en el servidor perimetral heredado y la puerta de enlace XMPP que se ejecuta en el servidor front-end heredado.</span><span class="sxs-lookup"><span data-stu-id="57436-110">XMPP functionality is installed in two parts: as an XMPP proxy that runs on the legacy Edge Server, and the XMPP Gateway that runs on the legacy Front End Server.</span></span> 
  
<span data-ttu-id="57436-111">Desde el punto de vista de la migración, los usuarios que deseen disponer de la característica XMPP deben permanecer en el servidor heredado y no se deben mover a un grupo de servidores de Skype empresarial 2019, pero seguir usando la puerta de enlace XMPP heredada.</span><span class="sxs-lookup"><span data-stu-id="57436-111">From a migration perspective, users who want to avail the XMPP feature should remain in the legacy server and should not be moved to a Skype for Business Server 2019 pool but continue to use the legacy XMPP gateway.</span></span> <span data-ttu-id="57436-112">Esto solo es posible si el socio de XMPP federado está configurado en Skype empresarial Server 2015 o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="57436-112">This is possible only when the XMPP federated partner is configured in Skype for Business Server 2015 or Lync Server 2013.</span></span> <span data-ttu-id="57436-113">No debe migrar el servidor perimetral heredado a Skype empresarial Server 2019 si desea continuar con la funcionalidad de XMPP.</span><span class="sxs-lookup"><span data-stu-id="57436-113">You should not migrate the legacy Edge Server to Skype for Business Server 2019 if you want to continue with XMPP functionality.</span></span> <span data-ttu-id="57436-114">Sin embargo, puede tener coexistencia del servidor perimetral heredado (con proxy XMPP) y el servidor EDGE 2019 de Skype empresarial.</span><span class="sxs-lookup"><span data-stu-id="57436-114">However, you can have coexistence of the legacy Edge Server (with XMPP Proxy) and the Skype for Business 2019 Edge Server.</span></span>
  

    

