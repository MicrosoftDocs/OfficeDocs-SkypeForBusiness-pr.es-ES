---
title: Planificar la capacidad para el servidor de chat persistente en Skype Empresarial Server 2015
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/23/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7a850cd5-c789-4795-a8ff-083be21ae784
description: 'Resumen: Lea este tema para obtener más información acerca de la planeación de capacidad para el servidor de Chat persistente en Skype para Business Server 2015.'
ms.openlocfilehash: 08c360b26efd04c34ca1833b0c0022394f8c4ac2
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30898334"
---
# <a name="capacity-planning-for-persistent-chat-server-in-skype-for-business-server-2015"></a>Planificar la capacidad para el servidor de chat persistente en Skype Empresarial Server 2015
 
**Resumen:** Lea este tema para obtener más información acerca de la planeación de capacidad para el servidor de Chat persistente en Skype para Business Server 2015.
  
Persistent Chat Server puede realizar chat de varios usuario, en tiempo real que se puede conservar para búsqueda y recuperación futura. A diferencia de grupo mensajería instantánea (IM) que se guarda en el buzón del usuario si está configurado el historial de conversaciones, una sesión de servidor de Chat persistente ya permanece abierta y se guarda el contenido en un servidor, junto con los mensajes, los archivos, las direcciones URL y otros datos que forman parte de una conversación en curso.
  
Planeación de la capacidad es una parte importante de la preparación para implementar servidor de Chat persistente. Este tema brinda tablas para la planificación de la capacidad que puede usar para determinar cuál es la mejor configuración para su implementación. También se describe cómo administrar mejor las implementaciones de servidor de Chat persistente que requieren mayor capacidad en las horas punta.
  
Antes de leer esta sección, necesita conocer las topologías de chat persistente. Para obtener más información, consulte [Plan Persistent Chat Server topology](topology.md).

> [!NOTE] 
> Chat persistente está disponible en Skype para Business Server 2015, pero ya no se admite en Skype para Business Server 2019. La misma funcionalidad está disponible en los equipos. Para obtener más información, vea [viaje de Skype para la empresa a los equipos de Microsoft](/microsoftteams/journey-skypeforbusiness-teams). Si necesita usar chat en grupo, las opciones son para migrar los usuarios que requieren esta funcionalidad a los equipos, o para continuar usando Skype para Business Server 2015. 
  
## <a name="persistent-chat-server-capacity-planning"></a>Planeación de capacidad de servidor de Chat persistente

En las tablas siguientes pueden ayudarle con la planeación de capacidad para servidor de Chat persistente por cómo diferentes opciones de servidor de Chat persistente afectan a la capacidad de modelado.
  
- Planificar la capacidad para la cantidad de usuarios
    
- Planificar la capacidad para el acceso a los salones de chat
    
- Planear la capacidad para el acceso de salón de chat por invitación
    
- Planificar la capacidad para el rendimiento
    
### <a name="plan-capacity-for-number-of-users-for-persistent-chat-server"></a>Planear la capacidad para el número de usuarios para el servidor de Chat persistente

Usa la siguiente tabla de muestra para determinar la cantidad de usuarios que podrás admitir.
  
**Ejemplo de capacidad máxima de grupo de servidores de servidor de Chat persistente**

|||
|:-----|:-----|
|Instancias de servicio de Chat persistente activas  <br/> |4  <br/> |
|Instancias de servicio de Chat persistentes  <br/> |8 (solo un máximo de 4 pueden estar activas; 4 necesitan estar inactivas)  <br/> |
|Usuarios activos conectados  <br/> |80,000  <br/> |
|Cantidad total de usuarios aprovisionados  <br/> |150,000  <br/> |
|Cantidad de extremos  <br/> |120,000  <br/> |
   
En el ejemplo anterior, es el plan admitir el número máximo de usuarios que permite que el servidor de Chat persistente: cuatro servidores o instancias del servicio de Chat persistente (puede tener cuatro servidores más pasivos que ejecuta el servidor de Chat persistente para una alta disponibilidad y recuperación ante desastres) y 20.000 usuarios por servidor, para un total de 80.000 usuarios activos.
  
### <a name="plan-capacity-for-chat-room-access"></a>Planificar la capacidad para el acceso a los salones de chat

