---
title: "Lync Server 2013 : Dét. de la conf. req. pour DNS pour Lync Server 2013"
TOCTitle: Determinar los requisitos DNS
ms:assetid: 95777017-6282-44c0-a685-f246af0501b4
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398758(v=OCS.15)
ms:contentKeyID: 48276069
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Determinar los requisitos DNS para Lync Server 2013

 

_**Última modificación del tema:** 2016-12-08_

Use el diagrama de flujo siguiente para determinar los requisitos del Sistema de nombres de dominio (DNS). Los cambios para las actualizaciones acumulativas de Lync Server 2013 de febrero de 2013 se indican en su caso.

> [!IMPORTANT]  
> Microsoft Lync Server 2013 admite el uso del direccionamiento IPv6. Para usar direcciones IPv6, también debe proporcionar compatibilidad para DNS IPv6 y configurar registros AAAA de host DNS (conocidos como “cuádruple A”). En implementaciones en las que se están usando IPv4 e IPv6, es mejor configurar y mantener registros A de host para IPv4 y AAAA de host para IPv6. Aunque su implementación ha realizado una transición completa a IPv6, los registros de host DNS IPv4 todavía pueden ser necesarios cuando los usuarios externos estén usando todavía IPv4.



**Diagrama de flujo para determinar los requisitos de DNS**

![Diagrama de flujo de requisitos de DNS](images/Gg398758.175782ac-363e-408a-912f-8991bf152970(OCS.15).jpg "Diagrama de flujo de requisitos de DNS")

> [!IMPORTANT]  
> De manera predeterminada, el nombre de equipo de un equipo que no está unido a un dominio es un nombre de host, en lugar de un nombre de dominio completo (FQDN). Generador de topologías utiliza nombres de dominio completos, en vez de nombres de host. Así pues, debe configurar un sufijo de DNS en el nombre del equipo para poder implementarlo como servidor perimetral no incorporado a un dominio. <strong>Utilice únicamente caracteres estándar</strong> (A–Z, a–z, 0–9 y guiones) cuando asigne los nombres de dominio completo de sus servidores Lync, servidores perimetrales y grupos de servidores. No utilice caracteres Unicode ni de subrayado. Los DNS externos y las entidades de certificación públicas no admiten caracteres que no sean estándar en un nombre de dominio completo (es decir, cuando el FQDN se debe asignar al nombre de sujeto en el certificado). Para más información, consulte <a href="lync-server-2013-configure-dns-host-records.md">Configurar registros de host DNS para Lync Server 2013</a>.



## Cómo localizan servicios los clientes de Lync

Microsoft Lync 2010, Lync 2013 y Lync Mobile son similares en el modo en que el cliente encuentra y obtiene acceso a los servicios de Lync Server 2013. La excepción más destacada es la Aplicación de la Tienda Windows de Lync, que usa un proceso de localización de servicio distinto. En esta sección se describen dos escenarios en los que los clientes localizan servicios: el primero es el método tradicional que usa una serie de SRV y registros de host A; el segundo usa únicamente los registros del servicio Detección automática. Las actualizaciones acumulativas de los clientes de escritorio cambian el proceso de localización de DNS de Lync Server 2010. Para todos los clientes, el proceso de consulta de DNS continúa hasta que se devuelve una consulta con éxito o hasta que se agota la lista de posibles registros DNS y se devuelve un error final al cliente.

Para todos los clientes **excepto** para la Aplicación de la Tienda Windows de Lync. Durante la búsqueda de DNS, los registros SRV se consultan y se devuelven al cliente en el orden siguiente:

1.  lyncdiscoverinternal. *\<dominio\>*    Un registro (host) para el servicio Detección automática en los servicios web internos

2.  lyncdiscoverinternal. *\<dominio\>*    Registro A (host) para el servicio Detección automática en los servicios web externos

3.  \_sipinternaltls.\_tcp. *\<dominio\>*    Registro SRV (localizador de servicios) para conexiones TLS internas

4.  \_sipinternal.\_tcp. *\<dominio\>*    Registro SRV (localizador de servicios) para conexiones TCP internas (solo si se permite TCP)

5.  \_sip.\_tls. *\<dominio\>*    Registro SRV (localizador de servicios) para conexiones TLS externas

6.  sipinternal. *\<dominio\>*    Registro A (host) para el Grupo de servidores front-end o Director, soluble solo en la red interna

