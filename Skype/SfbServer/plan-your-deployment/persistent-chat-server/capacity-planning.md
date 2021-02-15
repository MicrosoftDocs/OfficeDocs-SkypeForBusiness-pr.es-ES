---
title: Planeación de capacidad para el servidor de chat persistente en Skype Empresarial Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/23/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 7a850cd5-c789-4795-a8ff-083be21ae784
description: 'Resumen: lea este tema para obtener información sobre la planeación de capacidad para el servidor de chat persistente en Skype Empresarial Server 2015.'
ms.openlocfilehash: d3d166f3b91ef0e7f711441387b4bef3d56f18b8
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49834580"
---
# <a name="capacity-planning-for-persistent-chat-server-in-skype-for-business-server-2015"></a>Planeación de capacidad para el servidor de chat persistente en Skype Empresarial Server 2015
 
**Resumen:** Lea este tema para obtener información sobre la planeación de capacidad para el servidor de chat persistente en Skype Empresarial Server 2015.
  
El servidor de chat persistente puede realizar chats en tiempo real de varios usuarios que pueden persistir para futuras recuperaciones y búsquedas. A diferencia de la mensajería instantánea (MI) de grupo que se guarda en el buzón de un usuario si se configura el historial de conversaciones, una sesión del servidor de chat persistente permanece abierta durante más tiempo y el contenido se guarda en un servidor, junto con los mensajes, archivos, direcciones URL y otros datos que forman parte de una conversación en curso.
  
La planeación de la capacidad es una parte importante de la preparación para implementar el servidor de chat persistente. En este tema se proporcionan tablas de planeación de capacidad que puede usar para determinar la mejor configuración para su implementación. También se describe cómo administrar mejor las implementaciones de servidores de chat persistente que requieren una mayor capacidad en horas pico.
  
Antes de leer esta sección, debe familiarizarse con las topologías de chat persistente. Para obtener más información, vea [Planear la topología del servidor de chat persistente.](topology.md)

> [!NOTE] 
> El chat persistente está disponible en Skype Empresarial Server 2015, pero ya no es compatible con Skype Empresarial Server 2019. La misma funcionalidad está disponible en Teams. Para obtener más información, consulte [Introducción a la actualización de Microsoft Teams.](/microsoftteams/upgrade-start-here) Si necesita usar el chat persistente, puede migrar usuarios que requieran esta funcionalidad a Teams o seguir usando Skype Empresarial Server 2015. 
  
## <a name="persistent-chat-server-capacity-planning"></a>Planeación de la capacidad del servidor de chat persistente

Las tablas siguientes pueden ayudarle con la planeación de capacidad para el servidor de chat persistente mediante el modelado de la forma en que diversas configuraciones del servidor de chat persistente afectan a la capacidad.
  
- Planeación de la capacidad para el número de usuarios
    
- Planeación de la capacidad para el acceso a los salón de chat
    
- Planeación de la capacidad para el acceso a los salón de chat por invitación
    
- Planeación de la capacidad de rendimiento
    
### <a name="plan-capacity-for-number-of-users-for-persistent-chat-server"></a>Planeación de la capacidad para el número de usuarios para el servidor de chat persistente

Use la siguiente tabla de ejemplo para determinar el número de usuarios que podrá admitir.
  
**Ejemplo de capacidad máxima del grupo de servidores de chat persistente**

|||
|:-----|:-----|
|Instancias del servicio de chat persistente activo  <br/> |4   <br/> |
|Instancias del servicio de chat persistente  <br/> |8 (solo un máximo de 4 puede estar activo; 4 debe estar inactivo)  <br/> |
|Usuarios activos conectados  <br/> |80,000  <br/> |
|Total de usuarios aprovisionados  <br/> |150,000  <br/> |
|Número de puntos de conexión  <br/> |120,000  <br/> |
   
En el ejemplo anterior, el plan es admitir el número máximo de usuarios que permite el servidor de chat persistente: cuatro servidores o instancias del servicio de chat persistente (pueden tener cuatro servidores pasivos más que ejecuten el servidor de chat persistente para alta disponibilidad y recuperación ante desastres) y 20 000 usuarios por servidor, para un total de 80 000 usuarios activos.
  
