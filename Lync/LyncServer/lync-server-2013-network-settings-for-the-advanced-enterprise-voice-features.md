---
title: "Configuración de red para las características avanzadas de telefonía IP empresarial"
TOCTitle: Configuración de red para las características avanzadas de telefonía IP empresarial
ms:assetid: 7f6de9e4-c8a4-44e4-8d14-21fe8c45283a
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398637(v=OCS.15)
ms:contentKeyID: 48275816
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuración de red para las características avanzadas de telefonía IP empresarial en Lync Server 2013

 

_**Última modificación del tema:** 2012-10-10_

Lync Server tiene tres características avanzadas de Telefonía IP empresarial: control de admisión de llamadas (CAC), servicios de emergencia (E9-1-1) y desvío de medios. Estas características comparten algunos requisitos de configuración de regiones de red, sitios de red y asociación de cada subred en la topología de Lync Server con un sitio de red. Para ver más detalles acerca de cómo planear la implementación de estas características, consulte:

  - [Planear el control de admisión de llamadas en Lync Server 2013](lync-server-2013-planning-for-call-admission-control.md)

  - [Planeación de los servicios de emergencia (E9-1-1) en Lync Server 2013](lync-server-2013-planning-for-emergency-services-e9-1-1.md)

  - [Planificar la omisión de medios en Lync Server 2013](lync-server-2013-planning-for-media-bypass.md)

Para ver más detalles acerca de cómo implementar cada una de estas características, consulte “ [Implementación de características avanzadas de telefonía IP empresarial en Lync Server 2013](lync-server-2013-deploying-advanced-enterprise-voice-features.md)” en la documentación sobre implementación.

Este tema resume los requisitos de configuración comunes a las tres características avanzadas de Telefonía IP empresarial.

## Regiones de red

Una región de red es un concentrador de red o una red troncal de red que solo se usa en la configuración del servicio de control de admisión de llamadas (CAC), E9-1-1 y la omisión de medios.


> [!NOTE]
> Las regiones de red no son lo mismo que las regiones de conferencias de acceso telefónico de Lync Server, necesarias para asociar los números de acceso a conferencias de acceso telefónico con uno o más planes de marcado de Lync Server. Para ver más detalles acerca de las regiones de conferencias de acceso telefónico, consulte “ <A href="lync-server-2013-dial-in-conferencing-requirements.md">Planeación de las conferencias de acceso telefónico local en Lync Server 2013</A>” en la documentación sobre planeación.



El CAC requiere que todas las regiones de red tengan asociado un sitio central de Lync Server, que administra el tráfico de medios dentro de la región (es decir, toma decisiones según las directivas que haya configurado para saber si se puede o no establecer una sesión de audio o vídeo en tiempo real). Los sitios centrales de Lync Server no representan ubicaciones geográficas, sino grupos lógicos de servidores configurados como un grupo de servidores o un conjunto de grupos de servidores. Para ver más detalles acerca de los sitios centrales, consulte “ [Topologías de referencia en Lync Server 2013](lync-server-2013-reference-topologies.md)” en la documentación sobre planeación. Consulte también “ [Topologías compatibles en Lync Server 2013](lync-server-2013-supported-topologies.md)” en la documentación sobre compatibilidad.

Para configurar una región de red, puede usar la pestaña **Regiones** de la sección **Configuración de red** de Panel de control de Lync Server, o ejecutar los cmdlets **New-CsNetworkRegion** o **Set-CsNetworkRegion** del Shell de administración de Lync Server. Para ver las instrucciones, consulte “ [Crear o modificar una región de red en Lync Server 2013](lync-server-2013-create-or-modify-a-network-region.md)” en la documentación sobre implementación, o consulte la documentación del Shell de administración de Lync Server.

Las tres características avanzadas de Telefonía IP empresarial comparten las mismas definiciones de regiones de red. Si ya ha creado las regiones de red de una característica, no necesitará crear regiones de red nuevas para las otras características. Sin embargo, es posible que necesite modificar una definición de región de red existente para aplicar una configuración específica de una característica. Por ejemplo, si ha creado las regiones de red de E9-1-1 (que no necesitan tener asociado un sitio central) y, más tarde, implementa el control de admisión de llamadas, debe modificar cada una de las definiciones de las regiones de red para especificar un sitio central.

Para asociar un sitio central de Lync Server a una región de red, especifique el nombre del sitio central mediante la sección **Configuración de red** de Panel de control de Lync Server o ejecutando los cmdlets **New-CsNetworkRegion** o **Set-CsNetworkRegion**Shell de administración de Lync Server. Para ver las instrucciones, consulte [Crear o modificar una región de red en Lync Server 2013](lync-server-2013-create-or-modify-a-network-region.md) en la documentación sobre implementación, o consulte la documentación del Shell de administración de Lync Server.

