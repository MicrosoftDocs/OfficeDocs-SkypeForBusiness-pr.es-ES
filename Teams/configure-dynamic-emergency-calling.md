---
title: Configurar las llamadas de emergencia dinámicas
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
ms.reviewer: roykuntz
localization_priority: Normal
search.appverid: MET150
description: Configurar las llamadas de emergencia dinámicas
appliesto:
- Microsoft Teams
ms.openlocfilehash: 006f131183fe75b8246f0d2fa2d0ae28575e9e1d
ms.sourcegitcommit: 8fb89d6226b02ba8b1f8396eb4d1a37da4608b7c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/04/2019
ms.locfileid: "37396550"
---
# <a name="plan-and-configure-dynamic-emergency-calling-for-calling-plans"></a>Planear y configurar las llamadas de emergencia dinámicas para los planes de llamadas
Las llamadas de emergencia dinámicas para los planes de llamadas de Microsoft proporcionan la capacidad de configurar y enrutar llamadas de emergencia basadas en la ubicación actual del cliente de Teams.  La capacidad de llevar a cabo el enrutamiento automático para el correspondiente punto de respuesta de seguridad pública (PSAP) o para notificar personal de escritorio de seguridad varía según el país de uso del usuario de Teams.  

> [!Note] 
> Las llamadas de emergencia dinámicas actualmente solo están disponibles en los Estados Unidos. La notificación del centro de seguridad, sin embargo, es compatible con los límites de países.

**Dentro de los Estados Unidos**, puede configurar el enrutamiento dinámico de llamadas de emergencia de la siguiente manera:
  
- Si un cliente de Teams se encuentra en una ubicación de emergencia dinámica definida por el inquilino, las llamadas de emergencia de ese cliente se enrutan automáticamente al PSAP que atiende esa ubicación geográfica.  

- Si un cliente de Teams no se encuentra en una ubicación de emergencia dinámica definida por el inquilino, las llamadas de emergencia de ese cliente las puede filtrar un centro de atención nacional para determinar la ubicación de la persona que llama antes de transferir la llamada a la PSAP que atiende a esa ubicación geográfica.

Puede configurar la notificación del servicio de seguridad de la siguiente manera:

- Si un cliente de Teams se encuentra en un sitio de red definido por el inquilino, se notificará a los miembros del grupo de seguridad configurados para ese sitio.

- Si un cliente de Teams no se encuentra en un sitio de red definido por el inquilino, se notificará a los miembros del grupo de seguridad configurados para el usuario.

**Fuera de los Estados Unidos, las**llamadas de emergencia se dirigen a la PSAP que está asignada al número de teléfono asignado al usuario.  Algunos países, como el gran Reino Unido y Canadá, filtran las llamadas a nivel nacional antes de transferir a la persona que llama a la PSAP adecuada, mientras que otras se dirigen directamente a la PSAP, independientemente de dónde se encuentre el usuario en ese momento. 

Tenga en cuenta que puede configurar una notificación de servicio de seguridad dinámica para todos los usuarios del plan de llamadas.


## <a name="supported-clients"></a>Clientes compatibles

Actualmente se admiten los siguientes clientes.  Vuelva a consultar a menudo para ver las actualizaciones de esta lista.

- Cliente de escritorio de Teams para Windows
- Cliente de escritorio de Teams para Mac

## <a name="configure-dynamic-emergency-calling"></a>Configurar las llamadas de emergencia dinámicas

Para configurar las llamadas de emergencia dinámicas, debe realizar las siguientes tareas:

