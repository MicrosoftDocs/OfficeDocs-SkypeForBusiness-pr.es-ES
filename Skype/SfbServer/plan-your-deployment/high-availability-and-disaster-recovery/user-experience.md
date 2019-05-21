---
title: Experiencia de usuario durante la falla de un grupo de servidores de Skype empresarial
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: b224b0d0-87e3-4cac-ae87-f45f54fabb49
description: Obtenga más información sobre lo que experimentan los usuarios cuando un grupo de servidores front-end conmuta por error o vuelve a producirse durante la recuperación ante desastres en Skype empresarial Server.
ms.openlocfilehash: cc8ea8c51bebcffdbf0873f2f1a355cd648b6df0
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34297235"
---
# <a name="user-experience-during-pool-failure-in-skype-for-business-server"></a>Experiencia de usuario durante la falla de un grupo de servidores de Skype empresarial
 
Obtenga más información sobre lo que experimentan los usuarios cuando un grupo de servidores front-end conmuta por error o vuelve a producirse durante la recuperación ante desastres en Skype empresarial Server.
  
Si se produce una conmutación por error en un grupo, se obliga a todos los usuarios del grupo afectado a cerrar sesión y, luego, a iniciar sesión en el grupo de copia de seguridad. Durante un período breve los usuarios que inicien sesión en el grupo de copia de seguridad pueden encontrarse en modo de resistencia. En el modo de resistencia, los usuarios no pueden realizar tareas que provocarían un cambio continuo en Skype empresarial Server, como agregar un contacto. Una vez finalizada la conmutación por error, todos los usuarios pueden utilizar todos los servicios del grupo de copia de seguridad.
  
Cuando se produce un error en el grupo, se interrumpen todas las llamadas, las reuniones y las conversaciones, y el usuario debe volver a establecer estas sesiones tras la conmutación por error.
  
No se vuelven a ubicar los usuarios durante la conmutación por error o la conmutación por recuperación. Los usuarios que están hospedados en un grupo donde se produce un error se hospedarán temporalmente en el grupo de copia de seguridad. Cuando se restaura el grupo principal, el administrador puede llevar a cabo la conmutación por recuperación de esos usuarios para que vuelven a hospedarse en su grupo original.
  
Ten en cuenta que no se replica la base de datos del servidor de información de ubicación en el grupo de copia de seguridad. Como procedimiento recomendado, el administrador tiene que realizar una copia de seguridad de la base de datos LIS periódicamente y usar la última versión de dicha copia para restaurar la base de datos LIS en el grupo de copia de seguridad tras la conmutación por error.
  
## <a name="user-experience-during-failover"></a>Experiencia del usuario durante la conmutación por error

Cuando un usuario se encuentra en un grupo donde se produce un error, su sesión se cierra. Se finaliza cualquier sesión punto a punto en la que participe el usuario, como las conferencias organizadas por ese usuario. El usuario no puede volver a iniciar sesión hasta que caduque el temporizador de resistencia del registrador o el administrador inicie los procedimientos de conmutación por error, lo que ocurra primero. Cuando el usuario reinicia sesión, iniciará la sesión en el grupo de copia de seguridad. Si inicia sesión antes de que finalice la conmutación por error, estará en modo de resistencia hasta que finalice la conmutación por error. Solamente entonces el usuario podrá establecer nuevas sesiones o restablecer las sesiones anteriores.
  
## <a name="user-experience-during-failback"></a>Experiencia del usuario durante la conmutación por recuperación

La conmutación por recuperación de un grupo puede ocurrir cuando un usuario afectado ha iniciado sesión en el grupo de copia de seguridad y el usuario permanece conectado y sigue trabajando durante la conmutación por recuperación. Ten en cuenta que el proceso de conmutación por recuperación tarda varios minutos en completarse. Como referencia, se espera que tarde 60 minutos como máximo para un grupo de 20 000 usuarios.
  
Las siguientes tablas muestran más detalles sobre cómo un usuario se ve afectado durante y después de la conmutación por recuperación y también cómo los usuarios de otros grupos ven e interactúan con un usuario en un grupo que está en proceso de conmutación por recuperación. 
  