### <a name="plan-capacity-for-chat-room-access"></a>Planeación de la capacidad para el acceso a los salón de chat

La siguiente tabla de ejemplo puede ayudarle a planear la administración del acceso a los salas de chat en un grupo de servidores de chat persistente.
  
**Ejemplo de administración del acceso a los salón de chat**

||**Salas de chat pequeñas**|**Salas de chat medianas**|**Grandes salas de chat**|**Total**|
|:-----|:-----|:-----|:-----|:-----|
|Tamaño de los salas de chat (número de usuarios conectados)  <br/> |30 por sala  <br/> |150 por sala  <br/> |16 000 por sala  <br/> ||
|Salones de chat  <br/> |32,000  <br/> |1,067  <br/> |10    <br/> |33,077  <br/> |
|% de salas que son auditorio  <br/> |1%  <br/> |1%  <br/> |50%  <br/> ||
|% de salas que están abiertas  <br/> |3%  <br/> |3%  <br/> |50%  <br/> ||
|Salas abiertas (sin pertenencia explícita)  <br/> |960  <br/> |32  <br/> |5   <br/> |997  <br/> |
|Salas no abiertas (salas normales con pertenencia explícita)  <br/> |31,040  <br/> |1.035  <br/> |5   <br/> |32,080  <br/> |
|Salas de auditorio (entrada de presentadores adicionales)  <br/> |0  <br/> |32  <br/> |5   <br/> ||
|Salas administradas por pertenencia directa  <br/> |50%  <br/> |10%  <br/> |0 %  <br/> ||
|Salas administradas por grupos de usuarios  <br/> |50%  <br/> |90 %  <br/> |100 %  <br/> ||
|Grupos de usuarios en la lista de pertenencia de cada salón de chat para salas abiertas (no se especifica explícitamente)  <br/> |0  <br/> |0  <br/> |0  <br/> ||
|Usuarios de la lista de pertenencia de cada salón de chat para salas no abiertas  <br/> |30  <br/> |150  <br/> |16,000  <br/> ||
|Grupos de usuarios en la lista de pertenencia de cada salón de chat para salas no abiertas  <br/> |3   <br/> |5   <br/> |10    <br/> ||
|Usuarios y grupos de usuarios en la lista de administradores de cada salón de chat (para salas abiertas y no abiertas)  <br/> |6   <br/> |6   <br/> |6   <br/> ||
|Usuarios y grupos de usuarios en la lista de presentadores de cada salón de chat de auditorio (para salas abiertas y no abiertas)  <br/> |6   <br/> |6   <br/> |6   <br/> ||
|Entidades de pertenencia basadas en usuarios en todas las salas no abiertas  <br/> |465,600  <br/> |15,520  <br/> |-  <br/> ||
|Entidades de pertenencia basadas en grupos de usuarios en todas las salas no abiertas  <br/> |46,560  <br/> |4656  <br/> |50  <br/> ||
|Entidades basadas en usuarios y grupos de usuarios en todos los salas de chat de auditorio  <br/> |0  <br/> |192  <br/> |50  <br/> ||
|Entidades de administrador basadas en usuarios y grupos de usuarios en todas las listas de administradores de salas de chat  <br/> |192,000  <br/> |6,400  <br/> |60  <br/> ||
|Usuarios activos por salón de chat  <br/> |30  <br/> |150  <br/> |16,000  <br/> ||
|Salas de chat por usuario  <br/> |12   <br/> |2   <br/> |2   <br/> |16   <br/> |
|Grupos de usuarios en la lista de pertenencia de cada salón de chat  <br/> |10    <br/> |10    <br/> |15   <br/> ||
|Salas administradas por grupos de usuarios  <br/> |50%  <br/> |50%  <br/> |50%  <br/> ||
|Entidades de pertenencia basadas en grupos de usuarios en todos los salón de chat  <br/> |155,200  <br/> |5173  <br/> |68  <br/> ||
|Entidades de pertenencia basadas en usuarios en todos los salón de chat  <br/> |465,600  <br/> |77,600  <br/> |72,000  <br/> ||
|Usuarios y grupos de usuarios en las listas de administrador, moderador y ámbito de cada salón de chat  <br/> |6   <br/> |6   <br/> |6   <br/> ||
|Usuarios y grupos de usuarios en todas las listas de administradores, moderadores y ámbitos de todos los salón de chat  <br/> |192,000  <br/> |6400  <br/> |60  <br/> ||
|Entradas de control de acceso  <br/> |704,160  <br/> |26,768  <br/> |160  <br/> |731,088  <br/> |
|Número máximo de entradas de control de acceso  <br/> ||||2,000,000  <br/> |
   
