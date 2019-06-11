---
title: Lync Server 2013 planeamiento de capacidad con los modelos de usuario
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Capacity planning using the user models
ms:assetid: 902ab23e-94d6-482a-9d6e-c0b28dc3e03d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615015(v=OCS.15)
ms:contentKeyID: 49733733
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3b7db58e8c6f3e84f95a51ddd393ddca5ec18091
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842690"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="capacity-planning-for-lync-server-2013-using-the-user-models"></a>Planificación de capacidad para Lync Server 2013 con los modelos de usuario

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-01-14_

Esta sección proporciona instrucciones sobre cuántos servidores necesita en un sitio para el número de usuarios de ese sitio, según el uso descrito en modelos de [usuario en Lync Server 2013](lync-server-2013-user-models.md).

<div>

## <a name="tested-hardware-platform"></a>Plataforma de hardware probada

Todos los resultados de rendimiento y las recomendaciones de implementación de esta sección se basan en pruebas de rendimiento en servidores que ejecutan el hardware que se describe en la tabla siguiente. Le recomendamos que use hardware similar. Si usa un hardware menos eficaz, puede tener problemas de funcionalidad o un rendimiento deficiente. Tenga en cuenta que estas recomendaciones de hardware son superiores a las de las versiones anteriores de Lync Server.

### <a name="hardware-used-in-performance-testing"></a>Hardware usado en pruebas de rendimiento

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Componente de hardware</th>
<th>Recomendado</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>CPU</p></td>
<td><p>Procesador dual de 64 bits, de seis núcleos, 2,26 gigahercios (GHz) o superior</p>
<p>Los procesadores Intel Itanium no son compatibles con los roles de servidor de Lync Server.</p></td>
</tr>
<tr class="even">
<td><p>Memoria</p></td>
<td><p>32 gigabytes (GB)</p></td>
</tr>
<tr class="odd">
<td><p>Disco</p></td>
<td><ul>
<li><p>8 o más unidades de disco duro de 10 000 RPM con al menos 72 GB de espacio libre en disco.</p>
<p>Dos de los discos deben usar RAID 1 y seis deben usar RAID 10.</p>
<p>-Ni</p></li>
<li><p>Unidades de estado sólido (SSD) con un rendimiento igual al de 8 unidades de disco duro mecánicas de 10.000 rpm.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Red</p></td>
<td><ul>
<li><p>1 adaptador de red de puerto dual, 1 Gbps o superior (2 recomendados, lo que requiere la formación de equipos con una sola dirección MAC y una sola dirección IP).</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="summary-of-results"></a>Resumen de los resultados

En la tabla siguiente se resumen estas recomendaciones.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Rol de servidor</th>
<th>Cantidad máxima de usuarios admitidos</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Grupo front-end con doce servidores front-end y un servidor back-end o un par espejeado de servidores back end.</p></td>
<td><p>80.000 usuarios únicos con sesión iniciada simultáneamente, más un 50% de múltiples puntos de presencia (MPOP) que representan instancias no móviles, más un 40% de los usuarios habilitados para movilidad, lo que hace un total de 152.000 extremos.</p></td>
</tr>
<tr class="even">
<td><p>Conferencia A/V</p></td>
<td><p>El servicio de conferencia A/V suministrado por un grupo de servidores front-end admite las conferencias de la agrupación suponiendo un tamaño máximo de conferencia de usuarios de 250 y solo una de estas conferencias de gran tamaño.</p>
<div>

> [!NOTE]  
> Además, puede admitir conferencias grandes de usuarios de 250 y 1000 implementando un grupo de servidores front-end independiente con dos servidores front-end para hospedar las grandes conferencias. Para obtener más información, consulte <A href="lync-server-2013-supporting-large-meetings.md">compatibilidad con reuniones grandes con Lync Server 2013</A>.


