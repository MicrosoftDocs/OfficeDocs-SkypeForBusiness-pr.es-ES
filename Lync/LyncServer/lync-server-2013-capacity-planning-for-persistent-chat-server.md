---
title: "Lync Server 2013 : Plan. de capacité pr le serveur de conv. permanente"
TOCTitle: Planificar la capacidad para el servidor de chat persistente
ms:assetid: 7a850cd5-c789-4795-a8ff-083be21ae784
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg615006(v=OCS.15)
ms:contentKeyID: 48275764
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Planificar la capacidad para el servidor de chat persistente en Lync Server 2013

 

_**Última modificación del tema:** 2016-12-08_

Con el Servidor de chat persistente se pueden realizar chats multiusuario en tiempo real que persisten para poder recuperarlos y buscar en ellos más adelante. A diferencia de la mensajería instantánea (MI) de grupo que se guarda en el buzón del usuario si se configura el historial de conversaciones, las sesiones del Servidor de chat persistente permanecen más tiempo abiertas y su contenido se guarda en un servidor, junto con los mensajes, los archivos, las direcciones URL y los demás datos que se incluyan en una conversación en curso.

La planeación de la capacidad es una parte importante de la preparación para implementar Servidor de chat persistente. Este tema describe los detalles de las topologías de Servidor de chat persistente compatibles y tablas de planeación de la capacidad que puede usar para averiguar cuál es la mejor configuración para la implementación. Explica también cómo administrar mejor las implementaciones de Servidor de chat persistente que necesiten mayor capacidad en horas pico.