En el ejemplo anterior, al implementar los servidores de chat persistente según las directrices recomendadas, pueden controlar hasta 80 000 usuarios activos en un grupo de cuatro servidores con cumplimiento habilitado.
  
En este ejemplo se muestran los salón de chat clasificados como pequeños (30 usuarios activos en un momento dado), medianos (150 usuarios activos) y grandes (16.000 usuarios activos). El número admitido de salas de chat de un tamaño determinado en la tabla anterior se calcula en función del número total de:
  
- Usuarios activos en el sistema
    
- Usuarios activos en salas de chat del tamaño especificado
    
- Salas de chat del tamaño especificado al que se une un único usuario
    
Para cada salón de chat, la tabla de planeación de capacidad anterior especifica el número de entradas de control de acceso asociadas con el salón de chat, incluidas las entradas asignadas directamente al salón de chat. Puede controlar el acceso a salas de chat individuales mediante listas de control de acceso (ACL). También puede controlar el acceso en el nivel de categoría. En una ACL, una entrada de control de acceso individual puede ser un grupo de usuarios, por ejemplo, un grupo de seguridad, una lista de distribución o un único usuario. Puede definir entradas de control de acceso para los administradores, presentadores y miembros del salón de chat.
  
> [!IMPORTANT]
> Al planear la estrategia para administrar los salas de chat, tenga en cuenta que el número total de entradas de control de acceso permitido es de 2 millones. Si las entradas de control de acceso calculado superan los 2 millones, el rendimiento del servidor podría degradarse significativamente. Para evitar este problema, siempre que sea posible, asegúrese de que las entradas de control de acceso son grupos de usuarios en lugar de usuarios individuales. 
  
### <a name="plan-capacity-for-managing-chat-room-access-by-invitation"></a>Planeación de la capacidad para administrar el acceso a los salón de chat por invitación

Puede usar la siguiente tabla de planeación de capacidad para comprender el número de invitaciones que crea y almacena el servidor de chat persistente en la base de datos de chat persistente cuando se configura para enviar invitaciones. Las invitaciones se administran  en la categoría mediante la página configuración de categoría de salón de chat en el Panel de control de Skype Empresarial Server, o mediante el cmdlet Windows PowerShell, **set-csPersistentChatCategory**. You can manage invitations on a chat room (in line with what the category allows) by using the **Room Management** page launched from the Skype for Business client, or by using a Windows PowerShell cmdlet, **set-csPersistentChatRoom**.
  
Los datos de ejemplo de la tabla  siguiente suponen que, en la página  Configuración del salón de chat para el 50 % de todos los salón de chat, la opción Invitaciones se establece en **Sí**.
  
> [!IMPORTANT]
> Si el valor calculado para el número de invitaciones generadas por el servidor supera el millón, el rendimiento del servidor podría degradarse significativamente. Para evitar este problema, asegúrese de minimizar el número de salas de chat configuradas para enviar invitaciones o restringir el número de usuarios que pueden unirse a los salas de chat que se han configurado para enviar invitaciones. 
  
**Acceso a la sala de chat por ejemplo de invitación**

