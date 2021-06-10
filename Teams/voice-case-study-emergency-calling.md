---
title: Teams caso práctico de Contoso de voz
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
description: Teams caso de voz para empresas multinacionales
appliesto:
- Microsoft Teams
ms.openlocfilehash: e4503576df8d8e9f3d332cda45eb235d8162cf53
ms.sourcegitcommit: af15d99837a389b6b26952211e65cd68c4b7f46e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/18/2020
ms.locfileid: "44786104"
---
# <a name="contoso-case-study-emergency-calling"></a>Caso práctico de Contoso: Llamadas de emergencia

Para comprender la disponibilidad de llamadas de emergencia y terminología relacionadas con las llamadas de emergencia Dirección de emergencia, Lugar, Ubicación de emergencia y Dirección registrada Contoso revisó Administrar llamadas de emergencia y Planear y configurar llamadas de emergencia &mdash; &mdash; [dinámicas.](configure-dynamic-emergency-calling.md) [](what-are-emergency-locations-addresses-and-call-routing.md)

En Office 365, un usuario del Plan de llamadas se habilita automáticamente para las llamadas de emergencia. Pero solo los usuarios del Plan de llamadas de Estados Unidos pueden usar ubicaciones dinámicas para enrutar llamadas de emergencia. 

En El enrutamiento directo, Contoso aprendió que se requiere una configuración adicional para enrutar llamadas de emergencia y posiblemente para la conectividad de partners. El administrador debe configurar la conexión a un proveedor de servicios de enrutamiento de emergencia (ERSP) (Estados Unidos) O configurar el controlador de borde de sesión (SBC) para una aplicación de número de identificación de ubicación de emergencia (ELIN).

Contoso tiene oficinas en Estados Unidos y fuera de los Estados Unidos:

- En Estados Unidos, los usuarios del Plan de llamadas contoso pueden usar ubicaciones dinámicas para enrutar llamadas de emergencia. 

- Fuera de los Estados Unidos, Contoso tiene algunos sitios que usan planes de llamadas y algunos sitios que están conectados a Sistema telefónico mediante enrutamiento directo.

## <a name="emergency-calling-use-cases"></a>Casos de uso de llamadas de emergencia

Después de decidir cómo Contoso se conectará Teléfono sistema, Contoso identificó los siguientes casos de uso de llamadas de emergencia: 

- [Usuario del plan de llamadas en Estados Unidos](#calling-plan-user-in-the-united-states) 

- [Usuario del Plan de llamadas fuera de los Estados Unidos](#calling-plan-user-outside-of-the-united-states)

- [Usuario que se conecta a Sistema telefónico mediante enrutamiento directo](#user-who-connects-to-phone-system-through-direct-routing )


### <a name="calling-plan-user-in-the-united-states"></a>Usuario del plan de llamadas en Estados Unidos  

Hay requisitos para cuando el número de teléfono debe estar asociado a una ubicación de emergencia. Para comprender estos requisitos, Contoso revisó [Consideraciones para planes de llamadas.](what-are-emergency-locations-addresses-and-call-routing.md#considerations-for-calling-plans) 

En función de estos requisitos, Contoso decidió asociar la ubicación con el número de teléfono cuando se asigna un número a un usuario en Estados Unidos.

### <a name="calling-plan-user-outside-of-the-united-states"></a>Usuario del Plan de llamadas fuera de los Estados Unidos 

Para comprender cuándo un número de teléfono debe estar asociado a una ubicación de emergencia, Contoso revisó Consideraciones para [planes de llamadas.](what-are-emergency-locations-addresses-and-call-routing.md#considerations-for-calling-plans) Según los requisitos, Contoso decidió lo siguiente:  

-  Contoso asociará la ubicación con el número de teléfono cuando se asigne un número a un usuario en Canadá. 

- Contoso asignará una ubicación de emergencia cuando el número de teléfono se adquiere de Office 365 o cuando se transfiere un número de otro proveedor de servicios u operador. 

### <a name="user-who-connects-to-phone-system-through-direct-routing"></a>Usuario que se conecta a Sistema telefónico mediante enrutamiento directo 

Para planear el enrutamiento de emergencia para este caso de uso, Contoso revisó [Consideraciones para enrutamiento directo.](what-are-emergency-locations-addresses-and-call-routing.md#considerations-for-direct-routing) Como los usuarios de Enrutamiento directo no reciben llamadas de emergencia de la misma manera que los usuarios del Plan de llamadas, Contoso tuvo que decidir cómo proporcionar llamadas de emergencia. El enrutamiento directo se puede conectar a un proveedor de servicios de enrutamiento de emergencia (ERSP). El enrutamiento directo también puede tener un SBC que incluye un número de identificación de ubicación de emergencia (ELIN).   

#### <a name="emergency-routing-service-provider-ersp-considerations"></a>Consideraciones del Proveedor de servicios de enrutamiento de emergencia (ERSP)

Los proveedores de servicios de enrutamiento de emergencia (ERSP) pueden enrutar automáticamente las llamadas de emergencia en función de la ubicación del autor de la llamada.  

- Si un proveedor de servicios de enrutamiento de emergencia está integrado en una implementación de enrutamiento directo, las llamadas de emergencia con una ubicación adquirida dinámicamente se enruta automáticamente al Punto de respuesta de seguridad pública (PSAP) que sirve a esa ubicación. 

- Las llamadas de emergencia sin una ubicación adquirida dinámicamente se primero se proyectan para determinar la ubicación actual del usuario antes de conectar la llamada al centro de envío adecuado en función de la ubicación actualizada. 


#### <a name="elin-considerations"></a>Consideraciones de ELIN

Si una aplicación ELIN de SBC está integrada en una implementación de enrutamiento directo, es necesario realizar pasos de configuración adicionales para asociar las direcciones de emergencia con números de teléfono.  

Contoso decidió usar controladores de borde de sesión que incluyen aplicaciones de número de identificación de ubicación de emergencia (ELIN).  

## <a name="security-desk-notification"></a>Notificación de escritorio de seguridad

La capacidad de notificar al departamento de seguridad cuando se realiza una llamada de emergencia está disponible tanto para planes de llamadas de Microsoft como para Sistema telefónico enrutamiento directo. Contoso revisó los detalles en la notificación de escritorio de seguridad para determinar si esto se debe configurar en sus oficinas  

Contoso decidió usar la notificación de escritorio de seguridad.

## <a name="configuration"></a>Configuración 

Contoso siguió los pasos de [Configurar llamadas de emergencia dinámicas](configure-dynamic-emergency-calling.md) para: 

- Asignar direcciones de emergencia 

- Configurar la configuración de red 

- Configurar el servicio de información de ubicación 

- Configurar directivas de emergencia 

- Habilitar usuarios y sitios 

- Probar llamadas de emergencia 

Una vez configuradas las llamadas de emergencia dinámicas, Contoso necesitaba asignar la ubicación al usuario adecuado.  

- Para agregar, cambiar o quitar una ubicación de emergencia para [su organización,](add-change-remove-emergency-location-organization.md) Contoso siguió los pasos de Agregar, cambiar o quitar una ubicación de emergencia para su organización

- Para crear lugares para edificios, pisos y oficinas, Contoso siguió los pasos de Agregar, cambiar o quitar un lugar para [una ubicación de emergencia.](add-change-remove-emergency-place-organization.md) 

- Para asignar una ubicación de emergencia, Contoso siguió los pasos de [Asignar o cambiar una ubicación de emergencia para un usuario.](assign-change-emergency-location-user.md) 

 