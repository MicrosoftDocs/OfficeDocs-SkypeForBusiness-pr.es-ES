---
title: Servicio de elemento para el panel de calidad de llamada (CQD)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: b6d7b02a-a34e-4fef-986c-ca442e18fa0c
description: 'Resumen: Información sobre el servicio de elemento, que es parte de la API de repositorio para llamar al panel de calidad. Panel de calidad de llamada es una herramienta de Skype para Business Server.'
ms.openlocfilehash: cbebdcfcac62eae375c13785b8d9866d055c2b50
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33897502"
---
# <a name="item-service-for-call-quality-dashboard-cqd"></a>Servicio de elemento para el panel de calidad de llamada (CQD)
 
**Resumen:** Obtenga información sobre el servicio de elemento, que es parte de la API de repositorio para llamar al panel de calidad. Panel de calidad de llamada es una herramienta de Skype para Business Server.
  
El servicio de elemento es parte de la API de repositorio para llamar al panel de calidad.
  
## <a name="item-service"></a>Servicio de elemento

API del depósito ofrece un servicio de administración de contenido simple, conocido como servicio de elemento, que se puede usar para almacenar cualquier contenido definido por la aplicación para los usuarios. 
  
El contenido del sistema es propiedad del usuario del sistema y compartido por todos los usuarios con acceso de solo lectura. Contenido de usuario dedicada pertenecen a los usuarios habituales y sólo los propietarios pueden modificar o eliminar, pero aún, todos los usuarios tienen acceso de solo lectura a ellos.
  
> [!NOTE]
> Esta documentación de API trata las operaciones de sólo lectura de API de repositorio. 
  
Panel de calidad de llamada guarda informes y consultas como elementos en la base de datos de repositorio. Un elemento puede tener elementos secundarios opcionales y panel de calidad de llamadas organiza los informes y consultas en una estructura jerárquica con la característica de elementos secundarios.
  
Servicio de elemento incluye los siguientes conceptos:
  
- **Elemento** - el elemento básico del repositorio. Cada elemento pertenece a exactamente un usuario.
    
- **Elemento secundario** - los mecanismos básicos organizativos del repositorio. Elemento puede tener cero, uno o más elementos subordinados.
    
- **Elemento antecesores** - la lista de elementos, comenzando desde el elemento de nivel superior, que es el valor predeterminado de elemento del usuario, lo que lleva a un elemento determinado.
    
- **Elemento de contenido** : el contenido específico de la aplicación almacenado en los elementos. Panel de calidad de llamada guarda representaciones de JSON de informes y consultas en contenido.
    
Las operaciones de REST se incluyen en la siguiente tabla.
  

|**Operación**|**Descripción**|
|:-----|:-----|
|[Obtener elementos](get-items.md) <br/> |Obtener elementos devuelve todos los elementos en el repositorio.  <br/> |
|[Obtener elemento](get-item.md) <br/> |Obtener elemento devuelve un elemento específico.  <br/> |
|[Obtener elementos secundarios](get-sub-items.md) <br/> |Obtener elementos secundarios devuelve elementos secundarios de un elemento específico.  <br/> |
|[Obtener predecesores del elemento](get-item-ancestors.md) <br/> |Get elemento antecesores devuelve a antecesores de un elemento específico.  <br/> |
|[Actualizar elemento](update-item.md) <br/> |Actualizar un elemento específico en el repositorio.  <br/> |
   

