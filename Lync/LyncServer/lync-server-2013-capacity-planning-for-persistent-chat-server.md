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
ms.openlocfilehash: dde4bcb499e38e729850f06bb08590bf537696e5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41737030"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="capacity-planning-for-persistent-chat-server-in-lync-server-2013"></a>Planificación de capacidad para el servidor de chat persistente en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-05_

El servidor de chat persistente puede llevar a cabo una conversación en tiempo real con varios usuarios que puede persistir para una recuperación y búsqueda futura. A diferencia de la mensajería instantánea (mi) grupal que se guarda en el buzón de un usuario si está configurado el historial de conversaciones, una sesión de servidor de chat persistente permanece abierta más tiempo y el contenido se guarda en un servidor, junto con los mensajes, archivos, direcciones URL y otros datos que forman parte de un conversación en curso.

El plan de capacidad es una parte importante de la preparación para implementar un servidor de chat persistente. Este tema proporciona detalles sobre las topologías de servidores de chat persistentes compatibles y las tablas de planeación de capacidad que puede usar para determinar la mejor configuración para su implementación. También se describe cómo administrar mejor las implementaciones del servidor de chat persistentes que requieren mayor capacidad en horas punta.

Para descargar el servidor de chat persistente, consulte "servidor de chat persistente de Microsoft Lync [http://go.microsoft.com/fwlink/p/?linkId=209539](http://go.microsoft.com/fwlink/p/?linkid=209539)Server 13" en.

Para obtener más información sobre cómo instalar el servidor de chat persistente, consulte [instalar el servidor de chat persistente en Lync server 2013](lync-server-2013-installing-persistent-chat-server.md) y [configurar el servidor de chat persistente en Lync Server 2013](lync-server-2013-configuring-persistent-chat-server.md) en la documentación de implementación.

Las herramientas de soporte técnico, como la herramienta de planeación de Lync Server, pueden ayudarle aún más para planear la capacidad. Para obtener más información sobre la herramienta de planeación, consulte [comenzar el proceso de planeación de Lync Server 2013](lync-server-2013-beginning-the-planning-process.md) en la documentación de planeación.

<div>

## <a name="persistent-chat-server-supported-topologies"></a>Topologías compatibles con el servidor de chat persistente

Puede implementar un servidor de chat persistente en grupos de un solo servidor o de varios servidores, y con topología de un único grupo o de varios grupos.

También se admite el servidor de chat persistente en el servidor Standard Edition para nuevas implementaciones de Lync Server 2013. Sin embargo, el rendimiento y la escala se verán afectados, y dado que no hay una opción de alta disponibilidad para esta nueva implementación, esperamos que use esto principalmente para fines de pruebas de concepto, evaluación, etc.

<div>


> [!NOTE]  
> Para obtener más información sobre las dos topologías, vea <A href="lync-server-2013-planning-for-persistent-chat-server.md">planear el servidor de chat persistente en Lync server 2013</A> en la documentación de implementación y en <A href="lync-server-2013-deploying-persistent-chat-server.md">implementar el servidor de chat persistente en Lync Server 2013</A> .



</div>

<div>

## <a name="single-server-topology"></a>Topología de servidor único

La configuración mínima y la implementación más sencilla para el servidor de chat persistente es una topología única de servidor de chat persistente. Esta implementación requiere un único servidor que ejecute el servidor de chat persistente (que, opcionalmente, ejecuta el servicio de cumplimiento, si el cumplimiento está habilitado), un servidor que hospede tanto la base de datos de SQL Server como la de la base de datos de SQL Server para almacenar el datos de cumplimiento.

<div>


> [!IMPORTANT]  
> No puede agregar servidores adicionales a un grupo de servidores de chat persistente que se inicie como una implementación de servidor único en el generador de topología. Le recomendamos que use la topología del grupo de varios servidores, incluso si está usando un solo servidor. De esta manera, podrás agregar más servidores más adelante, si es necesario. 


</div>