- [Configurar direcciones de emergencia](#configure-emergency-addresses)
- [Configurar las opciones de red](#configure-network-settings)
- [Configurar servicio de información de ubicación](#configure-location-information-service)
- [Configurar directivas de emergencia](#configure-emergency-policies)
- [Habilitar usuarios y sitios](#enable-users-and-sites)
- [Probar las llamadas de emergencia](#test-emergency-calling)


### <a name="configure-emergency-addresses"></a>Configurar direcciones de emergencia

Para admitir el enrutamiento automatizado dentro de los Estados Unidos, debe configurar completamente la dirección cívica que forma parte de las ubicaciones de emergencia asignadas a los identificadores de red e incluir los códigos geográficas asociados. (No se pueden asignar direcciones de emergencia sin códigos geográficas a los identificadores de red necesarios para las ubicaciones dinámicas).

- Si especifica una dirección de emergencia a través del centro de administración de Microsoft Teams, los códigos geográficas se incluyen automáticamente si se encuentra una coincidencia.

- Si no se encuentra ninguna coincidencia, tendrá la oportunidad de crear manualmente una dirección de emergencia.  

Esto significa que si una dirección de emergencia existente está configurada para hacer llamadas de emergencia, debe volver a crearse la misma dirección para incluir los códigos geográficas.  Para distinguir entre las dos direcciones, debe incluir una descripción diferente. La nueva dirección de emergencia se puede asignar a los usuarios que tienen la dirección antigua. Cuando se realiza una migración completa, la dirección anterior puede eliminarse. 

Para obtener más información sobre cómo configurar las direcciones de emergencia, vea [¿Qué son las ubicaciones de emergencia, los lugares y el enrutamiento de llamadas?](what-are-emergency-locations-addresses-and-call-routing.md)

### <a name="configure-network-settings"></a>Configurar las opciones de red

Debe configurar las opciones de red para obtener dinámicamente una ubicación de emergencia usada para el enrutamiento de las llamadas de emergencia y, opcionalmente, para proporcionar una configuración dinámica de las notificaciones del equipo de seguridad. La experiencia de llamadas de emergencia que deseas determinará qué configuración de red debe configurarse. 

Tenga en cuenta las siguientes definiciones:

- La IP de confianza contiene una colección de las direcciones IP externas de Internet de la red de la empresa y se usan para determinar si el extremo del usuario se encuentra dentro de la red corporativa. Las ubicaciones dinámicas solo se habilitarán si la IP externa del usuario coincide con una IP de la colección de IP de confianza.  Se puede establecer una coincidencia con las direcciones IP IPv4 o IPv6, y depende del formato del paquete IP que se envía a la configuración de red.

- Una región de red incluye una colección de sitios de red. 

- Un sitio de red representa una ubicación en la que su organización tiene un valor físico, como una oficina, un conjunto de edificios o un campus. Estos sitios se definen como una colección de subredes IP.

- Una subred de red debe estar asociada a un sitio de red específico. La ubicación de un cliente se determina en función de la subred de la red y el sitio de red asociado.  


Para los usuarios del plan de llamadas:

- Si se requiere la configuración dinámica de la notificación del escritorio de seguridad, debe configurar tanto las direcciones IP de confianza como los sitios de red.

- Si solo se necesitan ubicaciones dinámicas, debe configurar solo direcciones IP de confianza. 

- Si no es necesario, no es necesario configurar la configuración de red. 

Para obtener más información, vea [configuración de la red para el enrutamiento basado en la ubicación](location-based-routing-configure-network-settings.md), que describe cómo configurar las opciones de red. (La información de este artículo se aplica a los planes de llamadas y al enrutamiento directo).


### <a name="configure-location-information-service"></a>Configurar servicio de información de ubicación

Un cliente de Teams obtiene las direcciones de emergencia de las ubicaciones de emergencia asociadas a diferentes identificadores de red.  Se admiten las subredes y los puntos de acceso inalámbrico. (La compatibilidad con el conmutador/puerto Ethernet está pendiente).

Para configurar el servicio de información de ubicación (LIS) con identificadores de red y ubicaciones de emergencia, use los siguientes cmdlets:

- Get, Set, Remove-CsOnlineLisPort
- Get, Set, Remove-CsOnlineLisSwitch
- Get, Set, Remove-CsOnlineLisSubnet
- Get, Set, Remove-CsOnlineLisWirelessAccessPoint 

> [!Important] 
> Si se usan subredes como parte de sitios de red, deben redefinirse en el servicio de información de ubicación para representar ubicaciones dinámicas.


### <a name="configure-emergency-policies"></a>Configurar directivas de emergencia

Las directivas de emergencia determinan lo que sucede cuando un usuario de su organización hace una llamada de emergencia.  Puedes establecer a quién deseas notificar y cómo se les notifica cuando un usuario llama a servicios de emergencia. Por ejemplo, puede configurar opciones de directiva para notificar automáticamente al escritorio de seguridad de su organización y hacer que escuchen en llamadas de emergencia.

Para administrar las directivas de emergencia, use los cmdlets de directiva New-, set-and-CsTeamsEmergencyCalling.  Para obtener más información, consulte [Administrar directivas de llamadas de emergencia en Teams](manage-emergency-calling-policies.md).


### <a name="enable-users-and-sites"></a>Habilitar usuarios y sitios

Mientras que los usuarios del plan de llamadas se habilitan automáticamente para llamadas de emergencia, debe habilitar a los usuarios para recibir notificaciones de seguridad configurando la Directiva de llamadas de emergencia, como se muestra en el siguiente ejemplo:


```
Grant-CsTeamsEmergencyCallingPolicy -Identity user1 -PolicyName SecurityDeskNotification
```

También puede asignar la Directiva de llamadas de emergencia a un sitio de red como se muestra en el ejemplo siguiente, que asigna una directiva denominada "Directiva de llamadas de emergencia de Contoso 1" al sitio 1:

```
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallingPolicy "Contoso Emergency Calling Policy 1"
```

Si ha asignado una directiva de llamadas de emergencia a un sitio de red y a un usuario, y si ese usuario se encuentra en el sitio de red, la directiva asignada al sitio de red reemplaza la directiva asignada al usuario.


### <a name="test-emergency-calling"></a>Probar las llamadas de emergencia

Para probar las llamadas de emergencia en los Estados Unidos, use el número de emergencia de prueba predefinido 933.  Este número se enruta a un bot, que después vuelve a devolverle el número de teléfono de la persona que llama (identificación de la línea de llamada), la dirección o ubicación de emergencia, y si la llamada se dirige automáticamente a la PSAP o se ha superpuesto.  