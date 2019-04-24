---
title: Planificar IPv6 en Skype Empresarial
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 01f77196-38f4-4292-9480-2e2fbd57eabe
description: 'Resumen: Implementar IPv6 antes de instalar Skype para Business Server.'
ms.openlocfilehash: c2ac3470646c78e0a7312fb9390a712321793915
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32206285"
---
# <a name="plan-for-ipv6-in-skype-for-business"></a>Planificar IPv6 en Skype Empresarial
 
**Resumen:** Implementar IPv6 antes de instalar Skype para Business Server.
  
Skype para Business Server incluye compatibilidad con IP versión 6 (IPv6) direcciones, junto con el soporte técnico continuado de IP versión 4 (IPv4) direcciones. 

Las direcciones IPv4 son direcciones de 32 bits que permiten a los equipos comunicarse a través de Internet. Debido al número creciente de dispositivos en todo el mundo, las direcciones IPv4 disponibles se agoten. Por este motivo, muchos dispositivos nuevos se mueven a con las direcciones IPv6. Las direcciones IPv6 cumplen la misma función que las direcciones IPv4 (con algunas características adicionales), pero en lugar de usar solo 32 bits, usan 128 bits. Esto no solo proporciona un nuevo conjunto de direcciones, sino también una cantidad mucho más elevada de estas. 

Las direcciones IPv4 típicas son similares a esta: 192.0.2.235, mientras que las direcciones IPv6 son de este tipo: 2001:0db8:85a3:0000:0000:8a2e:0370:7334. El cambio en el formato y la funcionalidad en los dispositivos que usan direcciones IPv6 requiere varias consideraciones de implementación y configuración en su Skype para la instalación de Business Server. 

En este tema se incluyen las siguientes secciones:
  
