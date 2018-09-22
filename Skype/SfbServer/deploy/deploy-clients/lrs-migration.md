---
title: Migrar dispositivos de sistema de salas de Lync al sistema de sala de Skype versión 2
ms.author: jambirk
author: jambirk
ms.reviewer: sohailta
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ''
description: Lea este tema para obtener información sobre cómo migrar el sistema de salas de Lync dispositivos para utilizar el software de sistema de salas de Skype v2.
ms.openlocfilehash: 954d7893572c1d97506f4b6845792b0b940c3f2b
ms.sourcegitcommit: 6212645c485c41aafe1206bf7d39171ce35837b2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2018
ms.locfileid: "24968641"
---
# <a name="migrate-lync-room-system-lrs-devices-to-skype-room-system-v2"></a><span data-ttu-id="a5920-103">Migrar dispositivos de Lync salón del sistema (LRS) al sistema de salas de Skype v2</span><span class="sxs-lookup"><span data-stu-id="a5920-103">Migrate Lync Room System (LRS) devices to Skype Room System v2</span></span> 
<span data-ttu-id="a5920-104">Dispositivos de Lync salón del sistema (LRS) con el software del sistema de sala de Skype versión 1 (v1 SRS) llegará a fin de soporte en el 9 de octubre de 2018.</span><span class="sxs-lookup"><span data-stu-id="a5920-104">Lync Room System (LRS) devices with Skype Room System Version 1 (SRS v1) software will reach end of support on October 9, 2018.</span></span> <span data-ttu-id="a5920-105">Esto significa que el software de sistemas de salón de Skype no obtendrá cualquier actualizaciones de productos o revisiones después de esta fecha.</span><span class="sxs-lookup"><span data-stu-id="a5920-105">This means Skype Room Systems software will not get any product updates or fixes after this date.</span></span> <span data-ttu-id="a5920-106">Se aconseja a los clientes de dispositivos del sistema de salas de Lync mediante el sistema de salas de Skype v1 software para actualizar sus dispositivos al sistema de sala de Skype versión 2 (v2 SRS).</span><span class="sxs-lookup"><span data-stu-id="a5920-106">Customers with Lync Room System devices using Skype Room System v1 software are advised to upgrade their devices to Skype Room System version 2 (SRS v2).</span></span>

<span data-ttu-id="a5920-107">Software Skype salón del sistema versión 2 (v2 SRS) funciona con Microsoft Teams además de Skype para servicios de Business Server y en línea para las reuniones y llamar al método en todos los dispositivos de v2 admitidas SRS.</span><span class="sxs-lookup"><span data-stu-id="a5920-107">Skype Room System Version 2 (SRS v2) software works with Microsoft Teams in addition to Skype for Business Server and Online services for meetings and calling on all SRS v2 supported devices.</span></span>

<span data-ttu-id="a5920-108">Los dispositivos existente **puede** seguir funcionan después de que el final del software de sistema de salas de Skype v1 admitir.</span><span class="sxs-lookup"><span data-stu-id="a5920-108">Your existing devices **may** continue to work after the end of Skype Room System v1 software support.</span></span> <span data-ttu-id="a5920-109">Este software llegará finalmente a un error de software que necesita Microsoft para liberar una solución, o que tenga un caso donde un protocolo de comunicación existente utilizado por los cambios en el software del sistema de salas de Skype v1 o ya no se admite.</span><span class="sxs-lookup"><span data-stu-id="a5920-109">This software will eventually hit a software bug that needs Microsoft to release a fix, or may have a case where an existing communication protocol used by Skype Room System v1 software changes or is no longer supported.</span></span> <span data-ttu-id="a5920-110">Uno de estos cambios conocido es el tipo de proyectos de TLS 1.0 / 1.1 en Microsoft Office 365.</span><span class="sxs-lookup"><span data-stu-id="a5920-110">One such known change is deprecation of TLS 1.0/ 1.1 in Microsoft Office 365.</span></span> <span data-ttu-id="a5920-111">Encontrará más información acerca de la [Preparación para TLS 1.0/1.1 desaprobación](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Preparing-for-TLS-1-0-1-1-Deprecation-O365-Skype-for-Business/bc-p/223608).</span><span class="sxs-lookup"><span data-stu-id="a5920-111">You can learn more about [Preparing for TLS 1.0/1.1 Deprecation](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Preparing-for-TLS-1-0-1-1-Deprecation-O365-Skype-for-Business/bc-p/223608).</span></span>  

