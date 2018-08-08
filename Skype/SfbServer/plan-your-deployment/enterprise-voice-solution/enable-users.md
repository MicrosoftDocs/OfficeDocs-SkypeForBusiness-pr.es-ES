---
title: Habilitar a usuarios para E9-1-1 en Skype para Business Server
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 3cc64f5b-492e-4c47-9713-3c376f2aad02
description: Decisiones necesarias para la directiva de ubicación para una implementación de E9-1-1 en Skype para Business Server Enterprise Voice, incluido qué usuarios para habilitar y cómo admitir usuarios móviles.
ms.openlocfilehash: c5dbbc7904313ffc1706615f2aec506032e20074
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2018
ms.locfileid: "20997197"
---
# <a name="enable-users-for-e9-1-1-in-skype-for-business-server"></a><span data-ttu-id="d3d1d-103">Habilitar a usuarios para E9-1-1 en Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="d3d1d-103">Enable users for E9-1-1 in Skype for Business Server</span></span>
 
<span data-ttu-id="d3d1d-104">Decisiones necesarias para la directiva de ubicación para una implementación de E9-1-1 en Skype para Business Server Enterprise Voice, incluido qué usuarios para habilitar y cómo admitir usuarios móviles.</span><span class="sxs-lookup"><span data-stu-id="d3d1d-104">Decisions necessary for the location policy for an E9-1-1 deployment in Skype for Business Server Enterprise Voice, including which users to enable and how to support roaming users.</span></span>
  
<span data-ttu-id="d3d1d-105">Durante el registro de cliente, Skype para Business Server usa una directiva de ubicación para configurar las propiedades de E9-1-1 para los usuarios habilitados para Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="d3d1d-105">During client registration, Skype for Business Server uses a location policy to configure the E9-1-1 properties for Enterprise Voice-enabled users.</span></span> <span data-ttu-id="d3d1d-106">Esta directiva contiene la configuración que define cómo se implementa E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="d3d1d-106">This policy contains the settings that define how E9-1-1 is implemented.</span></span> <span data-ttu-id="d3d1d-107">Por ejemplo, la directiva de ubicación contiene información como la emergencia cadena de marcado y, si un usuario es necesario escribir manualmente una ubicación si el servicio de información de ubicación no automáticamente proporcionar uno.</span><span class="sxs-lookup"><span data-stu-id="d3d1d-107">For example, the location policy contains information such as the emergency dial string, and whether or not a user is required to manually enter a location if the Location Information service does not automatically provide one.</span></span> <span data-ttu-id="d3d1d-108">Para ver una definición completa de una directiva de ubicación, vea [Planear las directivas de ubicación para Skype para Business Server](location-policies.md).</span><span class="sxs-lookup"><span data-stu-id="d3d1d-108">For a complete definition of a location policy, see [Plan location policies for Skype for Business Server](location-policies.md).</span></span>
  
<span data-ttu-id="d3d1d-109">Skype para Business Server puede asignar una directiva de ubicación a los clientes en función de la subred, o a los usuarios en función de un global por sitio o directiva por usuario.</span><span class="sxs-lookup"><span data-stu-id="d3d1d-109">Skype for Business Server can assign a location policy to clients based on subnet, or to users based on a global, per-site, or per-user policy.</span></span> <span data-ttu-id="d3d1d-110">Para ayudarte a decidir cómo habilitarás los usuarios, necesitas responder primero las siguientes preguntas.</span><span class="sxs-lookup"><span data-stu-id="d3d1d-110">To help decide how you will enable users, you should first answer the following questions.</span></span>
  
 <span data-ttu-id="d3d1d-111">**¿Piensa habilitar todos los usuarios o limitar la compatibilidad a zonas geográficas específicas de la empresa?**</span><span class="sxs-lookup"><span data-stu-id="d3d1d-111">**Do you plan to enable all users, or limit support to specific geographic areas of the enterprise?**</span></span>
  
> <span data-ttu-id="d3d1d-112">Puede asignar una ubicación para todos los usuarios de su empresa mediante el uso de una directiva de ubicación global.</span><span class="sxs-lookup"><span data-stu-id="d3d1d-112">You can assign a location to all users in your enterprise by using a global location policy.</span></span> <span data-ttu-id="d3d1d-113">Sin embargo, mediante la asignación de una directiva de ubicación a un Skype para el sitio de red de Business Server y, a continuación, agregar subredes al sitio, puede limitar la compatibilidad de E9-1-1 a ubicaciones seleccionadas dentro de la empresa y especificar el comportamiento de enrutamiento de E9-1-1 por sitio.</span><span class="sxs-lookup"><span data-stu-id="d3d1d-113">However, by assigning a location policy to a Skype for Business Server network site and then adding subnets to the site, you can limit E9-1-1 support to selected locations within the enterprise and specify E9-1-1 routing behavior on a per-site basis.</span></span> 
    
 <span data-ttu-id="d3d1d-114">**¿Piensa habilitar usuarios individuales a través de una directiva de usuario?**</span><span class="sxs-lookup"><span data-stu-id="d3d1d-114">**Do you plan to enable individual users through a user policy?**</span></span>
  
> <span data-ttu-id="d3d1d-115">Si deseas personalizar la asistencia de E9-1-1, puedes asignar directivas de ubicación directamente a usuarios o a objetos de contactos telefónicos de un área común específicos.</span><span class="sxs-lookup"><span data-stu-id="d3d1d-115">You can assign location policies directly to specific users or common area phone contact objects if you want to customize their E9-1-1 support.</span></span>
    
 <span data-ttu-id="d3d1d-116">**Cuando los clientes se desplazan fuera de la red o se encuentran en una subred no definida en la red, ¿tienen los clientes que seguir habilitados en E9-1-1?**</span><span class="sxs-lookup"><span data-stu-id="d3d1d-116">**When clients roam outside the network or connect from an undefined subnet, should the clients still be enabled for E9-1-1?**</span></span>
  
> <span data-ttu-id="d3d1d-117">Si los usuarios tienen asignada una global, de sitio, o directiva de ubicación por usuario, pueden ser necesarios para especificar manualmente una ubicación en el cliente si el cliente no se encuentra dentro de una subred definida o se ha encontrado ninguna ubicación mediante el servicio de información de ubicación.</span><span class="sxs-lookup"><span data-stu-id="d3d1d-117">If users are assigned a global, site, or per-user location policy, they can be required to manually enter a location into the client if the client is not located within a defined subnet or no location has been found by the Location Information service.</span></span> <span data-ttu-id="d3d1d-118">Para obtener más información, consulte [definir la experiencia del usuario para adquirir manualmente una ubicación en Skype para Business Server](manually-acquiring-a-location.md).</span><span class="sxs-lookup"><span data-stu-id="d3d1d-118">For details, see [Define the user experience for manually acquiring a location in Skype for Business Server](manually-acquiring-a-location.md).</span></span>
    

