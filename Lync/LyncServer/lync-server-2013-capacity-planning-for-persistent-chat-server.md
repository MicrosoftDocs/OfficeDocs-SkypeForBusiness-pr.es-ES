---
title: 'Lync Server 2013: Planeación de capacidad para el servidor de chat persistente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Capacity planning for Persistent Chat Server
ms:assetid: 7a850cd5-c789-4795-a8ff-083be21ae784
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615006(v=OCS.15)
ms:contentKeyID: 48184580
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d0cd27f961d3b4857cf13d5786897bd29a657851
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42135567"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="capacity-planning-for-persistent-chat-server-in-lync-server-2013"></a>Planeación de la capacidad para el servidor de chat persistente en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-05_

El servidor de chat persistente puede realizar chat en tiempo real para varios usuarios que puede persistir para una recuperación y búsqueda en el futuro. A diferencia de la mensajería instantánea (mi) de grupo que se guarda en el buzón de un usuario si está configurado el historial de la conversación, una sesión del servidor de chat persistente permanece abierta más tiempo y el contenido se guarda en un servidor, junto con los mensajes, archivos, direcciones URL y otros datos que forman parte de un conversación en curso.

La planeación de la capacidad es una parte importante de la preparación para implementar el servidor de chat persistente. En este tema se proporcionan detalles sobre las topologías de servidor de chat persistente admitidas y las tablas de planeación de capacidad que puede usar para determinar la mejor configuración para su implementación. También se describe cómo administrar mejor las implementaciones del servidor de chat persistente que requieren mayor capacidad en horas punta.

Para descargar el servidor de chat persistente, consulte "servidor de chat persistente de Microsoft Lync [https://go.microsoft.com/fwlink/p/?linkId=209539](https://go.microsoft.com/fwlink/p/?linkid=209539)Server 13" en.

Para obtener información detallada sobre la instalación del servidor de chat persistente, vea [Installing persistent chat Server in Lync server 2013](lync-server-2013-installing-persistent-chat-server.md) y [Configuring persistent chat Server in Lync Server 2013](lync-server-2013-configuring-persistent-chat-server.md) en la documentación sobre implementación.

Las herramientas de soporte, como la herramienta de planeación de Lync Server, pueden ayudarle con la planeación de capacidad. Para obtener más información sobre la herramienta de planeación, consulte [comenzar el proceso de planeación de Lync Server 2013](lync-server-2013-beginning-the-planning-process.md) en la documentación referente a la planeación.

<div>

## <a name="persistent-chat-server-supported-topologies"></a>Topologías compatibles con el servidor de chat persistente

Puede implementar un servidor de chat persistente en grupos de un solo servidor o de varios servidores, y con una topología de un único grupo o de varios grupos.

Ahora también se admite el servidor de chat persistente en un servidor Standard Edition para implementaciones nuevas de Lync Server 2013. Sin embargo, el rendimiento y la escala se verán afectados, y dado que no hay una opción de alta disponibilidad para esta nueva implementación, esperamos que lo use principalmente con fines de prueba de concepto, evaluación, etc.

<div>


> [!NOTE]  
> Para obtener más información sobre ambas topologías, consulte <A href="lync-server-2013-planning-for-persistent-chat-server.md">Planning for persistent chat Server in Lync server 2013</A> en este conjunto de documentación y <A href="lync-server-2013-deploying-persistent-chat-server.md">Deploying persistent chat Server in Lync Server 2013</A> en la documentación sobre implementación.



</div>

<div>

## <a name="single-server-topology"></a>Topología de un solo servidor

La configuración mínima y la implementación más sencilla para el servidor de chat persistente son una única topología de servidor front-end de chat persistente. Esta implementación requiere un único servidor que ejecute el servidor de chat persistente (que, opcionalmente, ejecuta el servicio de cumplimiento, si el cumplimiento está habilitado), un servidor que hospede la base de datos de SQL Server y, si es necesario el cumplimiento normativo, la base de datos de SQL Server para almacenar el datos de cumplimiento.

<div>


> [!IMPORTANT]  
> No puede agregar servidores adicionales a un grupo de servidores de chat persistente que se inicie como una implementación de un solo servidor en el generador de topologías. Se recomienda usar la topología de grupo de varios servidores, incluso si está usando un solo servidor. De este modo, podrá agregar más servidores más adelante, si es necesario. 


