---
title: Obtener elementos
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 9e189a48-4944-4f93-88d7-9d56b56770a6
description: 'Resumen: Obtenga información sobre la operación obtener elementos, que es parte del servicio de elementos. El servicio de artículo forma parte de la API del repositorio para el panel de calidad de llamadas. El panel de calidad de llamadas es una herramienta para Skype empresarial Server.'
ms.openlocfilehash: a1e7e8525df77cd5aacafb6d41316a985fbe9694
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34274705"
---
# <a name="get-items"></a>Obtener elementos
 
**Resumen:** Obtenga más información sobre la operación obtener elementos, que es parte del servicio de elemento. El servicio de artículo forma parte de la API del repositorio para el panel de calidad de llamadas. El panel de calidad de llamadas es una herramienta para Skype empresarial Server.
  
La operación obtener elementos forma parte del servicio de elemento en la API del repositorio para el panel de calidad de llamadas.
  
## <a name="get-items"></a>Obtener elementos

Obtener elementos devuelve todos los elementos del repositorio.
  
|**Método**|**Solicitar URI**|**Versión HTTP**|
|:-----|:-----|:-----|
|Obtener  <br/> |https://\<portal\>/QoERepositoryService/Repository/Item  <br/> |HTTP/1.1  <br/> |
   
 **Parámetros de URI** : ninguno.
  
 **Solicitar encabezados** : no hay encabezados adicionales.
  
 **Solicitar cuerpo** : ninguno.
  
 **Respuesta** : la respuesta incluye un código de estado http y un conjunto de encabezados de respuesta.
  
 **Código de estado** : una operación correcta devuelve el código de estado 200 (correcto).
  
 **Encabezados de respuesta** : no hay encabezados adicionales.
  
 **Cuerpo de respuesta** : a continuación se muestra un ejemplo de carga de respuesta en JSON.
  
> [!NOTE]
> Se devuelve una matriz de objetos de elemento. Para obtener más información sobre el objeto de elemento, vea obtener elemento. 
  
```
[{
"itemId": 1652,
"userId": 0,
"type": "application/json"
},
{
"itemId": 1653,
"userId": 0,
"type": "application/json"
},
{
"itemId": 1654,
"userId": 0,
"type": "application/json"
}]
```
