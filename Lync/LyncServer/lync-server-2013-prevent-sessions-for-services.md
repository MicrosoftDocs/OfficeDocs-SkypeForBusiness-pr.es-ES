---
title: Impedir sesiones para servicios en Lync Server 2013
TOCTitle: Impedir sesiones para servicios en Lync Server 2013
ms:assetid: 977dcc5c-2aac-48ef-86a1-a8d47b4d9e74
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg182553(v=OCS.15)
ms:contentKeyID: 48276093
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Impedir sesiones para servicios en Lync Server 2013

 

_**Última modificación del tema:** 2012-11-01_

Puede usar Panel de control de Lync Server para impedir que se creen nuevas sesiones en todos los servicios de Lync Server 2013 que se ejecutan en un equipo específico o para impedir que se creen sesiones nuevas en un servicio de Lync Server 2013 específico.

## Para impedir que se creen sesiones nuevas en todos los servicios de Lync Server en un equipo

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes), o se asigne al rol CsServerAdministrator o CsAdministrator, inicie sesión en cualquier equipo que esté en la red en la que haya implementado Lync Server 2013.

2.  Abra una ventana del explorador y después introduzca la dirección URL de administración para abrir el panel de control de Lync Server. Para más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Abrir las herramientas administrativas de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Topología** y, a continuación, en **Estado**.

4.  En la página **Estado**, clasifique o busque en la lista, según sea necesario, para localizar el equipo que está ejecutando los servicios para los que desea impedir que se creen sesiones nuevas y, a continuación, haga clic en él.

5.  Haga clic en **Acción**.

6.  Haga clic en **Evitar sesiones nuevas en todos los servicios**.

## Para impedir que se creen sesiones nuevas para un servicio específico

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes), o se asigne al rol CsServerAdministrator o CsAdministrator, inicie sesión en cualquier equipo que esté en la red en la que haya implementado Lync Server 2013.

2.  Abra una ventana del explorador y después introduzca la dirección URL de administración para abrir el panel de control de Lync Server. Para más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Abrir las herramientas administrativas de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Topología** y, a continuación, en **Estado**.

4.  En la página **Estado**, clasifique o busque en la lista, según sea necesario, para localizar el equipo que está ejecutando el servicio que desea iniciar o detener y, a continuación, haga clic en él.

5.  Haga clic en **Propiedades**.

6.  Clasifique la lista de servicios, si fuera necesario y, a continuación, haga clic en el servicio para el que desea impedir que se creen sesiones nuevas.

7.  Haga clic en **Acción**.

8.  Haga clic en **Evitar sesiones nuevas en el servicio**.

9.  Haga clic en **Cerrar**.

## Vea también

#### Otros recursos

[Administración de la topología de Lync Server 2013](lync-server-2013-managing-the-lync-server-topology.md)

