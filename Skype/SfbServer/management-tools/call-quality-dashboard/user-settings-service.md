---
title: Servicio de configuración de usuario para el panel de calidad de llamada (CQD)
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: eafeb54a-2574-415b-b991-a0ff0470d8c3
description: 'Resumen: Información sobre el servicio de configuración de usuario, que forma parte de la API de repositorio para llamar al panel de calidad. Panel de calidad de llamada es una herramienta de Skype para Business Server.'
ms.openlocfilehash: 00d0662e777ef2f13c9783fe4b79d5c582faa8af
ms.sourcegitcommit: b680505c5dad435d98fbd0b235e0e7c67b9d8c9c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2018
ms.locfileid: "26035613"
---
# <a name="user-settings-service-for-call-quality-dashboard-cqd"></a>Servicio de configuración de usuario para el panel de calidad de llamada (CQD)
 
**Resumen:** Obtenga información sobre el servicio de configuración de usuario, que forma parte de la API de repositorio para llamar al panel de calidad. Panel de calidad de llamada es una herramienta de Skype para Business Server.
  
El servicio de configuración de usuario es parte de la API de repositorio para llamar al panel de calidad.
  
## <a name="user-settings-service"></a>Servicio de configuración de usuario

Configuración de usuario es pares de clave y valor que las aplicaciones pueden usar para almacenar metadatos para diversos fines, como la personalización de nivel de aplicación comportamientos de usuario. Cada usuario recibe un almacenamiento de información para la configuración de usuario. Sólo los propietarios pueden agregar, modificar y quitar la configuración de usuario.
  
 **Configuración global**
  
La configuración global es la configuración de usuario que pertenecen al usuario del sistema y todos los usuarios tienen acceso de solo lectura a ellos. La configuración global es constantes: se crean durante la creación de repositorio, y se debe cambiar nunca.
  
Cada usuario puede invalidar la configuración global mediante la creación de configuración de usuario con las mismas claves. Cuando la aplicación solicita la configuración de usuario eficaz, la API devuelve un conjunto de configuración global que se combina con la configuración de usuario, con cada opción de usuario el reemplazo de la correspondiente configuración global si las claves son las mismas. La API también puede devolver la configuración del usuario para que las aplicaciones pueden averiguar se reemplazan los valores de configuración. 
  
Las operaciones de REST se incluyen en la siguiente tabla.

|**Operación**|**Descripción**|
|:-----|:-----|
|[Obtener la configuración de usuario](get-user-settings.md) <br/> |Configuración del usuario Get devuelve una lista de valores para un usuario especificado.  <br/> |
|[Obtener la configuración de usuario](get-user-setting.md) <br/> |Obtener configuración de usuario devuelve una configuración de usuario único.  <br/> |
   

