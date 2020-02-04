---
title: 'Lync Server 2013: configuración de red para las características de telefonía avanzada empresarial'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Network settings for the advanced Enterprise Voice features
ms:assetid: 7f6de9e4-c8a4-44e4-8d14-21fe8c45283a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398637(v=OCS.15)
ms:contentKeyID: 48184632
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b1ce4983f7744158c9c9ff56cdfdde818fdc8e14
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765881"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="network-settings-for-the-advanced-enterprise-voice-features-in-lync-server-2013"></a>Network settings for the advanced Enterprise Voice features in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-10_

Lync Server tiene tres características avanzadas de Enterprise Voice: control de admisión de llamadas (CAC), servicios de emergencia (E9-1-1) y omisión de medios. Estas características comparten determinados requisitos de configuración para regiones de red, sitios de red y Asociación de cada subred en la topología de Lync Server con un sitio de red. Para obtener más información sobre cómo planear la implementación de estas características, consulte:

  - [Planear el control de admisión de llamadas en Lync Server 2013](lync-server-2013-planning-for-call-admission-control.md)

  - [Planeación de los servicios de emergencia (E9-1-1) en Lync Server 2013](lync-server-2013-planning-for-emergency-services-e9-1-1.md)

  - [Planificar la omisión de medios en Lync Server 2013](lync-server-2013-planning-for-media-bypass.md)

Para obtener detalles sobre la implementación de cada una de estas características, consulte [implementar características avanzadas de telefonía empresarial en Lync Server 2013](lync-server-2013-deploying-advanced-enterprise-voice-features.md) en la documentación de implementación.

Este tema proporciona una descripción general de los requisitos de configuración comunes a las tres características avanzadas de telefonía empresarial.

<div>

## <a name="network-regions"></a>Regiones de red

Una región de red es un concentrador de red o una red troncal de red que solo se usa en la configuración del servicio de control de admisión de llamadas (CAC), E9-1-1 y la omisión de medios.

<div>


> [!NOTE]  
> Las regiones de red no son las mismas que las regiones de conferencia de acceso telefónico local de Lync Server, que son necesarias para asociar los números de acceso de las conferencias de acceso telefónico local a uno o varios planes de marcado de Lync Server. Para obtener más información sobre las regiones de conferencia de acceso telefónico local, consulte <A href="lync-server-2013-dial-in-conferencing-requirements.md">requisitos de conferencia de acceso telefónico local en Lync Server 2013</A> en la documentación de planeación.



</div>

CAC requiere que cada región de la red tenga un sitio de Lync Server central asociado, que administra el tráfico multimedia dentro de la región (es decir, toma decisiones basadas en las directivas que haya configurado, sobre si una sesión de audio o vídeo en tiempo real puede establecerse). Los sitios centrales de Lync Server no representan ubicaciones geográficas, sino grupos lógicos de servidores que están configurados como un grupo o un conjunto de grupos. Para obtener más información sobre los sitios centrales, consulte [topologías de referencia en Lync Server 2013](lync-server-2013-reference-topologies.md) en la documentación de planeación. Consulte también las [topologías compatibles en Lync Server 2013](lync-server-2013-supported-topologies.md) en la documentación de soporte técnico.

Para configurar una región de red, puede usar la pestaña **regiones** de la sección **configuración de red** del panel de control de Lync Server o ejecutar los cmdlets del shell de administración de Lync Server **New-CsNetworkRegion** o **set-CsNetworkRegion** . Para obtener instrucciones, consulte [crear o modificar una región de red en Lync Server 2013](lync-server-2013-create-or-modify-a-network-region.md) en la documentación de implementación o consulte la documentación del shell de administración de Lync Server.

Las mismas definiciones de regiones de red son compartidas por las tres características avanzadas de Enterprise Voice. Si ya has creado las regiones de red de una característica, no necesitarás crear regiones de red para las otras características. Pero, es posible que necesites modificar una definición de región de red existente para aplicar una configuración específica de una característica. Por ejemplo, si has creado las regiones de red de E9-1-1 (que no necesitan tener asociado un sitio central) y, más tarde, implementas el servicio de control de admisión de llamadas, necesitas modificar cada una de las definiciones de las regiones de red para especificar un sitio central.

Para asociar un sitio central de Lync Server a una región de red, especifique el nombre del sitio central, ya sea mediante la sección de **configuración de red** del panel de control de Lync Server, o ejecutando los cmdlets de Shell de administración de Lync Server **New-CsNetworkRegion** o **set-CsNetworkRegion** . Para obtener instrucciones, consulte [crear o modificar una región de red en Lync Server 2013](lync-server-2013-create-or-modify-a-network-region.md) en la documentación de implementación o consulte la documentación del shell de administración de Lync Server.

</div>

<div>

## <a name="network-sites"></a>Sitios de red

