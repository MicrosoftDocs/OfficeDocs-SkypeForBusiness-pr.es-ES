---
title: 'Lync Server 2013: Determinar los requisitos DNS'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Determine DNS requirements
ms:assetid: 95777017-6282-44c0-a685-f246af0501b4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398758(v=OCS.15)
ms:contentKeyID: 48184839
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e299f138a28ba4863250d2e0be1f31f705f4a173
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34835483"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="determine-dns-requirements-for-lync-server-2013"></a>Determinar los requisitos DNS para Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-22_

Use el diagrama de flujo siguiente para determinar los requisitos del Sistema de nombres de dominio (DNS). Cambios para las actualizaciones acumulativas para Lync Server 2013:2013 de febrero se indican dónde se aplican.

<div>


> [!IMPORTANT]  
> Microsoft Lync Server 2013 admite el uso de direcciones IPv6. Para usar direcciones IPv6, también necesita proporcionar compatibilidad para DNS IPv6 y configurar registros AAAA de host DNS (conocidos como “cuádruple A”). En implementaciones en las que se están usando IPv4 e IPv6, es mejor configurar y mantener registros A de host para IPv4 y AAAA de host para IPv6. Aunque su implementación haya realizado una transición completa a IPv6, los registros de host DNS IPv4 todavía pueden ser necesarios cuando los usuarios externos estén usando todavía IPv4.



</div>

**Diagrama de flujo para determinar los requisitos de DNS**

![175782ac-363e-408A-912f-8991bf152970] (images/Gg398758.175782ac-363e-408a-912f-8991bf152970(OCS.15).jpg "175782ac-363e-408A-912f-8991bf152970")

<div>


> [!IMPORTANT]  
> De forma predeterminada, el nombre de equipo de un equipo que no está unido a un dominio es un nombre de host, no un nombre de dominio completo (FQDN). El generador de topología usa FQDN, no nombres de host. Por lo tanto, debe configurar un sufijo DNS en el nombre del equipo para implementarse como servidor perimetral que no está unido a un dominio. <STRONG>Utilice únicamente caracteres estándar</STRONG> (incluyendo A–Z, a–z, 0–9 y guiones) a la hora de asignar FQDN de sus Lync Server, servidores perimetrales y grupos. No utilice caracteres Unicode ni de subrayado. Los caracteres no estándar en una dirección URL o un FQDN a menudo no son compatibles con DNS externas y CA públicas (es decir, cuando el FQDN debe asignarse al SN en el certificado). Para obtener más información, vea <A href="lync-server-2013-configure-dns-host-records.md">configurar registros de host DNS para Lync Server 2013</A>



</div>

<div>

## <a name="how-lync-clients-locate-services"></a>Cómo los clientes de Lync encuentran los servicios

Microsoft Lync 2010, Lync 2013 y Lync Mobile son similares en la forma en que el cliente encuentra y obtiene acceso a los servicios en Lync Server 2013. La excepción más importante es la aplicación de la tienda Windows de Lync que usa un proceso de ubicación de servicio diferente. En esta sección se describen dos escenarios en los que los clientes localizan servicios: el primero es el método tradicional que usa una serie de SRV y registros de host A y el segundo usa únicamente los registros del servicio de detección automática. Las actualizaciones acumulativas de los clientes de escritorio cambian el proceso de ubicación DNS de Lync Server 2010 para todos los clientes, el proceso de consulta DNS continúa hasta que se devuelve una consulta correcta, o bien se agota la lista de posibles registros DNS, y se devuelve el error final a el cliente.

Para todos los clientes **excepto** para la aplicación de la tienda Windows de Lync durante la búsqueda de DNS, los registros SRV se consultan y devuelven al cliente en el siguiente orden:

1.  lyncdiscoverinternal. \<Registro\> a (host) de dominio para el servicio de detección automática en los servicios Web internos

2.  lyncdiscover. \<Registro\> a (host) de dominio para el servicio de detección automática en los servicios web externos

3.  \_sipinternaltls. \_TCP. \<Registro\> SRV de dominio (Ubicador de servicio) para conexiones TLS internas

