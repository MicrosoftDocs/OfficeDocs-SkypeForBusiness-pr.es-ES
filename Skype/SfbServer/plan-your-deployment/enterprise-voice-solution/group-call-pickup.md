---
title: Plan de respuesta de llamadas en grupo en Skype para la empresa
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 3dc0eca8-c773-463c-96bb-9cd6afa2a840
description: Planeación de recogida de llamadas de grupo en Skype para Business Server Enterprise Voice, que permite a los usuarios atender las llamadas originalmente destinadas a otras personas.
ms.openlocfilehash: 17c3d453fa54ea72c02c022d33b0b2f1c61e8b0b
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2018
ms.locfileid: "21016201"
---
# <a name="plan-for-group-call-pickup-in-skype-for-business"></a>Plan de respuesta de llamadas en grupo en Skype para la empresa
 
Planeación de recogida de llamadas de grupo en Skype para Business Server Enterprise Voice, que permite a los usuarios atender las llamadas originalmente destinadas a otras personas.
  
Recogida de llamadas de grupo permite a los usuarios responder a las llamadas entrantes a sus compañeros de trabajo desde sus propios teléfonos. De esta forma, se aumenta la disponibilidad de la línea de un usuario, ya que permite que otros usuarios respondan una llamada entrante al marcar un número de grupo de atención de llamadas. Cuando se implementa recogida de llamadas de grupo, el número de llamadas entrantes que se enrutan al correo de voz se puede significativamente reducir, que es especialmente útil para las llamadas de los clientes que son externos a su organización.
  
La característica de recogida de llamadas de grupo está diseñada en particular para las unidades de negocio en entornos de office open. Las llamadas entrantes no resultan molestas porque solo suenan en el destino previsto. Pero los otros usuarios que escuchan el timbre pueden atender la llamada muy fácilmente al marcar el número del grupo. 
  
En entornos donde los usuarios no se encuentran en un diseño de oficina open o donde los usuarios que comparten una responsabilidad común están distribuidos geográficamente, llamada de equipo presenta la solución más adecuada. La diferencia principal entre recogida de llamadas de grupo y llamada de equipo es que, con grupo de llamada recogida, llama una llamada entrante sólo en el destino previsto, pero aún, cualquier usuario puede elegir responder a la llamada marcando un número de grupo. Con la llamada de equipo, la llamada en absoluto suena teléfonos de los miembros del equipo y cualquier usuario en el equipo puede recoger el teléfono para responder a la llamada. Una diferencia adicional entre recogida de llamadas de grupo y llamada de equipo es que recogida de llamadas de grupo sea administrado por un administrador, a través de Skype para Business Server. Con la llamada de equipo, los usuarios finales administrar la característica mediante el uso de la Skype para clientes empresariales. Por lo tanto, con recogida de llamadas de grupo, este aspecto de la administración de llamadas puede ser centralizada.
  
Recogida de llamadas de grupo se basa en la aplicación de estacionamiento de llamadas. Al implementar recogida de llamadas de grupo, configurar la tabla de órbitas de estacionamiento de llamadas con los rangos de números de extensión que se designan como números de llamada de grupo pickup independientes. Al igual que los números de órbita del estacionamiento de llamadas, los números de grupo de atención de llamadas necesitan ser extensiones virtuales que no tengan asignado ningún usuario o teléfono. Cada grupo de servidores Front-End donde implementa recogida de llamadas de grupo puede tener uno o varios intervalos de números de llamada de grupo pickup. Los intervalos de números de grupo deben ser únicos global a través de la Skype para la implementación de Business Server. 
  
> [!NOTE]
> Intervalos de números que se designan como números de recogida de llamadas de grupo en la tabla de órbitas de estacionamiento de llamada se no administrados o visualizarse mediante el Skype para el Panel de Control de servidor empresarial. La única forma para ver todos los intervalos de números en la tabla de órbitas de estacionamiento de llamada es usar Skype para Shell de administración de servidor empresarial. De forma similar, la única forma de agregar, modificar o quitar los números de recogida de llamadas de grupo consiste en usar Skype para Shell de administración de servidor empresarial. 
  
