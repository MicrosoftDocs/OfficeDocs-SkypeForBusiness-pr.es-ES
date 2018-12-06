﻿---
title: 'Lync Server 2013: Modelos de usuario'
TOCTitle: Modelos de usuario de Lync Server 2013
ms:assetid: c551371c-d740-4372-bada-f0d713ec0d33
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398811(v=OCS.15)
ms:contentKeyID: 49889673
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Modelos de usuario en Lync Server 2013

 

_**Última modificación del tema:** 2015-03-09_

Los modelos de usuario de este artículo proporcionan una base para las mediciones y recomendaciones de planeación de la capacidad que se describen en [Planificar la capacidad con los modelos de usuario para Lync Server 2013](lync-server-2013-capacity-planning-using-the-user-models.md).

## Modelos de usuario de Lync Server 2013

En la tabla siguiente se describe el modelo de usuario para el registro, los contactos, la mensajería instantánea (MI) y la presencia para Lync Server 2013.

### Modelo de usuario de registro y entorno

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Categoría</th>
<th>Descripción</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Tamaño de implementación y distribución</p></td>
<td><p>Se modela una implementación de gran tamaño con tres sitios centrales y un grupo de servidores front-end por sitio.</p></td>
</tr>
<tr class="even">
<td><p>Porcentaje de usuarios de Active Directory</p></td>
<td><p>Se presupone que el 70 % de todos los usuarios de Active Directory de la organización está habilitado para Lync Server. El 80 % de estos usuarios habilitados ha iniciado sesión en Lync Server todos los días (con un 80 % de simultaneidad). Los usuarios simultáneos constituyen la base de los cálculos del resto de esta sección.</p></td>
</tr>
<tr class="odd">
<td><p>Cambios en Active Directory</p></td>
<td><p>Se supone que el 0,5 % del total de los usuarios se ha creado y habilitado para Lync en Active Directory cada semana, y que también cada semana el 0,5 % del total de usuarios se deshabilita de Active Directory y de Lync. El 5 % de los usuarios cambia al menos un atributo de Active Directory cada semana.</p></td>
</tr>
<tr class="even">
<td><p>Grupos de distribución de Active Directory</p></td>
<td><p>Se supone que el número de grupos de distribución de Active Directory de la organización es igual al triple de todos los usuarios de Active Directory. Los grupos de distribución tienen las dimensiones siguientes:</p>
<ul>
<li><p>El 64 % tiene de 2 a 30 usuarios.</p></li>
<li><p>El 13 % tiene de 31 a 50 usuarios.</p></li>
<li><p>El 10 % tiene de 51 a 100 usuarios.</p></li>
<li><p>El 13 % tiene de 101 a 500 usuarios.</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Usuarios de voz sobre IP (VoIP)</p></td>
<td><p>El 60 % de los usuarios de Lync Server está habilitado para las comunicaciones unificadas (es decir, sus números de teléfono son propiedad de Lync Server).</p></td>
</tr>
<tr class="even">
<td><p>Distribución de clientes registrados</p></td>
<td><p>El 65 % de los clientes ejecuta el software de Lync 2013, incluidos Lync y Lync Phone Edition.</p>
<p>El 30 % de los clientes ejecuta el software de cliente de una versión anterior de Lync.</p>
<p>El 5 % de los clientes usa Lync Web App.</p>
<p>Si la movilidad está habilitada, se supone que el 40 % de los usuarios está usando la movilidad al mismo tiempo que las otras opciones de cliente registradas mencionadas anteriormente. En este caso, la relación de varios puntos de presencia (MPOP) del cliente es de 1:1,9. Si la movilidad está deshabilitada, la relación de MPOP será de 1:1,5.</p></td>
</tr>
<tr class="odd">
<td><p>Distribución de usuarios remotos</p></td>
<td><p>El 70 % de los usuarios se conecta internamente.</p>
<p>El 30 % de los usuarios se conecta a través de un servidor perimetral y un Director.</p></td>
</tr>
<tr class="even">
<td><p>Distribución de contactos</p></td>
<td><p>El número máximo de contactos que tiene un usuario es de 1.000. Menos del 1 % de los usuarios tiene 1.000 contactos. Menos del 25 % de los usuarios tiene 100 o más contactos.</p>
<p>Una media de 80 contactos para los usuarios con conectividad en la nube pública. De estos usuarios:</p>
<ul>
<li><p>El 50% de los contactos está dentro de la organización. El 10 % de estos usuarios corresponde a usuarios remotos que se conectan desde fuera del firewall.</p></li>
<li><p>El 40 % de los contactos son usuarios de la nube pública (como los usuarios de AOL, Yahoo!, MSN o Google Talk).</p></li>
<li><p>El 10% de los contactos corresponde a socios federados.</p>

