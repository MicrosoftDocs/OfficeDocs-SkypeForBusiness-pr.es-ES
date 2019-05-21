---
title: Planificar IPv6 en Skype Empresarial
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 01f77196-38f4-4292-9480-2e2fbd57eabe
description: 'Resumen: implemente IPv6 antes de instalar Skype empresarial Server.'
ms.openlocfilehash: e4af5403ce416332ec7c75ca26522038fd9c42df
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34297046"
---
# <a name="plan-for-ipv6-in-skype-for-business"></a>Planificar IPv6 en Skype Empresarial
 
**Resumen:** Implemente IPv6 antes de instalar Skype empresarial Server.
  
Skype empresarial Server incluye compatibilidad con direcciones IP versión 6 (IPv6), además de compatibilidad continuada con direcciones IP versión 4 (IPv4). 

Las direcciones IPv4 son direcciones de 32 bits que permiten a los equipos comunicarse a través de Internet. Debido al creciente número de dispositivos en todo el mundo, las direcciones IPv4 disponibles se agotan. Por este motivo, muchos dispositivos nuevos se mueven a usar direcciones IPv6. Las direcciones IPv6 cumplen la misma función que las direcciones IPv4 (con algunas características adicionales), pero en lugar de usar solo 32 bits, usan 128 bits. Esto no solo proporciona un nuevo conjunto de direcciones, sino también una cantidad mucho más elevada de estas. 

Las direcciones IPv4 típicas son similares a esta: 192.0.2.235, mientras que las direcciones IPv6 son de este tipo: 2001:0db8:85a3:0000:0000:8a2e:0370:7334. El cambio en el formato y la funcionalidad de los dispositivos que usan direcciones IPv6 requiere varias consideraciones de implementación y configuración en la instalación de Skype empresarial Server. 

En este tema se incluyen las siguientes secciones:
  
