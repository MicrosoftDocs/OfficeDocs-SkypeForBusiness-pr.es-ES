---
title: Obtener configuración de usuario
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: bdfe063b-e808-4f3c-884a-acbbabb9be0a
description: 'Resumen: Obtenga información sobre la operación obtener configuración de usuario, que es parte del servicio de configuración de usuario. El servicio de configuración de usuario es parte de la API del repositorio para el panel de calidad de llamadas. El panel de calidad de llamadas es una herramienta para Skype empresarial Server.'
ms.openlocfilehash: 5b5ad679387866ba6562e031b6d3a42cc68851a0
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816749"
---
# <a name="get-user-settings"></a><span data-ttu-id="e66cf-105">Obtener configuración de usuario</span><span class="sxs-lookup"><span data-stu-id="e66cf-105">Get User Settings</span></span>
 
<span data-ttu-id="e66cf-106">**Resumen:** Obtenga más información sobre la operación obtener configuración del usuario, que es parte del servicio de configuración de usuario.</span><span class="sxs-lookup"><span data-stu-id="e66cf-106">**Summary:** Learn about the Get User Settings operation, which is part of the User Settings Service.</span></span> <span data-ttu-id="e66cf-107">El servicio de configuración de usuario es parte de la API del repositorio para el panel de calidad de llamadas.</span><span class="sxs-lookup"><span data-stu-id="e66cf-107">The User Settings Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="e66cf-108">El panel de calidad de llamadas es una herramienta para Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="e66cf-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="e66cf-109">La operación obtener configuración del usuario es parte del servicio de configuración de usuario en la API del repositorio para el panel de calidad de llamadas.</span><span class="sxs-lookup"><span data-stu-id="e66cf-109">The Get User Settings operation is part of the User Settings Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-user-settings"></a><span data-ttu-id="e66cf-110">Obtener configuración de usuario</span><span class="sxs-lookup"><span data-stu-id="e66cf-110">Get User Settings</span></span>

<span data-ttu-id="e66cf-111">Obtener configuración de usuario devuelve una lista de opciones de configuración para un usuario especificado.</span><span class="sxs-lookup"><span data-stu-id="e66cf-111">Get User Settings returns a list of settings for a specified user.</span></span>
  

|<span data-ttu-id="e66cf-112">**Método**</span><span class="sxs-lookup"><span data-stu-id="e66cf-112">**Method**</span></span>|<span data-ttu-id="e66cf-113">**Solicitar URI**</span><span class="sxs-lookup"><span data-stu-id="e66cf-113">**Request URI**</span></span>|<span data-ttu-id="e66cf-114">**Versión HTTP**</span><span class="sxs-lookup"><span data-stu-id="e66cf-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="e66cf-115">Obtener</span><span class="sxs-lookup"><span data-stu-id="e66cf-115">GET</span></span>  <br/> |<span data-ttu-id="e66cf-116">https://\<portal\>/QoERepositoryService/Repository/User/{userId}/setting</span><span class="sxs-lookup"><span data-stu-id="e66cf-116">https://\<portal\>/QoERepositoryService/repository/user/{userId}/setting</span></span>  <br/> |<span data-ttu-id="e66cf-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="e66cf-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="e66cf-118">**Parámetros de URI**</span><span class="sxs-lookup"><span data-stu-id="e66cf-118">**URI Parameters**</span></span>
  
- <span data-ttu-id="e66cf-119">*eficaz* : opcional.</span><span class="sxs-lookup"><span data-stu-id="e66cf-119">*effective*  - Optional.</span></span> <span data-ttu-id="e66cf-120">Este parámetro solo se aplica cuando se usa el identificador de usuario especial predeterminado.</span><span class="sxs-lookup"><span data-stu-id="e66cf-120">This parameter applies only when the special user ID default is used.</span></span> <span data-ttu-id="e66cf-121">En otros casos, se omitirá.</span><span class="sxs-lookup"><span data-stu-id="e66cf-121">In other cases, it will be ignored.</span></span> <span data-ttu-id="e66cf-122">`True`Devuelve la configuración de usuario `false` eficaz y devuelve solo la configuración del usuario (valor predeterminado).</span><span class="sxs-lookup"><span data-stu-id="e66cf-122">`True` returns effective user settings and `false` returns just user settings (default).</span></span>
    
  <span data-ttu-id="e66cf-123">**Solicitar encabezados** : no hay encabezados adicionales.</span><span class="sxs-lookup"><span data-stu-id="e66cf-123">**Request Headers** - No additional headers.</span></span>
  
  <span data-ttu-id="e66cf-124">**Solicitar cuerpo** : ninguno.</span><span class="sxs-lookup"><span data-stu-id="e66cf-124">**Request Body** - None.</span></span>
  
  <span data-ttu-id="e66cf-125">**Respuesta** : la respuesta incluye un código de estado http y un conjunto de encabezados de respuesta.</span><span class="sxs-lookup"><span data-stu-id="e66cf-125">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
  <span data-ttu-id="e66cf-126">**Código de estado** : una operación correcta devuelve el código de estado 200 (correcto).</span><span class="sxs-lookup"><span data-stu-id="e66cf-126">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
  <span data-ttu-id="e66cf-127">**Encabezados de respuesta** : no hay encabezados adicionales.</span><span class="sxs-lookup"><span data-stu-id="e66cf-127">**Response Headers** - No additional headers.</span></span>
  
  <span data-ttu-id="e66cf-128">**Cuerpo de respuesta** : a continuación se muestra un ejemplo de carga de respuesta en JSON.</span><span class="sxs-lookup"><span data-stu-id="e66cf-128">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
```json
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