La siguiente ilustración muestra todos los componentes obligatorios y opcionales de una topología para un único servidor de usuario de chat persistente con cumplimiento normativo.

**Servidor único de chat persistente**

![Topología de servidor único con servicio de cumplimiento](images/Gg398500.9168fa52-61e0-4d17-a14d-45fd32e81456(OCS.15).jpg "Topología de servidor único con servicio de cumplimiento")

</div>

<div>

## <a name="multiple-server-topology"></a>Topología de varios servidores

Para proporcionar mayor capacidad y confiabilidad, puede implementar una topología de varios servidores, como se describe en [planear el servidor de chat persistente en Lync server 2013](lync-server-2013-planning-for-persistent-chat-server.md). La topología de varios servidores puede incluir hasta cuatro equipos activos que ejecutan el servidor de chat persistente (la alta disponibilidad y las configuraciones de recuperación ante desastres permiten hasta ocho, pero solo cuatro pueden estar activos y los cuatro restantes en espera). Cada servidor puede admitir hasta 20.000 usuarios simultáneos, para un total de 80.000 usuarios simultáneos conectados a un grupo de servidores de chat persistente con 4 servidores. Una topología de varios servidores es la misma que la topología de servidor único, excepto en que varios servidores hospedan un servidor de chat persistente y pueden escalar más alto. Varios equipos que ejecutan el servidor de chat persistente deben residir en el mismo dominio de servicios de dominio de Active Directory que Lync Server y el servicio de cumplimiento.

La siguiente ilustración muestra todos los componentes de una topología de varios servidores con varios equipos que ejecutan un servidor de chat persistente, el servicio de cumplimiento opcional y una base de datos de cumplimiento independiente.

**Varios servidores de chat persistentes**

![Topología de varios servidores](images/Gg398500.19aea898-28df-4d9b-903c-f72ef062d919(OCS.15).jpg "Topología de varios servidores")

En una implementación de servidor de chat persistente de cuatro servidores, en la que los usuarios de 80.000 pueden iniciar sesión y usar la conversación de forma permanente, la carga se distribuye uniformemente en 20.000 usuarios por servidor. Si un servidor no está disponible, los usuarios que estén conectados a él perderán el acceso al servidor de chat persistente. Los usuarios desconectados se transferirán automáticamente a los servidores restantes hasta que se restaure el servidor que no se encuentra disponible. En función de la cantidad de tráfico de chat persistente en la red, esta transferencia puede demorar unos minutos o más. Como es posible que cada uno de los servidores restantes aloje hasta 30.000 usuarios, le recomendamos que restaure el servidor no disponible lo antes posible para evitar problemas de rendimiento. De lo contrario, puede hacer que otro servidor de chat persistente esté disponible con el generador de topologías o el cmdlet de Windows PowerShell **set-CsPersistentChatActiveServer**.

</div>

</div>

<div>

## <a name="persistent-chat-server-capacity-planning"></a>Planificación de capacidad del servidor de chat persistente

Las siguientes tablas pueden ayudarle con la planificación de capacidad de un servidor de chat persistente. Modelan cómo afectan las capacidades de capacidad a cambiar la configuración del servidor de chat persistente.

<div>

## <a name="planning-your-maximum-capacity-for-persistent-chat-server"></a>Planificación de su capacidad máxima para el servidor de chat persistente

Usa la siguiente tabla de muestra para determinar la cantidad de usuarios que podrás admitir.

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
<td><p>Instancias del servicio de chat persistentes</p></td>
<td><p><em>8 (4 debe estar inactivo; solo un máximo de 4 puede estar activo)</em></p></td>
</tr>
<tr class="odd">
<td><p>Usuarios activos conectados</p></td>
<td><p><em>80,000</em></p></td>
</tr>
<tr class="even">
<td><p>Cantidad total de usuarios aprovisionados</p></td>
<td><p>150,000</p></td>
</tr>
<tr class="odd">
<td><p>Cantidad de extremos</p></td>
<td><p>120,000</p></td>
</tr>
</tbody>
</table>