4.  \_sipinternal. \_TCP. \<Registro\> SRV de dominio (Ubicador de servicio) para conexiones TCP internas (se realiza solo si se permite TCP)

5.  \_SIP. \_TLS. \<Registro\> SRV de dominio (Ubicador de servicio) para conexiones TLS externas

6.  sipinternal. \<Registro\> a (host) de dominio para el director o grupo de servidores front-end, que solo se pueda resolver en la red interna

7.  SIP. \<Registro\> a (host) de dominio para el grupo de servidores front-end o director de la red interna, o el servicio perimetral de acceso cuando el cliente es externo

8.  sipexternal. \<Registro\> a (host) de dominio para el servicio perimetral de acceso cuando el cliente es externo

La aplicación de la tienda Windows de Lync cambia el proceso por completo porque usa dos registros:

1.  lyncdiscoverinternal. \<Registro\> a (host) de dominio para el servicio de detección automática en los servicios Web internos

2.  lyncdiscover. \<Registro\> a (host) de dominio para el servicio de detección automática en los servicios web externos

No hay reserva para los otros tipos de registros.

La diferencia entre los métodos usados para los clientes más recientes en comparación con los clientes más antiguos es que el servicio de detección automática se convierte en el método preferido para localizar todos los servicios.

Cuando una conexión se realiza correctamente, el servicio Detección automática devuelve todas las direcciones URL de servicios web para el grupo de hogar del usuario, incluido el servicio de movilidad (conocido como MCX por el directorio virtual creado para el servicio en IIS), Microsoft Lync Web App y las direcciones URL del programador web. Pero, la dirección URL interna del servicio de movilidad y la dirección URL externa del servicio de movilidad se asocian al FQDN externo de los servicios web. Por lo tanto, independientemente de si un dispositivo móvil es interno o externo a la red, el dispositivo siempre se conecta al servicio de movilidad de forma externa a través del proxy inverso.

Si se han instalado las actualizaciones acumulativas de Lync Server 2013:2013 de febrero, el servicio de detección automática también devuelve referencias a Internal/UCWA, external/UCWA y UCWA. Estas entradas hacen referencia al componente web de la API web de comunicaciones unificadas (UCWA). Actualmente solo se usa la entrada de UCWA y proporciona una referencia a una URL para el componente web. UCWA lo usan los clientes móviles de Lync 2013 en lugar del servicio de movilidad MCX que usan los clientes móviles de Lync 2010.

<div>


> [!NOTE]  
> A la hora de crear registros SRV, es importante recordar que necesitan señalar a un registro A y AAAA (si está usando direccionamiento IPv6) de DNS del mismo dominio donde se crea el registro SRV de DNS. Por ejemplo, si el registro SRV se encuentra en contoso.com, los registros a y AAAA (si usa IPv6 Addressing) no pueden estar en fabrikam.com.



</div>

<div>


> [!TIP]  
> La configuración predeterminada dirige todo el tráfico de clientes móviles a través del sitio externo. Puede cambiar la configuración para devolver solamente la dirección URL interna, si esto se adapta más a sus requisitos. Con esta configuración, los usuarios pueden usar aplicaciones móviles de Skype Empresarial en sus dispositivos móviles solo cuando están dentro de la red corporativa. Para definir esta configuración, use el cmdlet <STRONG>Set-CsMcxConfiguration</STRONG>.



</div>

<div>


> [!NOTE]  
> Aunque las aplicaciones móviles también pueden conectarse a otros servicios de Lync Server 2013, como el servicio de libreta de direcciones, las solicitudes web internas de la aplicación móvil van al FQDN de la web externa solo para el servicio de movilidad. Otras solicitudes de servicios, como las solicitudes de la libreta de direcciones, no requieren esta configuración.



</div>

Los dispositivos móviles admiten la detección manual de servicios. En este caso, cada usuario necesita configurar los parámetros del dispositivo móvil con los URI internos y externos completos del servicio de detección automática, incluso el protocolo y la ruta de acceso, de la manera siguiente:

  - https://\<ExtPoolFQDN\>/Autodiscover/autodiscoverservice.SVC/root para acceso externo

  - https://\<IntPoolFQDN\>/AutoDiscover/AutoDiscover.SVC/root para acceso interno

