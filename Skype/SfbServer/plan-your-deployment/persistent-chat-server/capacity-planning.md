---
title: Planeación de capacidad para el servidor de chat persistente en Skype Empresarial Server 2015
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/23/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 7a850cd5-c789-4795-a8ff-083be21ae784
description: 'Resumen: lea este tema para obtener información sobre la planeación de capacidad para el servidor de chat persistente en Skype Empresarial Server 2015.'
ms.openlocfilehash: 48df53528b31babe6419bc42ac303b810abdf197
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/05/2022
ms.locfileid: "62390002"
---
# <a name="capacity-planning-for-persistent-chat-server-in-skype-for-business-server-2015"></a>Planeación de capacidad para el servidor de chat persistente en Skype Empresarial Server 2015
 
**Resumen:** Lea este tema para obtener información sobre la planeación de capacidad para el servidor de chat persistente en Skype Empresarial Server 2015.
  
El servidor de chat persistente puede realizar chat multiusual en tiempo real que puede persistir para futuras recuperaciones y búsquedas. A diferencia de la mensajería instantánea de grupo (MI) que se guarda en el buzón de un usuario si se configura el historial de conversaciones, una sesión del servidor de chat persistente permanece abierta más tiempo y el contenido se guarda en un servidor, junto con los mensajes, archivos, direcciones URL y otros datos que forman parte de una conversación en curso.
  
La planeación de capacidad es una parte importante de la preparación para implementar el servidor de chat persistente. En este tema se proporcionan tablas de planeación de capacidad que puede usar para determinar la mejor configuración para la implementación. También describe cómo administrar mejor las implementaciones del servidor de chat persistente que requieren una mayor capacidad en las horas pico.
  
Antes de leer esta sección, debe estar familiarizado con las topologías de chat persistente. Para obtener más información, vea [Plan Persistent Chat Server topology](topology.md).

> [!NOTE] 
> El chat persistente está disponible en Skype Empresarial Server 2015, pero ya no se admite en Skype Empresarial Server 2019. La misma funcionalidad está disponible en Teams. Para obtener más información, consulte [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here). Si necesita usar el chat persistente, las opciones son migrar usuarios que requieren esta funcionalidad a Teams, o bien seguir usando Skype Empresarial Server 2015. 
  
## <a name="persistent-chat-server-capacity-planning"></a>Planeación de capacidad del servidor de chat persistente

Las tablas siguientes pueden ayudarle con la planeación de capacidad para el servidor de chat persistente mediante el modelado de cómo afectan las distintas opciones de configuración del servidor de chat persistente a la capacidad.
  
- Planear la capacidad para el número de usuarios
    
- Planear la capacidad para el acceso al salón de chat
    
- Planear la capacidad para el acceso al salón de chat por invitación
    
- Planear la capacidad de rendimiento
    
### <a name="plan-capacity-for-number-of-users-for-persistent-chat-server"></a>Planear la capacidad del número de usuarios para el servidor de chat persistente

Use la siguiente tabla de ejemplo para determinar el número de usuarios que podrá admitir.
  
**Ejemplo de capacidad máxima del grupo de servidores de chat persistente**

- Instancias del servicio de chat persistente activo: 4  <br/> 
- Instancias de servicio de chat persistente: 8 (un máximo de 4 puede estar activo; 4 debe estar inactivo)  <br/>
- Usuarios activos conectados: 80.000  <br/>
- Total de usuarios aprovisionados: 150 000  <br/>
- Número de puntos de conexión: 120 000  <br/>
   
En el ejemplo anterior, el plan es admitir el número máximo de usuarios que permite el servidor de chat persistente: cuatro servidores o instancias del servicio de chat persistente (puede tener cuatro servidores pasivos más que ejecuten el servidor de chat persistente para alta disponibilidad y recuperación ante desastres) y 20.000 usuarios por servidor, para un total de 80.000 usuarios activos.
  
### <a name="plan-capacity-for-chat-room-access"></a>Planear la capacidad para el acceso al salón de chat

La siguiente tabla de ejemplo puede ayudarle a planear la administración del acceso al salón de chat en un grupo de servidores de chat persistente.
  
**Ejemplo de administración de acceso al salón de chat**