En el ejemplo anterior, el plan es compatible con el número máximo de usuarios que permite el servidor de chat persistente: cuatro servidores/instancias del servicio de chat persistente (pueden tener cuatro servidores más pasivos con servidor de chat persistente para una alta disponibilidad y recuperación ante desastres) y 20.000 usuarios por servidor, para un total de 80.000 usuarios activos.

</div>

<div>

## <a name="capacity-planning-for-managing-persistent-chat-room-access"></a>Planificación de capacidad para administrar el acceso permanente al salón de chat

La siguiente tabla de ejemplo puede ayudarle a planear la administración del acceso permanente al salón de chat en un grupo de servidores de chat persistente.

### <a name="managing-chat-room-access-sample"></a>Ejemplo de administración de acceso al salón de chat

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
<td><p>Tamaño de los salones de chat (cantidad de usuarios conectados)</p></td>
<td><p>30 por salón</p></td>
<td><p>150 por salón</p></td>
<td><p>16 000 por salón</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Salones de chat</p></td>
<td><p>32,000</p></td>
<td><p>1,067</p></td>
<td><p>base10</p></td>
<td><p>33,077</p></td>
</tr>
<tr class="odd">
<td><p>% de salones que son auditorios</p></td>
<td><p>1 %</p></td>
<td><p>1 %</p></td>
<td><p>50%</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>% de salones que están abiertos</p></td>
<td><p>3%</p></td>
<td><p>3%</p></td>
<td><p>50%</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Salones abiertos (ninguna pertenencia explícita)</p></td>
<td><p>960</p></td>
<td><p>32</p></td>
<td><p>5</p></td>
<td><p>997</p></td>
</tr>
<tr class="even">
<td><p>Salones no abiertos (salones regulares con pertenencia explícita)</p></td>
<td><p>31,040</p></td>
<td><p>1.035</p></td>
<td><p>5</p></td>
<td><p>32,080</p></td>
</tr>
<tr class="odd">
<td><p>Salones de auditorio (entrada de moderadores adicionales)</p></td>
<td><p>,0</p></td>
<td><p>32</p></td>
<td><p>5</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Salones administrados por pertenencia directa</p></td>
<td><p>50%</p></td>
<td><p>10%</p></td>
<td><p>0%</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Salones administrados por grupos de usuarios</p></td>
<td><p>50%</p></td>
<td><p>90%</p></td>
<td><p>100%</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Grupos de usuarios en la lista de pertenencia de cada salón de chat para los salones abiertos (no especificado explícitamente)</p></td>
<td><p>,0</p></td>
<td><p>,0</p></td>
<td><p>,0</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Usuarios en la lista de pertenencia de cada salón de chat para los salones no abiertos</p></td>
<td><p>0,30</p></td>
<td><p>150</p></td>
<td><p>16,000</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Grupos de usuarios en la lista de pertenencia de cada salón de chat para los salones no abiertos</p></td>
<td><p>3</p></td>
<td><p>5</p></td>
<td><p>base10</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Usuarios y grupos de usuarios en la lista del administrador de cada salón de chat (para salones abiertos y no abiertos)</p></td>
<td><p>6</p></td>
<td><p>6</p></td>
<td><p>6</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Usuarios y grupos de usuarios en la lista de moderadores de cada salón de chat de auditorio (para salones abiertos y no abiertos)</p></td>
<td><p>6</p></td>
<td><p>6</p></td>
<td><p>6</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Entidades de pertenencia basadas en usuarios en todos los salones no abiertos</p></td>
<td><p>465,600</p></td>
<td><p>15,520</p></td>
<td><p>-</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Entidades de pertenencia basadas en grupos de usuarios en todos los salones no abiertos</p></td>
<td><p>46,560</p></td>
<td><p>4656</p></td>
<td><p>50</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Entidades basadas en usuarios y grupos de usuarios en todos los salones de chat de auditorio</p></td>
<td><p>,0</p></td>
<td><p>192</p></td>
<td><p>50</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Entidades de administradores basadas en usuarios y grupos de usuarios en todas las listas de administrador de salones de chat</p></td>
<td><p>192,000</p></td>
<td><p>6,400</p></td>
<td><p>60</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Usuarios activos por salón de chat</p></td>
<td><p><em>0,30</em></p></td>
<td><p><em>150</em></p></td>
<td><p><em>16,000</em></p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Salones de chat por usuario</p></td>
<td><p><em>2007</em></p></td>
<td><p><em>2</em></p></td>
<td><p><em>2</em></p></td>
<td><p><em>apartado</em></p></td>
</tr>
<tr class="odd">
<td><p>Grupos de usuarios en la lista de pertenencia de cada salón de chat</p></td>
<td><p><em>base10</em></p></td>
<td><p><em>base10</em></p></td>
<td><p><em>4,5</em></p></td>
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
<td><p>155,200</p></td>
<td><p>5173</p></td>
<td><p>68</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Entidades de pertenencia basadas en usuarios en todos los salones de chat</p></td>
<td><p>465,600</p></td>
<td><p>77,600</p></td>
<td><p>72,000</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Usuarios y grupos de usuarios en las listas de administradores, moderadores y ámbitos de cada salón de chat</p></td>
<td><p>6</p></td>
<td><p>6</p></td>
<td><p>6</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Usuarios y grupos de usuarios en las listas de administradores, moderadores y ámbitos de todos los salones de chat</p></td>
<td><p>192,000</p></td>
<td><p>6400</p></td>
<td><p>60</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Entradas de control de acceso</p></td>
<td><p>704,160</p></td>
<td><p>26,768</p></td>
<td><p>160</p></td>
<td><p>731,088</p></td>
</tr>
<tr class="even">
<td><p>Máximo de entradas de control de acceso</p></td>
<td></td>
<td></td>
<td></td>
<td><p>2,000,000</p></td>
</tr>
</tbody>
</table>


