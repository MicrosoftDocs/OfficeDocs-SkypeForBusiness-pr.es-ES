---
title: Migrar dispositivos de Lync Room System a Salas de Microsoft Teams
ms.author: dstrome
author: dstrome
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
ms.assetid: ''
description: Lea este tema para obtener información sobre cómo migrar dispositivos de Lync Room System para usar el software de Salas de Microsoft Teams.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: d8da14f2d5f3ec75c6a9fb9c03a33d7e83cd1aed
ms.sourcegitcommit: 975f81d9e595dfb339550625d7cef8ad84449e20
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662625"
---
# <a name="migrate-lync-room-system-lrs-devices-to-microsoft-teams-rooms"></a><span data-ttu-id="04156-103">Migrar dispositivos de Lync Room System (LRS) a Salas de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="04156-103">Migrate Lync Room System (LRS) devices to Microsoft Teams Rooms</span></span>

<span data-ttu-id="04156-104">Los dispositivos de Lync Room System (LRS) con el software Skype Room System 1 (SRS v1) finalizaron el soporte el 9 de octubre de [2018.](https://support.microsoft.com/help/4043450/products-reaching-end-of-support-for-2018)</span><span class="sxs-lookup"><span data-stu-id="04156-104">Lync Room System (LRS) devices with Skype Room System Version 1 (SRS v1) software has reached [end of support on October 9, 2018](https://support.microsoft.com/help/4043450/products-reaching-end-of-support-for-2018).</span></span> <span data-ttu-id="04156-105">Es decir, el software de sistemas de la Sala de reuniones de Skype v1 ya no recibirá más actualizaciones ni correcciones.</span><span class="sxs-lookup"><span data-stu-id="04156-105">This means Skype Room Systems v1 software will no longer get any product updates or fixes anymore.</span></span> <span data-ttu-id="04156-106">Se recomienda a los clientes que usan los dispositivos con el sistema de la Sala de reuniones de Lync con el software del sistema de Sala de reuniones de Skype v1 que actualicen sus dispositivos a las Salas de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="04156-106">Customers with Lync Room System devices using Skype Room System v1 software are advised to upgrade their devices to Microsoft Teams Rooms.</span></span>

<span data-ttu-id="04156-107">El software de salas de Microsoft Teams funciona con Microsoft Teams, así como con Skype Empresarial Server y con los servicios en línea para reuniones y llamadas en todos los dispositivos compatibles con salas de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="04156-107">Microsoft Teams Rooms software works with Microsoft Teams in addition to Skype for Business Server and Online services for meetings and calling on all Microsoft Teams Rooms supported devices.</span></span>

<span data-ttu-id="04156-108">Es posible que **sus dispositivos existentes** sigan funcionando después del fin de la compatibilidad con el software de Skype Room System v1.</span><span class="sxs-lookup"><span data-stu-id="04156-108">Your existing devices **may** continue to work after the end of Skype Room System v1 software support.</span></span> <span data-ttu-id="04156-109">Sin embargo, si este software encuentra un error de software que necesita que Microsoft libere una corrección, no será compatible.</span><span class="sxs-lookup"><span data-stu-id="04156-109">However, if this software hits a software bug that needs Microsoft to release a fix, it will not be supported.</span></span> <span data-ttu-id="04156-110">SRS v1 usa TLS 1.0/ 1.1, que Microsoft dejará de usar en el futuro.</span><span class="sxs-lookup"><span data-stu-id="04156-110">SRS v1 uses TLS 1.0/ 1.1 which will be deprecated by Microsoft in the future.</span></span> <span data-ttu-id="04156-111">Puede obtener más información sobre la preparación del desuso de [TLS 1.0/1.1.](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Preparing-for-TLS-1-0-1-1-Deprecation-O365-Skype-for-Business/bc-p/223608)</span><span class="sxs-lookup"><span data-stu-id="04156-111">You can learn more about [preparing for TLS 1.0/1.1 deprecation](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Preparing-for-TLS-1-0-1-1-Deprecation-O365-Skype-for-Business/bc-p/223608).</span></span> 

## <a name="which-devices-are-affected"></a><span data-ttu-id="04156-112">¿Qué dispositivos se ven afectados?</span><span class="sxs-lookup"><span data-stu-id="04156-112">Which devices are affected?</span></span>

<span data-ttu-id="04156-113">Esta es la lista de los dispositivos afectados por este cambio:</span><span class="sxs-lookup"><span data-stu-id="04156-113">Here is the list of the devices that are affected by this change:</span></span>

- <span data-ttu-id="04156-114">Crestron RL</span><span class="sxs-lookup"><span data-stu-id="04156-114">Crestron RL</span></span>
- [<span data-ttu-id="04156-115">Crestron RL2</span><span class="sxs-lookup"><span data-stu-id="04156-115">Crestron RL2</span></span>](https://www.crestron.com/Products/Featured-Solutions/Crestron-RL-2)
- [<span data-ttu-id="04156-116">Sistemas de sala INTELIGENTE</span><span class="sxs-lookup"><span data-stu-id="04156-116">SMART Room systems</span></span>](https://support.smarttech.com/en/hardware/room-systems-skype)
- [<span data-ttu-id="04156-117">Polycom CX8000</span><span class="sxs-lookup"><span data-stu-id="04156-117">Polycom CX8000</span></span>](https://www.polycom.com/products-services/products-for-microsoft/skype-for-business/cx8000.html)

## <a name="upgrade-options"></a><span data-ttu-id="04156-118">Opciones de actualización</span><span class="sxs-lookup"><span data-stu-id="04156-118">Upgrade options</span></span>

<span data-ttu-id="04156-119">Existen varias opciones para actualizar Sistemas de salas de Lync a la siguiente generación de salas de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="04156-119">There are multiple options for upgrading Lync Room Systems to the next generation of Microsoft Teams Rooms.</span></span>

### <a name="crestron-hardware-trade-in-program"></a><span data-ttu-id="04156-120">Programa de intercambio de hardware Crestron</span><span class="sxs-lookup"><span data-stu-id="04156-120">Crestron hardware Trade-in program</span></span>

<span data-ttu-id="04156-121">Crestron proporcionará una actualización al sistema [Crestron SR](https://www.crestron.com/products/featured-solutions/crestron-sr) o equivalente para todos los clientes de Lync Room System que no son de Crestron (por ejemplo, Smart o Polycom LRS).</span><span class="sxs-lookup"><span data-stu-id="04156-121">Crestron will provide an upgrade to the [Crestron SR system](https://www.crestron.com/products/featured-solutions/crestron-sr) or equivalent for all Non-Crestron Lync Room System customers (e.g Smart or Polycom LRS).</span></span> <span data-ttu-id="04156-122">Consulta los detalles de este [programa aquí o](https://support.crestron.com/app/answers/answer_view/a_id/1000220)</span><span class="sxs-lookup"><span data-stu-id="04156-122">See details of this program [here](https://support.crestron.com/app/answers/answer_view/a_id/1000220) or</span></span> <!-- For details, --><span data-ttu-id="04156-123">[correo electrónico](mailto:lrsupgrade@crestron.com) Compatibilidad con Lrron LRS.</span><span class="sxs-lookup"><span data-stu-id="04156-123">[email](mailto:lrsupgrade@crestron.com) Crestron LRS support.</span></span>  

### <a name="crestron-rl2-upgrade-to-microsoft-teams-rooms"></a><span data-ttu-id="04156-124">Actualización de Crestron RL2 a Salas de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="04156-124">Crestron RL2 upgrade to Microsoft Teams Rooms</span></span>

<span data-ttu-id="04156-125">Los clientes existentes de Crestron RL2 (también conocido como Crestron RL200) pueden adquirir un kit de actualización para actualizar RL2 a RL3 actual usando un costo mínimo por dispositivo.</span><span class="sxs-lookup"><span data-stu-id="04156-125">Existing Crestron RL2 (also referred to as Crestron RL200) customers can acquire an upgrade kit to upgrade current RL2 to RL3 using a for a minimal cost per device.</span></span> <span data-ttu-id="04156-126">Consulta aquí los detalles de este [programa.](https://crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-RL-2/CCS-UC-250-KIT)</span><span class="sxs-lookup"><span data-stu-id="04156-126">See details of this program [here](https://crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-RL-2/CCS-UC-250-KIT).</span></span>

### <a name="smart-room-systems-upgrade"></a><span data-ttu-id="04156-127">Actualización de SMART Room Systems</span><span class="sxs-lookup"><span data-stu-id="04156-127">SMART Room Systems upgrade</span></span>

<span data-ttu-id="04156-128">Para los clientes SMART LRS, además del programa de intercambio de hardware Crestron, SMART también está trabajando en proporcionar una solución para actualizar a Microsoft Teams Rooms.</span><span class="sxs-lookup"><span data-stu-id="04156-128">For SMART LRS customers, apart from Crestron hardware trade-in program, SMART is also working on providing a solution to upgrade to Microsoft Teams Rooms.</span></span> <span data-ttu-id="04156-129">SMART Technologies Inc. proporciona esta actualización al cliente en soporte técnico.</span><span class="sxs-lookup"><span data-stu-id="04156-129">This upgrade will be provided by SMART Technologies Inc. to customer under product support.</span></span> <span data-ttu-id="04156-130">Para obtener más información, haz [clic aquí.](https://support.smarttech.com/docs/hardware/room-systems-skype/srs-skype-v2/en/about/default.cshtml)</span><span class="sxs-lookup"><span data-stu-id="04156-130">Please see more about this [here](https://support.smarttech.com/docs/hardware/room-systems-skype/srs-skype-v2/en/about/default.cshtml).</span></span>


## <a name="what-should-you-do"></a><span data-ttu-id="04156-131">¿Qué debe hacer?</span><span class="sxs-lookup"><span data-stu-id="04156-131">What should you do?</span></span>

<span data-ttu-id="04156-132">Le recomendamos que planee actualizar los dispositivos de Lync Room System a Microsoft Teams Rooms antes del desuso de TLS 1.0/1.1 mediante las opciones de actualización mencionadas anteriormente.</span><span class="sxs-lookup"><span data-stu-id="04156-132">We recommend you plan to update Lync Room System devices to Microsoft Teams Rooms before TLS 1.0/1.1 deprecation using upgrade options mentioned above.</span></span> <span data-ttu-id="04156-133">Además, también puede considerar la posibilidad de reemplazar los dispositivos existentes con nuevos dispositivos certificados para Salas de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="04156-133">Additionally, you may also consider replacing existing devices with new devices certified for Microsoft Teams Rooms.</span></span> <span data-ttu-id="04156-134">Consulte [los dispositivos de](https://aka.ms/roomdevices) sala para obtener más información y consulte los [requisitos de salas de Microsoft Teams.](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/clients-and-devices/requirements)</span><span class="sxs-lookup"><span data-stu-id="04156-134">See [Room devices](https://aka.ms/roomdevices) for details and also take a look at [Microsoft Teams Rooms requirements](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/clients-and-devices/requirements).</span></span>  


> [!NOTE]
> <span data-ttu-id="04156-135">El software de salas de Microsoft Teams admite el protocolo TLS 1.2 del 14 de diciembre de 2018 con la versión 4.0.64.0 de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="04156-135">Microsoft Teams Rooms software supports the TLS 1.2 protocol as of December 14, 2018 with app version 4.0.64.0.</span></span> <span data-ttu-id="04156-136">Para los clientes locales, habilitar la comunicación a través de TLS 1.2 para salas de Microsoft Teams requiere La actualización acumulativa 9 (CU9) de Skype Empresarial Server 2015 o la actualización acumulativa 1 (CU1) de Skype Empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="04156-136">For on-premises customers, enabling communication over TLS 1.2 for Microsoft Teams Rooms requires Skype for Business Server 2015 Cumulative Update 9 (CU9) or Skype for Business Server 2019 Cumulative Update 1 (CU1).</span></span> <span data-ttu-id="04156-137">El cambio no tiene que afectar a los clientes de Skype Empresarial Online, ya que los cambios de cliente son compatibles con versiones anteriores y 2010.</span><span class="sxs-lookup"><span data-stu-id="04156-137">The change should not affect Skype for Business Online customers as client changes are forward and backward compliant.</span></span>