</div></td>
</tr>
<tr class="odd">
<td><p>Un servidor perimetral</p></td>
<td><p>12.000 usuarios remotos simultáneos</p></td>
</tr>
<tr class="even">
<td><p>Un director</p></td>
<td><p>12.000 usuarios remotos simultáneos</p></td>
</tr>
<tr class="odd">
<td><p>Supervisión y archivado</p></td>
<td><p>En Lync Server 2013, los servicios front-end de supervisión y archivado se ejecutan ahora en cada servidor front-end, en lugar de en roles de servidor diferentes.</p>
<p>Los servicios de supervisión y archivado aún necesitan sus propios almacenes de base de datos. Si también ejecuta Exchange 2013, puede mantener los datos de archivado en Exchange, en lugar de hacerlo en una base de datos SQL dedicada.</p></td>
</tr>
<tr class="even">
<td><p>Un servidor de mediación</p></td>
<td><p>El servidor de mediación en el servidor front-end se ejecuta en todos los servidores front end de un grupo y debe proporcionar la capacidad suficiente para los usuarios del grupo. Para el servidor de mediación independiente, consulte la sección "servidor de media", más adelante en este mismo tema.</p></td>
</tr>
<tr class="odd">
<td><p>Un servidor Standard Edition</p></td>
<td><p>Le recomendamos encarecidamente que si usa servidores Standard Edition para hospedar usuarios, siempre use dos servidores, emparejados mediante las recomendaciones de <a href="lync-server-2013-planning-for-high-availability-and-disaster-recovery.md">planeación de alta disponibilidad y recuperación ante desastres en Lync Server 2013</a>. Cada servidor del par puede hospedar hasta 2500 usuarios y, si uno de los servidores produce errores, el otro servidor puede admitir 5000 usuarios en un escenario de conmutación por error.</p>
<p>Si la implementación incluye una cantidad significativa de tráfico de audio o vídeo, el rendimiento del servidor puede verse afectado con más de 2500 usuarios por servidor. En este caso, debe considerar la posibilidad de agregar servidores Standard Edition o de ir a Lync Server Enterprise Edition.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="front-end-server"></a>Servidor front-end

<div>


> [!NOTE]  
> No se admiten agrupaciones extendidas para este rol de servidor.



</div>

En un grupo de servidores front-end, debe disponer de un servidor front-end para cada 6.660 usuarios alojados en el grupo, suponiendo que Hyper-Threading está habilitado en todos los servidores del grupo, y que el hardware del servidor cumpla con las recomendaciones de las [plataformas de hardware de servidor para Lync Server 2013](lync-server-2013-server-hardware-platforms.md). La cantidad máxima de usuarios de un grupo de servidores front-end es de 80.000, suponiendo que Hyper-Threading está habilitado en todos los servidores del grupo. Si tiene más de 80.000 usuarios en un sitio, puede implementar más de un grupo de servidores front-end.

Cuando se tiene en cuenta el número de usuarios en un grupo de servidores front-end, incluya los usuarios alojados en los equipos de las sucursales que sean revivientes y los servidores de sucursal con supervivencia que estén asociados a este grupo de servidores front-end.

Cuando un servidor activo no está disponible, sus conexiones se transfieren automáticamente al resto de los servidores del grupo. Por ejemplo, si tiene 30.000 usuarios y cinco servidores front-end, entonces si un servidor no está disponible, las conexiones de los usuarios de 6000 deben transferirse a los otros cuatro servidores. Cada uno de los cuatro servidores restantes tendrá 7500 usuarios, que es un número mayor que el recomendado.

Si en su lugar ha empezado con seis servidores front-end para los usuarios de 30.000 y, posteriormente, uno de ellos no estaba disponible, se moverá un total de 5000 usuarios a los cinco servidores restantes. Estos cinco servidores usarán a cada uno de los usuarios 6000, que se encuentra en el intervalo recomendado.

El número máximo de usuarios en un grupo de servidores front-end es de 80.000. La cantidad máxima de servidores frontales en un grupo es de 12.

En el caso de un grupo de servidores front-end con usuarios de 80.000, doce servidores front-end son suficientes para el rendimiento, en las implementaciones típicas que siguen los [modelos de usuario en Lync Server 2013](lync-server-2013-user-models.md). Las implementaciones diseñadas para admitir la conmutación por error de recuperación ante desastres suponen que se puede hospedar un máximo de 40.000 usuarios en cada uno de los dos grupos de aplicaciones para usuario emparejados, en el que cada grupo tiene suficientes servidores frontales para acomodar a los usuarios en los dos grupos si es necesario que se produzca un error en un bloque a la otra.

