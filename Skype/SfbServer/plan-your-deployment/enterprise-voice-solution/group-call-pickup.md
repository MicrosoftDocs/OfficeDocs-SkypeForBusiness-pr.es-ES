---
title: Planificar la atención de llamadas grupales en Skype Empresarial 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 2/16/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 3dc0eca8-c773-463c-96bb-9cd6afa2a840
description: Planificación para la recogida de grupo llamar en Skype para Telefonía IP empresarial de Business Server, que permite a los usuarios contestar llamadas originalmente destinadas a otras personas.
ms.openlocfilehash: ff23b08ca575f7296cbb3706ccdb351b89352804
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="plan-for-group-call-pickup-in-skype-for-business-2015"></a>Planificar la atención de llamadas grupales en Skype Empresarial 2015
 
Planificación para la recogida de grupo llamar en Skype para Telefonía IP empresarial de Business Server, que permite a los usuarios contestar llamadas originalmente destinadas a otras personas.
  
Recogida de llamar a grupo permite a los usuarios contestar las llamadas entrantes a sus compañeros desde sus propios teléfonos. De esta forma, se aumenta la disponibilidad de la línea de un usuario, ya que permite que otros usuarios respondan una llamada entrante al marcar un número de grupo de atención de llamadas. Cuando se implementa la recogida de llamar al grupo, el número de las llamadas entrantes se encaminan al buzón de voz puede significativamente reducirse, que es especialmente útil para las llamadas de los clientes que son externos a su organización.
  
La característica de grupo llamar recogida está diseñada especialmente para unidades de negocio en entornos de oficina abierta. Las llamadas entrantes no resultan molestas porque solo suenan en el destino previsto. Pero los otros usuarios que escuchan el timbre pueden atender la llamada muy fácilmente al marcar el número del grupo. 
  
En entornos donde los usuarios no se encuentran en un diseño de oficina abierta, o donde los usuarios que comparten una responsabilidad común se distribuyen geográficamente, llamada equipo presenta la solución más adecuada. La diferencia principal entre el grupo llamar recogida y llamada de equipo es que, con recogida llame al grupo, una llamada entrante suena sólo en el destino deseado, pero cualquier usuario puede optar por contestar marcando un número de grupo. Con la llamada de equipo, la llamada suena en todos los teléfonos de los miembros del equipo y cualquier usuario del equipo puede levantar el teléfono para contestar la llamada. Una diferencia adicional entre el grupo llamar recogida y llamada de equipo es que grupo llamar recogida es administrada por un administrador, a través de Skype para Business Server. Con la llamada de equipo, los usuarios finales administrar la característica utilizando el Skype para cliente de empresa. Con recogida llame al grupo, por lo tanto, este aspecto de la administración de llamadas puede centralizarse.
  
Grupo llame recogida se basa en la aplicación de llamada Park. Al implementar grupo llamar recogida, configura la tabla de órbita parque de llamada con los rangos de números de extensión que se designan como llamar a números de grupo recogida independientes. Al igual que los números de órbita del estacionamiento de llamadas, los números de grupo de atención de llamadas necesitan ser extensiones virtuales que no tengan asignado ningún usuario o teléfono. Cada grupo de servidores Front-End donde implementar grupo llamar recogida puede tener uno o más rangos de números de grupo recogida de llamada. Los rangos de números de grupo deben ser únicos globalmente en el Skype para la implementación de Business Server. 
  
> [!NOTE]
> Intervalos numéricos que se designan como grupo recogida llamar a números en la tabla de llamada park órbita no pueden ser administrados o ver utilizando el Skype para el Panel de Control de servidor empresarial. La única forma de ver todos los rangos de números en la tabla de llamada park órbita es utilizar Skype para el Shell de administración de servidor empresarial. De forma similar, la única manera de agregar, modificar o quitar números de grupo llamar recogida consiste en utilizar Skype para el Shell de administración de servidor empresarial. 
  
Una vez configurados los números de grupo de atención de llamadas, necesitas asignar los usuarios a un grupo de atención de llamadas. Las llamadas de un usuario asignado a un grupo de atención de llamadas pueden responderlas otros usuarios. Cuando entra una llamada para un usuario asignado a un grupo de atención de llamadas, cualquier otro usuario que escuche la llamada puede atenderla marcando de forma manual el número del grupo de atención de llamadas. No es necesario que el usuario que atiende la llamada sea miembro del grupo. Cuando otro usuario atiende una llamada, se envía una notificación al número al que se llamó originalmente.
  
> [!NOTE]
> Un usuario solo puede pertenecer a un grupo de atención de llamadas. 
  
> [!NOTE]
> Aunque cualquier usuario en el Skype para la implementación de Business Server puede responder a una llamada a un miembro del grupo de recogida de llamada, la persona que responde la llamada debe conocer el número de grupo de recogida de llamada correcta a marcar. 
  
Si un usuario marca el número de un grupo de atención de llamadas para responder una llamada cuando suenan varios teléfonos del grupo, atenderá la llamada que ha sonado por más tiempo.
  
La configuración de llamadas simultáneas resulta útil para los usuarios que disponen de la atención de llamadas grupales. Es decir, sonará una llamada realizada a un usuario que tenga el grupo llamar recogida para todos los destinos configurados y otro usuario puede contestar la llamada. La excepción a esta regla es cuando un usuario configura las llamadas simultáneas para llamar a todos los miembros del grupo.
  
Grupo llame recogida no pueden utilizarse para responder a los siguientes tipos de llamadas:
  
- Llamadas a una línea privada
    