</div>

En la siguiente figura se muestran todos los componentes necesarios y opcionales de una topología para un servidor front-end de servidor de chat persistente único con el cumplimiento normativo.

**Servidor de chat persistente único**

![Topología de un solo servidor con servicio de cumplimiento](images/Gg398500.9168fa52-61e0-4d17-a14d-45fd32e81456(OCS.15).jpg "Topología de un solo servidor con servicio de cumplimiento")

</div>

<div>

## <a name="multiple-server-topology"></a>Topología de varios servidores

Para proporcionar mayor capacidad y confiabilidad, puede implementar una topología de varios servidores, como se describe en [Planning for persistent chat Server in Lync server 2013](lync-server-2013-planning-for-persistent-chat-server.md). La topología de varios servidores puede incluir hasta cuatro equipos activos que ejecutan el servidor de chat persistente (la alta disponibilidad y las configuraciones de recuperación ante desastres permiten hasta ocho, pero solo cuatro pueden estar activos y los cuatro restantes en espera). Cada servidor puede admitir hasta 20.000 usuarios simultáneos, para un total de 80.000 usuarios simultáneos conectados a un grupo de servidores de chat persistente con 4 servidores. Una topología de varios servidores es la misma que la topología de un único servidor, excepto en que varios servidores hospedan un servidor de chat persistente y pueden escalar más. Los distintos equipos que ejecutan el servidor de chat persistente deben residir en el mismo dominio de servicios de dominio de Active Directory que Lync Server y el servicio de cumplimiento.

En la siguiente figura se muestran todos los componentes de una topología de varios servidores con varios equipos que ejecutan el servidor de chat persistente, el servicio opcional de cumplimiento y una base de datos de cumplimiento independiente.

**Varios servidores de chat persistente**

![Topología de varios servidores](images/Gg398500.19aea898-28df-4d9b-903c-f72ef062d919(OCS.15).jpg "Topología de varios servidores")

En una implementación de servidor de chat persistente de cuatro servidores, en la que los usuarios de 80.000 pueden iniciar sesión y usar chat persistente de forma simultánea, la carga se distribuye uniformemente en 20.000 usuarios por servidor. Si un servidor deja de estar disponible, los usuarios que están conectados a ese servidor perderán el acceso al servidor de chat persistente. Los usuarios desconectados se transferirán automáticamente a los servidores restantes hasta que se restaure el servidor no disponible. En función de la cantidad de tráfico de chat persistente en la red, esta transferencia puede tardar unos minutos o más. Como es posible que cada uno de los servidores restantes aloje hasta 30.000 usuarios, se recomienda restaurar el servidor no disponible tan pronto como sea posible para evitar problemas de rendimiento. De lo contrario, puede hacer que otro servidor de chat persistente esté disponible mediante el generador de topologías o el cmdlet de Windows PowerShell **set-CsPersistentChatActiveServer**.

</div>

</div>

<div>

## <a name="persistent-chat-server-capacity-planning"></a>Planeación de capacidad del servidor de chat persistente

Las tablas siguientes pueden ayudarle con la planeación de capacidad para el servidor de chat persistente. Modelan cómo afectan las capacidades de capacidad al cambio de la configuración del servidor de chat persistente.

<div>

## <a name="planning-your-maximum-capacity-for-persistent-chat-server"></a>Planeación de la capacidad máxima para el servidor de chat persistente

Use la siguiente tabla de ejemplo para determinar el número de usuarios a los que podrá dar soporte técnico.

### <a name="persistent-chat-server-pool-maximum-capacity-sample"></a>Muestra de capacidad máxima del grupo de servidores de chat persistente

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Instancias activas del servicio de chat persistente</p></td>
<td><p><em>4</em></p></td>
</tr>
<tr class="even">
<td><p>Instancias del servicio de chat persistente</p></td>
<td><p><em>8 (4 debe estar inactivo; solo un máximo de 4 pueden estar activos)</em></p></td>
</tr>
<tr class="odd">
<td><p>Usuarios activos conectados</p></td>
<td><p><em>80,000</em></p></td>
</tr>
<tr class="even">
<td><p>Total de usuarios aprovisionados</p></td>
<td><p>150.000</p></td>
</tr>
<tr class="odd">
<td><p>Número de puntos de conexión</p></td>
<td><p>120.000</p></td>
</tr>
</tbody>
</table>


