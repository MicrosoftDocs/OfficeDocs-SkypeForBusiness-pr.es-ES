---
title: Planificar la atención de llamadas grupales en Skype Empresarial
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
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 3dc0eca8-c773-463c-96bb-9cd6afa2a840
description: Planificación de la atención de llamadas grupales en Skype Empresarial Server Telefonía IP empresarial, que permite a los usuarios responder llamadas destinadas originalmente a otros usuarios.
ms.openlocfilehash: 874b9385352a8c51d9c9a356dd0ccc2ca3070601
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825620"
---
# <a name="plan-for-group-call-pickup-in-skype-for-business"></a>Planificar la atención de llamadas grupales en Skype Empresarial
 
Planificación de la atención de llamadas grupales en Skype Empresarial Server Telefonía IP empresarial, que permite a los usuarios responder llamadas destinadas originalmente a otros usuarios.
  
La atención de llamadas grupales permite a los usuarios responder llamadas entrantes a sus compañeros desde sus propios teléfonos. Esto aumenta la disponibilidad de la línea de un usuario al permitir que otros usuarios respondan a una llamada entrante marcando un número de grupo de atención de llamadas. Cuando se implementa la atención de llamadas grupales, el número de llamadas entrantes que se enruta al correo de voz puede reducirse considerablemente, lo que resulta especialmente útil para las llamadas de clientes externos a la organización.
  
La característica de atención de llamadas grupales está diseñada en particular para unidades de negocio en entornos de oficina abiertos. Las llamadas entrantes no son molestas porque solo suenan en el destino previsto. Sin embargo, otros usuarios que escuchan el sonido pueden seguir seleccionando el número de grupo. 
  
En entornos en los que los usuarios no están ubicados en un diseño de oficina abierta o donde los usuarios que comparten una responsabilidad común se distribuyen geográficamente, la llamada de equipo presenta la solución más adecuada. La principal diferencia entre la atención de llamadas grupales y la llamada de equipo es que, con la atención de llamadas grupales, una llamada entrante solo suena en el destino previsto, pero cualquier persona puede elegir responderla marcando un número de grupo. Con la llamada de equipo, la llamada suena en todos los teléfonos de los miembros del equipo, y cualquier usuario del equipo puede tomar el teléfono para responder a la llamada. Una diferencia adicional entre la atención de llamadas grupales y la llamada de equipo es que la atención de llamadas grupales la administra un administrador, a través de Skype Empresarial Server. Con la llamada de equipo, los usuarios finales administran la característica mediante el cliente de Skype Empresarial. Por lo tanto, con la atención de llamadas grupales, este aspecto de la administración de llamadas se puede centralizar.
  
La atención de llamadas grupales se basa en la aplicación Estacionamiento de llamadas. Al implementar la atención de llamadas grupales, se configura la tabla de órbitas de estacionamiento de llamadas con intervalos separados de números de extensión designados como números de grupo de atención de llamadas. Al igual que los números de órbita de estacionamiento de llamadas, los números de grupo de atención de llamadas deben ser extensiones virtuales que no tengan ningún usuario o teléfono asignado. Cada grupo de servidores front-end donde implemente la atención de llamadas grupales puede tener uno o más intervalos de números de grupo de atención de llamadas. Los intervalos de números de grupo deben ser únicos globalmente en toda la implementación de Skype Empresarial Server. 
  
> [!NOTE]
> Los intervalos de números designados como números de atención de llamadas grupales en la tabla de órbitas de estacionamiento de llamadas no se pueden administrar ni ver mediante el Panel de control de Skype Empresarial Server. La única forma de ver todos los intervalos de números en la tabla de órbitas de estacionamiento de llamadas es usar el Shell de administración de Skype Empresarial Server. De forma similar, la única forma de agregar, modificar o quitar números de atención de llamadas grupales es usar el Shell de administración de Skype Empresarial Server. 
  
Después de configurar los números del grupo de atención de llamadas, asigne usuarios a un grupo de atención de llamadas. Cualquier usuario asignado a un grupo de atención de llamadas puede tener sus llamadas contestadas por otros usuarios. Cuando una llamada llega a un usuario asignado a un grupo de atención de llamadas, cualquier otro usuario que observe la llamada puede responderla marcando manualmente el número del grupo de atención de llamadas. El usuario que toma la llamada no necesita ser miembro del grupo. Cuando otro usuario recibe una llamada, se envía una notificación al número al que se llamó originalmente.
  
> [!NOTE]
> Un usuario puede ser miembro de un solo grupo de atención de llamadas. 
  
> [!NOTE]
> Aunque cualquier usuario de la implementación de Skype Empresarial Server puede responder a una llamada a un miembro del grupo de atención de llamadas, la persona que responda a la llamada debe conocer el número de grupo de atención de llamadas correcto que se debe marcar. 
  
Si un usuario marca un número de grupo de atención de llamadas para responder a una llamada cuando suenan varios teléfonos del grupo, el usuario responde a la llamada que más tiempo ha sonado.
  
La configuración de llamadas simultáneas funcionará para los usuarios que tengan atención de llamadas grupales. Es decir, una llamada realizada a un usuario que tiene atención de llamadas grupales sonará para todos los destinos configurados y otro usuario puede responder a la llamada. La excepción a esta regla es cuando el usuario configura las llamadas simultáneas para llamar a todos los miembros del equipo.
  
La atención de llamadas grupales no se puede usar para responder a los siguientes tipos de llamadas:
  
- Llamadas a una línea privada
    