> [!IMPORTANT]  
> <ul>
> <li><p>El 1 de septiembre de 2012, la licencia de suscripción del usuario de Public IM Connectivity de Microsoft Lync (&quot;PIC USL&quot;) dejó de estar disponible para su compra en los contratos nuevos y en las prórrogas de contratos. Los clientes que tengan licencias activas podrán seguir federándose con Yahoo! Messenger hasta la fecha de cierre del servicio. La fecha anunciada para el fin de vida de AOL y Yahoo! es junio de 2014. Para más detalles, vea <a href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Soporte para la conectividad de mensajería instantánea pública en Lync Server 2013</a>.</p></li>
> <li><p>PIC USL es una licencia de suscripción por usuario/por mes requerida por Lync Server u Office Communications Server para la federación con Yahoo! Messenger. La posibilidad de Microsoft de proporcionar este servicio depende de la compatibilidad con Yahoo!, cuyo contrato subyacente está llegando a su fin.</p></li>
> <li><p>Hoy más que nunca, Lync es una herramienta eficaz para conectarse dentro de una organización y con individuos de todo el mundo. La federación con Windows Live Messenger no requiere ninguna licencia de usuario o dispositivo adicional aparte de la CAL estándar de Lync. La federación con Skype se agregará a esta lista, lo que permitirá a los usuarios de Lync conectarse con cientos de millones de personas a través de mensajería instantánea y voz.</p></li>
> </ul>

</li>
</ul>
<p>Una media de 50 contactos para los usuarios sin conectividad en la nube pública. De estos usuarios:</p>
<ul>
<li><p>El 80 % de los contactos está dentro de la organización. El 10 % de estos usuarios corresponde a usuarios remotos que se conectan desde fuera del firewall.</p></li>
<li><p>El 20 % de los contactos corresponde a socios federados.</p>
<p>Cada usuario tiene un grupo de distribución en su lista de contactos. Para las pruebas de rendimiento, se supone que los grupos de distribución son siempre expandidos.</p></li>
</ul>
<p>El 25 % de los contactos de un usuario usa XMPP.</p></td>
</tr>
<tr class="odd">
<td><p>Tiempo de la sesión</p></td>
<td><p>La sesión de inicio media de un usuario dura doce horas. Todos los usuarios inician sesión durante los primeros 120 minutos tras el inicio de la sesión.</p></td>
</tr>
</tbody>
</table>


### Modelo de usuario de presencia y MI

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Categoría</th>
<th>Descripción</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Sesiones de MI de punto a punto</p></td>
<td><p>Cada usuario mantiene una media diaria de seis sesiones de MI de punto a punto.</p>
<p>Diez mensajes instantáneos por sesión.</p>
<p>Cada mensaje se corresponde con dos mensajes SIP INFO y dos mensajes SIP 200 OK (para los indicadores de estado como “&lt;Nombre&gt; está escribiendo”).</p></td>
</tr>
<tr class="even">
<td><p>Sondeo de presencia</p></td>
<td><p>En términos generales, se supone que los sondeos de presencia tienen unos 60 sondeos de media por usuario y hora. Para cada usuario, se supone una media de:</p>
<ul>
<li><p>Un sondeo por día de la presencia de usuarios en la pestaña de organización de los usuarios (pero no en la de Lista de contactos). La media de no contactos en la pestaña de organización de los usuarios es de 15 usuarios. Dos operaciones de ver tarjetas de contacto al día.</p></li>
<li><p>Un sondeo de presencia cada vez que un usuario hace clic en otro usuario para iniciar una conversación, estimado en una vez por hora.</p></li>
<li><p>Seis búsquedas de usuario por hora. Cada vez que se realiza una búsqueda, se envía un sondeo por lotes para cada usuario de la lista de resultados de la búsqueda. Se supone que el tamaño medio de los resultados de la búsqueda es de 20. Si los resultados de la búsqueda permanecen en pantalla, el sondeo por lotes se actualiza cada 5 minutos. Se supone que habrá dos actualizaciones por hora.</p></li>
<li><p>Cuando un usuario abre u obtiene la vista previa de un mensaje de correo en Outlook, un sondeo de la presencia de los usuarios en los campos Para: y CC: del mensaje, estimado en cinco mensajes por hora y cuatro usuarios por mensaje.</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Suscripciones de presencia</p></td>
<td><p>Cuando un usuario agrega a otro como contacto, el primer usuario se <em>suscribe</em> a cinco categorías de información acerca del segundo usuario. Las actualizaciones de estas categorías de información se envían automáticamente al primer usuario.</p>
<p>Para cada cliente, se envía una única petición de suscripción por lotes para obtener el estado de presencia de una media de 40 contactos, con 40 diálogos adicionales para obtener la presencia de los contactos federados.</p>
<p>La presencia de los miembros de un grupo de distribución expandido se averigua a través de las suscripciones de presencia persistente, y no a través de los sondeos, y se modela como 1 expansión por usuario durante cada 2 horas.</p>
<p>Las <em>suscripciones breves</em> ocurren cuando un usuario inicia sesión, se realiza una suscripción por lotes para todos los contactos del usuario y, a continuación, el usuario se desconecta en un breve periodo. Se suponen 6 suscripciones breves por usuario y hora, y cada suscripción dura 10 minutos.</p></td>
</tr>
<tr class="even">
<td><p>Publicación de presencia</p></td>
<td><p>El estado de presencia se publica a una media de 4 publicaciones por usuario y hora, con un máximo de 6 por usuario y hora.</p>
<p></p></td>
</tr>
<tr class="odd">
<td><p>Tamaño del documento de presencia</p></td>
<td><p>Se supone que el tamaño medio de un documento de presencia completo es de 4 K (de 25 K como máximo).</p></td>
</tr>
</tbody>
</table>


