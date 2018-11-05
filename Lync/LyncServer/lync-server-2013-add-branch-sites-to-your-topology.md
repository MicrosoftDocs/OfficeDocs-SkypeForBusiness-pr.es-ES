---
title: 'Lync Server 2013: Agregar sitios de sucursal a la topología'
TOCTitle: Agregar sitios de sucursal a la topología
ms:assetid: b9c35fb0-0081-4aeb-8f95-ac2fcc6c3335
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg412905(v=OCS.15)
ms:contentKeyID: 48276479
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Agregar sitios de sucursal a la topología en Lync Server 2013

 

_**Última modificación del tema:** 2012-10-05_

Los sitios de sucursal representan las sucursales físicas que están conectadas a las oficinas principales con un vínculo WAN. Para agregar un sitio de sucursal a la topología de Lync, haga lo siguiente en el sitio central.

## Para agregar sitios de sucursal a la topología:

1.  Haga clic sucesivamente en **Inicio** , **Todos los programas** , **Microsoft Lync Server** y **Generador de topologías de Lync Server** .

2.  En el árbol de consola, expanda el sitio central, haga clic con el botón secundario en **Sitios de sucursal** y haga clic en **Nuevo sitio de sucursal** .

3.  En el cuadro de diálogo **Definir nuevo sitio de sucursal**, haga clic en **Nombre** y escriba el nombre del sitio de sucursal.

4.  (Opcional) Haga clic en **Descripción** y luego escriba una descripción significativa para el sitio de sucursal.

5.  Después, haga clic en **Siguiente** .

6.  (Opcional) En el siguiente cuadro de diálogo **Definir nuevo sitio de sucursal** , realice una de las siguientes acciones:
    
      - Haga clic en **Ciudad** y escriba el nombre de la ciudad en la se ubica el sitio de sucursal.
    
      - Haga clic en **Provincia o región** y escriba el nombre de la provincia o la región en la que se ubica el sitio de sucursal.
    
      - Haga clic en **Código de país** y luego escriba el código telefónico de dos dígitos del país o la región en el que se ubica el sitio de sucursal.

7.  Haga clic en **Siguiente** y luego siga uno de estos procedimientos:
    
      - Si usa Aplicación de sucursal con funciones de supervivencia o un servidor en este sitio, compruebe que la casilla **Abrir el Asistente con nuevas funciones de supervivencia cuando se cierre este asistente** esté activada, haga clic en **Finalizar** y siga las indicaciones del asistente que aparece. Para más información con relación a los asistentes, consulte [Definir un servidor o aplicación de sucursal con funciones de supervivencia en Lync Server 2013](lync-server-2013-define-a-survivable-branch-appliance-or-server.md).
    
      - Si no usa Aplicación de sucursal con funciones de supervivencia ni un servidor en este sitio, desactive la casilla **Abrir el Asistente con nuevas funciones de supervivencia cuando se cierre este asistente** y haga clic en **Finalizar** .

8.  Repita los pasos anteriores para cada sitio de sucursal que desee agregar a la topología.

**Siguiente paso:**

Para servidores o aplicaciones de sucursal con funciones de supervivencia: [Definir un servidor o aplicación de sucursal con funciones de supervivencia en Lync Server 2013](lync-server-2013-define-a-survivable-branch-appliance-or-server.md)

Para conectividad con RTC no resistente: [Definir una puerta de enlace RTC para un sitio de sucursal en Lync Server 2013](lync-server-2013-define-a-pstn-gateway-for-a-branch-site.md), [Configurar un tronco con omisión de medios en Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md) o [Configurar un tronco sin omisión de medios en Lync Server 2013](lync-server-2013-configure-a-trunk-without-media-bypass.md).

