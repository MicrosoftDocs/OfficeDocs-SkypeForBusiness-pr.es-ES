---
title: DNS del servidor de borde planificación avanzada para Skype para Business Server 2015
ms.author: heidip
author: microsoftheidi
ms.date: 2/15/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- IT_Skype16
ms.custom:
- Strat_SB_Hybrid
- Strat_SB_Hybrid
ms.assetid: f3a5895f-f64f-44eb-9a5e-8d606ac1fc38
description: 'Resumen: Revisar escenarios de Skype Business Server 2015 para opciones de implementación. Si desea que un único servidor o prefiere un grupo de servidores con DNS o HLB, debe ayudar este tema.'
ms.openlocfilehash: b3c9299586856b59a8f07f7f2bcb460268c6d687
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="advanced-edge-server-dns-planning-for-skype-for-business-server-2015"></a>DNS del servidor de borde planificación avanzada para Skype para Business Server 2015
 
**Resumen:** revise escenarios para las opciones de implementación de Skype Empresarial Server 2015. Tanto si desea un único servidor como si prefiere un grupo de servidores con DNS o HLB, este tema puede ayudarle.
  
En cuanto a la planificación de sistema de nombres de dominio (DNS) de Skype para Business Server 2015, hay muchos factores que pueden desempeñar en su decisión. Si la estructura del dominio de su organización ya está en el lugar correcto, puede ser una cuestión de revisar la manera en la que va a continuar. Comenzaremos con los temas que se encuentran a continuación:
  
- [Walkthrough of Skype for Business clients locating services](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype)
    
