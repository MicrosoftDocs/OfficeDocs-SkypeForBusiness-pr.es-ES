---
title: Lync Server 2013 planear la capacidad con los modelos de usuario
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Capacity planning using the user models
ms:assetid: 902ab23e-94d6-482a-9d6e-c0b28dc3e03d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615015(v=OCS.15)
ms:contentKeyID: 49733733
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d315de4f8b18a5ecbeabe7ba29231c70ff893e8a
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48508147"
---
# <a name="capacity-planning-for-lync-server-2013-using-the-user-models"></a>Planeación de la capacidad para Lync Server 2013 mediante los modelos de usuario

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-01-14_

En esta sección se proporcionan instrucciones sobre cuántos servidores se necesitan en un sitio para el número de usuarios de ese sitio, según el uso descrito en [modelos de usuario en Lync Server 2013](lync-server-2013-user-models.md).

<div>

## <a name="tested-hardware-platform"></a>Plataforma de hardware probada

Todas las recomendaciones de implementación y los resultados de rendimiento de esta sección se basan en las pruebas de rendimiento en los servidores que ejecutan el hardware descrito en la tabla siguiente. Le recomendamos que use hardware similar. Si usa un hardware menos eficaz, puede tener problemas de funcionalidad o un rendimiento deficiente. Tenga en cuenta que estas recomendaciones de hardware son más altas que las de las versiones anteriores de Lync Server.

### <a name="hardware-used-in-performance-testing"></a>Hardware usado en las pruebas de rendimiento

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
<td><p>Procesador dual de 64 bits, de seis núcleos, 2,26 gigahercios (GHz) o superior.</p>
<p>Los roles de servidor de Lync Server no admiten los procesadores Intel Itanium.</p></td>
</tr>
<tr class="even">
<td><p>Memoria</p></td>
<td><p>32 gigabytes (GB).</p></td>
</tr>
<tr class="odd">
<td><p>Disco</p></td>
<td><ul>
<li><p>8 o más unidades de disco duro 10.000-RPM con al menos 72 GB de espacio libre en disco.</p>
<p>Dos de los discos deben usar RAID 1 y seis deben usar RAID 10.</p>
<p>- O</p></li>
<li><p>Unidades de estado sólido (SSD) con rendimiento igual al de 8 unidades de disco mecánicas de 10.000 rpm.</p></li>
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

La tabla siguiente resume estas recomendaciones.


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
<td><p>Grupo de servidores front-end con doce servidores front-end y un servidor back-end o un par reflejado de servidores back-end.</p></td>
<td><p>80.000 usuarios únicos con sesión iniciada simultáneamente, más el 50% de puntos de presencia (MPOP) que representan instancias no móviles, más el 40% de usuarios habilitados para movilidad para un total de 152.000 puntos de conexión.</p></td>
</tr>
<tr class="even">
<td><p>Conferencia A/V</p></td>
<td><p>El servicio de conferencia A/V proporcionado por un grupo de servidores front-end es compatible con las conferencias del grupo suponiendo un tamaño máximo de conferencia de 250 usuarios y solo una conferencia grande en ejecución cada vez.</p>
<div>

> [!NOTE]  
> Además, puede admitir conferencias grandes de entre 250 y 1000 usuarios mediante la implementación de un grupo de servidores front-end independiente con dos servidores front-end para hospedar las conferencias grandes. Para obtener más información, consulte <A href="lync-server-2013-supporting-large-meetings.md">Supporting Large Meetings Using Lync Server 2013</A>.


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
<td><p>En Lync Server 2013, los servicios front-end de supervisión y archivado ahora se ejecutan en cada servidor front-end, en lugar de en roles de servidor independientes.</p>
<p>La supervisión y el archivado siguen requiriendo sus propios almacenes de bases de datos. Si también ejecuta Exchange 2013, puede mantener los datos de archivado en Exchange, en lugar de hacerlo en una base de datos SQL dedicada.</p></td>
</tr>
<tr class="even">
<td><p>Un servidor de mediación</p></td>
<td><p>El servidor de mediación combinado con el servidor front-end se ejecuta en cada servidor front-end de un grupo de servidores y debe proporcionar suficiente capacidad para los usuarios del grupo. Para un servidor de mediación independiente, consulte la sección "servidor de mediación" más adelante en este tema.</p></td>
</tr>
<tr class="odd">
<td><p>Un servidor Standard Edition</p></td>
<td><p>Se recomienda encarecidamente que si usa servidores Standard Edition para hospedar usuarios, use siempre dos servidores, emparejados con las recomendaciones de <a href="lync-server-2013-planning-for-high-availability-and-disaster-recovery.md">planeación de alta disponibilidad y recuperación ante desastres en Lync Server 2013</a>. Cada servidor del par puede hospedar hasta 2.500 usuarios y, si se produce un error en un servidor, el servidor restante puede admitir 5.000 usuarios en un escenario de conmutación por error.</p>
<p>Si la implementación incluye una cantidad significativa de tráfico de audio o vídeo, el rendimiento del servidor puede sufrir más de 2.500 usuarios por servidor. En este caso, considere la posibilidad de agregar más servidores Standard Edition o de migrar a Lync Server Enterprise Edition.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="front-end-server"></a>Servidor front-end