- [Overview of IP address types](ipv6.md#over)
    
- [Technical requirements for IPv6](ipv6.md#tech)
    
- [Migration and coexistence considerations for IPv6](ipv6.md#migration)
    
Si determina que va a usar direcciones IPv6, consulte el artículo [configurar tipos de direcciones IP en Skype empresarial](ip-address-types.md) .
  
## <a name="overview-of-ip-address-types"></a>Información general sobre los tipos de direcciones IP
<a name="over"> </a>

Tiene tres opciones al configurar las direcciones IP en Skype empresarial Server. Puede configurar Skype empresarial Server para que admita solo IP versión 4 (IPv4), solo IP versión 6 (IPv6) o una combinación de ambos (conocido como una pila doble). Cada tipo de configuración entraña varios aspectos que necesita tener en cuenta:
  
- **Solo IPv4** Se creó IPv6 porque el mundo se está quedando sin direcciones IPv4. En última instancia, IPv6 será totalmente compatible en todo el mundo, pero en este momento, muchas de las compañías y dispositivos que su empresa podría necesitar para comunicarse aún no son compatibles con IPv6, y es posible que no lo hagan durante algún tiempo. Una configuración de solo IPv4 le ayudará a asegurarse de que su implementación de Skype empresarial Server pueda comunicarse con la mayoría de los dispositivos existentes.
    
- **Solo IPv6** A la inversa, una implementación de IPv6 completa excluirá la comunicación con muchos dispositivos existentes.
    
- **Pila dual** Dual Stack es una red en la que se habilitan las direcciones IPv4 e IPv6. Esta configuración es compatible con Skype empresarial Server porque, en la mayoría de los casos, la transición de IPv4 completa a completada por IPv6 lleva varios años.
    
En las siguientes secciones se describe la compatibilidad entre estas tres configuraciones para las distintas características de Skype empresarial Server.
  
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

Skype empresarial Server no admite la omisión de medios para llamadas de red telefónica conmutada (RTC) si el tráfico se realiza a través de una interfaz de IPv6. Si se requiere la omisión de medios, recomendamos que la puerta de enlace RTC se configure con IPv4. 
  
|**Interfaz principal 1**|**Interfaz RTC (en el servidor de mediación)**|**Configuración de la puerta de enlace RTC**|
|:-----|:-----|:-----|
|IPv4  <br/> |Pila dual  <br/> |IPv4  <br/> |
|Pila dual  <br/> |Pila dual  <br/> |IPv4  <br/> |
|Pila dual  <br/> |Pila dual  <br/> |IPv6  <br/> |
   
1. La interfaz principal es la interfaz que se comunica con los componentes de Skype empresarial Server.
  
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

En la tabla siguiente se muestra la matriz de soporte técnico entre el grupo de servidores front-end y el grupo de servidores perimetrales internos.
  
**Matriz del grupo de servidores front-end y del grupo de servidores perimetrales (perímetro interno)**

||**Grupo de servidores perimetrales: IPv4** <br/> |**Grupo de servidores perimetrales: pila dual** <br/> |**Grupo de servidores perimetrales: IPv6** <br/> |
|:-----|:-----|:-----|:-----|
|**Grupo de servidores front-end: IPv4** <br/> |Sí   <br/> |Sí  <br/> |No  <br/> |
|**Grupo de servidores front-end: pila dual** <br/> |Sí   <br/> |Sí  <br/> |No  <br/> |
|**Grupo de servidores front-end: IPv6** <br/> |No  <br/> |Página de invitación a la reunión con números de teléfono de acceso telefónico predeterminados  <br/> |Sí\*  <br/> |
   
\*Use esta combinación solo en un entorno de laboratorio.
  
La tabla siguiente es una matriz de combinaciones admitidas de las interfaces perimetrales interna y externa.
  
**Matriz del grupo de servidores perimetrales (perímetro interno) y del grupo de servidores perimetrales (perímetro externo)**

||**Grupo de servidores perimetrales (perímetro externo): IPv4** <br/> |**Grupo de servidores perimetrales (perímetro externo): pila dual** <br/> |**Grupo de servidores perimetrales (perímetro externo): IPv6** <br/> |
|:-----|:-----|:-----|:-----|
|**Grupo de servidores perimetrales (perímetro interno): IPv4** <br/> |Sí  <br/> |Sí  <br/> |No  <br/> |
|**Grupo de servidores perimetrales (perímetro interno): pila dual** <br/> |No  <br/> |Sí  <br/> |No  <br/> |
|**Grupo de servidores perimetrales (perímetro interno): IPv6** <br/> |No  <br/> |Página de invitación a la reunión con números de teléfono de acceso telefónico predeterminados  <br/> |Sí\*  <br/> |
   
\*Use esta combinación solo en un entorno de laboratorio.
  
### <a name="advanced-enterprise-voice-support-for-ipv6"></a>Compatibilidad avanzada de Telefonía IP empresarial para IPv6
<a name="Ent_V"> </a>

Las implementaciones que incluyen el control de admisión de llamadas (CAC), Enhanced 9-1-1 (E9-1-1) o la omisión de medios se deben configurar como implementaciones de solo IPv4 o de pila dual. Los extremos que solo usen IPv6 no pueden usar ninguna de estas características.
  
> [!NOTE]
> En una implementación de doble pila, incluso si un cliente de Skype empresarial Server se conecta a un servidor de Skype empresarial mediante IPv6, Skype empresarial Server hará un esfuerzo óptimo para asignar una dirección IPv4 adecuada para admitir E9-1-1. 
  
No se admite el servicio de información de ubicación con direcciones IPv6.
  
La mensajería unificada (MU) de Exchange no admite IPv6. Para la MU de Exchange, asegúrese de que la resolución de DNS no devuelve una dirección IPv6. El uso de IPv6 puede provocar un fallo cuando se envían las llamadas al correo de voz. 
  
### <a name="other-skype-for-business-server-feature-support-for-ipv6"></a>Otra compatibilidad de características de Skype empresarial Server para IPv6
<a name="Ent_V"> </a>

Además de las características y componentes mencionados anteriormente, Skype empresarial Server admite IPv6 para las siguientes características:
  
- **Chat persistente**
    
    Para configurar IPv6 para la conversación persistente, use el generador de topología. Para obtener más información sobre cómo configurar una conversación persistente, consulte la documentación de implementación del servidor de chat persistente.
    
- **Informes de Calidad de la experiencia (QoE) y registro detallado de llamadas (CDR)**
    
    Los informes de supervisión incluyen la dirección IP cuando se guarda en la base de datos del servidor de supervisión, tanto del tipo IPv4 como IPv6.
    
## <a name="technical-requirements-for-ipv6"></a>Requisitos técnicos para IPv6
<a name="tech"> </a>

Si tiene previsto configurar Skype empresarial Server para IPv6, tenga en cuenta los siguientes requisitos:
  
- Para usar direcciones IPv6 con Skype empresarial Server, necesita crear registros del sistema de nombres de dominio (DNS) para los registros que se deben detectar y resolver en una dirección IPv6. El DNS de IPv6 usa registros AAAA de host (A cuádruple). Si usa IPv4 e IPv6 en la implementación, es mejor configurar y guardar los registros A de host para IPv4 y los registros AAAA de host para IPv6. Aun cuando pase completamente la implementación a IPv6, pueden ser necesarios registros de host DNS IPv4 para los usuarios externos que todavía usen IPv4.
    
    Puede implementar los registros de host DNS IPv6 antes de empezar a usar IPv6. Si el cliente o el servidor no usan IPv6, el registro no será referenciado. Las tecnologías de transición decidirán qué registro usar, sobre la base de las directivas y la configuración de la tecnología de transición.
    
- Cada dirección de IPv6 tiene un ámbito. Los tres ámbitos que puede usar para el direccionamiento IPv6 son direcciones globales de IPv6 (similares a las direcciones IPv4 públicas), direcciones locales IPv6 únicas (similares a los intervalos de direcciones IPv4 privadas) y direcciones locales del vínculo IPv6 (similares a las direcciones IP privadas automáticas de Windows Server para IPv4). Todos los servidores de un grupo necesitan tener direcciones IPv6 con el mismo ámbito. 
    
> [!IMPORTANT]
> IPv6 es un tema complejo y requiere un cuidadoso planeamiento con el equipo de redes y el proveedor de Internet para garantizar que las direcciones que asigne en el nivel de servidor de Windows y en el nivel de servidor de Skype empresarial funcionen de la manera esperada. Vea los vínculos del final de este tema para conocer otros recursos sobre la planeación y el direccionamiento de IPv6. 
  
## <a name="migration-and-coexistence-considerations-for-ipv6"></a>Consideraciones sobre coexistencia y migración para IPv6
<a name="migration"> </a>

La versión 6 de IP (IPv6) no es compatible con Lync Server 2010 o con Office Communications Server. Para fines piloto, puede probar Lync Server 2010 y la coexistencia de la pila doble de Skype empresarial Server. Le recomendamos que todos los grupos de un sitio central determinado se actualicen a Skype empresarial Server antes de habilitar IPv6 (red de doble pila) para cualquiera de los grupos. Si necesita configurar un grupo solo para IPv6, recomendamos configurar un grupo de servidores solo IPv6 en su entorno de prueba.
  
Se admiten los siguientes escenarios durante la migración y coexistencia:
  
- Los grupos de servidores de Skype empresarial, Lync Server 2013 y Lync Server 2010 en modo IPv4, coexistencia con Skype empresarial Server en modo Dual Stack.
    
- Grupo de servidores de Skype empresarial en modo de solo IPv6, si el grupo de solo IPv6 está en silos.
    
## <a name="see-also"></a>Vea también
<a name="migration"> </a>

[Configure IP address types in Skype for Business](ip-address-types.md)

[Arquitectura de direccionamiento de IP versión 6](https://tools.ietf.org/html/rfc4291)
  
[Formato de dirección global de unidifusión IPv6](https://tools.ietf.org/html/rfc3587)
  
[Direcciones de unidifusión IPv6 locales únicas](https://tools.ietf.org/html/rfc4193)
