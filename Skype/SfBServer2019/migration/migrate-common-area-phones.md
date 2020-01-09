---
title: Migrar teléfonos de área común
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Los teléfonos de área común son teléfonos IP que suelen residir en un área de trabajo compartida o en un área común, como un vestíbulo, una cocina o una fábrica. No es necesario que los teléfonos de área común estén conectados a un equipo para proporcionar la funcionalidad de comunicaciones unificadas (UC) de Skype empresarial Server. Después de migrar una implementación a Skype empresarial Server 2019, también debe migrar los objetos de contacto asociados con el teléfono de área común heredado. Usar el shell de administración de Skype empresarial Server primero recuperará todos los objetos de contacto asociados a los teléfonos de área común heredados y, a continuación, moverá esos objetos al grupo de servidores de Skype empresarial 2019.
ms.openlocfilehash: f268c22f1d1132b3b5b8c1c1676e5b3a0182cf3f
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991155"
---
# <a name="migrate-common-area-phones"></a><span data-ttu-id="e34b2-106">Migrar teléfonos de área común</span><span class="sxs-lookup"><span data-stu-id="e34b2-106">Migrate Common Area Phones</span></span>

<span data-ttu-id="e34b2-107">Los teléfonos de área común son teléfonos IP que suelen residir en un área de trabajo compartida o en un área común, como un vestíbulo, una cocina o una fábrica.</span><span class="sxs-lookup"><span data-stu-id="e34b2-107">Common Area Phones are IP phones that most often reside in a shared workspace or common area, like a lobby, kitchen, or factory floor.</span></span> <span data-ttu-id="e34b2-108">No es necesario que los teléfonos de área común estén conectados a un equipo para proporcionar la funcionalidad de comunicaciones unificadas (UC) de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="e34b2-108">Common Area Phones do not need to be connected to a computer to provide Skype for Business Server unified communications (UC) functionality.</span></span> <span data-ttu-id="e34b2-109">Después de migrar una implementación a Skype empresarial Server 2019, también debe migrar los objetos de contacto asociados con el teléfono de área común heredado.</span><span class="sxs-lookup"><span data-stu-id="e34b2-109">After migrating a deployment to Skype for Business Server 2019, you must also migrate the contact objects associated with the legacy Common Area Phone.</span></span> <span data-ttu-id="e34b2-110">Si usa el shell de administración de Skype empresarial Server, primero deberá recuperar todos los objetos de contacto asociados a los teléfonos de área común heredados y, a continuación, mover esos objetos al grupo de servidores de Skype empresarial 2019.</span><span class="sxs-lookup"><span data-stu-id="e34b2-110">Using Skype for Business Server Management Shell, you will first retrieve all contact objects associated with the legacy Common Area Phones, and then move those objects to the Skype for Business Server 2019 pool.</span></span>
  
### <a name="migrate-common-area-phones"></a><span data-ttu-id="e34b2-111">Migrar teléfonos de área común</span><span class="sxs-lookup"><span data-stu-id="e34b2-111">Migrate Common Area Phones</span></span>

1. <span data-ttu-id="e34b2-112">Desde el servidor front-end de Skype empresarial Server 2019, abra el shell de administración de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="e34b2-112">From the Skype for Business Server 2019 Front End server, open Skype for Business Server Management Shell.</span></span>
    
2. <span data-ttu-id="e34b2-113">En la línea de comandos, escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="e34b2-113">From the command line, type the following:</span></span>
    
   ```PowerShell
   Get-CsCommonAreaPhone -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsCommonAreaPhone -Target pool02.contoso.net
   ```

3. <span data-ttu-id="e34b2-114">Para comprobar que todos los objetos de contacto se han movido al grupo de servidores de Skype empresarial 2019, en el shell de administración de Skype empresarial Server, escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="e34b2-114">To verify that all contact objects have been moved to the Skype for Business Server 2019 pool, from the Skype for Business Server Management Shell type the following:</span></span>
    
   ```PowerShell
   Get-CsCommonAreaPhone -Filter {RegistrarPool -eq "pool02.contoso.net"}
   ```

    <span data-ttu-id="e34b2-115">Compruebe que todos los objetos de contacto ahora están asociados con el grupo de servidores de Skype empresarial 2019.</span><span class="sxs-lookup"><span data-stu-id="e34b2-115">Verify that all contact objects are now associated with the Skype for Business Server 2019 pool.</span></span>
    