En el ejemplo anterior, el plan es admitir el número máximo de usuarios que permite el servidor de chat persistente: cuatro servidores o instancias del servicio de chat persistente (pueden tener cuatro servidores más pasivos que ejecutan el servidor de chat persistente para alta disponibilidad y recuperación ante desastres) y 20.000 usuarios por servidor, para un total de 80.000 usuarios activos.

</div>

<div>

## <a name="capacity-planning-for-managing-persistent-chat-room-access"></a>Planeación de la capacidad para administrar el acceso a salones de chat persistente

La siguiente tabla de ejemplo puede ayudarle a planificar la administración del acceso a salones de chat persistente en un grupo de servidores de chat persistente.

### <a name="managing-chat-room-access-sample"></a>Ejemplo de administración de acceso a salones de chat

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
<th></th>
<th>Salones de chat pequeños</th>
<th>Salones de chat medianos</th>
<th>Salones de chat grandes</th>
<th>Total</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Tamaño de los salones de chat (número de usuarios conectados)</p></td>
<td><p>30 por salón</p></td>
<td><p>150 por salón</p></td>
<td><p>16.000 por salón</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Salones de chat</p></td>
<td><p>32.000</p></td>
<td><p>1.067</p></td>
<td><p>10 </p></td>
<td><p>33.077</p></td>
</tr>
<tr class="odd">
<td><p>% de salones que son de tipo auditorio</p></td>
<td><p>1%</p></td>
<td><p>1%</p></td>
<td><p>50%</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>% de salones que están abiertos</p></td>
<td><p>3%</p></td>
<td><p>3%</p></td>
<td><p>50%</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Salas abiertas (no hay pertenencia explícita)</p></td>
<td><p>960</p></td>
<td><p>32</p></td>
<td><p>2,5</p></td>
<td><p>997</p></td>
</tr>
<tr class="even">
<td><p>Salones no abiertos (salas normales con pertenencia explícita)</p></td>
<td><p>31.040</p></td>
<td><p>1,035</p></td>
<td><p>2,5</p></td>
<td><p>32.080</p></td>
</tr>
<tr class="odd">
<td><p>Salones de auditorio (entrada de moderadores adicionales)</p></td>
<td><p>comprendi</p></td>
<td><p>32</p></td>
<td><p>2,5</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Salones administrados por pertenencia directa</p></td>
<td><p>50%</p></td>
<td><p>10%</p></td>
<td><p>0 %</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Salones administrados por grupos de usuarios</p></td>
<td><p>50%</p></td>
<td><p>90%</p></td>
<td><p>100 %</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Grupos de usuarios en la lista de pertenencia de cada salón de chat para salas abiertas (no se especifica explícitamente)</p></td>
<td><p>comprendi</p></td>
<td><p>comprendi</p></td>
<td><p>comprendi</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Usuarios en la lista de pertenencia de cada salón de chat para salas no abiertas</p></td>
<td><p>semestre</p></td>
<td><p>150</p></td>
<td><p>16.000</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Grupos de usuarios en la lista de pertenencia de cada salón de chat para salas no abiertas</p></td>
<td><p>3</p></td>
<td><p>2,5</p></td>
<td><p>10 </p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Usuarios y grupos de usuarios en la lista de administradores de cada salón de chat (para salones abiertos y no abiertos)</p></td>
<td><p>6 </p></td>
<td><p>6 </p></td>
<td><p>6 </p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Usuarios y grupos de usuarios en la lista de moderadores de cada salón de chat de auditorio (para salones abiertos y no abiertos)</p></td>
<td><p>6 </p></td>
<td><p>6 </p></td>
<td><p>6 </p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Entidades de pertenencia basadas en usuarios en todos los salones no abiertos</p></td>
<td><p>465.600</p></td>
<td><p>15.520</p></td>
<td><p>-</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Entidades de pertenencia basadas en grupos de usuarios en todos los salones no abiertos</p></td>
<td><p>46.560</p></td>
<td><p>4656</p></td>
<td><p>50</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Entidades basadas en usuarios y grupos de usuarios en todos los salones de chat de Auditorio</p></td>
<td><p>comprendi</p></td>
<td><p>192</p></td>
<td><p>50</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Entidades de administración basadas en usuarios y grupos de usuarios en todas las listas del administrador de salones de chat</p></td>
<td><p>192.000</p></td>
<td><p>6.400</p></td>
<td><p>60</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Usuarios activos por salón de chat</p></td>
<td><p><em>semestre</em></p></td>
<td><p><em>150</em></p></td>
<td><p><em>16.000</em></p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Salones de chat por usuario</p></td>
<td><p><em>12</em></p></td>
<td><p><em>segundo</em></p></td>
<td><p><em>segundo</em></p></td>
<td><p><em>16</em></p></td>
</tr>
<tr class="odd">
<td><p>Grupos de usuarios en la lista de pertenencia de cada salón de chat</p></td>
<td><p><em>metros</em></p></td>
<td><p><em>metros</em></p></td>
<td><p><em>15</em></p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Salones administrados por grupos de usuarios</p></td>
<td><p><em>50%</em></p></td>
<td><p><em>50%</em></p></td>
<td><p><em>50%</em></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Entidades de pertenencia basadas en grupos de usuarios en todos los salones de chat</p></td>
<td><p>155.200</p></td>
<td><p>5173</p></td>
<td><p>68</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Entidades de pertenencia basadas en usuarios en todos los salones de chat</p></td>
<td><p>465.600</p></td>
<td><p>77.600</p></td>
<td><p>72.000</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Usuarios y grupos de usuarios en las listas de administradores, moderadores y ámbitos de cada salón de chat</p></td>
<td><p>6 </p></td>
<td><p>6 </p></td>
<td><p>6 </p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Usuarios y grupos de usuarios en las listas de administradores, moderadores y ámbitos de todos los salones de chat</p></td>
<td><p>192.000</p></td>
<td><p>6400</p></td>
<td><p>60</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Entradas de control de acceso</p></td>
<td><p>704.160</p></td>
<td><p>26.768</p></td>
<td><p>160</p></td>
<td><p>731.088</p></td>
</tr>
<tr class="even">
<td><p>Máximo de entradas de control de acceso</p></td>
<td></td>
<td></td>
<td></td>
<td><p>2 millones</p></td>
</tr>
</tbody>
</table>


