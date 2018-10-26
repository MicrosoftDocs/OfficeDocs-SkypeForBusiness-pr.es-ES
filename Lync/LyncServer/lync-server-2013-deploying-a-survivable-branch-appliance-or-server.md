---
title: "Lync Server 2013: Implementar aplicación o servidor de sucursal con supervivencia"
TOCTitle: Implementar una aplicación o servidor de sucursal con funciones de supervivencia
ms:assetid: cb780c14-dc5f-41ba-8092-f20ae905bd16
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398849(v=OCS.15)
ms:contentKeyID: 48276696
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Implementar una aplicación o servidor de sucursal con funciones de supervivencia con Lync Server 2013

 

_**Última modificación del tema:** 2014-12-10_

La resistencia de Telefonía IP empresarial hace referencia a la resistencia de sitios de sucursal, es decir, la capacidad de proporcionar un servicio continuo de Telefonía IP empresarial a los usuarios de sitios de sucursal en el caso de que el vínculo al sitio central deje de estar disponible.

Para sitios de sucursal pequeños y medianos (sitios de sucursal de entre 25 y 1.000 usuarios), se recomienda implementar una Aplicación de sucursal con funciones de supervivencia, que finalizará las llamadas de RTC (Red telefónica conmutada) mediante su puerta de enlace RTC integrada o un tronco SIP a un proveedor de servicios de telefonía. Una Aplicación de sucursal con funciones de supervivencia es un dispositivo de otro fabricante que incluye un servidor modular que ejecuta el Sistema operativo Windows Server 2008 R2, el registrador de Lync Server 2013, el software de Servidor de mediación y una puerta de enlace RTC, todo en un único chasis de aplicación.

Para sitios de sucursal de entre 1.000 y 5.000 usuarios y WAN no resistente, se recomienda un Servidor de sucursal con funciones de supervivencia conectado a una puerta de enlace RTC o un tronco SIP a un proveedor de servicios de telefonía. Un Servidor de sucursal con funciones de supervivencia es un equipo basado en Windows Server que tiene el registrador y el software de Servidor de mediación instalado.


> [!NOTE]
> Para sitios de sucursal con más de 5.000 usuarios y administradores de Lync Server dedicados, se recomienda una implementación de Lync Server 2013 completa, independiente de la del sitio central.<BR>Para obtener información detallada sobre cómo elegir la mejor solución de resistencia de sitios de sucursal en su organización y para obtener información sobre los requisitos previos y las consideraciones de planeación, vea <A href="lync-server-2013-branch-site-resiliency-requirements.md">Requisitos de resistencia de sitios de sucursal para Lync Server 2013</A> en la documentación referente a la planeación.



## En esta sección

  - [Implementación de una aplicación o un servidor de sucursal con funciones de supervivencia - Tareas de sitio central con Lync Server 2013](lync-server-2013-deploying-a-survivable-branch-appliance-or-server-central-site-tasks.md)

  - [Implementar una aplicación o servidor de sucursal con funciones de supervivencia con Lync Server 2013 - Tarea en el sitio de sucursal](lync-server-2013-deploy-a-survivable-branch-appliance-or-server-branch-site-task.md)

  - [Configuración de usuarios para la resistencia del sitio de sucursal en Lync Server 2013](lync-server-2013-configuring-users-for-branch-site-resiliency.md)

  - [Usuarios particulares en una aplicación o un servidor de sucursal con funciones de supervivencia en Lync Server 2013](lync-server-2013-home-users-on-a-survivable-branch-appliance-or-server.md)

  - [Apéndices: Servidores y aplicaciones de sucursal con funciones de supervivencia en Lync Server 2013](lync-server-2013-appendices-survivable-branch-appliances-and-servers.md)

## Vea también

#### Otros recursos

[Implementar Lync Server 2013](lync-server-2013-deploying-lync-server.md)