<div>


> [!NOTE]  
> Los grupos de servidores extendidos no son compatibles con este rol de servidor.



</div>

En un grupo de servidores front-end, debe disponer de un servidor front-end para cada 6.660 usuarios alojados en el grupo de servidores, suponiendo que la tecnología Hyper-Threading está habilitada en todos los servidores del grupo y que el hardware del servidor cumple con las recomendaciones de las [plataformas de hardware del servidor para Lync Server 2013](lync-server-2013-server-hardware-platforms.md). El número máximo de usuarios en un grupo de servidores front-end es de 80.000, suponiendo que la tecnología Hyper-Threading está habilitada en todos los servidores del grupo. Si tiene más de 80.000 usuarios en un sitio, puede implementar más de un grupo de servidores front-end.

Cuando calcule el número de usuarios de un grupo de servidores front-end, incluya los usuarios hospedados en aplicaciones de sucursal con funciones de supervivencia y servidores de sucursal con funciones de supervivencia asociados a este grupo de servidores front-end.

Cuando un servidor activo no está disponible, sus conexiones se transfieren automáticamente a los demás servidores del grupo. Por ejemplo, si tiene 30.000 usuarios y cinco servidores front-end, entonces si un servidor no está disponible, las conexiones de 6000 usuarios deben transferirse a los otros cuatro servidores. Los cuatro servidores restantes tendrán 7500 usuarios, que es un número mayor que el recomendado.

Si en su lugar ha empezado con seis servidores front-end para los usuarios de 30.000 y, posteriormente, uno dejó de estar disponible, se moverá un total de 5000 usuarios a los cinco servidores restantes. Estos cinco servidores tendrán cada host 6000 usuarios, que se encuentra en el intervalo recomendado.

La cantidad máxima de usuarios en un grupo de servidores front-end es 80.000. El número máximo de servidores front-end en un grupo es de 12.

Para un grupo de servidores front-end con 80.000 usuarios, doce servidores front-end son suficientes para el rendimiento, en implementaciones típicas que sigan los [modelos de usuario en Lync Server 2013](lync-server-2013-user-models.md). Las implementaciones diseñadas para admitir la conmutación por error de recuperación ante desastres suponen que se puede hospedar un máximo de 40.000 usuarios en cada uno de los dos grupos de servidores front-end emparejados, en los que cada grupo tiene suficientes servidores front-end para acomodar a los usuarios en ambos grupos, en caso de que un grupo necesite conmutar por error al otro.

El número de usuarios que un grupo de servidores front-end concreto admite con un buen rendimiento puede diferir de estos números por los motivos siguientes:

  - El hardware de los servidores front-end no cumple con las recomendaciones de las [plataformas de hardware de servidor para Lync Server 2013](lync-server-2013-server-hardware-platforms.md).

  - Si el uso de su organización difiere en gran medida de los modelos de usuario, por ejemplo, con un tráfico de conferencias significativamente mayor.

<div>


> [!IMPORTANT]  
> En Lync Server 2013, las bases de datos de presencia ahora están hospedadas en los servidores front-end, a diferencia de Lync Server 2010, donde se hospedan en el servidor back-end. Esto significa que el rendimiento de disco y la capacidad de los servidores front-end no se verán comprometidos con las recomendaciones enumeradas anteriormente en esta sección y en las <A href="lync-server-2013-server-hardware-platforms.md">plataformas de hardware de servidor para Lync Server 2013</A>, independientemente del número de usuarios hospedados en los servidores front-end.



</div>

