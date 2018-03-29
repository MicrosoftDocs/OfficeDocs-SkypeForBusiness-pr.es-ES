---
title: Servicio de configuración de usuario para el panel de calidad de la llamada (CQD)
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/18/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: eafeb54a-2574-415b-b991-a0ff0470d8c3
description: 'Resumen: Conozca el servicio de configuración de usuario, que forma parte de la API de repositorio para llamar al panel de calidad. Panel de calidad de la llamada es una herramienta de Skype para Business Server 2015.'
ms.openlocfilehash: fe51c96546903e09f28ffadf06451efc8c1a88b0
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="user-settings-service-for-call-quality-dashboard-cqd"></a>Servicio de configuración de usuario para el panel de calidad de la llamada (CQD)
 
**Resumen:** Obtener información sobre el servicio de configuración de usuario, que forma parte de la API de repositorio para llamar al panel de calidad. Panel de calidad de la llamada es una herramienta de Skype para Business Server 2015.
  
El servicio de configuración de usuario es parte de la API de repositorio para llamar al panel de calidad.
  
## <a name="user-settings-service"></a>Servicio de configuración de usuario

Configuración de usuario es pares de clave y valor que las aplicaciones pueden utilizar para almacenar metadatos para diversos fines, como la personalización de cada usuario de comportamientos de aplicación. Cada usuario recibe un almacenamiento de información para la configuración de usuario. Sólo los propietarios pueden agregar, modificar y quitar la configuración de usuario.
  
 **Configuración global**
  
Configuración global es la configuración de usuario que pertenecen al usuario del sistema y todos los usuarios tienen acceso de sólo lectura a ellos. Configuración global es constantes: se crean durante la creación del repositorio y nunca cambian.
  
Cada usuario puede reemplazar la configuración global mediante la creación de configuraciones de usuario con las mismas claves. Cuando la aplicación solicita la configuración de usuario eficaces, la API devuelve un conjunto de configuración global que se combina con la configuración de usuario, con cada configuración de usuario el reemplazo de la respectiva configuración global si las claves son iguales. La API también puede devolver la configuración del usuario para que las aplicaciones pueden averiguar qué valores prevalecen. 
  
Las operaciones de resto se incluyen en la tabla siguiente.

|**Operación**|**Descripción**|
|:-----|:-----|
|[Obtener la configuración de usuario](get-user-settings.md) <br/> |Configuración de usuario de Get devuelve una lista de valores para un usuario especificado.  <br/> |
|[Obtener la configuración de usuario](get-user-setting.md) <br/> |Obtener configuración de usuario devuelve un entorno de usuario único.  <br/> |
   

