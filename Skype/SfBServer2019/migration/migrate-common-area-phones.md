---
title: Migrar teléfonos de área común
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
description: Los teléfonos de área común son teléfonos IP que a menudo se encuentran en un espacio de trabajo compartido o un área común, como una sala de espera, cocina o una fábrica. No es necesario que los teléfonos de área común estén conectados a un equipo para proporcionar la funcionalidad de comunicaciones unificadas (UC) de Skype empresarial Server. Después de migrar una implementación a Skype empresarial Server 2019, también debe migrar los objetos de contacto asociados con el teléfono de área común heredado. Mediante el shell de administración de Skype empresarial Server recuperará primero todos los objetos de contacto asociados con los teléfonos de área común heredados y, a continuación, moverá dichos objetos al grupo de Skype empresarial Server 2019.
ms.openlocfilehash: b9cf5a32614ac41ac3c82773af4f37907c16e6f2
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752712"
---
# <a name="migrate-common-area-phones"></a><span data-ttu-id="5c10b-106">Migrar teléfonos de área común</span><span class="sxs-lookup"><span data-stu-id="5c10b-106">Migrate Common Area Phones</span></span>

<span data-ttu-id="5c10b-107">Los teléfonos de área común son teléfonos IP que a menudo se encuentran en un espacio de trabajo compartido o un área común, como una sala de espera, cocina o una fábrica.</span><span class="sxs-lookup"><span data-stu-id="5c10b-107">Common Area Phones are IP phones that most often reside in a shared workspace or common area, like a lobby, kitchen, or factory floor.</span></span> <span data-ttu-id="5c10b-108">No es necesario que los teléfonos de área común estén conectados a un equipo para proporcionar la funcionalidad de comunicaciones unificadas (UC) de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="5c10b-108">Common Area Phones do not need to be connected to a computer to provide Skype for Business Server unified communications (UC) functionality.</span></span> <span data-ttu-id="5c10b-109">Después de migrar una implementación a Skype empresarial Server 2019, también debe migrar los objetos de contacto asociados con el teléfono de área común heredado.</span><span class="sxs-lookup"><span data-stu-id="5c10b-109">After migrating a deployment to Skype for Business Server 2019, you must also migrate the contact objects associated with the legacy Common Area Phone.</span></span> <span data-ttu-id="5c10b-110">Mediante el shell de administración de Skype empresarial Server, primero se recuperarán todos los objetos de contacto asociados con los teléfonos de área común heredados y, a continuación, se mueven dichos objetos al grupo de servidores de Skype empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="5c10b-110">Using Skype for Business Server Management Shell, you will first retrieve all contact objects associated with the legacy Common Area Phones, and then move those objects to the Skype for Business Server 2019 pool.</span></span>
  
### <a name="migrate-common-area-phones"></a><span data-ttu-id="5c10b-111">Migrar teléfonos de área común</span><span class="sxs-lookup"><span data-stu-id="5c10b-111">Migrate Common Area Phones</span></span>

1. <span data-ttu-id="5c10b-112">En el servidor front-end de Skype empresarial Server 2019, abra Shell de administración de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="5c10b-112">From the Skype for Business Server 2019 Front End server, open Skype for Business Server Management Shell.</span></span>
    
2. <span data-ttu-id="5c10b-113">En la línea de comandos, escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="5c10b-113">From the command line, type the following:</span></span>
    
   ```PowerShell
   Get-CsCommonAreaPhone -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsCommonAreaPhone -Target pool02.contoso.net
   ```

3. <span data-ttu-id="5c10b-114">Para comprobar que todos los objetos de contacto se han movido al grupo de servidores de Skype empresarial Server 2019, desde el shell de administración de Skype empresarial Server, escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="5c10b-114">To verify that all contact objects have been moved to the Skype for Business Server 2019 pool, from the Skype for Business Server Management Shell type the following:</span></span>
    
   ```PowerShell
   Get-CsCommonAreaPhone -Filter {RegistrarPool -eq "pool02.contoso.net"}
   ```

    <span data-ttu-id="5c10b-115">Compruebe que todos los objetos de contacto están ahora asociados con el grupo de Skype empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="5c10b-115">Verify that all contact objects are now associated with the Skype for Business Server 2019 pool.</span></span>
    

