---
title: Plan for Group Call Pickup in Skype Empresarial
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 3dc0eca8-c773-463c-96bb-9cd6afa2a840
description: Planeación de la recogida de llamadas de grupo en Skype Empresarial Server Telefonía IP empresarial, lo que permite a los usuarios responder a llamadas diseñadas originalmente para otros usuarios.
ms.openlocfilehash: 27d0ae55891981c715127cf6d61aab7135448cc3
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/04/2021
ms.locfileid: "60765258"
---
# <a name="plan-for-group-call-pickup-in-skype-for-business"></a>Plan for Group Call Pickup in Skype Empresarial
 
Planeación de la recogida de llamadas de grupo en Skype Empresarial Server Telefonía IP empresarial, lo que permite a los usuarios responder a llamadas diseñadas originalmente para otros usuarios.
  
La recogida de llamadas en grupo permite a los usuarios responder llamadas entrantes a sus compañeros desde sus propios teléfonos. Esto aumenta la disponibilidad de la línea de un usuario al permitir que otros usuarios respondan a una llamada entrante marcando un número de grupo de recogida de llamadas. Cuando se implementa la recogida de llamadas de grupo, el número de llamadas entrantes que se enruta al correo de voz puede reducirse considerablemente, lo que resulta especialmente útil para las llamadas de clientes externos a su organización.
  
La característica de recogida de llamadas de grupo está diseñada especialmente para unidades de negocio en entornos de oficina abierta. Las llamadas entrantes no son disruptivas porque solo suenan en el destino previsto. Sin embargo, otros usuarios que escuchan el timbre aún pueden recoger la llamada simplemente marcando el número de grupo. 
  
En entornos donde los usuarios no están ubicados en un diseño de oficina abierta o donde los usuarios que comparten una responsabilidad común se distribuyen geográficamente, la llamada de equipo presenta la solución más adecuada. La diferencia principal entre la recogida de llamadas de grupo y la llamada de grupo es que, con la recogida de llamadas de grupo, una llamada entrante suena solo en el destino previsto, pero cualquier persona puede elegir responderla marcando un número de grupo. Con la llamada de equipo, la llamada suena en todos los teléfonos de los miembros del equipo y cualquier usuario del equipo puede tomar el teléfono para responder a la llamada. Una diferencia adicional entre la recogida de llamadas de grupo y la llamada de grupo es que la recogida de llamadas de grupo la administra un administrador, a través de Skype Empresarial Server. Con la llamada de equipo, los usuarios finales administran la característica mediante el Skype Empresarial cliente. Por lo tanto, con la recogida de llamadas en grupo, este aspecto de la administración de llamadas se puede centralizar.
  
La recogida de llamadas grupales se basa en la aplicación Estacionamiento de llamadas. Al implementar la recogida de llamadas de grupo, se configura la tabla de órbitas de estacionamiento de llamadas con intervalos independientes de números de extensión designados como números de grupo de recogida de llamadas. Al igual que los números de órbita de estacionamiento de llamadas, los números de grupo de recogida de llamadas deben ser extensiones virtuales que no tengan ningún usuario o teléfono asignado. Cada grupo de servidores front-end donde implemente la recogida de llamadas de grupo puede tener uno o más intervalos de números de grupo de recogida de llamadas. Los intervalos de números de grupo deben ser únicos globalmente en toda Skype Empresarial Server implementación. 
  
> [!NOTE]
> Los intervalos de números designados como números de recogida de llamadas de grupo en la tabla de órbitas de estacionamiento de llamadas no se pueden administrar ni ver mediante el panel de control Skype Empresarial Server de llamadas. La única forma de ver todos los intervalos de números en la tabla de órbitas de estacionamiento de llamadas es usar Skype Empresarial Server Shell de administración. Del mismo modo, la única forma de agregar, modificar o quitar números de recogida de llamadas de grupo es usar Skype Empresarial Server Shell de administración. 
  
Después de configurar los números de grupo de recogida de llamadas, se asignan usuarios a un grupo de recogida de llamadas. Cualquier usuario que esté asignado a un grupo de recogida de llamadas puede tener sus llamadas contestadas por otros usuarios. Cuando una llamada llega a un usuario que está asignado a un grupo de recogida de llamadas, cualquier otro usuario que observe la llamada puede responderla marcando manualmente el número de grupo de recogida de llamadas. El usuario que toma la llamada no necesita ser miembro del grupo. Cuando otro usuario selecciona una llamada, se envía una notificación al número al que se llamó originalmente.
  
> [!NOTE]
> Un usuario puede ser miembro de un solo grupo de recogida de llamadas. 
  
> [!NOTE]
> Aunque cualquier usuario de la implementación de Skype Empresarial Server puede responder una llamada a un miembro del grupo de recogida de llamadas, la persona que responde a la llamada debe conocer el número de grupo de recogida de llamadas correcto que se debe marcar. 
  
Si un usuario marca un número de grupo de recogida de llamadas para responder a una llamada cuando suenan varios teléfonos del grupo, el usuario responde a la llamada que más tiempo ha sonado.
  
La configuración de llamadas simultáneas funcionará para los usuarios que tengan recogida de llamadas grupales. Es decir, una llamada realizada a un usuario que tiene recogida de llamadas de grupo sonará para todos los destinos configurados y otro usuario puede responder a la llamada. La excepción a esta regla es cuando el usuario configura la llamada simultánea para llamar a todos los miembros del equipo.
  
La recogida de llamadas grupales no se puede usar para responder a los siguientes tipos de llamadas:
  
- Llamadas a una línea privada
    
