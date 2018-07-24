---
title: Experiencia del usuario durante error de grupo de servidores en Skype para Business Server
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: b224b0d0-87e3-4cac-ae87-f45f54fabb49
description: Obtenga información sobre lo que los usuarios experimentan cuando un grupo de servidores Front-End conmuta por error o se produce un error durante la recuperación ante desastres en Skype para Business Server.
ms.openlocfilehash: 741eb40d0bf4ee615d68d05ab6b9543b6f65474b
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2018
ms.locfileid: "21001192"
---
# <a name="user-experience-during-pool-failure-in-skype-for-business-server"></a>Experiencia del usuario durante error de grupo de servidores en Skype para Business Server
 
Obtenga información sobre lo que los usuarios experimentan cuando un grupo de servidores Front-End conmuta por error o se produce un error durante la recuperación ante desastres en Skype para Business Server.
  
Si se produce una conmutación por error en un grupo, se obliga a todos los usuarios del grupo afectado a cerrar sesión y, luego, a iniciar sesión en el grupo de copia de seguridad. Durante un período breve los usuarios que inicien sesión en el grupo de copia de seguridad pueden encontrarse en modo de resistencia. En modo de resistencia, los usuarios son lleven a cabo las tareas que hará que un cambio persistente en Skype para Business Server, como agregar un contacto. Una vez finalizada la conmutación por error, todos los usuarios pueden utilizar todos los servicios del grupo de copia de seguridad.
  
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
   