7.  sip. *\<dominio\>*    Registro A (host) para el Grupo de servidores front-end o Director en la red interna, o el Servidor perimetral de acceso cuando el cliente es externo

8.  sipexternal. *\<dominio\>*    Registro A (host) para el Servidor perimetral de acceso cuando el cliente es externo

La Aplicación de la Tienda Windows de Lync cambia el proceso completamente porque usa dos registros:

1.  lyncdiscoverinternal. *\<dominio\>*    Un registro (host) para el servicio Detección automática en los servicios web internos

2.  lyncdiscoverinternal. *\<dominio\>*    Registro A (host) para el servicio Detección automática en los servicios web externos

No hay reserva para los otros tipos de registros.

La diferencia entre los métodos usados para los clientes más recientes en comparación con los clientes más antiguos es que el servicio Detección automática se convierte en el método preferido para localizar todos los servicios.

Cuando una conexión es correcta, el servicio Detección automática devuelve todas las direcciones URL de servicios web del grupo de servidores principales del usuario, incluidas las direcciones URL del servicio Movilidad, (conocido como Mcx por el directorio virtual creado por el servicio en IIS), Microsoft Lync Web App y el programador web. No obstante, la dirección URL interna del servicio Movilidad y la dirección URL externa del servicio Movilidad se asocian al FQDN externo de los servicios web. Por lo tanto, independientemente de si un dispositivo móvil es interno o externo a la red, el dispositivo siempre se conecta al servicio Movilidad de forma externa a través del proxy inverso.

Si se han instalado las actualizaciones acumulativas de Lync Server 2013 de febrero de 2013, el servicio Detección automática también devuelve referencias a Internos/UCWA, Externos/UCWA y UCWA. Estas entradas hacen referencia al componente web de la API web de comunicaciones unificadas (UCWA). Actualmente solo se usa la entrada de UCWA y proporciona una referencia a una URL para el componente web. UCWA es usado por clientes de Lync 2013 Mobile en vez del servicio Movilidad Mcx usado por clientes de Lync 2010 Mobile.


> [!NOTE]
> A la hora de crear registros SRV, es importante recordar que deben señalar a un registro A y AAAA (si está usando direccionamiento IPv6) de DNS del mismo dominio donde se vaya a crear el registro SRV de DNS. Por ejemplo, si el registro SRV se encuentra en contoso.com, el registro A y AAAA (si se está usando direccionamiento IPv6) al que señala no puede encontrarse en fabrikam.com.



> [!TIP]  
> La configuración predeterminada dirige todo el tráfico de clientes móviles a través del sitio externo. Puede cambiar la configuración para devolver solamente la dirección URL interna, si esto se adapta más a sus necesidades. Con esta configuración, los usuarios pueden usar aplicaciones móviles de Lync en sus dispositivos móviles solo cuando están dentro de la red corporativa. Para definir esta configuración, hay que usar el cmdlet <strong>Set-CsMcxConfiguration</strong>.




> [!NOTE]
> Aunque las aplicaciones móviles también pueden conectarse a otros servicios de Lync Server 2013, como el servicio de la libreta de direcciones, las solicitudes web de aplicaciones móviles internas van al FQDN de web interno solamente para el servicio de movilidad. Otras solicitudes de servicios, como las solicitudes de la libreta de direcciones, no requieren esta configuración.



Los dispositivos móviles admiten la detección manual de servicios. En este caso, cada usuario debe configurar los parámetros del dispositivo móvil con las URL internas y externas completas del servicio Detección automática, incluyendo el protocolo y la ruta de acceso, de la manera siguiente:

  - https:// *\<ExtPoolFQDN\>* /Autodiscover/autodiscoverservice.svc/Raíz para acceso externo

  - https:// *\<IntPoolFQDN\>* /AutoDiscover.svc/Raíz para acceso interno

Recomendamos que use la detección automática, en lugar de la detección manual. No obstante, la configuración manual puede ser útil para solucionar problemas de conectividad de dispositivos móviles.

## Configuración de DNS de horizonte dividido con Lync Server

El término DNS de horizonte dividido se conoce con varios nombres, por ejemplo, DNS dividido o DNS de partición de red. Sencillamente describe una configuración de DNS en la que existen dos zonas DNS con el mismo espacio de nombre, pero una zona DNS procesa solo las solicitudes internas y la otra solo las externas. No obstante, muchos de los registros SRV y registros A de DNS que contiene el DNS interno no se incluirán en el DNS externo, y viceversa. Además, en los casos en que el mismo registro DNS existe tanto en el DNS interno como en el externo (por ejemplo, www<span/>.contoso.com), la dirección IP devuelta será distinta, en función de dónde (en el interior o en el exterior) se realice la consulta DNS.

