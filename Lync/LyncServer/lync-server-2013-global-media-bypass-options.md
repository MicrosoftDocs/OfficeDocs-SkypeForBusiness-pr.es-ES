---
title: Opciones globales de desvío de medios en Lync Server 2013
TOCTitle: Opciones globales de desvío de medios en Lync Server 2013
ms:assetid: 1bd35f90-8587-48a1-b0c2-095a4053fc77
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398255(v=OCS.15)
ms:contentKeyID: 48274592
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Opciones globales de desvío de medios en Lync Server 2013

 

_**Última modificación del tema:** 2016-12-08_


> [!NOTE]
> En este tema se da por hecho que ya se ha configurado un desvío de medios para los troncos a un nivel (una puerta de enlace de red telefónica conmutada (RTC), un sistema PBX IP o un controlador de borde de sesión (SBC) en un proveedor de servicios de telefonía por Internet) para un sitio o servicio específico en los que desea que los medios pasen por alto el servidor de mediación.



Además de habilitar el desvío de medios para las conexiones de tronco individuales asociadas a un nivel, también deberá habilitar el desvío de medios de forma global. La configuración del desvío de medios global puede establecer que se intente realizar siempre un desvío de medios de las llamadas a RTC, o bien que el desvío de medios se use con la asignación de subredes a sitios y regiones de red, algo similar a lo que lleva a cabo el control de admisión de llamadas, que es otra característica de voz avanzada. Cuando tanto el desvío de medios como el control de admisión de llamadas están habilitados, la información de región de red, sitio de red y subred especificada para el control de admisión de llamadas se usa automáticamente para determinar si ha de usarse o no el desvío de medios, lo cual quiere decir que no siempre se va a poder especificar que se intente desviar los medios a RTC siempre cuando el control de admisión de llamadas está habilitado.

En este tema se describe cómo usar el Panel de control de Lync Server y el Shell de administración de Lync Server de manera conjunta para configurar el desvío de medios global.


> [!NOTE]
> Cuando se usan estos pasos para configurar el desvío de medios, se da por hecho que existe una buena conectividad entre los clientes y el nivel de servidor de mediación (por ejemplo, una puerta de enlace RTC, un sistema PBX IP o un SBC en un proveedor de enlace troncal SIP). En caso de que haya limitaciones de ancho de banda en el vínculo, no podrá efectuarse el desvío de medios en la llamada. La omisión de medios no interactuará con todas las puertas de enlace RTC, los sistemas IP-PBX y las SBC. Microsoft ha probado una serie de puertas de enlace RTC y SBC con socios certificados y ha realizado algunas pruebas con los IP-PBX de Cisco. El desvío de medios solo se permite con los productos y las versiones listados en Infraestructura certificada para Microsoft Lync, en <A href="http://go.microsoft.com/fwlink/?linkid=214406%26clcid=0xc0a">http://go.microsoft.com/fwlink/?linkid=214406&amp;clcid=0xC0A</A>.



## Pasos siguientes: Elegir la configuración de desvío de medios global

Una vez habilitado el desvío de medios en las conexión de tronco a un nivel de los sitios o servicios especificados, haga uso del siguiente contenido para cualquiera de los siguientes cometidos:

  - Habilitar el desvío de medios siempre, tal y como se describe en [Configurar el desvío de medios en Lync Server 2013 para omitir siempre el servidor de mediación](lync-server-2013-configure-media-bypass-to-always-bypass-the-mediation-server.md).

  - Configurar el desvío de medios para que use la información de sitio y región, tal y como se describe en [Configurar las opciones globales del desvío de medios en Lync Server 2013 para usar la información de sitio y región](lync-server-2013-configure-media-bypass-global-settings-to-use-site-and-region-information.md).

## Vea también

#### Tareas

[Configurar un tronco con omisión de medios en Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md)  
[Asociar una subred a un sitio de red en Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md)  

#### Conceptos

[Configurar la omisión de medios en Lync Server 2013](lync-server-2013-configure-media-bypass.md)  
[Omisión de medios y servidor de mediación en Lync Server 2013](lync-server-2013-media-bypass-and-mediation-server.md)