En la tabla siguiente se describe el modelo de usuario para el uso de la libreta de direcciones.

### Modelo de usuario para el uso de la libreta de direcciones

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Modo de búsqueda de la libreta de direcciones</th>
<th>Uso</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Solo consulta web de la libreta de direcciones (todas las consultas realizadas por el servicio de consulta web de la libreta de direcciones)</p></td>
<td><p>Cuatro consultas de prefijo por usuario y día.</p>
<p>60 consultas de búsqueda exactas por usuario y día. El 40 % de estas consultas se procesa por lotes, con una media de 20 contactos por consulta. El 60 % restante de las consultas es para un solo contacto.</p>
<p>25 consultas de fotografías por usuario y día. 24 son para una sola fotografía y la otra es una consulta por lotes con una media de 20 contactos.</p>
<p>Una consulta de búsqueda de organización total por usuario y día.</p></td>
</tr>
<tr class="even">
<td><p>Modo mixto, se usa el archivo de la libreta de direcciones y las consultas web. Este es el modo predeterminado.</p></td>
<td><p>Solo dos tipos de consultas van a la red, las consultas de fotografía y de búsqueda de organización total.</p>
<p>25 consultas de fotografías por usuario y día. 24 son para una sola fotografía y la otra es una consulta por lotes con una media de 20 contactos.</p>
<p>Una consulta de búsqueda de organización total por usuario y día.</p></td>
</tr>
</tbody>
</table>


En la siguiente tabla se describe el modelo de conferencia.

### Modelo de conferencia

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Categoría</th>
<th>Descripción</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Reuniones programadas y reuniones de tipo &quot;Reunirse ahora&quot;</p></td>
<td><p>60 % programadas, 40 % no programadas.</p>
<p>De las reuniones programadas, se supone que el 80 % son conferencias asignadas, que son ocurrencias de conferencias periódicas. El 10 % son reuniones abiertas de una sola vez. El 8 % son reuniones anónimas de una sola vez y el 2 % son reuniones cerradas de una sola vez.</p></td>
</tr>
<tr class="even">
<td><p>Distribución de clientes de conferencia</p></td>
<td><p>Para reuniones programadas:</p>
<ul>
<li><p>El 65% de los usuarios de conferencia usa Lync 2013.</p></li>
<li><p>El 5% de los usuarios de conferencia usa Microsoft Lync Web App.</p></li>
<li><p>El 30 % de los usuarios de conferencia usa clientes anteriores, como Microsoft Lync 2010, Office Communicator 2007 R2, Office Communicator 2007 y Microsoft Office Communicator Web Access (versión 2007).</p></li>
</ul>
<p>Para reuniones no programadas:</p>
<ul>
<li><p>El 70 % de los usuarios de conferencia usa Lync 2013.</p></li>
<li><p>El 30 % de los usuarios de conferencia usa clientes anteriores, como Microsoft Lync 2010, Office Communicator 2007 R2, Office Communicator 2007 y Microsoft Office Communicator Web Access (versión 2007).</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Concurrencia en reuniones</p></td>
<td><p>El 5 % de los usuarios asistirá a conferencias durante el horario de trabajo. Por tanto, en un grupo de 80.000 usuarios, hasta 4.000 usuarios pueden asistir a conferencias en un momento dado.</p></td>
</tr>
<tr class="even">
<td><p>Distribución de audio en las reuniones</p></td>
<td><p>El 40 % combinó el audio por VoIP y la conferencia de acceso telefónico local, con una relación 3 usuarios de VoIP por 1 usuario de acceso telefónico.</p>
<p>El 35 % usó solo audio por VoIP.</p>
<p>El 15 % usó solo audioconferencia de acceso telefónico local.</p>
<p>El 10 % no usó audio (conferencias solo de mensajería instantánea, con una media de cinco mensajes enviados por usuario).</p></td>
</tr>
<tr class="odd">
<td><p>Combinación de medios para conferencias</p></td>
<td><p>El 75 % de las conferencias son conferencias web, con audio más otras modalidades de colaboración.</p>
<p>Para estas conferencias, los otros métodos de colaboración son los siguientes:</p>
<div>

