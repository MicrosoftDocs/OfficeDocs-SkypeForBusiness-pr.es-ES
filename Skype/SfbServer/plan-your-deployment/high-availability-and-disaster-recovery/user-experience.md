---
title: Experiencia del usuario durante el error del grupo en Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: b224b0d0-87e3-4cac-ae87-f45f54fabb49
description: Obtenga información sobre la experiencia de los usuarios cuando un grupo de servidores front-end conmuta por error o vuelve a fallar durante la recuperación ante desastres en Skype Empresarial Server.
ms.openlocfilehash: f17e589175c0d91db074f7ff1a1808a32d65410a5c5d7639fa2bcb284ed67680
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54276605"
---
# <a name="user-experience-during-pool-failure-in-skype-for-business-server"></a>Experiencia del usuario durante el error del grupo en Skype Empresarial Server
 
Obtenga información sobre la experiencia de los usuarios cuando un grupo de servidores front-end conmuta por error o vuelve a fallar durante la recuperación ante desastres en Skype Empresarial Server.
  
Si se con error en un grupo de servidores, todos los usuarios del grupo afectado se ven obligados a cerrar sesión y, a continuación, iniciar sesión en el grupo de copia de seguridad. Durante un breve período, los usuarios que inician sesión en el grupo de copia de seguridad pueden estar en modo de resistencia. En el modo de resistencia, los usuarios no pueden realizar tareas que provocarían un cambio persistente en Skype Empresarial Server, como agregar un contacto. Una vez completada la conmutación por error, todos los usuarios pueden obtener todos los servicios del grupo de copia de seguridad.
  
Las llamadas, reuniones o conversaciones que tenga un usuario cuando se produzca un error en el grupo de servidores se interrumpen y el usuario debe restablecer esas sesiones después de la conmutación por error para continuar.
  
Los usuarios no se rehomen durante la conmutación por error o la conmutación por recuperación. El grupo de servidores de copia de seguridad atenderá temporalmente a los usuarios que se encuentran en un grupo de servidores que produce un error. Cuando se restaura el grupo de servidores principal, el administrador puede realizar una conmutación por recuperación de estos usuarios para que sean atendidos por su grupo original, donde aún se encuentran en el hogar.
  
Tenga en cuenta que la base de datos del servidor de información de ubicación no se replica en el grupo de servidores de copia de seguridad. Para un procedimiento recomendado, el administrador debe hacer una copia de seguridad periódica de la base de datos lis y usar la copia de seguridad más reciente para restaurar la base de datos lis en el grupo de copia de seguridad después de la conmutación por error.
  
## <a name="user-experience-during-failover"></a>Experiencia del usuario durante la conmutación por error

Cuando un usuario está en un grupo de servidores que produce un error, el usuario ha cerrado sesión. Cualquier sesión punto a punto en la que el usuario participaba finaliza, al igual que las conferencias organizadas por ese usuario. El usuario no puede volver a iniciar sesión hasta que expire el temporizador de resistencia del registrador o el administrador inicie los procedimientos de conmutación por error, lo que sea primero. Cuando el usuario vuelva a iniciar sesión, iniciarán sesión en el grupo de copia de seguridad. Si inician sesión antes de que se complete la conmutación por error, estarán en modo de resistencia hasta que se complete la conmutación por error. Solo entonces un usuario puede establecer nuevas sesiones o restablecer sesiones anteriores.
  
## <a name="user-experience-during-failback"></a>Experiencia del usuario durante la conmutación por recuperación

La conmutación por recuperación del grupo de servidores puede producirse mientras un usuario afectado ha iniciado sesión en el grupo de copia de seguridad y el usuario permanece conectado y trabajando durante la conmutación por recuperación. Tenga en cuenta que el proceso de conmutación por recuperación tarda varios minutos en completarse. Como referencia, un grupo de 20.000  usuarios suele tardar 60 minutos.
  
En las tablas siguientes se muestran más detalles sobre cómo se ve afectado un usuario durante y después de la conmutación por recuperación, así como cómo los usuarios de otros grupos ven e interactúan con un usuario de un grupo al que se le está conmutando la conmutación por error. 
  
