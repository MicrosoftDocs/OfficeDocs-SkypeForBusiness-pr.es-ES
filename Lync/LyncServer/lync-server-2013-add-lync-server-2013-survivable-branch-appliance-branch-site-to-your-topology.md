---
title: "Agregar sucursal de aplic. sucursal con supervivencia de Lync Server 2013 a topología"
TOCTitle: Agregar un sitio de sucursal de aplicación de sucursal con función de supervivencia de Lync Server 2013 a la topología
ms:assetid: d3142a37-4606-456d-8ea9-6cc0e51e55f3
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ721896(v=OCS.15)
ms:contentKeyID: 49889747
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Agregar un sitio de sucursal de aplicación de sucursal con función de supervivencia de Lync Server 2013 a la topología

 

_**Última modificación del tema:** 2012-10-07_

Las Aplicaciones de sucursal con funciones de supervivencia (SBA) de Microsoft Lync Server 2013 no se pueden asociar a un Grupo de servidores front-end de Microsoft Lync Server 2010 como registrador de copia de seguridad. Asocie la SBA a un Grupo de servidores front-end de Microsoft Lync Server 2013. Estos pasos presuponen la existencia de una SBA de Microsoft Lync Server 2013. Ejecute este procedimiento en el sitio central.

## Para agregar sucursales con SBA de Microsoft Lync Server 2013 a la topología

1.  Inicie el Generador de topologías: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y, después, en **Generador de topologías de Lync Server**.

2.  En el árbol de consola, expanda sucesivamente el sitio central y los **Sitios de sucursal** y luego haga clic en **Nuevo sitio de sucursal**.

3.  En el cuadro de diálogo **Definir nuevo sitio de sucursal**, haga clic en **Nombre** y escriba un nombre para el sitio de sucursal nuevo.

4.  (Opcional) Haga clic en **Descripción** y luego escriba una descripción significativa para el sitio de sucursal.

5.  Después, haga clic en **Siguiente** .

6.  (Opcional) En el siguiente cuadro de diálogo **Definir nuevo sitio de sucursal**, realice una de las siguientes acciones:
    
      - Haga clic en **Ciudad** y escriba el nombre de la ciudad en la se ubica el sitio de sucursal.
    
      - Haga clic en **Provincia o región** y escriba el nombre de la provincia o la región en la que se ubica el sitio de sucursal.
    
      - Haga clic en **Código de país** y luego escriba el código telefónico de dos dígitos del país o la región en el que se ubica el sitio de sucursal.

7.  Haga clic en **Siguiente** y luego siga uno de estos procedimientos:
    
      - Si usa una Aplicación de sucursal con funciones de supervivencia o un Servidor de sucursal con funciones de supervivencia en este sitio, compruebe que la casilla **Abrir el Asistente con nuevas funciones de supervivencia cuando se cierre este asistente** esté activada.
    
      - Si usa una Aplicación de sucursal con funciones de supervivencia o un Servidor de sucursal con funciones de supervivencia en este sitio, desactive la casilla **Abrir el Asistente con nuevas funciones de supervivencia cuando se cierre este asistente**.
    
      - Haga clic en **Finalizar** y siga las instrucciones del asistente que se abre. Para más información sobre el asistente, vea [Definir un servidor o aplicación de sucursal con funciones de supervivencia en Lync Server 2013](lync-server-2013-define-a-survivable-branch-appliance-or-server.md).

8.  Repita los pasos anteriores para cada sitio de sucursal que desee agregar a la topología.

## Vea también

#### Tareas

[Definir un servidor o aplicación de sucursal con funciones de supervivencia en Lync Server 2013](lync-server-2013-define-a-survivable-branch-appliance-or-server.md)  
[Definir una puerta de enlace RTC para un sitio de sucursal en Lync Server 2013](lync-server-2013-define-a-pstn-gateway-for-a-branch-site.md)  
[Configurar un tronco con omisión de medios en Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md)  
[Configurar un tronco sin omisión de medios en Lync Server 2013](lync-server-2013-configure-a-trunk-without-media-bypass.md)

