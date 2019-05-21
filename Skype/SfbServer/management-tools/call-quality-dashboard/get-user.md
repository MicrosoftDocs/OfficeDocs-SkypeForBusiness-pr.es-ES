---
title: Obtener usuario
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 52b89a4b-a0bd-493d-bb5e-e21904eb8e48
description: 'Resumen: Obtenga información sobre la operación obtener usuario, que es parte del servicio de usuario. El servicio de usuario es parte de la API del repositorio para el panel de calidad de llamadas. El panel de calidad de llamadas es una herramienta para Skype empresarial Server.'
ms.openlocfilehash: 6c38bb2db2bef1a21dfc5c4791de7a163c57ff5f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34274600"
---
# <a name="get-user"></a><span data-ttu-id="5d372-105">Obtener usuario</span><span class="sxs-lookup"><span data-stu-id="5d372-105">Get User</span></span>
 
<span data-ttu-id="5d372-106">**Resumen:** Obtenga más información sobre la operación obtener usuario, que es parte del servicio de usuario.</span><span class="sxs-lookup"><span data-stu-id="5d372-106">**Summary:** Learn about the Get User operation, which is part of the User Service.</span></span> <span data-ttu-id="5d372-107">El servicio de usuario es parte de la API del repositorio para el panel de calidad de llamadas.</span><span class="sxs-lookup"><span data-stu-id="5d372-107">The User Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="5d372-108">El panel de calidad de llamadas es una herramienta para Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="5d372-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="5d372-109">La operación obtener usuarios forma parte del servicio de usuario en la API del repositorio para el panel de calidad de llamadas.</span><span class="sxs-lookup"><span data-stu-id="5d372-109">The Get Users operation is part of the User Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-user"></a><span data-ttu-id="5d372-110">Obtener usuario</span><span class="sxs-lookup"><span data-stu-id="5d372-110">Get User</span></span>

<span data-ttu-id="5d372-111">Obtener el usuario devuelve un registro de usuario del repositorio.</span><span class="sxs-lookup"><span data-stu-id="5d372-111">Get User returns a user record from the repository.</span></span>
  
|<span data-ttu-id="5d372-112">**Método**</span><span class="sxs-lookup"><span data-stu-id="5d372-112">**Method**</span></span>|<span data-ttu-id="5d372-113">**Solicitar URI**</span><span class="sxs-lookup"><span data-stu-id="5d372-113">**Request URI**</span></span>|<span data-ttu-id="5d372-114">**Versión HTTP**</span><span class="sxs-lookup"><span data-stu-id="5d372-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="5d372-115">Obtener</span><span class="sxs-lookup"><span data-stu-id="5d372-115">GET</span></span>  <br/> |<span data-ttu-id="5d372-116">https://\<portal\>/QoERepositoryService/Repository/User/{userId}</span><span class="sxs-lookup"><span data-stu-id="5d372-116">https://\<portal\>/QoERepositoryService/repository/user/{userId}</span></span>  <br/> |<span data-ttu-id="5d372-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="5d372-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="5d372-118">**Parámetros de URI** : ninguno.</span><span class="sxs-lookup"><span data-stu-id="5d372-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="5d372-119">**Solicitar encabezados** : no hay encabezados adicionales.</span><span class="sxs-lookup"><span data-stu-id="5d372-119">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="5d372-120">**Solicitar cuerpo** : ninguno.</span><span class="sxs-lookup"><span data-stu-id="5d372-120">**Request Body** - None.</span></span>
  
 <span data-ttu-id="5d372-121">**Respuesta** : la respuesta incluye un código de estado http y un conjunto de encabezados de respuesta.</span><span class="sxs-lookup"><span data-stu-id="5d372-121">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="5d372-122">**Código de estado** : una operación correcta devuelve el código de estado 200 (correcto).</span><span class="sxs-lookup"><span data-stu-id="5d372-122">**Status Code** - A successful operation returns status code 200 (OK).</span></span> <span data-ttu-id="5d372-123">Si no se encuentra un identificador de usuario especificado, devuelve el código de estado 404 (no se encontró).</span><span class="sxs-lookup"><span data-stu-id="5d372-123">If a specified user ID is not found, it returns status code 404 (Not Found).</span></span>
  
 <span data-ttu-id="5d372-124">**Encabezados de respuesta** : no hay encabezados adicionales.</span><span class="sxs-lookup"><span data-stu-id="5d372-124">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="5d372-125">**Cuerpo de respuesta** : a continuación se muestra un ejemplo de carga de respuesta en JSON.</span><span class="sxs-lookup"><span data-stu-id="5d372-125">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
```
{
"userId": 0,
"loginName": "system",
"defaultItemId": 1655
}
```

 <span data-ttu-id="5d372-126">\*\* ID. de usuario.</span><span class="sxs-lookup"><span data-stu-id="5d372-126">*userId*  - ID of the user.</span></span>
  
 <span data-ttu-id="5d372-127">*loginName* : identificación de usuario externo para usuarios comunes.</span><span class="sxs-lookup"><span data-stu-id="5d372-127">*loginName*  - External user identification for regular users.</span></span> <span data-ttu-id="5d372-128">Si se usa la autenticación de Windows para autenticar a los usuarios, esto puede ser un FQDN del usuario.</span><span class="sxs-lookup"><span data-stu-id="5d372-128">If Windows Authentication is used for authenticating users, then this may be a FQDN of the user.</span></span>
  
 <span data-ttu-id="5d372-129">*defaultItemId* : identificador del elemento predeterminado para este usuario.</span><span class="sxs-lookup"><span data-stu-id="5d372-129">*defaultItemId*  - ID of the default Item for this user.</span></span> <span data-ttu-id="5d372-130">El elemento predeterminado es el elemento de nivel superior asociado al usuario.</span><span class="sxs-lookup"><span data-stu-id="5d372-130">The default Item is the top-most Item that is associated to the user.</span></span> <span data-ttu-id="5d372-131">El resto de los elementos a los que pertenece este usuario se puede navegar desde el elemento predeterminado.</span><span class="sxs-lookup"><span data-stu-id="5d372-131">All other Items this user owns can be navigated from the default Item.</span></span>
  
> [!NOTE]
> <span data-ttu-id="5d372-132">Proporcione el `defaultItemId` valor para la operación obtener elemento para recuperar los detalles del elemento predeterminado.</span><span class="sxs-lookup"><span data-stu-id="5d372-132">Supply the  `defaultItemId` value to Get Item operation to retrieve the details of the default Item.</span></span>
  

