---
title: Instalación y configuración de nodos de monitor
TOCTitle: Instalación y configuración de nodos de monitor
ms:assetid: 61f6deea-e3ef-4468-9be8-a65705815ebb
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ204943(v=OCS.15)
ms:contentKeyID: 48275460
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Instalación y configuración de nodos de monitor

 

_**Última modificación del tema:** 2015-03-09_

Los *nodos de monitor* son equipos que ejecutan transacciones sintéticas de Lync Server de manera sistemática. Por su parte, las *transacciones sintéticas* son cmdlets de Windows PowerShell con los que se constata que los principales escenarios de usuario final (como la posibilidad de iniciar sesión en el sistema o de intercambiar mensajes instantáneos) funcionan según lo esperado. En Lync Server 2013, System Center Operations Manager puede ejecutar las transacciones sintéticas que figuran en la siguiente tabla. Existen tres tipos distintos de transacción sintética en la tabla:

  - **Predeterminada**. Son las transacciones sintéticas que un nodo de monitor ejecutará de manera predeterminada. Cuando se crea un nodo de monitor, existe la posibilidad de especificar las transacciones sintéticas que dicho nodo va a ejecutar (para ello sirve el parámetro Tests que el cmdlet **New-CsWatcherNodeConfiguration** utiliza). Si no se usa este parámetro al crear el nodo de monitor, este ejecutará todas las transacciones sintéticas predeterminadas y ninguna que no sea predeterminada. Esto significa que el nodo de monitor se configurará para ejecutar la prueba Test-CsAddressBookService, pero no la prueba Test-CsExumConnectivity.

  - **No predeterminada**. Como su nombre indica, las transacciones sintéticas no predeterminadas son pruebas que los nodos de monitor no ejecutan de manera predeterminada. Con todo, el nodo de monitor se puede habilitar para que ejecute cualquiera de estas transacciones sintéticas, algo que puede realizarse en el momento el que el nodo se cree (mediante el cmdlet **New-CsWatcherNodeConfiguration**) o en cualquier momento posterior. Muchas de las transacciones sintéticas no predeterminadas requieren pasos de configuración extra. Para obtener información, consulte [Instrucciones de configuración especiales para transacciones sintéticas](lync-server-2013-special-setup-instructions-for-synthetic-transactions.md).

  - **Ampliada**. Las pruebas ampliadas constituyen un tipo especial de transacción sintética no predeterminada. Al contrario de lo que sucede con otras transacciones sintéticas, las pruebas ampliadas se pueden ejecutar varias veces durante cada fase, lo que puede resultar útil a la hora de comprobar determinados comportamientos, como las rutas de voz de una red telefónica conmutada (RTC) de un grupo de servidores. Para configurar esto, basta con agregar varias instancias de una prueba ampliada a un nodo de monitor.

Para obtener información sobre cómo agregar otras transacciones sintéticas a un nodo de monitor, consulte [Administración de nodos de monitor](lync-server-2013-managing-watcher-nodes.md). Puede usar el Shell de administración de Lync Server para quitar transacciones sintéticas de un nodo de monitor.

