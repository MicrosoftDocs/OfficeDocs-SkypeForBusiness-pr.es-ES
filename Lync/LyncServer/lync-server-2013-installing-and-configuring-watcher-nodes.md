---
title: 'Lync Server 2013: instalación y configuración de nodos de monitor'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Installing and configuring watcher nodes
ms:assetid: 61f6deea-e3ef-4468-9be8-a65705815ebb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204943(v=OCS.15)
ms:contentKeyID: 48184284
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 89465227e351da3c69116201efe5ee4eab89eca4
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726170"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="installing-and-configuring-watcher-nodes-in-lync-server-2013"></a>Instalar y configurar nodos de monitor en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-11-07_

Los *nodos de monitor* son equipos que ejecutan transacciones sintéticas de Lync Server de forma periódica. *Las transacciones sintéticas* son cmdlets de Windows PowerShell que comprueban que los escenarios clave para usuarios finales, como la posibilidad de iniciar sesión en el sistema o la posibilidad de intercambiar mensajes instantáneos, funcionan de la manera esperada. Para Lync Server 2013, System Center Operations Manager puede ejecutar las transacciones sintéticas que se muestran en la tabla siguiente. En la tabla se muestran tres tipos de transacciones sintéticos diferentes:

  - **Valor predeterminado**. Estas son las transacciones sintéticas que un nodo de monitor se ejecutará de forma predeterminada. Al crear un nuevo nodo de monitor, tiene la opción de especificar qué transacciones sintéticas se ejecutarán. (Este es el propósito del parámetro tests usado por el cmdlet **New-CsWatcherNodeConfiguration** ). Si no usa el parámetro tests cuando se crea el nodo de monitor, se ejecutarán automáticamente todas las transacciones sintéticas predeterminadas y no se ejecutará ninguna de las transacciones sintéticas no predeterminadas. Esto significa que, por ejemplo, el nodo de monitor se configurará para ejecutar la prueba de prueba de CsAddressBookService, pero no se configurará para ejecutar la prueba de CsExumConnectivity de prueba.

  - **No predeterminado**. Como el nombre indica, las transacciones sintéticas no predeterminadas no se ejecutan de forma predeterminada. Sin embargo, el nodo de monitor se puede habilitar para ejecutar cualquiera de las que transacciones sintéticas que no son predeterminados. Puede hacerlo cuando cree el nodo de monitor (mediante el cmdlet **New-CsWatcherNodeConfiguration** ) o en cualquier otro momento después de ese. Muchas de las transacciones sintéticas no predeterminadas requieren pasos de configuración adicionales. Para obtener más información, consulte [instrucciones especiales de configuración para transacciones sintéticas en Lync Server 2013](lync-server-2013-special-setup-instructions-for-synthetic-transactions.md).

  - **Ampliado**. Las pruebas extendidas son un tipo especial de transacción sintética no predeterminada. A diferencia de otras transacciones sintéticas, las pruebas extendidas se pueden ejecutar varias veces durante cada pasada. Esto puede ser útil al comprobar el comportamiento como varias rutas de voz de la red telefónica conmutada (RTC) para un grupo. Esto se puede configurar simplemente agregando varias instancias de una prueba extendida a un nodo de monitor.

