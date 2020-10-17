---
title: 'Lync Server 2013: determinar los requisitos de DNS'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Determine DNS requirements
ms:assetid: 95777017-6282-44c0-a685-f246af0501b4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398758(v=OCS.15)
ms:contentKeyID: 48184839
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d00f86eb437f673e83e2ea2e610ad9b35dbea082
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48522607"
---
# <a name="determine-dns-requirements-for-lync-server-2013"></a>Determinación de los requisitos de DNS para Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-22_

Use el diagrama de flujo siguiente para determinar los requisitos del Sistema de nombres de dominio (DNS). Cambios en las actualizaciones acumulativas de Lync Server 2013: el 2013 de febrero se indica dónde se aplican.

<div>


> [!IMPORTANT]  
> Microsoft Lync Server 2013 admite el uso de direcciones IPv6. Para usar direcciones IPv6, también debe proporcionar compatibilidad con DNS de IPv6 y configurar registros de host DNS AAAA (conocidos como "Quad-A"). En las implementaciones en las que se usan IPv4 e IPv6, es mejor configurar y mantener registros de host A para IPv4 y host AAAA para IPv6. Incluso si la implementación se ha migrado por completo a IPv6, es posible que los registros de host DNS IPv4 sigan siendo necesarios cuando los usuarios externos sigan usando IPv4.



</div>

**Diagrama de flujo para determinar los requisitos de DNS**

![175782ac-363e-408a-912f-8991bf152970](images/Gg398758.175782ac-363e-408a-912f-8991bf152970(OCS.15).jpg "175782ac-363e-408a-912f-8991bf152970")

<div>


> [!IMPORTANT]  
> De forma predeterminada, el nombre de equipo de un equipo que no está unido a un dominio es un nombre de host, no un nombre de dominio completo (FQDN). El generador de topologías usa FQDN, no nombres de host. Así pues, debe configurar un sufijo de DNS en el nombre del equipo para poder implementarlo como servidor perimetral no incorporado a un dominio. <STRONG>Utilice únicamente caracteres estándar </STRONG> (A–Z, a–z, 0–9 y guiones) cuando asigne los nombres de dominio completo de sus servidores Lync, servidores perimetrales y grupos de servidores. No utilice caracteres Unicode ni de subrayado. Los DNS externos y las entidades de certificación públicas no admiten caracteres que no sean estándar en un nombre de dominio completo (es decir, cuando el FQDN se debe asignar al nombre de sujeto en el certificado). Para obtener más información, consulte <A href="lync-server-2013-configure-dns-host-records.md">configure DNS host Records for Lync Server 2013</A>



</div>

<div>

## <a name="how-lync-clients-locate-services"></a>Cómo localizan los clientes Lync Services

Microsoft Lync 2010, Lync 2013 y Lync Mobile son similares en la forma en que el cliente encuentra y obtiene acceso a los servicios en Lync Server 2013. La excepción más importante es la aplicación Lync de la tienda Windows que usa un proceso de ubicación del servicio diferente. En esta sección se detallan dos escenarios de cómo los clientes localizan los servicios, primero el método tradicional que usa una serie de registros de host y de host, segundo usando solo los registros del servicio Detección automática. Las actualizaciones acumulativas de los clientes de escritorio cambian el proceso de ubicación de DNS de Lync Server 2010 para todos los clientes, el proceso de consulta DNS sigue hasta que se devuelve una consulta correcta o se agota la lista de posibles registros DNS, y se devuelve el error final al cliente.

Para todos los clientes **excepto** para la aplicación Lync de la tienda Windows durante la búsqueda de DNS, los registros SRV se consultan y devuelven al cliente en el siguiente orden:

1.  lyncdiscoverinternal. \<domain\>     Registro a (host) para el servicio de detección automática en los servicios Web internos

2.  lyncdiscover. \<domain\>     Registro a (host) para el servicio de detección automática en los servicios web externos

3.  \_sipinternaltls. \_ TCP. \<domain\>     Registro SRV (localizador de servicios) para conexiones TLS internas

4.  \_sipinternal. \_ TCP. \<domain\>     Registro SRV (localizador de servicios) para conexiones TCP internas (se realiza solo si se permite TCP)

