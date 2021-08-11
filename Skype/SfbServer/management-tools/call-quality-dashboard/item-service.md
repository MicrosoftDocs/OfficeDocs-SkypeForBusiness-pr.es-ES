---
title: Servicio de elementos para panel de calidad de llamadas (CQD)
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
ms.assetid: b6d7b02a-a34e-4fef-986c-ca442e18fa0c
description: 'Summary: Learn about the Item Service, which is part of the Repository API for Call Quality Dashboard. Panel de calidad de llamadas es una herramienta para Skype Empresarial Server.'
ms.openlocfilehash: 4e46cb213502e646a9fc3c750e7aeb40ffb6aff47b4d2aba0c19e04c56ce6cc0
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54331232"
---
# <a name="item-service-for-call-quality-dashboard-cqd"></a>Servicio de elementos para panel de calidad de llamadas (CQD)
 
**Resumen:** Obtenga información sobre el servicio de elementos, que forma parte de la API de repositorio para el Panel de calidad de llamadas. Panel de calidad de llamadas es una herramienta para Skype Empresarial Server.
  
El servicio de elementos forma parte de la API de repositorio para el Panel de calidad de llamadas.
  
## <a name="item-service"></a>Servicio de elemento

La API de repositorio ofrece un servicio de administración de contenido simple, conocido como servicio de elementos, que se puede usar para almacenar contenido definido por la aplicación para los usuarios. 
  
El contenido del sistema es propiedad del usuario del sistema y lo comparten todos los usuarios con acceso de solo lectura. Los contenidos de usuarios dedicados son propiedad de usuarios normales y solo los propietarios pueden modificarlos o eliminarlos, pero todos los usuarios aún tienen acceso de solo lectura a ellos.
  
> [!NOTE]
> Esta documentación de la API trata las operaciones de solo lectura de la API de repositorio. 
  
El Panel de calidad de llamadas guarda informes y consultas como elementos en la base de datos del repositorio. Un elemento puede tener sub-elementos opcionales y el Panel de calidad de llamadas organiza informes y consultas en una estructura jerárquica mediante la característica de sub-elementos.
  
El servicio de elementos incluye los siguientes conceptos:
  
- **Item:** el elemento básico del repositorio. Cada elemento es propiedad de exactamente un usuario.
    
- **Sub item:** la mecánica organizativa básica del repositorio. El elemento puede tener cero, uno o más elementos subordinados.
    
- **Antecesores del** elemento: la lista de elementos, comenzando desde el elemento superior, que es el elemento predeterminado del usuario, lo que lleva a un elemento determinado.
    
- **Contenido del elemento:** el contenido específico de la aplicación almacenado en Elementos. El Panel de calidad de llamadas guarda representaciones JSON de informes y consultas en contenido.
    
Las operaciones rest se incluyen en la tabla siguiente.
  

|**Operación**|**Descripción**|
|:-----|:-----|
|[Obtener elementos](get-items.md) <br/> |Get Items devuelve todos los elementos del repositorio.  <br/> |
|[Obtener elemento](get-item.md) <br/> |Get Item devuelve un elemento específico.  <br/> |
|[Obtener elementos secundarios](get-sub-items.md) <br/> |Get Sub-Items devuelve los sub-elementos de un elemento específico.  <br/> |
|[Obtener predecesores del elemento](get-item-ancestors.md) <br/> |Get Item Ancestors devuelve los antecesores de un elemento específico.  <br/> |
|[Actualizar elemento](update-item.md) <br/> |Actualice un elemento específico en el repositorio.  <br/> |
   