En el ejemplo anterior, al implementar los servidores de chat persistente de acuerdo con las instrucciones recomendadas, pueden administrar hasta 80.000 usuarios activos en un grupo de cuatro servidores con cumplimiento habilitado.

En este ejemplo se muestran los salones de chat clasificados como pequeños (30 usuarios activos en un momento dado), medio (usuarios activos de 150) y grandes (16.000 usuarios activos). El número de salones de chat de un determinado tamaño se calcula en función del número total de:

  - Usuarios activos en el sistema

  - Usuarios activos en salones de chat de tamaño determinado

  - Salones de chat del tamaño especificado que un solo usuario combina

Para cada salón de chat, la tabla de planeación de capacidad anterior especifica el número de entradas de control de acceso que están asociadas con el salón de chat, incluidas las entradas que se asignan directamente al salón de chat. Puede controlar el acceso a los salones de chat individuales mediante listas de control de acceso (ACL). También puede controlar el acceso a nivel de categoría. En una ACL, una entrada de control de acceso individual puede ser un grupo de usuarios (por ejemplo, un grupo de seguridad, una lista de distribución o un único usuario). Puede definir entradas de control de acceso para administradores de salones de chat, moderadores y miembros.

<div>


> [!IMPORTANT]  
> Al planear la estrategia de administración de salones de chat, tenga en cuenta que el número total de entradas de control de acceso permitidas es de 2 millones. Si las entradas de control de acceso calculado superan los 2 millones, el rendimiento del servidor podría degradarse de forma significativa. Para evitar este problema, siempre que sea posible, asegúrese de que las entradas de control de acceso son grupos de usuarios en lugar de usuarios individuales.



</div>

</div>

<div>

## <a name="capacity-planning-for-managing-chat-room-access-by-invitation"></a>Planeación de la capacidad para administrar el acceso al salón de chat por invitación

