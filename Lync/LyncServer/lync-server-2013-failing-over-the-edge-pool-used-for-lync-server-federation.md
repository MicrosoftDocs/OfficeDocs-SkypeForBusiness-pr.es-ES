---
title: "Lync Server 2013: Conmut. por error del grupo perimetral usado para Lync Server"
TOCTitle: Conmutación por error para el grupo de servidores perimetrales usado para la federación Lync Server
ms:assetid: 5c9da0f2-7429-40bb-bb3c-5cc4ecb5a13d
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ688071(v=OCS.15)
ms:contentKeyID: 49889203
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Conmutación por error para el grupo de servidores perimetrales usado para la federación Lync Server en Lync Server 2013

 

_**Última modificación del tema:** 2012-09-17_

Si el grupo de servidores perimetrales en el que se ha configurado la federación de Lync Server deja de funcionar, deberá cambiar la federación para que use un grupo de servidores perimetrales diferente y así pueda funcionar correctamente.

## Conmutación por error para el grupo de servidores perimetrales usado para la federación Lync Server

1.  En un servidor front-end, abra el Generador de topologías. Expanda **Grupos de servidores perimetrales** y después haga clic con el botón secundario en el servidor perimetral o en el grupo de servidores perimetrales que está configurado actualmente para la federación. Seleccione **Editar propiedades** .

2.  En **Editar propiedades**, en la pestaña **General**, desactive **Habilitar la federación para este grupo de servidores perimetrales (puerto 5061)**. Haga clic en **Aceptar**.

3.  Expanda **Grupos de servidores perimetrales** y haga clic con el botón secundario en el servidor perimetral o el grupo de servidores perimetrales que quiera usar ahora para la federación. Seleccione **Editar propiedades** .

4.  En **Editar propiedades**, en **General**, seleccione **Habilitar la federación para este grupo de servidores perimetrales (puerto 5061)**. Haga clic en **Aceptar**.

5.  Haga clic en **Acción** , y seleccione sucesivamente **Topología** y **Publicar** . Cuando el sistema se lo solicite, en **Publicar la topología** , haga clic en **Siguiente** . Cuando haya acabado la publicación, haga clic en **Finalizar** .

6.  En el servidor perimetral, abra el asistente para la implementación de Lync Server. Haga clic en **Instalar o actualizar el sistema Lync Server** y después haga clic en **Instalar o eliminar componentes de Lync Server** . Haga clic en **Ejecutar de nuevo** .

7.  En Instalar componentes de Lync Server, haga clic en **Siguiente** . En la pantalla de resumen aparecerán las acciones tal como se ejecutan. Cuando haya acabado la implementación, haga clic en **Ver registro** para ver los archivos de registro disponibles. Haga clic en **Finalizar** para completar la implementación.
    
    Si el sitio del grupo de servidores perimetrales con el error contiene también servidores front-end que todavía funcionan, deberá actualizar los servicios de conferencia web y conferencia A/V de estos grupos de servidores front-end para que usen un grupo de servidores perimetrales que funcione en un sitio remoto. Consulte [Cambio del grupo de servidores perimetrales asociado al grupo de servidores front-end Lync Server 2013](lync-server-2013-changing-the-edge-pool-associated-with-a-front-end-pool.md) para obtener más información.

## Vea también

#### Tareas

[Conmutación por error para el grupo de servidores perimetrales para la federación XMPP en Lync Server 2013](lync-server-2013-failing-over-the-edge-pool-used-for-xmpp-federation.md)  
[Conmutación por recuperación para el grupo de servidores perimetrales que se usa para la federación Lync Server o la federación XMPP en Lync Server 2013](lync-server-2013-failing-back-the-edge-pool-used-for-lync-server-federation-or-xmpp-federation.md)  

#### Conceptos

[Recuperación ante desastres del servidor perimetral en Lync Server 2013](lync-server-2013-edge-server-disaster-recovery.md)