> [!IMPORTANT]  
> Actualmente, el DNS de horizonte dividido no es compatible con la movilidad o, más concretamente, con los registros DNS LyncDiscover y LyncDiscoverInternal. LyncDiscover tiene que definirse en un servidor DNS externo y LyncDiscoverInternal tiene que definirse en un servidor DNS interno.



Aquí se utilizará el término DNS de horizonte dividido.

Si va a configurar DNS de horizonte dividido, a continuación se incluye un resumen de los tipos de registros DNS necesarios para cada zona. Para más información, consulte [Escenarios para el acceso de usuarios externos en Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md).

**DNS interno:**

  - Contiene una zona DNS llamada contoso.com sobre la cual es autoritativo

  - La zona contoso.com interna contiene:
    
      - Registros SRV y AAAA (si está usando direccionamiento IPv6) y A de DNS para la configuración automática de clientes de Lync Server 2013 interno (opcional)
    
      - Registros A y AAAA (si está usando direccionamiento IPv6) o CNAME de DNS para la detección automática de servicios web de Lync Server 2013 (opcional)
    
      - Registros SRV y A y AAAA (si está usando direccionamiento IPv6) de DNS para el nombre del grupo de servidores front-end, el director o el nombre de grupo del director y todos los servidores internos que ejecutan Lync Server 2013 en la red corporativa
    
      - Registros A y AAAA (si está usando direccionamiento IPv6) de DNS para la interfaz interna perimetral de cada Lync Server 2013 o servidor perimetral de la red perimetral
    
      - Registros A y AAAA (si está usando direccionamiento IPv6) de DNS para la interfaz interna de proxy inverso de cada servidor de proxy inverso de la red perimetral
    
      - Todos las interfaces perimetrales internas de Lync Server 2013  Servidor perimetral de la red perimetral utilizan la zona DNS interna para la resolución de consultas a contoso.com
    
      - Todos los servidores que ejecutan Lync Server 2013 y los clientes que ejecutan Lync 2013 en la red corporativa apuntan a los servidores DNS internos para la resolución de consultas a contoso.com, o utilizan un archivo de HOST en cada registro de servidor perimetral y de lista A y AAAA (si está usando direccionamiento IPv6) para el servidor del próximo salto, especialmente el director, el VIP del director, el VIP del grupo de servidores front-end o el servidor Standard Edition.

**DNS externo:**

  - Contiene una zona DNS llamada contoso.com sobre la cual es autoritativo

  - La zona contoso.com externa contiene:
    
      - Registros SRV y A y AAAA (si está usando direccionamiento IPv6) de DNS para la configuración automática de clientes de Lync Server 2013 (opcional)
    
      - Registros A y AAAA (si está usando direccionamiento IPv6) o CNAME de DNS para la detección automática de servicios web de Lync Server 2013 para utilizar con movilidad.
    
      - Registros SRV y A y AAAA (si está usando direccionamiento IPv6) de DNS para la interfaz externa perimetral de cada dirección IP virtual (VIP) de Lync Server 2013, servidor perimetral o equilibrador de carga de hardware de la red perimetral
    
      - Registros A y AAAA (si está usando direccionamiento IPv6) de DNS para la interfaz externa de proxy inverso de cada servidor de proxy inverso de la red perimetral

## Configuración automática sin DNS de horizonte dividido

Si usa DNS de horizonte dividido y un usuario de Lync Server 2013 que inicia sesión de forma interna, este puede sacar provecho de la configuración automática, siempre que la zona DNS interna contenga un registro SRV \_sipinternaltls.\_tcp para cada uno de los dominios SIP en uso. No obstante, si no usa DNS de horizonte dividido, la configuración automática interna de los clientes que ejecutan Lync no funcionará, a menos que se implemente una de las soluciones alternativas descritas más adelante en esta sección. Esto es debido a que Lync Server 2013 requiere que el URI del SIP del usuario coincida con el dominio del grupo de servidores front-end designado para la configuración automática. Lo mismo sucedía en versiones anteriores de Communicator.

