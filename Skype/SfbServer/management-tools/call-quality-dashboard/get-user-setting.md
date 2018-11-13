---
title: Obtener la configuración de usuario
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/18/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 16611a55-79fb-487a-a936-20caca829f87
description: 'Resumen: Obtenga información acerca de la operación de obtener la configuración de usuario, que es parte del servicio de configuración de usuario. El servicio de configuración de usuario es parte de la API de repositorio para llamar al panel de calidad. Panel de calidad de llamada es una herramienta de Skype para Business Server 2015.'
ms.openlocfilehash: a839045197e8b72f72a99fd5fb6e3cf0a724b342
ms.sourcegitcommit: 1cb5a3570032250aecd5a1a839cbbe4daeb77f2c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/13/2018
ms.locfileid: "26296092"
---
# <a name="get-user-setting"></a><span data-ttu-id="afd0d-105">Obtener la configuración de usuario</span><span class="sxs-lookup"><span data-stu-id="afd0d-105">Get User Setting</span></span>
 
<span data-ttu-id="afd0d-106">**Resumen:** Obtenga información acerca de la operación de obtener la configuración de usuario, que es parte del servicio de configuración de usuario.</span><span class="sxs-lookup"><span data-stu-id="afd0d-106">**Summary:** Learn about the Get User Setting operation, which is part of the User Settings Service.</span></span> <span data-ttu-id="afd0d-107">El servicio de configuración de usuario es parte de la API de repositorio para llamar al panel de calidad.</span><span class="sxs-lookup"><span data-stu-id="afd0d-107">The User Settings Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="afd0d-108">Panel de calidad de llamada es una herramienta de Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="afd0d-108">Call Quality Dashboard is a tool for Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="afd0d-109">La operación de obtener la configuración de usuario es parte del servicio de configuración de usuario de la API de repositorio para llamar al panel de calidad.</span><span class="sxs-lookup"><span data-stu-id="afd0d-109">The Get User Setting operation is part of the User Settings Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-user-setting"></a><span data-ttu-id="afd0d-110">Obtener la configuración de usuario</span><span class="sxs-lookup"><span data-stu-id="afd0d-110">Get User Setting</span></span>

<span data-ttu-id="afd0d-111">Obtener configuración de usuario devuelve una configuración de usuario único.</span><span class="sxs-lookup"><span data-stu-id="afd0d-111">Get User Setting returns a single user setting.</span></span>
  

|<span data-ttu-id="afd0d-112">**(Método)**</span><span class="sxs-lookup"><span data-stu-id="afd0d-112">**Method**</span></span>|<span data-ttu-id="afd0d-113">**URI de la solicitud**</span><span class="sxs-lookup"><span data-stu-id="afd0d-113">**Request URI**</span></span>|<span data-ttu-id="afd0d-114">**Versión de HTTP**</span><span class="sxs-lookup"><span data-stu-id="afd0d-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="afd0d-115">Obtener</span><span class="sxs-lookup"><span data-stu-id="afd0d-115">GET</span></span>  <br/> |<span data-ttu-id="afd0d-116">https://\<portal\>/QoERepositoryService/repositorio/usuario / {userId} /setting/ {clave}</span><span class="sxs-lookup"><span data-stu-id="afd0d-116">https://\<portal\>/QoERepositoryService/repository/user/{userId}/setting/{key}</span></span>  <br/> |<span data-ttu-id="afd0d-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="afd0d-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="afd0d-118">**Los parámetros URI** - ninguno.</span><span class="sxs-lookup"><span data-stu-id="afd0d-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="afd0d-119">**Encabezados de solicitud** - sin encabezados adicionales.</span><span class="sxs-lookup"><span data-stu-id="afd0d-119">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="afd0d-120">**Cuerpo de la convocatoria** - ninguno.</span><span class="sxs-lookup"><span data-stu-id="afd0d-120">**Request Body** - None.</span></span>
  
 <span data-ttu-id="afd0d-121">**Respuesta** : la respuesta incluye un código de estado HTTP y un conjunto de encabezados de respuesta.</span><span class="sxs-lookup"><span data-stu-id="afd0d-121">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="afd0d-122">**Código de estado** - una operación correcta devuelve código de estado 200 (Aceptar).</span><span class="sxs-lookup"><span data-stu-id="afd0d-122">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="afd0d-123">**Encabezados de respuesta** - sin encabezados adicionales.</span><span class="sxs-lookup"><span data-stu-id="afd0d-123">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="afd0d-124">**Cuerpo de la respuesta** - a continuación es una carga de respuesta de ejemplo en JSON.</span><span class="sxs-lookup"><span data-stu-id="afd0d-124">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
```
{
"userId": 6,
"key": "ShowDescriptions",
"value": "true"
}
```

 <span data-ttu-id="afd0d-125">*userId* : identificador del usuario.</span><span class="sxs-lookup"><span data-stu-id="afd0d-125">*userId*  - ID of the user.</span></span>
  
 <span data-ttu-id="afd0d-126">*clave* : clave de la configuración.</span><span class="sxs-lookup"><span data-stu-id="afd0d-126">*key*  - Key of the setting.</span></span>
  
 <span data-ttu-id="afd0d-127">*valor* : valor de la opción.</span><span class="sxs-lookup"><span data-stu-id="afd0d-127">*value*  - Value of the setting.</span></span>
  

