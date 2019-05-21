---
title: Servicio de configuración de usuario del panel de calidad de llamadas (CQD)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: eafeb54a-2574-415b-b991-a0ff0470d8c3
description: 'Resumen: Obtenga información sobre el servicio de configuración de usuario, que es parte de la API del repositorio para el panel de calidad de llamadas. El panel de calidad de llamadas es una herramienta para Skype empresarial Server.'
ms.openlocfilehash: e5e068d66adb325900b055a19aedcfaeabf4f2bc
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34274488"
---
# <a name="user-settings-service-for-call-quality-dashboard-cqd"></a>Servicio de configuración de usuario del panel de calidad de llamadas (CQD)
 
**Resumen:** Obtenga más información sobre el servicio de configuración de usuario, que es parte de la API del repositorio para el panel de calidad de llamadas. El panel de calidad de llamadas es una herramienta para Skype empresarial Server.
  
El servicio de configuración de usuario es parte de la API del repositorio para el panel de calidad de llamadas.
  
## <a name="user-settings-service"></a>Servicio de configuración de usuario

La configuración de usuario son pares clave-valor que las aplicaciones pueden usar para almacenar metadatos con diversos fines, entre ellos, la personalización de los comportamientos de la aplicación por usuario. Cada usuario recibe un almacenamiento para la configuración de usuario. Solo los propietarios pueden agregar, modificar y quitar configuraciones de usuario.
  
 **Configuración global**
  
Configuración global es la configuración del usuario propiedad del usuario del sistema y todos los usuarios tienen acceso de solo lectura a ellos. La configuración global es constante: se crean durante la creación del repositorio y nunca cambian.
  
Cada usuario puede invalidar la configuración global creando la configuración de usuario con las mismas claves. Cuando la aplicación solicita la configuración de usuario efectiva, la API devuelve un conjunto de opciones de configuración global combinadas con la configuración de usuario, con cada configuración de usuario que reemplaza la configuración global correspondiente si las claves son las mismas. La API también puede devolver solo la configuración de usuario para que las aplicaciones puedan averiguar qué opciones de configuración se reemplazan. 
  
Las operaciones de REST se incluyen en la tabla siguiente.

|**Operación**|**Descripción**|
|:-----|:-----|
|[Obtener configuración de usuario](get-user-settings.md) <br/> |Obtener configuración de usuario devuelve una lista de opciones de configuración para un usuario especificado.  <br/> |
|[Obtener configuración de usuario](get-user-setting.md) <br/> |Obtener configuración de usuario devuelve la configuración de un solo usuario.  <br/> |
   