Para más información sobre el proceso de adición de otras transacciones sintéticas a un nodo de monitor, vea [administrar nodos de monitor en Lync Server 2013](lync-server-2013-managing-watcher-nodes.md). Puede usar el shell de administración de Lync Server para quitar transacciones sintéticas de un nodo de monitor.

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
<td><p>Confirma que los usuarios pueden buscar usuarios que no se encuentran en su lista de contactos.</p></td>
<td><p>Valor predeterminado</p></td>
</tr>
<tr class="even">
<td><p>Test-CsAddressBookWebQuery (ABWQ)</p></td>
<td><p>Confirma que los usuarios pueden buscar usuarios que no se encuentran en su lista de contactos a través de HTTP.</p></td>
<td><p>Valor predeterminado</p></td>
</tr>
<tr class="odd">
<td><p>Prueba-CsIM (mi)</p></td>
<td><p>Confirma que los usuarios pueden enviar mensajes instantáneos punto a punto.</p></td>
<td><p>Valor predeterminado</p></td>
</tr>
<tr class="even">
<td><p>Test-CsP2PAV (P2PAV)</p></td>
<td><p>Confirma que los usuarios pueden realizar llamadas de audio de punto a punto (solo señalización).</p></td>
<td><p>Valor predeterminado</p></td>
</tr>
<tr class="odd">
<td><p>Test-CsPresence (Presence)</p></td>
<td><p>Confirma que los usuarios pueden ver la presencia de otros usuarios.</p></td>
<td><p>Valor predeterminado</p></td>
</tr>
<tr class="even">
<td><p>Test-CsRegistration (Registration)</p></td>
<td><p>Confirma que los usuarios pueden iniciar sesión en Lync.</p></td>
<td><p>Valor predeterminado</p></td>
</tr>
<tr class="odd">
<td><p>Prueba-CsAudioConferencingProvider (ACP)</p></td>
<td><p>No se utiliza con la versión local de Lync Server 2013</p></td>
<td><p>Textos</p></td>
</tr>
<tr class="even">
<td><p>Test-CsPstnPeerToPeerCall (RTC)</p></td>
<td><p>Confirma que los usuarios pueden hacer y recibir llamadas con gente ajena a la empresa (números de RTC).</p></td>
<td><p>No predeterminado, ampliado</p></td>
</tr>
<tr class="odd">
<td><p>Test-CsAVConference (AvConference)</p></td>
<td><p>Confirma que los usuarios pueden crear conferencias de audio/vídeo y participar en ellas.</p></td>
<td><p>Valor predeterminado</p></td>
</tr>
<tr class="even">
<td><p>Test-CsAVEdgeConnectivity (AVEdgeConnectivity)</p></td>
<td><p>Confirma que los servidores perimetrales a/V pueden aceptar conexiones de llamadas de punto a punto y llamadas en conferencia.</p></td>
<td><p>No predeterminada</p></td>
</tr>
<tr class="odd">
<td><p>Test-CsDataConference (DataConference)</p></td>
<td><p>Confirma que los usuarios pueden participar en una conferencia de colaboración de datos, una reunión en línea que incluye actividades como pizarras y sondeos.</p></td>
<td><p>No predeterminada</p></td>
</tr>
<tr class="even">
<td><p>Test-CsExumConnectivity (ExumConnectivity)</p></td>
<td><p>Confirma que un usuario puede conectarse a la mensajería unificada de Exchange (UM).</p></td>
<td><p>No predeterminada</p></td>
</tr>
<tr class="odd">
<td><p>Prueba-CsGroupIM (GroupIM)</p></td>
<td><p>Confirma que los usuarios pueden enviar mensajes instantáneos durante las conferencias y participar en conversaciones de mensajes instantáneos con tres o más personas.</p></td>
<td><p>Valor predeterminado</p></td>
</tr>
<tr class="even">
<td><p>Test-CsGroupIM –TestJoinLauncher (JoinLauncher)</p></td>
<td><p>Confirma que los usuarios pueden crear y unirse a reuniones programadas a través de un vínculo de dirección Web.</p></td>
<td><p>No predeterminada</p></td>
</tr>
<tr class="odd">
<td><p>Test-CsMCXP2PIM (MCXP2PIM)</p></td>
<td><p>Confirma que los usuarios de dispositivos móviles pueden registrarse y enviar mensajes instantáneos.</p></td>
<td><p>No predeterminada</p></td>
</tr>
<tr class="even">
<td><p>Test-CsPersistentChatMessage (PersistentChatMessage)</p></td>
<td><p>Confirma que los usuarios pueden intercambiar mensajes mediante el servicio de chat persistente.</p></td>
<td><p>No predeterminada</p></td>
</tr>
<tr class="odd">
<td><p>Test-CsUnifiedContactStore (UnifiedContactStore)</p></td>
<td><p>Confirma que se puede acceder a los contactos de un usuario a través del almacén de contactos unificados. El almacén de contactos unificado proporciona a los usuarios una manera de mantener un único conjunto de contactos al que se puede obtener acceso mediante Lync 2013, Outlook y Outlook Web Access.</p></td>
<td><p>No predeterminada</p></td>
</tr>
<tr class="even">
<td><p>Test-CsXmppIM (XmppIM)</p></td>
<td><p>Confirma que un mensaje instantáneo puede enviarse a través de la puerta de enlace XMPP (Protocolo de presencia y mensajería extensible).</p></td>
<td><p>No predeterminada</p></td>
</tr>
</tbody>
</table>