5.  \_SIP. \_ TLS. \<domain\>     Registro SRV (localizador de servicios) para conexiones TLS externas

6.  sipinternal. \<domain\>     Registro a (host) para el director o el grupo de servidores front-end, que solo se pueda resolver en la red interna

7.  SIP. \<domain\>     Registro a (host) para el grupo de servidores front-end o el director de la red interna, o el servicio perimetral de acceso cuando el cliente es externo

8.  sipexternal. \<domain\>     Registro a (host) para el servicio perimetral de acceso cuando el cliente es externo

La aplicación Lync de la tienda Windows cambia el proceso por completo porque usa dos registros:

1.  lyncdiscoverinternal. \<domain\>     Registro a (host) para el servicio de detección automática en los servicios Web internos

2.  lyncdiscover. \<domain\>     Registro a (host) para el servicio de detección automática en los servicios web externos

No hay ninguna reserva para los otros tipos de registros.

La diferencia entre los métodos usados para los clientes más recientes en comparación con los clientes anteriores es que el servicio de detección automática se convierte en el método preferido para buscar todos los servicios.

Cuando una conexión se realiza correctamente, el servicio Detección automática devuelve todas las direcciones URL de servicios web para el grupo principal del usuario, incluido el servicio de movilidad (conocido como MCX por el directorio virtual creado para el servicio en IIS), las direcciones URL de Microsoft Lync Web App y Web Scheduler. En cambio, las direcciones URL interna y externa de Mobility Service están asociadas con el FQDN externo de los servicios web. Por lo tanto, independientemente de si un dispositivo móvil es interno o externo a la red, el dispositivo siempre se conecta al servicio de movilidad de forma externa a través del proxy inverso.

Si se instalaron las actualizaciones acumulativas de Lync Server 2013: febrero de 2013, el servicio de detección automática también devuelve referencias a Internal/UCWA, external/UCWA y UCWA. Estas entradas se refieren al componente web de la API web de comunicaciones unificadas (UCWA). Actualmente, solo se utiliza la entrada UCWA y se proporciona una referencia a una dirección URL para el componente Web. UCWA usa los clientes móviles de Lync 2013 en lugar del servicio de movilidad MCX que usan los clientes móviles de Lync 2010.

<div>


> [!NOTE]  
> Al crear registros SRV, es importante recordar que deben apuntar a un registro DNS A y AAAA (si se usa direccionamiento IPv6) en el mismo dominio en el que se crea el registro SRV de DNS. Por ejemplo, si el registro SRV está en contoso.com, el registro a y AAAA (si está usando direccionamiento IPv6) al que apunta no puede estar en fabrikam.com.



</div>

<div>


> [!TIP]  
> La configuración predeterminada es dirigir todo el tráfico de clientes móviles a través del sitio externo. Puede modificar la configuración para que devuelva solo la dirección URL interna, si es más preferible para sus requisitos. Con esta configuración, los usuarios pueden usar aplicaciones móviles de Lync en sus dispositivos móviles solo cuando están dentro de la red corporativa. Para definir esta configuración, use el cmdlet <STRONG>set-CsMcxConfiguration</STRONG> .



</div>

<div>


> [!NOTE]  
> Aunque las aplicaciones móviles también pueden conectarse a otros servicios de Lync Server 2013, como el servicio de libreta de direcciones, las solicitudes web internas de aplicaciones móviles van al FQDN de Web externo solo para el servicio de movilidad. Otras solicitudes de servicios, como las solicitudes de la libreta de direcciones, no requieren esta configuración.



</div>

Los dispositivos móviles admiten la detección manual de servicios. En este caso, cada usuario debe configurar los parámetros del dispositivo móvil con las URL internas y externas completas del servicio Detección automática, incluyendo el protocolo y la ruta de acceso, de la manera siguiente:

  - https:// \<ExtPoolFQDN\> /Autodiscover/autodiscoverservice.SVC/root para acceso externo

  - https:// \<IntPoolFQDN\> /AutoDiscover/AutoDiscover.SVC/root para el acceso interno

Le recomendamos que use la detección automática en lugar de la detección manual. Sin embargo, la configuración manual puede ser útil para solucionar problemas de conectividad de dispositivos móviles.

