---
title: 'Lync Server 2013: instalar y configurar nodos de monitor'
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
ms.openlocfilehash: 1765e9108619c5947eda02dd758aa764b0b407e6
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42197063"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="installing-and-configuring-watcher-nodes-in-lync-server-2013"></a>Instalación y configuración de nodos de monitor en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-11-07_

Los *nodos de monitor* son equipos que ejecutan periódicamente transacciones sintéticas de Lync Server. *Las transacciones sintéticas* son cmdlets de Windows PowerShell que comprueban que los escenarios clave de usuario final (como la capacidad de iniciar sesión en el sistema o la capacidad de intercambiar mensajes instantáneos) funcionan según lo esperado. Para Lync Server 2013, System Center Operations Manager puede ejecutar las transacciones sintéticas que se muestran en la tabla siguiente. Existen tres tipos distintos de transacción sintética en la tabla:

  - **Valor predeterminado**. Estas son las transacciones sintéticas que se ejecutarán de forma predeterminada con un nodo de monitor. Al crear un nuevo nodo de monitor, tiene la opción de especificar qué transacciones sintéticas se ejecutarán. (Este es el propósito del parámetro tests usado por el cmdlet **New-CsWatcherNodeConfiguration** ). Si no usa el parámetro tests cuando se crea el nodo de monitor, se ejecutarán automáticamente todas las transacciones sintéticas predeterminadas y no se ejecutará ninguna de las transacciones sintéticas que no sean predeterminadas. Esto significa que, por ejemplo, el nodo de monitor se configurará para ejecutar la prueba test-CsAddressBookService, pero no se configurará para ejecutar la prueba test-CsExumConnectivity.

  - **No predeterminado**. Como su nombre indica, las transacciones sintéticas no predeterminadas son pruebas que los nodos de monitor no se ejecutan de forma predeterminada. Sin embargo, el nodo de monitor se puede habilitar para ejecutar cualquiera de las transacciones sintéticas que no son predeterminadas. Puede hacerlo cuando cree el nodo de monitor (mediante el cmdlet **New-CsWatcherNodeConfiguration** ) o en cualquier momento después. Muchas de las transacciones sintéticas no predeterminadas requieren pasos de configuración adicionales. Para obtener más información, consulte [instrucciones de configuración especiales para transacciones sintéticas en Lync Server 2013](lync-server-2013-special-setup-instructions-for-synthetic-transactions.md).

  - **Ampliado**. Las pruebas extendidas son un tipo especial de transacción sintética no predeterminada. A diferencia de otras transacciones sintéticas, las pruebas extendidas se pueden ejecutar varias veces durante cada pasada. Esto puede ser útil cuando se comprueba el comportamiento como varias rutas de voz de red telefónica conmutada (RTC) para un grupo de servidores. Esto se puede configurar simplemente agregando varias instancias de una prueba extendida a un nodo de monitor.

