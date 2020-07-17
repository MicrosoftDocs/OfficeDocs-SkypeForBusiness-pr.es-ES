---
title: Migrar dispositivos analógicos
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
description: Skype empresarial Server proporciona compatibilidad con dispositivos analógicos. En concreto, los dispositivos analógicos compatibles son los teléfonos de audio analógicos y los equipos de fax analógicos. Puede configurar las puertas de enlace calificadas para que admitan el uso de dispositivos analógicos en su entorno de Skype empresarial Server. Después de migrar a Skype empresarial Server 2019, también debe migrar los objetos de contacto asociados con los dispositivos analógicos. Use el shell de administración de Skype empresarial Server para recuperar primero todos los objetos de contacto asociados con los dispositivos analógicos heredados y, a continuación, mover dichos objetos al grupo de servidores de Skype empresarial 2019.
ms.openlocfilehash: 7b90a52486725c2cf30856dc643660d569d698e2
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752832"
---
# <a name="migrate-analog-devices"></a><span data-ttu-id="c1c1c-107">Migrar dispositivos analógicos</span><span class="sxs-lookup"><span data-stu-id="c1c1c-107">Migrate analog devices</span></span>

<span data-ttu-id="c1c1c-108">Skype empresarial Server proporciona compatibilidad con dispositivos analógicos.</span><span class="sxs-lookup"><span data-stu-id="c1c1c-108">Skype for Business Server provides support for analog devices.</span></span> <span data-ttu-id="c1c1c-109">En concreto, los dispositivos analógicos compatibles son los teléfonos de audio analógicos y los equipos de fax analógicos.</span><span class="sxs-lookup"><span data-stu-id="c1c1c-109">Specifically, the supported analog devices are analog audio phones and analog fax machines.</span></span> <span data-ttu-id="c1c1c-110">Puede configurar las puertas de enlace calificadas para que admitan el uso de dispositivos analógicos en su entorno de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="c1c1c-110">You can configure the qualified gateways to support the use of analog devices in your Skype for Business Server environment.</span></span> <span data-ttu-id="c1c1c-111">Después de migrar a Skype empresarial Server 2019, también debe migrar los objetos de contacto asociados con los dispositivos analógicos.</span><span class="sxs-lookup"><span data-stu-id="c1c1c-111">After you migrate to Skype for Business Server 2019, you must also migrate the contact objects associated with the analog devices.</span></span> <span data-ttu-id="c1c1c-112">Use el shell de administración de Skype empresarial Server para recuperar primero todos los objetos de contacto asociados con los dispositivos analógicos heredados y, a continuación, mover dichos objetos al grupo de servidores de Skype empresarial 2019.</span><span class="sxs-lookup"><span data-stu-id="c1c1c-112">Use Skype for Business Server Management Shell to first retrieve all contact objects associated with the legacy analog devices, and then move those objects to the Skype for Business Server 2019 pool.</span></span>

### <a name="to-migrate-analog-devices"></a><span data-ttu-id="c1c1c-113">Para migrar dispositivos analógicos</span><span class="sxs-lookup"><span data-stu-id="c1c1c-113">To migrate analog devices</span></span>

1. <span data-ttu-id="c1c1c-114">Inicie el shell de administración de Skype empresarial Server: haga clic en **Inicio**, **todos los programas**, **Microsoft Skype empresarial Server 2019**y, a continuación, haga clic en **Shell de administración de Skype empresarial Server**.</span><span class="sxs-lookup"><span data-stu-id="c1c1c-114">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Skype for Business Server 2019**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="c1c1c-115">En la línea de comandos, escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="c1c1c-115">At the command line, type:</span></span>

   ```PowerShell
   Get-CsAnalogDevice -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsAnalogDevice -Target pool02.contoso.net
   ```

3. <span data-ttu-id="c1c1c-116">Compruebe que todos los objetos de contacto se han movido al grupo de Skype empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="c1c1c-116">Verify that all contact objects have been moved to the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="c1c1c-117">En la línea de comandos, escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="c1c1c-117">At the command line, type:</span></span>

   ```PowerShell
   Get-CsAnalogDevice -Filter {RegistrarPool -eq "pool02.contoso.net"}
   ```

4. <span data-ttu-id="c1c1c-118">Compruebe que todos los objetos de contacto están ahora asociados con el grupo de Skype empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="c1c1c-118">Verify that all the contact objects are now associated with the Skype for Business Server 2019 pool.</span></span>