|&nbsp;|Salas de chat pequeñas|Salas de chat medianas|Salas de chat grandes|Total|
|:-----|:-----|:-----|:-----|:-----|
|Tamaño de los salas de chat (número de usuarios conectados)   |30 por sala   |150 por sala   |16 000 por sala   ||
|Salones de chat   |32,000   |1,067   |10   |33,077   |
|% de salas que son auditorio   |1%   |1%   |50%   ||
|% de salas que están abiertas   |3%   |3%   |50%   ||
|Salas abiertas (sin pertenencia explícita)   |960   |32   |5   |997   |
|Salas no abiertas (salas regulares con pertenencia explícita)   |31,040   |1.035   |5   |32,080   |
|Salas de auditorio (entrada de presentadores adicionales)   |0   |32   |5   ||
|Salas administradas por pertenencia directa   |50%   |10%   |0%   ||
|Salas administradas por grupos de usuarios   |50%   |90 %   |100 %   ||
|Grupos de usuarios en la lista de pertenencia de cada salón de chat para salas abiertas (no especificada explícitamente)   |0   |0   |0   ||
|Usuarios de la lista de miembros de cada salón de chat para salas no abiertas   |30   |150   |16,000   ||
|Grupos de usuarios en la lista de pertenencia de cada salón de chat para salas no abiertas   |3   |5   |10   ||
|Usuarios y grupos de usuarios en la lista de administradores de cada salón de chat (para salas abiertas y no abiertas)   |6    |6    |6    ||
|Usuarios y grupos de usuarios en la lista de presentadores de cada salón de chat de auditorio (para salas abiertas y no abiertas)   |6    |6    |6    ||
|Entidades de pertenencia basadas en usuarios en todas las salas no abiertas   |465,600   |15,520   |-   ||
|Entidades de pertenencia basadas en grupos de usuarios en todas las salas no abiertas   |46,560   |4656   |50   ||
|Entidades basadas en usuarios y grupos de usuarios en todos los salas de chat del auditorio   |0   |192   |50   ||
|Usuarios y entidades de administrador basadas en grupos de usuarios en todas las listas de administradores de salas de chat   |192,000   |6,400   |60   ||
|Usuarios activos por salón de chat   |30   |150   |16,000   ||
|Salas de chat por usuario   |12    |2   |2   |16   |
|Grupos de usuarios en la lista de pertenencia de cada salón de chat   |10   |10   |15    ||
|Salas administradas por grupos de usuarios   |50%   |50%   |50%   ||
|Entidades de pertenencia basadas en grupos de usuarios en todos los salón de chat   |155,200   |5173   |68   ||
|Entidades de pertenencia basadas en usuarios en todos los salón de chat   |465,600   |77,600   |72,000   ||
|Usuarios y grupos de usuarios en las listas de administrador, moderador y ámbito de cada salón de chat   |6    |6    |6    ||
|Usuarios y grupos de usuarios en todas las listas de administradores, moderadores y ámbitos de todos los salas de chat   |192,000   |6400   |60   ||
|Entradas de control de acceso   |704,160   |26,768   |160   |731,088   |
|Entradas máximas de control de acceso   ||||2,000,000   |
   
En el ejemplo anterior, al implementar los servidores de chat persistente de acuerdo con las directrices recomendadas, pueden controlar hasta 80 000 usuarios activos en un grupo de cuatro servidores con el cumplimiento habilitado.
  
En este ejemplo se muestran los salas de chat categorizados como pequeños (30 usuarios activos en un momento dado), medianos (150 usuarios activos) y grandes (16.000 usuarios activos). El número admitido de salas de chat de un tamaño determinado en la tabla anterior se calcula en función del número total de:
  
- Usuarios activos en el sistema
    
- Usuarios activos en salas de chat del tamaño especificado
    
- Salas de chat del tamaño dado al que se une un solo usuario
    
Para cada salón de chat, la tabla de planeación de capacidad anterior especifica el número de entradas de control de acceso asociadas al salón de chat, incluidas las entradas asignadas directamente al salón de chat. Puede controlar el acceso a salas de chat individuales mediante listas de control de acceso (ACL). También puede controlar el acceso en el nivel de categoría. En una ACL, una entrada de control de acceso individual puede ser un grupo de usuarios, por ejemplo, un grupo de seguridad, una lista de distribución o un único usuario. Puede definir entradas de control de acceso para administradores de salas de chat, presentadores y miembros.
  
> [!IMPORTANT]
> Al planear la estrategia para administrar salas de chat, tenga en cuenta que el número total de entradas de control de acceso permitido es de 2 millones. Si las entradas de control de acceso calculado superan los 2 millones, el rendimiento del servidor podría degradarse significativamente. Para evitar este problema, siempre que sea posible, asegúrese de que las entradas de control de acceso son grupos de usuarios en lugar de usuarios individuales. 
  
### <a name="plan-capacity-for-managing-chat-room-access-by-invitation"></a>Planear la capacidad para administrar el acceso al salón de chat por invitación

Puede usar la siguiente tabla de planeación de capacidad para comprender el número de invitaciones que el servidor de chat persistente crea y almacena en la base de datos de chat persistente cuando está configurado para enviar invitaciones. Las invitaciones se administran en la categoría mediante  la página Configuración de categoría de salón de chat en el Panel de control de Skype Empresarial Server o mediante el cmdlet Windows PowerShell, **set-csPersistentChatCategory**. Puede administrar invitaciones en un salón de chat (en línea con lo que permite la categoría) mediante la  página Administración de salas iniciada desde el cliente de Skype Empresarial o mediante un cmdlet Windows PowerShell, **set-csPersistentChatRoom**.
  
