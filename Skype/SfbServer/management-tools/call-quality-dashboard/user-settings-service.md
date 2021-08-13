---
title: Servicio Configuración usuario para panel de calidad de llamadas (CQD)
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
ms.assetid: eafeb54a-2574-415b-b991-a0ff0470d8c3
description: 'Summary: Learn about the User Configuración Service, which is part of the Repository API for Call Quality Dashboard. Panel de calidad de llamadas es una herramienta para Skype Empresarial Server.'
ms.openlocfilehash: c037024c8fe336c3614dd9daf6ee02370337ad5c6c44b45c783044cc421f626f
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54315566"
---
# <a name="user-settings-service-for-call-quality-dashboard-cqd"></a>Servicio Configuración usuario para panel de calidad de llamadas (CQD)
 
**Resumen:** Obtenga información sobre el servicio de Configuración usuario, que forma parte de la API de repositorio para el Panel de calidad de llamadas. Panel de calidad de llamadas es una herramienta para Skype Empresarial Server.
  
El servicio de Configuración usuario forma parte de la API de repositorio para el Panel de calidad de llamadas.
  
## <a name="user-settings-service"></a>Servicio de configuración de usuario

La configuración de usuario son pares clave-valor que las aplicaciones pueden usar para almacenar metadatos con diversos fines, incluida la personalización de los comportamientos de la aplicación por usuario. Cada usuario recibe un almacenamiento para la configuración del usuario. Solo los propietarios pueden agregar, modificar y quitar la configuración de usuario.
  
 **Global Configuración**
  
La configuración global es la configuración de usuario propiedad del usuario del sistema y todos los usuarios tienen acceso de solo lectura a ellos. La configuración global son constantes: se crean durante la creación del repositorio y nunca cambian.
  
Cada usuario puede invalidar la configuración global creando la configuración de usuario con las mismas claves. Cuando la aplicación solicita la configuración de usuario eficaz, la API devuelve un conjunto de configuraciones globales combinadas con la configuración de usuario, con cada configuración de usuario supersediendo la configuración global respectiva si las claves son las mismas. La API también puede devolver solo la configuración del usuario para que las aplicaciones puedan averiguar qué configuración se invalida. 
  
Las operaciones rest se incluyen en la tabla siguiente.

|**Operación**|**Descripción**|
|:-----|:-----|
|[Obtener configuración de usuario](get-user-settings.md) <br/> |Get User Configuración devuelve una lista de opciones de configuración para un usuario especificado.  <br/> |
|[Obtener configuración de usuario](get-user-setting.md) <br/> |Obtener configuración de usuario devuelve una única configuración de usuario.  <br/> |
   