- [Split-brain DNS](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#SplitBrainDNS)
    
- [Automatic configuration without split-brain DNS](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#NoSplitBrainDNS)
    
- [DNS disaster recovery](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#DNSDR)
    
- [DNS load balancing](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#DNSLB)
    
## <a name="walkthrough-of-skype-for-business-clients-locating-services"></a>Walkthrough of Skype for Business clients locating services
<a name="WalkthroughOfSkype"> </a>

Skype para clientes de empresa son similares a las versiones anteriores de clientes de Lync en cómo encontrar y tener acceso a los servicios de Skype para Business Server 2015. Esta sección contiene información sobre el proceso de ubicación del servidor.
  
1. lyncdiscoverinternal. \<dominio\>
    
     *Es un registro de host A para el servicio Detección automática en los servicios web internos.* 
    
2. lyncdiscover. \<dominio\>
    
     *Es un registro de host A para el servicio Detección automática en los servicios web externos.* 
    
3. _sipinternaltls._tcp. \<dominio\>
    
     *Es un registro SRV para las conexiones TLS internas.* 
    
4. _sip._tls. \<dominio\>
    
     *Es un registro SRV para las conexiones TLS externas.* 
    
5. sipinternal. \<dominio\>
    
     *Se trata de un registro de host a para el grupo de servidores Front-End o Director, puede resolver únicamente en la red interna.* 
    
6. SIP. \<dominio\>
    
     *Se trata de un registro de host a para el grupo de servidores Front-End o Director, puede resolver únicamente en la red interna.* 
    
7. sipexternal. \<dominio\>
    
     *Esto es un registro host para el servicio de servidor perimetral de acceso, cuando el cliente es externo.* 
    
El servicio Detección automática es siempre el favorito, ya que es el método preferido para la ubicación del servicio y los demás son métodos reserva.
  
> [!NOTE]
> Al crear registros SRV, es importante recordar que tienen que señalar a un registro A de DNS (y AAAA si está usando el direccionamiento IPv6) en el mismo dominio en el que se ha creado el registro de DNS SRV. Por ejemplo, si el registro SRV está en contoso.com, el registro A (y AAAA) al que señala no puede encontrarse en fabrikam.com. 
  
Si está dispuesto a hacerlo, puede configurar su dispositivo móvil para la detección manual de servicios. Si es lo que quiere hacer, cada usuario tiene que configurar los parámetros del dispositivo móvil con las URL internas y externas completas del servicio Detección automática, incluyendo el protocolo y la ruta de acceso, de la manera siguiente:
  
- Para obtener acceso externo: https://\<ExtPoolFQDN\>/Autodiscover/autodiscoverservice.svc/Root
    
- Para el acceso interno: https://\<IntPoolFQDN\>/AutoDiscover/AutoDiscover.svc/Root
    
Le recomendamos usar la detección automática en contraposición con la detección manual, pero si está solucionando problemas o realizando alguna prueba, la configuración manual puede ser muy útil.
  
## <a name="split-brain-dns"></a>DNS de horizonte dividido
<a name="SplitBrainDNS"> </a>

Se trata de una configuración de DNS en la que tiene dos zonas de DNS con el mismo espacio de nombres. La primera zona DNS trata solicitudes internas, mientras que la segunda zona DNS trata las solicitudes externas.
  
¿Por qué haría esto una compañía? Puede que tengan un requisito de usar el mismo espacio de nombres internamente y externamente, pero, por supuesto esto llevará a muchos SRV de DNS y registros A únicos en una zona u otra, y donde hay duplicación, las direcciones IP asociadas con estos registros serían únicas.
  
Esto presenta algunos desafíos. El más importante es que DNS Brain **no compatible** para la movilidad. Esto se debe a los registros DNS LyncDiscover y LyncDiscoverInternal (LyncDiscover tiene que definirse en el servidor DNS externo, mientras que LyncDiscoverInternal tiene que definirse en el servidor DNS interno).
  
Le enumeramos los registros DNS para las zonas internas y externas, pero encontrará ejemplos detallados en la sección de requisitos del entorno de servidor perimetral.
  
### <a name="internal-dns"></a>DNS interno

- Contiene una zona DNS llamada (por ejemplo) contoso.com, para la que es relevante.
    
- Esta contoso.com interna contiene:
    
  - Registros DNS A y AAAA (si se utiliza direccionamiento IPv6) para el grupo de servidores Front-End, Director grupo o nombre de grupo de Director y todos los servidores internos con Skype para Business Server 2015 en la red de su organización.
    
  - A y AAAA (si se utiliza direccionamiento IPv6) registros DNS para la interfaz interna del borde para cada Skype para Business Server 2015 Edge Server en la red perimetral.
    
  - Registros DNS A y AAAA (si se utiliza direccionamiento IPv6) para la interfaz interna de cada servidor proxy inverso en la red perimetral (que es **opcional** para la administración de un proxy inverso).
    
  - Registros DNS A y AAAA (si se utiliza direccionamiento IPv6) y SRV de Skype interno para la configuración automática del cliente de Business Server 2015 (que es **opcional** ).
    
  - DNS A y AAAA (si se utiliza direccionamiento IPv6) o CNAME de detección automática de Skype para Business Server 2015 Web Services (que es **opcional** ).
    
- Todos tu Skype para Business Server 2015 interfaces internas del borde de la red perimetral Utilice esta zona DNS interna para resolver consultas en contoso.com.
    
- Seleccione todos los servidores de Skype para Business Server 2015 y clientes que ejecutan Skype para Business Server 2015 en la red corporativa, a los servidores DNS internos para resolver consultas en contoso.com o utilizar el archivo hosts de cada servidor perimetral y lista A y AAAA si ( utiliza direccionamiento IPv6) registros para el servidor del próximo salto (específicamente por el Director o grupo VIP del Director, frontal final grupo VIP o servidor Standard Edition).
    
### <a name="external-dns"></a>DNS externo

- Contiene una zona DNS llamada (por ejemplo) contoso.com, para la que es relevante.
    
- Esta contoso.com externa contiene:
    
  - DNS A y AAAA (si se utiliza direccionamiento IPv6) o CNAME registros, la detección automática de Skype para los servicios web de Business Server 2015. Es para usar con movilidad.
    
  - DNS A y AAAA (si se utiliza direccionamiento IPv6) y los registros SRV para la interfaz externa del borde de cada Skype para Business Server 2015 Edge Server o carga de hardware habían equilibrado a VIP (HLB) en la red perimetral.
    
  - Registros DNS A y AAAA (si se utiliza direccionamiento IPv6) y SRV para la interfaz externa del servidor proxy inverso o (VIP para un grupo de servidores de proxy inverso), en la red perimetral.
    
  - Registros DNS A y AAAA (si se utiliza direccionamiento IPv6) y SRV de Skype para la configuración automática de cliente Business Server 2015 (**opcional**).
    
## <a name="automatic-configuration-without-split-brain-dns"></a>Configuración automática sin DNS de horizonte dividido
<a name="NoSplitBrainDNS"> </a>

Si no utiliza DNS Brain, la configuración automática interna de clientes de Skype para empresas no funcionará si no está utilizando una de las soluciones que tenemos aquí. ¿Por qué no? Porque Skype para Business Server 2015 requiere URI de SIP del usuario para que coincida con el dominio del grupo de servidores Front-End designado para la configuración automática. Esto no ha cambiado desde las versiones anteriores de Lync Server.
  
Por lo tanto, si tiene dos dominios SIP en uso, necesitará estos registros SRV de DNS:
  
- _sipinternaltls._tcp.contoso.com. 86400 IN SRV 0 0 5061 pool01.contoso.com
    
     *Si un usuario inicia una sesión como bob@contoso.com, este registro funcionaría para la configuración automática, como dominio SIP del usuario coincide con el dominio del grupo de servidores Front-End (contoso.com).* 
    
- _sipinternaltls._tcp.fabrikam.com. 86400 IN SRV 0 0 5061 pool01.fabrikam.com
    
     *Si un usuario inicia una sesión como alice@fabrikam.com, este registro funcionaría para la configuración automática del segundo dominio, nuevo porque el dominio SIP coincide con el grupo de Front-End para ese dominio.* 
    
Para llevar el ejemplo más allá, esto no funcionaría:
  
- _sipinternaltls._tcp.litwareinc.com. 86400 IN SRV 0 0 5061 pool01.fabrikam.com
    
     *Un usuario iniciando sesión como tim@litwareinc.com no funcionará para la configuración automática, porque su dominio SIP (litwareinc.com) no coincide con el dominio del grupo (fabrikam.com).* 
    
Ahora que sabemos todo eso, si usted necesita el requisito automático para tu Skype para clientes empresariales sin DNS Brain, tienes estas opciones:
  
- **Objetos de directiva de grupo**
    
    Puede usar objetos de directiva de grupo (GPO) para rellenar los valores de servidor correctos.
    
    > [!NOTE]
    > Esta opción no habilita la configuración automática, pero automatiza la configuración manual. Si se usa este enfoque, los registros SRV asociados con la configuración automática no son obligatorios. 
  
- **Correspondencia de zona interna**
    
    Necesitará crear una zona en el DNS interno que coincida con su zona DNS externa (por ejemplo, contoso.com) y, a continuación, crear DNS A (y AAAA si utiliza direccionamiento IPv6) registros que corresponden a la Skype para grupo de Business Server 2015 utilizado en automático configuración.
    
    Por ejemplo, si tiene un usuario alojados en pool01.contoso.net, pero signos en Skype para negocios como bob@contoso.com, crear una zona DNS interna llamada contoso.com y, dentro de lo que necesite crear un DNS A (y AAAA si se utiliza IPv6 addressing) registro de pool01.contoso.com.
    
- **Zona interna de punto de anclaje**
    
    Si crear una zona entera en el DNS interno no es una opción, puede crear zonas de punto de anclaje (dedicadas) que se correspondan con los registros SRV necesarios para la configuración automática y rellenar esas zonas con dnscmd.exe. Dnscmd.exe es obligatorio porque la interfaz de usuario de DNS no admite la creación de zonas de punto de anclaje.
    
    Por ejemplo, si su dominio SIP es contoso.com, y tiene un grupo de Front-End llamado pool01 que contiene dos servidores frontales, necesitará las siguientes zonas de la punta y registros en el DNS interno:
    
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
> Verá el grupo de servidores frontales que FQDN aparece dos veces, pero con dos direcciones IP diferentes. Esto se debe a que se usa el equilibrio de carga de DNS. Si se utiliza HLB, sólo habría un único movimiento de grupo de servidores Front-End. 
  
> [!NOTE]
> Asimismo, cambian los valores FQDN del grupo de servidores de Front-End entre los ejemplos de contoso.com y fabrikam.com, pero las direcciones IP siguen siendo los mismos. Eso es porque los usuarios que están identificando desde cualquiera de los dominios SIP va a utilizar el mismo grupo de Front-End para la configuración automática. 
  
## <a name="dns-disaster-recovery"></a>Recuperación ante desastres de DNS
<a name="DNSDR"> </a>

Para configurar DNS para redirigir Skype para el tráfico web de Business Server 2015 para la recuperación ante desastres (DR) y los sitios de conmutación por error, debe utilizar un proveedor DNS que admite GeoDNS. Puede configurar los registros DNS para admitir la recuperación de desastres, por lo que características que utilizan servicios web continuar incluso si falla un grupo completo de Front-End. Esta característica de DR es compatible con la detección automática, las reuniones y las direcciones URL sencillas de acceso telefónico local.
  
Puede definir y configurar registros A de host de DNS adicionales (AAAA si usa IPv6) para la resolución interna y externa de servicios web en su proveedor de GeoDNS. La siguiente información asume grupos emparejados, dispersos geográficamente y que el GeoDNS que admite su proveedor **tanto** tiene DNS round robin **como** está configurado para usar Pool1 como principal y conmutar por error a Pool2 en caso de cualquier pérdida de comunicación o error de alimentación.
  
Todos los registros DNS en esta tabla son ejemplos.
  
|**Registro de GeoDNS**|**Registros de grupo**|**Registros CNAME**|**Configuración de DNS (seleccione una opción)**|
|:-----|:-----|:-----|:-----|
|Satisfacer int.geolb.contoso.com  <br/> |Pool1InternalWebFQDN.contoso.com  <br/> Pool2InternalWebFQDN.contoso.com  <br/> |Alias Meet.contoso.com a Pool1InternalWebFQDN.contoso.com  <br/> Alias Meet.contoso.com a Pool2InternalWebFQDN.contoso.com  <br/> |Round robin entre grupos  <br/> **O bien** <br/> Usa el primario, se conecta al secundario en caso de error  <br/> |
|Satisfacer ext.geolb.contoso.com  <br/> |Pool1ExternalWebFQDN.contoso.com  <br/> Pool2ExternalWebFQDN.contoso.com  <br/> |Alias Meet.contoso.com a Pool1ExternalWebFQDN.contoso.com  <br/> Alias Meet.contoso.com a Pool2ExternalWebFQDN.contoso.com  <br/> |Round robin entre grupos  <br/> **O bien** <br/> Usa el primario, se conecta al secundario en caso de error  <br/> |
|Dialin-int.geolb.contoso.com  <br/> |Pool1InternalWebFQDN.contoso.com  <br/> Pool2InternalWebFQDN.contoso.com  <br/> |Alias Dialin.contoso.com a Pool1InternalWebFQDN.contoso.com  <br/> Alias Dialin.contoso.com a Pool2InternalWebFQDN.contoso.com  <br/> |Round robin entre grupos  <br/> **O bien** <br/> Usa el primario, se conecta al secundario en caso de error  <br/> |
|Dialin-ext.geolb.contoso.com  <br/> |Pool1ExternalWebFQDN.contoso.com  <br/> Pool2ExternalWebFQDN.contoso.com  <br/> |Alias Dialin.contoso.com a Pool1ExternalWebFQDN.contoso.com  <br/> Alias Dialin.contoso.com a Pool2ExternalWebFQDN.contoso.com  <br/> |Round robin entre grupos  <br/> **O bien** <br/> Usa el primario, se conecta al secundario en caso de error  <br/> |
|Lyncdiscoverint-int.geolb.contoso.com  <br/> |Pool1InternalWebFQDN.contoso.com  <br/> Pool2InternalWebFQDN.contoso.com  <br/> |Alias Lyncdiscoverinternal.contoso.com a Pool1InternalWebFQDN.contoso.com  <br/> Alias Lyncdiscoverinternal.contoso.com a Pool2InternalWebFQDN.contoso.com  <br/> |Round robin entre grupos  <br/> **O bien** <br/> Usa el primario, se conecta al secundario en caso de error  <br/> |
|Lyncdiscover-ext.geolb.contoso.com  <br/> |Pool1ExternalWebFQDN.contoso.com  <br/> Pool2ExternalWebFQDN.contoso.com  <br/> |Alias Lyncdiscover.contoso.com a Pool1ExternalWebFQDN.contoso.com  <br/> Alias Lyncdiscover.contoso.com a Pool2ExternalWebFQDN.contoso.com  <br/> |Round robin entre grupos  <br/> **O bien** <br/> Usa el primario, se conecta al secundario en caso de error  <br/> |
|Programador int.geolb.contoso.com  <br/> |Pool1InternalWebFQDN.contoso.com  <br/> Pool2InternalWebFQDN.contoso.com  <br/> |Alias Scheduler.contoso.com a Pool1InternalWebFQDN.contoso.com  <br/> Alias Scheduler.contoso.com a Pool2InternalWebFQDN.contoso.com  <br/> |Round robin entre grupos  <br/> **O bien** <br/> Usa el primario, se conecta al secundario en caso de error  <br/> |
|Programador ext.geolb.contoso.com  <br/> |Pool1ExternalWebFQDN.contoso.com  <br/> Pool2ExternalWebFQDN.contoso.com  <br/> |Alias Scheduler.contoso.com a Pool1ExternalWebFQDN.contoso.com  <br/> Alias Scheduler.contoso.com a Pool2ExternalWebFQDN.contoso.com  <br/> |Round robin entre grupos  <br/> **O bien** <br/> Usa el primario, se conecta al secundario en caso de error  <br/> |
   
## <a name="dns-load-balancing"></a>Equilibrio de carga de DNS
<a name="DNSLB"> </a>

El equilibrio de carga de DNS suele implementarse en el nivel de la aplicación. La aplicación (por ejemplo, un cliente ejecuta Skype para empresas), intenta conectarse a un servidor en un grupo mediante la conexión a una de las direcciones IP devueltas desde el DNS A y AAAA (si se utiliza direccionamiento IPv6) de registro de consulta para el FQDN del grupo.
  
Por ejemplo, si hay tres servidores frontales en un grupo denominado pool01.contoso.com, lo siguiente ocurre:
  
- Los clientes ejecutan Skype para empresas consultar DNS para pool01.contoso.com. La consulta devuelve tres direcciones IP y se almacena en caché como sigue (en cualquier orden):
    
   |||
   |:-----|:-----|
   |pool01.contoso.com  <br/> |192.168.10.90  <br/> |
   |pool01.contoso.com  <br/> |192.168.10.91  <br/> |
   |pool01.contoso.com  <br/> |192.168.10.92  <br/> |
   
- El cliente intenta establecer una conexión TCP con una de las direcciones IP. Si se genera un error, lo intentará con la siguiente dirección IP copiada en caché de esa lista.
    
- Si la conexión TCP se establece correctamente, el cliente negocia con el TLS para conectarse con el registrador principal en pool01.contoso.com.
    
- Si el cliente intenta en caché todas las entradas sin una conexión correcta, el usuario recibe una notificación de que no hay servidores ejecutando Skype para Business Server 2015 están disponibles en este momento.
    
> [!NOTE]
> El equilibrio de carga basado en DNS es distinto al round robin de DNS (DNS RR), que normalmente hace referencia al equilibrio de carga usando el DNS para darle un orden distinto de direcciones IP para los servidores del grupo de servidores. Por lo general, DNS RR habilita la distribución de carga, pero no le permitirá habilitar la conmutación por error. Por ejemplo, si la conexión con la dirección IP devuelta por la consulta de DNS A (o AAAA en un escenario IPv6) provoca un error, esa conexión dará error. Esto hace que el DNS RR sea menos fiable que el equilibrio de carga basado en DNS. Todavía puede usar el DNS RR en combinación con el equilibrio de carga basado en DNS si lo necesita. 
  
Usa el equilibrio de carga de DNS para:
  
- Equilibra la carga de servidor a servidor SIP para los servidores perimetrales.
    
- Equilibrar la carga de aplicaciones de servicios de aplicaciones de comunicaciones unificadas (UCAS) como Operador automático de conferencia, Grupo de respuesta y Estacionamiento de llamadas.
    
- Impedir el establecimiento de nuevas conexiones con aplicaciones UCAS (también conocido como purga).
    
- Equilibra la carga de todo el tráfico de cliente a servidor entre clientes y servidores perimetrales.
    
No puede usar el equilibrio de carga de DNS para:
  
- Tráfico de cliente a servidor web a los servidores frontales o un Director.
    
Para profundizar un poco más en cómo se selecciona un registro SRV de DNS cuando varios registros DNS son devueltos por una consulta, el servicio de servidor perimetral de acceso siempre elige el registro con la prioridad numérica más baja y, si es un factor de desempate es necesario, el peso numérico más alto. Esto es coherente con la [documentación de Internet Engineering Task Force](https://www.ietf.org/rfc/rfc2782.txt).
  
Por tanto, por ejemplo, si el primer registro SRV de DNS tiene un peso de 20 y una prioridad de 40 y el segundo registro SRV de DNS tiene un peso de 10 y una prioridad de 50, se elegirá el primer registro porque tiene la prioridad más baja, 40. La prioridad siempre va primero y es el host que un cliente elegirá primero. ¿Qué ocurre si hay dos destinos con la misma prioridad? 
  
En ese caso, el peso entra en consideración. Un mayor peso tendrá una probabilidad alta, en esta circunstancia, de ser seleccionado. Los administradores de DNS deben usar peso 0 cuando no hay ninguna selección de servidor. En la presencia de registros con peso mayor que 0, los registros con peso 0 tienen una probabilidad muy pequeña de ser seleccionados.
  
Por lo tanto, ¿qué sucede si se devuelven varios registros SRV de DNS con la misma prioridad y el mismo peso? En esta situación, el servidor perimetral de acceso servicio elegirá el registro SRV que obtuvo desde el servidor DNS primero.
  