En la tabla siguiente se muestra el ancho de banda medio para mensajería instantánea y presencia, según el modelo de usuario, como se define en los [modelos de usuario en Lync Server 2013](lync-server-2013-user-models.md).


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Ancho de banda medio por usuario</th>
<th>Requisitos de ancho de banda por servidor front-end con 6.660 usuarios</th>
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
> Para mejorar el rendimiento de los medios en los servidores front-end de conferencias A/V y servidores de mediación colocalizados, debe habilitar el ajuste de escala en el lado de recepción (RSS) en los adaptadores de red de los servidores front-end. El RSS permite administrar los paquetes entrantes en paralelo con varios procesadores del servidor. Para obtener más información, vea "mejoras en el ajuste de escala en lado de recepción en Windows Server 2008" en <A href="https://go.microsoft.com/fwlink/p/?linkid=268731">https://go.microsoft.com/fwlink/p/?linkId=268731</A> . Para obtener más información sobre cómo habilitar RSS, consulte la documentación de su adaptador de red.



</div>

</div>

<div>

## <a name="conferencing-maximums"></a>Máximos de conferencia

Dado el modelo de usuario que establece que el 5% de los usuarios de un grupo de servidores puede estar en una conferencia en cualquier momento dado, un grupo de 80.000 usuarios podría tener unos 4.000 usuarios en conferencias en un determinado momento. Se espera que esas conferencias sean una combinación de varios medios (algunas, solo de MI; otras, de MI con audio; otras, de audio y vídeo, por ejemplo) y diferentes números de participantes. No hay ningún límite fijo para el número real de conferencias permitidas y el uso real determinará el rendimiento real. Por ejemplo, si su organización tiene muchas más conferencias de modo combinado de lo que supone el modelo de usuario, probablemente necesite implementar más servidores front-end o servidores de conferencia A/V del número recomendado en este documento. Para obtener más información sobre los supuestos del modelo de usuario, vea [User Models in Lync Server 2013](lync-server-2013-user-models.md).

El tamaño máximo de conferencia compatible hospedado en un grupo de servidores front-end de Lync Server 2013 normal que también hospeda a los usuarios es de 250 participantes. Mientras está ocurriendo una conferencia de 250 usuarios, el grupo todavía admite otras conferencias, de modo que un total del 5% de los usuarios del grupo está en conferencias simultáneas. Por ejemplo, en un grupo de doce servidores front-end y 80.000 usuarios, mientras se está produciendo la Conferencia 250-User, Lync Server admite 3.750 otros usuarios que participen en conferencias más pequeñas.

Independientemente del número de usuarios alojados en el grupo de servidores front-end o del servidor Standard Edition, Lync Server admite un mínimo de 125 otros usuarios que participan en conferencias más pequeñas en el mismo grupo o servidor que hospeda una conferencia 250-User.

Para habilitar las conferencias entre los usuarios de 250 y 1000, puede configurar un grupo de servidores front-end independiente solo para hospedar esas conferencias. Este grupo de servidores front-end no hospedará ningún usuario. Para obtener más información, consulte [Supporting Large Meetings Using Lync Server 2013](lync-server-2013-supporting-large-meetings.md).

Si su organización tiene muchas más conferencias de modo mixto del que se supone en el modelo de usuario, es posible que deba implementar más servidores front-end que las recomendaciones de este documento (hasta un límite de 12 FEs). Para obtener más información sobre los supuestos del modelo de usuario, vea [User Models in Lync Server 2013](lync-server-2013-user-models.md).

</div>

<div>

## <a name="edge-server"></a>Servidor perimetral

<div>


> [!NOTE]  
> Los grupos de servidores extendidos no son compatibles con este rol de servidor.



</div>

Debe implementar un servidor perimetral para cada 12.000 usuarios remotos que tendrán acceso a un sitio de forma simultánea. Como mínimo, se recomienda el uso de dos servidores perimetrales para obtener alta disponibilidad. En estas recomendaciones se presupone que el hardware de los servidores perimetrales cumple con las recomendaciones de las [plataformas de hardware de servidor para Lync Server 2013](lync-server-2013-server-hardware-platforms.md).

Cuando calcule el número de usuarios de los servidores perimetrales, incluya los usuarios hospedados en aplicaciones de sucursal con funciones de supervivencia y servidores de sucursal con funciones de supervivencia de las sucursales que estén asociados a un grupo de servidores front-end en este sitio.

<div>


> [!NOTE]  
> Para mejorar el rendimiento del servicio de conferencia A/V en los servidores perimetrales, debe habilitar el ajuste de escala en lado de recepción (RSS) en los adaptadores de red de los servidores perimetrales. El RSS permite administrar los paquetes entrantes en paralelo con varios procesadores del servidor. Para obtener más información, vea "mejoras en el ajuste de escala en lado de recepción en Windows Server 2008" en <A href="https://go.microsoft.com/fwlink/p/?linkid=268731">https://go.microsoft.com/fwlink/p/?linkId=268731</A> . Para obtener más información sobre cómo habilitar RSS, consulte la documentación de su adaptador de red.