||**Salas de chat pequeñas**|**Salas de chat medianas**|**Grandes salas de chat**|**Total**|
|:-----|:-----|:-----|:-----|:-----|
|Usuarios que pueden acceder al salón de chat  <br/> |30 por sala  <br/> |150 por sala  <br/> |16 000 por sala  <br/> ||
|Porcentaje de salas que tienen invitaciones  <br/> |50%  <br/> |50%  <br/> |50%  <br/> ||
|Salas de chat configuradas para enviar invitaciones  <br/> |16,000  <br/> |533  <br/> |5   <br/> ||
|Usuarios que pueden acceder al salón de chat  <br/> |60  <br/> |225  <br/> |16,000  <br/> ||
|Invitaciones generadas por el servidor de chat persistente  <br/> |960,000  <br/> |120,000  <br/> |80,000  <br/> |1,160,000  <br/> |
|Número máximo permitido de invitaciones  <br/> ||||2,000,000  <br/> |
|Modelo 1: comience con el número esperado de mensajes por sala y día  <br/> |||||
|Tasa de chat por salón (por día)  <br/> |50  <br/> |500  <br/> |100  <br/> |650  <br/> |
|Tasa de chat (por segundo) en todos los salas  <br/> |55.56  <br/> |18.52  <br/> |0.03  <br/> |74  <br/> |
|Modelo 2: Empezar con el número de mensajes publicados por usuario y día  <br/> |||||
|Tasa de chat por usuario y día  <br/> |15   <br/> |5   <br/> |0.1  <br/> |20  <br/> |
|Tasa de chat por salón (por día)  <br/> |38  <br/> |375  <br/> |800  <br/> |1,213  <br/> |
|Tasa de chat (por segundo) en todos los salas  <br/> |41.67  <br/> |13.89  <br/> |0.28  <br/> |56  <br/> |
   
### <a name="plan-capacity-for-persistent-chat-server-performance"></a>Planeación de la capacidad para el rendimiento del servidor de chat persistente

En la tabla siguiente se describe el modelo de usuario para el servidor de chat persistente. Proporciona la base para los requisitos de planeación de capacidad y representa una organización típica con 80 000 usuarios simultáneos en cuatro servidores.
  
**Modelo de usuario de rendimiento del servidor de chat persistente**

|||
|:-----|:-----|
|Número de usuarios activos conectados  <br/> |80,000  <br/> |
|Número de instancias de servicio del servidor de chat persistente  <br/> |4   <br/> |
|Tamaño de los pequeños salón de chat  <br/> |30 usuarios  <br/> |
|Tamaño de los salas de chat medianas  <br/> |150 usuarios  <br/> |
|Tamaño de los grandes salas de chat  <br/> |16 000 usuarios  <br/> |
|Número total de salas de chat  <br/> |33,077  <br/> |
|Número de salas de chat pequeñas  <br/> |32,000  <br/> |
|Número de salas de chat medianas  <br/> |1,067  <br/> |
|Número de salas de chat grandes  <br/> |10    <br/> |
|Número total de salas de chat por usuario  <br/> |16   <br/> |
|Número de salas de chat pequeñas por usuario  <br/> |12   <br/> |
|Número de salas de chat medianas por usuario  <br/> |2   <br/> |
|Número de salas de chat grandes por usuario  <br/> |2   <br/> |
|Número de salas unidas por usuario  <br/> |24  <br/> |
|Velocidad máxima de combinación  <br/> |10/segundo  <br/> |
|Tasa total de chat  <br/> |24/segundo  <br/> |
|Tasa de chat para salas de chat pequeñas  <br/> |22,22/segundo  <br/> |
|Tasa de chat para salas de chat medianas  <br/> |1,67/segundo  <br/> |
|Tasa de chat para grandes salas de chat  <br/> |~0,15/segundo  <br/> |
|Porcentaje de salas de chat configuradas para invitaciones  <br/> |50%  <br/> |
|Porcentaje de pertenencias directas  <br/> |50%  <br/> |
|Porcentaje de pertenencias a grupos  <br/> |50%  <br/> |
|Número medio de afiliaciones antecesores en los Servicios de dominio de Active Directory  <br/> |100 - 200  <br/> |
|Número de contactos suscritos por usuario  <br/> |80  <br/> |
|Número medio de puntos de conexión por usuario  <br/> |1,5  <br/> |
|Promedio de salas de chat visibles por extremo  <br/> |1,5  <br/> |
|Promedio de salas de chat visibles por usuario  <br/> |2,25 (50 % para 1 sala y 50 % para 2 salas); Hasta 6 salas abiertas, una por monitor  <br/> |
|Número de participantes sondeados por intervalo  <br/> |25 por salón de chat visible  <br/> |
|Duración del intervalo de sondeo  <br/> |5 minutos  <br/> |
|Número de participantes sondeados por segundo  <br/> |15.000  <br/> |
|Número de cambios de presencia por hora por usuario  <br/> |6   <br/> |
|Número de cambios de presencia por segundo  <br/> |133.33  <br/> |
   