Las transacciones sintéticas disponibles para los nodos de monitor son las siguientes:


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Nombre del cmdlet (nombre de la prueba)</th>
<th>Descripción</th>
<th>Tipo de transacción sintética</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Test-CsAddressBookService (ABS)</p></td>
<td><p>Confirma que los usuarios pueden buscar usuarios que no estén en su lista de contactos.</p></td>
<td><p>Predeterminada</p></td>
</tr>
<tr class="even">
<td><p>Test-CsAddressBookWebQuery (ABWQ)</p></td>
<td><p>Confirma que los usuarios pueden buscar usuarios que no estén en su lista de contactos mediante HTTP.</p></td>
<td><p>Predeterminada</p></td>
</tr>
<tr class="odd">
<td><p>Test-CsIM (IM)</p></td>
<td><p>Confirma que los usuarios pueden enviar mensajes instantáneos punto a punto.</p></td>
<td><p>Predeterminada</p></td>
</tr>
<tr class="even">
<td><p>Test-CsP2PAV (P2PAV)</p></td>
<td><p>Confirma que los usuarios pueden realizar llamadas de audio punto a punto (solo señalización).</p></td>
<td><p>Predeterminada</p></td>
</tr>
<tr class="odd">
<td><p>Test-CsPresence (Presence)</p></td>
<td><p>Confirma que los usuarios pueden ver la presencia de otros usuarios.</p></td>
<td><p>Predeterminada</p></td>
</tr>
<tr class="even">
<td><p>Test-CsRegistration (Registration)</p></td>
<td><p>Confirma que los usuarios pueden iniciar sesión en Lync.</p></td>
<td><p>Predeterminada</p></td>
</tr>
<tr class="odd">
<td><p>Test-CsAudioConferencingProvider (ACP)</p></td>
<td><p>No se usa en la versión local de Lync Server 2013.</p></td>
<td><p>Ampliada</p></td>
</tr>
<tr class="even">
<td><p>Test-CsPstnPeerToPeerCall (RTC)</p></td>
<td><p>Confirma que los usuarios pueden hacer y recibir llamadas con gente ajena a la empresa (números de RTC).</p></td>
<td><p>No predeterminada, ampliada</p></td>
</tr>
<tr class="odd">
<td><p>Test-CsAVConference (AvConference)</p></td>
<td><p>Confirma que los usuarios pueden crear conferencias de audio/vídeo y participar en ellas.</p></td>
<td><p>Predeterminada</p></td>
</tr>
<tr class="even">
<td><p>Test-CsAVEdgeConnectivity (AVEdgeConnectivity)</p></td>
<td><p>Confirma que los servidores perimetrales A/V pueden aceptar conexiones para las llamadas punto a punto y las llamadas de conferencia.</p></td>
<td><p>No predeterminada</p></td>
</tr>
<tr class="odd">
<td><p>Test-CsDataConference (DataConference)</p></td>
<td><p>Confirma que los usuarios pueden participar en una conferencia de colaboración de datos, una reunión en línea que engloba actividades como pizarras y sondeos.</p></td>
<td><p>No predeterminada</p></td>
</tr>
<tr class="even">
<td><p>Test-CsExumConnectivity (ExumConnectivity)</p></td>
<td><p>Confirma que un usuario se puede conectar a la Mensajería unificada de Exchange (UM).</p></td>
<td><p>No predeterminada</p></td>
</tr>
<tr class="odd">
<td><p>Test-CsGroupIM (GroupIM)</p></td>
<td><p>Confirma que los usuarios pueden enviar mensajes instantáneos durante las conferencias y participar en conversaciones de mensajes instantáneos con tres o más personas.</p></td>
<td><p>Predeterminada</p></td>
</tr>
<tr class="even">
<td><p>Test-CsGroupIM –TestJoinLauncher (JoinLauncher)</p></td>
<td><p>Confirma que los usuarios pueden crear reuniones programadas y unirse a ellas a través de un vínculo de dirección web.</p></td>
<td><p>No predeterminada</p></td>
</tr>
<tr class="odd">
<td><p>Test-CsMCXP2PIM (MCXP2PIM)</p></td>
<td><p>Confirma que los usuarios de dispositivos móviles pueden registrarse y enviar mensajes instantáneos.</p></td>
<td><p>No predeterminada</p></td>
</tr>
<tr class="even">
<td><p>Test-CsPersistentChatMessage (PersistentChatMessage)</p></td>
<td><p>Confirma que los usuarios pueden intercambiar mensajes mediante el servicio de Chat persistente.</p></td>
<td><p>No predeterminada</p></td>
</tr>
<tr class="odd">
<td><p>Test-CsUnifiedContactStore (UnifiedContactStore)</p></td>
<td><p>Confirma que se puede acceder a los contactos de un usuario a través del almacén de contactos unificados. Este almacén se puede usar para conservar un grupo único de contactos accesible desde Lync 2013, Outlook o Outlook Web Access.</p></td>
<td><p>No predeterminada</p></td>
</tr>
<tr class="even">
<td><p>Test-CsXmppIM (XmppIM)</p></td>
<td><p>Confirma que se pueden enviar mensajes instantáneos por la puerta de enlace XMPP (protocolo extensible de mensajería y presencia).</p></td>
<td><p>No predeterminada</p></td>
</tr>
</tbody>
</table>


