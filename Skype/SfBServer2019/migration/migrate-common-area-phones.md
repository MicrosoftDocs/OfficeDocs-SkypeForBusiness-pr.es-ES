---
title: Migrar teléfonos de área común
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Teléfonos de área común son IP teléfonos que más a menudo residen en un área de trabajo compartida o área común, como una sala de espera, cocinas o fábrica de planta. Teléfonos de área común no es necesario estar conectado a un equipo para proporcionar que Skype para Business Server unificada funcionalidad de comunicaciones unificadas. Después de la migración de una implementación a Skype para Business Server 2019, también debe migrar los objetos de contacto asociados con el teléfono de área común heredado. Mediante Skype para Shell de administración de servidor empresarial se primero recuperar todos los objetos de contacto asociados con los teléfonos de área común heredado y, a continuación, mover los objetos a la Skype para el grupo de servidores de Business Server 2019.
ms.openlocfilehash: d17e15224a9124eaf3e9fd6696e6ecd9265044eb
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32231668"
---
# <a name="migrate-common-area-phones"></a><span data-ttu-id="0190f-106">Migrar teléfonos de área común</span><span class="sxs-lookup"><span data-stu-id="0190f-106">Migrate Common Area Phones</span></span>

<span data-ttu-id="0190f-107">Teléfonos de área común son IP teléfonos que más a menudo residen en un área de trabajo compartida o área común, como una sala de espera, cocinas o fábrica de planta.</span><span class="sxs-lookup"><span data-stu-id="0190f-107">Common Area Phones are IP phones that most often reside in a shared workspace or common area, like a lobby, kitchen, or factory floor.</span></span> <span data-ttu-id="0190f-108">Teléfonos de área común no es necesario estar conectado a un equipo para proporcionar que Skype para Business Server unificada funcionalidad de comunicaciones unificadas.</span><span class="sxs-lookup"><span data-stu-id="0190f-108">Common Area Phones do not need to be connected to a computer to provide Skype for Business Server unified communications (UC) functionality.</span></span> <span data-ttu-id="0190f-109">Después de la migración de una implementación a Skype para Business Server 2019, también debe migrar los objetos de contacto asociados con el teléfono de área común heredado.</span><span class="sxs-lookup"><span data-stu-id="0190f-109">After migrating a deployment to Skype for Business Server 2019, you must also migrate the contact objects associated with the legacy Common Area Phone.</span></span> <span data-ttu-id="0190f-110">Usa Skype para Shell de administración de servidor empresarial, se primero recuperar todos los objetos de contacto asociados con los teléfonos de área común heredado y, a continuación, mover los objetos a la Skype para el grupo de servidores de Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="0190f-110">Using Skype for Business Server Management Shell, you will first retrieve all contact objects associated with the legacy Common Area Phones, and then move those objects to the Skype for Business Server 2019 pool.</span></span>
  
### <a name="migrate-common-area-phones"></a><span data-ttu-id="0190f-111">Migrar teléfonos de área común</span><span class="sxs-lookup"><span data-stu-id="0190f-111">Migrate Common Area Phones</span></span>

1. <span data-ttu-id="0190f-112">De Skype para servidor Front-End de Business Server 2019, abra Skype para Shell de administración de servidor empresarial.</span><span class="sxs-lookup"><span data-stu-id="0190f-112">From the Skype for Business Server 2019 Front End server, open Skype for Business Server Management Shell.</span></span>
    
2. <span data-ttu-id="0190f-113">Desde la línea de comandos, escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="0190f-113">From the command line, type the following:</span></span>
    
   ```
   Get-CsCommonAreaPhone -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsCommonAreaPhone -Target pool02.contoso.net
   ```

3. <span data-ttu-id="0190f-114">Para comprobar que todos los objetos de contacto se han movido a la Skype para el grupo de servidores de Business Server 2019, desde el Skype para Shell de administración de servidor empresarial escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="0190f-114">To verify that all contact objects have been moved to the Skype for Business Server 2019 pool, from the Skype for Business Server Management Shell type the following:</span></span>
    
   ```
   Get-CsCommonAreaPhone -Filter {RegistrarPool -eq "pool02.contoso.net"}
   ```

    <span data-ttu-id="0190f-115">Compruebe que todos los objetos de contacto están ahora asociadas con el Skype para el grupo de servidores de Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="0190f-115">Verify that all contact objects are now associated with the Skype for Business Server 2019 pool.</span></span>
    

