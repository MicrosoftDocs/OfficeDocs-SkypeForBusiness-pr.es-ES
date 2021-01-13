---
title: Plan for Busy Options for Skype for Business Server
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
ms.openlocfilehash: 558d7486ca7aaa794c3114f5c210702a54e02fc4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813700"
---
# <a name="plan-for-busy-options-for-skype-for-business-server"></a>Plan for Busy Options for Skype for Business Server
 
Lea acerca de la característica Opciones de disponibilidad en Skype Empresarial Server.
  
Opciones de disponibilidad es una nueva directiva de voz introducida en la actualización acumulativa de julio de 2016 que le permite configurar cómo se administran las llamadas entrantes cuando un usuario ya está en una llamada o conferencia, o tiene una llamada en espera. Las llamadas nuevas o entrantes pueden rechazarse con una señal de disponibilidad o reenviarse al correo de voz. 
  
La directiva Opciones de disponibilidad es compatible con la conmutación por error y la recuperación ante desastres en grupos de servidores front-end emparejados y servidores de sucursal con funciones de supervivencia (SBS).
  
En este tema se describen las características de Opciones de disponibilidad. Para obtener información sobre cómo instalar y configurar Opciones de disponibilidad, consulte Instalar y configurar opciones de disponibilidad [para Skype Empresarial Server.](../../deploy/deploy-enterprise-voice/install-and-configure-busy-options.md)
  
## <a name="configuration-options"></a>Opciones de configuración

Si Opciones de disponibilidad está habilitada para la organización, todos los usuarios de la organización, tanto los Telefonía IP empresarial como los que no Telefonía IP empresarial, pueden usar las siguientes características:
  
- Ocupado en Ocupado: en el que se rechazarán las nuevas llamadas entrantes con una señal de ocupado si el usuario está ocupado.
    
- Correo de voz en Ocupado: en el que las nuevas llamadas entrantes se reenviarán al correo de voz si el usuario está ocupado.
    
La característica Opciones de disponibilidad proporciona capacidad de conmutación por error. Si se produce un problema y los usuarios conmutan por error a otro servidor front-end o a otro grupo en Skype Empresarial Server, se conservará la configuración de Opciones de disponibilidad.
  
Independientemente de cómo se configuren sus opciones de disponibilidad, los usuarios de una llamada o conferencia, o aquellos con una llamada en espera, no se les impide iniciar nuevas llamadas o conferencias. 
  
Después de la configuración, la opción Opciones de disponibilidad está en vigor para todos los clientes y dispositivos de llamadas de Skype Empresarial del usuario. En función de la configuración de Opciones de disponibilidad del usuario, la llamada que se rechaza o se envía al correo de voz no sonará en ninguno de los dispositivos de llamada del usuario (incluidos Macintosh, Escritorio de Windows, clientes móviles o teléfonos IP) en los que el usuario haya iniciado sesión. 
  
Los usuarios verán notificaciones de llamadas perdidas en sus dispositivos y clientes de Skype Empresarial, y también se les notificará por correo electrónico. Los autores de llamadas cuya llamada se rechazó debido a Ocupado en ocupado verán una notificación en su cliente de Skype Empresarial que indica que el usuario con el que intentaron contactar está ocupado en otra llamada.
  
Puede configurar la característica Opciones de disponibilidad con los cmdlets de PowerShell de Skype Empresarial para:
  
- Habilitar o deshabilitar la directiva de voz de Opciones de disponibilidad para la empresa.
    
- Administrar ocupado en ocupado o correo de voz en ocupado para todos los usuarios de la empresa.
    
- Administrar ocupado en ocupado o correo de voz en ocupado para todos los usuarios que se alojen en un grupo de servidores front-end determinado.
    
- Administrar ocupado en ocupado o correo de voz en ocupado para una lista de usuarios.
    
- Administrar ocupado en ocupado o correo de voz en ocupado para un solo usuario.
    
## <a name="interoperability-with-voice-applications"></a>Interoperabilidad con aplicaciones de voz

Opciones de disponibilidad proporciona interoperabilidad con las siguientes aplicaciones de voz en Skype Empresarial:
  
- Grupos de respuesta (RGS)
    
  - El sistema omitirá las opciones de disponibilidad establecidas en los números de grupo de respuesta; se permitirán varias llamadas simultáneas. 
    
  - La experiencia de enrutamiento del operador actual en grupos de respuesta no se modificará para la configuración de Agentes con Opciones de disponibilidad.
    
  - Las llamadas procedentes de grupos de respuesta a los usuarios que son agentes de grupos de respuesta no se limitarán con la configuración de Opciones de disponibilidad y se mantendrá la experiencia actual de RGS.
    
  - La configuración de Opciones de disponibilidad respetará las llamadas no relacionadas con RGS a los agentes.
    
- Llamada de equipo
    
  - Se dará prioridad a las llamadas entrantes a los usuarios que están configurados para una llamada de equipo para omitir la configuración ocupado en ocupado y correo de voz en ocupado.
    
  - La experiencia actual de llamada de equipo no cambiará con opciones de disponibilidad establecidas para los usuarios.
    
  - La configuración de Opciones de disponibilidad respetará las llamadas que no sean relacionadas con llamadas de equipo a dichos usuarios.
    
- Delegación jefe/administrador 
    
  - Se dará prioridad a las llamadas entrantes a los usuarios configurados para una delegación de jefe o administrador como jefe o administrador para omitir ocupado en ocupado y correo de voz en la configuración de ocupado.
    
  - La experiencia actual de delegación jefe/administrador no cambiará con opciones de disponibilidad establecidas para los administradores o jefes.
    
  - La configuración de Opciones de disponibilidad respetará las llamadas a administradores que no sean jefes o administradores.
    
- Apariencia de línea compartida 
    
  - Se omitirá la configuración de Opciones de disponibilidad en las cuentas de usuario configuradas para apariencia de línea compartida. 
    
  - En su lugar, se respetará la opción "Ocupado" nativo de apariencia de línea compartida y "Correo de voz en Ocupado".
    
- Servicio de estacionamiento de llamadas 
    
  - Las llamadas estacionadas que no se recuperaron y que están sonando debido al tiempo de inacurrida podrán sonar para el usuario que estacionó la llamada mediante Opciones de disponibilidad. 
    
- Conferencia de llamadas
    
  - Los usuarios de las llamadas de conferencia se consideran ocupados y las llamadas entrantes nuevas se rechazarán con una señal de ocupado o se reenviarán al correo de voz de acuerdo con la configuración de Opciones de disponibilidad.
    
  - Las opciones de disponibilidad no impiden que los usuarios de las conferencias inicien nuevas llamadas o conferencias.
    
  - Los usuarios de las conferencias aún pueden recibir nuevas invitaciones a conferencias, pero las llamadas punto a punto nuevas se rechazarán según la configuración de Opciones de disponibilidad.
    
- Llamadas simultáneas y reenvío de llamadas
    
    La característica Ocupado en ocupado no está diseñada para funcionar con llamadas simultáneas y el reenvío de llamadas.
    