Por ejemplo, si tiene dos dominios SIP en uso, se necesitarán los registros de servicio DNS (SRV) siguientes:

  - Si un usuario inicia sesión como lstest01@contoso.com, el registro SRV siguiente funcionará para la configuración automática porque el dominio SIP del usuario (contoso.com) coincide con el dominio del grupo de servidores front-end de configuración automática):
    
     \_sipinternaltls.\_tcp.contoso.com. 86400 IN SRV 0 0 5061 pool01.contoso.com

  - Si un usuario inicia sesión como lstest01@fabrikam.com, el siguiente registro SRV de DNS funcionará para la configuración automática del segundo dominio SIP.
    
     \_sipinternaltls.\_tcp.fabrikam.com. 86400 IN SRV 0 0 5061 pool01.fabrikam.com

En cambio, si un usuario inicia sesión como lstest01@litwareinc.com, el siguiente registro SRV de DNS no funcionará para la configuración automática, porque el dominio SIP del cliente (litwareinc.com) no coincide con el dominio donde se encuentra el grupo de servidores (fabrikam.com):

 \_sipinternaltls.\_tcp.litwareinc.com. 86400 IN SRV 0 0 5061 pool01.fabrikam.com

Si se requiere la configuración automática para clientes que ejecutan Lync, seleccione una de las opciones siguientes:

  - **Objetos de directiva de grupo :** use los objetos de directiva de grupo (GPO) para rellenar los valores de servidor correctos.
    

    > [!NOTE]
    > Esta opción no habilita la configuración automática, pero automatiza el proceso de configuración manual, de modo que si se usa este enfoque, no se requerirán los registros SRV asociados con la configuración automática.



  - **Zona interna coincidente :** cree una zona en el DNS interno que coincida con la zona DNS externa (por ejemplo, contoso.com) y cree registros A y AAAA (si está usando direccionamiento IPv6) de DNS que se correspondan con el grupo de servidores de Lync Server 2013 usado para la configuración automática. Por ejemplo, si un usuario está hospedado en pool01.contoso.net pero inicia sesión en Lync como bob@contoso.com, cree una zona DNS interna llamada contoso.com y dentro de ella, cree un registro A y AAAA (si está usando direccionamiento IPv6) de DNS para pool01.contoso.com.

  - **Zona interna designada :** si crear una zona entera en el DNS interno no es una opción, puede crear zonas designadas (es decir, dedicadas) que correspondan a los registros SRV que son necesarios para la configuración automática y rellenar dichas zonas mediante dnscmd.exe. Dnscmd.exe es obligatorio porque la interfaz de usuario de DNS no admite la creación de zonas designadas. Por ejemplo, si el dominio SIP es contoso.com y dispone de un grupo de servidores front-end llamado pool01 que contiene dos servidores front-end, necesitará los siguientes registros A y zonas designadas en el DNS interno:
    
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


> [!NOTE]
> El FQDN del grupo de servidores front-end aparece dos veces, pero con dos direcciones IP distintas. Esto se debe a que se usa el equilibrio de carga de DNS, pero si se usara el equilibrio de carga de hardware, solo habría una entrada de grupo de servidores front-end. Asimismo, los valores de FQDN del grupo de servidores front-end cambian entre el ejemplo de contoso.com y el ejemplo de fabrikam.com, pero las direcciones IP permanecen iguales. Esto se debe a que los usuarios que inician sesión desde cualquiera de los dominios SIP, usan el mismo grupo de servidores front-end para la configuración automática.



Para obtener más información, consulte el artículo del blog DMTF "Communicator Automatic Configuration and Split-Brain DNS" en inglés (DNS de horizonte dividido y configuración automática de Communicator) en <http://go.microsoft.com/fwlink/?linkid=200707>.


> [!NOTE]
> El contenido de los blogs y sus URL están sujetos a cambios sin previo aviso.



## Configuración del sistema de nombres de dominio (DNS) para la recuperación ante desastres