No es necesario instalar nodos de monitor para usar System Center Operations Manager. Si no instala estos nodos, aún podrá recibir alertas en tiempo real de los componentes de Lync Server 2013 cuando se produzca un problema. (El paquete de administración de componentes y usuarios no usa nodos de monitor). Sin embargo, se necesitan nodos de monitor si desea supervisar escenarios descentralizados mediante el módulo de administración de supervisión activa.

<div>


> [!NOTE]  
> Los administradores también pueden ejecutar transacciones sintéticas de forma manual, sin necesidad de usar ni instalar Operations Manager. Para obtener más información sobre los diversos cmdlets test-CS, consulte el <A href="https://docs.microsoft.com/powershell/module/skype/?view=skype-ps">Índice cmdlets de 2013 de Lync Server</A>.



</div>

Según el tamaño de la implementación, las transacciones sintéticas pueden usar una gran cantidad de memoria del equipo y tiempo de procesador. Por esta razón, le recomendamos que use un equipo dedicado como nodo de monitor. Por ejemplo, no debe configurar un servidor front-end para que actúe como nodo de monitor. Los nodos de monitor deben cumplir las siguientes especificaciones de hardware:

<div>


> [!NOTE]  
> No se puede colocar un nodo de monitor heredado de Microsoft Lync Server 2010 en el mismo equipo con un nodo de monitor de Lync Server 2013. Esto se debe a que los archivos del sistema del núcleo de Lync Server 2010 y Lync Server 2013 no se pueden instalar en el mismo equipo.<BR>Sin embargo, los nodos de monitor de Lync Server 2013 pueden supervisar de forma simultánea Lync Server 2013 y Lync Server 2010. Las transacciones sintéticas predeterminadas son compatibles con ambas versiones del producto.



</div>

Los nodos de monitor de Lync Server 2013 se pueden implementar dentro o fuera de una empresa para ayudar a comprobar:

  - <span></span>  
    La conectividad con los grupos de servidores de usuarios de la empresa.

  - <span></span>  
    Conectividad a través de redes perimetrales para usuarios remotos que trabajan fuera de la empresa.

  - <span></span>  
    La conectividad con aplicaciones de sucursal.

  - <span></span>  
    Conectividad con Lync Server 2010 dentro de la empresa y a través de redes perimetrales.

Hay diferentes opciones de autenticación disponibles para el interior y el exterior de la empresa para ayudar a simplificar la administración. Para obtener más información, vea [configurar un nodo de monitor para ejecutar transacciones sintéticas en Lync Server 2013](lync-server-2013-configuring-a-watcher-node-to-run-synthetic-transactions.md).

Para configurar un equipo para que funcione como un nodo de monitor, debe completar los siguientes pasos después de instalar System Center Operations Manager e importar los paquetes de administración de Lync Server 2013.

Antes de instalar los archivos básicos de Lync Server 2013 y los archivos del agente de System Center, también debe asegurarse de que el equipo del nodo de supervisor cumpla todos los requisitos previos para instalar Lync Server 2013. Además, el equipo del nodo de monitor también debe tener instalados los siguientes elementos:


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
<td><p>Uno de los siguientes:</p>
<ul>
<li><p>Procesador de 64 bits, cuatro núcleos, 2,33 GHz o superior</p></li>
<li><p>Procesador de 64 bits, dos canales, doble núcleo, 2,33 GHz o superior</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Memoria</p></td>
<td><p>8 GB</p></td>
</tr>
<tr class="odd">
<td><p>Sistema operativo de red</p></td>
<td><ul>
<li><p>1 adaptador de red de 1 Gbps</p></li>
<li><p>Windows Server 2008 R2, Windows Server 2012 o</p>
<p>Windows Server 2012 R2</p></li>
</ul></td>
</tr>
</tbody>
</table>


  - La versión completa de .NET Framework 4,5.

  - Windows Identity Foundation.

  - Windows PowerShell 3,0.

En cuanto se cumplan todos estos requisitos previos, puede configurar el nodo de monitor de la manera siguiente:

  - Instalar los archivos principales de Lync Server 2013 en el equipo del nodo de monitor.

  - Instalar el agente de System Center Operations Manager en el equipo del nodo de monitor.

  - Ejecutar el archivo ejecutable Watchernode. msi.

  - Usar los cmdlets de **CsWatcherNodeConfiguration** para configurar los usuarios de prueba que usará el nodo de monitor.

</div>

<span> </span>

</div>

</div>

</div>

