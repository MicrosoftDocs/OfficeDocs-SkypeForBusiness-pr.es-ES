---
title: Planeación avanzada de DNS del servidor perimetral para Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
audience: ITPro
manager: serdars
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: f3a5895f-f64f-44eb-9a5e-8d606ac1fc38
description: Ver escenarios para Skype Empresarial Server de implementación. Tanto si desea un solo servidor como si prefiere un grupo de servidores con DNS o HLB, este tema debe ser de ayuda.
ms.openlocfilehash: 49a0af504833a30154c54e90f595b972712a530f
ms.sourcegitcommit: f3c2559a89e1c4b3514e102cf94c38a697b4bc57
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2021
ms.locfileid: "53724593"
---
# <a name="advanced-edge-server-dns-planning-for-skype-for-business-server"></a>Planeación avanzada de DNS del servidor perimetral para Skype Empresarial Server
 
**Resumen:** Revise los escenarios para Skype Empresarial Server de implementación. Tanto si desea un solo servidor como si prefiere un grupo de servidores con DNS o HLB, este tema debe ser de ayuda.
  
Cuando se trata de la planeación del sistema de nombres de dominio (DNS) para Skype Empresarial Server, pueden jugarse muchos factores en tu decisión. Si la estructura de dominio de su organización ya está en su lugar, esto puede ser una cuestión de revisar cómo va a continuar. Comenzaremos con los temas que se encuentran a continuación:
  
- [Tutorial de Skype Empresarial clientes que localizan servicios](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype)
    
