---
title: 'Lync Server 2013: Soluciones de resistencia de sitios de sucursales'
TOCTitle: Soluciones de resistencia de sitios de sucursales
ms:assetid: 1700f99b-709c-4e47-88eb-c0a5490e26e2
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398234(v=OCS.15)
ms:contentKeyID: 48274554
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Soluciones de resistencia de sitios de sucursales en Lync Server 2013

 

_**Última modificación del tema:** 2015-03-09_

Las ventajas que una organización obtiene al disponer de resistencia en las sucursales son más que evidentes. Por ejemplo, si los usuarios de la sucursal pierden la conexión con el sitio central, pueden seguir teniendo servicios de voz y de Telefonía IP empresarial, siempre y cuando el correo de voz se haya configurado para que se pueda volver a enrutar (consulte [Requisitos de resistencia de sitios de sucursal para Lync Server 2013](lync-server-2013-branch-site-resiliency-requirements.md) para obtener información detallada). Sin embargo, una solución de resistencia probablemente no compense lo suficiente en sitios con menos de 25 usuarios.

Si decide proporcionar resistencia en las sucursales, tiene tres maneras de hacerlo. La siguiente tabla puede ayudarle a saber cuál es la mejor opción para su organización.



<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Si...</th>
<th>Se recomienda...</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Hospeda entre 25 y 1000 usuarios en la sucursal y no compensa una implementación completa o no se dispone de asistencia administrativa local</p></td>
<td><p>Aplicación de sucursal con funciones de supervivencia</p>
<p>La Aplicación de sucursal con funciones de supervivencia es un servidor modular estándar del sector con un registrador y un servidor de mediación de Lync Server que se ejecutan en Windows Server 2008 R2. La Aplicación de sucursal con funciones de supervivencia contiene también una puerta de enlace de red telefónica conmutada (RTC). Los dispositivos de otros fabricantes calificados (desarrollados por socios de Microsoft en el programa de certificación/calificación de aplicación de sucursal con funciones de supervivencia [SBA]) ofrecen una conexión RTC ininterrumpida en caso de que se produzca un error de WAN, aunque este enfoque no proporciona presencia y conferencia resistentes, ya que ambas características dependen de los servidores front-end del sitio central.</p>
<p>Si desea información detallada sobre Aplicaciones de sucursal con funciones de supervivencia, vea &quot;Detalles de Aplicación de sucursal con funciones de supervivencia&quot;, más adelante en este tema.</p>
<p><strong>Nota:</strong> si opta por usar también un tronco SIP con la Aplicación de sucursal con funciones de supervivencia, póngase en contacto con el proveedor de la Aplicación de sucursal con funciones de supervivencia para obtener más información sobre qué proveedor de servicios es el mejor para su organización.</p></td>
</tr>
<tr class="even">
<td><p>Hospeda entre 1000 y 2000 usuarios en la sucursal, carece de conexión WAN resistente y dispone de administradores de Lync Server debidamente formados</p></td>
<td><p>Servidor de sucursal con funciones de supervivencia o dos Aplicaciones de sucursal con funciones de supervivencia</p>
<p>El Servidor de sucursal con funciones de supervivencia es un servidor de reunión de Windows que reúne una serie de requisitos de hardware y que tiene instalado el software de registrador y servidor de mediación de Lync Server. Debe conectarse a una puerta de enlace RTC o a un tronco SIP hacia un proveedor de servicios telefónicos.</p>
<p>Si desea información detallada sobre Servidores de sucursal con funciones de supervivencia, vea &quot;Detalles de Servidor de sucursal con funciones de supervivencia&quot;, más adelante en este tema.</p></td>
</tr>
<tr class="odd">
<td><p>Si, además de las características de voz, necesita las características de presencia y conferencia para un máximo de 5000 usuarios y dispone de administradores de Lync Server debidamente formados</p></td>
<td><p>Realizar una implementación como un sitio central con un servidor Standard Edition en lugar de como una sucursal.</p>
<p>Una implementación de Lync Server a escala completa proporciona una conexión RTC constante y unas características de presencia y conferencia resistentes en caso de error de WAN.</p>
<p>Para obtener detalles sobre cómo prepararse para esta solución, consulte <a href="lync-server-2013-planning-for-your-organization.md">Planeación de la organización para Lync Server 2013</a>, <a href="lync-server-2013-determining-your-system-requirements.md">Determinar los requisitos del sistema para Lync Server 2013</a>, <a href="lync-server-2013-determining-your-infrastructure-requirements.md">Determinar los requisitos de infraestructura para Lync Server 2013</a> y otras secciones relevantes en la documentación de planeación.</p></td>
</tr>
</tbody>
</table>


## Topologías de resistencia

La siguiente figura refleja las topologías recomendadas de resistencia en las sucursales.

**Opciones de resistencia de las sucursales**

![Opciones de resistencia de voz para sucursal](images/Gg398234.47eecd19-08ae-4d82-acbe-61f0de760306(OCS.15).jpg "Opciones de resistencia de voz para sucursal")

## Detalles de la aplicación de sucursal con funciones de supervivencia