</div>

</div>

<div>

## <a name="director"></a>Director

<div>


> [!NOTE]  
> Los grupos de servidores extendidos no son compatibles con este rol de servidor.



</div>

Si implementa el rol de servidor Director, le recomendamos que implemente un director por cada 12.000 usuarios remotos que tendrán acceso a un sitio de forma simultánea. Como mínimo, se recomienda el uso de dos directores para obtener alta disponibilidad. En estas recomendaciones se presupone que el hardware de los servidores perimetrales cumple con las recomendaciones de las [plataformas de hardware de servidor para Lync Server 2013](lync-server-2013-server-hardware-platforms.md).

Cuando calcule el número de usuarios de los directores, incluya los usuarios hospedados en aplicaciones de sucursal con funciones de supervivencia y servidores de sucursal con funciones de supervivencia de las sucursales que estén asociados a un grupo de servidores front-end en este sitio.

</div>

<div>

## <a name="mediation-server"></a>Servidor de mediación

<div>


> [!NOTE]  
> Los grupos de servidores extendidos no son compatibles con este rol de servidor.



</div>

Si combinar servidor de mediación con el servidor front-end, el servidor de mediación se ejecuta en todos los servidores front-end del grupo y debe proporcionar suficiente capacidad para los usuarios del grupo.

Si implementa un grupo de servidores de mediación independiente, entonces el número de servidores de mediación que se van a implementar depende de muchos factores, como el hardware usado para el servidor de mediación, el número de usuarios de VoIP que tiene, el número de puertas de enlace que controla cada grupo de servidores de mediación, el tráfico de horas de disponibilidad a través de dichas puertas de enlace y el

En las tablas siguientes se proporciona una guía para conocer cuántas llamadas simultáneas puede controlar un servidor de mediación, suponiendo que el hardware de los servidores de mediación cumpla los requisitos de las [plataformas de hardware de servidor para Lync Server 2013](lync-server-2013-server-hardware-platforms.md) y que la tecnología Hyper-Threading esté habilitada. Para obtener más información sobre la escalabilidad del servidor de mediación, consulte [Estimating Voice Usage and Traffic for Lync server 2013](lync-server-2013-estimating-voice-usage-and-traffic.md) y [Deployment Guidelines for Mediation Server in Lync Server 2013](lync-server-2013-deployment-guidelines-for-mediation-server.md).

En las tablas siguientes se supone que el uso se resume en los [modelos de usuario en Lync Server 2013](lync-server-2013-user-models.md).

### <a name="stand-alone-mediation-server-capacity-70-internal-users-30-external-users-with-non-bypass-call-capacity-media-transcoding-performed-by-mediation-server"></a>Capacidad de un servidor de mediación independiente: 70% de usuarios internos, 30% de usuarios externos con capacidad de llamada sin desvío (transcodificación multimedia realizada por el servidor de mediación)

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
<td><p>Procesador dual, núcleo hexadecimal, CPU Hyper-threaded de 2,26 GHz <strong>con la tecnología Hyper-Threading deshabilitada</strong>, con 32 GB de memoria y una tarjeta adaptadora de red de doble puerto.</p></td>
<td><p>1100</p></td>
<td><p>46</p></td>
<td><p>35</p></td>
</tr>
<tr class="even">
<td><p>Procesador dual, núcleo hexadecimal, CPU Hyper-threaded de 2,26 GHz, con 32 GB de memoria y una tarjeta adaptadora de red de doble puerto.</p></td>
<td><p>1500</p></td>
<td><p>63</p></td>
<td><p>47</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> Aunque se utilizaron servidores con 32 GB de memoria para la prueba, se pueden utilizar servidores con 16 GB de memoria como servidores de mediación independientes y son suficientes para ofrecer el rendimiento mostrado en esta tabla.



</div>

### <a name="mediation-server-capacity-mediation-server-collocated-with-front-end-server-70-internal-users-30-external-users-non-bypass-call-capacity-media-processing-performed-by-mediation-server"></a>Capacidad del servidor de mediación (servidor de mediación combinado con el servidor front-end) 70% de usuarios internos, 30% de usuarios externos, capacidad de llamada sin omisiones (procesamiento de medios realizado por el servidor de mediación)

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
<td><p>Procesador dual, núcleo hexadecimal, CPU Hyper-threaded de 2,26 GHz, con 32 GB de memoria y 2 tarjetas adaptadoras de red de 1 GB.</p></td>
<td><p>150</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> Este número es mucho menor que los números del servidor de mediación independiente, ya que el servidor front-end tiene que administrar otras características y funciones para los usuarios de 6600 que se hospedan en él, además de la transcodificación necesaria para las llamadas de voz.



