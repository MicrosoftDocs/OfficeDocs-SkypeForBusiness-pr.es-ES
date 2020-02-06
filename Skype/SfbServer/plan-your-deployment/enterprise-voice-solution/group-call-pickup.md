---
title: Plan para la recogida de llamadas grupales en Skype empresarial
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: Planificación de la recogida de llamadas grupales en la telefonía IP empresarial de Skype empresarial, que permite a los usuarios contestar llamadas originalmente destinadas a otros.
ms.openlocfilehash: 0be7adb5b3832851b9c38179416cfedb414508b0
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802880"
---
# <a name="plan-for-group-call-pickup-in-skype-for-business"></a>Plan para la recogida de llamadas grupales en Skype empresarial
 
Planificación de la recogida de llamadas grupales en la telefonía IP empresarial de Skype empresarial, que permite a los usuarios contestar llamadas originalmente destinadas a otros.
  
La recogida de llamada grupal permite a los usuarios contestar llamadas entrantes a sus colegas desde sus propios teléfonos. De esta forma, se aumenta la disponibilidad de la línea de un usuario, ya que permite que otros usuarios respondan una llamada entrante al marcar un número de grupo de atención de llamadas. Cuando se implementa la recogida de llamadas grupales, el número de llamadas entrantes que se dirigen al correo de voz se puede reducir significativamente, lo cual es especialmente útil para llamadas de clientes externos a su organización.
  
La característica de recogida de llamadas grupales está diseñada especialmente para las unidades de negocio en entornos de Office abiertos. Las llamadas entrantes no resultan molestas porque solo suenan en el destino previsto. Pero los otros usuarios que escuchan el timbre pueden atender la llamada muy fácilmente al marcar el número del grupo. 
  
In environments where users are not located in an open office layout, or where users who share a common responsibility are geographically distributed, team call presents the most suitable solution. La principal diferencia entre la recogida de llamadas Grupals y la llamada de equipo es que, con la recogida de llamadas grupales, las llamadas entrantes solo suenan en el destino previsto, pero cualquier persona puede responderla marcando un número de grupo. With team call, the call rings at all the team members' phones, and any user in the team can pick up the phone to answer the call. Una diferencia adicional entre la recogida de llamadas Grupals y la llamada de equipo es que un administrador administra la recogida de llamadas de grupo a través de Skype empresarial Server. Con la llamada de equipo, los usuarios finales administran la característica con el cliente de Skype empresarial. Con la recogida de llamadas grupales, este aspecto de la administración de llamadas puede centralizarse.
  
La recogida de llamadas grupales está integrada en la aplicación de estacionamiento de llamadas. Cuando se implementa la recogida de llamadas grupales, se configura la tabla de llamadas en órbita con distintos intervalos de números de extensión que se designan como números de grupo de recogida de llamadas. Al igual que los números de órbita del estacionamiento de llamadas, los números de grupo de atención de llamadas necesitan ser extensiones virtuales que no tengan asignado ningún usuario o teléfono. Cada grupo de servidores front-end en el que se implementa la recogida de llamadas grupales puede tener uno o más intervalos de números de grupo de recogida de llamadas. Los intervalos de números de grupo deben ser únicos globalmente en la implementación de Skype empresarial Server. 
  
> [!NOTE]
> Los intervalos de números que se designan como números de recogida de llamadas grupales en la tabla llamada en órbita de la llamada no pueden administrarse ni verse mediante el panel de control de Skype empresarial Server. La única forma de ver todos los intervalos de números en la tabla llamada de la órbita de la tabla de la órbita es usar el shell de administración de Skype empresarial Server. De forma similar, la única manera de agregar, modificar o quitar números de recogida de llamadas de grupo es usar el shell de administración de Skype empresarial. 
  
Una vez configurados los números de grupo de atención de llamadas, necesitas asignar los usuarios a un grupo de atención de llamadas. Las llamadas de un usuario asignado a un grupo de atención de llamadas pueden responderlas otros usuarios. Cuando entra una llamada para un usuario asignado a un grupo de atención de llamadas, cualquier otro usuario que escuche la llamada puede atenderla marcando de forma manual el número del grupo de atención de llamadas. No es necesario que el usuario que atiende la llamada sea miembro del grupo. Cuando otro usuario atiende una llamada, se envía una notificación al número al que se llamó originalmente.
  
> [!NOTE]
> Un usuario solo puede pertenecer a un grupo de atención de llamadas. 
  
> [!NOTE]
> Aunque cualquier usuario de la implementación de Skype empresarial Server puede responder a una llamada a un miembro del grupo de recogida de llamadas, la persona que contesta la llamada debe conocer el número de grupo de recogida de llamadas correcto para marcar. 
  
Si un usuario marca el número de un grupo de atención de llamadas para responder una llamada cuando suenan varios teléfonos del grupo, atenderá la llamada que ha sonado por más tiempo.
  
La configuración de llamadas simultáneas resulta útil para los usuarios que disponen de la atención de llamadas grupales. Es decir, una llamada realizada a un usuario que tiene la característica de recogida de llamadas de grupo sonará para todos los destinos configurados y otro usuario podrá contestar la llamada. La excepción a esta regla es cuando un usuario configura las llamadas simultáneas para llamar a todos los miembros del grupo.
  
La recogida de llamada grupal no se puede usar para responder a los siguientes tipos de llamadas:
  
- Llamadas a una línea privada
    