- [Overview of IP address types](ipv6.md#over)
    
- [Technical requirements for IPv6](ipv6.md#tech)
    
- [Migration and coexistence considerations for IPv6](ipv6.md#migration)
    
Si determina que va a utilizar las direcciones IPv6, consulte el artículo de [tipos de direcciones IP configurar en Skype para la empresa](ip-address-types.md) .
  
## <a name="overview-of-ip-address-types"></a>Información general sobre los tipos de direcciones IP
<a name="over"> </a>

Dispone de tres opciones al configurar las direcciones IP en Skype para Business Server. Puede configurar Skype para Business Server admitir sólo IP versión 4 (IPv4), sólo IP versión 6 (IPv6), o una combinación de ambos (conocido como una pila dual). Cada tipo de configuración entraña varios aspectos que necesita tener en cuenta:
  
- **Solo IPv4** IPv6 se creó debido a que el mundo se está quedando sin las direcciones IPv4. En última instancia, IPv6 se admitirá totalmente en todo el mundo, pero en este momento, muchas compañías y dispositivos que es posible que necesite comunicarse con su empresa todavía no admiten IPv6 y es posible que no durante algún tiempo. Una configuración de sólo IPv4 le ayudará a asegurarse de que su Skype para la implementación de Business Server puede comunicarse con la mayoría de los dispositivos existente.
    
- **Solo IPv6** Por el contrario, una implementación completa de IPv6 excluirá la comunicación con muchos dispositivos existentes.
    
- **Pila dual** Pila dual es una red donde se habilitan las direcciones IPv4 e IPv6. Esta configuración se admite en Skype para Business Server debido a que en la mayoría de los casos, la transición de completo IPv4 a IPv6 de completo tardarán varios años.
    
En las secciones siguientes se describen la compatibilidad entre estas tres configuraciones para distintos Skype para las características de Business Server.
  
> [!NOTE]
> La configuración de tipo solo IPv6 en el cliente o el servidor solo se admite en entornos de laboratorio y con fines de validación, no se admite en implementaciones de producción. 
  
### <a name="client-registration"></a>Registro de clientes
<a name="client"> </a>

|**Red de extremo de cliente**|**Red del servidor**|
|:-----|:-----|
|IPv4  <br/> |IPv4  <br/> |
|IPv4  <br/> |Pila dual  <br/> |
|Pila dual  <br/> |IPv4  <br/> |
|Pila dual  <br/> |Pila dual  <br/> |
|Pila dual  <br/> |IPv6  <br/> |
|IPv6  <br/> |Pila dual  <br/> |
|IPv6  <br/> |IPv6  <br/> |
   
### <a name="peer-to-peer-client"></a>Cliente de punto a punto
<a name="peer"> </a>

Las comunicaciones de punto a punto incluyen audio, audio y vídeo, uso compartido de aplicaciones y transferencia de archivos. Después de que se hayan registrado con éxito ambos clientes, se admiten las combinaciones siguientes.
  
|**Extremo de cliente 1**|**Extremo de cliente 2**|
|:-----|:-----|
|IPv4  <br/> |IPv4  <br/> |
|IPv4  <br/> |Pila dual  <br/> |
|Pila dual  <br/> |Pila dual  <br/> |
|IPv6  <br/> |Pila dual  <br/> |
|IPv6  <br/> |IPv6  <br/> |
   
### <a name="conferencing"></a>Conferencia
<a name="conf"> </a>

Las conferencias incluyen audio y vídeo, uso compartido de aplicaciones y aplicaciones de colaboración de datos (pizarra y uso compartido de archivos).
  
|**Red de extremo de cliente**|**Red del servidor**|
|:-----|:-----|
|IPv4  <br/> |IPv4  <br/> |
|IPv4  <br/> |Pila dual  <br/> |
|Pila dual  <br/> |IPv4  <br/> |
|Pila dual  <br/> |Pila dual  <br/> |
|Pila dual  <br/> |IPv6  <br/> |
|IPv6  <br/> |Pila dual  <br/> |
|IPv6  <br/> |IPv6  <br/> |
   
### <a name="mediation-serverpstn"></a>Servidor de mediación/RTC
<a name="med"> </a>

Skype para Business Server no admite el desvío de medios para las llamadas de telefónica conmutada (RTC) de la red si el tráfico a través de una interfaz de IPv6. Si se requiere la omisión de medios, recomendamos que la puerta de enlace RTC se configure con IPv4. 
  
|**Interfaz principal 1**|**Interfaz RTC (en el servidor de mediación)**|**Configuración de la puerta de enlace RTC**|
|:-----|:-----|:-----|
|IPv4  <br/> |Pila dual  <br/> |IPv4  <br/> |
|Pila dual  <br/> |Pila dual  <br/> |IPv4  <br/> |
|Pila dual  <br/> |Pila dual  <br/> |IPv6  <br/> |
   
1. La interfaz principal es la interfaz que se comunica con el Skype para los componentes de Business Server.
  
### <a name="remote-user-peer-to-peer-communications"></a>Comunicaciones de punto a punto de usuarios remotos
<a name="remote"> </a>

Las comunicaciones de punto a punto con usuarios remotos incluyen mensajería instantánea, audio y vídeo, uso compartido de aplicaciones y transferencia de archivos.
  
|**Red de usuarios remotos**|**Servidor perimetral (perímetro externo)**|
|:-----|:-----|
|IPv4  <br/> |IPv4  <br/> |
|Pila dual  <br/> |IPv4  <br/> |
|Pila dual  <br/> |Pila dual  <br/> |
|IPv6  <br/> |Pila dual  <br/> |
|IPv6  <br/> |IPv6  <br/> |
   
### <a name="front-end-pool-and-edge-pool-configuration"></a>Configuración del grupo de servidores front-end y del grupo de servidores perimetrales
<a name="FE_pool"> </a>

En la siguiente tabla se muestra la matriz de compatibilidad entre el grupo de servidor Front-End y el grupo de servidores perimetrales interno.
  
**Matriz del grupo de servidores front-end y del grupo de servidores perimetrales (perímetro interno)**

||**Grupo de servidores perimetrales: IPv4** <br/> |**Grupo de servidores perimetrales: pila dual** <br/> |**Grupo de servidores perimetrales: IPv6** <br/> |
|:-----|:-----|:-----|:-----|
|**Grupo de servidores front-end: IPv4** <br/> |Sí   <br/> |Sí  <br/> |No  <br/> |
|**Grupo de servidores front-end: pila dual** <br/> |Sí   <br/> |Sí  <br/> |No  <br/> |
|**Grupo de servidores front-end: IPv6** <br/> |No  <br/> |Página de invitación a la reunión con números de teléfono de acceso telefónico predeterminados  <br/> |Sí\*  <br/> |
   
\*Utilice esta combinación únicamente en un entorno de laboratorio.
  
La tabla siguiente es una matriz de combinaciones admitidas de las interfaces perimetrales interna y externa.
  
**Matriz del grupo de servidores perimetrales (perímetro interno) y del grupo de servidores perimetrales (perímetro externo)**

||**Grupo de servidores perimetrales (perímetro externo): IPv4** <br/> |**Grupo de servidores perimetrales (perímetro externo): pila dual** <br/> |**Grupo de servidores perimetrales (perímetro externo): IPv6** <br/> |
|:-----|:-----|:-----|:-----|
|**Grupo de servidores perimetrales (perímetro interno): IPv4** <br/> |Sí  <br/> |Sí  <br/> |No  <br/> |
|**Grupo de servidores perimetrales (perímetro interno): pila dual** <br/> |No  <br/> |Sí  <br/> |No  <br/> |
|**Grupo de servidores perimetrales (perímetro interno): IPv6** <br/> |No  <br/> |Página de invitación a la reunión con números de teléfono de acceso telefónico predeterminados  <br/> |Sí\*  <br/> |
   
\*Utilice esta combinación únicamente en un entorno de laboratorio.
  
### <a name="advanced-enterprise-voice-support-for-ipv6"></a>Compatibilidad avanzada de Telefonía IP empresarial para IPv6
<a name="Ent_V"> </a>

Las implementaciones que incluyen el control de admisión de llamadas (CAC), Enhanced 9-1-1 (E9-1-1) o la omisión de medios se deben configurar como implementaciones de solo IPv4 o de pila dual. Los extremos que solo usen IPv6 no pueden usar ninguna de estas características.
  
> [!NOTE]
> En una implementación de pila dual, incluso si un Skype para cliente de Business Server se conecta a un Skype para Business Server mediante el uso de IPv6, Skype para Business Server hará un gran esfuerzo para asignar una dirección IPv4 adecuada para admitir E9-1-1. 
  
No se admite el servicio de información de ubicación con direcciones IPv6.
  
La mensajería unificada (MU) de Exchange no admite IPv6. Para la MU de Exchange, asegúrese de que la resolución de DNS no devuelve una dirección IPv6. El uso de IPv6 puede provocar un fallo cuando se envían las llamadas al correo de voz. 
  
### <a name="other-skype-for-business-server-feature-support-for-ipv6"></a>Otro Skype para compatibilidad con la característica de servidor de negocio para IPv6
<a name="Ent_V"> </a>

Además de las características y los componentes mencionados anteriormente, Skype para Business Server admite IPv6 para las siguientes características:
  
- **Chat persistente**
    
    Configurar IPv6 para Chat persistente mediante el generador de topología. Para obtener información detallada sobre la configuración de Chat persistente, consulte la documentación de implementación de servidor de Chat persistente.
    
- **Informes de Calidad de la experiencia (QoE) y registro detallado de llamadas (CDR)**
    
    Los informes de supervisión incluyen la dirección IP cuando se guarda en la base de datos del servidor de supervisión, tanto del tipo IPv4 como IPv6.
    
## <a name="technical-requirements-for-ipv6"></a>Requisitos técnicos para IPv6
<a name="tech"> </a>

Si planea configurar Skype para Business Server para IPv6, recuerde los siguientes requisitos:
  
- Para usar las direcciones IPv6 con Skype para Business Server, debe crear registros de (dominio DNS) para los registros que se deben detectar y resolver en una dirección IPv6 de sistema de nombres de dominio. El DNS de IPv6 usa registros AAAA de host (A cuádruple). Si usa IPv4 e IPv6 en la implementación, es mejor configurar y guardar los registros A de host para IPv4 y los registros AAAA de host para IPv6. Aun cuando pase completamente la implementación a IPv6, pueden ser necesarios registros de host DNS IPv4 para los usuarios externos que todavía usen IPv4.
    
    Puede implementar los registros de host DNS IPv6 antes de empezar a usar IPv6. Si el cliente o el servidor no usan IPv6, el registro no será referenciado. Las tecnologías de transición decidirán qué registro usar, sobre la base de las directivas y la configuración de la tecnología de transición.
    
- Cada dirección de IPv6 tiene un ámbito. Los tres ámbitos que se pueden usar direcciones IPv6 son direcciones globales de IPv6 (similares a las direcciones IPv4 públicas), IPv6 único las direcciones locales (similares a los intervalos de direcciones IPv4 privados) y las direcciones locales de vínculo IPv6 (similares a direcciones IP privadas automáticas en Windows Server para IPv4). Todos los servidores de un grupo necesitan tener direcciones IPv6 con el mismo ámbito. 
    
> [!IMPORTANT]
> IPv6 es un tema complejo y requiere una planeación cuidadosa con su equipo de red y su proveedor de Internet para ayudar a garantizar que las direcciones que va a asignar en el nivel del servidor de Windows y en el Skype para nivel Business Server funcionan según lo previsto. Vea los vínculos del final de este tema para conocer otros recursos sobre la planeación y el direccionamiento de IPv6. 
  
## <a name="migration-and-coexistence-considerations-for-ipv6"></a>Consideraciones sobre coexistencia y migración para IPv6
<a name="migration"> </a>

IP versión 6 (IPv6) no se admite en Lync Server 2010 u Office Communications Server. Para fines de las pruebas piloto, puede probar Lync Server 2010 y Skype para la coexistencia de pila dual Business Server. Se recomienda que todos los grupos de servidores para un determinado sitio central se actualizan a Skype para Business Server antes de habilitar IPv6 (red de doble pila) para cualquiera de los grupos de servidores. Si necesita configurar un grupo solo para IPv6, recomendamos configurar un grupo de servidores solo IPv6 en su entorno de prueba.
  
Se admiten los siguientes escenarios durante la migración y coexistencia:
  
- Skype para grupos de Business Server, Lync Server 2013 y Lync Server 2010 en el modo IPv4, coexisten con Skype para Business Server en modo de pila dual.
    
- Skype para profesionales de servidores en modo de solo IPv6, si el grupo de servidores solo IPv6 se encuentra aislado.
    
## <a name="see-also"></a>Vea también
<a name="migration"> </a>

[Configure IP address types in Skype for Business](ip-address-types.md)

[Arquitectura de direccionamiento de IP versión 6](https://tools.ietf.org/html/rfc4291)
  
[Formato de dirección de unidifusión Global IPv6](https://tools.ietf.org/html/rfc3587)
  
[Direcciones de unidifusión IPv6 Local único](https://tools.ietf.org/html/rfc4193)
