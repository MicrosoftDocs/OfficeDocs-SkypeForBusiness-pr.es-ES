---
title: Caso práctico de Teams voice Contoso
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 06/17/2020
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
ms.reviewer: jowrig
search.appverid: MET150
f1.keywords:
- NOCSH
description: Caso práctico de voz de Teams para una corporación multinacional
appliesto:
- Microsoft Teams
ms.openlocfilehash: e4503576df8d8e9f3d332cda45eb235d8162cf53
ms.sourcegitcommit: af15d99837a389b6b26952211e65cd68c4b7f46e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/18/2020
ms.locfileid: "44786104"
---
# <a name="contoso-case-study-emergency-calling"></a>Caso práctico Contoso: Llamadas de emergencia

Para comprender la disponibilidad de las llamadas de emergencia y la terminología relacionada con las llamadas de emergencia: Dirección de emergencia, Lugar, Ubicación de emergencia y Dirección registrada, Contoso revisó Administrar llamadas de emergencia y Planear y configurar las llamadas de emergencia &mdash; &mdash; [dinámicas.](configure-dynamic-emergency-calling.md) [](what-are-emergency-locations-addresses-and-call-routing.md)

En Office 365, se habilita automáticamente un usuario del plan de llamadas para llamadas de emergencia. Pero solo los usuarios del plan de llamadas en Estados Unidos pueden usar ubicaciones dinámicas para enrutar llamadas de emergencia. 

En el caso del enrutamiento directo, Contoso aprendió que se requiere configuración adicional para enrutar llamadas de emergencia y, posiblemente, para la conectividad con asociados. El administrador debe configurar la conexión a un Proveedor de servicios de enrutamiento de emergencia (ERSP) (Estados Unidos) O configurar el controlador de borde de sesión (SBC) para una aplicación de número de identificación de ubicación de emergencia (ELIN).

Contoso tiene oficinas en los Estados Unidos y fuera de estos:

- En los Estados Unidos, los usuarios del plan de llamadas Contoso pueden usar ubicaciones dinámicas para enrutar llamadas de emergencia. 

- Fuera de los Estados Unidos, Contoso tiene algunos sitios que usan planes de llamadas y algunos sitios que están conectados a Sistema telefónico a través del enrutamiento directo.

## <a name="emergency-calling-use-cases"></a>Casos de uso de llamadas de emergencia

Después de decidir cómo contoso se conectará al sistema telefónico, Contoso identificó los siguientes casos de uso de las llamadas de emergencia: 