- Llamadas de un contacto al que se ha asignado la relación de privacidad Amigos y familiares
    
    > [!TIP]
    > Un usuario que es miembro de un grupo de atención de llamadas puede evitar que se recuperen determinadas llamadas a través de la atención de llamadas grupales marcando el contacto como contacto personal en el cliente de Skype Empresarial. Para marcar un contacto como contacto personal, establezca la relación de privacidad del contacto en Amigos y familiares. Las llamadas entrantes de contactos con la relación de privacidad establecida en Amigos y familiares no se pueden recuperar mediante la atención de llamadas grupales. 
  
- Parte de vídeo de las llamadas de audio y vídeo 
    
    > [!NOTE]
    > Si un usuario responde a una llamada de audio o vídeo, el usuario recibe solo el audio. La persona que llama o la persona que responde la llamada puede escalar la llamada para agregar vídeo. 
  
- Llamadas de llamadas simultáneas que se enrutar a los miembros de la llamada de equipo
    
- Llamadas enrutadas a un delegado
    
- Llamadas enrutadas a un grupo de respuesta
    
Los siguientes tipos de usuarios no pueden participar en la atención de llamadas grupales. Es decir, no deben incluirse en un grupo de atención de llamadas grupales y no pueden realizar llamadas para los usuarios que tienen habilitada la atención de llamadas grupales.
  
- Usuarios que están en línea en una implementación híbrida
    
- Usuarios que no están en un grupo de Skype Empresarial Server 2015 o en un grupo de Lync Server 2013 con actualizaciones acumulativas para Lync Server 2013: febrero de 2013 en una implementación local
    
Si nadie responde una llamada a un miembro de un grupo de atención de llamadas, la llamada se enruta como se especifica en la configuración del cliente. Es decir, la llamada va al correo de voz o se reenvía a un destino diferente, como se especifica en la configuración del cliente.
  
## <a name="deployment-and-requirements"></a>Implementación y requisitos

La atención de llamadas grupales se implementa automáticamente al implementar Telefonía IP empresarial aplicación estacionamiento de llamadas. Para habilitar la atención de llamadas grupales, configure la tabla de órbitas de estacionamiento de llamadas con intervalos separados de números designados como números de grupo de atención de llamadas y, a continuación, asigne usuarios a grupos de atención de llamadas y habilite los usuarios para la atención de llamadas grupales.
  
## <a name="clients-supported-for-group-call-pickup"></a>Clientes compatibles con la atención de llamadas grupales

Cualquiera de los siguientes clientes se puede usar para responder llamadas a miembros de la atención de llamadas grupales:
  
- Skype Empresarial
    
- Lync 2013
    
- Lync 2010
    
- Lync Phone Edition
    
> [!NOTE]
> Los usuarios pueden usar cualquiera de estos clientes para responder llamadas a los miembros de la respuesta de llamadas grupales, pero los usuarios deben estar en un grupo de Skype Empresarial Server o un grupo de Lync Server 2013 con actualizaciones acumulativas para Lync Server 2013: febrero de 2013. 
  
No se admiten los siguientes clientes y dispositivos para la atención de llamadas a miembros de la atención de llamadas grupales:
  
- Lync Mobile
    
- Aplicación lync para Windows 8 y Windows RT
    
- Lync para iPad
    
- Teléfonos analógicos
    
- Teléfonos con números de red telefónica conmutada (RTC)
    
## <a name="capacity-planning"></a>Planeamiento de capacidad

En la tabla siguiente se describe el modelo de usuario de atención de llamadas grupales que puede usar como base para los requisitos de planeación de capacidad.
  
> [!IMPORTANT]
> La atención de llamadas grupales se basa en la aplicación Estacionamiento de llamadas. Tenga en cuenta que, para planear la capacidad de recuperación ante desastres, cada grupo de un grupo emparejado debe ser capaz de administrar las cargas de trabajo de los servicios de estacionamiento de llamadas, incluida la atención de llamadas grupales, en ambos grupos. 
  
**Modelo de usuario de atención de llamadas grupales**

|**Métrica**|**Por grupo de servidores front-end  <br/>  (con 8 servidores front-end)**|**Por servidor Standard Edition**|
|:-----|:-----|:-----|
|Número recomendado de usuarios por grupo  <br/> |50  <br/> |50  <br/> |
|Número recomendado de grupos  <br/> |500  <br/> |60  <br/> |
|Número máximo de usuarios por grupo habilitados para la atención de llamadas grupales  <br/> |25 000  <br/> |3,000  <br/> |
|Tasa máxima de llamadas entrantes al total de usuarios habilitados para la atención de llamadas grupales por grupo por minuto  <br/> |500  <br/> |60  <br/> |
|Tasa máxima de llamadas recuperadas por usuarios con atención de llamadas grupales por grupo por minuto  <br/> |200  <br/> |25  <br/> |
   
> [!NOTE]
> Para los grupos de servidores front-end que tienen menos de ocho servidores front-end, calcule las métricas linealmente. Por ejemplo, si el grupo de servidores front-end tiene un servidor front-end, calcule la carga máxima como 1/8 de los valores que se muestran en la tabla. 
  
> [!NOTE]
> Puede aumentar o disminuir el número recomendado de usuarios por grupo y el número de grupos siempre que no supere el número máximo de usuarios por grupo. Por ejemplo, el servidor Standard Edition puede tener 120 grupos con 25 usuarios por grupo porque el número de usuarios habilitados para la atención de llamadas grupales sigue estando dentro del máximo del modelo de usuario (es decir, 120 grupos por 25 usuarios es 3.000 usuarios habilitados para la atención de llamadas grupales). 
  