</div>

<div>


> [!NOTE]  
> Para mejorar el rendimiento del servidor de mediación, debe habilitar el ajuste de escala en el lado de recepción (RSS) en los adaptadores de red de los servidores de mediación. El RSS permite administrar los paquetes entrantes en paralelo con varios procesadores del servidor. Para obtener más información, vea "mejoras en el ajuste de escala en lado de recepción en Windows Server 2008" en <A href="https://go.microsoft.com/fwlink/p/?linkid=268731">https://go.microsoft.com/fwlink/p/?linkId=268731</A> . Para obtener más información sobre cómo habilitar RSS, consulte la documentación de su adaptador de red.



</div>

</div>

<div>

## <a name="back-end-server"></a>Servidor back-end

En Lync Server 2013, las bases de datos de presencia se encuentran en los servidores front-end en lugar de en el servidor back-end. Esto ha dado como resultado un requisito mucho más sencillo para cada servidor back-end en Lync Server 2013, equivalente al requisito de hardware para el servidor front-end. Compare esto con Lync Server 2010, donde era necesario que el servidor back-end fuera un servidor mucho más importante con 25 discos. Sin embargo, la carga de trabajo de los servidores back-end todavía es tal que no se deben superar las recomendaciones de hardware enumeradas anteriormente en esta sección y en las [plataformas de hardware de servidor para Lync Server 2013](lync-server-2013-server-hardware-platforms.md).

Para proporcionar alta disponibilidad del servidor back-end, se recomienda implementar la creación de reflejos del servidor. Para obtener más información, vea [back end Server High Availability in Lync server 2013](lync-server-2013-back-end-server-high-availability.md).

</div>

<div>

## <a name="monitoring-and-archiving"></a>Supervisión y archivado

En Lync Server 2013, si implementa la supervisión o el archivado, la funcionalidad front-end de estos servicios se ejecuta en los servidores front-end, en lugar de en roles de servidor independientes. La supervisión y el archivado siguen usando su propio almacén de base de datos, independiente del almacén back-end. Como alternativa, si tiene implementado Exchange 2013, puede almacenar datos de archivado de mensajes instantáneos en Exchange en lugar de hacerlo en un almacén de SQL dedicado.

En la tabla siguiente se indica aproximadamente cuánto almacenamiento de base de datos se necesita por usuario y día para la supervisión y archivado de datos.


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
<td><p><strong>CDR (supervisión)</strong></p></td>
<td><p><strong>QoE (supervisión)</strong></p></td>
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


Microsoft usó el hardware de la siguiente tabla para el servidor de bases de datos para la supervisión y el archivado durante las pruebas de rendimiento. Las pruebas recopilaron los datos de dos grupos de servidores front-end, cada uno de los cuales contenía 80.000 usuarios.

### <a name="hardware-used-in-monitoring-and-archiving-performance-testing"></a>Hardware usado en las pruebas de rendimiento de supervisión y archivado

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
<td><p>Procesador dual de 64 bits, de seis núcleos, 2,26 gigahercios (GHz) o superior.</p></td>
</tr>
<tr class="even">
<td><p>Memoria</p></td>
<td><p>48 gigabytes (GB)</p></td>
</tr>
<tr class="odd">
<td><p>Disco</p></td>
<td><p>unidades de disco duro 25 10.000-RPM con 300 GB en cada disco, con la siguiente configuración</p>
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
<td><p><strong>Drive</strong></p></td>
<td><p><strong>Configuración de RAID</strong></p></td>
<td><p><strong>Número de discos</strong></p></td>
</tr>
<tr class="even">
<td><p>CDR, QoE y archivos de datos de la base de datos de archivado en una única unidad</p></td>
<td><p>1 + 0</p></td>
<td><p>16 </p></td>
</tr>
<tr class="odd">
<td><p>El archivo de registro de la base de datos CDR</p></td>
<td><p>1</p></td>
<td><p>segundo</p></td>
</tr>
<tr class="even">
<td><p>El archivo de registro de la base de datos QoE</p></td>
<td><p>1</p></td>
<td><p>segundo</p></td>
</tr>
<tr class="odd">
<td><p>Archivo de registro de la base de datos de archivado</p></td>
<td><p>1</p></td>
<td><p>segundo</p></td>
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

