---
title: Habilitación del desvío de medios de red
TOCTitle: Habilitación del desvío de medios de red
ms:assetid: 95c4fa06-49d3-41ac-acdc-7dcda66e5508
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg182552(v=OCS.15)
ms:contentKeyID: 48276071
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Habilitación del desvío de medios de red

 

_**Última modificación del tema:** 2012-11-01_

La configuración del desvío de medios se aplica globalmente en toda la implementación de Microsoft Lync Server 2013. Con el desvío de medios, las llamadas pueden omitir el servidor de mediación. Para obtener información detallada sobre cuándo usar el desvío de medios, consulte[Planificar la omisión de medios en Lync Server 2013](lync-server-2013-planning-for-media-bypass.md) en la sección referente a la planeación.

Puede habilitar y configurar el desvío de medios desde Panel de control de Lync Server.

## Para habilitar y configurar el desvío de medios

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y después introduzca la dirección URL de administración para abrir el panel de control de Lync Server. Para más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Abrir las herramientas administrativas de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Configuración de red** y, a continuación, en **Global**.

4.  En la página **Global**, haga clic en la configuración **Global**. En todos los casos hay solo una configuración y siempre se llama Global.

5.  En el menú **Editar**, haga clic en **Ver detalles**.

6.  En la página **Editar configuración global**, haga clic en la casilla **Habilitar desvío de medios**.

7.  Seleccione una de las siguientes opciones:
    
      - **Omitir siempre**   Seleccione esta opción para que se intente el desvío de medios en todas las llamadas. Esta opción no estará disponible si se ha habilitado el control de admisión de llamadas (CAC). Si el CAC no está habilitado, seleccione esta opción en las situaciones siguientes:
        
          - No es necesario controlar el ancho de banda.
        
          - No se necesita una configuración específica para saber cuándo debe producirse el desvío.
        
          - Existe plena conectividad entre las puertas de enlace y los clientes.
    
      - **Usar la configuración de sitios y regiones**   Si se habilita el CAC, esta opción se selecciona de forma predeterminada y no se puede modificar. Cuando se selecciona esta opción, los sitios y regiones de configuración de red se usarán para determinar cuando resulta posible el desvío de medios. Si selecciona esta opción, puede optar por habilitar el desvío para sitios que no se han asignado. Haga clic en la casilla **Habilitar desvío para sitios sin asignar** solamente si dispone de uno o más sitios grandes asociados con la misma región que no tenga restricciones de ancho de banda (por ejemplo, un sitio central grande) y si dispone también de algunos sitios de sucursal asociados con la misma región que no tienen restricciones de ancho de banda. Cuando habilita el desvío para sitios sin asignar, la configuración se simplifica porque solo especifica subredes asociadas con los sitios de sucursal en lugar de tener que especificar todas las subredes asociadas a todos los sitios. Se recomienda no seleccionar la casilla **Habilitar desvío para sitios sin asignar** si se ha habilitado el CAC.

8.  Haga clic en **Confirmar** para guardar los cambios.

## Vea también

#### Tareas

[Deshabilitación de la omisión de medios de red](lync-server-2013-disabling-network-media-bypass.md)  

#### Conceptos

[Opciones globales de desvío de medios en Lync Server 2013](lync-server-2013-global-media-bypass-options.md)  

#### Otros recursos

[Planificar la omisión de medios en Lync Server 2013](lync-server-2013-planning-for-media-bypass.md)