- Llamadas de un contacto al que se ha asignado la relación de privacidad Amigos y familiares
    
    > [!TIP]
    > Un usuario que sea miembro de un grupo de recogida de llamadas puede impedir que se recuperen determinadas llamadas a través de la recogida de llamadas grupales marcando el contacto como contacto personal en el cliente de Skype empresarial. Para marcar un contacto como contacto personal, establece la relación de privacidad del contacto en Amigos y familiares. Las llamadas entrantes de contactos con la relación de privacidad establecida a amigos y familiares no se pueden recuperar mediante la recogida de llamadas grupales. 
  
- Parte de vídeo de llamadas de audio y vídeo 
    
    > [!NOTE]
    > Si un usuario responde una llamada de audio y vídeo, solo recibe el audio. La persona que llama o la persona que responde la llamada puede escalarla para agregar vídeo. 
  
- Llamadas simultáneas redirigidas a miembros de llamada de equipo
    
- Llamadas redirigidas a un delegado
    
- Llamadas redirigidas a un grupo de respuesta
    
Los siguientes tipos de usuarios no pueden participar en la recogida de llamadas grupales. Es decir, no deben incluirse en un grupo de recogida de llamadas Grupals y no pueden atender llamadas de usuarios que tienen habilitada la recogida de llamadas grupales.
  
- Usuarios alojados en línea en una implementación híbrida
    
- Usuarios que no están alojados en un grupo de servidores de Skype empresarial 2015 o un grupo de servidores de Lync Server 2013 con actualizaciones acumulativas para Lync Server 2013:2013 de febrero en una implementación local
    
Si nadie atiende una llamada realizada a un miembro de un grupo de atención de llamadas, la llamada se redirige según lo especificado en la configuración del cliente. Es decir, la llamada se desvía al correo de voz o se reenvía a otro destino, tal como se especifique en la configuración del cliente.
  
## <a name="deployment-and-requirements"></a>Requisitos e implementación

La recopilación de llamadas grupales se implementa automáticamente al implementar la telefonía IP empresarial y la aplicación estacionamiento de llamadas. Para habilitar la recopilación de llamadas de grupo, configure la tabla de llamadas en órbita con intervalos de números designados como números de grupo de recogida de llamadas y, a continuación, asigne usuarios para llamar a grupos de recogida y habilitar a los usuarios para la recogida de llamadas grupales.
  
## <a name="clients-supported-for-group-call-pickup"></a>Clientes compatibles con la recogida de llamadas grupales

Puede usar cualquiera de los siguientes clientes para responder a los miembros de la recogida de llamadas grupales:
  
- Skype Empresarial
    
- Lync 2013
    
- Lync 2010
    
- Lync Phone Edition
    
> [!NOTE]
> Los usuarios pueden usar cualquiera de estos clientes para responder a los miembros de la recogida de llamadas grupales, pero los usuarios deben estar alojados en un grupo de servidores de Skype empresarial o un grupo de servidores de Lync Server 2013 con actualizaciones acumulativas para Lync Server 2013: febrero de 2013. 
  
Los siguientes clientes y dispositivos no son compatibles con la recopilación de llamadas a miembros de la recogida de llamadas grupales:
  
- Lync Mobile
    
- Aplicación Lync para Windows 8 y Windows RT
    
- Lync para iPad
    
- Teléfonos analógicos
    
- Teléfonos con números de la red telefónica conmutada (RTC)
    
## <a name="capacity-planning"></a>Planificación de la capacidad

En la siguiente tabla se describe el modelo de usuario de recogida de llamadas grupales que puede usar como base para los requisitos de planes de capacidad.
  
> [!IMPORTANT]
> La recogida de llamadas grupales se basa en la aplicación de estacionamiento de llamadas. Tenga en cuenta que, para la planeación de la capacidad de recuperación ante desastres, cada grupo de un grupo emparejado debería poder controlar las cargas de trabajo de los servicios de estacionamiento de llamadas, incluida la recogida de llamadas grupales, en ambos grupos. 
  
**Modelo de usuario de llamada grupal**

|**Métrica**|**Por grupo <br/> front-end (con 8 servidores frontales)**|**Por servidor Standard Edition**|
|:-----|:-----|:-----|
|Cantidad recomendada de usuarios por grupo  <br/> |50  <br/> |50  <br/> |
|Cantidad recomendada de grupos  <br/> |500  <br/> |60  <br/> |
|Cantidad máxima de usuarios por grupo habilitados para la atención de llamadas grupales  <br/> |25 000  <br/> |3 000  <br/> |
|Tasa máxima de llamadas entrantes al total de usuarios habilitados para la atención de llamadas grupales por grupo, por minuto  <br/> |500  <br/> |60  <br/> |
|Tasa máxima de llamadas recuperadas por los usuarios con la atención de llamadas grupales por grupo, por minuto  <br/> |200  <br/> |veinticinco  <br/> |
   
> [!NOTE]
> Para los grupos de servidores front-end que tienen menos de ocho servidores front-end, calcule las métricas linealmente. Por ejemplo, si el grupo de servidores front-end tiene un servidor front-end, calcule la carga máxima como 1/8 de los valores que se muestran en la tabla. 
  
> [!NOTE]
> Puedes aumentar o disminuir la cantidad recomendada de usuarios por grupo y la cantidad de grupos siempre y cuando no supere la cantidad máxima de usuarios por grupo. Por ejemplo, su servidor Standard Edition puede tener 120 grupos con 25 usuarios por grupo, porque la cantidad de usuarios habilitada para la recogida de llamadas grupales todavía está dentro del modelo de usuario máximo (es decir, 120 grupos de 25 usuarios es 3.000 usuarios habilitados para la recogida de llamadas grupales). 
  