Para obtener información detallada sobre el proceso de agregar otras transacciones sintéticas a un nodo de monitor, consulte [administrar nodos de monitor en Lync Server 2013](lync-server-2013-managing-watcher-nodes.md). Puede usar el shell de administración de Lync Server para quitar transacciones sintéticas de un nodo de monitor.

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
<td><p>Valor predeterminado</p></td>
</tr>
<tr class="even">
<td><p>Test-CsAddressBookWebQuery (ABWQ)</p></td>
<td><p>Confirma que los usuarios pueden buscar usuarios que no estén en su lista de contactos mediante HTTP.</p></td>
<td><p>Valor predeterminado</p></td>
</tr>
<tr class="odd">
<td><p>Test-CsIM (IM)</p></td>
<td><p>Confirma que los usuarios pueden enviar mensajes instantáneos punto a punto.</p></td>
<td><p>Valor predeterminado</p></td>
</tr>
<tr class="even">
<td><p>Test-CsP2PAV (P2PAV)</p></td>
<td><p>Confirma que los usuarios pueden realizar llamadas de audio punto a punto (solo señalización).</p></td>
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
<td><p>Test-CsAudioConferencingProvider (ACP)</p></td>
<td><p>No se usa con la versión local de Lync Server 2013</p></td>
<td><p>Extendido</p></td>
</tr>
<tr class="even">
<td><p>Test-CsPstnPeerToPeerCall (RTC)</p></td>
<td><p>Confirma que los usuarios pueden hacer y recibir llamadas con gente ajena a la empresa (números de RTC).</p></td>
<td><p>No predeterminada, ampliada</p></td>
</tr>
<tr class="odd">
<td><p>Test-CsAVConference (AvConference)</p></td>
<td><p>Confirma que los usuarios pueden crear conferencias de audio/vídeo y participar en ellas.</p></td>
<td><p>Valor predeterminado</p></td>
</tr>
<tr class="even">
<td><p>Test-CsAVEdgeConnectivity (AVEdgeConnectivity)</p></td>
<td><p>Confirma que los servidores perimetrales A/V pueden aceptar conexiones para las llamadas punto a punto y las llamadas de conferencia.</p></td>
<td><p>No predeterminado</p></td>
</tr>
<tr class="odd">
<td><p>Test-CsDataConference (congresos)</p></td>
<td><p>Confirma que los usuarios pueden participar en una conferencia de colaboración de datos, una reunión en línea que engloba actividades como pizarras y sondeos.</p></td>
<td><p>No predeterminado</p></td>
</tr>
<tr class="even">
<td><p>Test-CsExumConnectivity (ExumConnectivity)</p></td>
<td><p>Confirma que un usuario puede conectarse a la mensajería unificada (UM) de Exchange.</p></td>
<td><p>No predeterminado</p></td>
</tr>
<tr class="odd">
<td><p>Test-CsGroupIM (GroupIM)</p></td>
<td><p>Confirma que los usuarios pueden enviar mensajes instantáneos durante las conferencias y participar en conversaciones de mensajes instantáneos con tres o más personas.</p></td>
<td><p>Valor predeterminado</p></td>
</tr>
<tr class="even">
<td><p>Test-CsGroupIM – TestJoinLauncher (JoinLauncher)</p></td>
<td><p>Confirma que los usuarios pueden crear reuniones programadas y unirse a ellas a través de un vínculo de dirección web.</p></td>
<td><p>No predeterminado</p></td>
</tr>
<tr class="odd">
<td><p>Test-CsMCXP2PIM (MCXP2PIM)</p></td>
<td><p>Confirma que los usuarios de dispositivos móviles pueden registrarse y enviar mensajes instantáneos.</p></td>
<td><p>No predeterminado</p></td>
</tr>
<tr class="even">
<td><p>Test-CsPersistentChatMessage (PersistentChatMessage)</p></td>
<td><p>Confirma que los usuarios pueden intercambiar mensajes mediante el servicio de chat persistente.</p></td>
<td><p>No predeterminado</p></td>
</tr>
<tr class="odd">
<td><p>Test-CsUnifiedContactStore (UnifiedContactStore)</p></td>
<td><p>Confirma que se puede acceder a los contactos de un usuario a través del almacén de contactos unificados. El almacén de contactos unificado permite a los usuarios mantener un único conjunto de contactos a los que se puede tener acceso mediante Lync 2013, Outlook o Outlook Web Access.</p></td>
<td><p>No predeterminado</p></td>
</tr>
<tr class="even">
<td><p>Test-CsXmppIM (XmppIM)</p></td>
<td><p>Confirma que se pueden enviar mensajes instantáneos por la puerta de enlace XMPP (protocolo extensible de mensajería y presencia).</p></td>
<td><p>No predeterminado</p></td>
</tr>
</tbody>
</table>


No es necesario instalar los nodos de monitor para poder usar System Center Operations Manager. Si no instala estos nodos, podrá seguir consigo alertas en tiempo real de los componentes de Lync Server 2013 cuando se produzca un problema. (El módulo de administración de componentes y usuarios no usa nodos de monitor). Sin embargo, los nodos de monitor son necesarios si desea supervisar los escenarios de un extremo a otro mediante el módulo de administración de supervisión activa.

