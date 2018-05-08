---
title: Avanzada planeación DNS del servidor perimetral de Skype para Business Server 2015
ms.author: heidip
author: microsoftheidi
ms.date: 2/15/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: f3a5895f-f64f-44eb-9a5e-8d606ac1fc38
description: 'Resumen: Revise los escenarios de Skype para opciones de implementación empresarial Server 2015. Si desea que un servidor único o prefiere un grupo de servidores con DNS o HLB, en este tema debe ayudar a.'
ms.openlocfilehash: 575bbacfa58f52197d50b335942909dc8748a965
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="advanced-edge-server-dns-planning-for-skype-for-business-server-2015"></a>Avanzada planeación DNS del servidor perimetral de Skype para Business Server 2015
 
**Resumen:** revise escenarios para las opciones de implementación de Skype Empresarial Server 2015. Tanto si desea un único servidor como si prefiere un grupo de servidores con DNS o HLB, este tema puede ayudarle.
  
En cuanto a la planeación de sistema de nombres de dominio (DNS) de Skype para Business Server 2015, hay una gran cantidad de factores que pueden reproducir en su decisión. Si la estructura del dominio de su organización ya está en el lugar correcto, puede ser una cuestión de revisar la manera en la que va a continuar. Comenzaremos con los temas que se encuentran a continuación:
  