- Llamadas de un contacto al que se ha asignado la relación de privacidad amigos y familiares
    
    > [!TIP]
    > Un usuario que es miembro de un grupo de recogida de llamadas puede impedir que determinadas llamadas se recuperen a través de la recogida de llamadas de grupo marcando el contacto como contacto personal en el Skype Empresarial cliente. Para marcar un contacto como contacto personal, establece la relación de privacidad del contacto en Amigos y familia. Cualquier llamada entrante de los contactos con la relación de privacidad establecida en Amigos y familia no se puede recuperar mediante la recogida de llamadas de grupo. 
  
- Parte de vídeo de llamadas de audio y vídeo 
    
    > [!NOTE]
    > Si un usuario responde a una llamada de audio y vídeo, el usuario recibe solo el audio. La persona que llama o la persona que responde a la llamada puede escalar la llamada para agregar vídeo. 
  
- Llamadas simultáneas que se enruta a miembros de llamadas de equipo
    
- Llamadas enrutadas a un delegado
    
- Llamadas enrutadas a un grupo de respuesta
    
Los siguientes tipos de usuarios no pueden participar en la recogida de llamadas en grupo. Es decir, no deben incluirse en un grupo de recogida de llamadas de grupo y no pueden recoger llamadas para usuarios que tienen habilitada la recogida de llamadas de grupo.
  
- Usuarios que se encuentran en línea en una implementación híbrida
    
- Usuarios que no se encuentran en un grupo de servidores de Skype Empresarial Server 2015 o en un grupo de servidores de Lync Server 2013 con actualizaciones acumulativas para Lync Server 2013: febrero de 2013 en una implementación local
    
Si nadie responde una llamada a un miembro de un grupo de recogida de llamadas, la llamada se enruta según se especifica en la configuración del cliente. Es decir, la llamada va al correo de voz o se reenvía a otro destino, como se especifica en la configuración del cliente.
  
## <a name="deployment-and-requirements"></a>Implementación y requisitos

La recogida de llamadas de grupo se implementa automáticamente al implementar Telefonía IP empresarial y la aplicación estacionamiento de llamadas. Para habilitar la recogida de llamadas de grupo, configure la tabla de órbitas de estacionamiento de llamadas con intervalos separados de números designados como números de grupo de recogida de llamadas y, a continuación, asigne a los usuarios grupos de recogida de llamadas y habilite a los usuarios para la recogida de llamadas de grupo.
  
## <a name="clients-supported-for-group-call-pickup"></a>Clientes compatibles con la recogida de llamadas de grupo

Cualquiera de los siguientes clientes se puede usar para responder llamadas a los miembros de la recogida de llamadas en grupo:
  
- Skype Empresarial
    
- Lync 2013
    
- Lync 2010
    
- Lync Phone Edition
    
> [!NOTE]
> Los usuarios pueden usar cualquiera de estos clientes para responder llamadas a miembros de la recogida de llamadas en grupo, pero los usuarios deben hospedarse en un grupo de servidores de Skype Empresarial Server o un grupo de servidores de Lync Server 2013 con actualizaciones acumulativas para Lync Server 2013: febrero de 2013. 
  
Los siguientes clientes y dispositivos no son compatibles para recoger llamadas a miembros de la recogida de llamadas en grupo:
  
- Lync Mobile
    
- Aplicación lync para Windows 8 y Windows RT
    
- Lync para iPad
    
- Teléfonos analógicos
    
- Teléfonos con números de red telefónica conmutada (RTC)
    
## <a name="capacity-planning"></a>Planeamiento de la capacidad

En la tabla siguiente se describe el modelo de usuario de recogida de llamadas de grupo que puede usar como base para los requisitos de planeación de capacidad.
  
> [!IMPORTANT]
> La recogida de llamadas en grupo se basa en la aplicación Estacionamiento de llamadas. Tenga en cuenta que, para planear la capacidad de recuperación ante desastres, cada grupo de un grupo de servidores emparejado debe poder controlar las cargas de trabajo de los servicios de estacionamiento de llamadas, incluida la recogida de llamadas en grupo, en ambos grupos. 
  
**Modelo de usuario de recogida de llamadas de grupo**

|**Métrica**|**Por grupo de servidores front-end  <br/>  (con 8 servidores front-end)**|**Por Standard Edition servidor**|
|:-----|:-----|:-----|
|Número recomendado de usuarios por grupo  <br/> |50  <br/> |50  <br/> |
|Número recomendado de grupos  <br/> |500  <br/> |60  <br/> |
|Número máximo de usuarios por grupo habilitado para la recogida de llamadas de grupo  <br/> |25 000  <br/> |3,000  <br/> |
|Velocidad máxima de llamadas entrantes al total de usuarios habilitados para la recogida de llamadas en grupo por grupo por minuto  <br/> |500  <br/> |60  <br/> |
|Velocidad máxima de llamadas recuperadas por los usuarios con recogida de llamadas de grupo por grupo por minuto  <br/> |200  <br/> |25  <br/> |
   
> [!NOTE]
> Para grupos de servidores front-end con menos de ocho servidores front-end, calcule las métricas de forma lineal. Por ejemplo, si el grupo de servidores front-end tiene un servidor front-end, calcule la carga máxima como 1/8 de los valores que se muestran en la tabla. 
  
> [!NOTE]
> Puede aumentar o disminuir el número recomendado de usuarios por grupo y el número de grupos siempre que no supere el número máximo de usuarios por grupo. Por ejemplo, el servidor Standard Edition puede tener 120 grupos con 25 usuarios por grupo porque el número de usuarios habilitados para la recogida de llamadas de grupo sigue dentro del máximo del modelo de usuario (es decir, 120 grupos por 25 usuarios es 3.000 usuarios habilitados para la recogida de llamadas en grupo). 
  