Recomendamos que use la detección automática, en lugar de la detección manual. Pero, la configuración manual puede ser útil para solucionar problemas de conectividad de los dispositivos móviles.

</div>

<div>

## <a name="configuring-split-brain-dns-with-lync-server"></a>Configuración de DNS de horizonte dividido con Lync Server

El término DNS de horizonte dividido se conoce con varios nombres, por ejemplo, DNS dividido o DNS de partición de red. Sencillamente describe una configuración de DNS en la que existen dos zonas de DNS con el mismo espacio de nombre, pero una zona de DNS procesa solo las solicitudes internas y la otra solo las externas. Pero, muchos de los registros SRV y los registros A de DNS que contiene el DNS interno no se incluirán en el DNS externo, y viceversa. Además, en los casos en que el mismo registro de DNS existe tanto en el DNS interno como en el externo (por ejemplo, www.contoso.com), la dirección IP devuelta será distinta, en función de dónde (en el interior o en el exterior) se realice la consulta de DNS.

<div>


> [!IMPORTANT]  
> Actualmente, el DNS de horizonte dividido no es compatible con la movilidad o, más concretamente, con los registros de DNS LyncDiscover y LyncDiscoverInternal. LyncDiscover tiene que definirse en un servidor DNS externo y LyncDiscoverInternal tiene que definirse en un servidor DNS interno.



</div>

Aquí se utilizará el término DNS de horizonte dividido.

Si va a configurar DNS de horizonte dividido, en la siguiente área interna y externa encontrará un resumen de los tipos de registros de DNS necesarios para cada zona. Para obtener más información, vea [escenarios de acceso de usuarios externos en Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md).

**DNS interno:**

  - Contiene una zona de DNS llamada contoso.com sobre la que es autoritativo

  - La zona contoso.com interna contiene:
    
      - DNS A y AAAA (si está usando direccionamiento IPv6) y los registros SRV para la configuración automática del cliente de Lync Server 2013 (opcional)
    
      - DNS A y AAAA (si usa direccionamiento IPv6) o registros CNAME para el descubrimiento automático de los servicios Web de Lync Server 2013 (opcional)
    
      - DNS A y AAAA (si está usando direcciones IPv6) registros para el nombre del grupo de servidores front-end, el nombre del grupo o director y todos los servidores internos que ejecutan Lync Server 2013 en la red corporativa
    
      - DNS A y AAAA (si usa IPv6 Addressing) para la interfaz interna perimetral de cada servidor de Lync Server 2013, Edge en la red perimetral
    
      - Registros A y AAAA (si está usando direccionamiento IPv6) de DNS para la interfaz interna de cada servidor proxy inverso en la red perimetral (opcional para la administración del proxy inverso)
    
      - Todas las interfaces de borde interno del servidor perimetral 2013 de Lync Server en la red perimetral usan la zona DNS interna para resolver las consultas a contoso.com
    
      - Todos los servidores que ejecutan Lync Server 2013 y los clientes que ejecutan Lync 2013 en la red corporativa apuntan a los servidores DNS internos para resolver las consultas a contoso.com, o el uso del archivo hosts en cada servidor perimetral y los registros de lista a y AAAA (si usa IPv6 Addressing) para servidor del próximo salto, en concreto, el director o la dirección VIP del Director, la VIP del grupo frontal o el servidor Standard Edition

**DNS externo:**

  - Contiene una zona de DNS llamada contoso.com sobre la que es autoritativo

  - La zona contoso.com externa contiene:
    
      - DNS A y AAAA (si usa direccionamiento IPv6) y los registros SRV para la configuración automática del cliente de Lync Server 2013 (opcional)
    
      - DNS A y AAAA (si usa direccionamiento IPv6) o registros CNAME para el descubrimiento automático de los servicios Web de Lync Server 2013 para usarlos con la movilidad
    
      - DNS A y AAAA (si está usando direccionamiento IPv6) y los registros SRV para la interfaz externa perimetral de cada Lync Server 2013, servidor perimetral o IP virtual del equilibrador de carga de hardware (VIP) en la red perimetral
    
      - Registros A y AAAA (si está usando direccionamiento IPv6) de DNS para la interfaz externa del servidor proxy inverso o VIP para un grupo de servidores proxy inversos en la red perimetral

