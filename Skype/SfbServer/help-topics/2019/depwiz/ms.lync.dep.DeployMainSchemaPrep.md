---
title: Preparar esquema
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeployMainSchemaPrep
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 337aa234-c5f3-4468-a047-2023848e942c
ROBOTS: NOINDEX, NOFOLLOW
description: Para preparar el esquema para los Servicios de dominio de Active Directory, ejecute el paso Preparar esquema en el Asistente para la implementación de Skype Empresarial Server. Haga clic en Ejecutar para comenzar la preparación del esquema.
ms.openlocfilehash: b666cda29267c6f74eb034389f3f7967d7af99c5
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49833780"
---
# <a name="prepare-schema"></a>Preparar esquema
 
Para preparar el esquema para los Servicios de dominio de Active Directory, ejecute el paso Preparar esquema en el Asistente para la implementación de Skype Empresarial Server. Haga clic en **Ejecutar** para comenzar la preparación del esquema. El paso Preparar esquema lee los archivos de definición de esquema proporcionados en el directorio \Archivos de programa\Skype Empresarial Server 2019\Deployment\Setup del sistema en el que se ejecuta el Asistente para la implementación. Estos archivos también están disponibles en el directorio \Soporte\Esquema del medio de instalación. El paso Preparar el esquema ampliará el esquema e informará sobre el estado del proceso. Además, avisará cuando el proceso haya finalizado. En la pantalla de resumen se podrán ver los registros del proceso. Examine los registros para asegurarse de que la preparación se haya completado correctamente.
  
> [!IMPORTANT]
> Para ampliar el esquema, debe iniciar sesión en el dominio como miembro de los grupos Administradores de esquema y Administradores de organización. 
  
Se agregan clases y atributos para ampliar el esquema de Servicios de dominio de Active Directory para admitir objetos de servidor, servicio y usuario de Skype Empresarial Server. Antes de ampliar el esquema, se recomienda realizar una copia de seguridad del estado del sistema del controlador de dominio que tiene la función maestra de esquema. 
  
> [!CAUTION]
> La ampliación del esquema es una acción que no puede deshacerse. Debe hacer lo posible para limitar el impacto potencial de una ampliación de esquema incorrecta y para asegurarse de que la ampliación de esquema sea correcta. Esto es especialmente crítico en caso de pérdida de comunicación o de cualquier otro error en el servidor. Debe realizar una copia de seguridad del controlador de dominio maestro de esquema y una copia de seguridad completa de Active Directory. 
  
Para realizar una copia de seguridad del controlador de dominio maestro de esquema y una copia de seguridad completa de Active Directory:
  
1. Desconecte de la red el controlador de dominio que tiene el rol maestro de esquema.
    
2. Efectúe una copia de seguridad de estado del sistema del controlador de dominio que tiene el rol maestro de esquema.
    
3. Amplíe el esquema.
    
4. Si la ampliación del esquema es correcta, vuelva a conectar el controlador de dominio a la red y compruebe que la replicación esté activa y en funcionamiento.
    
5. En el caso poco probable de un error de extensión de esquema, restaure el estado del sistema del controlador de dominio y Active Directory mediante la copia de seguridad del estado del sistema que ha tomado anteriormente.
    
> [!NOTE]
> Si necesita revisar los archivos de registro creados por el Asistente para la implementación de Skype Empresarial Server, puede encontrar los archivos en el equipo donde se ejecutó el Asistente para la implementación, en el directorio de usuarios del usuario de Active Directory que realizó el paso. Por ejemplo, si el usuario inició sesión como administrador de dominio en el dominio Contoso.net, los archivos de registro se encuentran en: C:\Users\Administrator.Contoso\AppData\Local\Temp 
  