## <a name="which-devices-are-affected"></a><span data-ttu-id="a5920-112">¿Los dispositivos que se ven afectados?</span><span class="sxs-lookup"><span data-stu-id="a5920-112">Which devices are affected?</span></span>
<span data-ttu-id="a5920-113">Ésta es la lista de los dispositivos que se ven afectados por este cambio:</span><span class="sxs-lookup"><span data-stu-id="a5920-113">Here is the list of the devices that are affected by this change:</span></span>
- [<span data-ttu-id="a5920-114">Sistemas inteligentes de salón</span><span class="sxs-lookup"><span data-stu-id="a5920-114">SMART Room systems</span></span>](https://smartkapp.com/products/smart-room-systems)
- [<span data-ttu-id="a5920-115">Crestron RL2</span><span class="sxs-lookup"><span data-stu-id="a5920-115">Crestron RL2</span></span>](https://www.crestron.com/en-US/Products/Featured-Solutions/Crestron-RL-2)
- [<span data-ttu-id="a5920-116">Polycom CX8000</span><span class="sxs-lookup"><span data-stu-id="a5920-116">Polycom CX8000</span></span>](http://www.polycom.com/products-services/products-for-microsoft/skype-for-business/cx8000.html)
- <span data-ttu-id="a5920-117">RL Crestron</span><span class="sxs-lookup"><span data-stu-id="a5920-117">Crestron RL</span></span>

## <a name="upgrade-options"></a><span data-ttu-id="a5920-118">Opciones de actualización</span><span class="sxs-lookup"><span data-stu-id="a5920-118">Upgrade options</span></span>
<span data-ttu-id="a5920-119">Hay varias opciones para actualizar los sistemas de la sala de Lync a la próxima generación de sistemas de salón de Skype (SRS v2).</span><span class="sxs-lookup"><span data-stu-id="a5920-119">There are multiple options for upgrading Lync Room Systems to the next generation of Skype Room Systems (SRS v2).</span></span>

### <a name="crestron-hardware-trade-in-program"></a><span data-ttu-id="a5920-120">Programa de permuta de hardware de Crestron</span><span class="sxs-lookup"><span data-stu-id="a5920-120">Crestron hardware Trade-in program</span></span>
<span data-ttu-id="a5920-121">Crestron proporcionará una actualización en el [sistema de Crestron SR](https://www.crestron.com/en-us/products/featured-solutions/crestron-sr) o equivalente para todos los clientes de sistema de salas de Lync no Crestron.</span><span class="sxs-lookup"><span data-stu-id="a5920-121">Crestron will provide an upgrade to the [Crestron SR system](https://www.crestron.com/en-us/products/featured-solutions/crestron-sr) or equivalent for all Non-Crestron Lync Room System customers.</span></span> <span data-ttu-id="a5920-122">Ver los detalles de este programa [aquí](https://support.crestron.com/app/answers/answer_view/a_id/1000220) o <!-- For details, --> [correo electrónico](mailto:lrsupgrade@crestron.com) de soporte técnico de Crestron LRS.</span><span class="sxs-lookup"><span data-stu-id="a5920-122">See details of this program [here](https://support.crestron.com/app/answers/answer_view/a_id/1000220) or <!-- For details, -->[email](mailto:lrsupgrade@crestron.com) Crestron LRS support.</span></span>  


### <a name="crestron-rl2-to-rl3"></a><span data-ttu-id="a5920-123">Crestron RL2 a RL3</span><span class="sxs-lookup"><span data-stu-id="a5920-123">Crestron RL2 to RL3</span></span>
<span data-ttu-id="a5920-124">Los clientes existentes de Crestron RL2 (también denominada Crestron RL200) pueden adquirir un paquete de actualización para actualizar RL2 actual a RL3 utilizando un para un costo mínimo por dispositivo.</span><span class="sxs-lookup"><span data-stu-id="a5920-124">Existing Crestron RL2 (also referred to as Crestron RL200) customers can acquire an upgrade package to upgrade current RL2 to RL3 using a for a minimal cost per device.</span></span> <span data-ttu-id="a5920-125">Ver los detalles de este programa [aquí](https://support.crestron.com/app/answers/answer_view/a_id/1000220) o <!-- For details, --> [correo electrónico](mailto:lrsupgrade@crestron.com) de soporte técnico de Crestron LRS.</span><span class="sxs-lookup"><span data-stu-id="a5920-125">See details of this program [here](https://support.crestron.com/app/answers/answer_view/a_id/1000220) or <!-- For details, -->[email](mailto:lrsupgrade@crestron.com) Crestron LRS support.</span></span>  


### <a name="smart-room-systems-upgrade--diy-program"></a><span data-ttu-id="a5920-126">Sistemas inteligentes de salón de actualización & BRICOLAJE programa</span><span class="sxs-lookup"><span data-stu-id="a5920-126">SMART Room Systems upgrade & DIY program</span></span>
<span data-ttu-id="a5920-127">Para los clientes inteligentes LRS, aparte de programa de permuta de hardware Crestron, Microsoft e inteligente también estén trabajando en proporcionar una solución para actualizar a v2 de sistema de salas de Skype.</span><span class="sxs-lookup"><span data-stu-id="a5920-127">For SMART LRS customers, apart from Crestron hardware trade-in program, Microsoft and SMART are also working on providing a solution to upgrade to Skype Room System v2.</span></span> <span data-ttu-id="a5920-128">Microsoft también está probando una solución DIY para los clientes inteligentes LRS.</span><span class="sxs-lookup"><span data-stu-id="a5920-128">Microsoft is also testing a DIY solution for SMART LRS customers.</span></span> <span data-ttu-id="a5920-129">Para obtener más detalles de estos programas se proporcionará en esta página de 2018 anticipado de octubre.</span><span class="sxs-lookup"><span data-stu-id="a5920-129">More details of these programs will be provided on this page in early October 2018.</span></span> <span data-ttu-id="a5920-130">Asegúrese de comprobar si hay actualizaciones en estas opciones de actualización.</span><span class="sxs-lookup"><span data-stu-id="a5920-130">Please make sure to check back for updates on these upgrade options.</span></span>

<!--  
For later 
### Do-It-Yourself
A Do-It-Yourself option is also available for customers with upgrade to Windows 10 and Skype Room Systems v2 software. Windows 10 Enterprise Licenses are available through [approved resellers](https://www.microsoft.com/en-us/Licensing/how-to-buy/how-to-buy.aspx) and Skype Room System V2 software will be available through this guide. 
 
  
To use this option however, customers must additionaly buy a [Logitech Screen Share](https://www.logitech.com/en-us/product/screen-share) adapter. Microsoft will provide instructions on how to use this adapter with Skype Room System v2 software. 


Look for upgrade instructions on this page shortly. 
  
### Summary of upgrade options
This table lists summary of all available options for existing LRS devices:
<!--  For later 
| Upgrade Option | SMART Room Systems | Crestron RL2 | Polycom CX8000 | Crestron RL |
|:--- |:--- |:--- |:--- |:--- |
|**Crestron hardware </br>Trade-in program**|Available|Available|Available|Available|
|**Crestron RL3**|Not Available|Available|Not Available|Not Available|
|**Do-It-Yourself**|Available|Not Available|Not Available|Not Available|
| | | | | |
-->

## <a name="what-should-you-do"></a><span data-ttu-id="a5920-131">¿Qué debe hacer?</span><span class="sxs-lookup"><span data-stu-id="a5920-131">What should you do?</span></span>
<span data-ttu-id="a5920-132">Se recomienda que planear actualizar los dispositivos de sistema de salas de Lync a sistemas de salón de Skype v2 antes de degradación de TLS 1.0/1.1 mediante las opciones de actualización mencionadas anteriormente.</span><span class="sxs-lookup"><span data-stu-id="a5920-132">We recommend you plan to update Lync Room System devices to Skype Room Systems v2 before TLS 1.0/1.1 deprecation using upgrade options mentioned above.</span></span> <span data-ttu-id="a5920-133">Además, también puede considerar la sustitución de dispositivos existentes con nuevos dispositivos certificados para SRS v2.</span><span class="sxs-lookup"><span data-stu-id="a5920-133">Additionally, you may also consider replacing existing devices with new devices certified for SRS v2.</span></span> <span data-ttu-id="a5920-134">Consulte los detalles en [requisitos de sistemas de salón de Skype v2](https://docs.microsoft.com/en-us/skypeforbusiness/plan-your-deployment/clients-and-devices/requirements).</span><span class="sxs-lookup"><span data-stu-id="a5920-134">See details in [Skype Room Systems v2 requirements](https://docs.microsoft.com/en-us/skypeforbusiness/plan-your-deployment/clients-and-devices/requirements).</span></span>  

> [!NOTE]
> <span data-ttu-id="a5920-135">Funcionalidad táctil y Pizarra no se admite todavía en el sistema de salas de Skype v2.</span><span class="sxs-lookup"><span data-stu-id="a5920-135">Touch and whiteboard functionality is not yet supported in Skype Room System v2.</span></span> <span data-ttu-id="a5920-136">Compatibilidad con táctil y Pizarra se encuentra en el registro de sistema de salas de Skype v2 y se agregará en CY2019 H1.</span><span class="sxs-lookup"><span data-stu-id="a5920-136">Touch and whiteboard support is in the backlog for Skype Room System v2 and will be added in H1 CY2019.</span></span>