El número de usuarios admitidos por un buen rendimiento de un grupo de servidores front-end determinado puede diferir de estos números por los siguientes motivos:

  - El hardware de los servidores front-end no cumple con las recomendaciones de las [plataformas de hardware de servidor para Lync Server 2013](lync-server-2013-server-hardware-platforms.md).

  - El uso de su organización difiere significativamente de los modelos de usuario, como, por ejemplo, mucho más tráfico de conferencias.

<div>


> [!IMPORTANT]  
> En Lync Server 2013, las bases de datos de presencia ahora se encuentran en los servidores de aplicaciones para el usuario, a diferencia de Lync Server 2010, donde se hospedan en el servidor back-end. Esto significa que el rendimiento de disco y la capacidad de los servidores front-end no deben verse comprometidos en las recomendaciones mencionadas anteriormente en esta sección y en las <A href="lync-server-2013-server-hardware-platforms.md">plataformas de hardware de servidor para Lync Server 2013</A>, independientemente del número de usuarios alojados en los servidores front-end.



</div>

En la tabla siguiente se muestra el ancho de banda medio para mensajería instantánea y presencia, dado el modelo de usuario, según se define en los [modelos de usuario de Lync Server 2013](lync-server-2013-user-models.md).


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Ancho de banda medio por usuario</th>
<th>Requisitos de ancho de banda por servidor front-end con usuarios de 6.660</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>1,3 Kbps</p></td>
<td><p>13 Mbps</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> Para mejorar el rendimiento de los medios de la funcionalidad de servidor de mediación y conferencias A/V, en los servidores front-end, debe habilitar el escalado de recepción (RSS) en los adaptadores de red de los servidores front-end. RSS permite que los paquetes entrantes se administren en paralelo por varios procesadores en el servidor. Para obtener más información, consulte "mejoras de escala en el lado de recepción en Windows <A href="http://go.microsoft.com/fwlink/p/?linkid=268731">http://go.microsoft.com/fwlink/p/?linkId=268731</A>Server 2008" en. Para más información sobre cómo habilitar RSS, vea la documentación de su adaptador de red.



</div>

</div>

<div>

## <a name="conferencing-maximums"></a>Máximos de conferencia

Dado el modelo de usuario en el que un 5% de los usuarios de un grupo puede estar en una conferencia en un momento dado, un grupo de usuarios de 80.000 podría tener unos 4.000 usuarios en conferencias al mismo tiempo. Se espera que esas conferencias sean una combinación de varios medios (algunas, solo de mensajería instantánea; otras, de mensajería instantánea con audio; otras, de audio y vídeo, por ejemplo) y diferentes números de participantes. No hay un límite rígido para el número real de conferencias permitidas y el uso real determina el rendimiento real. Por ejemplo, si su organización tiene muchas más conferencias de modo mixto de lo que se supone en el modelo de usuario, es posible que tenga que implementar más servidores front-end o servidores de conferencia A/V con las recomendaciones de este documento. Para obtener más información sobre los supuestos en el modelo de usuario, consulte [modelos de usuario en Lync Server 2013](lync-server-2013-user-models.md).

El tamaño máximo de conferencia admitido hospedado por un grupo de front-end de Lync Server 2013 que también hospeda usuarios es de 250 participantes. Mientras se celebra una conferencia de 250 usuarios, el grupo puede admitir también otras conferencias, con un total del 5 % de los usuarios del grupo en conferencias simultáneas. Por ejemplo, en un grupo de doce servidores front-end y usuarios de 80.000, mientras se celebra la Conferencia 250-User, Lync Server admite 3.750 usuarios que participen en conferencias más pequeñas.

Independientemente del número de usuarios alojados en el grupo de servidores front-end o del servidor Standard Edition, Lync Server admite un mínimo de 125 otros usuarios que participen en conferencias más pequeñas en el mismo Pool o servidor que hospeda una conferencia 250-usuario.

