---
title: 'Lync Server 2013: configuración de un nodo de monitor para ejecutar transacciones sintéticas'
description: 'Lync Server 2013: configuración de un nodo de monitor para ejecutar transacciones sintéticas.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring a watcher node to run synthetic transactions
ms:assetid: cedda508-8881-4079-88d5-49798f342ddf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205314(v=OCS.15)
ms:contentKeyID: 48185578
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bd5fdb3d1a1499a6ef79e962a41d9eb3ee174c33
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48567886"
---
# <a name="configuring-a-watcher-node-to-run-synthetic-transactions-in-lync-server-2013"></a>Configuración de un nodo de monitor para ejecutar transacciones sintéticas en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-02-07_

Después de instalar los archivos de agentes de System Center, configure el nodo de monitor. La configuración del nodo de monitor varía en función de si está dentro de la red del perímetro o fuera de dicha red.

Cuando configure un nodo de monitor, elija también el tipo de método de autenticación que el nodo empleará. Lync Server 2013 permite elegir uno de estos dos métodos de autenticación: autenticación de servidor de confianza o de credenciales. Las diferencias entre estos dos métodos se indican en la tabla siguiente:


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Configuración</th>
<th>Descripción</th>
<th>Ubicaciones admitidas</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Servidor de confianza</p></td>
<td><p>Usa un certificado para representar a un servidor interno y evitar los problemas de autenticación.</p>
<p>Es útil para los administradores que prefieran administrar un solo certificado en vez de varias contraseñas de usuario en cada nodo de monitor.</p></td>
<td><p>Dentro de la empresa.</p>
<p>Con este método, el nodo de monitor debe estar en el mismo dominio que los grupos de servidores que se están supervisando. Si están en dominios diferentes, use la autenticación de credenciales.</p></td>
</tr>
<tr class="even">
<td><p>Autenticación de credenciales</p></td>
<td><p>Almacena los nombres de usuario y las contraseñas con seguridad en Windows Credential Manager en cada nodo de monitor.</p>
<p>Este modo necesita más administración de contraseñas, pero es la única opción para los nodos de monitor ubicados fuera de la empresa. Estos nodos de monitor no se pueden tratar como un extremo de confianza para la autenticación.</p></td>
<td><p>Fuera de la empresa.</p>
<p>Dentro de la empresa.</p></td>
</tr>
</tbody>
</table>


También debe comprobar que el firewall tiene reglas de entrada para MonitoringHost.exe y PowerShell.exe. Si el Firewall bloquea estos procesos, se producirá un error de 504 (tiempo de espera de servidor) en las transacciones sintéticas.

</div>

<span> </span>

</div>

</div>

</div>