<div>


> [!NOTE]  
> Los administradores también pueden ejecutar las transacciones sintéticas manualmente, sin tener que usar o instalar Operations Manager. Para obtener más información sobre los distintos cmdlets test-CS, vea el <A href="https://docs.microsoft.com/powershell/module/skype/?view=skype-ps">Índice de cmdlets de Lync Server 2013</A>.



</div>

Las transacciones sintéticas pueden consumir una gran cantidad de memoria y tiempo de procesador del equipo, según cuál sea la envergadura de su implementación. Por ello, se recomienda tener un equipo dedicado como nodo de monitor. Por ejemplo, no debe configurar un servidor front-end para que actúe como un nodo de monitor. Los nodos de monitor deben cumplir las siguientes especificaciones de hardware:

<div>


> [!NOTE]  
> Un nodo de monitor de Microsoft Lync Server 2010 heredado no se puede combinar en el mismo equipo con un nodo de monitor de Lync Server 2013. Esto se debe a que los archivos del sistema principales para Lync Server 2010 y Lync Server 2013 no se pueden instalar en el mismo equipo.<BR>Sin embargo, los nodos de monitor de 2013 de Lync Server pueden supervisar simultáneamente Lync Server 2013 y Lync Server 2010. Las transacciones sintéticas predeterminadas se admiten en ambas versiones de producto.



</div>

Los nodos de monitor de 2013 de Lync Server se pueden implementar dentro o fuera de una empresa para ayudar a comprobar lo siguiente:

  - <span></span>  
    La conectividad con los grupos de servidores de usuarios de la empresa.

  - <span></span>  
    La conectividad a través de redes perimetrales de los usuarios remotos que trabajan fuera de la empresa.

  - <span></span>  
    La conectividad con aplicaciones de sucursal.

  - <span></span>  
    Conectividad con Lync Server 2010 dentro de la empresa y a través de redes perimetrales.

Existen distintas opciones de autenticación desde dentro y fuera de la empresa que ayudan a simplificar las tareas administrativas. Para obtener más información, consulte [configuración de un nodo de monitor para ejecutar transacciones sintéticas en Lync Server 2013](lync-server-2013-configuring-a-watcher-node-to-run-synthetic-transactions.md).

Para configurar un equipo para que actúe como un nodo de monitor, debe completar los siguientes pasos después de haber instalado System Center Operations Manager e importado los paquetes de administración de Lync Server 2013.

Antes de instalar los archivos principales de Lync Server 2013 y los archivos del agente de System Center, también debe asegurarse de que el equipo del nodo de monitor cumpla todos los requisitos previos para instalar Lync Server 2013. Además, dicho equipo debe tener instalados los siguientes elementos:


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
<li><p>procesador de 64 bits, Quad-Core, 2,33 GHz o superior</p></li>
<li><p>procesador de 2 vías de 64 bits, doble núcleo, 2,33 GHz o superior</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Memoria</p></td>
<td><p>8 GB</p></td>
</tr>
<tr class="odd">
<td><p>Sistema operativo de red</p></td>
<td><ul>
<li><p>1 adaptador de red de 1 Gbps</p></li>
<li><p>Windows Server 2008 R2, Windows Server 2012 o</p>
<p>Windows Server 2012 R2</p></li>
</ul></td>
</tr>
</tbody>
</table>


  - La versión completa de .NET Framework 4.5.

  - Windows Identity Foundation.

  - Windows PowerShell 3.0.

Cuando se cumplan todos estos requisitos previos, podrá configurar el nodo de monitor del siguiente modo:

  - Instalar los archivos principales de Lync Server 2013 en el equipo del nodo de monitor.

  - Instalar el agente de System Center Operations Manager en el equipo del nodo de monitor.

  - Ejecute el archivo ejecutable Watchernode.msi.

  - Use los cmdlets de **CsWatcherNodeConfiguration** para configurar usuarios de prueba para que los utilice el nodo de monitor.

</div>

<span> </span>

</div>

</div>

</div>