Para habilitar conferencias con usuarios de 250 y 1000, puede configurar un grupo de servidores front-end independiente solo para hospedar esas conferencias. Este grupo de servidores front-end no alojará ningún usuario. Para obtener más información, consulte [compatibilidad con reuniones grandes con Lync Server 2013](lync-server-2013-supporting-large-meetings.md).

Si su organización tiene muchas más conferencias de modo mixto de lo que se supone en el modelo de usuario, es posible que tenga que implementar más servidores front-end que las recomendaciones de este documento (hasta un límite de 12 FEs). Para obtener más información sobre los supuestos en el modelo de usuario, consulte [modelos de usuario en Lync Server 2013](lync-server-2013-user-models.md).

</div>

<div>

## <a name="edge-server"></a>Servidor perimetral

<div>


> [!NOTE]  
> No se admiten agrupaciones extendidas para este rol de servidor.



</div>

Debe implementar un servidor perimetral para cada 12.000 usuarios remotos que tengan acceso a un sitio al mismo tiempo. Como mínimo, recomendamos dos servidores perimetrales para una alta disponibilidad. En estas recomendaciones se supone que el hardware de los servidores perimetrales cumple con las recomendaciones de las [plataformas de hardware de servidor para Lync Server 2013](lync-server-2013-server-hardware-platforms.md).

Cuando tenga en cuenta el número de usuarios de los servidores perimetrales, incluya los usuarios alojados en los equipos de las sucursales que sean revivientes y los servidores de sucursal con la supervivencia que están asociados a un grupo de servidores front-end en este sitio.

<div>


> [!NOTE]  
> Para mejorar el rendimiento del servicio perimetral de conferencia A/V en los servidores perimetrales, debe habilitar el escalado de recepción (RSS) en los adaptadores de red de los servidores perimetrales. RSS permite que los paquetes entrantes se administren en paralelo por varios procesadores en el servidor. Para obtener más información, consulte "mejoras de escala en el lado de recepción en Windows <A href="http://go.microsoft.com/fwlink/p/?linkid=268731">http://go.microsoft.com/fwlink/p/?linkId=268731</A>Server 2008" en. Para más información sobre cómo habilitar RSS, vea la documentación de su adaptador de red.



</div>

</div>

<div>

## <a name="director"></a>Director

<div>


> [!NOTE]  
> No se admiten agrupaciones extendidas para este rol de servidor.



</div>

Si implementa el rol de servidor Director, se recomienda implementar un director por cada 12.000 usuarios remotos que tengan acceso a un sitio al mismo tiempo. Como mínimo, recomendamos dos directores para una alta disponibilidad. En estas recomendaciones se supone que el hardware de los servidores perimetrales cumple con las recomendaciones de las [plataformas de hardware de servidor para Lync Server 2013](lync-server-2013-server-hardware-platforms.md).

Cuando tenga en cuenta la cantidad de usuarios para los directores, incluya los usuarios alojados en los equipos de las sucursales que sean revivientes y en los servidores de sucursal con la supervivencia que están asociados a un grupo de servidores front-end en este sitio.

</div>

<div>

## <a name="mediation-server"></a>Servidor de mediación

<div>


> [!NOTE]  
> No se admiten agrupaciones extendidas para este rol de servidor.



</div>

Si Collocate Server Mediation with front end Server, Media Server se ejecuta en todos los servidores front end del grupo y debe proporcionar la capacidad suficiente para los usuarios del grupo.

Si implementa un grupo de servidores de mediación independiente, entonces la cantidad de servidores de mediación que se van a implementar depende de muchos factores, incluido el hardware usado para el servidor de mediación, el número de usuarios de VoIP que tiene, el número de puertas de enlace y el número de puertas de enlace de cada grupo de servidores de mediación controles, el tráfico de horas ocupado a través de estas puertas de enlace y el porcentaje de llamadas con medios que omiten el servidor de mediación.

