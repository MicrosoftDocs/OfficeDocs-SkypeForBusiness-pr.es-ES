---
title: 'Lync Server 2013: Planificar la capacidad con los modelos de usuario'
TOCTitle: Planificar la capacidad con los modelos de usuario
ms:assetid: 902ab23e-94d6-482a-9d6e-c0b28dc3e03d
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg615015(v=OCS.15)
ms:contentKeyID: 49889382
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Planificar la capacidad con los modelos de usuario para Lync Server 2013

 

_**Última modificación del tema:** 2016-12-08_

Esta sección sirve de guía para calcular cuántos servidores necesita en un sitio para la cantidad de usuarios que tenga ese sitio, según el uso descrito en [Modelos de usuario en Lync Server 2013](lync-server-2013-user-models.md).

## Plataforma de hardware probada

Todos los resultados de rendimiento y las recomendaciones de implementación de esta sección se basan en pruebas de rendimiento realizadas en servidores con el hardware descrito en la siguiente tabla. Recomendamos que utilice un hardware similar. Si usa un hardware menos eficaz, podría experimentar problemas de funcionalidad o un rendimiento insuficiente. Tenga en cuenta que estas recomendaciones de hardware son superiores a las de versiones anteriores de Lync Server.

### Hardware usado en pruebas de rendimiento

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
<li><p>8 o más unidades de disco duro de 10.000 r.p.m. con al menos 72 GB de espacio libre en disco.</p>
<p>Dos de los discos deben usar RAID 1 y seis deben usar RAID 10.</p>
<p>O BIEN:</p></li>
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


## Resumen de los resultados

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
<td><p>Grupo de servidores front-end con doce Servidores front-end y un Servidor back-end o un par reflejado de Servidores back-end.</p></td>
<td><p>80.000 usuarios únicos con sesión iniciada simultáneamente, más un 50% de múltiples puntos de presencia (MPOP) que representan instancias no móviles, más un 40% de los usuarios habilitados para movilidad, lo que hace un total de 152.000 extremos.</p></td>
</tr>
<tr class="even">
<td><p>Conferencia A/V</p></td>
<td><p>El servicio Conferencia A/V proporcionado por un Grupo de servidores front-end admite las conferencias del grupo, asumiendo un tamaño máximo de conferencia de 250 usuarios y solo una conferencia grande al mismo tiempo.</p>
<div>

> [!NOTE]
> Asimismo, puede admitir conferencias grandes de entre 250 y 1000 usuarios implementando un Grupo de servidores front-end diferente con dos Servidores front-end para hospedar las conferencias grandes. Para más información, consulte <A href="lync-server-2013-supporting-large-meetings.md">Compatibilidad para grandes reuniones mediante Lync Server 2013</A>.


</div></td>
</tr>
<tr class="odd">
<td><p>Un Servidor perimetral</p></td>
<td><p>12.000 usuarios remotos simultáneos</p></td>
</tr>
<tr class="even">
<td><p>Un Director</p></td>
<td><p>12.000 usuarios remotos simultáneos</p></td>
</tr>
<tr class="odd">
<td><p>Supervisión y archivado</p></td>
<td><p>En Lync Server 2013, los servicios front-end de supervisión y archivado ahora se ejecutan en cada Servidor front-end, en lugar de en cada rol de servidor por separado.</p>
<p>Los servicios de supervisión y archivado aún requieren sus propios almacenes de base de datos. Si también ejecuta Exchange 2013, puede guardar los datos de archivado en Exchange en lugar de en una base de datos SQL dedicada.</p></td>
</tr>
<tr class="even">
<td><p>Un Servidor de mediación</p></td>
<td><p>Servidor de mediación instalado con Servidor front-end se ejecuta en todos los Servidor front-end de un grupo, y debe proporcionar capacidad suficiente para los usuarios del grupo. Para Servidor de mediación independientes, consulte la sección “Servidor de mediación” más adelante en este tema.</p></td>
</tr>
<tr class="odd">
<td><p>Un servidor Standard Edition</p></td>
<td><p>Se recomienda encarecidamente que si usa servidores Standard Edition para hospedar usuarios, siempre use dos servidores, emparejados con las recomendaciones en <a href="lync-server-2013-planning-for-high-availability-and-disaster-recovery.md">Planeación de alta disponibilidad y recuperación ante desastres en Lync Server 2013</a>. Cada servidor en el par puede hospedar hasta 2500 usuarios y si uno de los servidores falla, el servidor restante puede admitir 5000 usuarios en un escenario de conmutación por error.</p>
<p>Si la implementación incluye una cantidad significativa de tráfico de audio o vídeo, el rendimiento del servidor puede verse afectado con más de 2500 usuarios por servidor. En este caso, considere la opción de agregar más servidores Standard Edition o cambiar a Lync ServerEnterprise Edition.</p></td>
</tr>
</tbody>
</table>


