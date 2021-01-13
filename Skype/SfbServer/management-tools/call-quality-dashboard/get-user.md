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
description: 'Resumen: obtenga información sobre la operación Obtener usuario, que forma parte del servicio de usuario. El servicio de usuario forma parte de la API de repositorio para el panel de calidad de llamadas. El Panel de calidad de llamadas es una herramienta para Skype Empresarial Server.'
ms.openlocfilehash: dd2bb5e46ddbe3e65faf441a11e39cbc5429e473
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832420"
---
# <a name="get-user"></a>Obtener usuario
 
**Resumen:** Obtenga información sobre la operación Obtener usuario, que forma parte del servicio de usuario. El servicio de usuario forma parte de la API de repositorio para el panel de calidad de llamadas. El Panel de calidad de llamadas es una herramienta para Skype Empresarial Server.
  
La operación Obtener usuarios forma parte del servicio de usuario en la API de repositorio para el panel de calidad de llamadas.
  
## <a name="get-user"></a>Obtener usuario

Get User devuelve un registro de usuario del repositorio.
  
|**Método**|**URI de solicitud**|**Versión HTTP**|
|:-----|:-----|:-----|
|GET  <br/> |https:// \<portal\> /QoERepositoryService/repository/user/{userId}  <br/> |HTTP/1.1  <br/> |
   
 **Parámetros uri:** ninguno.
  
 **Encabezados de solicitud:** no hay encabezados adicionales.
  
 **Cuerpo de la** solicitud: ninguno.
  
 **Respuesta:** la respuesta incluye un código de estado HTTP y un conjunto de encabezados de respuesta.
  
 **Código de estado:** una operación correcta devuelve el código de estado 200 (Correcto). Si no se encuentra un identificador de usuario especificado, devuelve el código de estado 404 (No encontrado).
  
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
  
 *loginName:*  identificación de usuario externo para usuarios normales. Si se usa la autenticación de Windows para autenticar usuarios, puede ser un FQDN del usuario.
  
 *defaultItemId:*  identificador del elemento predeterminado para este usuario. El elemento predeterminado es el elemento de nivel superior asociado al usuario. Todos los demás elementos que posee este usuario se pueden navegar desde el elemento predeterminado.
  
> [!NOTE]
> Proporcione el  `defaultItemId` valor de la operación Obtener elemento para recuperar los detalles del elemento predeterminado.
  