El término usuario afectado hace referencia a cualquier usuario que sufrió una conmutación por error en el grupo principal y está hospedado ahora en el grupo de copia de seguridad. Un usuario originalmente hospedado en el grupo de copia de seguridad no es un usuario afectado.
  
**Experiencia de un usuario afectado en un grupo de conmutación por recuperación**

|**Tarea o estado del usuario**|**Durante la conmutación por recuperación**|**Una vez finalizada la conmutación por recuperación**|
|:-----|:-----|:-----|
|Estado del usuario que ya ha iniciado sesión  <br/> |El usuario permanece en su sesión y sigue conectado al grupo de copia de seguridad. En algún momento, se cerrará la sesión del usuario y volverá a la sesión en el grupo principal original, en el modo de resistencia.  <br/> |El usuario continúa en su sesión y se coloca en modo normal.  <br/> |
|Inicio de sesión de un nuevo usuario  <br/> |El usuario puede iniciar sesión en el grupo principal en el modo de resistencia.  <br/> |El usuario puede iniciar sesión en el grupo principal original en modo normal.  <br/> |
|Conferencias en curso organizadas por un usuario afectado  <br/> |Se terminan todas las modalidades de conferencia. Se mostrará el botón Unirse de nuevo, pero ningún usuario puede volver a unirse mientras el usuario afectado está en modo de resistencia.  <br/> |Ahora funcionan todas las modalidades. Cada participante tiene que hacer clic para volver a unirse a la conferencia.  <br/> |
|Conferencias en curso organizadas por un usuario no afectado  <br/> |La conferencia continúa y el usuario afectado puede permanecer en la conferencia. El usuario afectado está limitado a lo que se puede hacer en el modo de resistencia.  <br/> |La conferencia continúa y el usuario afectado puede permanecer en la conferencia y todas las modalidades funcionan después de que el usuario sale del modo de resistencia.  <br/> |
|Programación o modificación de las reuniones programadas, creación de conferencias ad-hoc  <br/> |No son posibles mientras el usuario está en modo de resistencia.  <br/> |Disponibles para todas las modalidades.  <br/> |
|Presencia según otros usuarios en el mismo grupo  <br/> |Presencia desconocida mientras el usuario está conectado al grupo de copia de seguridad durante el modo de resistencia.  <br/> |Muestra el último estado de presencia establecido por el usuario, y los cambios de presencia ahora se reflejarán.  <br/> |
|Disponibilidad del servicio de la libreta de direcciones y la lista de contactos  <br/> |No disponible  <br/> |Disponible  <br/> |
|Todas las sesiones punto a punto y las modalidades  <br/> |Disponible  <br/> |Disponible  <br/> |
   
**Experiencia de un usuario hospedado en un grupo de servidores no afectado durante la conmutación por recuperación de otro grupo**

|**Tarea de usuario**|**Durante la conmutación por recuperación**|**Una vez finalizada la conmutación por recuperación**|
|:-----|:-----|:-----|
|Visualización de la presencia del usuario afectado  <br/> |Muestra el último estado de presencia establecido por el usuario afectado.  <br/> |En funcionamiento. Los usuarios no afectados verán las actualizaciones realizadas por los usuarios afectados.  <br/> |
|Conferencias en curso organizadas por un usuario afectado  <br/> |Se terminan todas las modalidades de conferencia.  <br/> |Ahora funcionan todas las modalidades. Cada participante tiene que hacer clic para volver a unirse a la conferencia.  <br/> |
|Conferencias en curso organizadas por un usuario no afectado  <br/> |La conferencia continúa, el usuario afectado puede permanecer en la conferencia y funcionan todas las modalidades.  <br/> |La conferencia continúa, el usuario afectado puede permanecer en la conferencia y funcionan todas las modalidades.  <br/> |
|Todas las sesiones punto a punto y las modalidades  <br/> |Disponible  <br/> |Disponible  <br/> |
   