## Servidor front-end


> [!NOTE]
> Los grupos de servidores extendidos no son compatibles con esta función del servidor.



En un Grupo de servidores front-end, debe tener un Servidor front-end por cada 6.660 usuarios hospedados en el grupo, suponiendo que la tecnología hyper-threading esté habilitada en todos los servidores del grupo y que el hardware de los servidores cumpla los requisitos descritos en [Plataformas de hardware de servidor para Lync Server 2013](lync-server-2013-server-hardware-platforms.md). El número máximo de usuarios en un Grupo de servidores front-end es 80.000, suponiendo que la tecnología hyper-threading esté habilitada en todos los servidores del grupo. Si tiene más de 80.000 usuarios en un sitio, puede implementar más de un Grupo de servidores front-end.

Cuando calcule el número de usuarios de un Grupo de servidores front-end, incluya los usuarios hospedados en aplicaciones de sucursal con funciones de supervivencia y servidores de sucursal con funciones de supervivencia asociados a este Grupo de servidores front-end.

Cuando un servidor activo no está disponible, sus conexiones se transfieren automáticamente a los demás servidores del grupo. Por ejemplo, si tiene 30.000 usuarios y cinco Servidores front-end, en el caso de que un servidor no esté disponible, las conexiones de 6.000 usuarios tendrán que transferirse a los otros cuatro servidores. Cada uno de los cuatro servidores restantes tendrá 7.500 usuarios, un número mayor del recomendado.

En cambio, si hubiera comenzado con seis Servidores front-end para los 30.000 usuarios y, posteriormente, uno deja de estar disponible, se moverá un total de 5.000 usuarios a los cinco servidores restantes. Cada uno de estos cinco servidores hospedará 6.000 usuarios, que está en el intervalo recomendado.

La cantidad máxima de usuarios en un Grupo de servidores front-end es 80.000. La cantidad máxima de Servidores front-end en un grupo de servidores es 12.

Para un Grupo de servidores front-end con 80.000 usuarios, doce Servidores front-end es suficiente para lograr rendimiento, en implementaciones típicas que siguen el [Modelos de usuario en Lync Server 2013](lync-server-2013-user-models.md). Las implementaciones diseñadas para admitir conmutación por error y recuperación ante desastres, considere que se puede hospedar un máximo de 40.000 usuarios en cada uno de los dos Grupos de servidores front-end emparejados, en los cuales cada grupo dispone de suficientes Servidores front-end para acomodar a los usuarios de ambos grupos si uno de los grupos conmuta por error al otro.

El número de usuarios que un Grupo de servidores front-end admite con buen rendimiento puede variar respecto a estas cifras por los motivos siguientes:

  - Si el hardware de los Servidores front-end no cumple las recomendaciones de [Plataformas de hardware de servidor para Lync Server 2013](lync-server-2013-server-hardware-platforms.md).

  - Si el uso de su organización difiere en gran medida de los modelos de usuario, por ejemplo, con un tráfico de conferencias significativamente mayor.