## Sitios de red

Un sitio de red representa una ubicación geográfica, como una oficina de sucursal, una oficina regional o una oficina principal. Cada sitio de red debe asociarse con una región de red determinada.


> [!NOTE]
> Solo usan los sitios de red las características avanzadas de Telefonía IP empresarial. No equivalen a las sucursales que puede configurar en la topología de Lync Server. Para ver más detalles acerca de las sucursales, consulte “ <A href="lync-server-2013-reference-topologies.md">Topologías de referencia en Lync Server 2013</A>” en la documentación sobre planeación. Consulte también <A href="lync-server-2013-supported-topologies.md">Topologías compatibles en Lync Server 2013</A> en la documentación sobre compatibilidad.



Para configurar un sitio de red y asociarlo a una región de red, puede usar la sección **Configuración de red** de Panel de control de Lync Server o ejecutar los cmdlets Shell de administración de Lync Server**New-CsNetworkSite** o **Set-CsNetworkSite**. Para ver los detalles, consulte [Crear o modificar un sitio de red en Lync Server 2013](lync-server-2013-create-or-modify-a-network-site.md) en la documentación sobre implementación, o consulte la documentación del Shell de administración de Lync Server.

## Identificar subredes IP

Para cada sitio de red, tendrá que trabajar con el administrador de la red para determinar qué subredes IP están asignadas a cada sitio de red. Si el administrador de la red ya ha organizado las subredes IP en regiones de red y sitios de red, su trabajo se habrá simplificado en gran medida.

En nuestro ejemplo, el sitio Nueva York de la región Norteamérica puede tener asignadas las siguientes subredes IP: 172.29.80.0/23, 157.57.216.0/25, 172.29.91.0/23, 172.29.81.0/24. Si Bob, que suele trabajar en Detroit, viaja a la oficina de Nueva York para asistir a un curso enciende su equipo y se conecta a la red, su equipo obtendrá una dirección IP de uno de los cuatro rangos asignados a Nueva York, por ejemplo, 172.29.80.103.

> [!WARNING]  
> Las subredes IP especificadas durante la configuración de red del servidor deben coincidir con el formato que proporcionan los equipos cliente para que se puedan usar adecuadamente para la omisión de medios. Un cliente de Lync toma su dirección IP local y enmascara la dirección IP con la máscara de subred asociada. Al determinar el identificador de omisión asociado a cada cliente, el registrador comparará la lista de subredes IP asociadas con cada sitio de red con la subred indicada por el cliente para comprobar que coincidan exactamente. Por este motivo, es importante que las subredes introducidas durante la configuración de la red del servidor sean subredes reales y no virtuales. (Si implementa el sistema de control de admisión de llamadas, pero no la omisión de medios, el control de admisión de llamadas funcionará correctamente incluso aunque configure subredes virtuales).<br />
> Por ejemplo, si un cliente Lync inicia sesión en un PC con una dirección IP 172.29.81.57 con una máscara de subred IP 255.255.255.0, solicitará el identificador de omisión asociado con la subred 172.29.81.0. Si la red se define como 172.29.0.0/16, aunque el cliente pertenezca a una subred virtual, el registrador no lo considerará una coincidencia debido a que el registrador está buscando específicamente la subred 172.29.81.0. Por lo tanto, es importante que el administrador introduzca las subredes exactamente tal y como las proporcionan los clientes Lync (que se aprovisionan con subredes durante la configuración de red, ya sea de forma estática o mediante el Protocolo de configuración dinámica de host - DHCP).


## Asociación de subredes con sitios de red

Cada subred de la red empresarial debe asociarse a un sitio de red (es decir, cada subred tiene que estar asociada a una ubicación geográfica). Esta asociación de subredes permite que las características avanzadas de Telefonía IP empresarial ubiquen los extremos geográficamente. Por ejemplo, ubicar los extremos permite al CAC regular el flujo de datos de audio y vídeo que recibe y envía el sitio de red en tiempo real.

Para asociar subredes a sitios de red, puede usar la sección **Configuración de red** de Panel de control de Lync Server o usar el Shell de administración de Lync Server. Para ver las instrucciones, consulte “ [Asociar una subred a un sitio de red en Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md)” en la documentación sobre implementación, o consulte la documentación del Shell de administración de Lync Server.

## Vea también

#### Otros recursos

[Planear el control de admisión de llamadas en Lync Server 2013](lync-server-2013-planning-for-call-admission-control.md)  
[Planeación de los servicios de emergencia (E9-1-1) en Lync Server 2013](lync-server-2013-planning-for-emergency-services-e9-1-1.md)  
[Planificar la omisión de medios en Lync Server 2013](lync-server-2013-planning-for-media-bypass.md)

