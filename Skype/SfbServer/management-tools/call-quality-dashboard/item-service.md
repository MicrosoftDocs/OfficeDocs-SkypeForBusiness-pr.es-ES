---
title: Servicio de artículos para el panel de calidad de llamadas (CQD)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: b6d7b02a-a34e-4fef-986c-ca442e18fa0c
description: 'Resumen: Obtenga información sobre el servicio de elementos, que forma parte de la API del repositorio para el panel de calidad de llamadas. El panel de calidad de llamadas es una herramienta para Skype empresarial Server.'
ms.openlocfilehash: 585ba97d9dedbfcbbd572069a792a121e6156afe
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34274614"
---
# <a name="item-service-for-call-quality-dashboard-cqd"></a>Servicio de artículos para el panel de calidad de llamadas (CQD)
 
**Resumen:** Obtenga más información sobre el servicio de elementos, que forma parte de la API del repositorio para el panel de calidad de llamadas. El panel de calidad de llamadas es una herramienta para Skype empresarial Server.
  
El servicio de artículo forma parte de la API del repositorio para el panel de calidad de llamadas.
  
## <a name="item-service"></a>Servicio de elemento

La API de repositorio ofrece un servicio de administración de contenido simple, conocido como servicio de elementos, que se puede usar para almacenar cualquier contenido definido por la aplicación para los usuarios. 
  
El contenido del sistema pertenece al usuario del sistema y lo comparten todos los usuarios con acceso de solo lectura. El contenido del usuario dedicado pertenece a usuarios normales, y solo los propietarios pueden modificarlos o eliminarlos, pero todos los usuarios siguen teniendo acceso de solo lectura a ellos.
  
> [!NOTE]
> Esta documentación de API cubre las operaciones de solo lectura de la API del repositorio. 
  
El panel de calidad de llamadas guarda informes y consultas como elementos en la base de datos del repositorio. Un elemento puede tener subelementos opcionales y el panel de calidad de llamadas organiza los informes y las consultas en una estructura jerárquica mediante la característica subelementos.
  
El servicio de artículos incluye los siguientes conceptos:
  
- **Elemento** : el elemento básico del repositorio. Cada elemento pertenece a un solo usuario.
    
- **Elemento secundario** : el mecanismo básico de la organización del repositorio. El elemento puede tener cero, uno o más elementos subordinados.
    
- **Antecesores de elemento** : la lista de elementos, empezando por el elemento de nivel superior, que es el elemento predeterminado del usuario, que lleva a un elemento determinado.
    
- **Contenido del elemento** : el contenido específico de la aplicación almacenado en los elementos. El panel de calidad de llamadas guarda las representaciones JSON de informes y consultas en el contenido.
    
Las operaciones de REST se incluyen en la tabla siguiente.
  

|**Operación**|**Descripción**|
|:-----|:-----|
|[Obtener elementos](get-items.md) <br/> |Obtener elementos devuelve todos los elementos del repositorio.  <br/> |
|[Obtener elemento](get-item.md) <br/> |Obtener elemento devuelve un elemento específico.  <br/> |
|[Obtener elementos secundarios](get-sub-items.md) <br/> |Obtener subelementos devuelve los subelementos de un elemento específico.  <br/> |
|[Obtener predecesores del elemento](get-item-ancestors.md) <br/> |Obtener elementos antecesores del elemento devuelve los antecesores de un elemento específico.  <br/> |
|[Actualizar elemento](update-item.md) <br/> |Actualice un elemento específico del repositorio.  <br/> |
   