</div>

<div>

## <a name="automatic-configuration-without-split-brain-dns"></a>Configuración automática sin DNS de horizonte dividido

Con DNS de horizonte dividido, un usuario de Lync Server 2013 que inicia sesión internamente puede aprovechar la configuración automática si la zona DNS interna contiene un \_sipinternaltls. \_registro TCP SRV para cada dominio SIP en uso. Sin embargo, si no usa DNS dividido-Brain, la configuración automática interna de clientes que ejecutan Lync no funcionará a menos que se implemente una de las soluciones descritas en más adelante en esta sección. Esto se debe a que Lync Server 2013 requiere que el URI SIP del usuario coincida con el dominio del grupo de servidores front-end designado para la configuración automática. Este también es el caso de las versiones anteriores de Communicator.

Por ejemplo, si tiene dos dominios SIP en uso, se necesitarán los registros de servicio DNS (SRV) siguientes:

  - Si un usuario inicia sesión como bob@contoso.com, el registro SRV siguiente funcionará para la configuración automática porque el dominio SIP del usuario (contoso.com) coincide con el dominio del grupo de servidores front-end de configuración automática:
    
     \_sipinternaltls. \_TCP.contoso.com. 86400 IN SRV 0 0 5061 pool01.contoso.com

  - Si un usuario inicia sesión como alice@fabrikam.com, el siguiente registro SRV de DNS funcionará para la configuración automática del segundo dominio SIP.
    
     \_sipinternaltls. \_TCP.fabrikam.com. 86400 IN SRV 0 0 5061 pool01.fabrikam.com

En cambio, si un usuario inicia sesión como tim@litwareinc.com, el siguiente registro SRV de DNS no funcionará para la configuración automática, porque el dominio SIP del cliente (litwareinc.com) no coincide con el dominio donde se encuentra el grupo de servidores (fabrikam.com):

 \_sipinternaltls. \_TCP.litwareinc.com. 86400 IN SRV 0 0 5061 pool01.fabrikam.com

Si la configuración automática es necesaria para los clientes que ejecutan Lync, seleccione una de las siguientes opciones:

  - **Los objetos**   de directiva de grupo usan objetos de directiva de grupo (GPO) para rellenar los valores de servidor correctos.
    
    <div>
    

    > [!NOTE]  
    > Esta opción no habilita la configuración automática, pero automatiza el proceso de configuración manual, de modo que si se usa este enfoque, no se requerirán los registros SRV asociados con la configuración automática.

    
    </div>

  - **Zona interna de coincidencia**   cree una zona en el DNS interno que coincida con la zona DNS externa (por ejemplo, contoso.com) y cree registros de DNS a y AAAA (si usa direcciones IPv6) que correspondan al grupo de Lync Server 2013 usado para automático configuración. Por ejemplo, si un usuario se ha alojado en pool01.contoso.net pero inicia sesión en Lync como bob@contoso.com, cree una zona de DNS interna denominada contoso.com y dentro de ella, cree un registro DNS A y AAAA (si se usa el direccionamiento IPv6) para pool01.contoso.com.

  - **Zona interna de punto de ancla**   si está creando una zona completa en el DNS interno no es una opción, puede crear zonas de punto de ancla (es decir, dedicada) que se correspondan con los registros SRV necesarios para la configuración automática y rellenarlas zonas con dnscmd. exe. Dnscmd.exe es necesario porque la interfaz de usuario de DNS no admite la creación de zonas designadas. Por ejemplo, si el dominio SIP es contoso.com y dispone de un grupo de servidores front-end llamado pool01 que contiene dos servidores front-end, necesitará los siguientes registros A y las siguientes zonas designadas en el DNS interno:
    
        dnscmd . /zoneadd _sipinternaltls._tcp.contoso.com. /dsprimary
        dnscmd . /recordadd _sipinternaltls._tcp.contoso.com. @ SRV 0 0 5061 pool01.contoso.com.
        dnscmd . /zoneadd pool01.contoso.com. /dsprimary
        dnscmd . /recordadd pool01.contoso.com. @ A 192.168.10.90
        dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
        dnscmd . /recordadd pool01.contoso.com. @ A 192.168.10.91 
        dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
    
    Si su entorno contiene un segundo dominio SIP (por ejemplo, fabrikam.com), necesitará los siguientes registros A y las siguientes zonas designadas en el DNS interno:
    
        dnscmd . /zoneadd _sipinternaltls._tcp.fabrikam.com. /dsprimary
        dnscmd . /recordadd _sipinternaltls._tcp.fabrikam.com. @ SRV 0 0 5061 pool01.fabrikam.com.
        dnscmd . /zoneadd pool01.fabrikam.com. /dsprimary
        dnscmd . /recordadd pool01.fabrikam.com. @ A 192.168.10.90
        dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
        dnscmd . /recordadd pool01.fabrikam.com. @ A 192.168.10.91
        dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>