> [!IMPORTANT]  
> En Lync Server 2013, las bases de datos de presencia ahora se hospedan en Servidores front-end, a diferencia de Lync Server 2010 que las hospedaba en el Servidor back-end. Esto significa que el rendimiento de disco y la capacidad del Servidores front-end no deben ser inferiores a las recomendaciones indicadas anteriormente en esta sección y en <a href="lync-server-2013-server-hardware-platforms.md">Plataformas de hardware de servidor para Lync Server 2013</a>, independientemente del número de usuarios que hospede el Servidores front-end.



La siguiente tabla muestra el ancho de banda medio dedicado a la MI y a la presencia, dado el modelo de usuario, según se define en [Modelos de usuario en Lync Server 2013](lync-server-2013-user-models.md).


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Ancho de banda medio por usuario</th>
<th>Requisitos de ancho de banda por cada Servidor front-end con 6.660 usuarios</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>1,3 Kbps</p></td>
<td><p>13 Mbps</p></td>
</tr>
</tbody>
</table>



> [!NOTE]
> Para mejorar el rendimiento multimedia de las funcionalidades Conferencia A/V y Servidor de mediación instaladas en sus Servidores front-end, debe habilitar el ajuste de escala en el lado de recepción (RSS) en los adaptadores de red de sus Servidores front-end. RSS permite que varios procesadores del servidor administren en paralelo los paquetes entrantes. Para más información, consulte "Mejora de la escala en el lado de recepción en Windows Server 2008" en <A class=uri href="http://go.microsoft.com/fwlink/?linkid=268731">http://go.microsoft.com/fwlink/?linkid=268731</A>. Para más información sobre cómo habilitar RSS, consulte la documentación de su adaptador de red.



## Máximos de conferencia

Dado el modelo de usuario que establece que el 5% de los usuarios de un grupo de servidores puede estar en una conferencia en cualquier momento dado, un grupo de 80.000 usuarios podría tener unos 4.000 usuarios en conferencias en un determinado momento. Se espera que esas conferencias sean una combinación de varios medios (algunas, solo de MI; otras, de MI con audio; otras, de audio y vídeo, por ejemplo) y diferentes números de participantes. No hay ningún límite fijo para el número real de conferencias permitidas y el uso real determinará el rendimiento real. Por ejemplo, si su organización tiene muchas más conferencias de modo combinado de lo que supone el modelo de usuario, probablemente necesite implementar más Servidores front-end o servidores de conferencia A/V del número recomendado en este documento. Para ver más detalles acerca de los supuestos de este modelo de usuario, consulte [Modelos de usuario en Lync Server 2013](lync-server-2013-user-models.md).

El tamaño máximo admitido de las conferencias que puede hospedar un Grupo de servidores front-end de Lync Server 2013 que también hospeda usuarios es de 250 participantes. Mientras se celebra una conferencia de 250 usuarios, el grupo puede admitir también otras conferencias, con un total del 5% de los usuarios del grupo en conferencias simultáneas. Por ejemplo, en un grupo formado por doce Servidores front-end y 80.000 usuarios, mientras se lleva a cabo la conferencia de 250 usuarios, Lync Server admite la participación de otros 3.750 usuarios en conferencias más pequeñas.

Al margen de la cantidad de usuarios hospedados en el Grupo de servidores front-end o el servidor Standard Edition, Lync Server admite, como mínimo, la participación de otros 125 usuarios en conferencias más pequeñas en el mismo grupo o servidor que hospeda la conferencia de 250 usuarios.

Para permitir conferencias de entre 250 y 1000 usuarios, puede configurar un Grupo de servidores front-end independiente solo para hospedar estas conferencias. Este Grupo de servidores front-end no hospedará usuarios. Para más información, consulte [Compatibilidad para grandes reuniones mediante Lync Server 2013](lync-server-2013-supporting-large-meetings.md).

Si su organización tiene muchas más conferencias de modo mixto que las que se esperan en el modelo de usuario, quizás necesite implementar más Servidores front-end que los recomendados en este documento (con un límite de 12 servidores front-end). Para más información sobre los supuestos del modelo de usuario, consulte [Modelos de usuario en Lync Server 2013](lync-server-2013-user-models.md).

