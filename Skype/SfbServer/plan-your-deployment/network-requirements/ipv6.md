---
title: Planificar IPv6 en Skype Empresarial
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/21/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 01f77196-38f4-4292-9480-2e2fbd57eabe
description: 'Resumen: Implementar IPv6 antes de instalar Skype para Business Server 2015.'
ms.openlocfilehash: e91b0a3afabf8088d6fed2f21124fb17a4f7e94f
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="plan-for-ipv6-in-skype-for-business"></a>Planificar IPv6 en Skype Empresarial
 
**Resumen:** Implementar IPv6 antes de instalar Skype para Business Server 2015.
  
Skype para Business Server incluye soporte para IP versión 6 (IPv6) direcciones, junto con el continuo apoyo de IP versión 4 (IPv4) direcciones. 

Las direcciones IPv4 son direcciones de 32 bits que permiten a los equipos comunicarse a través de Internet. Debido al número creciente de dispositivos en todo el mundo, las direcciones IPv4 disponibles se agoten. Por este motivo, muchos nuevos dispositivos están cambiando a mediante direcciones IPv6. Las direcciones IPv6 cumplen la misma función que las direcciones IPv4 (con algunas características adicionales), pero en lugar de usar solo 32 bits, usan 128 bits. Esto no solo proporciona un nuevo conjunto de direcciones, sino también una cantidad mucho más elevada de estas. 

Las direcciones IPv4 típicas son similares a esta: 192.0.2.235, mientras que las direcciones IPv6 son de este tipo: 2001:0db8:85a3:0000:0000:8a2e:0370:7334. El cambio en el formato y la funcionalidad en los dispositivos que utilizan direcciones IPv6 requiere varias consideraciones de implementación y configuración en su Skype para instalación del servidor de empresa. 

En este tema se incluyen las siguientes secciones:
  