Para configurar DNS para redirigir el tráfico web de Lync Server 2013 a los sitios de recuperación ante desastres y conmutación por error, debe usar un proveedor de DNS que admita. Puede configurar los registros DNS para la Web para admitir recuperación ante desastres y, de esta manera, las características que usan servicios web continúen aunque un Grupo de servidores front-end entero deje de estar disponible. Esta característica de recuperación ante desastres admite direcciones URL sencillas de Detección automática (URL de Lyncdiscover), Reunión y Acceso telefónico.

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
<th>Opciones de configuración de DNS (seleccione una opción)</th>
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
<p>Usa el primario, se conecta al secundario en caso de error</p></td>
</tr>
<tr class="even">
<td><p>Meet-ext.geolb.contoso.com</p></td>
<td><p>Pool1ExternalWebFQDN.contoso.com</p>
<p>Pool2ExternalWebFQDN.contoso.com</p></td>
<td><p>Alias Meet.contoso.com a Pool1ExternalWebFQDN.contoso.com</p>
<p>Alias Meet.contoso.com a Pool2ExternalWebFQDN.contoso.com</p></td>
<td><p>Round robin entre grupos</p>
<p>Usa el primario, se conecta al secundario en caso de error</p></td>
</tr>
<tr class="odd">
<td><p>Dialin-int.geolb.contoso.com</p></td>
<td><p>Pool1InternalWebFQDN.contoso.com</p>
<p>Pool2InternalWebFQDN.contoso.com</p></td>
<td><p>Alias Dialin.contoso.com a Pool1InternalWebFQDN.contoso.com</p>
<p>Alias Dialin.contoso.com a Pool2InternalWebFQDN.contoso.com</p></td>
<td><p>Round robin entre grupos</p>
<p>Usa el primario, se conecta al secundario en caso de error</p></td>
</tr>
<tr class="even">
<td><p>Dialin-ext.geolb.contoso.com</p></td>
<td><p>Pool1ExternalWebFQDN.contoso.com</p>
<p>Pool2ExternalWebFQDN.contoso.com</p></td>
<td><p>Alias Dialin.contoso.com a Pool1ExternalWebFQDN.contoso.com</p>
<p>Alias Dialin.contoso.com a Pool2ExternalWebFQDN.contoso.com</p></td>
<td><p>Round robin entre grupos</p>
<p>Usa el primario, se conecta al secundario en caso de error</p></td>
</tr>
<tr class="odd">
<td><p>Lyncdiscoverint-int.geolb.contoso.com</p></td>
<td><p>Pool1InternalWebFQDN.contoso.com</p>
<p>Pool2InternalWebFQDN.contoso.com</p></td>
<td><p>Alias Lyncdiscoverinternal.contoso.com a Pool1InternalWebFQDN.contoso.com</p>
<p>Alias Lyncdiscoverinternal.contoso.com a Pool2InternalWebFQDN.contoso.com</p></td>
<td><p>Round robin entre grupos</p>
<p>Usa el primario, se conecta al secundario en caso de error</p></td>
</tr>
<tr class="even">
<td><p>Lyncdiscover-ext.geolb.contoso.com</p></td>
<td><p>Pool1ExternalWebFQDN.contoso.com</p>
<p>Pool2ExternalWebFQDN.contoso.com</p></td>
<td><p>Alias Lyncdiscover.contoso.com a Pool1ExternalWebFQDN.contoso.com</p>
<p>Alias Lyncdiscover.contoso.com a Pool2ExternalWebFQDN.contoso.com</p></td>
<td><p>Round robin entre grupos</p>
<p>Usa el primario, se conecta al secundario en caso de error</p></td>
</tr>
<tr class="odd">
<td><p>Scheduler-int.geolb.contoso.com</p></td>
<td><p>Pool1InternalWebFQDN.contoso.com</p>
<p>Pool2InternalWebFQDN.contoso.com</p></td>
<td><p>Alias Scheduler.contoso.com a Pool1InternalWebFQDN.contoso.com</p>
<p>Alias Scheduler.contoso.com a Pool2InternalWebFQDN.contoso.com</p></td>
<td><p>Round robin entre grupos</p>
<p>Usa el primario, se conecta al secundario en caso de error</p></td>
</tr>
<tr class="even">
<td><p>Scheduler-ext.geolb.contoso.com</p></td>
<td><p>Pool1ExternalWebFQDN.contoso.com</p>
<p>Pool2ExternalWebFQDN.contoso.com</p></td>
<td><p>Alias Scheduler.contoso.com a Pool1ExternalWebFQDN.contoso.com</p>
<p>Alias Scheduler.contoso.com a Pool2ExternalWebFQDN.contoso.com</p></td>
<td><p>Round robin entre grupos</p>
<p>Usa el primario, se conecta al secundario en caso de error</p></td>
</tr>
</tbody>
</table>


## Equilibrio de carga de DNS

El equilibrio de carga de DNS suele implementarse en el nivel de la aplicación. La aplicación (por ejemplo, un cliente que ejecuta Lync), intenta conectarse a un servidor en un grupo de servidores conectándose a una de las direcciones IP obtenidas a raíz de la consulta del registro A y AAAA (si se usa el direccionamiento IPv6) de DNS para el nombre de dominio completo (FQDN) del grupo de servidores.

