---
title: Servicio de elementos de panel de calidad de la llamada (CQD)
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 6/8/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: b6d7b02a-a34e-4fef-986c-ca442e18fa0c
description: 'Resumen: Conozca el servicio del elemento, que es parte de la API de repositorio para llamar al panel de calidad. Panel de calidad de la llamada es una herramienta de Skype para Business Server 2015.'
ms.openlocfilehash: 218fdb4f2c4b3d73fb4e7f78b5679b66eecf34cc
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="item-service-for-call-quality-dashboard-cqd"></a>Servicio de elementos de panel de calidad de la llamada (CQD)
 
**Resumen:** Obtener información sobre el servicio del elemento, que es parte de la API de repositorio para llamar al panel de calidad. Panel de calidad de la llamada es una herramienta de Skype para Business Server 2015.
  
El servicio del elemento es parte de la API de repositorio para llamar al panel de calidad.
  
## <a name="item-service"></a>Servicio del elemento

API del depósito ofrece un servicio de administración de contenido simple, conocido como servicio de elemento, que se puede utilizar para almacenar cualquier contenido definido por la aplicación para los usuarios. 
  
El contenido del sistema es propiedad del usuario del sistema y compartido por todos los usuarios con acceso de sólo lectura. Contenido de usuario dedicada son propiedad de usuarios normales y sólo los propietarios pueden modificar o eliminar, pero todos los usuarios aún tienen acceso de sólo lectura a ellos.
  
> [!NOTE]
> Esta documentación de API cubre operaciones de sólo lectura de la API del depósito. 
  
Panel de calidad llamada guarda informes y consultas como elementos en la base de datos de repositorio. Un elemento puede tener elementos secundarios opcionales, y llamar al panel de calidad organiza los informes y consultas en una estructura jerárquica con la característica de subelementos.
  
Servicio de elemento incluye los siguientes conceptos:
  
- **Elemento** : elemento básico del repositorio. Cada elemento pertenece a exactamente un usuario.
    
- **Subtema** - los mecanismos básicos de organización del repositorio. Elemento puede tener cero, uno o más elementos subordinan.
    
- **Los antecesores de elemento** - la lista de elementos, comenzando por el elemento de nivel superior, que es el elemento del usuario, llevando a un determinado elemento predeterminado.
    
- **Elemento de contenido** - el contenido específico de la aplicación almacenado en artículos. Panel de calidad llamada guarda representaciones JSON de informes y consultas en contenido.
    
Las operaciones de resto se incluyen en la tabla siguiente.
  

|**Operación**|**Descripción**|
|:-----|:-----|
|[Obtener elementos](get-items.md) <br/> |Obtener elementos devuelve todos los elementos en el repositorio.  <br/> |
|[Obtener elemento](get-item.md) <br/> |Obtener un elemento específico de devoluciones de artículos.  <br/> |
|[Obtener elementos secundarios](get-sub-items.md) <br/> |Obtener elementos secundarios devuelve subelementos de un elemento específico.  <br/> |
|[Obtener los antecesores del elemento](get-item-ancestors.md) <br/> |Antecesores del elemento Get devuelve a los antecesores de un elemento específico.  <br/> |
|[Actualizar artículo](update-item.md) <br/> |Actualizar un elemento específico en el repositorio.  <br/> |
   

