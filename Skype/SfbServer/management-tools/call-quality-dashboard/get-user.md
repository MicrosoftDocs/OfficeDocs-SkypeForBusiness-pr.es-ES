---
title: Obtener usuario
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/18/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 52b89a4b-a0bd-493d-bb5e-e21904eb8e48
description: 'Resumen: Conozca la operación de obtener el usuario, que es parte del servicio de usuario. El servicio de usuario forma parte de la API de repositorio para llamar al panel de calidad. Panel de calidad de la llamada es una herramienta de Skype para Business Server 2015.'
ms.openlocfilehash: e3863819ea15a1039a3a02b1a35cfc7326af7e1d
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="get-user"></a>Obtener usuario
 
**Resumen:** Obtener información sobre la operación de obtener el usuario, que es parte del servicio de usuario. El servicio de usuario forma parte de la API de repositorio para llamar al panel de calidad. Panel de calidad de la llamada es una herramienta de Skype para Business Server 2015.
  
La operación de obtener usuarios forma parte del servicio de usuario de la API de repositorio para llamar al panel de calidad.
  
## <a name="get-user"></a>Obtener usuario

Obtener devoluciones de usuario en un registro de usuario del repositorio.
  
|**Método**|**URI de la solicitud**|**Versión de HTTP**|
|:-----|:-----|:-----|
|Obtener  <br/> |https://\<portal\>/QoERepositoryService/repository/usuario / {ID}  <br/> |HTTP/1.1  <br/> |
   
 **URI parámetros** : ninguno.
  
 **Encabezados de solicitud** - sin encabezados adicionales.
  
 **Cuerpo de la solicitud** - ninguno.
  
 **Respuesta** : la respuesta incluye un código de estado HTTP y un conjunto de encabezados de respuesta.
  
 **Código de estado** - una operación correcta devuelve el código de estado 200 (OK). Si un usuario especificado que no se encuentra el identificador, devuelve el código de estado 404 (no encontrado).
  
 **Encabezados de respuesta** - sin encabezados adicionales.
  
 **Cuerpo de la respuesta** : a continuación es una carga de respuesta de ejemplo en JSON.
  
```
{
"userId": 0,
"loginName": "system",
"defaultItemId": 1655
}

```

 *userId* : identificador del usuario.
  
 *loginName* - identificación de usuario externo para los usuarios normales. Si utiliza la autenticación de Windows para autenticar a los usuarios, esto puede ser un nombre de dominio completo del usuario.
  
 *defaultItemId* - ID del elemento predeterminado para este usuario. El valor predeterminado de elemento es el elemento superior que está asociado al usuario. Todos los demás elementos de que este usuario se pueden navegar desde el elemento predeterminado.
  
> [!NOTE]
> Proporcionar el `defaultItemId` valor de la operación obtener elemento para recuperar los detalles del elemento predeterminado.
  

