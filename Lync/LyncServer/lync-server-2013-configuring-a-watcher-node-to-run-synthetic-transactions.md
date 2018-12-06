---
title: "Conf. d’un nœud obs. pour l’exécution des transactions synthétiques"
TOCTitle: "Conf. d’un nœud obs. pour l’exécution des transactions synthétiques"
ms:assetid: cedda508-8881-4079-88d5-49798f342ddf
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ205314(v=OCS.15)
ms:contentKeyID: 48276724
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuración de un nodo de monitor para ejecutar transacciones sintéticas

 

_**Última modificación del tema:** 2015-03-09_

Después de instalar los archivos de agentes de System Center, configure el nodo de monitor. La configuración del nodo de monitor varía en función de si está dentro de la red del perímetro o fuera de dicha red.

Cuando configure un nodo de monitor, elija también el tipo de método de autenticación que el nodo empleará. Lync Server 2013 le permite elegir uno de los dos métodos de autenticación: servidor de confianza o autenticación de credenciales. Las diferencias entre estos dos métodos se indican en la tabla siguiente:


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


Debe comprobar también que su firewall cuenta con reglas de acceso de entrada para MonitoringHost.exe y para PowerShell.exe. Si el firewall bloquea estos procesos, las transacciones sintéticas presentarán el error 504 (tiempo de espera en el servidor sobrepasado).