Una vez configurados los números de grupo de atención de llamadas, necesitas asignar los usuarios a un grupo de atención de llamadas. Las llamadas de un usuario asignado a un grupo de atención de llamadas pueden responderlas otros usuarios. Cuando entra una llamada para un usuario asignado a un grupo de atención de llamadas, cualquier otro usuario que escuche la llamada puede atenderla marcando de forma manual el número del grupo de atención de llamadas. No es necesario que el usuario que atiende la llamada sea miembro del grupo. Cuando otro usuario atiende una llamada, se envía una notificación al número al que se llamó originalmente.
  
> [!NOTE]
> Un usuario solo puede pertenecer a un grupo de atención de llamadas. 
  
> [!NOTE]
> Aunque cualquier usuario en la Skype para la implementación de Business Server puede responder a una llamada a un miembro del grupo pickup llamada, la persona a la llamada debe conocer el número de grupo pickup llamada correcta a marcar. 
  
Si un usuario marca el número de un grupo de atención de llamadas para responder una llamada cuando suenan varios teléfonos del grupo, atenderá la llamada que ha sonado por más tiempo.
  
La configuración de llamadas simultáneas resulta útil para los usuarios que disponen de la atención de llamadas grupales. Es decir, una llamada realizada a un usuario que tiene recogida de llamadas de grupo recibirán la llamada para todos los destinos configurados y otro usuario puede responder a la llamada. La excepción a esta regla es cuando un usuario configura las llamadas simultáneas para llamar a todos los miembros del grupo.
  
Recogida de llamadas de grupo no puede usarse para responder a los siguientes tipos de llamadas:
  
- Llamadas a una línea privada
    
- Llamadas de un contacto al que se ha asignado la relación de privacidad Amigos y familiares
    
    > [!TIP]
    > Un usuario que sea miembro de un grupo de recogida de llamada puede evitar que ciertas llamadas desde que se recuperan a través de recogida de grupo de llamada marcando el contacto como un contacto personal en el Skype para clientes empresariales. Para marcar un contacto como contacto personal, establece la relación de privacidad del contacto en Amigos y familiares. Cualquier llamada entrante de los contactos con la relación de privacidad de establece a amigos y familiares no se puede recuperar mediante el uso de recogida de llamadas de grupo. 
  
- Parte de vídeo de llamadas de audio y vídeo 
    
    > [!NOTE]
    > Si un usuario responde una llamada de audio y vídeo, solo recibe el audio. La persona que llama o la persona que responde la llamada puede escalarla para agregar vídeo. 
  
- Llamadas simultáneas redirigidas a miembros de llamada de equipo
    
- Llamadas redirigidas a un delegado
    
- Llamadas redirigidas a un grupo de respuesta
    
Los siguientes tipos de usuarios no pueden participar en recogida de llamadas de grupo. Es decir, que no deben incluirse en un grupo de recogida de llamadas de grupo, y no se puede recoger de llamadas para los usuarios que tienen habilitado de recogida de llamadas de grupo.
  
- Usuarios alojados en línea en una implementación híbrida
    
- Los usuarios que no están hospedados en puede ser un Skype para el grupo de servidores de 2015 de servidor empresarial o un grupo de servidores de Lync Server 2013 con actualizaciones acumulativas para Lync Server 2013: en una implementación local de febrero de 2013
    
Si nadie atiende una llamada realizada a un miembro de un grupo de atención de llamadas, la llamada se redirige según lo especificado en la configuración del cliente. Es decir, la llamada se desvía al correo de voz o se reenvía a otro destino, tal como se especifique en la configuración del cliente.
  
## <a name="deployment-and-requirements"></a>Requisitos e implementación

