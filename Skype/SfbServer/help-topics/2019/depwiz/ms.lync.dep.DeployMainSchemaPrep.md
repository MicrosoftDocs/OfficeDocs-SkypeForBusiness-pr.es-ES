---
title: Preparar esquema
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployMainSchemaPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 337aa234-c5f3-4468-a047-2023848e942c
ROBOTS: NOINDEX, NOFOLLOW
description: Para preparar el esquema para servicios de dominio de Active Directory, ejecute el paso preparar el esquema en el Asistente para la implementación de Skype empresarial Server. Haga clic en Ejecutar para comenzar la preparación del esquema.
ms.openlocfilehash: e48ae4ff28cf0423d3a29ae9f7d637cb8a58297c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34288214"
---
# <a name="prepare-schema"></a>Preparar esquema
 
Para preparar el esquema para servicios de dominio de Active Directory, ejecute el paso preparar el esquema en el Asistente para la implementación de Skype empresarial Server. Haga clic en **Ejecutar** para comenzar la preparación del esquema. El paso preparar el esquema Lee los archivos de definición del esquema suministrados en el directorio \Archivos de Files\Skype for Business Server 2019 \ Deployment\Setup del sistema en el que se está ejecutando el Asistente para la implementación. Estos archivos también están disponibles en el directorio \Support\Schema del medio de instalación. El paso Preparar esquema ampliará el esquema e informará sobre el estado del proceso. Además, avisará cuando el proceso haya finalizado. En la pantalla de resumen se podrán ver los registros del proceso. Examine los registros para asegurarse de que la preparación se haya completado correctamente.
  
> [!IMPORTANT]
> Para ampliar el esquema, debe iniciar sesión en el dominio como miembro de los grupos Administradores de esquema y Administradores de organización. 
  
Las clases y atributos se agregan para extender el esquema de servicios de dominio de Active Directory para admitir objetos de servidor, servicio y usuario de Skype empresarial Server. Antes de ampliar el esquema, se recomienda realizar una copia de seguridad del estado del sistema del controlador de dominio que tiene la función maestra de esquema. 
  
> [!CAUTION]
> La ampliación del esquema es una acción que no puede deshacerse. Debe hacer lo posible para limitar el impacto potencial de una ampliación de esquema incorrecta y para asegurarse de que la ampliación de esquema sea correcta. Esto es especialmente crítico en caso de pérdida de comunicación o de cualquier otro error en el servidor. Debe realizar una copia de seguridad del controlador de dominio maestro de esquema y una copia de seguridad completa de Active Directory. 
  
Para realizar una copia de seguridad del controlador de dominio maestro de esquema y una copia de seguridad completa de Active Directory:
  
1. Desconecte de la red el controlador de dominio que tiene el rol maestro de esquema.
    
2. Efectúe una copia de seguridad de estado del sistema del controlador de dominio que tiene el rol maestro de esquema.
    
3. Amplíe el esquema.
    
4. Si la ampliación del esquema es correcta, vuelva a conectar el controlador de dominio a la red y compruebe que la replicación esté activa y en funcionamiento.
    
5. En el caso improbable de que se produzca un error de extensión de esquema, restaure el estado de los sistemas del controlador de dominio y Active Directory con la copia de seguridad de estado del sistema que tomó anteriormente.
    
> [!NOTE]
> Si necesita revisar los archivos de registro creados por el Asistente para la implementación de Skype empresarial Server, puede encontrar los archivos en el equipo en el que se ejecutó el Asistente para la implementación, en el directorio usuarios del usuario de Active Directory que ejecutó el paso. Por ejemplo, si el usuario ha iniciado sesión como administrador del dominio Contoso.net, los archivos de registro se encuentran en: C:\Users\Administrator.Contoso\AppData\Local\Temp 
  