La aplicación de sucursal con funciones de supervivencia de Lync Server engloba los siguientes componentes:

  - Un registrador para la autenticación y registro de usuarios y el enrutado de llamadas

  - Un servidor de mediación para controlar la señalización entre el registrador y una puerta de enlace RTC

  - Una puerta de enlace RTC para enrutar llamadas a la RTC a modo de transporte de reserva en caso de que se produzca una interrupción en la red WAN

  - SQL Server Express para el almacenamiento local de los datos de usuario

La Aplicación de sucursal con funciones de supervivencia también incorpora troncos RTC, puertos analógicos y un adaptador Ethernet.

Si la conexión WAN de una sucursal a un sitio central deja de estar disponible, los usuarios de la sucursal seguirán estando registrados gracias al registrador de la Aplicación de sucursal con funciones de supervivencia y seguirán teniendo un servicio de voz ininterrumpido mediante la conexión de la Aplicación de sucursal con funciones de supervivencia a la red RTC. En caso de que el vínculo WAN a una sucursal no esté disponible, los usuarios de sucursal que se conecten desde casa o desde otras ubicaciones remotas tendrán la posibilidad de registrarse con un servidor registrador ubicado en el sitio central. Estos usuarios disfrutarán de la funcionalidad de comunicaciones unificadas completa, con la única salvedad de que las llamadas entrantes a la sucursal se trasladarán al correo de voz. Cuando la conexión WAN vuelva, deberá restaurarse la funcionalidad completa para los usuarios de las sucursales. No es necesario recurrir a un administrador de TI ni para la conmutación a la Aplicación de sucursal con funciones de supervivencia ni para la restauración del servicio.

Lync Server admite hasta dos Aplicación de sucursal con funciones de supervivencia en un Sitio de sucursal.

## Descripción general de la implementación de la aplicación de sucursal con funciones de supervivencia

Un equipo de fabricantes de equipos originales en colaboración con Microsoft se encarga de la fabricación de la Aplicación de sucursal con funciones de supervivencia, mientras que su implementación corre a cargo de distribuidores de valor agregado. Esta implementación debe tener lugar solo si se ha implementado Lync Server en el sitio central, existe una conexión WAN a la sucursal y los usuarios de la sucursal tienen acceso a Telefonía IP empresarial.

Para obtener información detallada sobre estas fases, consulte [Implementar una aplicación o servidor de sucursal con funciones de supervivencia con Lync Server 2013](lync-server-2013-deploying-a-survivable-branch-appliance-or-server.md) en la documentación de implementación.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Fase</th>
<th>Pasos</th>
<th>Derechos de usuario</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Configurar Servicios de dominio de Active Directory para la Aplicación de sucursal con funciones de supervivencia</p></td>
<td><p><strong>En el sitio central:</strong></p>
<ol>
<li><p>Cree una cuenta de usuario de dominio (o identidad de empresa) para el técnico que vaya a instalar y activar la Aplicación de sucursal con funciones de supervivencia en la sucursal.</p></li>
<li><p>Cree una cuenta de equipo (con el nombre de dominio completo [FQDN] pertinente) para la Aplicación de sucursal con funciones de supervivencia en Active Directory</p></li>
<li><p>En Generador de topologías, cree y publique la Aplicación de sucursal con funciones de supervivencia.</p></li>
</ol></td>
<td><p>La cuenta de usuario del técnico debe ser miembro de RTCUniversalSBATechnicians. La Aplicación de sucursal con funciones de supervivencia debe pertenecer al grupo RTCSBAUniversalServices, algo que sucede automáticamente al usar Topology Builder.</p></td>
</tr>
<tr class="even">
<td><p>Instalar y activar la Aplicación de sucursal con funciones de supervivencia.</p></td>
<td><p><strong>En la sucursal:</strong></p>
<ol>
<li><p>Conecte la Aplicación de sucursal con funciones de supervivencia a un puerto Ethernet o puerto RTC.</p></li>
<li><p>Inicie la Aplicación de sucursal con funciones de supervivencia.</p></li>
<li><p>Una la Aplicación de sucursal con funciones de supervivencia al dominio usando la cuenta de usuario de dominio que creó para la Aplicación de sucursal con funciones de supervivencia en el sitio central. Establezca el FQDN y la dirección IP de forma que coincidan con el FQDN creado en la cuenta del equipo.</p></li>
<li><p>Configure la Aplicación de sucursal con funciones de supervivencia mediante la interfaz de usuario del fabricante de equipos originales.</p></li>
<li><p>Compruebe la conectividad RTC.</p></li>
</ol></td>
<td><p>La cuenta de usuario del técnico debe ser miembro de RTCUniversalSBATechnicians.</p></td>
</tr>
</tbody>
</table>


## Detalles del servidor de sucursal con funciones de supervivencia

En Generador de topologías, cree la sucursal, agregue el Servidor de sucursal con funciones de supervivencia a esta y, a continuación, ejecute el Asistente para la implementación de Lync Server en el equipo en el que desea instalar el rol.

## Vea también

#### Otros recursos

[Implementar Lync Server 2013](lync-server-2013-deploying-lync-server.md)

