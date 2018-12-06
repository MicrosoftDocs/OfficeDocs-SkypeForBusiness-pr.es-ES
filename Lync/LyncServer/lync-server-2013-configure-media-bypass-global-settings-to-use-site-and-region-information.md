---
title: "Config. global del desvío de medios en Lync Server 2013 para info. de sitio y región"
TOCTitle: "Conf. par. gl. du cont. média ds LS 2013 pr ut. inf. rel. aux sites et rég."
ms:assetid: 0a21cdf1-f350-49da-b346-70806f256bea
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398150(v=OCS.15)
ms:contentKeyID: 48274377
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configurar las opciones globales del desvío de medios en Lync Server 2013 para usar la información de sitio y región

 

_**Última modificación del tema:** 2012-09-21_


> [!NOTE]
> En este tema se asume que ya ha configurado el desvío de medios para todas las conexiones basadas en troncos desde el servidor de mediación a un servidor del mismo nivel (una puerta de enlace de la red telefónica conmutada (RTC), un sistema IP-PBX, o un controlador de borde de sesión (SBC) en un proveedor de servicios de telefonía por Internet (ITSP)) para un servicio o sitio específico para el que desea que los medios se desvíen del servidor de mediación.<BR>En este tema también se asume que ya ha definido todos los sitios centrales y las sucursales en Generador de topologías de modo que coincidan con la región de red, el sitio de red y la configuración de subred que ha realizado de acuerdo con los pasos que se muestran en <A href="lync-server-2013-create-or-modify-a-network-region.md">Crear o modificar una región de red en Lync Server 2013</A>, <A href="lync-server-2013-create-or-modify-a-network-site.md">Crear o modificar un sitio de red en Lync Server 2013</A> y <A href="lync-server-2013-associate-a-subnet-with-a-network-site.md">Asociar una subred a un sitio de red en Lync Server 2013</A>. Si no coinciden, el desvío de medios no se realizará.



Además de la habilitación del desvío de medios para conexiones individuales basadas en troncos asociadas a un servidor del mismo nivel, también deberá configurar opciones globales. Si usa los pasos que se muestran en este tema para configurar las opciones globales para el desvío de medios, se asume que una de las siguientes situaciones, o ambas, repercutirán en su configuración:

  - *No* dispone de buena conectividad entre los extremos de Lync Server y los puntos para los que ha configurado el desvío de medios en la conexión basada en troncos.

  - El control de admisión de llamadas (CAC) para la administración del ancho de banda está habilitado.
    

    > [!NOTE]
    > Para obtener más información acerca de las consideraciones relacionadas con el control de admisión de llamadas y el desvío de medios, consulte la sección Control de admisión de llamadas de conexiones RTC de <A href="lync-server-2013-media-bypass-and-mediation-server.md">Omisión de medios y servidor de mediación en Lync Server 2013</A> en la documentación referente a la planeación.



La información de región de red y sitio de red se comparte entre las características de Enterprise Voice avanzadas del control de admisión de llamadas y el desvío de medios cuando ambos están habilitados. Por consiguiente, si ya ha configurado el control de admisión de llamadas, no es necesario que realice el siguiente procedimiento para editar la información de región y sitio específica para el desvío de medios. Siga los pasos de este procedimiento si todavía no ha configurado los sitios y regiones de red para el control de admisión de llamadas y desea cambiar las opciones del desvío de medios.

O bien, siga estos pasos si desea usar la información de sitio y región al tomar la decisión de desvío, pero no pretende habilitar el control de admisión de llamadas. En este caso, los vínculos de restricción de ancho de banda deberán representarse a través de directivas entre sitios de red tal y como se describe en [Crear directivas entre sitios de red en Lync Server 2013](lync-server-2013-create-network-intersite-policies.md). En este caso, las restricciones del ancho de banda real no son tan importantes, ya que no se ha habilitado el control de admisión de llamadas. En su lugar, se usan estos vínculos para que las subredes de división especifiquen cuáles son las que no presentan límites de ancho de banda y pueden usar, por consiguiente, el desvío de medios. Tenga en cuenta que esto también es posible cuando se ha habilitado tanto el control de admisión de llamadas como el desvío de medios.

Además, para que la desviación funcione correctamente, debe existir coherencia entre cómo se define un sitio en Generador de topologías y cómo se define al configurar sitios de red y regiones de red. Por ejemplo, si dispone de una sucursal y define en Generador de topologías que solo tiene implementada una puerta de enlace RTC, esa sucursal deberá configurarse con una directiva de Enterprise Voice que permita que las llamadas RTC de los usuarios de la sucursal pasen a través de la puerta de enlace RTC de la sucursal.

## Configurar la información de sitio y región para el desvío de medios

1.  Abra una ventana del explorador y después introduzca la dirección URL de administración para abrir el panel de control de Lync Server. Para más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Abrir las herramientas administrativas de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

2.  En la barra de navegación izquierda, haga clic en **Configuración de red**.

3.  Haga doble clic en la configuración **Global** de la tabla.

4.  En la página **Editar configuración global**, seleccione la casilla **Habilitar desvío de medios**.

5.  Haga clic en **Usar la configuración de sitios y regiones**.

6.  Si es necesario, seleccione la casilla **Habilitar desvío para sitios sin asignar**.
    

    > [!NOTE]
    > Seleccione esta casilla solamente si dispone de uno o más sitios grandes asociados a la misma región que no tenga restricciones de ancho de banda (por ejemplo, un sitio central grande) y si dispone también de algunas sucursales asociadas con la misma región que no tienen restricciones de ancho de banda. Cuando habilita el desvío para sitios sin asignar, la configuración se simplifica ya que solo especifica subredes asociadas con las sucursales, en lugar de tener que especificar todas las subredes asociadas a todos los sitios. Se recomienda no activar esta casilla si se ha habilitado el control de admisión de llamadas.



7.  Haga clic en **Confirmar**.

A continuación, agregue subredes al sitio de red, tal y como se indica en [Asociar subredes a sitios de red para el desvío de medios](lync-server-2013-associate-subnets-with-network-sites-for-media-bypass.md). (Los procedimientos reales para asociar subredes a sitios de red se describen en [Asociar una subred a un sitio de red en Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md)). Cuando haya asociado todas las subredes a sitios de red, la implementación del desvío de medios habrá finalizado.

> [!IMPORTANT]  
> Si todavía no ha creado regiones de red y sitios de red, deberá crearlos en primer lugar para poder continuar con la implementación del desvío de medios. Para obtener más información, consulte <a href="lync-server-2013-create-or-modify-a-network-region.md">Crear o modificar una región de red en Lync Server 2013</a> y <a href="lync-server-2013-create-or-modify-a-network-site.md">Crear o modificar un sitio de red en Lync Server 2013</a>.



## Vea también

#### Conceptos

[Asociar subredes a sitios de red para el desvío de medios](lync-server-2013-associate-subnets-with-network-sites-for-media-bypass.md)