En el ejemplo anterior, al implementar los servidores de chat persistentes de acuerdo con las pautas recomendadas, pueden administrar hasta 80.000 usuarios activos en un grupo de cuatro servidores con la compatibilidad habilitada.

Esta muestra representa los salones de chat clasificados como pequeños (30 usuarios activos en un momento dado), medianos (150 usuarios activos) y grandes (16 000 usuarios activos). El número de salones de chat con un tamaño determinado se calcula en función del número total de:

  - Usuarios activos en el sistema

  - Usuarios activos en los salones de chat del tamaño correspondiente

  - Salones de chat del tamaño correspondiente a los que se una un solo usuario

Para cada salón de chat, la tabla de planificación de la capacidad anterior especifica la cantidad de entradas de control de acceso asociadas al salón de chat, incluidas las entradas asignadas directamente al salón de chat. Puedes controlar el acceso a salones de chat individuales al utilizar listas de control de acceso (ACL). También puedes controlar el acceso en cuanto a la categoría. En una ACL, una entrada de control de acceso individual puede corresponder a un grupo de usuarios (por ejemplo, un grupo de seguridad, una lista de distribución o a un solo usuario). Puedes definir las entradas de control de acceso de los administradores, los moderadores y los miembros de los salones de chat.

<div>


> [!IMPORTANT]  
> A la hora de planificar tu estrategia para administrar los salones de chat, ten en cuenta que la cantidad total de entradas de control de acceso permitida es 2 millones. Si las entradas de control de acceso que calcules superan los 2 millones, el rendimiento del servidor puede disminuir en gran medida. Para evitar este problema, siempre que sea posible, asegúrate de que las entradas de control de acceso sean grupos de usuarios, en lugar de usuarios individuales.



</div>

</div>

<div>

## <a name="capacity-planning-for-managing-chat-room-access-by-invitation"></a>Planificación de capacidad para administrar el acceso al salón de chat mediante una invitación

