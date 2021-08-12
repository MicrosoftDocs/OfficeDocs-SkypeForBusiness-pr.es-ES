---
title: Obtener usuario
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
ms.assetid: 52b89a4b-a0bd-493d-bb5e-e21904eb8e48
description: 'Resumen: obtenga información sobre la operación Obtener usuario, que forma parte del servicio de usuario. El servicio de usuario forma parte de la API de repositorio para el Panel de calidad de llamadas. Panel de calidad de llamadas es una herramienta para Skype Empresarial Server.'
ms.openlocfilehash: bb99ec52cb270bdef51eac65070c1f5204bb03b93c81dd46d31f86a2ffc3b836
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54311048"
---
# <a name="get-user"></a>Obtener usuario
 
**Resumen:** Obtenga información sobre la operación Obtener usuario, que forma parte del servicio de usuario. El servicio de usuario forma parte de la API de repositorio para el Panel de calidad de llamadas. Panel de calidad de llamadas es una herramienta para Skype Empresarial Server.
  
La operación Obtener usuarios forma parte del servicio de usuario de la API de repositorio para el Panel de calidad de llamadas.
  
## <a name="get-user"></a>Obtener usuario

Get User devuelve un registro de usuario del repositorio.
  
|**Método**|**URI de solicitud**|**Versión HTTP**|
|:-----|:-----|:-----|
|GET  <br/> |https:// \<portal\> /QoERepositoryService/repository/user/{userId}  <br/> |HTTP/1.1  <br/> |
   
 **Parámetros uri:** ninguno.
  
 **Encabezados de solicitud:** no hay encabezados adicionales.
  
 **Cuerpo de la** solicitud: ninguno.
  
 **Respuesta:** la respuesta incluye un código de estado HTTP y un conjunto de encabezados de respuesta.
  
 **Código de estado:** una operación correcta devuelve el código de estado 200 (Aceptar). Si no se encuentra un identificador de usuario especificado, devuelve el código de estado 404 (No encontrado).
  
 **Encabezados de respuesta:** no hay encabezados adicionales.
  
 **Cuerpo de la** respuesta: a continuación se muestra una carga de respuesta de ejemplo en JSON.
  
```json
{
"userId": 0,
"loginName": "system",
"defaultItemId": 1655
}
```

 *userId:*  id. del usuario.
  
 *loginName:*  identificación de usuario externo para usuarios normales. Si Windows autenticación se usa para autenticar usuarios, puede ser un FQDN del usuario.
  
 *defaultItemId:*  identificador del elemento predeterminado para este usuario. El elemento predeterminado es el elemento más alto que está asociado al usuario. Todos los demás elementos que posee este usuario se pueden navegar desde el elemento predeterminado.
  
> [!NOTE]
> Proporcione el  `defaultItemId` valor a la operación Obtener elemento para recuperar los detalles del elemento predeterminado.
  

