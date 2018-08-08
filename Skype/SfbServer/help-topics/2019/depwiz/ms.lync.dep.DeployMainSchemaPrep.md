---
title: Preparar esquema
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployMainSchemaPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 337aa234-c5f3-4468-a047-2023848e942c
ROBOTS: NOINDEX, NOFOLLOW
description: Para preparar el esquema de los servicios de dominio de Active Directory, ejecute el paso Preparar el esquema en el Skype para el Asistente para la implementación de servidor de negocio. Haga clic en Ejecutar para comenzar la preparación del esquema.
ms.openlocfilehash: 829c3062fcbfc1dab41e56de63e7a469f8e6e069
ms.sourcegitcommit: 0c2d1766b96b99d9985f5a0f4f90b8d8bd9aa3ef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/08/2018
ms.locfileid: "22138544"
---
# <a name="prepare-schema"></a>Preparar esquema
 
Para preparar el esquema de los servicios de dominio de Active Directory, ejecute el paso Preparar el esquema en el Skype para el Asistente para la implementación de servidor de negocio. Haga clic en **Ejecutar** para comenzar la preparación del esquema. El paso Preparar esquema lee los archivos de definición de esquema suministrados que se ubican en el directorio \Archivos de programa\Microsoft Lync Server 2013\Deployment\Setup en el sistema en el que se ejecuta el Asistente para la implementación. Estos archivos también están disponibles en el directorio \Support\Schema del medio de instalación. El paso Preparar esquema ampliará el esquema e informará sobre el estado del proceso. Además, avisará cuando el proceso haya finalizado. En la pantalla de resumen se podrán ver los registros del proceso. Examine los registros para asegurarse de que la preparación se haya completado correctamente.
  
> [!IMPORTANT]
> Para ampliar el esquema, debe iniciar sesión en el dominio como miembro de los grupos Administradores de esquema y Administradores de organización. 
  
Se agregan las clases y atributos para extender el esquema de los servicios de dominio de Active Directory para admitir Skype para server Business Server, servicio y objetos de usuario. Antes de ampliar el esquema, se recomienda realizar una copia de seguridad del estado del sistema del controlador de dominio que tiene la función maestra de esquema. 
  
> [!CAUTION]
> La ampliación del esquema es una acción que no puede deshacerse. Debe hacer lo posible para limitar el impacto potencial de una ampliación de esquema incorrecta y para asegurarse de que la ampliación de esquema sea correcta. Esto es especialmente crítico en caso de pérdida de comunicación o de cualquier otro error en el servidor. Debe realizar una copia de seguridad del controlador de dominio maestro de esquema y una copia de seguridad completa de Active Directory. 
  
Para realizar una copia de seguridad del controlador de dominio maestro de esquema y una copia de seguridad completa de Active Directory:
  
1. Desconecte de la red el controlador de dominio que tiene el rol maestro de esquema.
    
2. Efectúe una copia de seguridad de estado del sistema del controlador de dominio que tiene el rol maestro de esquema.
    
3. Amplíe el esquema.
    
4. Si la ampliación del esquema es correcta, vuelva a conectar el controlador de dominio a la red y compruebe que la replicación esté activa y en funcionamiento.
    
5. En el evento poco probable de un error de extensión de esquema, restaure el estado de sistemas del controlador de dominio y Active Directory mediante el uso de la copia de seguridad de estado del sistema que realizó anteriormente.
    
> [!NOTE]
> Si necesita revisar los archivos de registro que se crean mediante la Skype para el Asistente para la implementación de servidor de negocio, puede encontrar los archivos en el equipo donde se ejecutó el Asistente para la implementación, en el directorio de usuarios del usuario de Active Directory que se ejecutó el paso. Por ejemplo, si el usuario iniciado sesión como administrador de dominio en el dominio Contoso.net, los archivos de registro se encuentran en: C:\Users\Administrator.Contoso\AppData\Local\Temp 
  

