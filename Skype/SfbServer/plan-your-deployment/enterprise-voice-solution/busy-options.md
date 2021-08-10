---
title: Plan for Busy Options for Skype Empresarial Server
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
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 5f85c6bc-a962-4283-971c-4380d83b3a66
description: Lea acerca de la característica Opciones de disponibilidad en Skype Empresarial Server.
ms.openlocfilehash: 9c752ebfbfc24f250b1dc9ad68118d1795cfc356cb1332ff7d1d5c66026cfca1
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54306951"
---
# <a name="plan-for-busy-options-for-skype-for-business-server"></a>Plan for Busy Options for Skype Empresarial Server
 
Lea acerca de la característica Opciones de disponibilidad en Skype Empresarial Server.
  
Opciones de disponibilidad es una nueva directiva de voz que se introdujo en la actualización acumulativa de julio de 2016 que le permite configurar cómo se controlan las llamadas entrantes cuando un usuario ya está en una llamada o conferencia o tiene una llamada en espera. Las llamadas nuevas o entrantes se pueden rechazar con una señal de disponibilidad o reenviarse al correo de voz. 
  
La directiva opciones de disponibilidad es compatible con la conmutación por error y la recuperación ante desastres en grupos front-end emparejados y servidores de sucursal con funciones de supervivencia (SBS).
  
En este tema se describen las características de Opciones de disponibilidad. Para obtener información sobre cómo instalar y configurar opciones de disponibilidad, vea [Instalar y configurar opciones de disponibilidad para Skype Empresarial Server](../../deploy/deploy-enterprise-voice/install-and-configure-busy-options.md).
  
## <a name="configuration-options"></a>Opciones de configuración

Si las opciones de disponibilidad están habilitadas para la organización, todos los usuarios de la organización, tanto Telefonía IP empresarial como los usuarios que no Telefonía IP empresarial, pueden usar las siguientes características:
  
- Ocupado en ocupado: en el que las nuevas llamadas entrantes se rechazarán con una señal de disponibilidad si el usuario está ocupado.
    
- Correo de voz en ocupado: en el que las nuevas llamadas entrantes se reenviarán al correo de voz si el usuario está ocupado.
    
La característica Opciones de disponibilidad proporciona la funcionalidad de conmutación por error. Si se produce un problema y los usuarios conmutan por error a otro servidor front-end o a otro grupo de servidores de Skype Empresarial Server, se conservará la configuración de Opciones de disponibilidad.
  
Independientemente de cómo se configuren sus opciones de disponibilidad, los usuarios de una llamada o conferencia, o aquellos con una llamada en espera, no se les impide iniciar nuevas llamadas o conferencias. 
  
Después de la configuración, la configuración Opciones de disponibilidad está en vigor para todos los dispositivos y clientes de Skype Empresarial llamadas del usuario. Según la configuración de Opciones de disponibilidad del usuario, la llamada que se rechaza o se envía al correo de voz no sonaría en ninguno de los dispositivos de llamada del usuario (incluidos Macintosh, escritorio de Windows, clientes móviles o teléfonos IP) en los que el usuario ha iniciado sesión. 
  
Los usuarios verán notificaciones de llamadas perdidas en sus Skype Empresarial y dispositivos, y también se les notificará por correo electrónico. Los autores de llamadas cuya llamada se rechazó debido a Ocupado en ocupado verán una notificación en su cliente de Skype Empresarial que indica que el usuario al que intentaron llegar está ocupado en otra llamada.
  
Puede configurar la característica Opciones de disponibilidad mediante Skype Empresarial cmdlets de PowerShell para:
  
- Habilitar o deshabilitar la directiva de voz opciones de disponibilidad para el Enterprise.
    
- Administrar ocupado en ocupado o correo de voz en ocupado para todos los usuarios de la Enterprise.
    
- Administrar ocupado en ocupado o correo de voz en ocupado para todos los usuarios que se alojen en un grupo de servidores front-end determinado.
    
- Administrar ocupado en ocupado o correo de voz en ocupado para una lista de usuarios.
    
- Administrar ocupado en ocupado o correo de voz en ocupado para un solo usuario.
    
## <a name="interoperability-with-voice-applications"></a>Interoperabilidad con aplicaciones de voz

Opciones de disponibilidad proporciona interoperabilidad con las siguientes aplicaciones de voz en Skype Empresarial:
  
- Grupos de respuesta (RGS)
    
  - El sistema omitirá las opciones de disponibilidad establecidas en los números de grupo de respuesta; se permitirán varias llamadas simultáneas. 
    
  - La experiencia actual de enrutamiento de operadores en grupos de respuesta no cambiará para la configuración agentes con opciones de disponibilidad.
    
  - Las llamadas procedentes de grupos de respuesta a los usuarios que son agentes de grupos de respuesta no se limitarán con la configuración de opciones de disponibilidad y se mantendrá la experiencia actual de RGS.
    
  - Las llamadas que no sean relacionadas con RGS a los agentes se respetarán con su configuración de Opciones de disponibilidad.
    
- Llamada de equipo
    
  - Las llamadas entrantes a los usuarios que estén configurados para una llamada de equipo tendrán prioridad para omitir ocupados en ocupados y correo de voz en la configuración de disponibilidad.
    
  - La experiencia actual de llamada de equipo no cambiará con opciones de disponibilidad establecidas para los usuarios.
    
  - La configuración de opciones de disponibilidad respetará las llamadas no relacionadas con llamadas de equipo a dichos usuarios.
    
- Delegación jefe/administrador 
    
  - Se priorizarán las llamadas entrantes a los usuarios que estén configurados para una delegación de jefes o administradores como jefe o administrador para omitir ocupados en ocupados y correo de voz en la configuración de ocupado.
    
  - La experiencia actual de delegación de jefes y administradores no cambiará con las opciones de disponibilidad establecidas para los administradores o jefes.
    
  - La configuración de opciones de disponibilidad respetará las llamadas que no sean relacionadas con jefes o delegación de administradores a los administradores.
    
- Apariencia de línea compartida 
    
  - Se omitirá la configuración de opciones de disponibilidad de las cuentas de usuario configuradas para la apariencia de línea compartida. 
    
  - En su lugar, se respetará la disponibilidad nativa de La apariencia de línea compartida en ocupado y el correo de voz en las opciones ocupados.
    
- Servicio de estacionamiento de llamadas 
    
  - Las llamadas estacionadas que no se recuperaron y que están sonando de nuevo debido al tiempo de desasocupado podrán sonar, aunque para el usuario que estacionó la llamada por las opciones de disponibilidad. 
    
- Conferencia de llamadas
    
  - Los usuarios de llamadas de conferencia se consideran ocupados y las nuevas llamadas entrantes se rechazarán con una señal de disponibilidad o se reenviarán al correo de voz de acuerdo con la configuración de Opciones de disponibilidad.
    
  - Las opciones de disponibilidad no impiden que los usuarios de conferencias inicien nuevas llamadas o conferencias.
    
  - Los usuarios de las conferencias aún pueden recibir nuevas invitaciones a conferencias, pero las nuevas llamadas punto a punto se rechazarán según la configuración de opciones de disponibilidad.
    
- Llamadas simultáneas y reenvío de llamadas
    
    La característica Ocupado en ocupado no está diseñada para funcionar con llamadas simultáneas y reenvío de llamadas.
    

