---
title: Servicio de configuración de usuario para el panel de calidad de la llamada (CQD)
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/18/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: eafeb54a-2574-415b-b991-a0ff0470d8c3
description: 'Resumen: Conozca el servicio de configuración de usuario, que forma parte de la API de repositorio para llamar al panel de calidad. Panel de calidad de la llamada es una herramienta de Skype para Business Server 2015.'
ms.openlocfilehash: fe51c96546903e09f28ffadf06451efc8c1a88b0
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="user-settings-service-for-call-quality-dashboard-cqd"></a><span data-ttu-id="504d2-104">Servicio de configuración de usuario para el panel de calidad de la llamada (CQD)</span><span class="sxs-lookup"><span data-stu-id="504d2-104">User Settings Service for Call Quality Dashboard (CQD)</span></span>
 
<span data-ttu-id="504d2-105">**Resumen:** Obtener información sobre el servicio de configuración de usuario, que forma parte de la API de repositorio para llamar al panel de calidad.</span><span class="sxs-lookup"><span data-stu-id="504d2-105">**Summary:** Learn about the User Settings Service, which is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="504d2-106">Panel de calidad de la llamada es una herramienta de Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="504d2-106">Call Quality Dashboard is a tool for Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="504d2-107">El servicio de configuración de usuario es parte de la API de repositorio para llamar al panel de calidad.</span><span class="sxs-lookup"><span data-stu-id="504d2-107">The User Settings Service is part of the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="user-settings-service"></a><span data-ttu-id="504d2-108">Servicio de configuración de usuario</span><span class="sxs-lookup"><span data-stu-id="504d2-108">User Settings Service</span></span>

<span data-ttu-id="504d2-109">Configuración de usuario es pares de clave y valor que las aplicaciones pueden utilizar para almacenar metadatos para diversos fines, como la personalización de cada usuario de comportamientos de aplicación.</span><span class="sxs-lookup"><span data-stu-id="504d2-109">User settings are key-value pairs that applications can use to store metadata for various purposes including customization of application behaviors per-user basis.</span></span> <span data-ttu-id="504d2-110">Cada usuario recibe un almacenamiento de información para la configuración de usuario.</span><span class="sxs-lookup"><span data-stu-id="504d2-110">Each user receives a storage for user settings.</span></span> <span data-ttu-id="504d2-111">Sólo los propietarios pueden agregar, modificar y quitar la configuración de usuario.</span><span class="sxs-lookup"><span data-stu-id="504d2-111">Only the owners can add, modify, and remove user settings.</span></span>
  
 <span data-ttu-id="504d2-112">**Configuración global**</span><span class="sxs-lookup"><span data-stu-id="504d2-112">**Global Settings**</span></span>
  
<span data-ttu-id="504d2-113">Configuración global es la configuración de usuario que pertenecen al usuario del sistema y todos los usuarios tienen acceso de sólo lectura a ellos.</span><span class="sxs-lookup"><span data-stu-id="504d2-113">Global settings are the user settings owned by the system user, and all users have read-only access to them.</span></span> <span data-ttu-id="504d2-114">Configuración global es constantes: se crean durante la creación del repositorio y nunca cambian.</span><span class="sxs-lookup"><span data-stu-id="504d2-114">Global settings are constants: they are created during the repository creation, and they never change.</span></span>
  
<span data-ttu-id="504d2-115">Cada usuario puede reemplazar la configuración global mediante la creación de configuraciones de usuario con las mismas claves.</span><span class="sxs-lookup"><span data-stu-id="504d2-115">Each user can override global settings by creating user settings with the same keys.</span></span> <span data-ttu-id="504d2-116">Cuando la aplicación solicita la configuración de usuario eficaces, la API devuelve un conjunto de configuración global que se combina con la configuración de usuario, con cada configuración de usuario el reemplazo de la respectiva configuración global si las claves son iguales.</span><span class="sxs-lookup"><span data-stu-id="504d2-116">When application requests the effective user settings, the API returns a set of global settings merged with the user settings, with each user setting superseding the respective global setting if keys are the same.</span></span> <span data-ttu-id="504d2-117">La API también puede devolver la configuración del usuario para que las aplicaciones pueden averiguar qué valores prevalecen.</span><span class="sxs-lookup"><span data-stu-id="504d2-117">The API can also return just the user settings so that applications can find out which settings are overridden.</span></span> 
  
<span data-ttu-id="504d2-118">Las operaciones de resto se incluyen en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="504d2-118">The REST operations are included in the following table.</span></span>

|<span data-ttu-id="504d2-119">**Operación**</span><span class="sxs-lookup"><span data-stu-id="504d2-119">**Operation**</span></span>|<span data-ttu-id="504d2-120">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="504d2-120">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="504d2-121">Obtener la configuración de usuario</span><span class="sxs-lookup"><span data-stu-id="504d2-121">Get User Settings</span></span>](get-user-settings.md) <br/> |<span data-ttu-id="504d2-122">Configuración de usuario de Get devuelve una lista de valores para un usuario especificado.</span><span class="sxs-lookup"><span data-stu-id="504d2-122">Get User Settings returns a list of settings for a specified user.</span></span>  <br/> |
|[<span data-ttu-id="504d2-123">Obtener la configuración de usuario</span><span class="sxs-lookup"><span data-stu-id="504d2-123">Get User Setting</span></span>](get-user-setting.md) <br/> |<span data-ttu-id="504d2-124">Obtener configuración de usuario devuelve un entorno de usuario único.</span><span class="sxs-lookup"><span data-stu-id="504d2-124">Get User Setting returns a single user setting.</span></span>  <br/> |
   

