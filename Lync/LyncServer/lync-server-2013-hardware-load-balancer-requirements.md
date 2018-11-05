---
title: "Conf. requise pour l’équilibreur de charge matérielle pour Lync Server 2013"
TOCTitle: Requisitos del equilibrador de carga de hardware
ms:assetid: 32891268-2059-43d0-adf4-af4ff1e9ce66
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ656815(v=OCS.15)
ms:contentKeyID: 49889035
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Requisitos del equilibrador de carga de hardware en Lync Server 2013

 

_**Última modificación del tema:** 2016-12-08_

La topología perimetral consolidada escalada de Lync Server 2013 se optimiza con el equilibrio de carga de DNS que se aplica a las nuevas implementaciones que se federan principalmente con otras organizaciones por medio de Lync Server. En caso de que se necesite una gran disponibilidad en cualquiera de los siguientes escenarios, se deberá usar un equilibrador de carga de hardware en grupos de Servidor perimetral:

  - Federación con organizaciones que usen Office Communications Server 2007 R2 o Office Communications Server 2007

  - Mensajería unificada de Exchange para los usuarios remotos que utilicen Mensajería unificada de Exchange antes de Exchange 2010 con SP1

  - Conectividad con usuarios de mensajería instantánea pública

> [!IMPORTANT]  
> No se admite el uso del equilibrio de carga de DNS en una interfaz y del equilibrio de carga de hardware en otra. Debe utilizar el equilibrio de carga de hardware o de DNS en ambas interfaces.




> [!NOTE]
> Si usa un equilibrador de carga de hardware, el equilibrador de carga que se haya implementado para las conexiones con la red interna deberá configurarse de modo que solo equilibre la carga del tráfico de los servidores que ejecuten el servicio perimetral de acceso y el servicio perimetral A/V. No puede equilibrar la carga del tráfico al servicio perimetral de conferencia web interno o al servicio proxy XMPP interno.




> [!NOTE]
> Lync Server 2013 no admite NAT de retorno de servidor directo (DSR).