En la siguiente tabla de ejemplo que le ayudarán a planear la administración de acceso a los salones de chat en un grupo de servidores de Chat persistente.
  
**Muestra de la administración del acceso a los salones de chat**

||**Salones de chat pequeños**|**Salones de chat medianos**|**Salones de chat grandes**|**Total**|
|:-----|:-----|:-----|:-----|:-----|
|Tamaño de los salones de chat (cantidad de usuarios conectados)  <br/> |30 por salón  <br/> |150 por salón  <br/> |16 000 por salón  <br/> ||
|Salones de chat  <br/> |32,000  <br/> |1,067  <br/> |10  <br/> |33,077  <br/> |
|% de salones que son auditorios  <br/> |1 %  <br/> |1 %  <br/> |50%  <br/> ||
|% de salones que están abiertos  <br/> |3%  <br/> |3%  <br/> |50%  <br/> ||
|Salones abiertos (ninguna pertenencia explícita)  <br/> |960  <br/> |32  <br/> |5  <br/> |997  <br/> |
|Salones no abiertos (salones regulares con pertenencia explícita)  <br/> |31,040  <br/> |1.035  <br/> |5  <br/> |32,080  <br/> |
|Salones de auditorio (entrada de moderadores adicionales)  <br/> |0  <br/> |32  <br/> |5  <br/> ||
|Salones administrados por pertenencia directa  <br/> |50%  <br/> |10%  <br/> |0%  <br/> ||
|Salones administrados por grupos de usuarios  <br/> |50%  <br/> |90%  <br/> |100%  <br/> ||
|Grupos de usuarios en la lista de pertenencia de cada salón de chat para los salones abiertos (no especificado explícitamente)  <br/> |0  <br/> |0  <br/> |0  <br/> ||
|Usuarios en la lista de pertenencia de cada salón de chat para los salones no abiertos  <br/> |30  <br/> |150  <br/> |16,000  <br/> ||
|Grupos de usuarios en la lista de pertenencia de cada salón de chat para los salones no abiertos  <br/> |3  <br/> |5  <br/> |10  <br/> ||
|Usuarios y grupos de usuarios en la lista del administrador de cada salón de chat (para salones abiertos y no abiertos)  <br/> |6  <br/> |6  <br/> |6  <br/> ||
|Usuarios y grupos de usuarios en la lista de moderadores de cada salón de chat de auditorio (para salones abiertos y no abiertos)  <br/> |6  <br/> |6  <br/> |6  <br/> ||
|Entidades de pertenencia basadas en usuarios en todos los salones no abiertos  <br/> |465,600  <br/> |15,520  <br/> |-  <br/> ||
|Entidades de pertenencia basadas en grupos de usuarios en todos los salones no abiertos  <br/> |46,560  <br/> |4656  <br/> |50  <br/> ||
|Entidades basadas en usuarios y grupos de usuarios en todos los salones de chat de auditorio  <br/> |0  <br/> |192  <br/> |50  <br/> ||
|Entidades de administradores basadas en usuarios y grupos de usuarios en todas las listas de administrador de salones de chat  <br/> |192,000  <br/> |6,400  <br/> |60  <br/> ||
|Usuarios activos por salón de chat  <br/> |30  <br/> |150  <br/> |16,000  <br/> ||
|Salones de chat por usuario  <br/> |12  <br/> |2  <br/> |2  <br/> |16  <br/> |
|Grupos de usuarios en la lista de miembros de cada salón de chat  <br/> |10  <br/> |10  <br/> |15  <br/> ||
|Salones administrados por grupos de usuarios  <br/> |50%  <br/> |50%  <br/> |50%  <br/> ||
|Entidades de pertenencia basadas en grupos de usuarios en todos los salones de chat  <br/> |155,200  <br/> |5173  <br/> |68  <br/> ||
|Entidades de pertenencia basadas en usuarios en todos los salones de chat  <br/> |465,600  <br/> |77,600  <br/> |72,000  <br/> ||
|Usuarios y grupos de usuarios en las listas de administradores, moderadores y ámbitos de cada salón de chat  <br/> |6  <br/> |6  <br/> |6  <br/> ||
|Usuarios y grupos de usuarios en las listas de administradores, moderadores y ámbitos de todos los salones de chat  <br/> |192,000  <br/> |6400  <br/> |60  <br/> ||
|Entradas de control de acceso  <br/> |704,160  <br/> |26,768  <br/> |160  <br/> |731,088  <br/> |
|Máximo de entradas de control de acceso  <br/> ||||2,000,000  <br/> |
   