- [DNS de cerebro dividido](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#SplitBrainDNS)
    
- [Configuración automática sin DNS de cerebro dividido](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#NoSplitBrainDNS)
    
- [Recuperación ante desastres de DNS](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#DNSDR)
    
- [Equilibrio de carga DNS](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#DNSLB)
    
## <a name="walkthrough-of-skype-for-business-clients-locating-services"></a>Tutorial de Skype Empresarial clientes que localizan servicios
<a name="WalkthroughOfSkype"> </a>

Skype Empresarial clientes son similares a las versiones anteriores de los clientes de Lync en la forma en que encuentran y acceden a los servicios en Skype Empresarial Server. En esta sección se detalla el proceso de ubicación del servidor.
  
1. lyncdiscoverinternal.\<domain\>
    
     *Este es un registro de host A para el servicio de detección automática en los servicios web internos.* 
    
2. lyncdiscover.\<domain\>
    
     *Se trata de un registro de host A para el servicio de detección automática en los servicios web externos.* 
    
3. _sipinternaltls._tcp.\<domain\>
    
     *Se trata de un registro SRV para las conexiones TLS internas.* 
    
4. _sip._tls.\<domain\>
    
     *Se trata de un registro SRV para conexiones TLS externas.* 
    
5. sipinternal.\<domain\>
    
     *Se trata de un registro de host A para el grupo de servidores front-end o director, que solo se puede resolver en la red interna.* 
    
6. sip.\<domain\>
    
     *Se trata de un registro de host A para el grupo de servidores front-end o director, que solo se puede resolver en la red interna.* 
    
7. sipexternal.\<domain\>
    
     *Se trata de un registro de host A para el servicio perimetral de acceso, cuando el cliente es externo.* 
    
El servicio de detección automática siempre se favorece, ya que es el método preferido para la ubicación del servicio y los demás son métodos de reserva.
  
> [!NOTE]
> Al crear registros SRV, es importante recordar que deben apuntar a un DNS A (y AAAA si usa el direccionamiento IPv6) en el mismo dominio en el que se está creando el registro SRV dns. Por ejemplo, si el registro SRV está en contoso.com, el registro A (y AAAA) al que apunta no puede estar en fabrikam.com. 
  
Si estás inclinado a hacerlo, puedes configurar el dispositivo móvil para la detección manual de servicios. Si eso es lo que está buscando hacer, cada usuario debe configurar la configuración de su dispositivo móvil con los URI completos del servicio de detección automática internos y externos, incluidos el protocolo y la ruta de acceso, de la siguiente manera:
  
- Para el acceso externo: https:// \<ExtPoolFQDN\> /Autodiscover/autodiscoverservice.svc/Root
    
- Para el acceso interno: https:// \<IntPoolFQDN\> /AutoDiscover/AutoDiscover.svc/Root
    
Se recomienda usar la detección automática en lugar de la detección manual. Pero si estás realizando algunas pruebas o solución de problemas, la configuración manual puede ser útil.
  
## <a name="split-brain-dns"></a>DNS de cerebro dividido
<a name="SplitBrainDNS"> </a>

Se trata de una configuración DNS en la que tiene dos zonas DNS con el mismo espacio de nombres. La primera zona DNS controla las solicitudes internas, mientras que la segunda zona DNS controla las solicitudes externas.
  
¿Por qué haría esto una empresa? Es posible que tengan un requisito para usar el mismo espacio de nombres interna y externamente, pero, por supuesto, esto hará que muchos registros SRV y A dns sean únicos en una zona u otra, y cuando haya duplicación, las direcciones IP asociadas a estos registros serían únicas.
  
Esta situación presenta algunos desafíos. Lo más importante es que el DNS de cerebro dividido no **es compatible** con Mobility. Esto se debe a los registros DNS de LyncDiscover y LyncDiscoverInternal (LyncDiscover debe definirse en el servidor DNS externo, mientras que LyncDiscoverInternal debe definirse en el servidor DNS interno).
  
Enumeraremos los registros DNS de las zonas internas y externas aquí, pero encontrará ejemplos detallados en la sección Requisitos del entorno del servidor perimetral.
  
### <a name="internal-dns"></a>DNS interno

- Contiene una zona DNS llamada (por ejemplo) contoso.com, para la que es autoritativa.
    
- Esta configuración contoso.com contiene:
    
  - Registros DNS A y AAAA (si usa direccionamiento IPv6) para el grupo de servidores front-end, el grupo de directores o el nombre del grupo de directores, y todos los servidores internos que ejecutan Skype Empresarial Server en la red de la organización.
    
  - Registros DNS A y AAAA (si usa el direccionamiento IPv6) para la interfaz interna perimetral para cada servidor perimetral Skype Empresarial Server de la red perimetral.
    
  - Los registros DNS A y AAAA (si usa el direccionamiento IPv6) para la interfaz  interna de cada servidor proxy inverso de la red perimetral (que es opcional para la administración de un proxy inverso).
    
  - Dns A y AAAA (si usa el direccionamiento IPv6) y registros SRV para la configuración automática del cliente de Skype Empresarial Server interno (que es **opcional).**
    
  - Dns A y AAAA (si usa el direccionamiento IPv6) o registros CNAME para la detección automática de Skype Empresarial Server Web Services (que es **opcional** ).
    
- Todas las Skype Empresarial Server las interfaces perimetrales internas de la red perimetral usan esta zona DNS interna para resolver consultas en contoso.com.
    
- Todos los servidores que ejecutan Skype Empresarial Server y los clientes que ejecutan Skype Empresarial Server en la red corporativa, apuntan a servidores DNS internos para resolver consultas en contoso.com, o usan el archivo host en cada servidor perimetral y listan registros A y AAAA (si usa direccionamiento IPv6) para el servidor del próximo salto (específicamente para el director o el servidor VIP del grupo de directores, VIP del grupo front-end o servidor Standard Edition).
    
### <a name="external-dns"></a>DNS externo

- Contiene una zona DNS llamada (por ejemplo) contoso.com, para la que es autoritativa.
    
- Esta contoso.com contiene:
    
  - Dns A y AAAA (si usa el direccionamiento IPv6) o registros CNAME, para la detección automática de Skype Empresarial Server web. Esto se usa con movilidad.
    
  - Dns A y AAAA (si usa el direccionamiento IPv6) y registros SRV para la interfaz externa perimetral de cada servidor perimetral de Skype Empresarial Server o VIP de carga perimetral equilibrada (HLB) en la red perimetral.
    
  - Dns A y AAAA (si usa el direccionamiento IPv6) y registros SRV para la interfaz externa del servidor proxy inverso o (VIP para un grupo de servidores proxy inversos), en la red perimetral.
    
  - Dns A y AAAA (si usa el direccionamiento IPv6) y registros SRV para la configuración automática Skype Empresarial Server cliente ( **opcional** ).
    
## <a name="automatic-configuration-without-split-brain-dns"></a>Configuración automática sin DNS de cerebro dividido
<a name="NoSplitBrainDNS"> </a>

Si no usa DNS de cerebro dividido, la configuración automática interna de los clientes que ejecutan Skype Empresarial no funcionará a menos que use una de las soluciones alternativas que tenemos aquí. ¿Por qué no? Dado Skype Empresarial Server requiere que el URI de SIP del usuario coincida con el dominio del grupo de servidores front-end designado para la configuración automática. Esto no ha cambiado con respecto a versiones anteriores de Lync Server.
  
Por lo tanto, si tiene dos dominios SIP en uso, necesitará estos registros SRV dns:
  
- _sipinternaltls._tcp.contoso.com. 86400 IN SRV 0 0 5061 pool01.contoso.com
    
     *Si un usuario inicia sesión como bob@contoso.com, este registro funcionaría para la configuración automática, ya que el dominio SIP del usuario coincide con el dominio del grupo de servidores front-end (contoso.com).* 
    
- _sipinternaltls._tcp.fabrikam.com. 86400 IN SRV 0 0 5061 pool01.fabrikam.com
    
     *Si un usuario inicia sesión como alice@fabrikam.com, este registro funcionaría para la configuración automática del segundo dominio, de nuevo porque el dominio SIP coincide con el grupo de servidores front-end de ese dominio.* 
    
Para seguir con el ejemplo, esto no funcionaría:
  
- _sipinternaltls._tcp.litwareinc.com. 86400 IN SRV 0 0 5061 pool01.fabrikam.com
    
     *Un usuario que inicia sesión como tim@litwareinc.com no funcionará para la configuración automática, ya que su dominio SIP (litwareinc.com) no coincide con el dominio del grupo (fabrikam.com).* 
    
Por lo tanto, ahora que sabemos todo eso, si necesita requisitos automáticos para sus clientes de Skype Empresarial sin DNS de cerebro dividido, tiene estas opciones:
  
- **Objetos de directiva de grupo**
    
    Puede usar objetos de directiva de grupo (GPO) para rellenar los valores de servidor correctos.
    
    > [!NOTE]
    > Esta opción no habilita la configuración automática, pero automatiza la configuración manual. Si se usa este enfoque, no se requieren los registros SRV asociados con la configuración automática. 
  
- **Zona interna coincidente**
    
    Deberá crear una zona en el DNS interno que coincida con la zona DNS externa (por ejemplo, contoso.com) y, a continuación, crear registros DNS A (y AAAA si usa direccionamiento IPv6) que correspondan al grupo de servidores de Skype Empresarial Server usado para la configuración automática.
    
    Por ejemplo, si tiene un usuario en pool01.contoso.net, pero inicia sesión en Skype Empresarial como bob@contoso.com, cree una zona DNS interna denominada contoso.com y dentro de ella debe crear un registro DNS A (y AAAA si se usa el direccionamiento IPv6) para pool01.contoso.com.
    
- **Zona interna designada**
    
    Si la creación de una zona completa en el DNS interno no es una opción para usted, puede crear zonas de punto de patilla (dedicados) que correspondan a los registros SRV necesarios para la configuración automática y rellenar dichas zonas mediante dnscmd.exe. Dnscmd.exe es necesario porque la interfaz de usuario dns no admite la creación de zonas de punto de patilla.
    
    Por ejemplo, si el dominio SIP es contoso.com y tiene un grupo de servidores front-end denominado pool01 que contiene dos servidores front-end, necesitará las siguientes zonas de punto de patilla y registros A en su DNS interno:
    
  ```console
  dnscmd . /zoneadd _sipinternaltls._tcp.contoso.com. /dsprimary
  dnscmd . /recordadd _sipinternaltls._tcp.contoso.com. @ SRV 0 0 5061 pool01.contoso.com.
  dnscmd . /zoneadd pool01.contoso.com. /dsprimary
  dnscmd . /recordadd pool01.contoso.com. @ A 192.168.10.90
  dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
  dnscmd . /recordadd pool01.contoso.com. @ A 192.168.10.91 
  dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
  ```

    Es posible que tenga un segundo dominio SIP en su entorno. En ese caso, necesitará las siguientes zonas de punto de patilla y registros A en su DNS interno:
    
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
> Verá que el FQDN del grupo de servidores front-end aparece dos veces, pero con dos direcciones IP diferentes. Esto se debe a que se usa el equilibrio de carga dns. Si se usa HLB, solo habría una sola entrada de grupo front-end. 
  
> [!NOTE]
> Además, los valores de FQDN del grupo de servidores front-end cambian entre los ejemplos contoso.com y fabrikam.com, pero las direcciones IP siguen siendo las mismas. Esto se debe a que los usuarios que inician sesión desde cualquier dominio SIP usarán el mismo grupo de servidores front-end para la configuración automática. 
  
## <a name="dns-disaster-recovery"></a>Recuperación ante desastres de DNS
<a name="DNSDR"> </a>

Para configurar DNS para redirigir Skype Empresarial Server web a los sitios de recuperación ante desastres (DR) y de conmutación por error, debe usar un proveedor dns que admita GeoDNS. Puede configurar los registros DNS para admitir la recuperación ante desastres, de modo que las características que usan servicios web continúen incluso si un grupo de servidores front-end completo cae. Esta característica de recuperación ante desastres admite las direcciones URL sencillas de detección automática, reunión y acceso telefónico.
  
Defina y configure registros A de host DNS adicionales (AAAA si usa IPv6) para la resolución interna y externa de servicios web en su proveedor de GeoDNS. Los siguientes detalles suponen que los grupos de servidores emparejados, geográficamente dispersos, y que los GeoDNS admitidos por el proveedor tienen **DNS** por turnos o están configurados para usar Pool1 como principal y conmutan por error a Pool2 en caso de pérdida de comunicaciones o error de energía. 
  
Todos los registros DNS de esta tabla son ejemplos.
  
|**Registro GeoDNS**|**Registros de grupo**|**Registros CNAME**|**Configuración dns (seleccione una opción)**|
|:-----|:-----|:-----|:-----|
|Meet-int.geolb.contoso.com  <br/> |Pool1InternalWebFQDN.contoso.com  <br/> Pool2InternalWebFQDN.contoso.com  <br/> |Meet.contoso.com alias a Pool1InternalWebFQDN.contoso.com  <br/> Meet.contoso.com alias a Pool2InternalWebFQDN.contoso.com  <br/> |Round Robin entre grupos  <br/> **OR** <br/> Use primary, connect to secondary if there's a failure  <br/> |
|Meet-ext.geolb.contoso.com  <br/> |Pool1ExternalWebFQDN.contoso.com  <br/> Pool2ExternalWebFQDN.contoso.com  <br/> |Meet.contoso.com alias a Pool1ExternalWebFQDN.contoso.com  <br/> Meet.contoso.com alias a Pool2ExternalWebFQDN.contoso.com  <br/> |Round Robin entre grupos  <br/> **OR** <br/> Use primary, connect to secondary if there's a failure  <br/> |
|Dialin-int.geolb.contoso.com  <br/> |Pool1InternalWebFQDN.contoso.com  <br/> Pool2InternalWebFQDN.contoso.com  <br/> |Dialin.contoso.com alias a Pool1InternalWebFQDN.contoso.com  <br/> Dialin.contoso.com alias a Pool2InternalWebFQDN.contoso.com  <br/> |Round Robin entre grupos  <br/> **OR** <br/> Use primary, connect to secondary if there's a failure  <br/> |
|Dialin-ext.geolb.contoso.com  <br/> |Pool1ExternalWebFQDN.contoso.com  <br/> Pool2ExternalWebFQDN.contoso.com  <br/> |Dialin.contoso.com alias a Pool1ExternalWebFQDN.contoso.com  <br/> Dialin.contoso.com alias a Pool2ExternalWebFQDN.contoso.com  <br/> |Round Robin entre grupos  <br/> **OR** <br/> Use primary, connect to secondary if there's a failure  <br/> |
|Lyncdiscoverint-int.geolb.contoso.com  <br/> |Pool1InternalWebFQDN.contoso.com  <br/> Pool2InternalWebFQDN.contoso.com  <br/> |Lyncdiscoverinternal.contoso.com alias a Pool1InternalWebFQDN.contoso.com  <br/> Lyncdiscoverinternal.contoso.com alias a Pool2InternalWebFQDN.contoso.com  <br/> |Round Robin entre grupos  <br/> **OR** <br/> Use primary, connect to secondary if there's a failure  <br/> |
|Lyncdiscover-ext.geolb.contoso.com  <br/> |Pool1ExternalWebFQDN.contoso.com  <br/> Pool2ExternalWebFQDN.contoso.com  <br/> |Lyncdiscover.contoso.com alias a Pool1ExternalWebFQDN.contoso.com  <br/> Lyncdiscover.contoso.com alias a Pool2ExternalWebFQDN.contoso.com  <br/> |Round Robin entre grupos  <br/> **OR** <br/> Use primary, connect to secondary if there's a failure  <br/> |
|Scheduler-int.geolb.contoso.com  <br/> |Pool1InternalWebFQDN.contoso.com  <br/> Pool2InternalWebFQDN.contoso.com  <br/> |Scheduler.contoso.com alias a Pool1InternalWebFQDN.contoso.com  <br/> Scheduler.contoso.com alias a Pool2InternalWebFQDN.contoso.com  <br/> |Round Robin entre grupos  <br/> **OR** <br/> Use primary, connect to secondary if there's a failure  <br/> |
|Scheduler-ext.geolb.contoso.com  <br/> |Pool1ExternalWebFQDN.contoso.com  <br/> Pool2ExternalWebFQDN.contoso.com  <br/> |Scheduler.contoso.com alias a Pool1ExternalWebFQDN.contoso.com  <br/> Scheduler.contoso.com alias a Pool2ExternalWebFQDN.contoso.com  <br/> |Round Robin entre grupos  <br/> **OR** <br/> Use primary, connect to secondary if there's a failure  <br/> |
   
## <a name="dns-load-balancing"></a>equilibrio de carga de DNS
<a name="DNSLB"> </a>

El equilibrio de carga dns se suele implementar en el nivel de la aplicación. La aplicación (por ejemplo, un cliente que ejecuta Skype Empresarial), intenta conectarse a un servidor de un grupo de servidores conectándose a una de las direcciones IP devueltas de la consulta de registro DNS A y AAAA (si se usa el direccionamiento IPv6) para el FQDN del grupo.
  
Por ejemplo, si hay tres servidores front-end en un grupo denominado pool01.contoso.com, sucedería lo siguiente:
  
- Los clientes que Skype Empresarial consulta DNS para pool01.contoso.com. La consulta devuelve tres direcciones IP y las almacena en caché de la siguiente manera (en algún orden):
    
   |&nbsp;|&nbsp;|
   |:-----|:-----|
   |pool01.contoso.com  <br/> |192.168.10.90  <br/> |
   |pool01.contoso.com  <br/> |192.168.10.91  <br/> |
   |pool01.contoso.com  <br/> |192.168.10.92  <br/> |
   
- El cliente intenta establecer una conexión TCP a una de las direcciones IP. Si se produce un error, probará la siguiente dirección IP que se almacena en caché de esa lista.
    
- Si la conexión TCP se realiza correctamente, el cliente negocia TLS para conectarse al registrador principal en pool01.contoso.com.
    
- Si el cliente intenta todas las entradas almacenadas en caché sin una conexión correcta, el usuario recibe una notificación de que no hay servidores que ejecuten Skype Empresarial Server están disponibles en este momento.
    
> [!NOTE]
> El equilibrio de carga basado en DNS es diferente de DNS round robin (DNS RR), que normalmente hace referencia al equilibrio de carga al depender de DNS para dar un orden diferente de direcciones IP para los servidores del grupo. Normalmente, DNS RR habilita la distribución de carga, pero no permite habilitar la conmutación por error. Por ejemplo, si se produce un error en la conexión a la única dirección IP devuelta por la consulta DNS A (o AAAA en un escenario IPv6), se producirá un error en esa conexión. Esto hace que DNS RR sea menos confiable que el equilibrio de carga basado en DNS. Aún puede usar DNS RR junto con el equilibrio de carga basado en DNS si necesita hacerlo. 
  
Se usa el equilibrio de carga DNS para:
  
- Equilibrio de carga sip de servidor a servidor con los servidores perimetrales.
    
- Equilibrar la carga de aplicaciones de servicios de aplicaciones de comunicación unificada (UCAS), como conferencias Operador automático, grupo de respuesta y estacionamiento de llamadas.
    
- Impedir nuevas conexiones a aplicaciones de UCAS (también conocidas como desagüe).
    
- Equilibrio de carga de todo el tráfico de cliente a servidor entre clientes y servidores perimetrales.
    
No puede usar el equilibrio de carga dns para:
  
- Tráfico web de cliente a servidor a los servidores front-end o a un director.
    
Para ir un poco más en profundidad sobre cómo se selecciona un registro SRV dns cuando una consulta devuelve varios registros DNS, el servicio perimetral de acceso siempre elige el registro con la prioridad numérica más baja y, si se necesita un desempate, el mayor peso numérico. Esto es coherente con la [documentación del Grupo de tareas de ingeniería de Internet](https://www.ietf.org/rfc/rfc2782.txt).
  
Por ejemplo, si el primer registro SRV de DNS tiene un peso de 20 y una prioridad de 40, y el segundo registro SRV de DNS tiene un peso de 10 y una prioridad de 50, se elegirá el primer registro porque tiene la prioridad inferior de 40. La prioridad siempre va primero y ese es el host al que se dirigirá primero un cliente. ¿Qué sucede si hay dos objetivos con la misma prioridad? 
  
En ese caso, se tiene en cuenta el peso. Los pesos más grandes deben tener una alta probabilidad, en esta circunstancia, de ser seleccionados. Los administradores DNS deben usar el peso 0 cuando no hay ninguna selección de servidor que hacer. En presencia de registros que contienen pesos mayores que 0, los registros con el peso 0 tienen una probabilidad muy pequeña de traer seleccionados.
  
Entonces, ¿qué sucede si se devuelven varios registros SRV dns con la misma prioridad y peso? En esta situación, el servicio perimetral de acceso elegirá primero el registro SRV que obtuvo del servidor DNS.
  