- [Usuario del plan de llamadas en Estados Unidos](#calling-plan-user-in-the-united-states) 

- [Usuario del plan de llamadas fuera de Estados Unidos](#calling-plan-user-outside-of-the-united-states)

- [Usuario que se conecta al sistema telefónico a través del enrutamiento directo](#user-who-connects-to-phone-system-through-direct-routing )


### <a name="calling-plan-user-in-the-united-states"></a>Usuario del plan de llamadas en Estados Unidos  

Hay requisitos para cuando el número de teléfono debe estar asociado a una ubicación de emergencia. Para entender estos requisitos, Contoso ha revisado [consideraciones para los planes de llamadas.](what-are-emergency-locations-addresses-and-call-routing.md#considerations-for-calling-plans) 

Tras cumplir estos requisitos, Contoso decidió asociar la ubicación con el número de teléfono cuando se asignó un número a un usuario en Estados Unidos.

### <a name="calling-plan-user-outside-of-the-united-states"></a>Usuario del plan de llamadas fuera de Estados Unidos 

Para entender cuándo un número de teléfono debe estar asociado a una ubicación de emergencia, Contoso revisó [consideraciones para planes de llamadas.](what-are-emergency-locations-addresses-and-call-routing.md#considerations-for-calling-plans) En función de los requisitos, Contoso decidió lo siguiente:  

-  Contoso asociará la ubicación con el número de teléfono cuando se asigne un número a un usuario de Canadá. 

- Contoso asignará una ubicación de emergencia cuando el número de teléfono se adquiera de Office 365 o cuando un número se transfiera de otro proveedor de servicios u operador. 

### <a name="user-who-connects-to-phone-system-through-direct-routing"></a>Usuario que se conecta al sistema telefónico a través del enrutamiento directo 

Para planear el enrutamiento de emergencia para este caso de uso, Contoso revisó [las consideraciones de enrutamiento directo.](what-are-emergency-locations-addresses-and-call-routing.md#considerations-for-direct-routing) Como los usuarios de enrutamiento directo no reciben llamadas de emergencia de la misma manera que los usuarios del plan de llamadas, Contoso tuvo que decidir cómo proporcionar llamadas de emergencia. El enrutamiento directo se puede conectar a un proveedor de servicios de enrutamiento de emergencia (ERSP). El enrutamiento directo también puede tener un SBC que incluya un número de identificación de ubicación de emergencia (ELIN).   

#### <a name="emergency-routing-service-provider-ersp-considerations"></a>Consideraciones del Proveedor de servicios de enrutamiento de emergencia (ERSP)

Los proveedores de servicios de enrutamiento de emergencia (ERSP) pueden enrutar automáticamente las llamadas de emergencia en función de la ubicación del autor de la llamada.  

- Si se integra un proveedor de servicios de enrutamiento de emergencia en una implementación de enrutamiento directo, las llamadas de emergencia con una ubicación adquirida dinámicamente se enruta automáticamente al punto de respuesta de seguridad pública (PSAP) que sirve a esa ubicación. 

- Las llamadas de emergencia sin una ubicación adquirida dinámicamente se pantallan primero para determinar la ubicación actual del usuario antes de conectar la llamada al centro de emergencias adecuado según la ubicación actualizada. 


#### <a name="elin-considerations"></a>Consideraciones de ELIN

Si una aplicación de ELIN SBC está integrada en una implementación de enrutamiento directo, es necesario seguir pasos de configuración adicionales para asociar las direcciones de emergencia con los números de teléfono.  

Contoso ha decidido usar controladores de borde de sesión que incluyen aplicaciones de número de identificación de ubicación de emergencia (ELIN).  

## <a name="security-desk-notification"></a>Notificación del servicio de seguridad

La capacidad de notificar al servicio de seguridad cuando se realiza una llamada de emergencia está disponible tanto para planes de llamadas de Microsoft como para enrutamiento directo de sistema telefónico. Contoso revisó los detalles de la notificación del servicio de seguridad para determinar si debería configurarse en sus oficinas.  

Contoso ha decidido usar una notificación del servicio de seguridad.

## <a name="configuration"></a>Configuración 

Contoso siguió los pasos de [Configurar llamadas de emergencia dinámicas](configure-dynamic-emergency-calling.md) para: 

- Asignar direcciones de emergencia 

- Configurar las opciones de red 

- Configurar el servicio de información de ubicación 

- Configurar directivas de emergencia 

- Habilitar usuarios y sitios 

- Probar llamadas de emergencia 

Una vez configuradas las llamadas de emergencia dinámicas, Contoso necesita asignar la ubicación al usuario adecuado.  

- Para agregar, cambiar o quitar una ubicación de emergencia de [su organización,](add-change-remove-emergency-location-organization.md) Contoso siguió los pasos descritos en Agregar, cambiar o quitar una ubicación de emergencia de su organización

- Para crear lugares para edificios, pisos y oficinas, Contoso siguió los pasos de Agregar, cambiar o quitar un lugar [para una ubicación de emergencia.](add-change-remove-emergency-place-organization.md) 

- Para asignar una ubicación de emergencia, Contoso ha seguido los pasos indicados en [Asignar o cambiar una ubicación de emergencia para un usuario.](assign-change-emergency-location-user.md) 

 