Puede usar la siguiente tabla de planeación de capacidad para conocer el número de invitaciones que el servidor de chat persistente crea y almacena en la base de datos de chat persistente cuando está configurada para enviar invitaciones. Para administrar invitaciones en la categoría, use la página **configuración de categoría de salón de chat** en el panel de control de Lync Server o use el cmdlet **set-CsPersistentChatCategory**de Windows PowerShell. Puede administrar invitaciones en un salón de chat (en línea con lo que permite la categoría) mediante la página de **Administración de salas** iniciada desde el cliente de Lync o mediante un cmdlet de Windows PowerShell, **set-csPersistentChatRoom**.

Los datos de ejemplo de la siguiente tabla asumen que, en la página de **configuración del salón de chat** para el 50 por ciento de todos los salones de chat, la opción **invitaciones** está establecida en **sí**.

<div>


> [!IMPORTANT]  
> Si el valor calculado para el número de invitaciones generadas por el servidor supera 1 millón, el rendimiento del servidor podría degradarse de forma significativa. Para evitar este problema, asegúrese de minimizar el número de salones de chat configurados para enviar invitaciones o restringir el número de usuarios que pueden unirse a salones de chat configurados para enviar invitaciones.



</div>

### <a name="chat-room-access-by-invitation-sample"></a>Ejemplo de acceso a salones de chat por invitación

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
<th></th>
<th>Salones de chat pequeños</th>
<th>Salones de chat medianos</th>
<th>Salones de chat grandes</th>
<th>Total</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Usuarios que pueden acceder al salón de chat</p></td>
<td><p>30 por salón</p></td>
<td><p>150 por salón</p></td>
<td><p>16.000 por salón</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Porcentaje de salones que tienen invitaciones</p></td>
<td><p>50%</p></td>
<td><p>50%</p></td>
<td><p>50%</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Salones de chat configurados para enviar invitaciones</p></td>
<td><p><em>16.000</em></p></td>
<td><p><em>533</em></p></td>
<td><p><em>2,5</em></p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Usuarios que pueden acceder al salón de chat</p></td>
<td><p><em>60</em></p></td>
<td><p><em>225</em></p></td>
<td><p><em>16.000</em></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Invitaciones generadas por el servidor de chat persistente</p></td>
<td><p>960.000</p></td>
<td><p>120.000</p></td>
<td><p>80,000</p></td>
<td><p>1.160.000</p></td>
</tr>
<tr class="even">
<td><p>Número máximo de invitaciones permitidas</p></td>
<td></td>
<td></td>
<td></td>
<td><p>2 millones</p></td>
</tr>
<tr class="odd">
<td><p>Modelo 1: comienzo con número previsto de mensajes por habitación por día</p></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p>Tasa de chats por salón (por día)</p></td>
<td><p>50</p></td>
<td><p>500</p></td>
<td><p>100</p></td>
<td><p>650</p></td>
</tr>
<tr class="odd">
<td><p>Tasa de chat (por segundo) en todas las salas</p></td>
<td><p>55,56</p></td>
<td><p>18,52</p></td>
<td><p>0,03</p></td>
<td><p>74</p></td>
</tr>
<tr class="even">
<td><p>Modelo 2: Inicio con el número de mensajes publicados por usuario y día</p></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Tasa de chat por usuario y día</p></td>
<td><p>15 </p></td>
<td><p>2,5</p></td>
<td><p>0,1</p></td>
<td><p>20</p></td>
</tr>
<tr class="even">
<td><p>Tasa de chats por salón (por día)</p></td>
<td><p>38</p></td>
<td><p>375</p></td>
<td><p>800</p></td>
<td><p>1.213</p></td>
</tr>
<tr class="odd">
<td><p>Tasa de chat (por segundo) en todas las salas</p></td>
<td><p>41,67</p></td>
<td><p>13,89</p></td>
<td><p>0,28</p></td>
<td><p>56</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="persistent-chat-server-performance-user-model"></a>Modelo de usuario de rendimiento del servidor de chat persistente

En la tabla siguiente se describe el modelo de usuario para el servidor de chat persistente. Proporciona la base para los requisitos de planeación de la capacidad y representa una organización típica con 80.000 usuarios simultáneos en cuatro servidores.

