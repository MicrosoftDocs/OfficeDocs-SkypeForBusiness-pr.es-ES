---
title: Planear IPv6 en Skype Empresarial
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
ms.assetid: 01f77196-38f4-4292-9480-2e2fbd57eabe
description: 'Resumen: implemente IPv6 antes de instalar Skype Empresarial Server.'
ms.openlocfilehash: 02753ad0e2fee00e548dd2f709dc451373283cae2fe0fe2e30dbae62e77f12f1
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54289678"
---
# <a name="plan-for-ipv6-in-skype-for-business"></a>Planear IPv6 en Skype Empresarial
 
**Resumen:** Implemente IPv6 antes de instalar Skype Empresarial Server.
  
Skype Empresarial Server incluye compatibilidad con direcciones IP de la versión 6 (IPv6), junto con compatibilidad continua con direcciones IP de la versión 4 (IPv4). 

Las direcciones IPv4 son direcciones de 32 bits que permiten a los equipos comunicarse a través de Internet. Debido al número creciente de dispositivos en todo el mundo, las direcciones IPv4 disponibles se han quedo sin funcionar. Debido a esto, muchos dispositivos nuevos se están moviendo al uso de direcciones IPv6. Las direcciones IPv6 realizan la misma función que las direcciones IPv4 (con algunas funciones adicionales), pero en lugar de usar solo 32 bits, usan 128 bits. Esto no solo proporciona un nuevo conjunto de direcciones, sino también un número mucho más elevado de ellas. 

Las direcciones IPv4 típicas son similares a esta: 192.0.2.235, mientras que las direcciones IPv6 son de este tipo: 2001:0db8:85a3:0000:0000:8a2e:0370:7334. El cambio en el formato y la funcionalidad de los dispositivos que usan direcciones IPv6 requiere varias consideraciones de implementación y configuración en su Skype Empresarial Server instalación. 

En este tema se incluyen las secciones siguientes:
  