<div>


> [!NOTE]  
> El FQDN del grupo de servidores front-end aparece dos veces, pero con dos direcciones IP distintas. Esto es porque que se usa el equilibrio de carga de DNS, pero si se usara el equilibrio de carga de hardware, solo habría una única entrada de grupo de servidores front-end. Asimismo, los valores de FQDN del grupo de servidores front-end cambian entre el ejemplo de contoso.com y el ejemplo de fabrikam.com, pero las direcciones IP permanecen iguales. Esto se debe a que los usuarios que inician sesión desde cualquiera de los dominios SIP usan el mismo grupo de servidores front-end para la configuración automática.



</div>

Para obtener más información, consulte el artículo del blog de DMTF, "Communicator Automatic Configuration and split-brain [http://go.microsoft.com/fwlink/p/?linkId=200707](http://go.microsoft.com/fwlink/p/?linkid=200707)DNS", en.

<div>


> [!NOTE]  
> El contenido de los blogs y sus URL están sujetos a cambios sin previo aviso.



</div>

</div>

<div>

## <a name="configuring-the-domain-name-system-dns-for-disaster-recovery"></a>Configuración del sistema de nombres de dominio (DNS) para la recuperación ante desastres

Para configurar DNS de redirigir el tráfico web de Lync Server 2013 a los sitios de recuperación ante desastres y conmutación por error, debe estar usando un proveedor de DNS que admita GeoDNS. Puede configurar los registros DNS para que la web admita la recuperación ante desastres, de modo que las características que usan los servicios web continúen incluso si se interrumpe un grupo de servidores front-end completo. Esta característica de recuperación ante desastres admite direcciones URL sencillas de detección automática (URL de Lyncdiscover), de reunión y de acceso telefónico.