</div>

<div>

## <a name="configuring-split-brain-dns-with-lync-server"></a>Configuración de Split-Brain DNS con Lync Server

El DNS de cerebro dividido se conoce por una serie de nombres, por ejemplo, DNS dividido o DNS de horizonte dividido. Simplemente, describe una configuración de DNS en la que hay dos zonas de DNS con el mismo espacio de nombres, pero solo las solicitudes de servicios de zona DNS son internas y las solicitudes de otros servicios de zona DNS son solo externas. No obstante, muchos de los registros SRV y registros A de DNS que contiene el DNS interno no se incluirán en el DNS externo, y viceversa. En los casos en los que el mismo registro DNS existe en el DNS interno y externo (por ejemplo, www.contoso.com), la dirección IP devuelta será distinta en función de la ubicación (interna o externa) en la que se inició la consulta.

<div>


> [!IMPORTANT]  
> Actualmente, Split-Brain DNS no es compatible para la movilidad, o más concretamente, los registros DNS LyncDiscover y LyncDiscoverInternal. LyncDiscover debe definirse en un servidor DNS externo y LyncDiscoverInternal debe definirse en un servidor DNS interno.



</div>

Para los fines de estos temas, se usará el término DNS de cerebro dividido.

Si va a configurar DNS de horizonte dividido, a continuación se incluye un resumen de los tipos de registros DNS necesarios para cada zona. Para obtener más información, consulte [escenarios para el acceso de usuarios externos en Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md).

**DNS interno:**

  - Contiene una zona DNS llamada contoso.com sobre la cual es autoritativo

  - La zona contoso.com interna contiene:
    
      - DNS A y AAAA (si usa direccionamiento IPv6) y registros SRV para la configuración automática de clientes de Lync Server 2013 interna (opcional)
    
      - DNS A y AAAA (si está usando direccionamiento IPv6) o registros CNAME para la detección automática de servicios Web de Lync Server 2013 (opcional)
    
      - Los registros de DNS A y AAAA (si está usando direccionamiento IPv6) para el nombre del grupo de servidores front-end, el nombre del grupo de directores o el director y todos los servidores internos que ejecutan Lync Server 2013 en la red corporativa
    
      - Registros de DNS A y AAAA (si está usando direccionamiento IPv6) para la interfaz interna perimetral de cada servidor perimetral de Lync Server 2013 en la red perimetral
    
      - Registros de DNS A y AAAA (si está usando direccionamiento IPv6) para la interfaz interna de cada servidor proxy inverso en la red perimetral (opcional para la administración del proxy inverso)
    
      - Todas las interfaces perimetrales internas del servidor perimetral 2013 de Lync Server en la red perimetral usan la zona DNS interna para resolver las consultas a contoso.com
    
      - Todos los servidores que ejecutan Lync Server 2013 y los clientes que ejecutan Lync 2013 en la red corporativa punto a los servidores DNS internos para resolver las consultas a contoso.com, o el uso del archivo hosts en cada servidor perimetral y los registros de la lista A y AAAA (si está usando direccionamiento IPv6) para el servidor del próximo salto, específicamente el director o VIP de Director, VIP del grupo o servidor Standard Edition

**DNS externo:**

  - Contiene una zona DNS llamada contoso.com sobre la cual es autoritativo

  - La zona contoso.com externa contiene:
    
      - DNS A y AAAA (si está usando direccionamiento IPv6) y registros SRV para la configuración automática de clientes de Lync Server 2013 (opcional)
    
      - DNS A y AAAA (si está usando direccionamiento IPv6) o registros CNAME para la detección automática de servicios Web de Lync Server 2013 para su uso con la movilidad
    
      - DNS A y AAAA (si está usando direccionamiento IPv6) y los registros SRV para la interfaz perimetral externa de cada servidor de Lync Server 2013, servidor perimetral o dirección IP virtual (VIP) del equilibrador de carga de hardware en la red perimetral
    
      - Registros de DNS A y AAAA (si está usando direccionamiento IPv6) para la interfaz externa del servidor de proxy inverso o VIP para un grupo de servidores de proxy inverso en la red perimetral

</div>

<div>

