---
title: "Blocage des nlles connexions à Lync Server lors de la maintenance du serveur "
TOCTitle: "Blocage des nlles connexions à Lync Server lors de la maintenance du serveur "
ms:assetid: 22b27adf-a590-43bd-9306-a5789ae108d7
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg520964(v=OCS.15)
ms:contentKeyID: 48274674
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Impedir nuevas conexiones a Lync Server para el mantenimiento de servidores

 

_**Última modificación del tema:** 2012-11-01_

Lync Server le permite desconectar un servidor (por ejemplo, para agregar software o hacer actualizaciones de hardware) sin ninguna pérdida de servicio para los usuarios.

Si especifica la opción para prevenir nuevas conexiones o llamadas al servidor en un grupo de servidores, dicho grupo deja de atender nuevas conexiones o llamadas en el momento en que se implementa la opción. Dichas nuevas conexiones y llamadas se redirigen a los otros servidores del grupo. Un servidor que no permite las nuevas conexiones permite que continúen las sesiones de conexiones existentes hasta su final natural. Cuando terminan todas las sesiones iniciadas, el servidor está listo para ser desconectado.

Cuando deja de permitir las conexiones a un servidor de front-end, algunas características de Lync Server y servicios dependen del equilibrador de carga de DNS para garantizar su funcionamiento correcto. Si no usa el equilibrador de carga de DNS en el grupo de servidores, puede que las conexiones a través de dichos servicios no se redirijan a otros servidores durante el período en que el servidor no admite nuevas conexiones, por lo cual es posible que cuando el servidor se desconecte se vean interrumpidas algunas sesiones y llamadas. Las características que dependen del equilibrador de carga de DNS para garantizar que esta opción funciona correctamente son las siguientes:

  - Operador

  - Aplicación de anuncio de conferencia

  - Aplicación de grupo de respuesta

  - Aplicación de anuncio

  - Aplicación de estacionamiento de llamadas

Para más información detallada sobre el equilibrador de carga de DNS, consulte [Equilibrio de carga de DNS en Lync Server 2013](lync-server-2013-dns-load-balancing.md) en la documentación de planeación.

Además de dejar de admitir nuevas conexiones para todos los servicios de un servidor que ejecute Lync Server, también puede evitar que se establezcan nuevas conexiones para servicios individuales de Lync Server. Por ejemplo, este método es útil en una situación en que necesite aplicar una actualización de Lync Server que no requiere que se desconecte el servidor entero. Tenga en cuenta que cuando deje de admitir conexiones para un servicio, es necesario seleccionar un servicio según está agrupado y según se muestra en la lista de servicios de Windows. Por ejemplo, el servicio de front-end de Lync Server y el agente de recopilación de datos para la supervisión son servicios de Lync Server diferentes, pero en la lista de servicios de Windows están consolidados y se muestran como el servicio de front-end de Lync Server. Puede impedir nuevas conexiones para el servicio de front-end de Lync Server, pero no puede impedir nuevas conexiones para dichos dos servicios individuales subyacentes a Lync Server de forma separada.

> [!IMPORTANT]  
> Cuando se establece un servidor para impedir nuevas conexiones y después se reinicia el servidor, el servidor empezará de forma predeterminada y de inmediato a aceptar nuevas comunicaciones tras reiniciarse. Para evitar esto, establezca que el servidor solo pueda pausarse y reanudarse manualmente antes de reiniciar el servidor.



## Para impedir nuevas conexiones a Lync Server:

1.  Inicie sesión en el equipo local como miembro del grupo Administradores.

2.  Abra la consola del complemento Servicios: Haga clic en **Inicio**, elija **Todos los programas**, **Herramientas administrativas** y después haga clic en **Servicios**.

3.  En la lista, haga doble clic en el servicio de Windows Lync Server en el que desea impedir que se realicen nuevas conexiones.

4.  En el cuadro de diálogo Propiedades, en **Estado del servicio: Iniciado**, haga clic en **Pausar**.

5.  Como alternativa, y recomendación, junto a **Tipo de inicio**, haga clic en **Manual**.
    
    > [!IMPORTANT]  
    > Cuando se establece un servidor para impedir nuevas conexiones y después se reinicia el servidor, el servidor empezará de forma predeterminada y de inmediato a aceptar nuevas comunicaciones tras reiniciarse. Para evitar esto, establezca que el servidor solo pueda pausarse y reanudarse manualmente antes de reiniciar el servidor.
    


6.  Cuando haya terminado, haga clic en **Aceptar**.