Para usar System Center Operations Manager no es necesario instalar nodos de monitor; si no los instala, seguirá recibiendo avisos en tiempo real de los componentes de Lync Server 2013 cuando surja un problema (los módulos de administración de componentes y usuarios no usan nodos de monitor). No obstante, los nodos de monitor sí son necesarios en caso de que quiera supervisar escenarios integrales mediante el módulo de administración de supervisión activa.


> [!NOTE]
> Los administradores también pueden ejecutar las transacciones sintéticas manualmente, sin tener que usar o instalar Operations Manager. Para obtener información sobre los distintos cmdlets Test-Cs, consulte el <A href="https://docs.microsoft.com/en-us/powershell/module/skype/?view=skype-ps">Índice de cmdlets de Lync Server 2013</A>.



Las transacciones sintéticas pueden consumir una gran cantidad de memoria y tiempo de procesador del equipo según cuál sea el tamaño de su implementación. Por ello, recomendamos tener un equipo dedicado como nodo de monitor. Por ejemplo, no es aconsejable configurar un Servidor front-end como nodo de monitor. Los nodos de monitor deben reunir las especificaciones de hardware siguientes:


> [!NOTE]
> Un nodo de monitor de Microsoft Lync Server 2010 heredado no se puede combinar con uno de Lync Server 2013 en el mismo equipo. El motivo es que no se pueden instalar archivos principales de sistema de Lync Server 2010 y Lync Server 2013 en el mismo equipo.<BR>Sin embargo, los nodos de monitor de Lync Server 2013 pueden supervisar tanto Lync Server 2013 como Lync Server 2010 al mismo tiempo, ya que ambas versiones del producto admiten las transacciones sintéticas predeterminadas.



Los nodos de monitor de Lync Server 2013 se pueden implementar dentro o fuera de una empresa para comprobar aspectos como los siguientes:

   La conectividad con los grupos de servidores de usuarios de la empresa.  

   La conectividad a través de redes perimetrales de los usuarios remotos que trabajan fuera de la empresa.  

   La conectividad con aplicaciones de sucursal.  

   La conectividad con Lync Server 2010 dentro de la empresa y a través de redes perimetrales.  

Existen distintas opciones de autenticación desde dentro y fuera de la empresa que ayudan a simplificar las tareas administrativas. Para obtener información, consulte [Configuración de un nodo de monitor para ejecutar transacciones sintéticas](lync-server-2013-configuring-a-watcher-node-to-run-synthetic-transactions.md).

Si desea configurar un equipo para ser un nodo de monitor, deberá realizar los siguientes pasos después de haber instalado System Center Operations Manager e importado los módulos de administración de Lync Server 2013.

Antes de instalar los archivos principales de Lync Server 2013 y los archivos de agente de System Center, deberá asegurarse también de que el equipo que actúa como nodo de monitor reúne todos los requisitos previos necesarios para instalar Lync Server 2013. Además, dicho equipo debe tener instalados los siguientes elementos:


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Componente de hardware</th>
<th>Requisito mínimo</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>CPU</p></td>
<td><p>Lo siguiente:</p>
<ul>
<li><p>Procesador de 64 bits, cuatro núcleos, 2,33 GHz o superior</p></li>
<li><p>Procesador de 64 bits, dos canales, doble núcleo, 2,33 GHz o superior</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Memoria</p></td>
<td><p>8 GB</p></td>
</tr>
<tr class="odd">
<td><p>Sistema operativo de red</p></td>
<td><ul>
<li><p>1 adaptador de red de 1 Gbps</p></li>
<li><p>Windows Server 2008 R2, Windows Server 2012 o</p>
<p>Windows Server 2012 R2</p></li>
</ul></td>
</tr>
</tbody>
</table>


  - La versión completa de .NET Framework 4.5.

  - Windows Identity Foundation.

  - Windows PowerShell 3.0.

Cuando se cumplan todos estos requisitos previos, podrá configurar el nodo de monitor del siguiente modo:

  - Instale los archivos principales de Lync Server 2013 en el equipo que actúa como nodo de monitor.

  - Instale el agente de System Center Operations Manager en el equipo que actúa como nodo de monitor.

  - Ejecute el archivo ejecutable Watchernode.msi.

  - Use los cmdlets de **CsWatcherNodeConfiguration** para configurar usuarios de prueba para que los utilice el nodo de monitor.