## Servidor perimetral


> [!NOTE]
> Los grupos de servidores extendidos no son compatibles con esta función del servidor.



Debe implementar un Servidor perimetral por cada 12.000 usuarios remotos que tendrán acceso a un sitio simultáneamente. Como mínimo, se recomiendan dos Servidores perimetrales para alta disponibilidad. En estas recomendaciones se asume que el hardware de sus Servidores perimetrales cumple las recomendaciones descritas en [Plataformas de hardware de servidor para Lync Server 2013](lync-server-2013-server-hardware-platforms.md).

Cuando calcule el número de usuarios de los Servidores perimetrales, incluya los usuarios hospedados en aplicaciones de sucursal con funciones de supervivencia y servidores de sucursal con funciones de supervivencia de las sucursales que estén asociados a un Grupo de servidores front-end en este sitio.


> [!NOTE]
> Para mejorar el rendimiento multimedia del servicio perimetral Conferencia A/V en sus Servidores perimetrales, debe habilitar el ajuste de escala en el lado de recepción (RSS) en los adaptadores de red de sus Servidores perimetrales. RSS permite que varios procesadores del servidor administren en paralelo los paquetes entrantes. Para más información, consulte "Mejora de la escala en el lado de recepción en Windows Server 2008" en <A class=uri href="http://go.microsoft.com/fwlink/?linkid=268731">http://go.microsoft.com/fwlink/?linkid=268731</A>. Para más información sobre cómo habilitar RSS, consulte la documentación de su adaptador de red.



## Director


> [!NOTE]
> Los grupos de servidores extendidos no son compatibles con esta función del servidor.



Si implementa el rol de servidor Director, es recomendable que implemente un Director por cada 12.000 usuarios remotos que tendrán acceso a un sitio simultáneamente. Como mínimo, recomendamos dos Directores para alta disponibilidad. En estas recomendaciones asumimos que el hardware de sus Servidores perimetrales cumple las recomendaciones descritas en [Plataformas de hardware de servidor para Lync Server 2013](lync-server-2013-server-hardware-platforms.md).

Cuando calcule el número de usuarios de los Directores, incluya los usuarios hospedados en aplicaciones de sucursal con funciones de supervivencia y servidores de sucursal con funciones de supervivencia de las sucursales que estén asociados a un Grupo de servidores front-end en este sitio.

## Servidor de mediación


> [!NOTE]
> Los grupos de servidores extendidos no son compatibles con esta función del servidor.



Si instala Servidor de mediación con Servidor front-end, Servidor de mediación se ejecuta cada Servidor front-end del grupo y debe proporcionar capacidad suficiente para los usuarios del grupo.

Si implementa un grupo de Servidor de mediación independiente, la cantidad de Servidores de mediación que se debe implementar depende de muchos factores, como el hardware que usa el Servidor de mediación, el número de usuarios VoIP que tiene, el número de puertas de enlace del mismo nivel que controla cada Grupo de servidores de mediación, el tráfico de esas puertas de enlace en hora punta y el porcentaje de llamadas multimedia desviadas del Servidor de mediación.

Las siguientes tablas sirven de guía para saber cuántas llamadas simultáneas puede administrar un Servidor de mediación, asumiendo que el hardware de los Servidores de mediación cumple los requisitos descritos en [Plataformas de hardware de servidor para Lync Server 2013](lync-server-2013-server-hardware-platforms.md) y que la tecnología hyper-threading esté habilitada. Para ver más detalles acerca de la escalabilidad de un Servidor de mediación, consulte [Estimar el uso de voz y el tráfico para Lync Server 2013](lync-server-2013-estimating-voice-usage-and-traffic.md) y [Directrices de implementación para el servidor de mediación en Lync Server 2013](lync-server-2013-deployment-guidelines-for-mediation-server.md).

En las tablas siguientes se da por supuesto un uso como el resumido en [Modelos de usuario en Lync Server 2013](lync-server-2013-user-models.md).