## <a name="automatic-configuration-without-split-brain-dns"></a>Configuración automática sin DNS de horizonte dividido

Mediante el uso de DNS de horizonte dividido, un usuario de Lync Server 2013 que inicie sesión internamente puede aprovechar la configuración automática si la zona DNS interna contiene un \_ sipinternaltls. \_ registro SRV de TCP para cada dominio SIP en uso. Sin embargo, si no usa DNS de horizonte dividido, la configuración automática interna de clientes que ejecutan Lync no funcionará a menos que se implemente una de las soluciones descritas en más adelante en esta sección. Esto se debe a que Lync Server 2013 requiere que el URI del SIP del usuario se corresponda con el dominio del grupo de servidores front-end designado para la configuración automática. Este es también el caso de las versiones anteriores de Communicator.

Por ejemplo, si tiene dos dominios SIP en uso, se necesitarán los registros de servicio DNS (SRV) siguientes:

  - Si un usuario inicia sesión como bob@contoso.com, el siguiente registro SRV funcionará para la configuración automática porque el dominio SIP del usuario (contoso.com) coincide con el dominio del grupo de servidores front-end de configuración automática):
    
     \_sipinternaltls. \_ tcp.contoso.com. 86400 IN SRV 0 0 5061 pool01.contoso.com

  - Si un usuario inicia sesión como alice@fabrikam.com, el siguiente registro SRV de DNS funcionará para la configuración automática del segundo dominio SIP.
    
     \_sipinternaltls. \_ tcp.fabrikam.com. 86400 IN SRV 0 0 5061 pool01.fabrikam.com

Para la comparación, si un usuario inicia sesión como tim@litwareinc.com, el siguiente registro SRV de DNS no funcionará para la configuración automática, porque el dominio SIP del cliente (litwareinc.com) no coincide con el dominio en el que se encuentra el grupo de servidores (fabrikam.com):

 \_sipinternaltls. \_ tcp.litwareinc.com. 86400 IN SRV 0 0 5061 pool01.fabrikam.com

Si la configuración automática es necesaria para los clientes que ejecutan Lync, seleccione una de las siguientes opciones:

  - Objetos de directiva de **Grupo**     Use objetos de directiva de grupo (GPO) para rellenar los valores de servidor correctos.
    
    <div>
    

    > [!NOTE]  
    > Esta opción no habilita la configuración automática, pero automatiza el proceso de configuración manual, de modo que si se usa este enfoque, no se requerirán los registros SRV asociados con la configuración automática.

    
    </div>

  - **Coincidencia de zona interna**     Cree una zona en el DNS interno que coincida con la zona DNS externa (por ejemplo, contoso.com) y cree registros de DNS A y AAAA (si está usando direccionamiento IPv6) correspondientes al grupo de Lync Server 2013 que se usa para la configuración automática. Por ejemplo, si un usuario se hospeda en pool01.contoso.net pero inicia sesión en Lync como bob@contoso.com, cree una zona de DNS interna denominada contoso.com y dentro de ella, cree un registro de DNS A y AAAA (si se usa el direccionamiento IPv6) para pool01.contoso.com.

  - Zona interna de **punto de anclaje**     Si está creando una zona completa en el DNS interno no es una opción, puede crear zonas de punto de anclaje (es decir, dedicada) que correspondan a los registros SRV necesarios para la configuración automática y rellenar dichas zonas con dnscmd.exe. Dnscmd.exe es obligatorio porque la interfaz de usuario de DNS no admite la creación de zonas designadas. Por ejemplo, si el dominio SIP es contoso.com y dispone de un grupo de servidores front-end llamado pool01 que contiene dos servidores front-end, necesitará los siguientes registros A y zonas designadas en el DNS interno:
    
        dnscmd . /zoneadd _sipinternaltls._tcp.contoso.com. /dsprimary
        dnscmd . /recordadd _sipinternaltls._tcp.contoso.com. @ SRV 0 0 5061 pool01.contoso.com.
        dnscmd . /zoneadd pool01.contoso.com. /dsprimary
        dnscmd . /recordadd pool01.contoso.com. @ A 192.168.10.90
        dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
        dnscmd . /recordadd pool01.contoso.com. @ A 192.168.10.91 
        dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
    
    Si su entorno contiene un segundo dominio SIP (por ejemplo, fabrikam.com), necesitará los siguientes registros A y zonas designadas en el DNS interno:
    
        dnscmd . /zoneadd _sipinternaltls._tcp.fabrikam.com. /dsprimary
        dnscmd . /recordadd _sipinternaltls._tcp.fabrikam.com. @ SRV 0 0 5061 pool01.fabrikam.com.
        dnscmd . /zoneadd pool01.fabrikam.com. /dsprimary
        dnscmd . /recordadd pool01.fabrikam.com. @ A 192.168.10.90
        dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
        dnscmd . /recordadd pool01.fabrikam.com. @ A 192.168.10.91
        dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>

