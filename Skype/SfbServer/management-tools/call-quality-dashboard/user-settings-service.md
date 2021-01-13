---
title: Servicio de configuración de usuario para el Panel de calidad de llamadas (CQD)
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
description: 'Resumen: obtenga información sobre el servicio de configuración de usuario, que forma parte de la API de repositorio para el panel de calidad de llamadas. El Panel de calidad de llamadas es una herramienta para Skype Empresarial Server.'
ms.openlocfilehash: 2b2fc9810f1eceb74974dc105263b0bdcf37ae01
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49803041"
---
# <a name="user-settings-service-for-call-quality-dashboard-cqd"></a>Servicio de configuración de usuario para el Panel de calidad de llamadas (CQD)
 
**Resumen:** Obtenga información sobre el Servicio de configuración de usuario, que forma parte de la API de repositorio para el Panel de calidad de llamadas. El Panel de calidad de llamadas es una herramienta para Skype Empresarial Server.
  
El servicio de configuración de usuario forma parte de la API de repositorio para el panel de calidad de llamadas.
  
## <a name="user-settings-service"></a>Servicio de configuración de usuario

La configuración de usuario son pares clave-valor que las aplicaciones pueden usar para almacenar metadatos con diversos fines, incluida la personalización de comportamientos de aplicación por usuario. Cada usuario recibe un almacenamiento para la configuración de usuario. Solo los propietarios pueden agregar, modificar y quitar la configuración de usuario.
  
 **Configuración global**
  
La configuración global es la configuración de usuario propiedad del usuario del sistema y todos los usuarios tienen acceso de solo lectura a ellos. La configuración global son constantes: se crean durante la creación del repositorio y nunca cambian.
  
Cada usuario puede invalidar la configuración global mediante la creación de configuraciones de usuario con las mismas claves. Cuando la aplicación solicita la configuración de usuario efectiva, la API devuelve un conjunto de configuraciones globales combinadas con la configuración de usuario, con cada configuración de usuario supersedando la configuración global respectiva si las claves son las mismas. La API también puede devolver solo la configuración de usuario para que las aplicaciones puedan averiguar qué configuración se reemplaza. 
  
Las operaciones rest se incluyen en la tabla siguiente.

|**Operación**|**Descripción**|
|:-----|:-----|
|[Obtener configuración de usuario](get-user-settings.md) <br/> |Obtener configuración de usuario devuelve una lista de configuraciones para un usuario especificado.  <br/> |
|[Obtener configuración de usuario](get-user-setting.md) <br/> |Obtener configuración de usuario devuelve una configuración de usuario único.  <br/> |
   