- [Overview of IP address types](ipv6.md#over)
    
- [Technical requirements for IPv6](ipv6.md#tech)
    
- [Migration and coexistence considerations for IPv6](ipv6.md#migration)
    
Si decide que va a utilizar direcciones IPv6, consulte el artículo de [los tipos de direcciones de IP configurar en Skype para el negocio](ip-address-types.md) .
  
## <a name="overview-of-ip-address-types"></a>Información general sobre los tipos de direcciones IP
<a name="over"> </a>

Tiene tres opciones al configurar direcciones IP en Skype para Business Server. Puede configurar Skype para Business Server admitir sólo IP versión 4 (IPv4), sólo IP versión 6 (IPv6), o una combinación de ambos (conocido como pila doble). Cada tipo de configuración entraña varios aspectos que necesita tener en cuenta:
  
- **Sólo IPv4** IPv6 se creó porque el mundo se está quedando sin direcciones IPv4. En última instancia, IPv6 contará con soporte completo en todo el mundo, pero en este momento, muchas compañías y dispositivos que necesite comunicarse con su empresa todavía no admiten IPv6 y pueden no durante algún tiempo. Una configuración de sólo IPv4 le ayudará a asegurarse de que su Skype para implementación de Business Server puede comunicarse con la mayoría de los dispositivos existente.
    
- **Sólo IPv6** Por el contrario, una implementación de IPv6 completa excluirá comunicación con muchos dispositivos existentes.
    
- **Pila doble** Pila dual es una red donde se habilitan las direcciones IPv4 e IPv6. Esta configuración se admite en Skype para Business Server porque en la mayoría de los casos, la transición de completo IPv4 a IPv6 completo tardará varios años.
    
Las siguientes secciones describen la compatibilidad entre estas tres configuraciones para varios Skype para las características de Business Server.
  
> [!NOTE]
> La configuración de tipo solo IPv6 en el cliente o el servidor solo se admite en entornos de laboratorio y con fines de validación, no se admite en implementaciones de producción. 
  
### <a name="client-registration"></a>Registro de clientes
<a name="client"> </a>

|**Red de extremo de cliente**|**Red de servidor**|
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
  
|**Red de extremo de cliente**|**Red de servidor**|
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

Skype para Business Server no admite la omisión de medios para llamadas de telefónica pública conmutada (PSTN) de red si el tráfico es a través de una interfaz de IPv6. Si se requiere la omisión de medios, recomendamos que la puerta de enlace RTC se configure con IPv4. 
  
|**Interfaz principal 1**|**Interfaz PSTN (en el servidor de mediación)**|**Configuración de puerta de enlace PSTN**|
|:-----|:-----|:-----|
|IPv4  <br/> |Pila dual  <br/> |IPv4  <br/> |
|Pila dual  <br/> |Pila dual  <br/> |IPv4  <br/> |
|Pila dual  <br/> |Pila dual  <br/> |IPv6  <br/> |
   
1. La interfaz principal es la interfaz que se comunica con el Skype para los componentes de Business Server.
  
### <a name="remote-user-peer-to-peer-communications"></a>Comunicaciones de punto a punto de usuarios remotos
<a name="remote"> </a>

Las comunicaciones de punto a punto con usuarios remotos incluyen mensajería instantánea, audio y vídeo, uso compartido de aplicaciones y transferencia de archivos.
  
|**Red de usuarios remotos**|**Servidor perimetral (contorno externo)**|
|:-----|:-----|
|IPv4  <br/> |IPv4  <br/> |
|Pila dual  <br/> |IPv4  <br/> |
|Pila dual  <br/> |Pila dual  <br/> |
|IPv6  <br/> |Pila dual  <br/> |
|IPv6  <br/> |IPv6  <br/> |
   
### <a name="front-end-pool-and-edge-pool-configuration"></a>Configuración del grupo de servidores front-end y del grupo de servidores perimetrales
<a name="FE_pool"> </a>

La siguiente tabla muestra la matriz de soporte entre el grupo de servidor Front-End y el servidor perimetral interno.
  
**Grupo de servidores Front-End y matriz de borde Pool (contorno interno)**

|||||
|:-----|:-----|:-----|:-----|
||**Grupo de servidores perimetrales: IPv4** <br/> |**Grupo de servidores perimetrales: pila dual** <br/> |**Grupo de servidores perimetrales: IPv6** <br/> |
|**Grupo de servidores front-end: IPv4** <br/> |Sí  <br/> |Sí  <br/> |No  <br/> |
|**Grupo de servidores front-end: pila dual** <br/> |Sí  <br/> |Sí  <br/> |No  <br/> |
|**Grupo de servidores front-end: IPv6** <br/> |No  <br/> |No  <br/> |Sí\*  <br/> |
   
\*Utilice esta combinación sólo en un entorno de laboratorio.
  
La tabla siguiente es una matriz de combinaciones admitidas de las interfaces perimetrales interna y externa.
  
**Piscina de borde (contorno interno) y el borde de la piscina Matrix (contorno externo)**

|||||
|:-----|:-----|:-----|:-----|
||**Grupo de servidores perimetrales (perímetro externo): IPv4** <br/> |**Grupo de servidores perimetrales (perímetro externo): pila dual** <br/> |**Grupo de servidores perimetrales (perímetro externo): IPv6** <br/> |
|**Grupo de servidores perimetrales (perímetro interno): IPv4** <br/> |Sí  <br/> |Sí  <br/> |No  <br/> |
|**Grupo de servidores perimetrales (perímetro interno): pila dual** <br/> |No  <br/> |Sí  <br/> |No  <br/> |
|**Grupo de servidores perimetrales (perímetro interno): IPv6** <br/> |No  <br/> |No  <br/> |Sí\*  <br/> |
   
\*Utilice esta combinación sólo en un entorno de laboratorio.
  
### <a name="advanced-enterprise-voice-support-for-ipv6"></a>Compatibilidad avanzada de Telefonía IP empresarial para IPv6
<a name="Ent_V"> </a>

Las implementaciones que incluyen el control de admisión de llamadas (CAC), Enhanced 9-1-1 (E9-1-1) o la omisión de medios se deben configurar como implementaciones de solo IPv4 o de pila dual. Los extremos que solo usen IPv6 no pueden usar ninguna de estas características.
  
> [!NOTE]
> En una implementación de pila doble, incluso si un Skype para cliente Business Server se conecta a un Skype para Business Server mediante el uso de IPv6, Skype para Business Server hará un mayor esfuerzo para asignar una dirección IPv4 para admitir E9-1-1. 
  
Servicio de información de ubicación con direcciones IPv6 no es compatible.
  
La mensajería unificada (MU) de Exchange no admite IPv6. Para la MU de Exchange, asegúrese de que la resolución de DNS no devuelve una dirección IPv6. El uso de IPv6 puede provocar un fallo cuando se envían las llamadas al correo de voz. 
  
### <a name="other-skype-for-business-server-feature-support-for-ipv6"></a>Otro Skype para la característica de servidor de Business Support para IPv6
<a name="Ent_V"> </a>

Además de las características y los componentes mencionados anteriormente, Skype para Business Server es compatible con IPv6 para las siguientes características:
  
- **Chat persistente**
    
    Configurar IPv6 para Chat persistente mediante el generador de topología. Para obtener más información acerca de cómo configurar la charla persistente, consulte la documentación de implementación de servidor de charla persistente.
    
- **Informes de Calidad de la experiencia (QoE) y registro detallado de llamadas (CDR)**
    
    Los informes de supervisión incluyen la dirección IP cuando se guarda en la base de datos del servidor de supervisión, tanto del tipo IPv4 como IPv6.
    
## <a name="technical-requirements-for-ipv6"></a>Requisitos técnicos para IPv6
<a name="tech"> </a>

Si piensa configurar Skype para Business Server para IPv6, tenga presente los siguientes requisitos:
  
- Para utilizar direcciones IPv6 con Skype para Business Server, debe crear el sistema de nombres de dominio (DNS) para los registros que deben ser detectados y resuelto en una dirección IPv6. El DNS de IPv6 usa registros AAAA de host (A cuádruple). Si usa IPv4 e IPv6 en la implementación, es mejor configurar y guardar los registros A de host para IPv4 y los registros AAAA de host para IPv6. Aun cuando pase completamente la implementación a IPv6, pueden ser necesarios registros de host DNS IPv4 para los usuarios externos que todavía usen IPv4.
    
    Puede implementar los registros de host DNS IPv6 antes de empezar a usar IPv6. Si el cliente o el servidor no usan IPv6, el registro no será referenciado. Las tecnologías de transición decidirán qué registro usar, sobre la base de las directivas y la configuración de la tecnología de transición.
    
- Cada dirección de IPv6 tiene un ámbito. Los tres ámbitos que puede utilizar para direcciones IPv6 son direcciones globales de IPv6 (similares a las direcciones IPv4 públicas), único local las direcciones IPv6 (similares a los intervalos de direcciones IPv4 privados) y las direcciones locales de vínculo IPv6 (similares a direcciones IP privadas automáticas en Windows Server para IPv4). Todos los servidores de un grupo necesitan tener direcciones IPv6 con el mismo ámbito. 
    
> [!IMPORTANT]
> IPv6 es un tema complejo y requiere un planeamiento cuidadoso con su equipo de la red y su proveedor de Internet para ayudar a asegurarse de que las direcciones que se asignan al nivel del servidor de Windows y en el Skype para nivel Business Server funcionan como se esperaba. Vea los vínculos del final de este tema para conocer otros recursos sobre la planeación y el direccionamiento de IPv6. 
  
## <a name="migration-and-coexistence-considerations-for-ipv6"></a>Consideraciones sobre coexistencia y migración para IPv6
<a name="migration"> </a>

IP versión 6 (IPv6) no es compatible con Lync Server 2010 o Office Communications Server. Para propósitos de prueba piloto, puede probar Lync Server 2010 y Skype para la coexistencia de doble pila Business Server. Se recomienda que todos los grupos de un determinado sitio central se actualizan a Skype para Business Server antes de habilitar IPv6 (red de doble pila) para cualquiera de los grupos. Si necesita configurar un grupo solo para IPv6, recomendamos configurar un grupo de servidores solo IPv6 en su entorno de prueba.
  
Se admiten los siguientes escenarios durante la migración y coexistencia:
  
- Skype para pools de Lync Server 2010, Lync Server 2013 y Business Server en el modo IPv4, que coexiste con Skype para Business Server en modo de doble pila.
    
- Skype para el grupo de Business Server en modo de sólo IPv6, si el grupo sólo IPv6 en silos.
    
## <a name="see-also"></a>Vea también
<a name="migration"> </a>

#### 

[Configurar tipos de direcciones IP de Skype para empresas](ip-address-types.md)
#### 

[Arquitectura de direccionamiento IP versión 6](https://tools.ietf.org/html/rfc4291)
  
[Formato de dirección de unidifusión Global IPv6](https://tools.ietf.org/html/rfc3587)
  
[Direcciones de unidifusión de IPv6 Local único](https://tools.ietf.org/html/rfc4193)

