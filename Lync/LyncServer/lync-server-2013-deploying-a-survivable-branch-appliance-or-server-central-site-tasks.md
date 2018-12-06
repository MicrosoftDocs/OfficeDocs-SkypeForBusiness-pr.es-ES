---
title: "Lync Server 2013: Aplicación o servidor de sucursal con supervivencia, sitio central"
TOCTitle: Implementación de una aplicación o un servidor de sucursal con funciones de supervivencia - Tareas de sitio central
ms:assetid: 0f631a36-fc2e-41cd-8a0d-f27e84f4a89e
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398189(v=OCS.15)
ms:contentKeyID: 48274448
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Implementación de una aplicación o un servidor de sucursal con funciones de supervivencia - Tareas de sitio central con Lync Server 2013

 

_**Última modificación del tema:** 2012-10-18_

Complete las tareas de esta sección en el sitio central. Si está implementando un Servidor de sucursal con funciones de supervivencia, omita la primera tarea.

> [!IMPORTANT]  
> Antes de realizar las tareas de esta sección, deberán cumplirse las siguientes condiciones:
> <ul>
> <li><p>Lync Server debe estar configurado en el sitio central.</p></li>
> <li><p>Debe agregarse un técnico de instalación de la sucursal al grupo RTCUniversalSBATechnicians.</p></li>
> </ul>
> Además, se recomienda que haga lo siguiente:
> <ul>
> <li><p>Implementar un servidor DHCP en cada una de las sucursales para permitir que los clientes obtengan direcciones IP.</p></li>
> <li><p>Como alternativa a la implementación de un servidor DHCP en cada una de las sucursales, habilite DHCP de Lync Server en Aplicación de sucursal con funciones de supervivencia o Servidor de sucursal con funciones de supervivencia usando el cmdlet Shell de administración de Lync Server<strong>Set-CsRegistrarConfiguration –EnableDHCPServer $true</strong>. Para obtener más información, consulte la sección &quot;Requisitos de hardware y software&quot; de <a href="lync-server-2013-branch-site-resiliency-requirements.md">Requisitos de resistencia de sitios de sucursal para Lync Server 2013</a> en la documentación de planeación.</p></li>
> </ul>


## En esta sección

  - [Agregar una aplicación de sucursal con funciones de supervivencia a Active Directory en Lync Server 2013](lync-server-2013-add-a-survivable-branch-appliance-to-active-directory.md)

  - [Agregar sitios de sucursal a la topología en Lync Server 2013](lync-server-2013-add-branch-sites-to-your-topology.md)

  - [Definir un servidor o aplicación de sucursal con funciones de supervivencia en Lync Server 2013](lync-server-2013-define-a-survivable-branch-appliance-or-server.md)