El término usuario afectado hace referencia a cualquier usuario al que el grupo de servidores principal ha fallado y al que el grupo de copia de seguridad está prestando servicio. Un usuario que se encuentra originalmente en el grupo de servidores de copia de seguridad no es un usuario afectado.
  
**Experiencia del usuario para un usuario afectado en un grupo de servidores en conmutación por recuperación**

|**Estado o tarea del usuario**|**Durante la conmutación por recuperación**|**Después de la finalización de la conmutación por recuperación**|
|:-----|:-----|:-----|
|Estado de usuario del usuario que ya ha iniciado sesión  <br/> |El usuario permanece conectado y conectado al grupo de servidores de copia de seguridad. En algún momento, el usuario cerrará sesión y volverá a iniciar sesión en el grupo de servidores principal original, en modo resistencia.  <br/> |El usuario permanece iniciado sesión y pasa al modo normal.  <br/> |
|Nuevo inicio de sesión de usuario  <br/> |El usuario puede iniciar sesión en el grupo de servidores principal en modo de resistencia.  <br/> |El usuario puede iniciar sesión en el grupo de servidores principal original en modo normal.  <br/> |
|Conferencias en curso organizadas por el usuario afectado  <br/> |Se terminan todas las modalidades de conferencia. Aparecerá el botón Volver a unirse, pero ningún usuario puede volver a unirse mientras el usuario afectado está en modo resistencia.  <br/> |Todas las modalidades ahora funcionan. Todos los participantes deben hacer clic para volver a unirse a la conferencia.  <br/> |
|Conferencias en curso organizadas por un usuario no afectado  <br/> |La conferencia continúa y el usuario afectado puede permanecer en la conferencia. El usuario afectado está restringido a lo que puede hacer en modo de resistencia.  <br/> |La conferencia continúa y el usuario afectado puede permanecer en la conferencia y todas las modalidades funcionan después de que el usuario salga del modo de resistencia.  <br/> |
|Programar o modificar reuniones programadas, crear conferencias ad hoc  <br/> |No es posible mientras el usuario está en modo de resistencia.  <br/> |Disponible para todas las modalidades.  <br/> |
|Presencia como la ven otros usuarios en el mismo grupo  <br/> |Presencia desconocida mientras el usuario ha iniciado sesión en el grupo de copias de seguridad durante el modo de resistencia.  <br/> |Muestra el último estado de presencia establecido por el usuario y ahora se reflejarán los cambios de presencia.  <br/> |
|Disponibilidad de lista de contactos y servicio de libreta de direcciones  <br/> |No disponible  <br/> |Disponible  <br/> |
|Todas las sesiones y modalidades punto a punto  <br/> |Disponible  <br/> |Disponible  <br/> |
   
**Experiencia del usuario para un usuario que se encuentra en un grupo no afectado durante la conmutación por recuperación de otro grupo de servidores**

|**Tarea de usuario**|**Durante la conmutación por recuperación**|**Después de la finalización de la conmutación por recuperación**|
|:-----|:-----|:-----|
|Visualización de la presencia del usuario afectado  <br/> |Muestra el último estado de presencia establecido por el usuario afectado.  <br/> |Funcionando. Los usuarios no afectados ven las actualizaciones realizadas por los usuarios afectados.  <br/> |
|Conferencias en curso organizadas por el usuario afectado  <br/> |Se terminan todas las modalidades de conferencia.  <br/> |Todas las modalidades ahora funcionan. Todos los participantes deben hacer clic para volver a unirse a la conferencia.  <br/> |
|Conferencias en curso organizadas por un usuario no afectado  <br/> |La conferencia continúa y el usuario afectado puede permanecer en la conferencia y todas las modalidades funcionan.  <br/> |La conferencia continúa y el usuario afectado puede permanecer en la conferencia y todas las modalidades funcionan.  <br/> |
|Todas las sesiones y modalidades punto a punto  <br/> |Disponible  <br/> |Disponible  <br/> |
   

