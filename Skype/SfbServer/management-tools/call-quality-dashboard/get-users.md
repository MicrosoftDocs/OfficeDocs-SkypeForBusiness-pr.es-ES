---
title: Obtener usuarios
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
ms.assetid: 87d34baf-4c31-468d-b8f7-4faca0bc7a54
description: 'Resumen: Obtenga información sobre la operación obtener usuarios, que forma parte del servicio de usuario. El servicio de usuario es parte de la API del repositorio para el panel de calidad de llamadas. El panel de calidad de llamadas es una herramienta para Skype empresarial Server.'
ms.openlocfilehash: 81d261a49798ef49d4a1d693681b4497652cf395
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816729"
---
# <a name="get-users"></a><span data-ttu-id="15874-105">Obtener usuarios</span><span class="sxs-lookup"><span data-stu-id="15874-105">Get Users</span></span>
 
<span data-ttu-id="15874-106">**Resumen:** Obtenga más información sobre la operación obtener usuarios, que es parte del servicio de usuario.</span><span class="sxs-lookup"><span data-stu-id="15874-106">**Summary:** Learn about the Get Users operation, which is part of the User Service.</span></span> <span data-ttu-id="15874-107">El servicio de usuario es parte de la API del repositorio para el panel de calidad de llamadas.</span><span class="sxs-lookup"><span data-stu-id="15874-107">The User Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="15874-108">El panel de calidad de llamadas es una herramienta para Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="15874-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="15874-109">La operación obtener usuarios forma parte del servicio de usuario en la API del repositorio para el panel de calidad de llamadas.</span><span class="sxs-lookup"><span data-stu-id="15874-109">The Get Users operation is part of the User Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-users"></a><span data-ttu-id="15874-110">Obtener usuarios</span><span class="sxs-lookup"><span data-stu-id="15874-110">Get Users</span></span>

<span data-ttu-id="15874-111">Obtener usuarios devuelve una lista de usuarios del repositorio.</span><span class="sxs-lookup"><span data-stu-id="15874-111">Get Users returns a list of users in the repository.</span></span>
  
|<span data-ttu-id="15874-112">**Método**</span><span class="sxs-lookup"><span data-stu-id="15874-112">**Method**</span></span>|<span data-ttu-id="15874-113">**Solicitar URI**</span><span class="sxs-lookup"><span data-stu-id="15874-113">**Request URI**</span></span>|<span data-ttu-id="15874-114">**Versión HTTP**</span><span class="sxs-lookup"><span data-stu-id="15874-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="15874-115">Obtener</span><span class="sxs-lookup"><span data-stu-id="15874-115">GET</span></span>  <br/> |<span data-ttu-id="15874-116">https://\<portal\>/QoERepositoryService/Repository/User</span><span class="sxs-lookup"><span data-stu-id="15874-116">https://\<portal\>/QoERepositoryService/repository/user</span></span>  <br/> |<span data-ttu-id="15874-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="15874-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="15874-118">**Parámetros de URI** : ninguno.</span><span class="sxs-lookup"><span data-stu-id="15874-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="15874-119">**Solicitar encabezados** : no hay encabezados adicionales.</span><span class="sxs-lookup"><span data-stu-id="15874-119">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="15874-120">**Solicitar cuerpo** : ninguno.</span><span class="sxs-lookup"><span data-stu-id="15874-120">**Request Body** - None.</span></span>
  
 <span data-ttu-id="15874-121">**Respuesta** : la respuesta incluye un código de estado http y un conjunto de encabezados de respuesta.</span><span class="sxs-lookup"><span data-stu-id="15874-121">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="15874-122">**Código de estado** : una operación correcta devuelve el código de estado 200 (correcto).</span><span class="sxs-lookup"><span data-stu-id="15874-122">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="15874-123">**Encabezados de respuesta** : no hay encabezados adicionales.</span><span class="sxs-lookup"><span data-stu-id="15874-123">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="15874-124">**Cuerpo de respuesta** : a continuación se muestra un ejemplo de carga de respuesta en JSON.</span><span class="sxs-lookup"><span data-stu-id="15874-124">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
> [!NOTE]
> <span data-ttu-id="15874-125">Se devuelve una matriz de objetos de usuario.</span><span class="sxs-lookup"><span data-stu-id="15874-125">An array of User objects is returned.</span></span> <span data-ttu-id="15874-126">Para obtener más información sobre el objeto de usuario, vea obtener usuario.</span><span class="sxs-lookup"><span data-stu-id="15874-126">For details about the User object, see Get User.</span></span> 
  
```json
[{
"userId": 0,
"loginName": "system",
"defaultItemId": 1652
},
{
"userId": 1,
"loginName": "SAMPLEDOMAIN\\testuser1",
"defaultItemId": 1652
},
{
"userId": 2,
"loginName": "SAMPLEDOMAIN\\testuser2",
"defaultItemId": 1774
}]
```