Los datos de ejemplo de la tabla siguiente suponen que, en  la página Configuración del salón de chat para el 50 por ciento de todos  los salas de chat, la opción Invitaciones está establecida en **Sí**.
  
> [!IMPORTANT]
> Si el valor calculado para el número de invitaciones que genera el servidor supera el millón, el rendimiento del servidor podría degradarse significativamente. Para evitar este problema, asegúrese de minimizar el número de salas de chat configuradas para enviar invitaciones o restringir el número de usuarios que pueden unirse a los salas de chat que se han configurado para enviar invitaciones. 
  
**Acceso al salón de chat por ejemplo de invitación**

|&nbsp;|Salas de chat pequeñas|Salas de chat medianas|Salas de chat grandes|Total|
|:-----|:-----|:-----|:-----|:-----|
|Usuarios que pueden acceder al salón de chat   |30 por sala   |150 por sala   |16 000 por sala   ||
|Porcentaje de salas que tienen invitaciones   |50%   |50%   |50%   ||
|Salas de chat configuradas para enviar invitaciones   |16,000   |533   |5   ||
|Usuarios que pueden acceder al salón de chat   |60   |225   |16,000   ||
|Invitaciones generadas por el servidor de chat persistente   |960,000   |120,000   |80,000   |1,160,000   |
|Número máximo permitido de invitaciones   ||||2,000,000   |
|Modelo 1: comience con el número esperado de mensajes por sala y día   |||||
|Tasa de chat por sala (por día)   |50   |500   |100   |650   |
|Tasa de chat (por segundo) en todas las salas   |55.56   |18.52   |0.03   |74   |
|Modelo 2: empezar con el número de mensajes publicados por usuario y día   |||||
|Tasa de chat por usuario y día   |15    |5   |0,1   |20   |
|Tasa de chat por sala (por día)   |38   |375   |800   |1,213   |
|Tasa de chat (por segundo) en todas las salas   |41.67   |13.89   |0.28   |56   |
   
### <a name="plan-capacity-for-persistent-chat-server-performance"></a>Planear la capacidad para el rendimiento del servidor de chat persistente

En la tabla siguiente se describe el modelo de usuario para el servidor de chat persistente. Proporciona la base para los requisitos de planeación de capacidad y representa una organización típica con 80.000 usuarios simultáneos en cuatro servidores.
  
**Modelo de usuario de rendimiento del servidor de chat persistente**

- Número de usuarios activos conectados: 80 000  <br/>
- Número de instancias de servicio del servidor de chat persistente: 4  <br/>
- Tamaño de los pequeños salas de chat: 30 usuarios  <br/> 
- Tamaño de los salas de chat medianas: 150 usuarios  <br/>
- Tamaño de los grandes salas de chat: 16.000 usuarios  <br/>
- Número total de salas de chat: 33.077  <br/> 
- Número de salas de chat pequeñas: 32 000  <br/> 
- Número de salas de chat medianas: 1.067  <br/> 
- Número de salas de chat grandes: 10  <br/> 
- Número total de salas de chat por usuario: 16  <br/> 
- Número de salas de chat pequeñas por usuario: 12  <br/> 
- Número de salas de chat medianas por usuario: 2  <br/> 
- Número de salas de chat grandes por usuario: 2  <br/> 
- Número de salas unidas por usuario: 24  <br/>
- Velocidad máxima de combinación: 10/segundo  <br/> 
- Velocidad total de chat: 24/segundo  <br/> 
- Tasa de chat para salas de chat pequeñas: 22,22/segundo  <br/> 
- Tasa de chat para salas de chat medianas: 1,67/segundo  <br/> 
- Tasa de chat para salas de chat grandes: ~0,15/segundo  <br/> 
- Porcentaje de salas de chat configuradas para invitaciones: 50%  <br/>
- Porcentaje de pertenencias directas: 50%  <br/>
- Porcentaje de pertenencias a grupos: 50%  <br/> 
- Promedio de afiliaciones antecesoras en servicios de dominio de Active Directory: 100 - 200  <br/>
- Número de contactos suscritos por usuario: 80  <br/> 
- Número medio de puntos de conexión por usuario: 1,5  <br/> 
- Promedio de salas de chat visibles por punto de conexión: 1,5  <br/> 
- Número medio de salas de chat visibles por usuario: 2,25 (50 % para 1 sala y 50 % para 2 salas); Hasta 6 salas abiertas, una por monitor  <br/> 
- Número de participantes sondeados por intervalo: 25 por salón de chat visible  <br/> 
- Duración del intervalo de sondeo: 5 minutos  <br/> 
- Número de participantes sondeados por segundo: 15 000  <br/>
- Número de cambios de presencia por hora por usuario: 6  <br/> 
- Número de cambios de presencia por segundo: 133,33  
   