Puede usar la siguiente tabla de planeación de capacidad para comprender el número de invitaciones que el servidor de chat persistente crea y almacena en la base de datos de chat persistente cuando está configurada para enviar invitaciones. Para administrar las invitaciones de la categoría, use la página **configuración de categoría de salón de chat** en el panel de control de Lync Server, o bien use el cmdlet de Windows PowerShell **set-csPersistentChatCategory**. Puede administrar invitaciones en un salón de chat (en función de lo que permita la categoría) mediante la página de **Administración de salas** iniciada desde el cliente Lync, o mediante un cmdlet de Windows PowerShell, **set-csPersistentChatRoom**.

Los datos de muestra de la siguiente tabla presuponen que, en la página **Configuración de salones de chat** para el 50 % de los salones de chat, la opción **Invitaciones** se ha configurado como **Sí**.

<div>


> [!IMPORTANT]  
> Si el valor calculado para la cantidad de invitaciones que el servidor genera supera 1 millón, el rendimiento del servidor puede disminuir en gran medida. Para evitar este problema, asegúrese de minimizar la cantidad de salones de chat configurados para enviar invitaciones o restringir el número de usuarios que pueden unirse a salones de chat que se han configurado para enviar invitaciones.



</div>

### <a name="chat-room-access-by-invitation-sample"></a>Acceso a salón de chat por muestra de invitación

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
<td><p>Usuarios que pueden tener acceso a salones de chat</p></td>
<td><p>30 por salón</p></td>
<td><p>150 por salón</p></td>
<td><p>16 000 por salón</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Porcentaje de salones que disponen de invitaciones</p></td>
<td><p>50%</p></td>
<td><p>50%</p></td>
<td><p>50%</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Salones de chat configurados para enviar invitaciones</p></td>
<td><p><em>16,000</em></p></td>
<td><p><em>533</em></p></td>
<td><p><em>5</em></p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Usuarios que pueden acceder al salón de chat</p></td>
<td><p><em>60</em></p></td>
<td><p><em>225</em></p></td>
<td><p><em>16,000</em></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Invitaciones generadas por el servidor de chat persistente</p></td>
<td><p>960,000</p></td>
<td><p>120,000</p></td>
<td><p>80,000</p></td>
<td><p>1,160,000</p></td>
</tr>
<tr class="even">
<td><p>Cantidad máxima de invitaciones permitidas</p></td>
<td></td>
<td></td>
<td></td>
<td><p>2,000,000</p></td>
</tr>
<tr class="odd">
<td><p>Modelo 1: Inicio con la cantidad esperada de mensajes por salón por día</p></td>
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
<td><p>Tasa de chats (por segundo) en todos los salones</p></td>
<td><p>55.56</p></td>
<td><p>18.52</p></td>
<td><p>0.03</p></td>
<td><p>74</p></td>
</tr>
<tr class="even">
<td><p>Modelo 2: Inicio con la cantidad de mensajes publicados por usuario por día</p></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Tasa de chats por usuario por día</p></td>
<td><p>4,5</p></td>
<td><p>5</p></td>
<td><p>0.1</p></td>
<td><p>veinte</p></td>
</tr>
<tr class="even">
<td><p>Tasa de chats por salón (por día)</p></td>
<td><p>38</p></td>
<td><p>375</p></td>
<td><p>800</p></td>
<td><p>1,213</p></td>
</tr>
<tr class="odd">
<td><p>Tasa de chats (por segundo) en todos los salones</p></td>
<td><p>41.67</p></td>
<td><p>13.89</p></td>
<td><p>0.28</p></td>
<td><p>56</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="persistent-chat-server-performance-user-model"></a>Modelo de usuario de rendimiento del servidor de chat persistente

En la siguiente tabla se describe el modelo de usuario para el servidor de chat persistente. Constituye la base de los requisitos de planificación de la capacidad y representa una organización típica con 80 000 usuarios simultáneos, en cuatro servidores.