En las siguientes tablas se ofrecen instrucciones sobre cuántas llamadas simultáneas puede controlar un servidor de mediación, suponiendo que el hardware de los servidores de mediación cumpla con los requisitos de las [plataformas de hardware de servidor para Lync Server 2013](lync-server-2013-server-hardware-platforms.md) y que Hyper-Threading está habilitado. Para obtener más información sobre la escalabilidad del servidor de mediación, consulte estimar el [uso de voz y el tráfico para Lync server 2013](lync-server-2013-estimating-voice-usage-and-traffic.md) y las [directrices de implementación para servidor de mediación en Lync Server 2013](lync-server-2013-deployment-guidelines-for-mediation-server.md).

En todas las tablas siguientes se supone el uso tal como se resume en los [modelos de usuario en Lync Server 2013](lync-server-2013-user-models.md).

### <a name="stand-alone-mediation-server-capacity-70-internal-users-30-external-users-with-non-bypass-call-capacity-media-transcoding-performed-by-mediation-server"></a>Capacidad de servidor de mediación independiente: 70% usuarios internos, 30% usuarios externos con capacidad de llamada sin derivación (transcodificación multimedia realizada por el servidor de mediación)

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Hardware de servidor</th>
<th>Número máximo de llamadas</th>
<th>Número máximo de líneas T1</th>
<th>Número máximo de líneas E1</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Procesador dual, seis núcleos, CPU con Hyper-Threading a 2,26 GHz <strong>con la tecnología Hyper-Threading deshabilitada</strong>, con 32 GB de memoria y una tarjeta adaptadora de red de doble puerto.</p></td>
<td><p>1100</p></td>
<td><p>46</p></td>
<td><p>35</p></td>
</tr>
<tr class="even">
<td><p>Procesador dual, seis núcleos, CPU hyper-threaded a 2,26 GHz, con 32 GB de memoria y una tarjeta adaptadora de red de doble puerto.</p></td>
<td><p>1500</p></td>
<td><p>63</p></td>
<td><p>47</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> Aunque los servidores con 32 GB de memoria se usan para pruebas de rendimiento, los servidores con 16 GB de memoria son compatibles con el servidor de mediación independiente y son suficientes para proporcionar el rendimiento que se muestra en esta tabla.



</div>

### <a name="mediation-server-capacity-mediation-server-collocated-with-front-end-server-70-internal-users-30-external-users-non-bypass-call-capacity-media-processing-performed-by-mediation-server"></a>Capacidad del servidor de mediación (servidor de mediación en el servidor front-end) 70% usuarios internos, 30% de los usuarios externos, capacidad de llamada sin omisión (procesamiento de multimedia realizado por el servidor de mediación)

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Hardware de servidor</th>
<th>Número máximo de llamadas</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Procesador dual, seis núcleos, CPU hyper-threaded a 2,26 GHz, con 32 GB de memoria y 4 tarjetas adaptadoras de red de 1 GB.</p></td>
<td><p>150</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> Este número es mucho menor que los números del servidor de mediación independiente porque el servidor front-end tiene que manejar otras características y funciones para los usuarios de 6600 alojados en ella, además de la transcodificación necesaria para las llamadas de voz.



</div>

<div>


> [!NOTE]  
> Para mejorar el rendimiento del servidor de mediación, debe habilitar el escalado de recepción (RSS) en los adaptadores de red de los servidores de mediación. RSS permite que los paquetes entrantes se administren en paralelo por varios procesadores en el servidor. Para obtener más información, consulte "mejoras de escala en el lado de recepción en Windows <A href="http://go.microsoft.com/fwlink/p/?linkid=268731">http://go.microsoft.com/fwlink/p/?linkId=268731</A>Server 2008" en. Para más información sobre cómo habilitar RSS, vea la documentación de su adaptador de red.



</div>

</div>

<div>

## <a name="back-end-server"></a>Servidor back-end

En Lync Server 2013, las bases de datos de presencia se encuentran en los servidores front-end en lugar de en el servidor back-end. Esto ha provocado un requisito mucho más sencillo para cada servidor back-end en Lync Server 2013, equivalente al requisito de hardware para el servidor front-end. Compare esto con Lync Server 2010, en el que el servidor back-end debe ser un servidor mucho más importante con 25 discos. Sin embargo, la carga de trabajo de los servidores de servicios de fondo sigue siendo tal que no es posible cumplir con las recomendaciones de hardware enumeradas anteriormente en esta sección y en las [plataformas de hardware de servidor para Lync Server 2013](lync-server-2013-server-hardware-platforms.md).