<div>


> [!NOTE]  
> El FQDN del grupo de servidores front-end aparece dos veces, pero con dos direcciones IP distintas. Esto se debe a que se usa el equilibrio de carga de DNS, pero si se usara el equilibrio de carga de hardware, solo habría una entrada de grupo de servidores front-end. Asimismo, los valores de FQDN del grupo de servidores front-end cambian entre el ejemplo de contoso.com y el ejemplo de fabrikam.com, pero las direcciones IP permanecen iguales. Esto se debe a que los usuarios que inician sesión desde cualquiera de los dominios SIP, usan el mismo grupo de servidores front-end para la configuración automática.



</div>

Para obtener más información, consulte el artículo del blog DMTF "configuración automática de Communicator y DNS de Split-Brain" en [https://go.microsoft.com/fwlink/p/?linkId=200707](https://go.microsoft.com/fwlink/p/?linkid=200707) .

<div>


> [!NOTE]  
> El contenido de cada blog y su dirección URL están sujetos a cambio sin previo aviso.



</div>

</div>

<div>

## <a name="configuring-the-domain-name-system-dns-for-disaster-recovery"></a>Configuración del sistema de nombres de dominio (DNS) para la recuperación ante desastres

Para configurar DNS para redirigir el tráfico web de Lync Server 2013 a los sitios de recuperación ante desastres y conmutación por error, debe usar un proveedor de DNS que admita GeoDNS. Puede configurar los registros DNS para que admitan la recuperación ante desastres, de modo que las características que usan servicios web continúen incluso si hay un grupo de servidores front-end completo que deja de funcionar. Esta característica de recuperación ante desastres admite las direcciones URL sencillas de detección automática (URL de Lyncdiscover), de reunirse y de acceso telefónico.

Se definen y configuran registros adicionales de host DNS (A y AAAA si se usa IPv6) para la resolución interna y externa de servicios web en su proveedor de GeoDNS. Los siguientes detalles dan por sentado que los grupos emparejados, geográficamente dispersos y GeoDNS compatibles con el proveedor con DNS de operación por rondas, o que están configurados para usar Grupo1 como principal, y conmutan por error a grupo2 en caso de pérdida de comunicaciones o error de hardware.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Registro GeoDNS (ejemplo)</th>
<th>Registros de grupo (ejemplo)</th>
<th>Registros CNAME (ejemplo)</th>
<th>Configuración de DNS (seleccione una opción)</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Meet-int.geolb.contoso.com</p></td>
<td><p>Pool1InternalWebFQDN.contoso.com</p>
<p>Pool2InternalWebFQDN.contoso.com</p></td>
<td><p>Alias Meet.contoso.com a Pool1InternalWebFQDN.contoso.com</p>
<p>Alias Meet.contoso.com a Pool2InternalWebFQDN.contoso.com</p></td>
<td><p>Round Robin entre grupos</p>
<p>Usar principal, conectar con secundario si se produce un error</p></td>
</tr>
<tr class="even">
<td><p>Meet-ext.geolb.contoso.com</p></td>
<td><p>Pool1ExternalWebFQDN.contoso.com</p>
<p>Pool2ExternalWebFQDN.contoso.com</p></td>
<td><p>Alias Meet.contoso.com a Pool1ExternalWebFQDN.contoso.com</p>
<p>Alias Meet.contoso.com a Pool2ExternalWebFQDN.contoso.com</p></td>
<td><p>Round Robin entre grupos</p>
<p>Usar principal, conectar con secundario si se produce un error</p></td>
</tr>
<tr class="odd">
<td><p>Dialin-int.geolb.contoso.com</p></td>
<td><p>Pool1InternalWebFQDN.contoso.com</p>
<p>Pool2InternalWebFQDN.contoso.com</p></td>
<td><p>Alias Dialin.contoso.com a Pool1InternalWebFQDN.contoso.com</p>
<p>Alias Dialin.contoso.com a Pool2InternalWebFQDN.contoso.com</p></td>
<td><p>Round Robin entre grupos</p>
<p>Usar principal, conectar con secundario si se produce un error</p></td>
</tr>
<tr class="even">
<td><p>Dialin-ext.geolb.contoso.com</p></td>
<td><p>Pool1ExternalWebFQDN.contoso.com</p>
<p>Pool2ExternalWebFQDN.contoso.com</p></td>
<td><p>Alias Dialin.contoso.com a Pool1ExternalWebFQDN.contoso.com</p>
<p>Alias Dialin.contoso.com a Pool2ExternalWebFQDN.contoso.com</p></td>
<td><p>Round Robin entre grupos</p>
<p>Usar principal, conectar con secundario si se produce un error</p></td>
</tr>
<tr class="odd">
<td><p>Lyncdiscoverint-int.geolb.contoso.com</p></td>
<td><p>Pool1InternalWebFQDN.contoso.com</p>
<p>Pool2InternalWebFQDN.contoso.com</p></td>
<td><p>Alias Lyncdiscoverinternal.contoso.com a Pool1InternalWebFQDN.contoso.com</p>
<p>Alias Lyncdiscoverinternal.contoso.com a Pool2InternalWebFQDN.contoso.com</p></td>
<td><p>Round Robin entre grupos</p>
<p>Usar principal, conectar con secundario si se produce un error</p></td>
</tr>
<tr class="even">
<td><p>Lyncdiscover-ext.geolb.contoso.com</p></td>
<td><p>Pool1ExternalWebFQDN.contoso.com</p>
<p>Pool2ExternalWebFQDN.contoso.com</p></td>
<td><p>Alias Lyncdiscover.contoso.com a Pool1ExternalWebFQDN.contoso.com</p>
<p>Alias Lyncdiscover.contoso.com a Pool2ExternalWebFQDN.contoso.com</p></td>
<td><p>Round Robin entre grupos</p>
<p>Usar principal, conectar con secundario si se produce un error</p></td>
</tr>
<tr class="odd">
<td><p>Scheduler-int.geolb.contoso.com</p></td>
<td><p>Pool1InternalWebFQDN.contoso.com</p>
<p>Pool2InternalWebFQDN.contoso.com</p></td>
<td><p>Alias Scheduler.contoso.com a Pool1InternalWebFQDN.contoso.com</p>
<p>Alias Scheduler.contoso.com a Pool2InternalWebFQDN.contoso.com</p></td>
<td><p>Round Robin entre grupos</p>
<p>Usar principal, conectar con secundario si se produce un error</p></td>
</tr>
<tr class="even">
<td><p>Scheduler-ext.geolb.contoso.com</p></td>
<td><p>Pool1ExternalWebFQDN.contoso.com</p>
<p>Pool2ExternalWebFQDN.contoso.com</p></td>
<td><p>Alias Scheduler.contoso.com a Pool1ExternalWebFQDN.contoso.com</p>
<p>Alias Scheduler.contoso.com a Pool2ExternalWebFQDN.contoso.com</p></td>
<td><p>Round Robin entre grupos</p>
<p>Usar principal, conectar con secundario si se produce un error</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="dns-load-balancing"></a>Equilibrio de carga de DNS

El equilibrio de carga de DNS suele implementarse en el nivel de la aplicación. La aplicación (por ejemplo, un cliente que ejecuta Lync), intenta conectarse a un servidor de un grupo de servidores conectándose a una de las direcciones IP devueltas desde las direcciones IP a y AAAA (si se usa el direccionamiento IPv6) para el nombre de dominio completo (FQDN) del grupo de servidores.

Por ejemplo, si hay tres servidores front-end en un grupo de servidores denominado pool01.contoso.com, pasará lo siguiente:

  - Clientes que ejecutan el DNS de consulta de Lync para pool01.contoso.com. La consulta devuelve tres direcciones IP y las almacena en caché de la siguiente manera (no necesariamente en el orden indicado):
    
    pool01.contoso.com 192.168.10.90
    
    pool01.contoso.com 192.168.10.91
    
    pool01.contoso.com 192.168.10.92

  - El cliente intenta establecer una conexión de protocolo de control de transmisión (TCP) con una de las direcciones IP. Si no funciona, lo intentará con la siguiente dirección IP almacenada en caché.

  - Si la conexión TCP se realiza correctamente, el cliente negocia TLS para conectarse al registrador principal en pool01.contoso.com.

  - Si el cliente prueba todas las entradas almacenadas en caché sin establecer una conexión correctamente, se notificará al usuario que no hay servidores disponibles que ejecuten Lync Server 2013 en este momento.

<div>


> [!NOTE]  
> El equilibrio de carga basado en DNS es distinto al round robin de DNS (DNS RR), que normalmente hace referencia al equilibrio de carga usando el DNS para proporcionar un orden distinto de direcciones IP correspondientes a los servidores de un grupo de servidores. Por lo general, DNS RR solo habilita la distribución de carga, pero no habilita la conmutación por error. Por ejemplo, si la conexión a la dirección IP devuelta por la consulta de DNS A y AAAA (si está usando direccionamiento IPv6) produce un error, se producirá un error en la conexión. Por tanto, el round robin de DNS por sí solo es menos fiable que el equilibrio de carga basado en DNS. Puede usar el round robin de DNS junto con el equilibrio de carga de DNS.



</div>

El equilibrio de carga de DNS se usa para lo siguiente:

  - Equilibrio de carga de SIP de servidor a servidor a los servidores perimetrales

  - Equilibrar la carga de aplicaciones de servicios de aplicaciones de comunicaciones unificadas (UCAS, Unified Communications Application Services), como Operador automático de conferencia, Grupo de respuesta y Estacionamiento de llamadas.

  - Impedir el establecimiento de nuevas conexiones con aplicaciones UCAS (proceso también conocido como "purga").

  - Equilibrar la carga de todo el tráfico de servidor a cliente entre clientes y servidores perimetrales

El equilibrio de carga de DNS no puede usarse para:

  - Tráfico web de cliente a servidor a servidores de director o front-end

Equilibrio de carga de DNS y tráfico federado:

Si una consulta SRV de DNS devuelve varios registros DNS, el servicio perimetral de acceso siempre elige el registro SRV de DNS con la prioridad numérica más baja y el peso numérico más alto. El documento del equipo de la tarea de ingeniería de Internet "un RR de DNS para especificar la ubicación de los servicios (DNS SRV)" <http://www.ietf.org/rfc/rfc2782.txt> especifica que si hay varios registros SRV de DNS definidos, se usa primero la prioridad y luego el peso. Por ejemplo, el registro A de SRV de DNS tiene un peso de 20 y una prioridad de 40 y el registro B de SRV de DNS tiene un peso de 10 y una prioridad de 50. Se seleccionará el registro SRV de DNS A con prioridad 40. Las siguientes reglas se aplican a la selección de registros SRV de DNS:

  - La prioridad se considera en primer lugar. Un cliente debe intentar ponerse en contacto con el host de destino definido por el registro SRV de DNS con la prioridad con el número más bajo que pueda llegar. Los destinos con la misma prioridad deben probarse en el orden definido por el campo weight.

  - El campo peso especifica un peso relativo para las entradas con la misma prioridad. A los pesos más grandes se les debe dar una probabilidad proporcionalmente mayor de ser seleccionados. Los administradores de DNS deben usar Weight 0 cuando no hay ninguna selección de servidor que hacer. En presencia de registros que contienen pesos mayores que 0, los registros con peso 0 deben tener una probabilidad muy pequeña de ser seleccionados.

Si se devuelven varios registros SRV de DNS con la misma prioridad y el mismo peso, el servicio perimetral de acceso seleccionará el registro SRV que se recibió primero del servidor DNS.

</div>

</div>

<span> </span>

</div>

</div>

</div>

