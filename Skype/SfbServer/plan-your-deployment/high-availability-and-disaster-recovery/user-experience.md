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
description: Obtenga información sobre lo que experimentan los usuarios cuando un grupo de servidores front-end conmuta por error o conmuta por recuperación durante la recuperación ante desastres en Skype Empresarial Server.
ms.openlocfilehash: 137ad9076febccb272e88e457ee56e6474cff107
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809910"
---
# <a name="user-experience-during-pool-failure-in-skype-for-business-server"></a>Experiencia del usuario durante el error del grupo en Skype Empresarial Server
 
Obtenga información sobre lo que experimentan los usuarios cuando un grupo de servidores front-end conmuta por error o conmuta por recuperación durante la recuperación ante desastres en Skype Empresarial Server.
  
Si se ha con error en un grupo de servidores, todos los usuarios del grupo afectado se ven obligados a cerrar sesión y, a continuación, iniciar sesión en el grupo de copia de seguridad. Durante un breve período, los usuarios que inician sesión en el grupo de copia de seguridad pueden estar en modo de resistencia. En el modo de resistencia, los usuarios no pueden realizar tareas que provocarían un cambio persistente en Skype Empresarial Server, como agregar un contacto. Una vez completada la conmutación por error, todos los usuarios pueden obtener todos los servicios del grupo de servidores de copia de seguridad.
  
Las llamadas, reuniones o conversaciones que tenga un usuario cuando se produzca un error en el grupo de servidores se interrumpen y el usuario debe volver a establecer esas sesiones después de la conmutación por error para continuar.
  
Los usuarios no se vuelve a internar durante la conmutación por error o la conmutación por recuperación. El grupo de copia de seguridad atenderá temporalmente a los usuarios que se encuentran en un grupo de servidores que genera un error. Cuando se restaura el grupo de servidores principal, el administrador puede conmutar por recuperación a estos usuarios para que sean atendidos por su grupo de servidores original, donde aún están albergados.
  
Tenga en cuenta que la base de datos del servidor de información de ubicación no se replica en el grupo de copia de seguridad. Para un procedimiento recomendado, el administrador debe realizar periódicamente una copia de seguridad de la base de datos LIS y usar la copia de seguridad más reciente para restaurar la base de datos LIS en el grupo de servidores de copia de seguridad después de la conmutación por error.
  
## <a name="user-experience-during-failover"></a>Experiencia del usuario durante la conmutación por error

Cuando un usuario se encuentra en un grupo de servidores que genera un error, el usuario ha cerrado la sesión. Todas las sesiones punto a punto en las que participaba el usuario finalizan, al igual que las conferencias organizadas por ese usuario. El usuario no puede volver a iniciar sesión hasta que expire el temporizador de resistencia del registrador o el administrador inicie los procedimientos de conmutación por error, lo que sea lo primero. Cuando el usuario vuelve a iniciar sesión, inicia sesión en el grupo de copia de seguridad. Si inician sesión antes de que finalice la conmutación por error, estarán en modo de resistencia hasta que se complete la conmutación por error. Solo entonces un usuario puede establecer nuevas sesiones o volver a establecer sesiones anteriores.
  
## <a name="user-experience-during-failback"></a>Experiencia del usuario durante la conmutación por recuperación

La conmutación por recuperación del grupo de servidores puede producirse mientras un usuario afectado ha iniciado sesión en el grupo de copia de seguridad y el usuario permanece conectado y trabajando durante la conmutación por recuperación. Tenga en cuenta que el proceso de conmutación por recuperación tarda varios minutos en completarse. Como referencia, un grupo de 20.000  usuarios suele tardar 60 minutos.
  
En las tablas siguientes se muestran más detalles sobre cómo se ve afectado un usuario durante y después de la conmutación por recuperación, y también cómo los usuarios de otros grupos ven e interactúan con un usuario de un grupo de servidores al que se le está conmutando la conmutación por recuperación. 
  
