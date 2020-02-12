---
title: Planificación de DNS de Advanced Edge Server para Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
audience: ITPro
ms.topic: conceptual
manager: serdars
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: f3a5895f-f64f-44eb-9a5e-8d606ac1fc38
description: 'Resumen: Revise los escenarios de las opciones de implementación de Skype empresarial Server. Si desea un único servidor o prefiere un grupo de servidores con DNS o HLB, este tema debería ser de ayuda.'
ms.openlocfilehash: c1a5cc793cde46c1334d88dfcbd430922f0b7c32
ms.sourcegitcommit: 1a08ec9069332e19135312d35fc6a6c3247ce2d2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/11/2020
ms.locfileid: "41887649"
---
# <a name="advanced-edge-server-dns-planning-for-skype-for-business-server"></a>Planificación de DNS de Advanced Edge Server para Skype empresarial Server
 
**Resumen:** Revise los escenarios de las opciones de implementación de Skype empresarial Server. Si desea un único servidor o prefiere un grupo de servidores con DNS o HLB, este tema debería ser de ayuda.
  
Cuando se trata de planear el sistema de nombres de dominio (DNS) de Skype empresarial Server, hay muchos factores que pueden ser de su decisión. Si la estructura del dominio de su organización ya está en el lugar correcto, puede ser una cuestión de revisar la manera en la que va a continuar. Comenzaremos con los temas que se encuentran a continuación:
  