### <a name="persistent-chat-server-performance-user-model"></a>Modelo de usuario de rendimiento del servidor de chat persistente

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Número de usuarios activos conectados</p></td>
<td><p>80,000</p></td>
</tr>
<tr class="even">
<td><p>Número de instancias de servicio del servidor de chat persistente</p></td>
<td><p>4</p></td>
</tr>
<tr class="odd">
<td><p>Tamaño de salones de chat pequeños</p></td>
<td><p>30 usuarios</p></td>
</tr>
<tr class="even">
<td><p>Tamaño de salones de chat medianos</p></td>
<td><p>150 usuarios</p></td>
</tr>
<tr class="odd">
<td><p>Tamaño de salones de chat grandes</p></td>
<td><p>16.000 usuarios</p></td>
</tr>
<tr class="even">
<td><p>Cantidad total de salones de chat</p></td>
<td><p>33.077</p></td>
</tr>
<tr class="odd">
<td><p>Número de salones de chat pequeños</p></td>
<td><p>32.000</p></td>
</tr>
<tr class="even">
<td><p>Número de salones de chat medianos</p></td>
<td><p>1.067</p></td>
</tr>
<tr class="odd">
<td><p>Número de salones de chat grandes</p></td>
<td><p>10 </p></td>
</tr>
<tr class="even">
<td><p>Cantidad total de salones de chat por usuario</p></td>
<td><p>16 </p></td>
</tr>
<tr class="odd">
<td><p>Número de salones de chat pequeños por usuario</p></td>
<td><p>12</p></td>
</tr>
<tr class="even">
<td><p>Número de salones de chat medianos por usuario</p></td>
<td><p>segundo</p></td>
</tr>
<tr class="odd">
<td><p>Número de salones de chat grandes por usuario</p></td>
<td><p>segundo</p></td>
</tr>
<tr class="even">
<td><p>Número de salones Unidos por usuario</p></td>
<td><p>apartado</p></td>
</tr>
<tr class="odd">
<td><p>Tasa máxima de combinaciones</p></td>
<td><p>10/segundo</p></td>
</tr>
<tr class="even">
<td><p>Tasa de chats total</p></td>
<td><p>24/segundo</p></td>
</tr>
<tr class="odd">
<td><p>Tasa de chats para salones de chat pequeños</p></td>
<td><p>22.22/segundo</p></td>
</tr>
<tr class="even">
<td><p>Tasa de chats para salones de chat medianos</p></td>
<td><p>1.67/segundo</p></td>
</tr>
<tr class="odd">
<td><p>Tasa de chats para salones de chat grandes</p></td>
<td><p>~ 0,15/segundo</p></td>
</tr>
<tr class="even">
<td><p>Porcentaje de salones de chat configurados para invitaciones</p></td>
<td><p>50%</p></td>
</tr>
<tr class="odd">
<td><p>Porcentaje de pertenencia directa</p></td>
<td><p>50%</p></td>
</tr>
<tr class="even">
<td><p>Porcentaje de pertenencias a grupos</p></td>
<td><p>50%</p></td>
</tr>
<tr class="odd">
<td><p>Número medio de afiliaciones antecesoras en servicios de dominio de Active Directory</p></td>
<td><p>100-200</p></td>
</tr>
<tr class="even">
<td><p>Número de contactos suscritos por usuario</p></td>
<td><p>80</p></td>
</tr>
<tr class="odd">
<td><p>Número medio de puntos de conexión por usuario</p></td>
<td><p>1,5</p></td>
</tr>
<tr class="even">
<td><p>Número medio de salones de chat visibles por extremo</p></td>
<td><p>1,5</p></td>
</tr>
<tr class="odd">
<td><p>Número medio de salones de chat visibles por usuario</p></td>
<td><p>2,25 (50% para 1 habitación y 50% para 2 habitaciones); Hasta 6 salas abiertas, una por monitor</p></td>
</tr>
<tr class="even">
<td><p>Número de participantes sondeados por intervalo</p></td>
<td><p>25 por salón de chat visible</p></td>
</tr>
<tr class="odd">
<td><p>Longitud del intervalo de sondeo</p></td>
<td><p>5 minutos</p></td>
</tr>
<tr class="even">
<td><p>Número de participantes sondeados por segundo</p></td>
<td><p>15.000</p></td>
</tr>
<tr class="odd">
<td><p>Número de cambios de presencia por hora por usuario</p></td>
<td><p>6 </p></td>
</tr>
<tr class="even">
<td><p>Número de cambios de presencia por segundo</p></td>
<td><p>133,33</p></td>
</tr>
</tbody>
</table>


</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