Para saber si su equilibrador de carga de hardware admite las características que necesita Lync Server 2013, consulte " Lync Server 2010 Load Balancer Partners" en inglés (Socios de equilibradores de carga" en [http://go.microsoft.com/fwlink/?linkid=202452\&clcid=0xC0A](http://go.microsoft.com/fwlink/?linkid=202452%26clcid=0xc0a).

## Requisitos de equilibrador de carga de hardware para servidores perimetrales que ejecutan el servicio perimetral A/V

A continuación, se muestran los requisitos del equilibrador de carga de hardware para Servidores perimetrales que ejecuten un servicio perimetral A/V:

  - Deshabilitar la aplicación del algoritmo de Nagle TCP para los puertos 443 internos y externos. La aplicación del algoritmo de Nagle es la combinación de varios paquetes pequeños en un único paquete más grande para obtener una transmisión más eficiente.

  - Deshabilitar la aplicación del algoritmo de Nagle TCP para el intervalo de puertos externos de 50.000 a 59.999.

  - No utilizar NAT en el firewall interno o externo.

  - La interfaz interna del servidor perimetral y la interfaz externa del Servidor perimetral deben estar en redes diferentes, y debe inhabilitarse el enrutamiento entre ellas.

  - La interfaz interna del Servidor perimetral que ejecute el servicio perimetral A/V debe usar públicamente direcciones IP enrutables y ninguna NAT o traducción de puerto en ninguna de las direcciones IP externas del servidor perimetral.

## Requisitos del equilibrador de carga de hardware

Los requisitos de afinidad basada en cookies se han reducido en gran medida en Lync Server 2013 para los servicios web. Si va a implementar Lync Server 2013 no va a mantener ninguno de los Servidores front-end o Grupos de servidores front-end de Lync Server 2010, no necesita la persistencia basada en cookies. Sin embargo, si va a mantener de forma temporal o permanente algunos de los Servidores front-end o los Grupos de servidores front-end de Lync Server 2010, deberá seguir utilizando la persistencia basada en cookies tal como está implementada y configurada para Lync Server 2010.


> [!NOTE]
> <STRONG>La utilización de la afinidad basada en cookies pese a que su implementación no la necesite</STRONG> no tiene repercusiones.



Para las implementaciones que **no utilicen** la afinidad basada en cookies:

  - En la regla de publicación del proxy inverso para el puerto 4443, establezca **Transferir encabezado de host** en True. Esto garantizará que se transfiera la URL original.

Para las implementaciones que **utilicen** la afinidad basada en cookies:

  - En la regla de publicación del proxy inverso para el puerto 4443, establezca **Transferir encabezado de host** en True. Esto garantizará que se transfiera la URL original.

  - La cookie de equilibrio de carga de hardware NO DEBE estar marcada como httpOnly

  - La cookie de equilibrio de carga de hardware NO DEBE tener tiempo de expiración

  - La cookie de equilibrio de carga de hardware DEBE tener el nombre **MS-WSMAN** (este es el esperado por los servicios web y no puede modificarse)

  - La cookie de equilibrio de carga de hardware DEBE estar establecida en cada respuesta HTTP para la que la solicitud HTTP entrante no tenía una cookie, independientemente de si una respuesta HTTP anterior en la misma conexión TCP ya había obtenido una cookie. Si el equilibrador de carga optimiza la inserción de cookies para que solo ocurra una vez por conexión TCP, la optimización NO debe usarse.


> [!NOTE]
> Las configuraciones típicas del equilibrador de carga de hardware usan afinidad de direcciones de origen y una duración de sesión TCP de 20 minutos, que es adecuada para clientes de Lync Server y de Lync 2013 porque el estado de la sesión se mantiene a través del uso del cliente y/o la interacción de aplicaciones.



Si se implementan dispositivos móviles, el equilibrador de carga de hardware debe poder equilibrar la carga de una solicitud individual dentro de una sesión TCP (de hecho, debe poder equilibrar la carga de una solicitud individual basada en la dirección IP de destino).

> [!WARNING]  
> Los equilibradores de carga de hardware F5 tienen una característica llamada OneConnect que asegura que cada solicitud dentro de una conexión TCP tenga carga equilibrada individualmente. Si va a implementar dispositivos móviles, asegúrese de que su proveedor del equilibrador de carga de hardware admita la misma funcionalidad. Las últimas aplicaciones móviles que utilizan el sistema Apple iOS requieren el uso seguridad de capa de transporte (TLS), versión 1.2. F5 proporciona opciones de configuración específicas para este sistema.<br />
> Para obtener más información sobre los equilibradores de carga de hardware de terceros, vea <a href="http://go.microsoft.com/fwlink/?linkid=230700%26clcid=0xc0a">http://go.microsoft.com/fwlink/?linkid=230700&amp;clcid=0xC0A</a>


A continuación se muestran los requisitos del equilibrador de carga de hardware para servicios web de grupo de directores y de servidores front-end:

  - Para VIPS de servicios web internos, configure la persistencia Source\_addr (puerto interno 80, 443) en el equilibrador de carga de hardware. Para Lync Server 2013, la persistencia Source\_addr significa que se envían siempre varias conexiones de una única dirección IP a un servidor para mantener el estado de la sesión.

  - Use un tiempo de espera de inactividad TCP de 1.800 segundos

  - En el firewall entre el proxy inverso y el equilibrador de carga de hardware del grupo de servidores del próximo salto, cree una regla que permita el tráfico https: en el puerto 4443, del proxy inverso al equilibrador de carga de hardware. El equilibrador de carga de hardware debe configurarse de modo que escuche los puertos 80, 443 y 4443.

## Resumen de requisitos de afinidad del equilibrador de carga de hardware


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Ubicación de cliente/usuario</th>
<th>Requisitos de afinidad del FQDN de servicios web externos</th>
<th>Requisitos de afinidad del FQDN de servicios web internos</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync Web App (usuarios internos y externos)</p>
<p>Dispositivo móvil (usuarios internos y externos)</p></td>
<td><p>Sin afinidad</p></td>
<td><p>Afinidad de direcciones de origen</p></td>
</tr>
<tr class="even">
<td><p>Lync Web App (solo usuarios externos)</p>
<p>Dispositivo móvil (usuarios internos y externos)</p></td>
<td><p>Sin afinidad</p></td>
<td><p>Afinidad de direcciones de origen</p></td>
</tr>
<tr class="odd">
<td><p>Lync Web App (solo usuarios internos)</p>
<p>Dispositivo móvil (no implementado)</p></td>
<td><p>Sin afinidad</p></td>
<td><p>Afinidad de direcciones de origen</p></td>
</tr>
</tbody>
</table>


## Supervisión de puertos para los equilibradores de carga de hardware

Es necesario definir la supervisión de puertos en los equilibradores de carga de hardware para determinar cuándo determinados servicios dejan de estar disponibles debido a errores de comunicaciones o de hardware. Por ejemplo, si el servicio Servidor front-end (RTCSRV) se detiene debido a un error en el Servidor front-end o en el Grupo de servidores front-end, la supervisión de equilibrio de carga de hardware también debe dejar de recibir tráfico del Servicios web. La supervisión de puertos en el equilibrador de carga de hardware debe implementarse para supervisar lo siguiente:

### Grupo de usuarios del Servidor front-end – Interfaz interna de equilibrio de carga de hardware

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th>Puerto/IP virtual</th>
<th>Puerto de nodo</th>
<th>Monitor/máquina de nodo</th>
<th>Perfil de persistencia</th>
<th>Notas</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>&lt;pool&gt;web-int_mco_443_vs</p>
<p>443</p></td>
<td><p>443</p></td>
<td><p>Front-end</p>
<p>5061</p></td>
<td><p>Origen</p></td>
<td><p>HTTPS</p></td>
</tr>
<tr class="even">
<td><p>&lt;pool&gt;web-int_mco_80_vs</p>
<p>80</p></td>
<td><p>80</p></td>
<td><p>Front-end</p>
<p>5061</p></td>
<td><p>Origen</p></td>
<td><p>HTTP</p></td>
</tr>
</tbody>
</table>


### Grupo de usuarios del Servidor front-end – Interfaz externa de equilibrio de carga de hardware

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th>Puerto/IP virtual</th>
<th>Puerto de nodo</th>
<th>Monitor/máquina de nodo</th>
<th>Perfil de persistencia</th>
<th>Notas</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>&lt;pool&gt;web_mco_443_vs</p>
<p>443</p></td>
<td><p>4443</p></td>
<td><p>Front-end</p>
<p>5061</p></td>
<td><p>Ninguno</p></td>
<td><p>HTTPS</p></td>
</tr>
<tr class="even">
<td><p>&lt;pool&gt;web_mco_80_vs</p>
<p>80</p></td>
<td><p>8080</p></td>
<td><p>Front-end</p>
<p>5061</p></td>
<td><p>Ninguno</p></td>
<td><p>HTTP</p></td>
</tr>
</tbody>
</table>