Un sitio de red representa una ubicación geográfica, como una oficina de sucursal, una oficina regional o una oficina principal. Cada sitio de red necesita asociarse con una región de red determinada.

<div>


> [!NOTE]  
> Los sitios de red solo se usan con las características avanzadas de telefonía IP empresarial. No son iguales a los sitios de sucursales que se configuran en la topología de Lync Server. Para obtener más información sobre sitios de sucursales, consulte <A href="lync-server-2013-reference-topologies.md">topologías de referencia en Lync Server 2013</A> en la documentación de planeación. Consulte también las <A href="lync-server-2013-supported-topologies.md">topologías compatibles en Lync Server 2013</A> en la documentación de soporte técnico.



</div>

Para configurar un sitio de red y asociarlo a una región de red, puede usar la sección de **configuración de red** del panel de control de Lync Server o ejecutar el shell de administración de Lync Server **New-CsNetworkSite** o **set-CsNetworkSite** . Para obtener más información, vea [crear o modificar un sitio de red en Lync Server 2013](lync-server-2013-create-or-modify-a-network-site.md) en la documentación de implementación o consulte la documentación del shell de administración de Lync Server.

</div>

<div>

## <a name="identify-ip-subnets"></a>Identificar subredes IP

Para cada sitio de red, tendrás que trabajar con el administrador de la red para determinar qué subredes IP están asignadas a cada sitio de red. Si el administrador de la red ya ha organizado las subredes IP en regiones de red y sitios de red, tu trabajo se habrá simplificado en gran medida.

Por ejemplo, el sitio Nueva York de la región Norteamérica puede tener asignadas las siguientes subredes IP: 172.29.80.0/23, 157.57.216.0/25, 172.29.91.0/23, 172.29.81.0/24. Si Alberto, que normalmente trabaja en Detroit, viaja a la oficina de Nueva York para recibir formación, y enciende su PC y se conecta a la red, su PC obtendrá una dirección IP de uno de los cuatro rangos asignados a Nueva York, por ejemplo, 172.29.80.103.

<div>


> [!WARNING]  
> Las subredes IP especificadas durante la configuración de red del servidor necesitan coincidir con el formato que proporcionan los equipos cliente para que se puedan usar adecuadamente para la omisión de medios. Un cliente de Lync toma su dirección IP local y enmascara la dirección IP con la máscara de subred asociada. Al determinar el identificador de omisión asociado a cada cliente, el registrador comparará la lista de subredes IP asociadas con cada sitio de red con la subred indicada por el cliente para comprobar que coincidan exactamente. Por este motivo, es importante que las subredes introducidas durante la configuración de la red del servidor sean subredes reales y no virtuales. (Si implementas el servicio de control de admisión de llamadas, pero no la omisión de medios, el servicio de control de admisión de llamadas funcionará correctamente incluso aunque configures subredes virtuales).<BR>Por ejemplo, si un cliente de Lync inicia sesión en un equipo con una dirección IP de 172.29.81.57 con una máscara de subred IP 255.255.255.0, se solicitará el identificador de omisión asociado a la 172.29.81.0 de subred. Si la red se define como 172.29.0.0/16, aunque el cliente pertenezca a una subred virtual, el registrador no lo considerará una coincidencia porque el registrador está buscando específicamente la subred 172.29.81.0. Por lo tanto, es importante que el administrador escriba las subredes exactamente como se proporciona en los clientes de Lync (que se aprovisionan con subredes durante la configuración de red, ya sea estáticamente o mediante el protocolo de configuración dinámica de host (DHCP)).



</div>

</div>

<div>

## <a name="associating-subnets-with-network-sites"></a>Asociar subredes con sitios de red

Cada subred de la red empresarial necesita asociarse a un sitio de red (es decir, cada subred tiene que estar asociada a una ubicación geográfica). Esta asociación de subredes permite a las características avanzadas de telefonía a empresas ubicar los puntos de conexión geográficamente. Por ejemplo, ubicar los extremos permite al CAC regular el flujo de datos de audio y vídeo que recibe y envía el sitio de red en tiempo real.

Para asociar subredes a sitios de red, puede usar la sección **configuración de red** del panel de control de Lync Server, o bien, puede usar el shell de administración de Lync Server. Para obtener instrucciones, consulte [asociar una subred con un sitio de red en Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md) en la documentación de implementación o consulte la documentación del shell de administración de Lync Server.

</div>

<div>

## <a name="see-also"></a>Vea también


[Planear el control de admisión de llamadas en Lync Server 2013](lync-server-2013-planning-for-call-admission-control.md)  
[Planeación de los servicios de emergencia (E9-1-1) en Lync Server 2013](lync-server-2013-planning-for-emergency-services-e9-1-1.md)  
[Planificar la omisión de medios en Lync Server 2013](lync-server-2013-planning-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

