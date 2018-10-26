---
title: Ver una lista de aplicaciones de confianza
TOCTitle: Ver una lista de aplicaciones de confianza
ms:assetid: f09300b3-67cf-4e70-a51a-23d62479b913
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg182604(v=OCS.15)
ms:contentKeyID: 48277117
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Ver una lista de aplicaciones de confianza

 

_**Última modificación del tema:** 2012-09-21_

Puede usar Panel de control de Lync Server 2013 para ver una lista de las aplicaciones de confianza que ha implementado en su entorno de Lync Server 2013. Una aplicación de confianza es una aplicación basada en el SDK central de la API administrada de comunicaciones unificadas de Microsoft (UCMA) 3.0 en la que confía Lync Server 2013. Esta relación de confianza se resume en la siguiente lista:

  - Las aplicaciones de confianza no reciben un desafío de Lync Server para autenticarse.

  - Lync Server no limita a las aplicaciones de confianza para las transacciones SIP, las conexiones ni las llamadas salientes de Voz sobre protocolo de Internet (VoIP).

  - Las aplicaciones de confianza pueden imitar a cualquier usuario y pueden participar en conferencias sin aparecer en las listas.

  - Las aplicaciones de confianza tienen gran disponibilidad y resistencia.

En Panel de control de Lync Server, puede ver el nombre de las aplicaciones, el grupo de servidores en el que se ejecutan y el puerto que usan.

## Para ver una lista de las aplicaciones de confianza

1.  Desde una cuenta de usuario que esté asignada al rol CsServerAdministrator, CsAdministrator, CsHelpDesk o CsViewOnlyAdministrator, inicie sesión en cualquier equipo en la implementación interna. Para más información sobre los roles administrativos predefinidos disponibles en Lync Server 2013, consulte [Planeación del control de acceso basado en roles en Lync Server 2013](lync-server-2013-planning-for-role-based-access-control.md).

2.  Abra una ventana del explorador y después introduzca la dirección URL de administración para abrir el panel de control de Lync Server. Para más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Abrir las herramientas administrativas de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Topología** y, a continuación, en **Aplicación de confianza**.

4.  En la página **Aplicación de confianza**, haga clic en el encabezado de una columna para ordenar las aplicaciones si es necesario.

## Vea también

#### Otros recursos

[Administración de la topología de Lync Server 2013](lync-server-2013-managing-the-lync-server-topology.md)