> [!NOTE]
> Estas cifras suman más del 100 % porque una conferencia puede tener varios métodos de colaboración.


</div>
<ul>
<li><p>El 50 % agrega el uso compartido de aplicaciones. Se supone que un usuario envía datos a una velocidad pico de 1,1 MB por segundo.</p></li>
<li><p>El 50 % agrega mensajería instantánea (dos mensajes de media por usuario).</p></li>
<li><p>El 20 % agrega colaboración de datos, incluidos PowerPoint o la pizarra. Entre estos, una media de dos archivos de PowerPoint presentados por conferencia, con un tamaño medio de archivo de PowerPoint de 10 MB (sin vídeo integrado), o de 30 MB (con vídeo integrado). Una media de 20 anotaciones por pizarra.</p></li>
<li><p>El 20 % agrega vídeo. De estos usuarios, el 70 % está en conferencias habilitadas para vídeo de vista múltiple, en las que cada usuario recibe de 2 a 3 secuencias de vídeo.</p></li>
<li><p>El 15 % agrega notas compartidas.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Distribución de los participantes en las reuniones</p></td>
<td><p>El 50 % corresponde a usuarios internos autenticados.</p>
<p>El 25 % corresponde a usuarios remotos autenticados.</p>
<p>El 15 % corresponde a usuarios anónimos.</p>
<p>El 10% corresponde a usuarios federados.</p></td>
</tr>
<tr class="odd">
<td><p>Distribución de participación en las reuniones</p></td>
<td><p>Se simula que los usuarios se unen a la reunión durante los primeros 5 minutos.</p></td>
</tr>
</tbody>
</table>


En los grupos de servidores front-end habituales, Lync Server 2013 admite un tamaño máximo para las reuniones de 250 usuarios. Cada grupo puede hospedar una reunión de 250 usuarios de una vez. Mientras tiene lugar esta gran reunión, el grupo también puede hospedar otras conferencias más pequeñas. Además, se pueden admitir reuniones de hasta 1.000 usuarios si se configura un grupo dedicado para hospedar estas reuniones. Para más información, consulte [Compatibilidad con reuniones grandes en Lync Server 2013](lync-server-2013-support-for-large-meetings.md).

Las conferencias se simularon del modo siguiente.

  - El 85 % de las conferencias contó con cuatro participantes.

  - El 10 % de las conferencias contó con seis participantes.

  - El 5 % de las conferencias contó con 11 participantes.

  - Hubo una gran conferencia con 250 usuarios.

En la tabla siguiente se proporciona información detallada sobre el modelo de usuario para conferencias que incluye a usuarios de acceso telefónico local.

### Modelo de usuario de conferencias de acceso telefónico local

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Categoría</th>
<th>Descripción</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Autenticados/Anónimos</p></td>
<td><p>El 70 % de los autores de llamadas se une como anónimo y se le solicita un nombre registrado. El 30 % se une como usuario autenticado.</p></td>
</tr>
<tr class="even">
<td><p>Duración de la llamada y música en espera</p></td>
<td><p>Duración media de llamada sin música en espera: 50 segundos.</p>
<p>El 50 % de los usuarios que llaman escucha música en espera durante una media de cinco minutos.</p></td>
</tr>
<tr class="odd">
<td><p>Tono de marcado de frecuencia múltiple (DTMF)</p></td>
<td><p>El 15 % de las conferencias de acceso telefónico local solo tiene coordinadores de teléfono. El 10 % de las conferencias mixtas que incluyen a usuarios de acceso telefónico local también tiene coordinadores de teléfono.</p>
<p>El 20 % de los coordinadores de teléfono usa dos comandos DTMF por conferencia.</p></td>
</tr>
<tr class="even">
<td><p>Idiomas del anuncio</p></td>
<td><p>En las simulaciones se usa inglés como idioma del anuncio.</p></td>
</tr>
</tbody>
</table>


