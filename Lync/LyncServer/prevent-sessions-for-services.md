---
title: Impedir sesiones para servicios
TOCTitle: Impedir sesiones para servicios
ms:assetid: 4b541c72-cdc1-4f86-a5a8-c43c24f41d8b
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ688049(v=OCS.15)
ms:contentKeyID: 49889077
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Impedir sesiones para servicios

 

_**Última modificación del tema:** 2012-10-04_

Puede usar Panel de control de Microsoft Lync Server 2010 para impedir que se creen nuevas sesiones en todos los servicios de Lync Server 2010 que se ejecutan en un equipo específico o para impedir que se creen sesiones nuevas en un servicio de Lync Server 2010 específico.

## Para impedir que se creen sesiones nuevas en todos los servicios de Lync Server en un equipo

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes), o se asigne al rol CsServerAdministrator o CsAdministrator, inicie sesión en cualquier equipo que esté en la red en la que haya implementado Lync Server 2013.

2.  Abra Panel de control de Lync Server.

3.  En la barra de navegación izquierda, haga clic en **Topología** y, a continuación, en **Estado**.

4.  En la página **Estado**, clasifique o busque en la lista, según sea necesario, para localizar el equipo que está ejecutando los servicios para los que desea impedir que se creen sesiones nuevas y, a continuación, haga clic en él.

5.  Haga clic en **Acción**.

6.  Haga clic en **Evitar sesiones nuevas en todos los servicios**.

## Para impedir que se creen sesiones nuevas para un servicio específico

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes), o se asigne al rol CsServerAdministrator o CsAdministrator, inicie sesión en cualquier equipo que esté en la red en la que haya implementado Lync Server 2013.

2.  Abra Panel de control de Lync Server.

3.  En la barra de navegación izquierda, haga clic en **Topología** y, a continuación, en **Estado**.

4.  En la página **Estado**, ordene la lista o realice una búsqueda para encontrar el equipo que ejecuta el servicio que desea iniciar o detener, y haga clic en él.

5.  Haga clic en **Propiedades**.

6.  Clasifique la lista de servicios, si fuera necesario y, a continuación, haga clic en el servicio para el que desea impedir que se creen sesiones nuevas.

7.  Haga clic en **Acción**.

8.  Haga clic en **Evitar sesiones nuevas en el servicio**.

9.  Haga clic en **Cerrar**.