- Llamadas de un contacto al que se ha asignado la relación de privacidad Amigos y familiares
    
    > [!TIP]
    > Un usuario que sea miembro de un grupo de recogida de llamada puede impedir que ciertas llamadas se recuperen a través de la recogida de grupo llamar marcando el contacto como un contacto personal en el Skype para cliente de empresa. Para marcar un contacto como contacto personal, establece la relación de privacidad del contacto en Amigos y familiares. Cualquier llamada entrante de los contactos con la relación de privacidad establecida a amigos y familia no se puede recuperar utilizando la recogida de llamar al grupo. 
  
- Parte de vídeo de llamadas de audio y vídeo 
    
    > [!NOTE]
    > Si un usuario responde una llamada de audio y vídeo, solo recibe el audio. La persona que llama o la persona que responde la llamada puede escalarla para agregar vídeo. 
  
- Llamadas simultáneas redirigidas a miembros de llamada de equipo
    
- Llamadas redirigidas a un delegado
    
- Llamadas redirigidas a un grupo de respuesta
    
Los siguientes tipos de usuarios no pueden participar en la recogida de llamar al grupo. Es decir, no deben ser incluidas en un grupo de recogida de llamar al grupo y no se levantan las llamadas para usuarios que tienen habilitada de recogida llame al grupo.
  
- Usuarios alojados en línea en una implementación híbrida
    
- Los usuarios que no se encuentran en ambos un Skype para Business Server 2015 pool o una agrupación de Lync Server 2013 actualizaciones acumulativas para Lync Server 2013: febrero de 2013 en una implementación local
    
Si nadie atiende una llamada realizada a un miembro de un grupo de atención de llamadas, la llamada se redirige según lo especificado en la configuración del cliente. Es decir, la llamada se desvía al correo de voz o se reenvía a otro destino, tal como se especifique en la configuración del cliente.
  
## <a name="deployment-and-requirements"></a>Requisitos e implementación

Grupo llame recogida se despliega automáticamente al implementar la Telefonía IP empresarial y la aplicación de llamada Park. Activar grupo llamar recogida configurando la tabla órbita llamada Park con intervalos independientes de números designados como llamar a números de grupo de recogida y, a continuación, asignar usuarios a grupos de recogida y habilitar a los usuarios para la recogida de llamar al grupo.
  
## <a name="clients-supported-for-group-call-pickup"></a>Clientes admitidos para la recogida de llamar a grupo

Cualquiera de los siguientes clientes pueden utilizarse para responder a las llamadas a los miembros del grupo llame recogida:
  
- Skype Empresarial
    
- Lync 2013
    
- Lync 2010
    
- Lync Phone Edition
    
> [!NOTE]
> Los usuarios pueden utilizar para responder a las llamadas a los miembros del grupo recogida de llamar a cualquiera de estos clientes, pero los usuarios deben estar alojados en un Skype para el grupo de Business Server o un grupo de Lync Server 2013 actualizaciones acumulativas para Lync Server 2013: febrero de 2013. 
  
No se admiten los siguientes clientes y dispositivos para las llamadas a los miembros del grupo llame recogida de selección:
  
- Lync Mobile
    
- Aplicación Lync para Windows 8 y Windows RT
    
- Lync para iPad
    
- Teléfonos analógicos
    
- Teléfonos con números de la red telefónica conmutada (RTC)
    
## <a name="capacity-planning"></a>Planificación de la capacidad

La tabla siguiente describe el modelo de usuario recogida llamar de grupo que puede utilizar como base para los requerimientos de planificación de capacidad.
  
> [!IMPORTANT]
> Grupo llame recogida se basa en la aplicación de llamada Park. Tenga en cuenta que, para planear la capacidad de recuperación ante desastres, cada grupo de un grupo de par debe ser capaz de manejar las cargas de trabajo para servicios de llamada Park, incluyendo recogida llame al grupo, de ambos grupos. 
  
**Modelo de grupo de usuario recogida de llamada**

|**Métrica**|**Por cada grupo de Front-End <br/> (con 8 servidores frontales)**|**Por cada servidor Standard Edition**|
|:-----|:-----|:-----|
|Cantidad recomendada de usuarios por grupo  <br/> |50  <br/> |50  <br/> |
|Cantidad recomendada de grupos  <br/> |500  <br/> |60  <br/> |
|Cantidad máxima de usuarios por grupo habilitados para la atención de llamadas grupales  <br/> |25.000  <br/> |3.000  <br/> |
|Tasa máxima de llamadas entrantes al total de usuarios habilitados para la atención de llamadas grupales por grupo, por minuto  <br/> |500  <br/> |60  <br/> |
|Tasa máxima de llamadas recuperadas por los usuarios con la atención de llamadas grupales por grupo, por minuto  <br/> |200  <br/> |25  <br/> |
   
> [!NOTE]
> Para las agrupaciones de Front-End que tienen menos de ocho servidores frontales, calcular las métricas linealmente. Por ejemplo, si el grupo de servidores Front-End tiene un servidor de Front-End, calcular la carga máxima como 1/8 de los valores mostrados en la tabla. 
  
> [!NOTE]
> Puedes aumentar o disminuir la cantidad recomendada de usuarios por grupo y la cantidad de grupos siempre y cuando no supere la cantidad máxima de usuarios por grupo. Por ejemplo, el servidor Standard Edition puede tener 120 grupos con 25 usuarios por grupo porque el número de usuarios habilitados para la recogida de llamar a grupo es todavía dentro de un máximo de modelo de usuario (es decir, los tiempos 120 grupos 25 usuarios es 3.000 usuarios habilitados para la recogida de llamar al grupo). 
  

