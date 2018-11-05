---
title: 'Lync Server 2013: Definir una dirección IP de puerta de enlace SIP/CSTA'
TOCTitle: Definir una dirección IP de puerta de enlace SIP/CSTA
ms:assetid: ae944057-3ad6-4474-a09b-81a3d27bd50f
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg602125(v=OCS.15)
ms:contentKeyID: 48276357
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Definir una dirección IP de puerta de enlace SIP/CSTA en Lync Server 2013

 

_**Última modificación del tema:** 2012-09-21_

Si el Lync Server se conecta a la puerta de enlace SIP/CSTA que ha implementado para el control remoto de llamadas mediante una conexión de protocolo de control de transmisión (TCP), debe definir la dirección IP de las puerta de enlace en Generador de topologías. Este paso no es necesario para puertas de enlace compatibles con conexiones de Seguridad de la capa de transporte (TLS). Puede omitir este procedimiento y continuar la implementación de control remoto de llamadas siguiendo los pasos en [Habilitar a los usuarios de Lync para el control remoto de llamadas en Lync Server 2013](lync-server-2013-enable-lync-users-for-remote-call-control.md).

## Para definir la dirección IP de la puerta de enlace SIP/CSTA con el Generador de topologías

1.  Inicie sesión en el equipo donde se encuentre instalado el Generador de topologías como miembro del grupo Administradores del dominio y el grupo RTCUniversalServerAdmins.

2.  Inicie el Generador de topologías: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y, después, en **Generador de topologías de Lync Server**.

3.  Elija la opción para descargar una topología existente.

4.  Expanda el nodo **Servidores de aplicaciones de confianza** .

5.  Haga clic con el botón secundario en el grupo de aplicaciones de confianza que ha creado de acuerdo con el procedimiento descrito en [Configurar una entrada de aplicación de confianza para control remoto de llamadas en Lync Server 2013](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md) y haga clic en **Editar propiedades** .

6.  Desactive la casilla **Habilitar replicación de datos de configuración en este grupo de servidores** .

7.  Haga clic en **Limitar el uso del servicio a las direcciones IP seleccionadas** . La configuración predeterminada es **Usar todas las direcciones IP configuradas** .

8.  En el cuadro de texto **Dirección IP principal** , escriba la dirección IP de la puerta de enlace SIP/CSTA.

9.  Para actualizar la topología en el almacén de administración central, en el árbol de la consola, haga clic en **Lync Server** y, desde el panel **Acciones** , haga clic en **Publicar** .

## Vea también

#### Tareas

[Configurar una ruta estática para el control remoto de llamadas en Lync Server 2013](lync-server-2013-configure-a-static-route-for-remote-call-control.md)  
[Configurar una entrada de aplicación de confianza para control remoto de llamadas en Lync Server 2013](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md)