Los registros de host DNS adicionales (A y AAAA si se usa IPv6) se definen y se configuran para la resolución interna y externa de servicios web en su proveedor de GeoDNS. En la información siguiente se presupone que su proveedor admite grupos emparejados, geográficamente dispersos, y GeoDNS con round robin de DNS o configurados para usar Pool1 como grupo principal y conmutar por error a Pool2 en caso de pérdida de comunicaciones o error de hardware.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Registro de GeoDNS (ejemplo)</th>
<th>Registros del grupo (ejemplo)</th>
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
<td><p>Round robin entre grupos</p>
<p>Usa el principal; se conecta al secundario en caso de error</p></td>
</tr>
<tr class="even">
<td><p>Meet-ext.geolb.contoso.com</p></td>
<td><p>Pool1ExternalWebFQDN.contoso.com</p>
<p>Pool2ExternalWebFQDN.contoso.com</p></td>
<td><p>Alias Meet.contoso.com a Pool1ExternalWebFQDN.contoso.com</p>
<p>Alias Meet.contoso.com a Pool2ExternalWebFQDN.contoso.com</p></td>
<td><p>Round robin entre grupos</p>
<p>Usa el principal; se conecta al secundario en caso de error</p></td>
</tr>
<tr class="odd">
<td><p>Dialin-int.geolb.contoso.com</p></td>
<td><p>Pool1InternalWebFQDN.contoso.com</p>
<p>Pool2InternalWebFQDN.contoso.com</p></td>
<td><p>Alias Dialin.contoso.com a Pool1InternalWebFQDN.contoso.com</p>
<p>Alias Dialin.contoso.com a Pool2InternalWebFQDN.contoso.com</p></td>
<td><p>Round robin entre grupos</p>
<p>Usa el principal; se conecta al secundario en caso de error</p></td>
</tr>
<tr class="even">
<td><p>Dialin-ext.geolb.contoso.com</p></td>
<td><p>Pool1ExternalWebFQDN.contoso.com</p>
<p>Pool2ExternalWebFQDN.contoso.com</p></td>
<td><p>Alias Dialin.contoso.com a Pool1ExternalWebFQDN.contoso.com</p>
<p>Alias Dialin.contoso.com a Pool2ExternalWebFQDN.contoso.com</p></td>
<td><p>Round robin entre grupos</p>
<p>Usa el principal; se conecta al secundario en caso de error</p></td>
</tr>
<tr class="odd">
<td><p>Lyncdiscoverint-int.geolb.contoso.com</p></td>
<td><p>Pool1InternalWebFQDN.contoso.com</p>
<p>Pool2InternalWebFQDN.contoso.com</p></td>
<td><p>Alias Lyncdiscoverinternal.contoso.com a Pool1InternalWebFQDN.contoso.com</p>
<p>Alias Lyncdiscoverinternal.contoso.com a Pool2InternalWebFQDN.contoso.com</p></td>
<td><p>Round robin entre grupos</p>
<p>Usa el principal; se conecta al secundario en caso de error</p></td>
</tr>
<tr class="even">
<td><p>Lyncdiscover-ext.geolb.contoso.com</p></td>
<td><p>Pool1ExternalWebFQDN.contoso.com</p>
<p>Pool2ExternalWebFQDN.contoso.com</p></td>
<td><p>Alias Lyncdiscover.contoso.com a Pool1ExternalWebFQDN.contoso.com</p>
<p>Alias Lyncdiscover.contoso.com a Pool2ExternalWebFQDN.contoso.com</p></td>
<td><p>Round robin entre grupos</p>
<p>Usa el principal; se conecta al secundario en caso de error</p></td>
</tr>
<tr class="odd">
<td><p>Scheduler-int.geolb.contoso.com</p></td>
<td><p>Pool1InternalWebFQDN.contoso.com</p>
<p>Pool2InternalWebFQDN.contoso.com</p></td>
<td><p>Alias Scheduler.contoso.com a Pool1InternalWebFQDN.contoso.com</p>
<p>Alias Scheduler.contoso.com a Pool2InternalWebFQDN.contoso.com</p></td>
<td><p>Round robin entre grupos</p>
<p>Usa el principal; se conecta al secundario en caso de error</p></td>
</tr>
<tr class="even">
<td><p>Scheduler-ext.geolb.contoso.com</p></td>
<td><p>Pool1ExternalWebFQDN.contoso.com</p>
<p>Pool2ExternalWebFQDN.contoso.com</p></td>
<td><p>Alias Scheduler.contoso.com a Pool1ExternalWebFQDN.contoso.com</p>
<p>Alias Scheduler.contoso.com a Pool2ExternalWebFQDN.contoso.com</p></td>
<td><p>Round robin entre grupos</p>
<p>Usa el principal; se conecta al secundario en caso de error</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="dns-load-balancing"></a>Equilibrio de carga de DNS

El equilibrio de carga de DNS suele implementarse en la aplicación. La aplicación (por ejemplo, un cliente que ejecute Lync) intenta conectarse a un servidor de un grupo conectándose a una de las direcciones IP devueltas por el DNS a y AAAA (si se usa el direccionamiento IPv6) para el nombre de dominio completo del grupo (FQDN).