### Capacidad de un Servidor de mediación independiente: 70% de usuarios internos, 30% de usuarios externos sin capacidad para desviar llamadas (transcodificación multimedia realizada por el Servidor de mediación)

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
<td><p>Procesador dual, seis núcleos, CPU hyper-threaded a 2,26 GHz <strong>con hyper-threading deshabilitado</strong>, con 32 GB de memoria y una tarjeta adaptadora de red de doble puerto.</p></td>
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



> [!NOTE]
> Aunque se utilizaron servidores con 32 GB de memoria para la prueba, se pueden utilizar servidores con 16 GB de memoria como Servidor de mediación independientes y son suficientes para ofrecer el rendimiento mostrado en esta tabla.



### Capacidad del Servidor de mediación ( Servidor de mediación instalado con el Servidor front-end) 70% usuarios internos, 30% usuarios externos, sin capacidad para desviar llamadas (procesamiento multimedia realizado por el Servidor de mediación)

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



> [!NOTE]
> Esta cifra es mucho menor que las cifras del Servidor de mediación independiente porque el Servidor front-end tiene que administrar otras características y funciones para los 6.600&nbsp;usuarios que hospeda, además de la transcodificación necesaria para las llamadas de voz.




> [!NOTE]
> Para mejorar el rendimiento del Servidor de mediación, debe habilitar el ajuste de escala en el lado de recepción (RSS) en los adaptadores de red de sus Servidores de mediación. RSS permite que varios procesadores del servidor administren en paralelo los paquetes entrantes. Para más información, consulte "Mejora de la escala en el lado de recepción en Windows Server 2008" en <A class=uri href="http://go.microsoft.com/fwlink/?linkid=268731">http://go.microsoft.com/fwlink/?linkid=268731</A>. Para más información sobre cómo habilitar RSS, consulte la documentación de su adaptador de red.



## Servidor back-end

En Lync Server 2013, las bases de datos de presencia están situadas en el Servidores front-end en lugar del Servidor back-end. El resultado es unos requisitos mucho menores para cada Servidor back-end de Lync Server 2013, equivalente a los requisitos de hardware del Servidor front-end. Esto contrasta con Lync Server 2010, que requería que el Servidor back-end fuera un servidor de gama superior con 25 discos. Sin embargo, la carga de trabajo de los Servidores back-end sigue siendo tal que no se incumplirán las recomendaciones de hardware indicadas anteriormente en esta sección y en [Plataformas de hardware de servidor para Lync Server 2013](lync-server-2013-server-hardware-platforms.md).

Para proporcionar alta disponibilidad en su Servidor back-end, es recomendable que implemente creación de reflejos de servidores. Para más información, consulte [Alta disponibilidad del servidor back-end en Lync Server 2013](lync-server-2013-back-end-server-high-availability.md).

## Supervisión y archivado

En Lync Server 2013, si implementa supervisión o archivado, la funcionalidad front-end de estos servicios se ejecuta en los Servidores front-end en lugar de en roles de servidor independientes. La supervisión y el archivado siguen usando sus propios almacenes de base de datos, diferentes del almacén back-end. Si tiene Exchange 2013 implementado, también puede almacenar los datos de archivado de mensajería instantánea en Exchange en lugar de en un almacén SQL dedicado.

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
<td><p></p></td>
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


Durante las pruebas de rendimiento, Microsoft utilizó el hardware de la tabla siguiente para el servidor de base de datos de supervisión y archivado. Las pruebas recopilaron los datos de dos Grupos de servidores front-end, cada uno con 80.000 usuarios.

### Hardware utilizado en las pruebas de rendimiento de supervisión y archivado

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
<td><p>16</p></td>
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


## En esta sección

  - [Estimar el uso de voz y el tráfico para Lync Server 2013](lync-server-2013-estimating-voice-usage-and-traffic.md)

  - [Directrices de implementación para el servidor de mediación en Lync Server 2013](lync-server-2013-deployment-guidelines-for-mediation-server.md)