Para descargar el Servidor de chat persistente, vea “Servidor de chat persistente de Microsoft Lync Server 2013” en [http://go.microsoft.com/fwlink/p/?linkId=209539](http://go.microsoft.com/fwlink/p/?linkid=209539).

Para ver los detalles acerca de cómo instalar Servidor de chat persistente, consulte [Instalación del servidor de chat persistente en Lync Server 2013](lync-server-2013-installing-persistent-chat-server.md) y [Configurar servidor de chat persistente en Lync Server 2013](lync-server-2013-configuring-persistent-chat-server.md) en la documentación de planeación.

Las herramientas de soporte, como la herramienta de planeación de Lync Server, pueden serle de gran utilidad para planear la capacidad. Para más información sobre la herramienta de planeación, vea [Iniciar el proceso de planeación para Lync Server 2013](lync-server-2013-beginning-the-planning-process.md) en la documentación sobre planeación.

## Topologías compatibles con el Servidor de chat persistente

Puede implementar el Servidor de chat persistente en un grupo de un único servidor o de varios, y con una topología de un único grupo o de varios.

Ahora también ofrecemos compatibilidad del Servidor de chat persistente en el Servidor Standard Edition para nuevas implementaciones de Lync Server 2013. No obstante, el rendimiento y la escalabilidad se verán afectados y, ya que no existe ninguna opción de alta disponibilidad para esta nueva implementación, esperamos que lo utilice principalmente para la prueba de concepto o con fines de evaluación.


> [!NOTE]
> Para ver más detalles sobre estas dos topologías, consulte <A href="lync-server-2013-planning-for-persistent-chat-server.md">Planeación del servidor de chat persistente en Lync Server 2013</A> en este conjunto de documentación y <A href="lync-server-2013-deploying-persistent-chat-server.md">Implementar el servidor de chat persistente en Lync Server 2013</A> en la documentación de implementación.



## Topología de un solo servidor

La configuración mínima y la implementación más sencilla del Servidor de chat persistente es la topología de un solo Servidor front-end de Servidor de chat persistente. Requiere un servidor único para ejecutar el Servidor de chat persistente (que ejecuta opcionalmente el servicio de cumplimiento, en caso de que este se habilite), un servidor para hospedar la base de datos de SQL Server y, si se requiere el cumplimiento de normas, la base de datos de SQL Server para almacenar los datos de cumplimiento.

> [!IMPORTANT]  
> No se pueden agregar servidores adicionales a un Grupo de servidores de chat persistente que se inició como implementación de un único servidor en el Generador de topologías. Recomendamos utilizar la topología de grupos de varios servidores aunque solo se vaya a usar un único servidor, de manera que se puedan agregar otros servidores más adelante.



En la siguiente ilustración se muestran todos los componentes opcionales y obligatorios de una topología de un solo Servidor front-end de Servidor de chat persistente con el servicio de cumplimiento.

**Un solo servidor de chat persistente**

![Topología de un solo servidor con servicio de cumplimiento](images/Gg615006.9168fa52-61e0-4d17-a14d-45fd32e81456(OCS.15).jpg "Topología de un solo servidor con servicio de cumplimiento")

## Topología de varios servidores

Para ofrecer mayor capacidad y fiabilidad, puede implementar una topología de varios servidores, tal como se describe en [Planeación del servidor de chat persistente en Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md). Con la topología de varios servidores, el Servidor de chat persistente puede estar ejecutándose hasta en cuatro equipos activos (las configuraciones de recuperación ante desastres y la alta disponibilidad permitirán hasta ocho, pero solamente cuatro pueden estar activos, mientras que el resto permanecen en espera). Cada servidor puede admitir un máximo de 20.000 usuarios simultáneos para dar servicio a un total de 80.000 usuarios simultáneos conectados a un Grupo de servidores de chat persistente con 4 servidores. Las topologías de varios servidores son iguales que las de un solo servidor, salvo por el hecho de que el Servidor de chat persistente está hospedado en varios servidores y puede escalarse más. Los equipos en los que se ejecute el Servidor de chat persistente deben residir en el mismo dominio de Servicios de dominio de Active Directory que Lync Server y el servicio de cumplimiento.

En la ilustración siguiente se muestran todos los componentes de una topología de varios servidores con varios equipos en los que se ejecuta el Servidor de chat persistente, el servicio opcional de cumplimiento y una base de datos de cumplimiento independiente.

**Varios servidores de chat persistente**

![Topología de varios servidores](images/Gg615006.19aea898-28df-4d9b-903c-f72ef062d919(OCS.15).jpg "Topología de varios servidores")

En una implementación del Servidor de chat persistente de cuatro servidores, donde 80.000 usuarios pueden tener una sesión abierta y usar el Chat persistente simultáneamente, la carga se distribuye a partes iguales con 20.000 usuarios en cada servidor. Si uno de los servidores deja de estar disponible, los usuarios conectados a ese servidor perderán el acceso al Servidor de chat persistente. Los usuarios desconectados se transferirán automáticamente al resto de los servidores hasta que se restaure el servidor no disponible. Dependiendo de la cantidad de tráfico del Chat persistente en la red, esta transferencia puede tardar unos pocos minutos o más tiempo. Dado que cada uno de los servidores restantes puede hospedar hasta 30.000 usuarios, recomendamos restaurar el servidor que no está disponible tan pronto como sea posible para evitar problemas de rendimiento. De lo contrario, puede habilitar otro Servidor de chat persistente utilizando el Generador de topologías o el cmdlet de Windows PowerShell, **set-CsPersistentChatActiveServer**.

## Planeación de la capacidad del Servidor de chat persistente

Las siguientes tablas pueden ayudarle a planear la capacidad del Servidor de chat persistente. En ellas se indica cómo los cambios de diversas configuraciones del Servidor de chat persistente influyen en las funcionalidades de capacidad.

## Planeación de su capacidad máxima para el Servidor de chat persistente

Use la siguiente tabla de muestra para averiguar el número de usuarios que podrá admitir.

### Muestra de capacidad máxima del Grupo de servidores de chat persistente

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Instancias activas del servicio de Chat persistente</p></td>
<td><p><em>4</em></p></td>
</tr>
<tr class="even">
<td><p>Instancias del servicio de Chat persistente</p></td>
<td><p><em>8 (4 must be inactive; only a maximum of 4 can be active)</em></p></td>
</tr>
<tr class="odd">
<td><p>Usuarios activos conectados</p></td>
<td><p><em>80,000</em></p></td>
</tr>
<tr class="even">
<td><p>Número total de usuarios configurados</p></td>
<td><p>150.000</p></td>
</tr>
<tr class="odd">
<td><p>Número de extremos</p></td>
<td><p>120.000</p></td>
</tr>
</tbody>
</table>


En el ejemplo anterior, el plan es permitir la máxima cantidad de usuarios que permita el Servidor de chat persistente: cuatro servidores o instancias del servicio de Chat persistente (que puede tener cuatro servidores pasivos más ejecutando el Servidor de chat persistente por alta disponibilidad y recuperación ante desastres) y 20.000 usuarios por servidor, con un total de 80.000 usuarios activos.

## Planeación de la capacidad para administrar el acceso a los salones de Chat persistente

La siguiente tabla de muestra puede ayudarle a planear la administración del acceso a los salones de chat de Chat persistente en un Grupo de servidores de chat persistente.

### Muestra de administración del acceso a salones de chat

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
<td><p>Tamaño de salones de chat (número de usuarios conectados)</p></td>
<td><p>30 por salón</p></td>
<td><p>150 por salón</p></td>
<td><p>16.000 por salón</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>Salones de chat</p></td>
<td><p>32.000</p></td>
<td><p>1.067</p></td>
<td><p>10</p></td>
<td><p>33.077</p></td>
</tr>
<tr class="odd">
<td><p>% de salones que son auditorio</p></td>
<td><p>1%</p></td>
<td><p>1%</p></td>
<td><p>50%</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>% de salones que están abiertos</p></td>
<td><p>3%</p></td>
<td><p>3%</p></td>
<td><p>50%</p></td>
<td><p></p></td>
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
<td><p>31.040</p></td>
<td><p>1,035</p></td>
<td><p>5</p></td>
<td><p>32.080</p></td>
</tr>
<tr class="odd">
<td><p>Salones de auditorio (entrada de moderadores adicionales)</p></td>
<td><p>0</p></td>
<td><p>32</p></td>
<td><p>5</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>Salones administrados por pertenencia directa</p></td>
<td><p>50%</p></td>
<td><p>10%</p></td>
<td><p>0%</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>Salones administrados por grupos de usuarios</p></td>
<td><p>50%</p></td>
<td><p>90%</p></td>
<td><p>100%</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>Grupos de usuarios en la lista de miembros de cada salón de chat para salones abiertos (no especificado explícitamente)</p></td>
<td><p>0</p></td>
<td><p>0</p></td>
<td><p>0</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>Usuarios en la lista de miembros de cada salón de chat para salones no abiertos</p></td>
<td><p>30</p></td>
<td><p>150</p></td>
<td><p>16.000</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>Grupos de usuarios en la lista de miembros de cada salón de chat para salones no abiertos</p></td>
<td><p>3</p></td>
<td><p>5</p></td>
<td><p>10</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>Usuarios y grupos de usuarios en la lista del administrador de cada salón de chat (para salones abiertos y no abiertos)</p></td>
<td><p>6</p></td>
<td><p>6</p></td>
<td><p>6</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>Usuarios y grupos de usuarios en la lista de moderadores de cada salón de chat de auditorio (para salones abiertos y no abiertos)</p></td>
<td><p>6</p></td>
<td><p>6</p></td>
<td><p>6</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>Entidades de miembros basadas en usuarios en todos los salones no abiertos</p></td>
<td><p>465.600</p></td>
<td><p>15.520</p></td>
<td><p>-</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>Entidades de miembros basadas en grupos de usuarios en todos los salones no abiertos</p></td>
<td><p>46.560</p></td>
<td><p>4656</p></td>
<td><p>50</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>Entidades basadas en usuarios y grupos de usuarios en todos los salones de chat de auditorio</p></td>
<td><p>0</p></td>
<td><p>192</p></td>
<td><p>50</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>Entidades de administradores basdas en usuarios y grupos de usuarios en todas las listas de administrador de salones de chat</p></td>
<td><p>192.000</p></td>
<td><p>6.400</p></td>
<td><p>60</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>Usuarios activos por salón de chat</p></td>
<td><p><em>30</em></p></td>
<td><p><em>150</em></p></td>
<td><p><em>16,000</em></p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>Salones de chat por usuario</p></td>
<td><p><em>12</em></p></td>
<td><p><em>2</em></p></td>
<td><p><em>2</em></p></td>
<td><p><em>16</em></p></td>
</tr>
<tr class="odd">
<td><p>Grupos de usuarios en la lista de miembros de cada salón de chat</p></td>
<td><p><em>10</em></p></td>
<td><p><em>10</em></p></td>
<td><p><em>15</em></p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>Salones administrados por grupos de usuarios</p></td>
<td><p><em>50%</em></p></td>
<td><p><em>50%</em></p></td>
<td><p><em>50%</em></p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>Entidades de miembros basadas en grupos de usuarios en todos los salones de chat</p></td>
<td><p>155.200</p></td>
<td><p>5173</p></td>
<td><p>68</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>Entidades de miembros basadas en usuarios en todos los salones de chat</p></td>
<td><p>465.600</p></td>
<td><p>77.600</p></td>
<td><p>72.000</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>Usuarios y grupos de usuarios en las listas de administradores, moderadores y ámbitos de cada salón de chat</p></td>
<td><p>6</p></td>
<td><p>6</p></td>
<td><p>6</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>Usuarios y grupos de usuarios en las listas de administradores, moderadores y ámbitos de todos los salones de chat</p></td>
<td><p>192.000</p></td>
<td><p>6400</p></td>
<td><p>60</p></td>
<td><p></p></td>
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
<td><p></p></td>
<td><p></p></td>
<td><p></p></td>
<td><p>2.000.000</p></td>
</tr>
</tbody>
</table>


En la muestra anterior, al implementar los Servidores de chat persistente según las recomendaciones, podrán abarcar hasta 80.000 usuarios activos en un grupo de cuatro servidores con cumplimiento habilitado.

Esta muestra representa los salones de chat clasificados como pequeños (30 usuarios activos en un momento dado), medianos (150 usuarios activos) y grandes (16.000 usuarios activos). El número de salones de chat de un tamaño determinado se calcula según el número total de:

  - Usuarios activos en el sistema

  - Usuarios activos en los salones de chat del tamaño correspondiente

  - Salones de chat del tamaño correspondiente a los que se una un solo usuario

Para cada salón de chat, la tabla de planeación de la capacidad anterior especifica el número de entradas de control de acceso asociadas al salón de chat, incluidas las entradas asignadas directamente al salón de chat. Puede controlar el acceso a salones de chat individuales usando listas de control de acceso (ACL). También puede controlar el acceso en el nivel de categoría. En una ACL, una entrada de control de acceso individual puede corresponder a un grupo de usuarios (por ejemplo, un grupo de seguridad, una lista de distribución o a un solo usuario). Puede definir las entradas de control de acceso de los administradores, los moderadores y los miembros de los salones de chat.

> [!IMPORTANT]  
> A la hora de planear su estrategia para administrar salones de chat, tenga en cuenta que el número total de entradas de control de acceso permitidas es 2 millones. Si las entradas de control de acceso que calcule superan los 2 millones, el rendimiento del servidor puede disminuir en gran medida. Para evitar este problema, siempre que sea posible, asegúrese de que las entradas de control de acceso sean grupos de usuarios, en lugar de usuarios individuales.



## Planeación de la capacidad para administrar el acceso a los salones de chat por invitación

En la siguiente tabla de planeación de la capacidad puede ver el número de invitaciones que el Servidor de chat persistente crea y almacena en la base de datos del Chat persistente cuando se configura para enviar invitaciones. Puede administrar las invitaciones de la Categoría desde la página de **Configuración de la Categoría de los salones de chat** , en el Panel de control de Lync Server, o mediante el cmdlet de Windows PowerShell, **set-csPersistentChatCategory**. Puede administrar las invitaciones en un salón de chat (en línea con lo que permite la categoría) desde la página **Administración de los salones** iniciada desde el cliente de Lync, o bien con un cmdlet de Windows PowerShell, **set-csPersistentChatRoom**.

Los datos de muestra de la siguiente tabla presuponen que, en la página de **Configuración de salones de chat** para el 50% de los salones de chat, la opción **Invitación** se ha configurado como **Sí** .

> [!IMPORTANT]  
> Si el valor calculado del número de invitaciones que el servidor genera supera 1 millón, el rendimiento del servidor puede disminuir en gran medida. Para evitar este problema, asegúrese de reducir al mínimo el número de salones de chat configurados para enviar invitaciones o restrinja la cantidad de usuarios que pueden unirse a los salones de chat que se hayan configurado para enviar invitaciones.



### Muestra de acceso a salones de chat por invitación

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
<td><p>Usuarios que pueden tener acceso a salas de chat</p></td>
<td><p>30 por salón</p></td>
<td><p>150 por salón</p></td>
<td><p>16.000 por salón</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>Porcentaje de salones que disponen de invitaciones</p></td>
<td><p>50%</p></td>
<td><p>50%</p></td>
<td><p>50%</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>Salones de chat configurados para enviar invitaciones</p></td>
<td><p><em>16,000</em></p></td>
<td><p><em>533</em></p></td>
<td><p><em>5</em></p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>Usuarios que pueden acceder al salón de chat</p></td>
<td><p><em>60</em></p></td>
<td><p><em>225</em></p></td>
<td><p><em>16,000</em></p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>Invitaciones generadas por Servidor de chat persistente</p></td>
<td><p>960.000</p></td>
<td><p>120.000</p></td>
<td><p>80.000</p></td>
<td><p>1.160.000</p></td>
</tr>
<tr class="even">
<td><p>Número máximo de invitaciones permisible</p></td>
<td><p></p></td>
<td><p></p></td>
<td><p></p></td>
<td><p>2.000.000</p></td>
</tr>
<tr class="odd">
<td><p>Modelo 1: Inicio con el número esperado de mensajes por salón por día</p></td>
<td><p></p></td>
<td><p></p></td>
<td><p></p></td>
<td><p></p></td>
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
<td><p>55,56</p></td>
<td><p>18,52</p></td>
<td><p>0,03</p></td>
<td><p>74</p></td>
</tr>
<tr class="even">
<td><p>Modelo 2: Inicio con el número de mensajes publicados por usuario por día</p></td>
<td><p></p></td>
<td><p></p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>Tasa de chats por usuario por día</p></td>
<td><p>15</p></td>
<td><p>5</p></td>
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
<td><p>Tasa de chats (por segundo) en todos los salones</p></td>
<td><p>41,67</p></td>
<td><p>13,89</p></td>
<td><p>0,28</p></td>
<td><p>56</p></td>
</tr>
</tbody>
</table>


## Modelo de usuario de rendimiento del Servidor de chat persistente

La siguiente tabla describe el modelo de usuario de Servidor de chat persistente. Constituye la base de los requisitos de planeación de la capacidad y representa una organización típica con 80.000 usuarios simultáneos, en cuatro servidores.

### Modelo de usuario de rendimiento del Servidor de chat persistente

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Número de usuarios activos conectados</p></td>
<td><p>80.000</p></td>
</tr>
<tr class="even">
<td><p>Número de instancias de servicio de Servidor de chat persistente</p></td>
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
<td><p>Número total de salones de chat</p></td>
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
<td><p>10</p></td>
</tr>
<tr class="even">
<td><p>Número total de salones de chat por usuario</p></td>
<td><p>16</p></td>
</tr>
<tr class="odd">
<td><p>Número de salones de chat pequeños por usuario</p></td>
<td><p>12</p></td>
</tr>
<tr class="even">
<td><p>Número de salones de chat medianos por usuario</p></td>
<td><p>2</p></td>
</tr>
<tr class="odd">
<td><p>Número de salones de chat grandes por usuario</p></td>
<td><p>2</p></td>
</tr>
<tr class="even">
<td><p>Número de salones a los que se han unido por usuario</p></td>
<td><p>24</p></td>
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
<td><p>22,22/segundo</p></td>
</tr>
<tr class="even">
<td><p>Tasa de chats en salones de chat medianos</p></td>
<td><p>1,67/segundo</p></td>
</tr>
<tr class="odd">
<td><p>Tasa de chats en salones de chat grandes</p></td>
<td><p>~0,15/segundo</p></td>
</tr>
<tr class="even">
<td><p>Porcentaje de salones de chat configurados con invitaciones</p></td>
<td><p>50%</p></td>
</tr>
<tr class="odd">
<td><p>Porcentaje de miembros directos</p></td>
<td><p>50%</p></td>
</tr>
<tr class="even">
<td><p>Porcentaje de miembros de grupo</p></td>
<td><p>50%</p></td>
</tr>
<tr class="odd">
<td><p>Número medio de afiliaciones de antecesores en Servicios de dominio de Active Directory</p></td>
<td><p>100 - 200</p></td>
</tr>
<tr class="even">
<td><p>Número de contactos suscritos por usuario</p></td>
<td><p>80</p></td>
</tr>
<tr class="odd">
<td><p>Promedio de extremos por usuario</p></td>
<td><p>1,5</p></td>
</tr>
<tr class="even">
<td><p>Número medio de salones de chat visibles por extremo</p></td>
<td><p>1,5</p></td>
</tr>
<tr class="odd">
<td><p>Número medio de salones de chat visibles por usuario</p></td>
<td><p>2,25 (50% para 1 salón y 50% para 2 salones); hasta 6 salones abiertos, uno por monitor</p></td>
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
<td><p>Número de cambios de presencia por hora y usuario</p></td>
<td><p>6</p></td>
</tr>
<tr class="even">
<td><p>Número de cambios de presencia por segundo</p></td>
<td><p>133,33</p></td>
</tr>
</tbody>
</table>

