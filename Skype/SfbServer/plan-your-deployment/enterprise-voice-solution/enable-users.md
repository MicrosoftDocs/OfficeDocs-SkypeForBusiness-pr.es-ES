---
title: Habilitar usuarios para E9-1-1 en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 3cc64f5b-492e-4c47-9713-3c376f2aad02
description: Decisiones necesarias para la Directiva de ubicación de una implementación de E9-1-1 en Skype empresarial Server Enterprise Voice, incluyendo qué usuarios habilitar y cómo admitir usuarios móviles.
ms.openlocfilehash: 717b127a94fbac966476c681cfb7f6e81d91bde9
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802960"
---
# <a name="enable-users-for-e9-1-1-in-skype-for-business-server"></a><span data-ttu-id="c5dcd-103">Habilitar usuarios para E9-1-1 en Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="c5dcd-103">Enable users for E9-1-1 in Skype for Business Server</span></span>
 
<span data-ttu-id="c5dcd-104">Decisiones necesarias para la Directiva de ubicación de una implementación de E9-1-1 en Skype empresarial Server Enterprise Voice, incluyendo qué usuarios habilitar y cómo admitir usuarios móviles.</span><span class="sxs-lookup"><span data-stu-id="c5dcd-104">Decisions necessary for the location policy for an E9-1-1 deployment in Skype for Business Server Enterprise Voice, including which users to enable and how to support roaming users.</span></span>
  
<span data-ttu-id="c5dcd-105">Durante el registro del cliente, Skype empresarial Server usa una directiva de ubicación para configurar las propiedades E9-1-1 para los usuarios habilitados para voz.</span><span class="sxs-lookup"><span data-stu-id="c5dcd-105">During client registration, Skype for Business Server uses a location policy to configure the E9-1-1 properties for Enterprise Voice-enabled users.</span></span> <span data-ttu-id="c5dcd-106">Esta directiva contiene la configuración que define cómo se implementa E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="c5dcd-106">This policy contains the settings that define how E9-1-1 is implemented.</span></span> <span data-ttu-id="c5dcd-107">Por ejemplo, la Directiva de ubicación contiene información como, por ejemplo, la cadena de marcado de emergencia y si un usuario debe o no especificar manualmente una ubicación si el servicio de información de ubicación no proporciona una automáticamente.</span><span class="sxs-lookup"><span data-stu-id="c5dcd-107">For example, the location policy contains information such as the emergency dial string, and whether or not a user is required to manually enter a location if the Location Information service does not automatically provide one.</span></span> <span data-ttu-id="c5dcd-108">Para obtener una definición completa de una directiva de ubicación, consulte [planear directivas de ubicación para Skype empresarial Server](location-policies.md).</span><span class="sxs-lookup"><span data-stu-id="c5dcd-108">For a complete definition of a location policy, see [Plan location policies for Skype for Business Server](location-policies.md).</span></span>
  
<span data-ttu-id="c5dcd-109">Skype empresarial Server puede asignar una directiva de ubicación a clientes en función de la subred o a usuarios en función de una directiva global, por sitio o por usuario.</span><span class="sxs-lookup"><span data-stu-id="c5dcd-109">Skype for Business Server can assign a location policy to clients based on subnet, or to users based on a global, per-site, or per-user policy.</span></span> <span data-ttu-id="c5dcd-110">Para ayudarte a decidir cómo habilitarás los usuarios, necesitas responder primero las siguientes preguntas.</span><span class="sxs-lookup"><span data-stu-id="c5dcd-110">To help decide how you will enable users, you should first answer the following questions.</span></span>
  
 <span data-ttu-id="c5dcd-111">**¿Piensa habilitar todos los usuarios o limitar la compatibilidad a zonas geográficas específicas de la empresa?**</span><span class="sxs-lookup"><span data-stu-id="c5dcd-111">**Do you plan to enable all users, or limit support to specific geographic areas of the enterprise?**</span></span>
  
> <span data-ttu-id="c5dcd-112">Puede asignar una ubicación a todos los usuarios de su empresa mediante una directiva de ubicación global.</span><span class="sxs-lookup"><span data-stu-id="c5dcd-112">You can assign a location to all users in your enterprise by using a global location policy.</span></span> <span data-ttu-id="c5dcd-113">Sin embargo, si asigna una directiva de ubicación a un sitio de red de Skype empresarial Server y luego agrega subredes al sitio, puede limitar la compatibilidad con E9-1-1 a ubicaciones seleccionadas dentro de la empresa y especificar el comportamiento de enrutamiento E9-1-1 en cada sitio.</span><span class="sxs-lookup"><span data-stu-id="c5dcd-113">However, by assigning a location policy to a Skype for Business Server network site and then adding subnets to the site, you can limit E9-1-1 support to selected locations within the enterprise and specify E9-1-1 routing behavior on a per-site basis.</span></span> 
    
 <span data-ttu-id="c5dcd-114">**¿Piensa habilitar usuarios individuales a través de una directiva de usuario?**</span><span class="sxs-lookup"><span data-stu-id="c5dcd-114">**Do you plan to enable individual users through a user policy?**</span></span>
  
> <span data-ttu-id="c5dcd-115">Si deseas personalizar la asistencia de E9-1-1, puedes asignar directivas de ubicación directamente a usuarios o a objetos de contactos telefónicos de un área común específicos.</span><span class="sxs-lookup"><span data-stu-id="c5dcd-115">You can assign location policies directly to specific users or common area phone contact objects if you want to customize their E9-1-1 support.</span></span>
    
 <span data-ttu-id="c5dcd-116">**Cuando los clientes se desplazan fuera de la red o se encuentran en una subred no definida en la red, ¿tienen los clientes que seguir habilitados en E9-1-1?**</span><span class="sxs-lookup"><span data-stu-id="c5dcd-116">**When clients roam outside the network or connect from an undefined subnet, should the clients still be enabled for E9-1-1?**</span></span>
  
> <span data-ttu-id="c5dcd-117">Si se asigna a los usuarios una directiva de ubicación global, de sitio o por usuario, se les puede requerir introducir manualmente una ubicación en el cliente si el cliente no se encuentra en una subred definida o si el servicio de información de ubicación no ha encontrado ninguna ubicación.</span><span class="sxs-lookup"><span data-stu-id="c5dcd-117">If users are assigned a global, site, or per-user location policy, they can be required to manually enter a location into the client if the client is not located within a defined subnet or no location has been found by the Location Information service.</span></span> <span data-ttu-id="c5dcd-118">Para obtener más información, consulte [definir la experiencia de usuario para la adquisición manual de una ubicación en Skype empresarial Server](manually-acquiring-a-location.md).</span><span class="sxs-lookup"><span data-stu-id="c5dcd-118">For details, see [Define the user experience for manually acquiring a location in Skype for Business Server](manually-acquiring-a-location.md).</span></span>
    

