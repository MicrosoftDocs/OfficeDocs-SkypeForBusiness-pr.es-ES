---
title: "Configurar el desvío de medios en Lync Server 2013 para omitir servidor de mediación"
TOCTitle: "Conf. le contourn. de média ds LS 2013 pr tjs contourner le serv. de médiation"
ms:assetid: 370c4f54-e520-4d77-96a3-84c5e84a9996
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg425846(v=OCS.15)
ms:contentKeyID: 48274914
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configurar el desvío de medios en Lync Server 2013 para omitir siempre el servidor de mediación

 

_**Última modificación del tema:** 2013-02-25_


> [!NOTE]
> En este tema se presupone que ya ha configurado el desvío de medios para las conexiones de enlace troncal con un par (una puerta de enlace de red telefónica conmutada [RTC], un sistema PBX IP o un controlador de borde de sesión [SBC] en un proveedor de servicios de telefonía por Internet [ITSP]) para un sitio o servicio específico en el que desea que los medios omitan el servidor de mediación.<BR>No puede configurar los medios para que omitan siempre el servidor de mediación al tiempo que también habilita el control de admisión de llamadas. Estas configuraciones son incompatibles y, por lo tanto, se excluyen mutuamente en la interfaz de usuario de Panel de control de Lync Server.



Además de habilitar el desvío de medios para conexiones de enlace troncal individuales asociadas a un par en el servidor de mediación, debe configurar también opciones globales para el desvío de medios. Si sigue los pasos indicados en este tema para configurar las opciones globales del desvío de medios, se presupone que cuenta con una buena conectividad entre los extremos de Lync y cualquier par para el que haya configurado el desvío de medios en la conexión de enlace troncal.

Si no dispone de buena conectividad entre los extremos de Lync Server y todos los pares con el servidor de mediación cuyas conexiones de enlace troncal se han habilitado para el desvío de medios, debe configurar las opciones globales de desvío de medios para que usen la información del sitio y la región cuando se emplee el desvío de medios. Con esto se permite un control más preciso para determinar cuándo los medios omiten el servidor de mediación. Para ello, siga en su lugar los pasos indicados en [Configurar las opciones globales del desvío de medios en Lync Server 2013 para usar la información de sitio y región](lync-server-2013-configure-media-bypass-global-settings-to-use-site-and-region-information.md) y [Asociar una subred a un sitio de red en Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md).

## Para habilitar globalmente el desvío de medios para que omita siempre el servidor de mediación

1.  Abra una ventana del explorador y después introduzca la dirección URL de administración para abrir el panel de control de Lync Server. Para más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Abrir las herramientas administrativas de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

2.  En la barra de navegación izquierda, haga clic en **Configuración de red**.

3.  Haga doble clic en la configuración **Global** de la lista.

4.  En la página **Editar configuración global**, seleccione la casilla **Habilitar desvío de medios**.

5.  Haga clic en **Desviar siempre**.

6.  Haga clic en **Confirmar**.

## Vea también

#### Conceptos

[Configurar la omisión de medios en Lync Server 2013](lync-server-2013-configure-media-bypass.md)  
[Opciones globales de desvío de medios en Lync Server 2013](lync-server-2013-global-media-bypass-options.md)  
[Omisión de medios y servidor de mediación en Lync Server 2013](lync-server-2013-media-bypass-and-mediation-server.md)  

#### Otros recursos

[Planificar la omisión de medios en Lync Server 2013](lync-server-2013-planning-for-media-bypass.md)