En la tabla siguiente se proporciona información detallada sobre el modelo de usuario para salas de espera de conferencia.

### Modelo de usuario para salas de espera de conferencia

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Categoría</th>
<th>Descripción</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Número de usuarios en sala de espera</p></td>
<td><p>El 5 % de los usuarios de acceso telefónico local pasa por la sala de espera y el 25 % de otros usuarios también.</p></td>
</tr>
<tr class="even">
<td><p>Admisión desde la sala de espera</p></td>
<td><p>En las simulaciones, el moderador admitió a todos los usuarios antes de que transcurriera el tiempo de espera de cliente.</p></td>
</tr>
</tbody>
</table>


En la tabla siguiente se describe el modelo de usuario para otras sesiones punto a punto.

### Modelo de usuario para sesiones punto a punto

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Categoría</th>
<th>Descripción</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Uso compartido de aplicaciones</p></td>
<td><p>Cada usuario participa en 5 sesiones de uso compartido de aplicaciones de punto a punto al mes, para una media de 0,25 sesiones al día.</p></td>
</tr>
<tr class="even">
<td><p>Transferencia de archivos</p></td>
<td><p>Cada usuario participa en 1 sesión de transferencia de archivos de punto a punto al mes (como parte de una sesión de MI), para una media de 0,05 sesiones al día. El tamaño de archivo medio transferido por sesión es de 1 MB.</p></td>
</tr>
</tbody>
</table>


La siguiente tabla describe el modelo de usuario de las directivas.

### Modelo de usuario de directivas

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Categoría</th>
<th>Descripción</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Conferencias, presencia y directivas de archivado</p></td>
<td><p>Se supone que hay una directiva global, 10 directivas de conferencia de etiqueta, 4 directivas de archivado y 10 directivas de presencia de etiqueta.</p></td>
</tr>
<tr class="even">
<td><p>Directiva de voz</p></td>
<td><p>Se supone que hay una directiva global y 2 directivas de etiqueta por sitio. El 100 % de los sitios tiene una directiva de sitio y el 30 % de los usuarios tiene asignada una directiva por usuario. Se supone un plan de marcado por sitio y dos rutas por sitio.</p></td>
</tr>
</tbody>
</table>


## Hora punta

Para sesiones de punto a punto, la carga máxima se calcula con Intentos de llamada en hora punta (BHCA). Este término del sector de la voz presupone que el 50 % de todas las llamadas del día se realizará en el 20 % del tiempo. Se calcula con la siguiente fórmula:

`BHCA=(total calls * 0.5) / 1.6`

Las pruebas de rendimiento han simulado hora punta ejecutando VoIP y otras sesiones de punto a punto en una carga de hora punta para al menos 1,6 horas por día.

En la carga máxima de conferencia se supone que el 75 % de todas las conferencias para un día de ocho horas tiene lugar en cuatro horas punta. Estas horas punta tienen 1,5 veces la carga media de conferencia.

## Telefonía IP empresarial a llamadas RTC

Las siguientes suposiciones se refieren a las llamadas de Telefonía IP empresarial:

  - El 50 % de los usuarios está habilitado para Telefonía IP empresarial y el 60 % de estos usuarios está habilitado para las llamadas RTC.

  - Cada uno de estos usuarios habilitados para las llamadas RTC realiza 4 llamadas RTC durante la hora punta. Cada llamada dura 3 minutos.

  - El 65 % de estas llamadas de voz RTC usa desvío de medios.

## Movilidad

Se supone que el 40 % de los usuarios registrados está habilitado para la movilidad. Para cada usuario que tiene la movilidad habilitada, se supone que la actividad del cliente móvil se suma a la de las demás instancias de MPOP para dicho usuario, salvo las interacciones de conferencia, para las que el cliente de movilidad es solo otro tipo de cliente que se puede usar para participar en las conferencias.

## Chat persistente

Se supone que el 25 % de los usuarios registrado participará en sesiones de chat persistentes, con las siguientes características:

  - Una media de 1,5 salones de chat por usuario.

  - Cada salón de chat genera 12 peticiones de sondeo por hora, con una media de 10 destinatarios cada una.

## Grupo de respuesta y estacionamiento de llamadas

Se supone que el 0,15 % de los usuarios registrados pertenece a grupos de respuesta. Se supone que el 0,02 % de los usuarios registrados tiene llamadas estacionadas en un momento determinado.