El término usuario afectado hace referencia a cualquier usuario con error del grupo de servidores principal y al que el grupo de copia de seguridad está prestando servicio. Un usuario originalmente albergado en el grupo de copia de seguridad no es un usuario afectado.
  
**Experiencia del usuario para un usuario afectado en un grupo de servidores en conmutación por recuperación**

|**Estado o tarea del usuario**|**Durante la conmutación por recuperación**|**Después de la finalización de la conmutación por recuperación**|
|:-----|:-----|:-----|
|Estado de usuario del usuario que ya ha iniciado sesión  <br/> |El usuario permanece conectado y conectado al grupo de copia de seguridad. En algún momento, el usuario cerrará la sesión y volverá a iniciar sesión en el grupo principal original, en modo de resistencia.  <br/> |El usuario permanece iniciado sesión y pasa al modo normal.  <br/> |
|Nuevo inicio de sesión de usuario  <br/> |El usuario puede iniciar sesión en el grupo principal en modo de resistencia.  <br/> |El usuario puede iniciar sesión en el grupo principal original en modo normal.  <br/> |
|Conferencias continuas organizadas por el usuario afectado  <br/> |Se finalizan todas las modalidades de conferencia. Aparecerá el botón Volver a unirse, pero ningún usuario puede volver a unirse mientras el usuario afectado está en modo de resistencia.  <br/> |Ahora funcionan todas las modalidades. Todos los participantes deben hacer clic para volver a unirse a la conferencia.  <br/> |
|Conferencias en curso organizadas por usuarios no afectados  <br/> |La conferencia continúa y el usuario afectado puede permanecer en la conferencia. El usuario afectado está restringido a lo que puede hacer en modo de resistencia.  <br/> |La conferencia continúa y el usuario afectado puede permanecer en la conferencia y todas las modalidades funcionan después de que el usuario salga del modo de resistencia.  <br/> |
|Programar o modificar reuniones programadas, crear conferencias ad-hoc  <br/> |No es posible mientras el usuario está en modo de resistencia.  <br/> |Disponible para todas las modalidades.  <br/> |
|Presencia como la ven otros usuarios en el mismo grupo de servidores  <br/> |Presencia desconocida mientras el usuario ha iniciado sesión en el grupo de copia de seguridad durante el modo de resistencia.  <br/> |Muestra el último estado de presencia establecido por el usuario y ahora se reflejarán los cambios de presencia.  <br/> |
|Disponibilidad de lista de contactos y servicio de libreta de direcciones  <br/> |No disponible  <br/> |Disponible  <br/> |
|Todas las sesiones y modalidades punto a punto  <br/> |Disponible  <br/> |Disponible  <br/> |
   
**Experiencia del usuario para un usuario que se encuentra en un grupo de servidores no afectado durante la conmutación por recuperación de otro grupo**

|**Tarea de usuario**|**Durante la conmutación por recuperación**|**Después de la finalización de la conmutación por recuperación**|
|:-----|:-----|:-----|
|Visualización de la presencia del usuario afectado  <br/> |Muestra el último estado de presencia establecido por el usuario afectado.  <br/> |En funcionamiento. Los usuarios no afectados ven las actualizaciones realizadas por los usuarios afectados.  <br/> |
|Conferencias continuas organizadas por el usuario afectado  <br/> |Se finalizan todas las modalidades de conferencia.  <br/> |Ahora funcionan todas las modalidades. Todos los participantes deben hacer clic para volver a unirse a la conferencia.  <br/> |
|Conferencias en curso organizadas por usuarios no afectados  <br/> |La conferencia continúa y el usuario afectado puede permanecer en la conferencia y todas las modalidades funcionan.  <br/> |La conferencia continúa y el usuario afectado puede permanecer en la conferencia y todas las modalidades funcionan.  <br/> |
|Todas las sesiones y modalidades punto a punto  <br/> |Disponible  <br/> |Disponible  <br/> |
   