### <a name="persistent-chat-server-performance-user-model"></a>Modelo de usuario de rendimiento del servidor de chat persistente

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Cantidad de usuarios activos conectados</p></td>
<td><p>80,000</p></td>
</tr>
<tr class="even">
<td><p>Número de instancias de servicio del servidor de chat persistentes</p></td>
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
<td><p>16 000 usuarios</p></td>
</tr>
<tr class="even">
<td><p>Cantidad total de salones de chat</p></td>
<td><p>33,077</p></td>
</tr>
<tr class="odd">
<td><p>Cantidad de salones de chat pequeños</p></td>
<td><p>32,000</p></td>
</tr>
<tr class="even">
<td><p>Cantidad de salones de chat medianos</p></td>
<td><p>1,067</p></td>
</tr>
<tr class="odd">
<td><p>Cantidad de salones de chat grandes</p></td>
<td><p>base10</p></td>
</tr>
<tr class="even">
<td><p>Cantidad total de salones de chat por usuario</p></td>
<td><p>apartado</p></td>
</tr>
<tr class="odd">
<td><p>Cantidad de salones de chat pequeños por usuario</p></td>
<td><p>2007</p></td>
</tr>
<tr class="even">
<td><p>Cantidad de salones de chat medianos por usuario</p></td>
<td><p>1</p></td>
</tr>
<tr class="odd">
<td><p>Cantidad de salones de chat grandes por usuario</p></td>
<td><p>1</p></td>
</tr>
<tr class="even">
<td><p>Cantidad de salones a los que se han unido por usuario</p></td>
<td><p>veinticuatro</p></td>
</tr>
<tr class="odd">
<td><p>Tasa máxima de uniones</p></td>
<td><p>10/segundo</p></td>
</tr>
<tr class="even">
<td><p>Tasa de chats total</p></td>
<td><p>24/segundo</p></td>
</tr>
<tr class="odd">
<td><p>Tasa de chats en salones de chat pequeños</p></td>
<td><p>22.22/second</p></td>
</tr>
<tr class="even">
<td><p>Tasa de chats en salones de chat medianos</p></td>
<td><p>1.67/second</p></td>
</tr>
<tr class="odd">
<td><p>Tasa de chats en salones de chat grandes</p></td>
<td><p>~0.15/second</p></td>
</tr>
<tr class="even">
<td><p>Porcentaje de salones de chat configurados con invitaciones</p></td>
<td><p>50%</p></td>
</tr>
<tr class="odd">
<td><p>Porcentaje de pertenencia directa</p></td>
<td><p>50%</p></td>
</tr>
<tr class="even">
<td><p>Porcentaje de pertenencia de grupo</p></td>
<td><p>50%</p></td>
</tr>
<tr class="odd">
<td><p>Número promedio de afiliaciones antecesoras en servicios de dominio de Active Directory</p></td>
<td><p>100 - 200</p></td>
</tr>
<tr class="even">
<td><p>Cantidad de contactos suscritos por usuario</p></td>
<td><p>80</p></td>
</tr>
<tr class="odd">
<td><p>Cantidad promedio de extremos por usuario</p></td>
<td><p>1.5</p></td>
</tr>
<tr class="even">
<td><p>Cantidad promedio de salones de chat visibles por extremo</p></td>
<td><p>1.5</p></td>
</tr>
<tr class="odd">
<td><p>Cantidad promedio de salones de chat visibles por usuario</p></td>
<td><p>2,25 (50% para 1 salón y 50% para 2 salones); hasta 6 salones abiertos, uno por monitor</p></td>
</tr>
<tr class="even">
<td><p>Cantidad de participantes sondeados por intervalo</p></td>
<td><p>25 por salón de chat visible</p></td>
</tr>
<tr class="odd">
<td><p>Longitud del intervalo de sondeo</p></td>
<td><p>5 minutos</p></td>
</tr>
<tr class="even">
<td><p>Cantidad de participantes sondeados por segundo</p></td>
<td><p>15,000</p></td>
</tr>
<tr class="odd">
<td><p>Cantidad de cambios de presencia por hora y usuario</p></td>
<td><p>6</p></td>
</tr>
<tr class="even">
<td><p>Cantidad de cambios de presencia por segundo</p></td>
<td><p>133.33</p></td>
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