- [Walkthrough of Skype for Business clients locating services](../../plan-your-deployment/network-requirements/advanced-edge-server-dns.md#WalkthroughOfSkype)
    
- [Split-brain DNS](../../plan-your-deployment/network-requirements/advanced-edge-server-dns.md#SplitBrainDNS)
    
- [Automatic configuration without split-brain DNS](../../plan-your-deployment/network-requirements/advanced-edge-server-dns.md#NoSplitBrainDNS)
    
- [DNS disaster recovery](../../plan-your-deployment/network-requirements/advanced-edge-server-dns.md#DNSDR)
    
- [DNS load balancing](../../plan-your-deployment/network-requirements/advanced-edge-server-dns.md#DNSLB)
    
## <a name="walkthrough-of-skype-for-business-clients-locating-services"></a>Walkthrough of Skype for Business clients locating services
<a name="WalkthroughOfSkype"> </a>

Los clientes de Skype empresarial son similares a versiones anteriores de clientes de Lync en cuanto a la forma en que encuentran y tienen acceso a los servicios de Skype empresarial Server. Esta sección contiene información sobre el proceso de ubicación del servidor.
  
1. lyncdiscoverinternal. \<dominio\>
    
     *Es un registro de host A para el servicio Detección automática en los servicios web internos.* 
    
2. lyncdiscover. \<dominio\>
    
     *Es un registro de host A para el servicio Detección automática en los servicios web externos.* 
    
3. _sipinternaltls. _tcp. \<dominio\>
    
     *Es un registro SRV para las conexiones TLS internas.* 
    
4. _sip. _tls. \<dominio\>
    
     *Es un registro SRV para las conexiones TLS externas.* 
    
5. sipinternal. \<dominio\>
    
     *Este es un registro de host para el grupo de servidores front-end o director, que solo se pueda resolver en la red interna.* 
    
6. SIP. \<dominio\>
    
     *Este es un registro de host para el grupo de servidores front-end o director, que solo se pueda resolver en la red interna.* 
    
7. sipexternal. \<dominio\>
    
     *Este es un registro de host para el servicio perimetral de acceso, cuando el cliente es externo.* 
    
El servicio Detección automática es siempre el favorito, ya que es el método preferido para la ubicación del servicio y los demás son métodos reserva.
  
> [!NOTE]
> Al crear registros SRV, es importante recordar que tienen que señalar a un registro A de DNS (y AAAA si está usando el direccionamiento IPv6) en el mismo dominio en el que se ha creado el registro de DNS SRV. Por ejemplo, si el registro SRV está en contoso.com, el registro A (y AAAA) al que señala no puede encontrarse en fabrikam.com. 
  
Si está dispuesto a hacerlo, puede configurar su dispositivo móvil para la detección manual de servicios. Si es lo que quiere hacer, cada usuario tiene que configurar los parámetros del dispositivo móvil con las URL internas y externas completas del servicio Detección automática, incluyendo el protocolo y la ruta de acceso, de la manera siguiente:
  
- Para acceso externo: https://\<ExtPoolFQDN\>/Autodiscover/autodiscoverservice.SVC/root
    
- Para acceso interno: https://\<IntPoolFQDN\>/AutoDiscover/AutoDiscover.SVC/root
    
Le recomendamos usar la detección automática en contraposición con la detección manual, pero si está solucionando problemas o realizando alguna prueba, la configuración manual puede ser muy útil.
  
## <a name="split-brain-dns"></a>DNS de horizonte dividido
<a name="SplitBrainDNS"> </a>

Se trata de una configuración de DNS en la que tiene dos zonas de DNS con el mismo espacio de nombres. La primera zona DNS trata solicitudes internas, mientras que la segunda zona DNS trata las solicitudes externas.
  
¿Por qué haría esto una compañía? Puede que tengan un requisito de usar el mismo espacio de nombres internamente y externamente, pero, por supuesto esto llevará a muchos SRV de DNS y registros A únicos en una zona u otra, y donde hay duplicación, las direcciones IP asociadas con estos registros serían únicas.
  
Esto presenta algunos desafíos. Lo más importante es que el servidor DNS dividido **no es compatible** con la movilidad. Esto se debe a los registros DNS LyncDiscover y LyncDiscoverInternal (LyncDiscover tiene que definirse en el servidor DNS externo, mientras que LyncDiscoverInternal tiene que definirse en el servidor DNS interno).
  
Aquí se enumeran los registros DNS para las zonas interna y externa, pero puede encontrar ejemplos detallados en la sección requisitos ambientales del servidor perimetral.
  
### <a name="internal-dns"></a>DNS interno

- Contiene una zona DNS llamada (por ejemplo) contoso.com, para la que es relevante.
    
- Esta contoso.com interna contiene:
    
  - DNS A y AAAA (si usa direcciones IPv6) registros para el grupo de servidores front-end, grupo de directores o nombre del grupo de directores, y todos los servidores internos que ejecutan Skype empresarial Server en la red de su organización.
    
  - DNS A y AAAA (si usa direcciones IPv6) para su interfaz interna perimetral para cada servidor perimetral de Skype empresarial Server en la red perimetral.
    
  - DNS A y AAAA (si usa direcciones IPv6) para la interfaz interna de cada servidor proxy inverso en la red perimetral (que es **opcional** para la administración de un proxy inverso).
    
  - DNS A y AAAA (si usa direccionamiento IPv6) y los registros SRV para la configuración automática del cliente de Skype empresarial Server interna (que es **opcional** ).
    
  - DNS A y AAAA (si está usando direccionamiento IPv6) o registros CNAME para la detección automática de servicios Web de Skype empresarial Server (que es **opcional** ).
    
- Todas las interfaces de borde interno de Skype empresarial Server en la red perimetral usan esta zona DNS interna para resolver las consultas a contoso.com.
    
- Todos los servidores que ejecutan Skype empresarial Server y los clientes que ejecutan Skype empresarial Server en la red corporativa, señale a servidores DNS internos para resolver las consultas a contoso.com o que usen el archivo host en cada servidor perimetral y la lista a y AAAA (si está usando IPv6) registros para el servidor del próximo salto (específicamente para el director o el grupo de directores VIP, la VIP de la agrupación de front-end o el servidor Standard Edition).
    
### <a name="external-dns"></a>DNS externo

- Contiene una zona DNS llamada (por ejemplo) contoso.com, para la que es relevante.
    
- Esta contoso.com externa contiene:
    
  - DNS A y AAAA (si está usando direccionamiento IPv6) o registros CNAME, para el descubrimiento automático de servicios Web de Skype empresarial Server. Es para usar con movilidad.
    
  - DNS A y AAAA (si está usando direccionamiento IPv6) y los registros SRV para la interfaz externa perimetral de cada servidor perimetral de Skype empresarial Server o de la VIP de carga equilibrada (HLB) en la red perimetral.
    
  - DNS A y AAAA (si usa direccionamiento IPv6) y los registros SRV para la interfaz externa del servidor proxy inverso o (VIP para un grupo de servidores proxy inversos), en la red perimetral.
    
  - DNS A y AAAA (si usa direccionamiento IPv6) y los registros SRV para la configuración automática del cliente de Skype empresarial Server ( **opcional** ).
    
## <a name="automatic-configuration-without-split-brain-dns"></a>Configuración automática sin DNS de horizonte dividido
<a name="NoSplitBrainDNS"> </a>

Si no usa DNS de horizonte dividido, la configuración automática interna de clientes que ejecutan Skype empresarial no funcionará a menos que esté usando una de las soluciones alternativas que hemos aquí. ¿Por qué no? Debido a que Skype empresarial Server requiere que el URI SIP del usuario coincida con el dominio del grupo de servidores front-end designado para la configuración automática. Esto no ha cambiado con respecto a versiones anteriores de Lync Server.
  
Por lo tanto, si tiene dos dominios SIP en uso, necesitará estos registros SRV de DNS:
  
- _sipinternaltls._tcp.contoso.com. 86400 IN SRV 0 0 5061 pool01.contoso.com
    
     *Si un usuario inicia sesión como bob@contoso.com, este registro funcionará con la configuración automática, ya que el dominio SIP del usuario coincide con el dominio del grupo de servidores front-end (contoso.com).* 
    
- _sipinternaltls._tcp.fabrikam.com. 86400 IN SRV 0 0 5061 pool01.fabrikam.com
    
     *Si un usuario inicia sesión como alice@fabrikam.com, este registro funcionará para la configuración automática del segundo dominio, de nuevo porque el dominio SIP coincide con el grupo de servidores front-end de ese dominio.* 
    
Para llevar el ejemplo más allá, esto no funcionaría:
  
- _sipinternaltls._tcp.litwareinc.com. 86400 IN SRV 0 0 5061 pool01.fabrikam.com
    
     *Un usuario iniciando sesión como tim@litwareinc.com no funcionará para la configuración automática, porque su dominio SIP (litwareinc.com) no coincide con el dominio del grupo (fabrikam.com).* 
    
Ahora que lo sabemos todo, si necesita requisitos automáticos para sus clientes de Skype empresarial sin el DNS dividido, tiene estas opciones:
  
- **Objetos de directiva de grupo**
    
    Puede usar objetos de directiva de grupo (GPO) para rellenar los valores de servidor correctos.
    
    > [!NOTE]
    > Esta opción no habilita la configuración automática, pero automatiza la configuración manual. Si se usa este enfoque, los registros SRV asociados con la configuración automática no son obligatorios. 
  
- **Correspondencia de zona interna**
    
    Tendrá que crear una zona en el DNS interno que coincida con su zona DNS externa (por ejemplo, contoso.com) y, a continuación, crear los registros de DNS a (y AAAA si usa direcciones IPv6) que corresponden al grupo de servidores de Skype empresarial usado para la característica automática configuración.
    
    Por ejemplo, si tiene un usuario alojado en pool01.contoso.net, pero inicia sesión en Skype empresarial como bob@contoso.com, cree una zona DNS interna llamada contoso.com y, dentro de ella, debe crear un registro DNS A (y AAAA si se está usando la dirección IPv6).
    
- **Zona interna de punto de anclaje**
    
    Si crear una zona entera en el DNS interno no es una opción, puede crear zonas de punto de anclaje (dedicadas) que se correspondan con los registros SRV necesarios para la configuración automática y rellenar esas zonas con dnscmd.exe. Dnscmd.exe es obligatorio porque la interfaz de usuario de DNS no admite la creación de zonas de punto de anclaje.
    
    Por ejemplo, si su dominio SIP es contoso.com y tiene un grupo de servidores front-end denominado pool01 que contiene dos servidores front-end, necesitará las siguientes zonas de punto de ancla y registros A en su DNS interno:
    
  ```console
  dnscmd . /zoneadd _sipinternaltls._tcp.contoso.com. /dsprimary
  dnscmd . /recordadd _sipinternaltls._tcp.contoso.com. @ SRV 0 0 5061 pool01.contoso.com.
  dnscmd . /zoneadd pool01.contoso.com. /dsprimary
  dnscmd . /recordadd pool01.contoso.com. @ A 192.168.10.90
  dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
  dnscmd . /recordadd pool01.contoso.com. @ A 192.168.10.91 
  dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
  ```

    Puede que tenga un segundo dominio SIP en su entorno. En ese caso, necesitará los siguientes registros A y zonas de punto de anclaje en el DNS interno:
    
  ```console
  dnscmd . /zoneadd _sipinternaltls._tcp.fabrikam.com. /dsprimary
  dnscmd . /recordadd _sipinternaltls._tcp.fabrikam.com. @ SRV 0 0 5061 pool01.fabrikam.com.
  dnscmd . /zoneadd pool01.fabrikam.com. /dsprimary
  dnscmd . /recordadd pool01.fabrikam.com. @ A 192.168.10.90
  dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
  dnscmd . /recordadd pool01.fabrikam.com. @ A 192.168.10.91
  dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
  ```

> [!NOTE]
> Verá que el FQDN del grupo de servidores front-end aparece dos veces, pero con dos direcciones IP diferentes. Esto se debe a que se usa el equilibrio de carga de DNS. Si se usa HLB, solo habrá una sola entrada de grupo de servidores front-end. 
  
> [!NOTE]
> Además, los valores FQDN del grupo de servidores front-end cambian entre los ejemplos contoso.com y fabrikam.com, pero las direcciones IP siguen siendo las mismas. Esto se debe a que los usuarios que inician sesión desde cualquiera de los dominios SIP usarán el mismo grupo de servidores front-end para la configuración automática. 
  
## <a name="dns-disaster-recovery"></a>Recuperación ante desastres de DNS
<a name="DNSDR"> </a>

Para configurar DNS de redirigir el tráfico web de Skype empresarial Server a los sitios de recuperación ante desastres (DR) y de conmutación por error, debe usar un proveedor de DNS que admita GeoDNS. Puede configurar los registros DNS para que admitan la recuperación ante desastres, de modo que las características que usan los servicios web continúen incluso si se produce un grupo de servidores front-end completo. Esta característica de DR es compatible con la detección automática, las reuniones y las direcciones URL sencillas de acceso telefónico local.
  
Puede definir y configurar registros A de host de DNS adicionales (AAAA si usa IPv6) para la resolución interna y externa de servicios web en su proveedor de GeoDNS. La siguiente información asume grupos emparejados, dispersos geográficamente y que el GeoDNS que admite su proveedor **tanto** tiene DNS round robin **como** está configurado para usar Pool1 como principal y conmutar por error a Pool2 en caso de cualquier pérdida de comunicación o error de alimentación.
  
Todos los registros DNS en esta tabla son ejemplos.
  
|**Registro de GeoDNS**|**Registros del grupo**|**CNAME records**|**Configuración de DNS (seleccione una opción)**|
|:-----|:-----|:-----|:-----|
|Meet-int.geolb.contoso.com  <br/> |Pool1InternalWebFQDN.contoso.com  <br/> Pool2InternalWebFQDN.contoso.com  <br/> |Meet.contoso.com a Meet-int.geolb.contoso.com  <br/>   <br/> |Round robin entre grupos  <br/> **O bien** <br/> Usa el primario, se conecta al secundario en caso de error  <br/> |
|Meet-ext.geolb.contoso.com  <br/> |Pool1ExternalWebFQDN.contoso.com  <br/> Pool2ExternalWebFQDN.contoso.com  <br/> |Meet.contoso.com a Meet-ext.geolb.contoso.com  <br/>   <br/> |Round robin entre grupos  <br/> **O bien** <br/> Usa el primario, se conecta al secundario en caso de error  <br/> |
|Dialin-int.geolb.contoso.com  <br/> |Pool1InternalWebFQDN.contoso.com  <br/> Pool2InternalWebFQDN.contoso.com  <br/> |Meet.contoso.com a Meet-int.geolb.contoso.com   <br/>  <br/> |Round robin entre grupos  <br/> **O bien** <br/> Usa el primario, se conecta al secundario en caso de error  <br/> |
|Dialin-ext.geolb.contoso.com  <br/> |Pool1ExternalWebFQDN.contoso.com  <br/> Pool2ExternalWebFQDN.contoso.com  <br/> |Meet.contoso.com a Meet-ext.geolb.contoso.com  <br/>  <br/> |Round robin entre grupos  <br/> **O bien** <br/> Usa el primario, se conecta al secundario en caso de error  <br/> |
|Lyncdiscoverint-int.geolb.contoso.com  <br/> |Pool1InternalWebFQDN.contoso.com  <br/> Pool2InternalWebFQDN.contoso.com  <br/> |Meet.contoso.com a Meet-int.geolb.contoso.com   <br/>   <br/> |Round robin entre grupos  <br/> **O bien** <br/> Usa el primario, se conecta al secundario en caso de error  <br/> |
|Lyncdiscover-ext.geolb.contoso.com  <br/> |Pool1ExternalWebFQDN.contoso.com  <br/> Pool2ExternalWebFQDN.contoso.com  <br/> |Meet.contoso.com a Meet-ext.geolb.contoso.com  <br/>  <br/> |Round robin entre grupos  <br/> **O bien** <br/> Usa el primario, se conecta al secundario en caso de error  <br/> |
|Scheduler-int.geolb.contoso.com  <br/> |Pool1InternalWebFQDN.contoso.com  <br/> Pool2InternalWebFQDN.contoso.com  <br/> |Meet.contoso.com a Meet-int.geolb.contoso.com   <br/>  <br/> |Round robin entre grupos  <br/> **O bien** <br/> Usa el primario, se conecta al secundario en caso de error  <br/> |
|Scheduler-ext.geolb.contoso.com  <br/> |Pool1ExternalWebFQDN.contoso.com  <br/> Pool2ExternalWebFQDN.contoso.com  <br/> |Meet.contoso.com a Meet-ext.geolb.contoso.com   <br/>  <br/> |Round robin entre grupos  <br/> **O bien** <br/> Usa el primario, se conecta al secundario en caso de error  <br/> |
   
## <a name="dns-load-balancing"></a>Equilibrio de carga de DNS
<a name="DNSLB"> </a>

El equilibrio de carga de DNS suele implementarse en el nivel de la aplicación. La aplicación (por ejemplo, un cliente con Skype empresarial) intenta conectarse a un servidor de un grupo conectándose a una de las direcciones IP devueltas por el DNS a y AAAA (si se usa el direccionamiento IPv6) consulta de registro para el FQDN del grupo.
  
Por ejemplo, si hay tres servidores front-end en un grupo denominado pool01.contoso.com, ocurrirá lo siguiente:
  
- Los clientes que ejecutan DNS de consultas de Skype empresarial para pool01.contoso.com. La consulta devuelve tres direcciones IP y las copia en caché tal como se muestra a continuación (en algún orden):
    
   |||
   |:-----|:-----|
   |pool01.contoso.com  <br/> |192.168.10.90  <br/> |
   |pool01.contoso.com  <br/> |192.168.10.91  <br/> |
   |pool01.contoso.com  <br/> |192.168.10.92  <br/> |
   
- El cliente intenta establecer una conexión TCP con una de las direcciones IP. Si se genera un error, lo intentará con la siguiente dirección IP copiada en caché de esa lista.
    
- Si la conexión TCP se establece correctamente, el cliente negocia con el TLS para conectarse con el registrador principal en pool01.contoso.com.
    
- Si el cliente prueba todas las entradas almacenadas en caché sin una conexión correcta, el usuario recibirá una notificación que le notificará que no hay servidores con Skype empresarial Server disponibles en este momento.
    
> [!NOTE]
> El equilibrio de carga basado en DNS es distinto al round robin de DNS (DNS RR), que normalmente hace referencia al equilibrio de carga usando el DNS para darle un orden distinto de direcciones IP para los servidores del grupo de servidores. Por lo general, DNS RR habilita la distribución de carga, pero no le permitirá habilitar la conmutación por error. Por ejemplo, si la conexión con la dirección IP devuelta por la consulta de DNS A (o AAAA en un escenario IPv6) provoca un error, esa conexión dará error. Esto hace que el DNS RR sea menos fiable que el equilibrio de carga basado en DNS. Todavía puede usar el DNS RR en combinación con el equilibrio de carga basado en DNS si lo necesita. 
  
Usa el equilibrio de carga de DNS para:
  
- Equilibrio de carga SIP de servidor a servidor a los servidores perimetrales.
    
- Equilibrar la carga de aplicaciones de servicios de aplicaciones de comunicaciones unificadas (UCAS) como Operador automático de conferencia, Grupo de respuesta y Estacionamiento de llamadas.
    
- Impedir el establecimiento de nuevas conexiones con aplicaciones UCAS (también conocido como purga).
    
- Equilibre la carga de todo el tráfico de cliente a servidor entre los clientes y los servidores perimetrales.
    
No puede usar el equilibrio de carga de DNS para:
  
- Tráfico web de cliente a servidor a los servidores front-end o a un director.
    
Para avanzar un poco más en profundidad sobre cómo se selecciona un registro SRV de DNS cuando una consulta devuelva los registros DNS de mutiple, el servicio perimetral de acceso siempre selecciona el registro con la prioridad numérica más baja y, si se necesita un separador de empates, el peso numérico más alto. Esto es coherente con la [documentación de Internet Engineering Task Force](https://www.ietf.org/rfc/rfc2782.txt).
  
Por tanto, por ejemplo, si el primer registro SRV de DNS tiene un peso de 20 y una prioridad de 40 y el segundo registro SRV de DNS tiene un peso de 10 y una prioridad de 50, se elegirá el primer registro porque tiene la prioridad más baja, 40. La prioridad siempre va primero y es el host que un cliente elegirá primero. ¿Qué ocurre si hay dos destinos con la misma prioridad? 
  
En ese caso, el peso entra en consideración. Un mayor peso tendrá una probabilidad alta, en esta circunstancia, de ser seleccionado. Los administradores de DNS deben usar peso 0 cuando no hay ninguna selección de servidor. En la presencia de registros con peso mayor que 0, los registros con peso 0 tienen una probabilidad muy pequeña de ser seleccionados.
  
Por lo tanto, ¿qué sucede si se devuelven varios registros SRV de DNS con la misma prioridad y el mismo peso? En esta situación, el servicio perimetral de acceso elegirá primero el registro SRV que recibió del servidor DNS.
  

