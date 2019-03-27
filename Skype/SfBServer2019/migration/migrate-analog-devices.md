---
title: Migrar dispositivos analógicos
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Skype para Business Server proporciona compatibilidad con dispositivos analógicos. Específicamente, los dispositivos analógicos compatibles son teléfonos audioconferencias analógicos y equipos de fax analógicos. Puede configurar las puertas de enlace completa para admitir el uso de dispositivos analógicos en su Skype para el entorno de servidor empresarial. Después de migrar a Skype para Business Server 2019, también debe migrar los objetos de contacto asociados con los dispositivos analógicos. Usar Skype para Shell de administración de servidor empresarial para todos los recuperar primero objetos asociados con los dispositivos analógicos heredados de contacto y, a continuación, mover los objetos a la Skype para el grupo de servidores de Business Server 2019.
ms.openlocfilehash: 80edf5b806ffd192d125bd5da27207a37f3074d1
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30889969"
---
# <a name="migrate-analog-devices"></a><span data-ttu-id="16ec2-107">Migrar dispositivos analógicos</span><span class="sxs-lookup"><span data-stu-id="16ec2-107">Migrate analog devices</span></span>

<span data-ttu-id="16ec2-108">Skype para Business Server proporciona compatibilidad con dispositivos analógicos.</span><span class="sxs-lookup"><span data-stu-id="16ec2-108">Skype for Business Server provides support for analog devices.</span></span> <span data-ttu-id="16ec2-109">Específicamente, los dispositivos analógicos compatibles son teléfonos audioconferencias analógicos y equipos de fax analógicos.</span><span class="sxs-lookup"><span data-stu-id="16ec2-109">Specifically, the supported analog devices are analog audio phones and analog fax machines.</span></span> <span data-ttu-id="16ec2-110">Puede configurar las puertas de enlace completa para admitir el uso de dispositivos analógicos en su Skype para el entorno de servidor empresarial.</span><span class="sxs-lookup"><span data-stu-id="16ec2-110">You can configure the qualified gateways to support the use of analog devices in your Skype for Business Server environment.</span></span> <span data-ttu-id="16ec2-111">Después de migrar a Skype para Business Server 2019, también debe migrar los objetos de contacto asociados con los dispositivos analógicos.</span><span class="sxs-lookup"><span data-stu-id="16ec2-111">After you migrate to Skype for Business Server 2019, you must also migrate the contact objects associated with the analog devices.</span></span> <span data-ttu-id="16ec2-112">Usar Skype para Shell de administración de servidor empresarial para todos los recuperar primero objetos asociados con los dispositivos analógicos heredados de contacto y, a continuación, mover los objetos a la Skype para el grupo de servidores de Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="16ec2-112">Use Skype for Business Server Management Shell to first retrieve all contact objects associated with the legacy analog devices, and then move those objects to the Skype for Business Server 2019 pool.</span></span>

### <a name="to-migrate-analog-devices"></a><span data-ttu-id="16ec2-113">Para migrar dispositivos analógicos</span><span class="sxs-lookup"><span data-stu-id="16ec2-113">To migrate analog devices</span></span>

1. <span data-ttu-id="16ec2-114">Iniciar el Skype para Shell de administración de negocio Server: haga clic en **Inicio**, haga clic en **Todos los programas**, haga clic en **Microsoft Skype para Business Server 2019**y, a continuación, haga clic en **Skype para Shell de administración de servidor empresarial**.</span><span class="sxs-lookup"><span data-stu-id="16ec2-114">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Skype for Business Server 2019**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="16ec2-115">En la línea de comandos, escriba:</span><span class="sxs-lookup"><span data-stu-id="16ec2-115">At the command line, type:</span></span>

   ```
   Get-CsAnalogDevice -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsAnalogDevice -Target pool02.contoso.net
   ```

3. <span data-ttu-id="16ec2-116">Compruebe que todos los objetos de contacto se han movido a la Skype para el grupo de servidores de Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="16ec2-116">Verify that all contact objects have been moved to the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="16ec2-117">En la línea de comandos, escriba:</span><span class="sxs-lookup"><span data-stu-id="16ec2-117">At the command line, type:</span></span>

   ```
   Get-CsAnalogDevice -Filter {RegistrarPool -eq "pool02.contoso.net"}
   ```

4. <span data-ttu-id="16ec2-118">Compruebe que todos los objetos de contacto están ahora asociadas con el Skype para el grupo de servidores de Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="16ec2-118">Verify that all the contact objects are now associated with the Skype for Business Server 2019 pool.</span></span>


