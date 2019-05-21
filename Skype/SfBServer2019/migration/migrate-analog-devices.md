---
title: Migrar dispositivos analógicos
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Skype empresarial Server proporciona compatibilidad con dispositivos analógicos. Específicamente, los dispositivos analógicos compatibles son teléfonos de audio analógicos y equipos de fax analógico. Puede configurar las puertas de enlace calificadas para que admitan el uso de dispositivos analógicos en el entorno de Skype empresarial Server. Después de migrar a Skype empresarial Server 2019, también debe migrar los objetos de contacto asociados con los dispositivos analógicos. Use el shell de administración de Skype empresarial Server para recuperar primero todos los objetos de contacto asociados con los dispositivos analógicos heredados y, a continuación, mover esos objetos al grupo de servidores de Skype empresarial 2019.
ms.openlocfilehash: a822f8f73ad839654d266182172ef8e30d5d28e8
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34280846"
---
# <a name="migrate-analog-devices"></a><span data-ttu-id="c8d07-107">Migrar dispositivos analógicos</span><span class="sxs-lookup"><span data-stu-id="c8d07-107">Migrate analog devices</span></span>

<span data-ttu-id="c8d07-108">Skype empresarial Server proporciona compatibilidad con dispositivos analógicos.</span><span class="sxs-lookup"><span data-stu-id="c8d07-108">Skype for Business Server provides support for analog devices.</span></span> <span data-ttu-id="c8d07-109">Específicamente, los dispositivos analógicos compatibles son teléfonos de audio analógicos y equipos de fax analógico.</span><span class="sxs-lookup"><span data-stu-id="c8d07-109">Specifically, the supported analog devices are analog audio phones and analog fax machines.</span></span> <span data-ttu-id="c8d07-110">Puede configurar las puertas de enlace calificadas para que admitan el uso de dispositivos analógicos en el entorno de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="c8d07-110">You can configure the qualified gateways to support the use of analog devices in your Skype for Business Server environment.</span></span> <span data-ttu-id="c8d07-111">Después de migrar a Skype empresarial Server 2019, también debe migrar los objetos de contacto asociados con los dispositivos analógicos.</span><span class="sxs-lookup"><span data-stu-id="c8d07-111">After you migrate to Skype for Business Server 2019, you must also migrate the contact objects associated with the analog devices.</span></span> <span data-ttu-id="c8d07-112">Use el shell de administración de Skype empresarial Server para recuperar primero todos los objetos de contacto asociados con los dispositivos analógicos heredados y, a continuación, mover esos objetos al grupo de servidores de Skype empresarial 2019.</span><span class="sxs-lookup"><span data-stu-id="c8d07-112">Use Skype for Business Server Management Shell to first retrieve all contact objects associated with the legacy analog devices, and then move those objects to the Skype for Business Server 2019 pool.</span></span>

### <a name="to-migrate-analog-devices"></a><span data-ttu-id="c8d07-113">Para migrar dispositivos analógicos</span><span class="sxs-lookup"><span data-stu-id="c8d07-113">To migrate analog devices</span></span>

1. <span data-ttu-id="c8d07-114">Inicie el shell de administración de Skype empresarial Server: haga clic en **Inicio**, haga clic en **todos los programas**, haga clic en **Microsoft Skype empresarial Server 2019**y, a continuación, haga clic en **consola de administración de Skype empresarial Server**.</span><span class="sxs-lookup"><span data-stu-id="c8d07-114">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Skype for Business Server 2019**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="c8d07-115">En la línea de comandos, escriba:</span><span class="sxs-lookup"><span data-stu-id="c8d07-115">At the command line, type:</span></span>

   ```
   Get-CsAnalogDevice -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsAnalogDevice -Target pool02.contoso.net
   ```

3. <span data-ttu-id="c8d07-116">Compruebe que todos los objetos de contacto se han movido al grupo de servidores de Skype empresarial 2019.</span><span class="sxs-lookup"><span data-stu-id="c8d07-116">Verify that all contact objects have been moved to the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="c8d07-117">En la línea de comandos, escriba:</span><span class="sxs-lookup"><span data-stu-id="c8d07-117">At the command line, type:</span></span>

   ```
   Get-CsAnalogDevice -Filter {RegistrarPool -eq "pool02.contoso.net"}
   ```

4. <span data-ttu-id="c8d07-118">Compruebe que todos los objetos de contacto están asociados con el grupo de servidores de Skype empresarial 2019.</span><span class="sxs-lookup"><span data-stu-id="c8d07-118">Verify that all the contact objects are now associated with the Skype for Business Server 2019 pool.</span></span>