En el ejemplo anterior, al implementar los servidores de Chat persistente según las recomendaciones, pueden abarcar hasta 80.000 usuarios activos en un grupo de cuatro servidores con cumplimiento habilitado.
  
Esta muestra representa los salones de chat clasificados como pequeños (30 usuarios activos en un momento dado), medianos (150 usuarios activos) y grandes (16 000 usuarios activos). La cantidad de salones de chat de un tamaño determinado se calcula según la cantidad total de:
  
- Usuarios activos en el sistema
    
- Usuarios activos en los salones de chat del tamaño correspondiente
    
- Salones de chat del tamaño correspondiente a los que se una un solo usuario
    
Para cada salón de chat, la tabla de planificación de la capacidad anterior especifica la cantidad de entradas de control de acceso asociadas al salón de chat, incluidas las entradas asignadas directamente al salón de chat. Puedes controlar el acceso a salones de chat individuales al utilizar listas de control de acceso (ACL). También puedes controlar el acceso en cuanto a la categoría. En una ACL, una entrada de control de acceso individual puede corresponder a un grupo de usuarios (por ejemplo, un grupo de seguridad, una lista de distribución o a un solo usuario). Puedes definir las entradas de control de acceso de los administradores, los moderadores y los miembros de los salones de chat.
  
> [!IMPORTANT]
> A la hora de planificar tu estrategia para administrar los salones de chat, ten en cuenta que la cantidad total de entradas de control de acceso permitida es 2 millones. Si las entradas de control de acceso que calcules superan los 2 millones, el rendimiento del servidor puede disminuir en gran medida. Para evitar este problema, siempre que sea posible, asegúrate de que las entradas de control de acceso sean grupos de usuarios, en lugar de usuarios individuales. 
  
### <a name="plan-capacity-for-managing-chat-room-access-by-invitation"></a>Planificar la capacidad para administrar el acceso a los salones de chat por invitación

Puede usar la siguiente tabla de planeación de capacidad para comprender el número de las invitaciones que Persistent Chat Server crea y almacena en la base de datos de Chat persistente cuando está configurado para enviar invitaciones. Administrar las invitaciones en la categoría mediante el uso de la página de **configuración de las categorías de salón de Chat** en el Skype para el Panel de Control de servidor empresarial o mediante el cmdlet de Windows PowerShell, **set-csPersistentChatCategory**. Puede administrar las invitaciones en un salón de chat (en línea con lo que permite la categoría) mediante el uso de la página de **Administración de la sala** inicia desde el Skype para clientes empresariales, o mediante el uso de un cmdlet de Windows PowerShell, **set-csPersistentChatRoom**.
  
Los datos de muestra de la siguiente tabla presuponen que, en la página **Configuración de salones de chat** para el 50 % de los salones de chat, la opción **Invitaciones** se ha configurado como **Sí**.
  
> [!IMPORTANT]
> Si el valor calculado para la cantidad de invitaciones que el servidor genera supera 1 millón, el rendimiento del servidor puede disminuir en gran medida. Para evitar este problema, asegúrese de que minimizar el número de salones de chat que están configurados para enviar invitaciones o restringir el número de usuarios que pueden unirse a salones de chat que se han configurado para enviar invitaciones. 
  
**Muestra del acceso a salones de chat por invitación**

