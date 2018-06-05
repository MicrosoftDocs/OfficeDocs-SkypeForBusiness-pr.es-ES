---
title: Obtención de usuarios
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/18/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 87d34baf-4c31-468d-b8f7-4faca0bc7a54
description: 'Resumen: Obtenga información acerca de la operación obtener los usuarios, que es parte del servicio de usuario. El servicio de usuario es parte de la API de repositorio para llamar al panel de calidad. Panel de calidad de llamada es una herramienta de Skype para Business Server 2015.'
ms.openlocfilehash: 4d4de424776514479ed2204eeb0a5315a7323662
ms.sourcegitcommit: a79668bb45b73a63bea5c249d76a4c4c2530a096
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/05/2018
ms.locfileid: "19569701"
---
# <a name="get-users"></a><span data-ttu-id="7a687-105">Obtención de usuarios</span><span class="sxs-lookup"><span data-stu-id="7a687-105">Get Users</span></span>
 
<span data-ttu-id="7a687-106">**Resumen:** Obtenga información acerca de la operación obtener los usuarios, que es parte del servicio de usuario.</span><span class="sxs-lookup"><span data-stu-id="7a687-106">**Summary:** Learn about the Get Users operation, which is part of the User Service.</span></span> <span data-ttu-id="7a687-107">El servicio de usuario es parte de la API de repositorio para llamar al panel de calidad.</span><span class="sxs-lookup"><span data-stu-id="7a687-107">The User Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="7a687-108">Panel de calidad de llamada es una herramienta de Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="7a687-108">Call Quality Dashboard is a tool for Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="7a687-109">La operación de obtener los usuarios es parte del servicio de usuario de la API de repositorio para llamar al panel de calidad.</span><span class="sxs-lookup"><span data-stu-id="7a687-109">The Get Users operation is part of the User Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-users"></a><span data-ttu-id="7a687-110">Obtención de usuarios</span><span class="sxs-lookup"><span data-stu-id="7a687-110">Get Users</span></span>

<span data-ttu-id="7a687-111">Obtener una lista de los usuarios de devuelve los usuarios en el repositorio.</span><span class="sxs-lookup"><span data-stu-id="7a687-111">Get Users returns a list of users in the repository.</span></span>
  
|<span data-ttu-id="7a687-112">**(Método)**</span><span class="sxs-lookup"><span data-stu-id="7a687-112">**Method**</span></span>|<span data-ttu-id="7a687-113">**URI de la solicitud**</span><span class="sxs-lookup"><span data-stu-id="7a687-113">**Request URI**</span></span>|<span data-ttu-id="7a687-114">**Versión de HTTP**</span><span class="sxs-lookup"><span data-stu-id="7a687-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="7a687-115">Obtener</span><span class="sxs-lookup"><span data-stu-id="7a687-115">GET</span></span>  <br/> |<span data-ttu-id="7a687-116">https://\<portal\>/QoERepositoryService/repository/user</span><span class="sxs-lookup"><span data-stu-id="7a687-116">https://\<portal\>/QoERepositoryService/repository/user</span></span>  <br/> |<span data-ttu-id="7a687-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="7a687-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="7a687-118">**Los parámetros URI** - ninguno.</span><span class="sxs-lookup"><span data-stu-id="7a687-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="7a687-119">**Encabezados de solicitud** - sin encabezados adicionales.</span><span class="sxs-lookup"><span data-stu-id="7a687-119">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="7a687-120">**Cuerpo de la convocatoria** - ninguno.</span><span class="sxs-lookup"><span data-stu-id="7a687-120">**Request Body** - None.</span></span>
  
 <span data-ttu-id="7a687-121">**Respuesta** : la respuesta incluye un código de estado HTTP y un conjunto de encabezados de respuesta.</span><span class="sxs-lookup"><span data-stu-id="7a687-121">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="7a687-122">**Código de estado** - una operación correcta devuelve código de estado 200 (Aceptar).</span><span class="sxs-lookup"><span data-stu-id="7a687-122">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="7a687-123">**Encabezados de respuesta** - sin encabezados adicionales.</span><span class="sxs-lookup"><span data-stu-id="7a687-123">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="7a687-124">**Cuerpo de la respuesta** - a continuación es una carga de respuesta de ejemplo en JSON.</span><span class="sxs-lookup"><span data-stu-id="7a687-124">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
> [!NOTE]
> <span data-ttu-id="7a687-125">Se devuelve una matriz de objetos de usuario.</span><span class="sxs-lookup"><span data-stu-id="7a687-125">An array of User objects is returned.</span></span> <span data-ttu-id="7a687-126">Para obtener información detallada sobre el objeto de usuario, vea obtener el usuario.</span><span class="sxs-lookup"><span data-stu-id="7a687-126">For details about the User object, see Get User.</span></span> 
  
```
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


