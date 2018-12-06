---
title: Administración de la Calidad de servicio (QoS) en Lync Server 2013
TOCTitle: Administración de la Calidad de servicio (QoS) en Lync Server 2013
ms:assetid: ab1051c3-8380-4d72-86df-37a61b1e4a41
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg405409(v=OCS.15)
ms:contentKeyID: 48276309
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Administración de la Calidad de servicio (QoS) en Lync Server 2013

 

_**Última modificación del tema:** 2016-12-08_

La calidad de servicio (QoS) es una tecnología de red que usan algunas organizaciones para ofrecer una experiencia de usuario final óptima para las comunicaciones de audio y vídeo. QoS se usa principalmente en redes donde el ancho de banda es limitado. Como hay una gran cantidad de paquetes de red compitiendo por una cantidad relativamente pequeña de ancho de banda disponible, la calidad de servicio permite a los administradores asignar prioridades más altas a los paquetes que contienen datos de audio o vídeo. Al asignar una prioridad más alta a estos paquetes, las comunicaciones de audio y vídeo probablemente se completen con mayor rapidez y con menos interrupciones que las sesiones de red que incluyen transferencias de archivos, exploración web o copias de seguridad de bases de datos. Esto se debe a que se asigna una prioridad de "mejor esfuerzo" a los paquetes de red usados para las transferencias de archivos o las copias de seguridad de bases de datos.


> [!NOTE]
> Como regla general, la calidad de servicio se aplica solamente a las sesiones de comunicación de la red interna. Al implementar QoS, debe configurar los servidores y enrutadores para que admitan el marcado de paquetes, pero de una manera especial. No puede dar por sentado que la calidad de servicio se admitirá en Internet o en otras redes. Incluso si la calidad de servicio se admite en otras redes, no existe ninguna garantía de que QoS se configurará de la misma manera que configuró el servicio en la red.



Microsoft Lync Server 2013 no requiere la tecnología de calidad de servicio. Si actualmente no usa QoS, no es necesario que instale el servicio antes de instalar Lync Server 2013. Si sufre una pérdida de paquetes importante en la red, la manera recomendada de aliviar el problema es agregar ancho de banda adicional. Si no es posible agregar más ancho de banda, recomendamos implementar la calidad de servicio en su lugar.

Lync Server 2013 ofrece compatibilidad total con la calidad de servicio: eso significa que las organizaciones que ya usan QoS pueden integrar fácilmente Lync Server en la infraestructura de red existente. Para ello, es necesario realizar las siguientes tareas:

  - [Habilitación de la QoS para dispositivos que no están basados en Windows](lync-server-2013-enabling-qos-for-devices-that-are-not-based-on-windows.md). De manera predeterminada, QoS se deshabilita para los equipos y otros dispositivos (como iPhone) que ejecutan otros sistemas operativos. Aunque puede usar Lync Server para habilitar y deshabilitar la calidad de servicio para los dispositivos, por lo general, no puede usar el producto para modificar los códigos DSCP que usan estos dispositivos.

  - [Configuración de intervalos de puertos para servidores de conferencias, aplicaciones y mediación](lync-server-2013-configuring-port-ranges-for-your-conferencing-application-and-mediation-servers.md). Debe reservar un conjunto único de puertos para diferentes tipos de paquetes, como paquetes de audio y vídeo. Con Lync Server 2013, no se habilita ni deshabilita la calidad de servicio al, por ejemplo, definir un valor de propiedad en True o en False. En su lugar, la calidad de servicio se habilita al configurar intervalos de puertos, y al crear y aplicar luego una directiva de grupo. Si más adelante decide no usar QoS, para "deshabilitar" la calidad de servicio, simplemente puede quitar los objetos de directiva de grupo adecuados.

  - [Configuración de los intervalos de puertos para servidores perimetrales](lync-server-2013-configuring-port-ranges-for-your-edge-servers.md). Aunque no es un requisito, puede configurar los servidores perimetrales para que usen los mismos intervalos de puertos que los otros servidores.

  - [Configuración de los intervalos de puertos para clientes de Microsoft Lync](lync-server-2013-configuring-port-ranges-for-your-microsoft-lync-clients.md). Estos intervalos de puertos solo se aplican a equipos cliente y, por lo general, no son los mismos que los intervalos de puertos configurados en los servidores.

  - [Configurar la directiva de calidad de servicio para los servidores de conferencia, aplicación y mediación en Lync Server 2013](lync-server-2013-configuring-a-quality-of-service-policy-for-your-conferencing-application-and-mediation-servers.md). Estas directivas determinan los códigos DSCP que se aplican a diferentes tipos de paquetes.

  - [Configuración de la directiva de calidad de servicio para los servidores perimetrales de audio y vídeo](lync-server-2013-configuring-a-quality-of-service-policy-for-your-a-v-edge-servers.md). Esto solo se debe hacer para el lado interno de los servidores perimetrales, ya que la calidad de servicio está diseñada para usarse en la red interna y no en Internet.

  - [Configuración de las directivas de calidad de servicio para clientes que se ejecutan en Windows 7 o Windows 8](lync-server-2013-configuring-quality-of-service-policies-for-clients-running-on-windows-7-or-windows-8.md). Tenga en cuenta que Microsoft Lync Server 2013 no admite QoS para otros sistemas operativos Windows, como Windows Vista o Windows XP.

  - [Configuración de la calidad de servicio en dispositivos Microsoft Lync Phone Edition](lync-server-2013-configuring-quality-of-service-on-microsoft-lync-phone-edition-devices.md). De manera predeterminada, QoS se habilita para los dispositivos Lync Phone Edition. Sin embargo, recomendamos cambiar el valor predeterminado de DSCP a fin de garantizar que todos los paquetes de audio de la organización usen el mismo código DSCP.


> [!NOTE]
> Si utiliza Microsoft Windows Server 2012 o Windows Server 2012 R2, tal vez le interese el nuevo conjunto de cmdlets de Windows PowerShell disponible para administrar la Calidad de servicio en dicha plataforma. Para obtener más información, consulte Cmdlets para la Calidad de servicio de la red en Windows PowerShell en<A href="http://go.microsoft.com/fwlink/p/?linkid=285379">http://go.microsoft.com/fwlink/p/?LinkId=285379</A>.