- [Información general sobre los tipos de direcciones IP](ipv6.md#over)
    
- [Requisitos técnicos para IPv6](ipv6.md#tech)
    
- [Consideraciones de migración y coexistencia para IPv6](ipv6.md#migration)
    
Si determina que va a usar direcciones IPv6, consulte el artículo Configurar tipos de direcciones [IP en Skype Empresarial.](ip-address-types.md)
  
## <a name="overview-of-ip-address-types"></a>Información general sobre los tipos de direcciones IP
<a name="over"> </a>

Tiene tres opciones al configurar direcciones IP en Skype Empresarial Server. Puede configurar Skype Empresarial Server para admitir solo IP versión 4 (IPv4), solo ip versión 6 (IPv6) o una combinación de ambos (conocida como pila dual). Cada tipo de configuración entraña varios aspectos que debe tener en cuenta:
  
- **Solo IPv4** IPv6 se creó porque el mundo se está quedando sin direcciones IPv4. En última instancia, IPv6 será totalmente compatible en todo el mundo, pero en este momento, muchas empresas y dispositivos con los que su empresa podría tener que comunicarse aún no admiten IPv6 y es posible que no durante algún tiempo. Una configuración de solo IPv4 ayudará a garantizar que la implementación Skype Empresarial Server se pueda comunicar con la mayoría de los dispositivos existentes.
    
- **Solo IPv6** Por el contrario, una implementación completa de IPv6 excluirá la comunicación con muchos dispositivos existentes.
    
- **Pila dual** La pila dual es una red donde las direcciones IPv4 e IPv6 están habilitadas. Esta configuración se admite en Skype Empresarial Server porque en la mayoría de los casos la transición de full-IPv4 a full-IPv6 llevará varios años.
    
En las secciones siguientes se describe la compatibilidad entre estas tres configuraciones para varias Skype Empresarial Server características.
  
> [!NOTE]
> La configuración de tipo solo IPv6 en el cliente o el servidor solo se admite en entornos de ensayo y con fines de validación, no se admite en implementaciones de producción. 
  
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
   
### <a name="conferencing"></a>Conferencias
<a name="conf"> </a>

Las conferencias incluyen audio/vídeo, uso compartido de aplicaciones y aplicaciones de colaboración de datos, como pizarras y uso compartido de archivos.
  
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

Skype Empresarial Server no admite la omisión de medios para llamadas de red telefónica conmutada (RTC) si el tráfico se realiza a través de una interfaz IPv6. Si se requiere la omisión de medios, se recomienda que la puerta de enlace RTC se configure con IPv4. 
  
|**Interfaz principal 1**|**Interfaz RTC (en el servidor de mediación)**|**Configuración de la puerta de enlace RTC**|
|:-----|:-----|:-----|
|IPv4  <br/> |Pila dual  <br/> |IPv4  <br/> |
|Pila dual  <br/> |Pila dual  <br/> |IPv4  <br/> |
|Pila dual  <br/> |Pila dual  <br/> |IPv6  <br/> |
   
1. La interfaz principal es la interfaz que se comunica con los Skype Empresarial Server componentes.
  
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

En la tabla siguiente se muestra la matriz de compatibilidad entre el grupo de servidores front-end y el grupo de servidores perimetrales interno.
  
**Matriz del grupo de servidores front-end y del grupo de servidores perimetrales (perímetro interno)**

||**Grupo de servidores perimetrales: IPv4** <br/> |**Grupo de servidores perimetrales: pila dual** <br/> |**Grupo de servidores perimetrales: IPv6** <br/> |
|:-----|:-----|:-----|:-----|
|**Grupo de servidores front-end: IPv4** <br/> |Sí  <br/> |Sí  <br/> |No  <br/> |
|**Grupo de servidores front-end: pila dual** <br/> |Sí  <br/> |Sí  <br/> |No  <br/> |
|**Grupo de servidores front-end: IPv6** <br/> |No  <br/> |No  <br/> |Sí\*  <br/> |
   
\* Use esta combinación solo en un entorno de laboratorio.
  
La tabla siguiente es una matriz de combinaciones admitidas de las interfaces perimetrales interna y externa.
  
**Matriz del grupo de servidores perimetrales (perímetro interno) y del grupo de servidores perimetrales (perímetro externo)**

||**Grupo de servidores perimetrales (perímetro externo): IPv4** <br/> |**Grupo de servidores perimetrales (perímetro externo): pila dual** <br/> |**Grupo de servidores perimetrales (perímetro externo): IPv6** <br/> |
|:-----|:-----|:-----|:-----|
|**Grupo de servidores perimetrales (perímetro interno): IPv4** <br/> |Sí  <br/> |Sí  <br/> |No  <br/> |
|**Grupo de servidores perimetrales (perímetro interno): pila dual** <br/> |No  <br/> |Sí  <br/> |No  <br/> |
|**Grupo de servidores perimetrales (perímetro interno): IPv6** <br/> |No  <br/> |No  <br/> |Sí\*  <br/> |
   
\* Use esta combinación solo en un entorno de laboratorio.
  
### <a name="advanced-enterprise-voice-support-for-ipv6"></a>Compatibilidad avanzada de Enterprise Voice para IPv6
<a name="Ent_V"> </a>

Las implementaciones que incluyen el control de admisión de llamadas (CAC), Enhanced 9-1-1 (E9-1-1) o la omisión de medios se deben configurar como implementaciones de solo IPv4 o de pila dual. Los puntos de conexión que solo usan IPv6 no pueden usar ninguna de estas características.
  
> [!NOTE]
> En una implementación de doble pila, incluso si un cliente de Skype Empresarial Server se conecta a un Skype Empresarial Server mediante IPv6, Skype Empresarial Server hará el mejor esfuerzo para asignar una dirección IPv4 adecuada para admitir E9-1-1. 
  
No se admite el servicio de información de ubicación con direcciones IPv6.
  
La mensajería unificada (MU) de Exchange no admite IPv6. Para la MU de Exchange, asegúrese de que la resolución de DNS no devuelve una dirección IPv6. El uso de IPv6 puede provocar un fallo cuando se envían las llamadas al correo de voz. 
  
### <a name="other-skype-for-business-server-feature-support-for-ipv6"></a>Otras Skype Empresarial Server compatibilidad con características para IPv6
<a name="Ent_V"> </a>

Además de las características y componentes mencionados anteriormente, Skype Empresarial Server admite IPv6 para las siguientes características:
  
- **Chat persistente**
    
    Puede configurar IPv6 para chat persistente mediante el Generador de topologías. Para obtener más información sobre cómo configurar el chat persistente, consulte la documentación sobre implementación del servidor de chat persistente.
    
- **Informes de Calidad de la experiencia (QoE) y registro de detalles de llamadas (CDR)**
    
    Los informes de supervisión incluyen la dirección IP cuando se guarda en la base de datos del servidor de supervisión, tanto del tipo IPv4 como IPv6.
    
## <a name="technical-requirements-for-ipv6"></a>Requisitos técnicos para IPv6
<a name="tech"> </a>

Si tiene previsto configurar Skype Empresarial Server para IPv6, tenga en cuenta los siguientes requisitos:
  
- Para usar direcciones IPv6 con Skype Empresarial Server, debe crear registros del sistema de nombres de dominio (DNS) para los registros que deben detectarse y resolverse en una dirección IPv6. El DNS de IPv6 usa registros AAAA de host (A cuádruple). Si usa IPv4 e IPv6 en la implementación, es mejor configurar y guardar los registros A de host para IPv4 y los registros AAAA de host para IPv6. Aun cuando pase completamente la implementación a IPv6, pueden ser necesarios registros de host DNS IPv4 para los usuarios externos que todavía usen IPv4.
    
    Puede implementar los registros de host DNS IPv6 antes de empezar a usar IPv6. Si el cliente o el servidor no usan IPv6, el registro no será referenciado. Las tecnologías de transición tomarán la decisión sobre qué registro usar, sobre la base de las directivas y la configuración de la tecnología de transición.
    
- Cada dirección de IPv6 tiene un ámbito. Los tres ámbitos que puede usar para el direccionamiento IPv6 son las direcciones globales IPv6 (similares a las direcciones IPv4 públicas), las direcciones locales únicas de IPv6 (similares a los intervalos de direcciones IPv4 privados) y las direcciones IPv6 locales de vínculo (similares a las direcciones IP privadas automáticas en Windows Server para IPv4). Todos los servidores de un grupo deben tener direcciones IPv6 con el mismo ámbito. 
    
> [!IMPORTANT]
> IPv6 es un tema complejo y requiere una planeación cuidadosa con su equipo de redes y su proveedor de Internet para ayudar a garantizar que las direcciones que asigne en el nivel de servidor de Windows y en el nivel de Skype Empresarial Server funcionen según lo esperado. Consulte los vínculos al final de este tema para ver más recursos sobre la planeación y el direccionamiento de IPv6. 
  
## <a name="migration-and-coexistence-considerations-for-ipv6"></a>Consideraciones de migración y coexistencia para IPv6
<a name="migration"> </a>

La versión 6 de IP (IPv6) no es compatible con Lync Server 2010 o Office Communications Server. Para fines piloto, puede probar Lync Server 2010 y Skype Empresarial Server coexistencia de doble pila. Se recomienda que todos los grupos de servidores de un sitio central determinado se actualicen a Skype Empresarial Server antes de habilitar IPv6 (red de doble pila) para cualquiera de los grupos de servidores. Si necesita configurar un grupo solo para IPv6, se recomienda configurar un grupo de servidores solo IPv6 en su entorno de prueba.
  
Se admiten los siguientes escenarios durante la migración y coexistencia:
  
- Skype Empresarial Server, lync server 2013 y grupos de servidores de Lync Server 2010 en modo IPv4, coexistiendo con Skype Empresarial Server en modo de pila dual.
    
- Skype Empresarial Server en modo de solo IPv6, si el grupo de servidores de solo IPv6 está siloed.
    
## <a name="see-also"></a>Consulte también
<a name="migration"> </a>

[Configurar tipos de direcciones IP en Skype Empresarial](ip-address-types.md)

[Arquitectura de direcciones IP versión 6](https://tools.ietf.org/html/rfc4291)
  
[Formato global de direcciones de unidifusión IPv6](https://tools.ietf.org/html/rfc3587)
  
[Direcciones unicast locales únicas de IPv6](https://tools.ietf.org/html/rfc4193)
