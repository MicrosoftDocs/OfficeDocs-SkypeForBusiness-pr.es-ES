---
title: "Lync Server 2013 : Comp. et topologies utilisés pour le serveur de médiation"
TOCTitle: 'Componentes y topologías para el servidor de mediación '
ms:assetid: 71397168-36c3-4d21-b8ef-db6a751634ee
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398537(v=OCS.15)
ms:contentKeyID: 48275619
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Componentes y topologías para el servidor de mediación en Lync Server 2013

 

_**Última modificación del tema:** 2012-09-21_

En este tema se describen los componentes de los que depende el Servidor de mediación y las topologías en las que puede implementarse el Servidor de mediación

## Dependencias

El Servidor de mediación presenta las siguientes dependencias:

  - **Registrador.** Obligatorio. El registrador es el siguiente salto de señalización en las interacciones del Servidor de mediación con la red de Lync Server 2013. Tenga en cuenta que el Servidor de mediación puede colocarse en un Servidor front-end junto con el registrador, además de instalarse en un grupo de servidores independiente que conste únicamente de Servidores de mediación. El registrador se instala con un Servidor de mediación y una puerta de enlace RTC en una Aplicación de sucursal con funciones de supervivencia.

  - **Servidor de supervisión.** Opcional pero muy recomendable. El Servidor de supervisión permite que el Servidor de mediación registre mediciones de calidad relacionadas con sus sesiones multimedia.

  - **Servidor perimetral.** Obligatorio para la compatibilidad con usuarios externos. El Servidor perimetral permite que el Servidor de mediación interactúe con los usuarios que se encuentran detrás de un NAT o firewall.

## Topologías

El Servidor de mediación de Lync Server 2013 se instala de forma predeterminada con una instancia del registrador en un Servidor Standard Edition, un Grupo de servidores front-end o una Aplicación de sucursal con funciones de supervivencia. Todos los Servidores de mediación de un Grupo de servidores front-end deben configurarse de forma idéntica.

Cuando el rendimiento representa un problema, es preferible implementar uno o varios Servidores de mediación en un grupo de servidores independiente dedicado. Si está implementando troncos SIP, se recomienda que implemente un Grupo de servidores de mediación independiente.

Si implementa conexiones SIP directas a una puerta de enlace RTC cualificada compatible con la omisión de medios y el equilibrio de carga de DNS, no se necesita un Grupo de servidores de mediación independiente, ya que las puertas de enlace cualificadas pueden realizar el equilibrio de carga de DNS para un grupo de Servidores de mediación y pueden recibir tráfico de cualquier Servidor de mediación de un grupo.

Se recomienda también combinar el Servidor de mediación en un Grupo de servidores front-end si se ha implementado sistemas IP-PBX o si se conecta a un controlador de borde de sesión (SBC) del proveedor de servicios de telefonía por Internet, siempre y cuando se cumpla alguna de las condiciones siguientes:

  - El IP-PBX o SBC se configura para recibir tráfico desde cualquier Servidor de mediación del grupo de servidores y puede enrutar el tráfico uniformemente a todos los Servidores de mediación del grupo.

  - El IP-PBX no admite el desvío de medios, pero el Grupo de servidores front-end en que se hospeda el Servidor de mediación puede gestionar la transcodificación de voz para llamadas en las que no se aplique el desvío de medios.

Puede utilizar Microsoft Lync Server 2013, herramienta de planeación para evaluar si el Grupo de servidores front-end en el que ha combinado el Servidor de mediación puede gestionar la carga. Si el entorno no cumple estos requisitos, deberá implementar un Grupo de servidores de mediación independiente.

Para obtener información detallada sobre qué topología debe implementar, consulte [Directrices de implementación para el servidor de mediación en Lync Server 2013](lync-server-2013-deployment-guidelines-for-mediation-server.md).

En la siguiente figura se muestra una topología sencilla que consta de dos sitios conectados mediante un vínculo WAN. El Servidor de mediación se instala con el registrador en un Grupo de servidores front-end en el Sitio 1. Los Servidores de mediación del Sitio 1 controlan la puerta de enlace RTC del Sitio 1 y la puerta de enlace del Sitio 2. En esta topología, el desvío de medios se habilita globalmente para usar la información de sitio y de región, y los troncos a cada una de las puertas de enlace RTC (GW1 y GW2) tienen el desvío habilitado.

**Ejemplo de sitios conectados mediante un vínculo WAN con un servidor de mediación en el Sitio 1 y una puerta de enlace RTC en el Sitio 2**

![Puerta de enlace de WAN de topología de voz con servidor de mediación](images/Gg398537.67872e61-1444-447b-918c-abe89abc3004(OCS.15).jpg "Puerta de enlace de WAN de topología de voz con servidor de mediación")

En la siguiente figura se muestra una topología sencilla, en la que el Servidor de mediación se instala con el registrador en el Grupo de servidores front-end del Sitio 1 y tiene una conexión SIP directa al IP-PBX del Sitio 1. En esta figura, el Servidor de mediación también controla una puerta de enlace RTC del Sitio 2. Se asume que los usuarios de Lync existen en los Sitios 1 y 2. También se asume que el IP-PBX dispone de un procesador de medios asociado que deben atravesar todos los medios originados en los extremos de Lync antes de ser enviados a los extremos de medios controlados por el IP-PBX. En esta topología, el desvío de medios se habilita globalmente para usar la información de sitio y de región, y los troncos a la puerta de enlace RTC y al PBX tienen el desvío de medios habilitado.

**Ejemplo de sitios conectados mediante un vínculo WAN con un servidor de mediación en el Sitio 1 y un sistema PBX en el Sitio 2**

![PBX de WAN del servidor de mediación de topología de voz](images/Gg398537.df6c8a5b-8431-4187-907d-ff5ca26eeeec(OCS.15).jpg "PBX de WAN del servidor de mediación de topología de voz")

Para obtener más información acerca de la planeación para topologías PBX, consulte [Directrices de implementación para el servidor de mediación en Lync Server 2013](lync-server-2013-deployment-guidelines-for-mediation-server.md) y [Opciones de implementación SIP directa en Lync Server 2013](lync-server-2013-direct-sip-deployment-options.md).

En la última figura de este tema, se muestra una topología en la que el Servidor de mediación está conectado al SBC de un proveedor de servicios de telefonía por Internet. Para más información sobre las topologías de troncos SIP, consulte [Enlace troncal SIP en Lync Server 2013](lync-server-2013-sip-trunking.md).

