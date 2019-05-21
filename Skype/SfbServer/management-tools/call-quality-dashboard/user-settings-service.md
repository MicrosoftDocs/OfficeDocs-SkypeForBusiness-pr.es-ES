---
title: Servicio de configuración de usuario del panel de calidad de llamadas (CQD)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: eafeb54a-2574-415b-b991-a0ff0470d8c3
description: 'Resumen: Obtenga información sobre el servicio de configuración de usuario, que es parte de la API del repositorio para el panel de calidad de llamadas. El panel de calidad de llamadas es una herramienta para Skype empresarial Server.'
ms.openlocfilehash: e5e068d66adb325900b055a19aedcfaeabf4f2bc
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34274488"
---
# <a name="user-settings-service-for-call-quality-dashboard-cqd"></a><span data-ttu-id="6f020-104">Servicio de configuración de usuario del panel de calidad de llamadas (CQD)</span><span class="sxs-lookup"><span data-stu-id="6f020-104">User Settings Service for Call Quality Dashboard (CQD)</span></span>
 
<span data-ttu-id="6f020-105">**Resumen:** Obtenga más información sobre el servicio de configuración de usuario, que es parte de la API del repositorio para el panel de calidad de llamadas.</span><span class="sxs-lookup"><span data-stu-id="6f020-105">**Summary:** Learn about the User Settings Service, which is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="6f020-106">El panel de calidad de llamadas es una herramienta para Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="6f020-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="6f020-107">El servicio de configuración de usuario es parte de la API del repositorio para el panel de calidad de llamadas.</span><span class="sxs-lookup"><span data-stu-id="6f020-107">The User Settings Service is part of the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="user-settings-service"></a><span data-ttu-id="6f020-108">Servicio de configuración de usuario</span><span class="sxs-lookup"><span data-stu-id="6f020-108">User Settings Service</span></span>

<span data-ttu-id="6f020-109">La configuración de usuario son pares clave-valor que las aplicaciones pueden usar para almacenar metadatos con diversos fines, entre ellos, la personalización de los comportamientos de la aplicación por usuario.</span><span class="sxs-lookup"><span data-stu-id="6f020-109">User settings are key-value pairs that applications can use to store metadata for various purposes including customization of application behaviors per-user basis.</span></span> <span data-ttu-id="6f020-110">Cada usuario recibe un almacenamiento para la configuración de usuario.</span><span class="sxs-lookup"><span data-stu-id="6f020-110">Each user receives a storage for user settings.</span></span> <span data-ttu-id="6f020-111">Solo los propietarios pueden agregar, modificar y quitar configuraciones de usuario.</span><span class="sxs-lookup"><span data-stu-id="6f020-111">Only the owners can add, modify, and remove user settings.</span></span>
  
 <span data-ttu-id="6f020-112">**Configuración global**</span><span class="sxs-lookup"><span data-stu-id="6f020-112">**Global Settings**</span></span>
  
<span data-ttu-id="6f020-113">Configuración global es la configuración del usuario propiedad del usuario del sistema y todos los usuarios tienen acceso de solo lectura a ellos.</span><span class="sxs-lookup"><span data-stu-id="6f020-113">Global settings are the user settings owned by the system user, and all users have read-only access to them.</span></span> <span data-ttu-id="6f020-114">La configuración global es constante: se crean durante la creación del repositorio y nunca cambian.</span><span class="sxs-lookup"><span data-stu-id="6f020-114">Global settings are constants: they are created during the repository creation, and they never change.</span></span>
  
<span data-ttu-id="6f020-115">Cada usuario puede invalidar la configuración global creando la configuración de usuario con las mismas claves.</span><span class="sxs-lookup"><span data-stu-id="6f020-115">Each user can override global settings by creating user settings with the same keys.</span></span> <span data-ttu-id="6f020-116">Cuando la aplicación solicita la configuración de usuario efectiva, la API devuelve un conjunto de opciones de configuración global combinadas con la configuración de usuario, con cada configuración de usuario que reemplaza la configuración global correspondiente si las claves son las mismas.</span><span class="sxs-lookup"><span data-stu-id="6f020-116">When application requests the effective user settings, the API returns a set of global settings merged with the user settings, with each user setting superseding the respective global setting if keys are the same.</span></span> <span data-ttu-id="6f020-117">La API también puede devolver solo la configuración de usuario para que las aplicaciones puedan averiguar qué opciones de configuración se reemplazan.</span><span class="sxs-lookup"><span data-stu-id="6f020-117">The API can also return just the user settings so that applications can find out which settings are overridden.</span></span> 
  
<span data-ttu-id="6f020-118">Las operaciones de REST se incluyen en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="6f020-118">The REST operations are included in the following table.</span></span>

|<span data-ttu-id="6f020-119">**Operación**</span><span class="sxs-lookup"><span data-stu-id="6f020-119">**Operation**</span></span>|<span data-ttu-id="6f020-120">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="6f020-120">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="6f020-121">Obtener configuración de usuario</span><span class="sxs-lookup"><span data-stu-id="6f020-121">Get User Settings</span></span>](get-user-settings.md) <br/> |<span data-ttu-id="6f020-122">Obtener configuración de usuario devuelve una lista de opciones de configuración para un usuario especificado.</span><span class="sxs-lookup"><span data-stu-id="6f020-122">Get User Settings returns a list of settings for a specified user.</span></span>  <br/> |
|[<span data-ttu-id="6f020-123">Obtener configuración de usuario</span><span class="sxs-lookup"><span data-stu-id="6f020-123">Get User Setting</span></span>](get-user-setting.md) <br/> |<span data-ttu-id="6f020-124">Obtener configuración de usuario devuelve la configuración de un solo usuario.</span><span class="sxs-lookup"><span data-stu-id="6f020-124">Get User Setting returns a single user setting.</span></span>  <br/> |
   

