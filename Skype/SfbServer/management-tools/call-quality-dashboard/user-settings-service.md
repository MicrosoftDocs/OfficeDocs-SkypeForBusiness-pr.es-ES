---
title: Servicio de configuración de usuario para el panel de calidad de llamada (CQD)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: eafeb54a-2574-415b-b991-a0ff0470d8c3
description: 'Resumen: Información sobre el servicio de configuración de usuario, que forma parte de la API de repositorio para llamar al panel de calidad. Panel de calidad de llamada es una herramienta de Skype para Business Server.'
ms.openlocfilehash: ae87fcb28babbe3d9a480092d73e9c4cad2e1a76
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33914999"
---
# <a name="user-settings-service-for-call-quality-dashboard-cqd"></a><span data-ttu-id="3e75a-104">Servicio de configuración de usuario para el panel de calidad de llamada (CQD)</span><span class="sxs-lookup"><span data-stu-id="3e75a-104">User Settings Service for Call Quality Dashboard (CQD)</span></span>
 
<span data-ttu-id="3e75a-105">**Resumen:** Obtenga información sobre el servicio de configuración de usuario, que forma parte de la API de repositorio para llamar al panel de calidad.</span><span class="sxs-lookup"><span data-stu-id="3e75a-105">**Summary:** Learn about the User Settings Service, which is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="3e75a-106">Panel de calidad de llamada es una herramienta de Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="3e75a-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="3e75a-107">El servicio de configuración de usuario es parte de la API de repositorio para llamar al panel de calidad.</span><span class="sxs-lookup"><span data-stu-id="3e75a-107">The User Settings Service is part of the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="user-settings-service"></a><span data-ttu-id="3e75a-108">Servicio de configuración de usuario</span><span class="sxs-lookup"><span data-stu-id="3e75a-108">User Settings Service</span></span>

<span data-ttu-id="3e75a-109">Configuración de usuario es pares de clave y valor que las aplicaciones pueden usar para almacenar metadatos para diversos fines, como la personalización de nivel de aplicación comportamientos de usuario.</span><span class="sxs-lookup"><span data-stu-id="3e75a-109">User settings are key-value pairs that applications can use to store metadata for various purposes including customization of application behaviors per-user basis.</span></span> <span data-ttu-id="3e75a-110">Cada usuario recibe un almacenamiento de información para la configuración de usuario.</span><span class="sxs-lookup"><span data-stu-id="3e75a-110">Each user receives a storage for user settings.</span></span> <span data-ttu-id="3e75a-111">Sólo los propietarios pueden agregar, modificar y quitar la configuración de usuario.</span><span class="sxs-lookup"><span data-stu-id="3e75a-111">Only the owners can add, modify, and remove user settings.</span></span>
  
 <span data-ttu-id="3e75a-112">**Configuración global**</span><span class="sxs-lookup"><span data-stu-id="3e75a-112">**Global Settings**</span></span>
  
<span data-ttu-id="3e75a-113">La configuración global es la configuración de usuario que pertenecen al usuario del sistema y todos los usuarios tienen acceso de solo lectura a ellos.</span><span class="sxs-lookup"><span data-stu-id="3e75a-113">Global settings are the user settings owned by the system user, and all users have read-only access to them.</span></span> <span data-ttu-id="3e75a-114">La configuración global es constantes: se crean durante la creación de repositorio, y se debe cambiar nunca.</span><span class="sxs-lookup"><span data-stu-id="3e75a-114">Global settings are constants: they are created during the repository creation, and they never change.</span></span>
  
<span data-ttu-id="3e75a-115">Cada usuario puede invalidar la configuración global mediante la creación de configuración de usuario con las mismas claves.</span><span class="sxs-lookup"><span data-stu-id="3e75a-115">Each user can override global settings by creating user settings with the same keys.</span></span> <span data-ttu-id="3e75a-116">Cuando la aplicación solicita la configuración de usuario eficaz, la API devuelve un conjunto de configuración global que se combina con la configuración de usuario, con cada opción de usuario el reemplazo de la correspondiente configuración global si las claves son las mismas.</span><span class="sxs-lookup"><span data-stu-id="3e75a-116">When application requests the effective user settings, the API returns a set of global settings merged with the user settings, with each user setting superseding the respective global setting if keys are the same.</span></span> <span data-ttu-id="3e75a-117">La API también puede devolver la configuración del usuario para que las aplicaciones pueden averiguar se reemplazan los valores de configuración.</span><span class="sxs-lookup"><span data-stu-id="3e75a-117">The API can also return just the user settings so that applications can find out which settings are overridden.</span></span> 
  
<span data-ttu-id="3e75a-118">Las operaciones de REST se incluyen en la siguiente tabla.</span><span class="sxs-lookup"><span data-stu-id="3e75a-118">The REST operations are included in the following table.</span></span>

|<span data-ttu-id="3e75a-119">**Operación**</span><span class="sxs-lookup"><span data-stu-id="3e75a-119">**Operation**</span></span>|<span data-ttu-id="3e75a-120">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="3e75a-120">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="3e75a-121">Obtener configuración de usuario</span><span class="sxs-lookup"><span data-stu-id="3e75a-121">Get User Settings</span></span>](get-user-settings.md) <br/> |<span data-ttu-id="3e75a-122">Configuración del usuario Get devuelve una lista de valores para un usuario especificado.</span><span class="sxs-lookup"><span data-stu-id="3e75a-122">Get User Settings returns a list of settings for a specified user.</span></span>  <br/> |
|[<span data-ttu-id="3e75a-123">Obtener configuración de usuario</span><span class="sxs-lookup"><span data-stu-id="3e75a-123">Get User Setting</span></span>](get-user-setting.md) <br/> |<span data-ttu-id="3e75a-124">Obtener configuración de usuario devuelve una configuración de usuario único.</span><span class="sxs-lookup"><span data-stu-id="3e75a-124">Get User Setting returns a single user setting.</span></span>  <br/> |
   

