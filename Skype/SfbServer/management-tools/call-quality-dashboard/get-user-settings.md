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
ms.assetid: bdfe063b-e808-4f3c-884a-acbbabb9be0a
description: 'Resumen: Conozca la operación de obtener la configuración de usuario, que es parte del servicio de configuración de usuario. El servicio de configuración de usuario es parte de la API de repositorio para llamar al panel de calidad. Panel de calidad de la llamada es una herramienta de Skype para Business Server 2015.'
ms.openlocfilehash: 55c3247f0412a9ce10927496ee65255129edfd93
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="get-user-settings"></a><span data-ttu-id="383c3-105">Obtener la configuración de usuario</span><span class="sxs-lookup"><span data-stu-id="383c3-105">Get User Settings</span></span>
 
<span data-ttu-id="383c3-106">**Resumen:** Obtener información sobre la operación de obtener la configuración de usuario, que es parte del servicio de configuración de usuario.</span><span class="sxs-lookup"><span data-stu-id="383c3-106">**Summary:** Learn about the Get User Settings operation, which is part of the User Settings Service.</span></span> <span data-ttu-id="383c3-107">El servicio de configuración de usuario es parte de la API de repositorio para llamar al panel de calidad.</span><span class="sxs-lookup"><span data-stu-id="383c3-107">The User Settings Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="383c3-108">Panel de calidad de la llamada es una herramienta de Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="383c3-108">Call Quality Dashboard is a tool for Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="383c3-109">La operación de obtener la configuración de usuario es parte del servicio de configuración de usuario en la API de repositorio para llamar al panel de calidad.</span><span class="sxs-lookup"><span data-stu-id="383c3-109">The Get User Settings operation is part of the User Settings Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-user-settings"></a><span data-ttu-id="383c3-110">Obtener la configuración de usuario</span><span class="sxs-lookup"><span data-stu-id="383c3-110">Get User Settings</span></span>

<span data-ttu-id="383c3-111">Configuración de usuario de Get devuelve una lista de valores para un usuario especificado.</span><span class="sxs-lookup"><span data-stu-id="383c3-111">Get User Settings returns a list of settings for a specified user.</span></span>
  

|<span data-ttu-id="383c3-112">**Método**</span><span class="sxs-lookup"><span data-stu-id="383c3-112">**Method**</span></span>|<span data-ttu-id="383c3-113">**URI de la solicitud**</span><span class="sxs-lookup"><span data-stu-id="383c3-113">**Request URI**</span></span>|<span data-ttu-id="383c3-114">**Versión de HTTP**</span><span class="sxs-lookup"><span data-stu-id="383c3-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="383c3-115">Obtener</span><span class="sxs-lookup"><span data-stu-id="383c3-115">GET</span></span>  <br/> |<span data-ttu-id="383c3-116">https://\<portal\>/QoERepositoryService/repository/usuario / {ID} / configuración</span><span class="sxs-lookup"><span data-stu-id="383c3-116">https://\<portal\>/QoERepositoryService/repository/user/{userId}/setting</span></span>  <br/> |<span data-ttu-id="383c3-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="383c3-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="383c3-118">**Parámetros del URI**</span><span class="sxs-lookup"><span data-stu-id="383c3-118">**URI Parameters**</span></span>
  
-  <span data-ttu-id="383c3-119">*efectivo* : opcional.</span><span class="sxs-lookup"><span data-stu-id="383c3-119">*effective*  - Optional.</span></span> <span data-ttu-id="383c3-120">Este parámetro aplica únicamente cuando se utiliza el valor predeterminado de ID de usuario especial.</span><span class="sxs-lookup"><span data-stu-id="383c3-120">This parameter applies only when the special user ID default is used.</span></span> <span data-ttu-id="383c3-121">En otros casos, se omitirá.</span><span class="sxs-lookup"><span data-stu-id="383c3-121">In other cases, it will be ignored.</span></span> <span data-ttu-id="383c3-122">`True`Devuelve la configuración de usuario eficaz y `false` devuelve la configuración del usuario (predeterminado).</span><span class="sxs-lookup"><span data-stu-id="383c3-122">`True` returns effective user settings and `false` returns just user settings (default).</span></span>
    
 <span data-ttu-id="383c3-123">**Encabezados de solicitud** - sin encabezados adicionales.</span><span class="sxs-lookup"><span data-stu-id="383c3-123">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="383c3-124">**Cuerpo de la solicitud** - ninguno.</span><span class="sxs-lookup"><span data-stu-id="383c3-124">**Request Body** - None.</span></span>
  
 <span data-ttu-id="383c3-125">**Respuesta** : la respuesta incluye un código de estado HTTP y un conjunto de encabezados de respuesta.</span><span class="sxs-lookup"><span data-stu-id="383c3-125">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="383c3-126">**Código de estado** - una operación correcta devuelve el código de estado 200 (OK).</span><span class="sxs-lookup"><span data-stu-id="383c3-126">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="383c3-127">**Encabezados de respuesta** - sin encabezados adicionales.</span><span class="sxs-lookup"><span data-stu-id="383c3-127">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="383c3-128">**Cuerpo de la respuesta** : a continuación es una carga de respuesta de ejemplo en JSON.</span><span class="sxs-lookup"><span data-stu-id="383c3-128">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
```
[{
"userId": 6,
"key": "ShowDescriptions",
"value": "true"
},
{
"userId": 6,
"key": "ShowTimeStamps",
"value": "true"
}]

```