Para ofrecer una alta disponibilidad de su servidor back-end, recomendamos implementar el reflejo de servidor. Para obtener más información, consulte [back end Server High Availability in Lync server 2013](lync-server-2013-back-end-server-high-availability.md).

</div>

<div>

## <a name="monitoring-and-archiving"></a>Supervisión y archivado

En Lync Server 2013, si implementa la supervisión o el archivado, la funcionalidad front-end de estos servicios se ejecuta en los servidores front-end, en lugar de en roles de servidor diferentes. La supervisión y el archivado siguen usando su propia tienda de bases de datos, independiente de la tienda back-end. Como alternativa, si tiene Exchange 2013 implementado, puede almacenar datos de archivado de mensajes instantáneos en Exchange en lugar de en una tienda SQL dedicada.

En la tabla siguiente se indica cuánto almacenamiento de base de datos se necesita aproximadamente por usuario y por día para los datos de supervisión y archivado.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<tbody>
<tr class="odd">
<td></td>
<td><p><strong>CDR (Supervisión)</strong></p></td>
<td><p><strong>QoE (Supervisión)</strong></p></td>
<td><p><strong>Archivado</strong></p></td>
</tr>
<tr class="even">
<td><p>Espacio en disco necesario por usuario y por día</p></td>
<td><p>49 KB</p></td>
<td><p>28 KB</p></td>
<td><p>57 KB</p></td>
</tr>
</tbody>
</table>


Durante las pruebas de rendimiento, Microsoft usó el hardware de la tabla siguiente para el servidor de bases de datos de supervisión y archivado. Las pruebas recopilaron los datos de dos grupos de servidores front-end, cada uno de los cuales contiene 80.000 usuarios.

### <a name="hardware-used-in-monitoring-and-archiving-performance-testing"></a>Hardware utilizado en las pruebas de rendimiento de supervisión y archivado

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Componente de hardware</th>
<th>Recomendado</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>CPU</p></td>
<td><p>Procesador dual de 64 bits, de seis núcleos, 2,26 gigahercios (GHz) o superior</p></td>
</tr>
<tr class="even">
<td><p>Memoria</p></td>
<td><p>48 gigabytes (GB).</p></td>
</tr>
<tr class="odd">
<td><p>Disco</p></td>
<td><p>25 discos duros de 10.000 r.p.m. con 300 GB en cada disco, con la siguiente configuración</p>
<h3 id="section-3"> </h3>
<div>
<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Unidad</strong></p></td>
<td><p><strong>Configuración RAID</strong></p></td>
<td><p><strong>Número de discos</strong></p></td>
</tr>
<tr class="even">
<td><p>Archivos de datos de las bases de datos de CDR, QoE y archivado, en una sola unidad</p></td>
<td><p>1+0</p></td>
<td><p>apartado</p></td>
</tr>
<tr class="odd">
<td><p>Archivo de registro de la base de datos CDR</p></td>
<td><p>1</p></td>
<td><p>2</p></td>
</tr>
<tr class="even">
<td><p>Archivo de registro de la base de datos QoE</p></td>
<td><p>1</p></td>
<td><p>2</p></td>
</tr>
<tr class="odd">
<td><p>Archivo de registro de la base de datos de archivado</p></td>
<td><p>1</p></td>
<td><p>2</p></td>
</tr>
</tbody>
</table>

</div></td>
</tr>
<tr class="even">
<td><p>Red</p></td>
<td><ul>
<li><p>1 adaptador de red de puerto dual, 1 Gbps o superior (2 recomendados, lo que requiere la formación de equipos con una sola dirección MAC y una sola dirección IP).</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="in-this-section"></a>En esta sección

  - [Estimar el uso de voz y el tráfico para Lync Server 2013](lync-server-2013-estimating-voice-usage-and-traffic.md)

  - [Instrucciones de implementación para el servidor de mediación en Lync Server 2013](lync-server-2013-deployment-guidelines-for-mediation-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

