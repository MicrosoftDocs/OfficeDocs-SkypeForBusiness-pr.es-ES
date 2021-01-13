---
title: Servicio de configuración de usuario para el Panel de calidad de llamadas (CQD)
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: eafeb54a-2574-415b-b991-a0ff0470d8c3
description: 'Resumen: obtenga información sobre el servicio de configuración de usuario, que forma parte de la API de repositorio para el panel de calidad de llamadas. El Panel de calidad de llamadas es una herramienta para Skype Empresarial Server.'
ms.openlocfilehash: 2b2fc9810f1eceb74974dc105263b0bdcf37ae01
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49803041"
---
# <a name="user-settings-service-for-call-quality-dashboard-cqd"></a><span data-ttu-id="d0d4b-104">Servicio de configuración de usuario para el Panel de calidad de llamadas (CQD)</span><span class="sxs-lookup"><span data-stu-id="d0d4b-104">User Settings Service for Call Quality Dashboard (CQD)</span></span>
 
<span data-ttu-id="d0d4b-105">**Resumen:** Obtenga información sobre el Servicio de configuración de usuario, que forma parte de la API de repositorio para el Panel de calidad de llamadas.</span><span class="sxs-lookup"><span data-stu-id="d0d4b-105">**Summary:** Learn about the User Settings Service, which is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="d0d4b-106">El Panel de calidad de llamadas es una herramienta para Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="d0d4b-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="d0d4b-107">El servicio de configuración de usuario forma parte de la API de repositorio para el panel de calidad de llamadas.</span><span class="sxs-lookup"><span data-stu-id="d0d4b-107">The User Settings Service is part of the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="user-settings-service"></a><span data-ttu-id="d0d4b-108">Servicio de configuración de usuario</span><span class="sxs-lookup"><span data-stu-id="d0d4b-108">User Settings Service</span></span>

<span data-ttu-id="d0d4b-109">La configuración de usuario son pares clave-valor que las aplicaciones pueden usar para almacenar metadatos con diversos fines, incluida la personalización de comportamientos de aplicación por usuario.</span><span class="sxs-lookup"><span data-stu-id="d0d4b-109">User settings are key-value pairs that applications can use to store metadata for various purposes including customization of application behaviors per-user basis.</span></span> <span data-ttu-id="d0d4b-110">Cada usuario recibe un almacenamiento para la configuración de usuario.</span><span class="sxs-lookup"><span data-stu-id="d0d4b-110">Each user receives a storage for user settings.</span></span> <span data-ttu-id="d0d4b-111">Solo los propietarios pueden agregar, modificar y quitar la configuración de usuario.</span><span class="sxs-lookup"><span data-stu-id="d0d4b-111">Only the owners can add, modify, and remove user settings.</span></span>
  
 <span data-ttu-id="d0d4b-112">**Configuración global**</span><span class="sxs-lookup"><span data-stu-id="d0d4b-112">**Global Settings**</span></span>
  
<span data-ttu-id="d0d4b-113">La configuración global es la configuración de usuario propiedad del usuario del sistema y todos los usuarios tienen acceso de solo lectura a ellos.</span><span class="sxs-lookup"><span data-stu-id="d0d4b-113">Global settings are the user settings owned by the system user, and all users have read-only access to them.</span></span> <span data-ttu-id="d0d4b-114">La configuración global son constantes: se crean durante la creación del repositorio y nunca cambian.</span><span class="sxs-lookup"><span data-stu-id="d0d4b-114">Global settings are constants: they are created during the repository creation, and they never change.</span></span>
  
<span data-ttu-id="d0d4b-115">Cada usuario puede invalidar la configuración global mediante la creación de configuraciones de usuario con las mismas claves.</span><span class="sxs-lookup"><span data-stu-id="d0d4b-115">Each user can override global settings by creating user settings with the same keys.</span></span> <span data-ttu-id="d0d4b-116">Cuando la aplicación solicita la configuración de usuario efectiva, la API devuelve un conjunto de configuraciones globales combinadas con la configuración de usuario, con cada configuración de usuario supersedando la configuración global respectiva si las claves son las mismas.</span><span class="sxs-lookup"><span data-stu-id="d0d4b-116">When application requests the effective user settings, the API returns a set of global settings merged with the user settings, with each user setting superseding the respective global setting if keys are the same.</span></span> <span data-ttu-id="d0d4b-117">La API también puede devolver solo la configuración de usuario para que las aplicaciones puedan averiguar qué configuración se reemplaza.</span><span class="sxs-lookup"><span data-stu-id="d0d4b-117">The API can also return just the user settings so that applications can find out which settings are overridden.</span></span> 
  
<span data-ttu-id="d0d4b-118">Las operaciones rest se incluyen en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="d0d4b-118">The REST operations are included in the following table.</span></span>

|<span data-ttu-id="d0d4b-119">**Operación**</span><span class="sxs-lookup"><span data-stu-id="d0d4b-119">**Operation**</span></span>|<span data-ttu-id="d0d4b-120">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="d0d4b-120">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="d0d4b-121">Obtener configuración de usuario</span><span class="sxs-lookup"><span data-stu-id="d0d4b-121">Get User Settings</span></span>](get-user-settings.md) <br/> |<span data-ttu-id="d0d4b-122">Obtener configuración de usuario devuelve una lista de configuraciones para un usuario especificado.</span><span class="sxs-lookup"><span data-stu-id="d0d4b-122">Get User Settings returns a list of settings for a specified user.</span></span>  <br/> |
|[<span data-ttu-id="d0d4b-123">Obtener configuración de usuario</span><span class="sxs-lookup"><span data-stu-id="d0d4b-123">Get User Setting</span></span>](get-user-setting.md) <br/> |<span data-ttu-id="d0d4b-124">Obtener configuración de usuario devuelve una configuración de usuario único.</span><span class="sxs-lookup"><span data-stu-id="d0d4b-124">Get User Setting returns a single user setting.</span></span>  <br/> |
   