Por ejemplo, si hay tres servidores front-end en un grupo denominado pool01.contoso.com, pasará lo siguiente:

  - Los clientes que ejecutan DNS de consulta de Lync para pool01.contoso.com. La consulta devuelve tres direcciones IP y las almacena en caché como sigue (no necesariamente en este orden):
    
    pool01.contoso.com 192.168.10.90
    
    pool01.contoso.com 192.168.10.91
    
    pool01.contoso.com 192.168.10.92

  - Luego, el cliente intenta establecer una conexión del Protocolo de control de transmisión (TCP) con una de las direcciones IP. Si no funciona, lo intenta con la siguiente dirección IP almacenada en caché.

  - Si la conexión TCP se establece correctamente, el cliente negocia con el TLS para conectarse con el registrador principal en pool01.contoso.com.

  - Si el cliente prueba todas las entradas almacenadas en caché sin una conexión correcta, se notificará al usuario que no hay servidores que ejecuten Lync Server 2013 en este momento.

<div>


> [!NOTE]  
> El equilibrio de carga basado en DNS es distinto al round robin de DNS (RR de DNS), que normalmente hace referencia al equilibrio de carga usando el DNS para proporcionar un orden distinto de direcciones IP correspondientes a los servidores de un grupo de servidores. Por lo general, RR de DNS solo habilita la distribución de carga, pero no habilita la conmutación por error. Por ejemplo, si no se consigue establecer la conexión con una de las direcciones IP devueltas por la consulta A y AAAA (si está usando el direccionamiento IPv6) de DNS, la conexión será errónea. Por tanto, el round robin de DNS por sí solo es menos fiable que el equilibrio de carga basado en DNS. Puede usar el round robin de DNS junto con el equilibrio de carga de DNS.



</div>

El equilibrio de carga de DNS se usa para lo siguiente:

  - Equilibrar la carga SIP de servidor a servidor con los servidores perimetrales

  - Equilibrar la carga de aplicaciones de servicios de aplicaciones de comunicaciones unificadas (UCAS) como Operador automático de conferencia, Grupo de respuesta y Estacionamiento de llamadas

  - Impedir el establecimiento de nuevas conexiones con aplicaciones UCAS (proceso también conocido como "purga").

  - Equilibrar la carga de todo el tráfico desde el servidor al cliente entre clientes y servidores perimetrales

El equilibrio de carga de DNS no puede usarse para:

  - Tráfico web de cliente a servidor al director o a los servidores front-end

Equilibrio de carga de DNS y tráfico federado:

Si una consulta SRV de DNS devuelve varios registros de DNS, el servicio perimetral de acceso siempre selecciona el registro SRV de DNS con la prioridad numérica más baja y con el peso numérico más alto. El documento del grupo de tareas de ingeniería de Internet "un registro de registros de DNS para especificar la ubicación de <http://www.ietf.org/rfc/rfc2782.txt> los servicios (DNS SRV)" especifica que si hay varios registros SRV de DNS definidos, el primer uso de Priority y, a continuación, Weight. Por ejemplo, el registro A de SRV de DNS tiene un peso de 20 y una prioridad de 40, y el registro B de SRV de DNS tiene un peso de 10 y una prioridad de 50. Se seleccionará el registro A de SRV de DNS con una prioridad de 40. Las siguientes reglas se aplican a la selección de registros SRV de DNS:

  - La prioridad se considera primero. Un cliente TIENE QUE intentar contactar con el host de destino definido por el registro SRV de DNS con la menor prioridad numerada que pueda alcanzar. Los destinos con la misma prioridad NECESITAN intentarse siguiendo el orden definido por el campo de peso.

  - El campo de peso especifica un peso relativo para las entradas que tienen la misma prioridad. Es PRECISO que a los pesos más grandes se les otorgue una probabilidad proporcionalmente mayor para ser seleccionados. Los administradores de DNS TIENEN QUE usar el peso 0 cuando no hay ninguna selección de servidor que hacer. Cuando existen registros con pesos superiores a 0, los registros con peso 0 necesitan tener una oportunidad muy pequeña de ser elegidos.

Si se devuelven varios registros SRV de DNS con la misma prioridad y el mismo peso, el servicio perimetral de acceso seleccionará el registro SRV que se haya obtenido en primer lugar del servidor DNS.

</div>

</div>

<span> </span>

</div>

</div>

</div>

