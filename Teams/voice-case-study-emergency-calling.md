---
title: Caso práctico de voz de Contoso
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
description: Estudio de casos de voz de Teams para la corporación multinacional
appliesto:
- Microsoft Teams
ms.openlocfilehash: e4503576df8d8e9f3d332cda45eb235d8162cf53
ms.sourcegitcommit: af15d99837a389b6b26952211e65cd68c4b7f46e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/18/2020
ms.locfileid: "44786104"
---
# <a name="contoso-case-study-emergency-calling"></a>Caso práctico de Contoso: llamadas de emergencia

Para comprender la disponibilidad de las llamadas de emergencia y la terminología relacionada con las llamadas de emergencia &mdash; , lugar, ubicación de emergencia y dirección registrada &mdash; contoso revisada [administrar llamadas de emergencia](what-are-emergency-locations-addresses-and-call-routing.md) y [planificar y configurar llamadas de emergencia dinámicas](configure-dynamic-emergency-calling.md).

En Office 365, un usuario del plan de llamadas se habilita automáticamente para las llamadas de emergencia. Pero solo los usuarios del plan de llamadas de Estados Unidos pueden usar ubicaciones dinámicas para el enrutamiento de llamadas de emergencia. 

Para el enrutamiento directo, contoso aprendió que es necesaria una configuración adicional para enrutar llamadas de emergencia y posiblemente para conectividad de socios. El administrador debe configurar la conexión a un proveedor de servicios de enrutamiento de emergencia (ERSP) (Estados Unidos) o configurar el controlador de borde de sesión (SBC) para una aplicación de número de identificación de ubicación de emergencia (ELIN).

Contoso tiene oficinas en los Estados Unidos y fuera de los Estados Unidos:

- En los Estados Unidos, los usuarios del plan de llamadas de Contoso pueden usar ubicaciones dinámicas para el enrutamiento de llamadas de emergencia. 

- Fuera de los Estados Unidos, Contoso tiene algunos sitios que usan planes de llamadas y algunos sitios que están conectados al sistema telefónico a través del enrutamiento directo.

## <a name="emergency-calling-use-cases"></a>Casos de uso de llamadas de emergencia

Después de decidir cómo contoso se conectará al sistema telefónico, contoso identificó los siguientes casos de uso de llamadas de emergencia: 

- [Usuario del plan de llamadas en los Estados Unidos](#calling-plan-user-in-the-united-states) 

- [Usuario del plan de llamadas fuera de los Estados Unidos](#calling-plan-user-outside-of-the-united-states)

- [Usuario que se conecta al sistema telefónico a través del enrutamiento directo](#user-who-connects-to-phone-system-through-direct-routing )


### <a name="calling-plan-user-in-the-united-states"></a>Usuario del plan de llamadas en los Estados Unidos  

Existen requisitos para cuando el número de teléfono debe asociarse con una ubicación de emergencia. Para comprender estos requisitos, contoso revisó las [consideraciones para las llamadas a planes](what-are-emergency-locations-addresses-and-call-routing.md#considerations-for-calling-plans). 

En función de estos requisitos, contoso decidió asociar la ubicación con el número de teléfono cuando se asigna un número a un usuario de los Estados Unidos.

### <a name="calling-plan-user-outside-of-the-united-states"></a>Usuario del plan de llamadas fuera de los Estados Unidos 

Para entender cuándo un número de teléfono debe asociarse a una ubicación de emergencia, contoso revisó las [consideraciones para las llamadas a planes](what-are-emergency-locations-addresses-and-call-routing.md#considerations-for-calling-plans). En función de los requisitos, contoso decidió lo siguiente:  

-  Contoso asociará la ubicación con el número de teléfono cuando se asigne un número a un usuario de Canadá. 

- Contoso asignará una ubicación de emergencia cuando se adquiera el número de teléfono de Office 365 o cuando se transfiera un número de otro proveedor de servicios u operador. 

### <a name="user-who-connects-to-phone-system-through-direct-routing"></a>Usuario que se conecta al sistema telefónico a través del enrutamiento directo 

Para planear la enrutamiento de emergencia para este caso de uso, contoso revisó las [consideraciones para el enrutamiento directo](what-are-emergency-locations-addresses-and-call-routing.md#considerations-for-direct-routing). Dado que los usuarios de enrutamiento directo no reciben llamadas de emergencia de la misma manera que los usuarios del plan de llamadas, contoso tuvo que decidir sobre cómo proporcionar llamadas de emergencia. El enrutamiento directo se puede conectar a un proveedor de servicios de enrutamiento de emergencia (ERSP). El enrutamiento directo también puede tener un SBC que incluya un número de identificación de ubicación de emergencia (ELIN).   

#### <a name="emergency-routing-service-provider-ersp-considerations"></a>Consideraciones sobre el proveedor de servicios de enrutamiento de emergencia (ERSP)

Los proveedores de servicios de enrutamiento de emergencia (ERSPs) pueden enrutar llamadas de emergencia automáticamente según la ubicación de la persona que llama.  

- Si un proveedor de servicios de enrutamiento de emergencia se integra en una implementación de enrutamiento directo, las llamadas de emergencia con una ubicación de adquisición dinámica se dirigirán automáticamente al punto de respuesta de seguridad pública (PSAP) que atiende esa ubicación. 

- Para determinar la ubicación actual del usuario antes de conectar la llamada al centro de distribución adecuado, deberás hacer llamadas de emergencia sin una ubicación de adquisición dinámica 


#### <a name="elin-considerations"></a>Consideraciones de ELIN

Si una aplicación de ELIN de SBC se integra en una implementación de enrutamiento directo, deben realizarse pasos de configuración adicionales para asociar las direcciones de emergencia a los números de teléfono.  

Contoso decidió usar controladores de borde de sesión que incluyen aplicaciones de número de identificación de ubicación de emergencia (ELIN).  

## <a name="security-desk-notification"></a>Notificación del centro de seguridad

La capacidad de notificar al escritorio cuando se realiza una llamada de emergencia está disponible tanto para los planes de llamadas de Microsoft como para el enrutamiento directo del sistema telefónico. Contoso revisó los detalles de la notificación del centro de seguridad para determinar si debe configurarse en su oficina.  

Contoso decidió usar la notificación del servicio de seguridad.

## <a name="configuration"></a>Configuración 

Contoso siguió los pasos de [configurar las llamadas de emergencia dinámicas](configure-dynamic-emergency-calling.md) a: 

- Asignar direcciones de emergencia 

- Configurar las opciones de red 

- Configurar servicio de información de ubicación 

- Configurar directivas de emergencia 

- Habilitar usuarios y sitios 

- Probar las llamadas de emergencia 

Después de configurar las llamadas de emergencia dinámicas, contoso necesitaba asignar la ubicación al usuario correspondiente.  

- Para agregar, cambiar o quitar una ubicación de emergencia para su organización, contoso siguió los pasos indicados en [Agregar, cambiar o quitar una ubicación de emergencia para su organización](add-change-remove-emergency-location-organization.md)

- Para crear lugares para edificios, plantas y oficinas, contoso siguió los pasos indicados en [Agregar, cambiar o quitar un lugar para una ubicación de emergencia](add-change-remove-emergency-place-organization.md) . 

- Para asignar una ubicación de emergencia, contoso siguió los pasos que se indican en [asignar o cambiar una ubicación de emergencia para un usuario](assign-change-emergency-location-user.md). 

 