||**Salones de chat pequeños**|**Salones de chat medianos**|**Salones de chat grandes**|**Total**|
|:-----|:-----|:-----|:-----|:-----|
|Usuarios que pueden tener acceso a salones de chat  <br/> |30 por salón  <br/> |150 por salón  <br/> |16 000 por salón  <br/> ||
|Porcentaje de salones que disponen de invitaciones  <br/> |50%  <br/> |50%  <br/> |50%  <br/> ||
|Salones de chat configurados para enviar invitaciones  <br/> |16,000  <br/> |533  <br/> |5  <br/> ||
|Usuarios que pueden acceder al salón de chat  <br/> |60  <br/> |225  <br/> |16,000  <br/> ||
|Invitaciones generadas por el servidor de Chat persistente  <br/> |960,000  <br/> |120,000  <br/> |80,000  <br/> |1,160,000  <br/> |
|Cantidad máxima de invitaciones permitidas  <br/> ||||2,000,000  <br/> |
|Modelo 1: Inicio con la cantidad esperada de mensajes por salón por día  <br/> |||||
|Tasa de chats por salón (por día)  <br/> |50  <br/> |500  <br/> |100  <br/> |650  <br/> |
|Tasa de chats (por segundo) en todos los salones  <br/> |55.56  <br/> |18.52  <br/> |0.03  <br/> |74  <br/> |
|Modelo 2: Inicio con la cantidad de mensajes publicados por usuario por día  <br/> |||||
|Tasa de chats por usuario por día  <br/> |15  <br/> |5  <br/> |0.1  <br/> |20  <br/> |
|Tasa de chats por salón (por día)  <br/> |38  <br/> |375  <br/> |800  <br/> |1,213  <br/> |
|Tasa de chats (por segundo) en todos los salones  <br/> |41.67  <br/> |13.89  <br/> |0.28  <br/> |56  <br/> |
   
### <a name="plan-capacity-for-persistent-chat-server-performance"></a>Planear la capacidad de rendimiento del servidor de Chat persistente

En la siguiente tabla se describe el modelo de usuario para el servidor de Chat persistente. Constituye la base de los requisitos de planificación de la capacidad y representa una organización típica con 80 000 usuarios simultáneos, en cuatro servidores.
  
**Modelo de usuario de rendimiento de servidor de Chat persistente**

|||
|:-----|:-----|
|Cantidad de usuarios activos conectados  <br/> |80,000  <br/> |
|Número de instancias de servicio del servidor de Chat persistente  <br/> |4  <br/> |
|Tamaño de salones de chat pequeños  <br/> |30 usuarios  <br/> |
|Tamaño de salones de chat medianos  <br/> |150 usuarios  <br/> |
|Tamaño de salones de chat grandes  <br/> |16 000 usuarios  <br/> |
|Cantidad total de salones de chat  <br/> |33,077  <br/> |
|Cantidad de salones de chat pequeños  <br/> |32,000  <br/> |
|Cantidad de salones de chat medianos  <br/> |1,067  <br/> |
|Cantidad de salones de chat grandes  <br/> |10  <br/> |
|Cantidad total de salones de chat por usuario  <br/> |16  <br/> |
|Cantidad de salones de chat pequeños por usuario  <br/> |12  <br/> |
|Cantidad de salones de chat medianos por usuario  <br/> |2  <br/> |
|Cantidad de salones de chat grandes por usuario  <br/> |2  <br/> |
|Cantidad de salones a los que se han unido por usuario  <br/> |24  <br/> |
|Tasa máxima de uniones  <br/> |10/segundo  <br/> |
|Tasa de chats total  <br/> |24/segundo  <br/> |
|Tasa de chats en salones de chat pequeños  <br/> |22.22/second  <br/> |
|Tasa de chats en salones de chat medianos  <br/> |1.67/second  <br/> |
|Tasa de chats en salones de chat grandes  <br/> |~0.15/second  <br/> |
|Porcentaje de salones de chat configurados con invitaciones  <br/> |50%  <br/> |
|Porcentaje de pertenencia directa  <br/> |50%  <br/> |
|Porcentaje de pertenencia de grupo  <br/> |50%  <br/> |
|Número medio de afiliaciones de antecesores en servicios de dominio de Active Directory  <br/> |100 - 200  <br/> |
|Cantidad de contactos suscritos por usuario  <br/> |80  <br/> |
|Cantidad promedio de extremos por usuario  <br/> |1.5  <br/> |
|Cantidad promedio de salones de chat visibles por extremo  <br/> |1.5  <br/> |
|Cantidad promedio de salones de chat visibles por usuario  <br/> |2,25 (50% para 1 salón y 50% para 2 salones); hasta 6 salones abiertos, uno por monitor  <br/> |
|Cantidad de participantes sondeados por intervalo  <br/> |25 por salón de chat visible  <br/> |
|Longitud del intervalo de sondeo  <br/> |5 minutos  <br/> |
|Cantidad de participantes sondeados por segundo  <br/> |15,000  <br/> |
|Cantidad de cambios de presencia por hora y usuario  <br/> |6  <br/> |
|Cantidad de cambios de presencia por segundo  <br/> |133.33  <br/> |
   