Recogida de llamadas de grupo se implementa automáticamente al implementar Enterprise Voice y la aplicación de estacionamiento de llamadas. Habilitar recogida de llamadas de grupo mediante la configuración de la tabla de órbitas de estacionamiento de llamadas con independientes rangos de números designados como números de llamada de grupo pickup y, a continuación, asignar usuarios a grupos de recogida de llamadas y la habilitación de los usuarios para su recogida de llamadas de grupo.
  
## <a name="clients-supported-for-group-call-pickup"></a>Clientes admitidos para recogida de llamadas de grupo

Cualquiera de los siguientes clientes pueden usar para atender las llamadas a los miembros del grupo llamar recogida:
  
- Skype Empresarial
    
- Lync 2013
    
- Lync 2010
    
- Lync Phone Edition
    
> [!NOTE]
> Los usuarios pueden usar cualquiera de estos clientes para atender las llamadas a los miembros del grupo llamar recogida, pero los usuarios deben estar alojados en un Skype para el grupo de servidores de negocio o un grupo de servidores de Lync Server 2013 con actualizaciones acumulativas para Lync Server 2013: febrero de 2013. 
  
No se admiten los siguientes clientes y dispositivos para las llamadas a los miembros del grupo llamar recogida de selección:
  
- Lync Mobile
    
- Aplicación Lync para Windows 8 y Windows RT
    
- Lync para iPad
    
- Teléfonos analógicos
    
- Teléfonos con números de la red telefónica conmutada (RTC)
    
## <a name="capacity-planning"></a>Planificación de la capacidad

En la siguiente tabla se describe el modelo de usuario de recogida de llamadas de grupo que puede utilizar como base para los requisitos de planeación de capacidad.
  
> [!IMPORTANT]
> Recogida de llamadas de grupo se basa en la aplicación de estacionamiento de llamadas. Tenga en cuenta que, para planear la capacidad de recuperación ante desastres, cada grupo de servidores de un grupo formado en par debe ser capaz de controlar las cargas de trabajo para servicios de estacionamiento de llamadas, incluyendo recogida de llamadas de grupo, en ambos grupos. 
  
**Modelo de usuario Pickup de llamada de grupo**

|**Métrica**|**Por grupo de servidores Front-End <br/> (con 8 servidores Front-End)**|**Por servidor Standard Edition**|
|:-----|:-----|:-----|
|Cantidad recomendada de usuarios por grupo  <br/> |50  <br/> |50  <br/> |
|Cantidad recomendada de grupos  <br/> |500  <br/> |60  <br/> |
|Cantidad máxima de usuarios por grupo habilitados para la atención de llamadas grupales  <br/> |25.000  <br/> |3.000  <br/> |
|Tasa máxima de llamadas entrantes al total de usuarios habilitados para la atención de llamadas grupales por grupo, por minuto  <br/> |500  <br/> |60  <br/> |
|Tasa máxima de llamadas recuperadas por los usuarios con la atención de llamadas grupales por grupo, por minuto  <br/> |200  <br/> |25  <br/> |
   
> [!NOTE]
> Para los grupos de servidores de Front-End que tienen menos de ocho servidores Front-End, calcular las métricas linealmente. Por ejemplo, si el grupo de servidores Front-End tiene un servidor Front-End, calcular la carga máxima como 1/8 de los valores que se muestran en la tabla. 
  
> [!NOTE]
> Puedes aumentar o disminuir la cantidad recomendada de usuarios por grupo y la cantidad de grupos siempre y cuando no supere la cantidad máxima de usuarios por grupo. Por ejemplo, el servidor Standard Edition puede tener 120 grupos con 25 usuarios por grupo debido a que el número de usuarios habilitados para recogida de llamadas de grupo es aún dentro el máximo de modelo de usuario (es decir, veces 120 grupos 25 usuarios es 3.000 usuarios habilitados para recogida de llamadas de grupo). 
  