Por ejemplo, si hay tres servidores front-end en un grupo de servidores denominado pool01.contoso.com, pasará lo siguiente:

  - Los clientes que ejecutan Lync envían una consulta al DNS para pool01.contoso.com y obtendrá como resultado tres direcciones IP que almacenará en caché de la forma siguiente (no necesariamente en este orden):
    
    pool01.contoso.com      192.168.10.90
    
    pool01.contoso.com      192.168.10.91
    
    pool01.contoso.com      192.168.10.92

  - A continuación, el cliente intentará establecer una conexión de Protocolo de control de transmisión (TCP) con una de las direcciones IP. Si no funciona, lo intentará con la siguiente dirección IP almacenada en caché.

  - Si la conexión TCP se establece correctamente, el cliente negociará con el TLS para conectarse con el registrador principal en pool01.contoso.com.

  - Si el cliente intenta todas las entradas almacenadas en caché sin establecer una conexión correctamente, se notificará al usuario que en ese momento no hay disponible ningún servidor que ejecute Lync Server 2013.


> [!NOTE]
> El equilibrio de carga basado en DNS es distinto al round robin de DNS (DNS RR), que normalmente hace referencia al equilibrio de carga usando el DNS para proporcionar un orden distinto de direcciones IP correspondientes a los servidores de un grupo de servidores. Por lo general, DNS RR solo habilita la distribución de carga, pero no habilita la conmutación por error. Por ejemplo, si no se consigue establecer la conexión con la dirección IP devuelta por la consulta A y AAAA (si está usando el direccionamiento IPv6) de DNS, la conexión será errónea. Por tanto, el round robin de DNS por sí solo es menos fiable que el equilibrio de carga basado en DNS. Puede usar el round robin de DNS junto con el equilibrio de carga de DNS.



El equilibrio de carga de DNS se usa para lo siguiente:

  - Equilibrar la carga SIP entre servidores con los servidores perimetrales

  - Equilibrar la carga de aplicaciones de servicios de aplicaciones de comunicaciones unificadas (UCAS) como Operador automático de conferencia, Grupo de respuesta y Estacionamiento de llamadas

  - Impedir el establecimiento de nuevas conexiones con aplicaciones UCAS (proceso también conocido como "purga").

  - Equilibrar la carga de todo el tráfico de servidor a cliente entre clientes y servidores perimetrales

El equilibrio de carga de DNS no puede usarse para:

  - Tráfico web de cliente a servidor al director o a los servidores front-end

Equilibrio de carga de DNS y tráfico federado:

Si una consulta SRV de DNS devuelve varios registros DNS, el servicio perimetral de acceso siempre selecciona el registro SRV de DNS con la prioridad numérica más baja y con el peso numérico más alto. El documento de Internet Engineering Task Force “A DNS RR for specifying the location of services (DNS SRV)” (RR de DNS para especificar la ubicación de los servicios \[DNS SRV\]) <http://www.ietf.org/rfc/rfc2782.txt> especifica que si hay definidos varios registros SRV de DNS. La prioridad se usa primero y luego el peso. Por ejemplo, el registro A de SRV de DNS tiene un peso de 20 y una prioridad de 40 y el registro B de SRV de DNS tiene un peso de 10 y una prioridad de 50. Se seleccionará el registro A de SRV de DNS con una prioridad de 40. Las siguientes reglas se aplican a la selección de registros SRV de DNS:

  - La prioridad se considera primero. Un cliente DEBE intentar contactar con el host de destino definido por el registro SRV de DNS con la menor prioridad numerada que pueda alcanzar. Los destinos con la misma prioridad DEBEN intentarse siguiendo el orden definido por el campo de peso.

  - El campo de peso especifica un peso relativo para las entradas que tienen la misma prioridad. A los pesos más grandes DEBE otorgárseles una prioridad proporcionalmente mayor de ser seleccionados. Los administradores de DNS DEBEN usar el peso 0 cuando no hay ninguna selección de servidor que hacer. Cuando existen registros con pesos superiores a 0, los registros con peso 0 deben tener una oportunidad muy pequeña de ser elegidos.

Si se devuelven varios registros SRV de DNS con la misma prioridad y el mismo peso, el servicio perimetral de acceso seleccionará el registro SRV que se haya obtenido en primer lugar del servidor DNS.