- [Walkthrough of Skype for Business clients locating services](../../plan-your-deployment/network-requirements/advanced-edge-server-dns.md#WalkthroughOfSkype)
    
- [Split-brain DNS](../../plan-your-deployment/network-requirements/advanced-edge-server-dns.md#SplitBrainDNS)
    
- [Automatic configuration without split-brain DNS](../../plan-your-deployment/network-requirements/advanced-edge-server-dns.md#NoSplitBrainDNS)
    
- [DNS disaster recovery](../../plan-your-deployment/network-requirements/advanced-edge-server-dns.md#DNSDR)
    
- [DNS load balancing](../../plan-your-deployment/network-requirements/advanced-edge-server-dns.md#DNSLB)
    
## <a name="walkthrough-of-skype-for-business-clients-locating-services"></a>Walkthrough of Skype for Business clients locating services
<a name="WalkthroughOfSkype"> </a>

Skype para clientes empresariales son similares a las versiones anteriores de clientes de Lync en cómo buscar y obtener acceso a servicios de Skype para Business Server 2015. Esta sección contiene información sobre el proceso de ubicación del servidor.
  
1. lyncdiscoverinternal. \<dominio\>
    
     *Es un registro de host A para el servicio Detección automática en los servicios web internos.* 
    
2. lyncdiscover. \<dominio\>
    
     *Es un registro de host A para el servicio Detección automática en los servicios web externos.* 
    
3. _sipinternaltls._tcp. \<dominio\>
    
     *Es un registro SRV para las conexiones TLS internas.* 
    
4. _sip._tls. \<dominio\>
    
     *Es un registro SRV para las conexiones TLS externas.* 
    
5. sipinternal. \<dominio\>
    
     *Este es un registro de host a para el grupo de servidores Front-End o Director, puede resolver sólo en la red interna.* 
    
6. SIP. \<dominio\>
    
     *Este es un registro de host a para el grupo de servidores Front-End o Director, puede resolver sólo en la red interna.* 
    
7. sipexternal. \<dominio\>
    
     *Esto es un registro host para el servicio de servidor perimetral de acceso, cuando el cliente es externo.* 
    
El servicio Detección automática es siempre el favorito, ya que es el método preferido para la ubicación del servicio y los demás son métodos reserva.
  
> [!NOTE]
> Al crear registros SRV, es importante recordar que tienen que señalar a un registro A de DNS (y AAAA si está usando el direccionamiento IPv6) en el mismo dominio en el que se ha creado el registro de DNS SRV. Por ejemplo, si el registro SRV está en contoso.com, el registro A (y AAAA) al que señala no puede encontrarse en fabrikam.com. 
  
Si está dispuesto a hacerlo, puede configurar su dispositivo móvil para la detección manual de servicios. Si es lo que quiere hacer, cada usuario tiene que configurar los parámetros del dispositivo móvil con las URL internas y externas completas del servicio Detección automática, incluyendo el protocolo y la ruta de acceso, de la manera siguiente:
  
- Para el acceso externo: https://\<ExtPoolFQDN\>/Autodiscover/autodiscoverservice.svc/Root
    
- Para el acceso interno: https://\<IntPoolFQDN\>/AutoDiscover/AutoDiscover.svc/Root
    
Le recomendamos usar la detección automática en contraposición con la detección manual, pero si está solucionando problemas o realizando alguna prueba, la configuración manual puede ser muy útil.
  
## <a name="split-brain-dns"></a>DNS de horizonte dividido
<a name="SplitBrainDNS"> </a>

Se trata de una configuración de DNS en la que tiene dos zonas de DNS con el mismo espacio de nombres. La primera zona DNS trata solicitudes internas, mientras que la segunda zona DNS trata las solicitudes externas.
  
¿Por qué haría esto una compañía? Puede que tengan un requisito de usar el mismo espacio de nombres internamente y externamente, pero, por supuesto esto llevará a muchos SRV de DNS y registros A únicos en una zona u otra, y donde hay duplicación, las direcciones IP asociadas con estos registros serían únicas.
  
Esto presenta algunos desafíos. El más importante es que DNS de horizonte dividido **no se admite** para la movilidad. Esto se debe a los registros DNS LyncDiscover y LyncDiscoverInternal (LyncDiscover tiene que definirse en el servidor DNS externo, mientras que LyncDiscoverInternal tiene que definirse en el servidor DNS interno).
  
Aquí enumeramos los registros DNS para las zonas internas y externas, pero puede encontrar ejemplos detallados en la sección de requisitos de entorno de servidor perimetral.
  
### <a name="internal-dns"></a>DNS interno

- Contiene una zona DNS llamada (por ejemplo) contoso.com, para la que es relevante.
    
- Esta contoso.com interna contiene:
    
  - Registros DNS A y AAAA (si está usando direccionamiento IPv6) para el grupo de servidores Front-End, grupo de directores o nombre de grupo de servidores de Director y todos los servidores internos de Skype para Business Server 2015 en la red de su organización.
    
  - Registros de DNS A y AAAA (si está usando direccionamiento IPv6) para la interfaz perimetral interna para cada Skype para servidor perimetral de Business Server 2015 en la red perimetral.
    
  - Registros DNS A y AAAA (si está usando direccionamiento IPv6) para la interfaz interna de cada servidor proxy inverso en la red perimetral (que es **opcional** para la administración de un proxy inverso).
    
  - Registros DNS A y AAAA (si está usando direccionamiento IPv6) y SRV para Skype interno para la configuración automática de cliente de Business Server 2015 (que es **opcional** ).
    
  - DNS A y AAAA (si está usando direccionamiento IPv6) o los registros CNAME para la detección automática de Skype para Business Server 2015 Web Services (que es **opcional** ).
    
- Todos los su Skype para Business Server 2015 interfaces internas de borde en la red perimetral use esta zona DNS interna para la resolución de consultas a contoso.com.
    
- Todos los servidores que ejecutan Skype para Business Server 2015 y los clientes que ejecutan Skype para Business Server 2015 en la red corporativa, elija a los servidores DNS internos para la resolución de consultas a contoso.com o utilizan el archivo de Host en cada servidor perimetral y de lista A y AAAA si ( está usando direccionamiento IPv6) registros para el servidor del próximo salto (específicamente para el Director o la VIP del Director del grupo, Front End VIP de grupo de servidores o servidor Standard Edition).
    
### <a name="external-dns"></a>DNS externo

- Contiene una zona DNS llamada (por ejemplo) contoso.com, para la que es relevante.
    
- Esta contoso.com externa contiene:
    
  - DNS A y AAAA (si está usando direccionamiento IPv6) o CNAME de registros, para la detección automática de Skype para los servicios web de Business Server 2015. Es para usar con movilidad.
    
  - Registros SRV para la interfaz perimetral externa de cada Skype para servidor perimetral de Business Server 2015 o carga de hardware y A DNS y AAAA (si está usando direccionamiento IPv6) habían equilibrada a VIP (HLB) en la red perimetral.
    
  - Registros SRV y A y AAAA (si está usando direccionamiento IPv6) de DNS para la interfaz externa del servidor proxy inverso o (VIP para un grupo de servidores de proxy inverso), en la red perimetral.
    
  - Registros DNS A y AAAA (si está usando direccionamiento IPv6) y SRV para Skype para la configuración automática de cliente de Business Server 2015 ( **opcional** ).
    
## <a name="automatic-configuration-without-split-brain-dns"></a>Configuración automática sin DNS de horizonte dividido
<a name="NoSplitBrainDNS"> </a>

Si no utiliza DNS de horizonte dividido, la configuración automática interna de los clientes que ejecutan Skype para la empresa no funcionará a menos que se está utilizando una de las soluciones alternativas que tenemos aquí. ¿Por qué no? Debido a que Skype para Business Server 2015 requiere URI de SIP del usuario para que coincida con el dominio del grupo de servidores Front-End designado para la configuración automática. Esto no ha cambiado desde las versiones anteriores de Lync Server.
  
Por lo tanto, si tiene dos dominios SIP en uso, necesitará estos registros SRV de DNS:
  
- _sipinternaltls._tcp.contoso.com. 86400 IN SRV 0 0 5061 pool01.contoso.com
    
     *Si un usuario inicia sesión como bob@contoso.com, este registro funcionaría para la configuración automática, como dominio SIP del usuario coincide con el dominio del grupo de servidores Front-End (contoso.com).* 
    
- _sipinternaltls._tcp.fabrikam.com. 86400 IN SRV 0 0 5061 pool01.fabrikam.com
    
     *Si un usuario inicia sesión como alice@fabrikam.com, este registro funcionaría para la configuración automática del segundo dominio, vuelva a debido a que el dominio SIP coincide con el grupo de servidores Front-End para ese dominio.* 
    
Para llevar el ejemplo más allá, esto no funcionaría:
  
- _sipinternaltls._tcp.litwareinc.com. 86400 IN SRV 0 0 5061 pool01.fabrikam.com
    
     *Un usuario iniciando sesión como tim@litwareinc.com no funcionará para la configuración automática, porque su dominio SIP (litwareinc.com) no coincide con el dominio del grupo (fabrikam.com).* 
    
Por lo que ahora que sabemos todos los, si necesita requisito automática para su Skype para clientes empresariales sin DNS de horizonte dividido, tiene estas opciones:
  
- **Objetos de directiva de grupo**
    
    Puede usar objetos de directiva de grupo (GPO) para rellenar los valores de servidor correctos.
    
    > [!NOTE]
    > Esta opción no habilita la configuración automática, pero automatiza la configuración manual. Si se usa este enfoque, los registros SRV asociados con la configuración automática no son obligatorios. 
  
- **Correspondencia de zona interna**
    
    Para crear una zona en el DNS interno que coincida con su zona DNS externa (por ejemplo, contoso.com) y, a continuación, crear A DNS (y AAAA si está usando direccionamiento IPv6), necesitará los registros que corresponden a la Skype para grupo de negocio Server 2015 utilizado para automático configuración.
    
    Por ejemplo, si tiene un usuario alojado en pool01.contoso.net, pero signos en Skype para profesionales como bob@contoso.com, crear una zona DNS interna llamada contoso.com y dentro de él que necesita para crear un A DNS (y AAAA si direccionamiento de IPv6 se usa) registro para pool01.contoso.com.
    
- **Zona interna de punto de anclaje**
    
    Si crear una zona entera en el DNS interno no es una opción, puede crear zonas de punto de anclaje (dedicadas) que se correspondan con los registros SRV necesarios para la configuración automática y rellenar esas zonas con dnscmd.exe. Dnscmd.exe es obligatorio porque la interfaz de usuario de DNS no admite la creación de zonas de punto de anclaje.
    
    Por ejemplo, si su dominio SIP es contoso.com, y tiene un grupo de servidores Front-End denominado grupo01 que contiene dos servidores Front-End, necesitará las siguientes zonas designadas y los registros en el DNS interno:
    
  ```
  dnscmd . /zoneadd _sipinternaltls._tcp.contoso.com. /dsprimary
  dnscmd . /recordadd _sipinternaltls._tcp.contoso.com. @ SRV 0 0 5061 pool01.contoso.com.
  dnscmd . /zoneadd pool01.contoso.com. /dsprimary
  dnscmd . /recordadd pool01.contoso.com. @ A 192.168.10.90
  dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
  dnscmd . /recordadd pool01.contoso.com. @ A 192.168.10.91 
  dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
  ```

    Puede que tenga un segundo dominio SIP en su entorno. En ese caso, necesitará los siguientes registros A y zonas de punto de anclaje en el DNS interno:
    
  ```
  dnscmd . /zoneadd _sipinternaltls._tcp.fabrikam.com. /dsprimary
  dnscmd . /recordadd _sipinternaltls._tcp.fabrikam.com. @ SRV 0 0 5061 pool01.fabrikam.com.
  dnscmd . /zoneadd pool01.fabrikam.com. /dsprimary
  dnscmd . /recordadd pool01.fabrikam.com. @ A 192.168.10.90
  dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
  dnscmd . /recordadd pool01.fabrikam.com. @ A 192.168.10.91
  dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
  ```

> [!NOTE]
> Verá el grupo de servidores Front-End que FQDN aparece dos veces, pero con dos direcciones IP diferentes. Esto se debe a que se usa el equilibrio de carga de DNS. Si se utiliza HLB, sólo habrá una única entrada de grupo de servidores Front-End. 
  
> [!NOTE]
> Además, los valores FQDN del grupo de servidores Front-End cambian entre los ejemplos de contoso.com y fabrikam.com, pero las direcciones IP siguen siendo los mismos. Esto es debido a que los usuarios que se va a iniciar sesión desde cualquiera de los dominios SIP van a usar el mismo grupo de servidores Front-End para la configuración automática. 
  
## <a name="dns-disaster-recovery"></a>Recuperación ante desastres de DNS
<a name="DNSDR"> </a>

Para configurar DNS para redirigir Skype para el tráfico web de Business Server 2015 para la recuperación ante desastres (recuperación ante desastres) y los sitios de conmutación por error, debe usar un proveedor de DNS que es compatible con GeoDNS. Puede establecer sus registros DNS para admitir la recuperación ante desastres, para que las características que usan servicios web continuar incluso si un grupo completo de servidores Front-End deja de funcionar. Esta característica de DR es compatible con la detección automática, las reuniones y las direcciones URL sencillas de acceso telefónico local.
  
Puede definir y configurar registros A de host de DNS adicionales (AAAA si usa IPv6) para la resolución interna y externa de servicios web en su proveedor de GeoDNS. La siguiente información asume grupos emparejados, dispersos geográficamente y que el GeoDNS que admite su proveedor **tanto** tiene DNS round robin **como** está configurado para usar Pool1 como principal y conmutar por error a Pool2 en caso de cualquier pérdida de comunicación o error de alimentación.
  
Todos los registros DNS en esta tabla son ejemplos.
  
|**Registro de GeoDNS**|**Registros de grupo de servidores**|**Registros CNAME**|**Configuración de DNS (seleccione una opción)**|
|:-----|:-----|:-----|:-----|
|Reunirse int.geolb.contoso.com  <br/> |Pool1InternalWebFQDN.contoso.com  <br/> Pool2InternalWebFQDN.contoso.com  <br/> |Alias Meet.contoso.com a Pool1InternalWebFQDN.contoso.com  <br/> Alias Meet.contoso.com a Pool2InternalWebFQDN.contoso.com  <br/> |Round robin entre grupos  <br/> **O bien** <br/> Usa el primario, se conecta al secundario en caso de error  <br/> |
|Reunirse ext.geolb.contoso.com  <br/> |Pool1ExternalWebFQDN.contoso.com  <br/> Pool2ExternalWebFQDN.contoso.com  <br/> |Alias Meet.contoso.com a Pool1ExternalWebFQDN.contoso.com  <br/> Alias Meet.contoso.com a Pool2ExternalWebFQDN.contoso.com  <br/> |Round robin entre grupos  <br/> **O bien** <br/> Usa el primario, se conecta al secundario en caso de error  <br/> |
|Dialin-int.geolb.contoso.com  <br/> |Pool1InternalWebFQDN.contoso.com  <br/> Pool2InternalWebFQDN.contoso.com  <br/> |Alias Dialin.contoso.com a Pool1InternalWebFQDN.contoso.com  <br/> Alias Dialin.contoso.com a Pool2InternalWebFQDN.contoso.com  <br/> |Round robin entre grupos  <br/> **O bien** <br/> Usa el primario, se conecta al secundario en caso de error  <br/> |
|Dialin-ext.geolb.contoso.com  <br/> |Pool1ExternalWebFQDN.contoso.com  <br/> Pool2ExternalWebFQDN.contoso.com  <br/> |Alias Dialin.contoso.com a Pool1ExternalWebFQDN.contoso.com  <br/> Alias Dialin.contoso.com a Pool2ExternalWebFQDN.contoso.com  <br/> |Round robin entre grupos  <br/> **O bien** <br/> Usa el primario, se conecta al secundario en caso de error  <br/> |
|Lyncdiscoverint int.geolb.contoso.com  <br/> |Pool1InternalWebFQDN.contoso.com  <br/> Pool2InternalWebFQDN.contoso.com  <br/> |Alias Lyncdiscoverinternal.contoso.com a Pool1InternalWebFQDN.contoso.com  <br/> Alias Lyncdiscoverinternal.contoso.com a Pool2InternalWebFQDN.contoso.com  <br/> |Round robin entre grupos  <br/> **O bien** <br/> Usa el primario, se conecta al secundario en caso de error  <br/> |
|Lyncdiscover ext.geolb.contoso.com  <br/> |Pool1ExternalWebFQDN.contoso.com  <br/> Pool2ExternalWebFQDN.contoso.com  <br/> |Alias Lyncdiscover.contoso.com a Pool1ExternalWebFQDN.contoso.com  <br/> Alias Lyncdiscover.contoso.com a Pool2ExternalWebFQDN.contoso.com  <br/> |Round robin entre grupos  <br/> **O bien** <br/> Usa el primario, se conecta al secundario en caso de error  <br/> |
|Programador de int.geolb.contoso.com  <br/> |Pool1InternalWebFQDN.contoso.com  <br/> Pool2InternalWebFQDN.contoso.com  <br/> |Alias Scheduler.contoso.com a Pool1InternalWebFQDN.contoso.com  <br/> Alias Scheduler.contoso.com a Pool2InternalWebFQDN.contoso.com  <br/> |Round robin entre grupos  <br/> **O bien** <br/> Usa el primario, se conecta al secundario en caso de error  <br/> |
|Programador de ext.geolb.contoso.com  <br/> |Pool1ExternalWebFQDN.contoso.com  <br/> Pool2ExternalWebFQDN.contoso.com  <br/> |Alias Scheduler.contoso.com a Pool1ExternalWebFQDN.contoso.com  <br/> Alias Scheduler.contoso.com a Pool2ExternalWebFQDN.contoso.com  <br/> |Round robin entre grupos  <br/> **O bien** <br/> Usa el primario, se conecta al secundario en caso de error  <br/> |
   
## <a name="dns-load-balancing"></a>Equilibrio de carga de DNS
<a name="DNSLB"> </a>

El equilibrio de carga de DNS suele implementarse en el nivel de la aplicación. La aplicación (por ejemplo, un cliente que ejecuta Skype para la empresa), intenta conectarse a un servidor en un grupo de servidores mediante la conexión a una de las direcciones IP devueltas desde el DNS A y AAAA (si se usa el direccionamiento IPv6) de registro de consulta para el FQDN del grupo.
  
Por ejemplo, si hay tres servidores Front-End en un grupo denominado pool01.contoso.com, lo que sucedería:
  
- Los clientes que ejecutan Skype para la empresa de consulta DNS para pool01.contoso.com. La consulta devuelve tres direcciones IP y se almacena en caché como se indica a continuación (en cualquier orden):
    
   |||
   |:-----|:-----|
   |pool01.contoso.com  <br/> |192.168.10.90  <br/> |
   |pool01.contoso.com  <br/> |192.168.10.91  <br/> |
   |pool01.contoso.com  <br/> |192.168.10.92  <br/> |
   
- El cliente intenta establecer una conexión TCP con una de las direcciones IP. Si se genera un error, lo intentará con la siguiente dirección IP copiada en caché de esa lista.
    
- Si la conexión TCP se establece correctamente, el cliente negocia con el TLS para conectarse con el registrador principal en pool01.contoso.com.
    
- Si el cliente intenta almacenado en caché todas las entradas sin una conexión correctamente, el usuario recibe una notificación de que ningún servidor que ejecute Skype para Business Server 2015 está disponibles en ese momento.
    
> [!NOTE]
> El equilibrio de carga basado en DNS es distinto al round robin de DNS (DNS RR), que normalmente hace referencia al equilibrio de carga usando el DNS para darle un orden distinto de direcciones IP para los servidores del grupo de servidores. Por lo general, DNS RR habilita la distribución de carga, pero no le permitirá habilitar la conmutación por error. Por ejemplo, si la conexión con la dirección IP devuelta por la consulta de DNS A (o AAAA en un escenario IPv6) provoca un error, esa conexión dará error. Esto hace que el DNS RR sea menos fiable que el equilibrio de carga basado en DNS. Todavía puede usar el DNS RR en combinación con el equilibrio de carga basado en DNS si lo necesita. 
  
Usa el equilibrio de carga de DNS para:
  
- Equilibra la carga de servidor a servidor SIP a los servidores perimetrales.
    
- Equilibrar la carga de aplicaciones de servicios de aplicaciones de comunicaciones unificadas (UCAS) como Operador automático de conferencia, Grupo de respuesta y Estacionamiento de llamadas.
    
- Impedir el establecimiento de nuevas conexiones con aplicaciones UCAS (también conocido como purga).
    
- Equilibra la carga de todo el tráfico de cliente a servidor entre los clientes y servidores perimetrales.
    
No puede usar el equilibrio de carga de DNS para:
  
- Tráfico de cliente a servidor web para los servidores Front-End o un Director.
    
Para ir un poco más detallada de cómo un registro SRV de DNS seleccionado cuando varios registros DNS son devueltos por una consulta, el servicio de servidor perimetral de acceso siempre elige el objeto record con la prioridad numérica más baja y, si es un separador de placa es necesario, el peso numérico más alto. Esto es coherente con la [documentación de Internet Engineering Task Force](https://www.ietf.org/rfc/rfc2782.txt).
  
Por tanto, por ejemplo, si el primer registro SRV de DNS tiene un peso de 20 y una prioridad de 40 y el segundo registro SRV de DNS tiene un peso de 10 y una prioridad de 50, se elegirá el primer registro porque tiene la prioridad más baja, 40. La prioridad siempre va primero y es el host que un cliente elegirá primero. ¿Qué ocurre si hay dos destinos con la misma prioridad? 
  
En ese caso, el peso entra en consideración. Un mayor peso tendrá una probabilidad alta, en esta circunstancia, de ser seleccionado. Los administradores de DNS deben usar peso 0 cuando no hay ninguna selección de servidor. En la presencia de registros con peso mayor que 0, los registros con peso 0 tienen una probabilidad muy pequeña de ser seleccionados.
  
Por lo tanto, ¿qué sucede si se devuelven varios registros SRV de DNS con la misma prioridad y el mismo peso? En esta situación, el servidor perimetral de acceso servicio va a elegir el registro SRV que obtuvo desde el servidor DNS primera.
  

