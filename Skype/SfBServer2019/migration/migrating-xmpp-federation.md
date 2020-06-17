---
title: Migrar la federación XMPP
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 'Las versiones anteriores proporcionaban una puerta de enlace de protocolo extensible de mensajería y presencia (XMPP) que se podía implementar como una función de servidor independiente para permitir la Federación con las implementaciones de XMPP. La funcionalidad de XMPP ya no está disponible & en desuso en Skype empresarial Server 2019. Si desea continuar con la funcionalidad de XMPP, puede estar disponible en el entorno de coexitence con la versión heredada (Skype empresarial Server 2015/Lync Server 2013). La funcionalidad XMPP se instala en dos partes: como un proxy XMPP que se ejecuta en el servidor perimetral heredado y la puerta de enlace XMPP que se ejecuta en el servidor front-end heredado.'
ms.openlocfilehash: 71b6c213450f51ea4b3fe1f351e22dbb992ce8ca
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752652"
---
# <a name="migrating-xmpp-federation"></a><span data-ttu-id="16b0e-106">Migrar la federación XMPP</span><span class="sxs-lookup"><span data-stu-id="16b0e-106">Migrating XMPP federation</span></span>

<span data-ttu-id="16b0e-107">Las versiones anteriores proporcionaban una puerta de enlace de protocolo extensible de mensajería y presencia (XMPP) que se podía implementar como una función de servidor independiente para permitir la Federación con las implementaciones de XMPP.</span><span class="sxs-lookup"><span data-stu-id="16b0e-107">Previous versions provided an extensible messaging and presence protocol (XMPP) gateway that could be deployed as a separate server role to allow federating with XMPP deployments.</span></span> <span data-ttu-id="16b0e-108">La funcionalidad de XMPP ya no está disponible y está en desuso en Skype empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="16b0e-108">The XMPP functionality is no longer available and is deprecated in Skype for Business Server 2019.</span></span> <span data-ttu-id="16b0e-109">Si desea continuar con la funcionalidad XMPP, puede hacerlo en un entorno de coexistencia con una versión heredada (Skype empresarial Server 2015 o Lync Server 2013).</span><span class="sxs-lookup"><span data-stu-id="16b0e-109">If you want to continue with the XMPP functionality, you can do so in a coexistence environment with a legacy version (Skype for Business Server 2015 or Lync Server 2013).</span></span> <span data-ttu-id="16b0e-110">La funcionalidad XMPP se instala en dos partes: como un proxy XMPP que se ejecuta en el servidor perimetral heredado y la puerta de enlace XMPP que se ejecuta en el servidor front-end heredado.</span><span class="sxs-lookup"><span data-stu-id="16b0e-110">XMPP functionality is installed in two parts: as an XMPP proxy that runs on the legacy Edge Server, and the XMPP Gateway that runs on the legacy Front End Server.</span></span> 
  
<span data-ttu-id="16b0e-111">Desde el punto de vista de la migración, los usuarios que deseen Dispa la característica XMPP deben permanecer en el servidor heredado y no se deben mover a un grupo de servidores de 2019 de Skype empresarial, pero seguir usando la puerta de enlace XMPP heredada.</span><span class="sxs-lookup"><span data-stu-id="16b0e-111">From a migration perspective, users who want to avail the XMPP feature should remain in the legacy server and should not be moved to a Skype for Business Server 2019 pool but continue to use the legacy XMPP gateway.</span></span> <span data-ttu-id="16b0e-112">Esto solo es posible si el socio federado de XMPP está configurado en Skype empresarial Server 2015 o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="16b0e-112">This is possible only when the XMPP federated partner is configured in Skype for Business Server 2015 or Lync Server 2013.</span></span> <span data-ttu-id="16b0e-113">No debe migrar el servidor perimetral heredado a Skype empresarial Server 2019 si desea continuar con la funcionalidad XMPP.</span><span class="sxs-lookup"><span data-stu-id="16b0e-113">You should not migrate the legacy Edge Server to Skype for Business Server 2019 if you want to continue with XMPP functionality.</span></span> <span data-ttu-id="16b0e-114">Sin embargo, puede tener coexistencia del servidor perimetral heredado (con proxy XMPP) y el servidor perimetral 2019 de Skype empresarial.</span><span class="sxs-lookup"><span data-stu-id="16b0e-114">However, you can have coexistence of the legacy Edge Server (with XMPP Proxy) and the Skype for Business 2019 Edge Server.</span></span>
  

    

