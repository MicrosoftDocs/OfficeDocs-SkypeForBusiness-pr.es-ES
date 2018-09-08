---
title: Plan para Opciones de disponibilidad para Skype Empresarial Server
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 5f85c6bc-a962-4283-971c-4380d83b3a66
description: Lea acerca de la característica de opciones de disponibilidad de Skype para Business Server.
ms.openlocfilehash: 7b71cad7eebaf2d375098abfa0891cdf6b494fe9
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2018
ms.locfileid: "23884789"
---
# <a name="plan-for-busy-options-for-skype-for-business-server"></a>Plan para Opciones de disponibilidad para Skype Empresarial Server
 
Lea acerca de la característica de opciones de disponibilidad de Skype para Business Server.
  
Opciones de disponibilidad es una nueva directiva de voz introducida en la actualización acumulativa de julio de 2016 que permite configurar el tratamiento dado a las llamadas entrantes cuando un usuario ya está al teléfono o en una conferencia, o tiene una llamada en espera. Las llamadas nuevas o entrantes pueden rechazarse con una señal de línea ocupada o desviarse al correo de voz. 
  
La directiva de opciones de disponibilidad se admite para la recuperación ante desastres y la conmutación por error en grupos de servidores front-end emparejados y servidores de sucursal con funciones de supervivencia (SBS).
  
En este tema se describen las características de Opciones de disponibilidad. Para obtener información acerca de cómo instalar y configurar las opciones de disponibilidad, vea [instalar y configurar las opciones de disponibilidad de Skype para Business Server](../../deploy/deploy-enterprise-voice/install-and-configure-busy-options.md).
  
## <a name="configuration-options"></a>Opciones de configuración

Si Opciones de disponibilidad está habilitada para la organización, todos los usuarios que formen parte de esta, tanto los que usen la telefonía IP empresarial como los que no la usen, pueden utilizar las siguientes características:
  
- Ocupado cuando ocupado: en la cual se rechazan las llamadas entrantes nuevas con una señal de línea ocupada si el usuario está ocupado.
    
- Correo de voz cuando ocupado: en la cual se desvían al correo de voz las llamadas entrantes nuevas si el usuario está ocupado.
    
La característica Opciones de disponibilidad ofrece una capacidad de conmutación por error. Si se produce un problema y los usuarios conmuten por error a otro servidor Front-End o a otro grupo de servidores en Skype para Business Server, se conservarán su configuración de opciones de disponibilidad.
  
Independientemente de cómo esté configurada Opciones de disponibilidad, los usuarios que estén al teléfono o en una conferencia, o bien aquellos que tengan una llamada en espera, podrán iniciar nuevas llamadas o conferencias.   
  
Después de la configuración, la configuración de opciones de disponibilidad es en vigor para Skype todos los del usuario para clientes y dispositivos de llamada de negocio. En función de la configuración de Opciones de disponibilidad del usuario, la llamada que se rechace o se envíe al correo de voz no sonará en ninguno de los dispositivos de llamada del usuario (entre ellos, Macintosh, el escritorio de Windows, clientes móviles o teléfonos IP) en los que el usuario haya iniciado sesión. 
  
Los usuarios verán las notificaciones de llamadas perdidas en su Skype para clientes empresariales y dispositivos, y se les notifique por correo electrónico también. A quienes se les haya rechazado una llamada por Ocupado cuando ocupado verán una notificación en el cliente de Skype Empresarial que indicará que el usuario al que intentaron contactar está ocupado en otra llamada.
  
Puede configurar la característica de opciones ocupado mediante Skype para cmdlets de PowerShell de negocio para:
  
- Habilitar o deshabilitar la directiva de voz de Opciones de disponibilidad para la empresa.
    
- Administrar Ocupado cuando ocupado o Correo de voz cuando ocupado para todos los usuarios de la empresa.
    
- Administrar Ocupado cuando ocupado o Correo de voz cuando ocupado para todos los usuarios alojados en un grupo de servidores front-end particular.
    
- Administrar Ocupado cuando ocupado o Correo de voz cuando ocupado para una lista de usuarios.
    
- Administrar Ocupado cuando ocupado o Correo de voz cuando ocupado para un solo usuario.
    
## <a name="interoperability-with-voice-applications"></a>Interoperabilidad con aplicaciones de voz

Opciones de disponibilidad proporciona interoperabilidad con las siguientes aplicaciones de voz de Skype para la empresa:
  
- Grupos de respuesta (RGS)
    
  - El sistema omitirá los parámetros de configuración de Opciones de disponibilidad establecidos en los números de grupos de respuesta. Se permitirán varias llamadas simultáneas.  
    
  - La experiencia de enrutamiento del operador actual en los grupos de respuesta no cambiará para los agentes con la configuración de Opciones de disponibilidad.
    
  - Las llamadas que provengan de grupos de respuesta a los usuarios que sean agentes de grupos de respuesta no se verán limitadas por la configuración de Opciones de disponibilidad y se mantendrá la experiencia de RGS actual.
    
  - La configuración de Opciones de disponibilidad respetará las llamadas no relacionadas con RGS realizadas a los agentes.
    
- Llamada de equipo
    
  - Las llamadas entrantes a los usuarios que se han configurado para una llamada de equipo le dará prioridad para omitir no disponible en no disponible y correo de voz en la configuración de disponibilidad.
    
  - La experiencia actual de llamada de equipo no sufrirá cambios con los parámetros de configuración de Opciones de disponibilidad que se establezcan para los usuarios.
    
  - La configuración de Opciones de disponibilidad respetará las llamadas que no estén relacionadas con las llamadas de equipo a tales usuarios.
    
- Delegación Jefe/Administrador  
    
  - Las llamadas entrantes a los usuarios que estén configurados para la delegación de directores/Admin ya sea como jefe o un administrador le dará prioridad para omitir no disponible en no disponible y correo de voz en la configuración de disponibilidad.
    
  - La experiencia actual de delegación de Jefe/Administrador no sufrirá cambios con los parámetros de configuración de Opciones de disponibilidad que se establezcan para los administradores o jefes.
    
  - La configuración de Opciones de disponibilidad respetará las llamadas que no estén relacionadas con la delegación de Jefe/Administrador a los administradores.
    
- Apariencia de línea compartida    
    
  - Se omitirá la configuración de Opciones de disponibilidad en las cuentas de usuario configuradas para la apariencia de línea compartida.  
    
  - Ocupado nativo de la apariencia de línea compartida en no disponible y correo de voz en las opciones de disponibilidad tendrá en cuenta en su lugar.
    
- Servicio de estacionamiento de llamadas  
    
  - Las llamadas estacionadas que no se han recuperado y que estén sonando nuevamente debido al agotamiento del tiempo de espera podrán sonar en los dispositivos del usuario que las estacionó a través de Opciones de disponibilidad.  
    
- Conferencia de llamadas
    
  - Se considera que los usuarios que estén en llamadas de conferencia están ocupados, y se rechazarán todas las llamadas entrantes nuevas con una señal de línea ocupada o un envío al correo de voz de acuerdo con la configuración de Opciones de disponibilidad.
    
  - Opciones de disponibilidad no impide que los usuarios en conferencia inicien llamadas ni conferencias nuevas.
    
  - Los usuarios en conferencia todavía pueden recibir invitaciones a conferencias nuevas, pero se rechazarán las llamadas de par a par nuevas de acuerdo con la configuración de Opciones de disponibilidad.
    
- Desvío de llamadas y llamadas simultáneas
    
    La característica Ocupado cuando ocupado no se ha diseñado para funcionar con desvío de llamadas y llamadas simultáneas.
    

