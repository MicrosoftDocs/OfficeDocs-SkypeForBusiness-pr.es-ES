---
title: Configuración de red para las características Telefonía IP empresarial avanzadas en Skype Empresarial Server
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 7f6de9e4-c8a4-44e4-8d14-21fe8c45283a
description: Obtenga información sobre las regiones de red, los sitios de red y las subredes IP. Todos estos deben configurarse para implementar Plan for media bypass in Skype Empresarial, Plan for call admission control in Skype Empresarial Server) o Plan for emergency services in Skype Empresarial Server in Skype Empresarial Server Telefonía IP empresarial.
ms.openlocfilehash: 77472a77f26139f7a15f0a3820e6fb90a798a5b7
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/05/2022
ms.locfileid: "62391882"
---
# <a name="network-settings-for-the-advanced-enterprise-voice-features-in-skype-for-business-server"></a>Configuración de red para las características Telefonía IP empresarial avanzadas en Skype Empresarial Server

Obtenga información sobre las regiones de red, los sitios de red y las subredes IP. Todos estos deben configurarse para implementar [Plan for media bypass in Skype Empresarial](media-bypass.md), [Plan for call admission control in Skype Empresarial Server](call-admission-control.md) o [Plan for emergency services in Skype Empresarial Server](emergency-services.md) in Skype Empresarial Server Telefonía IP empresarial.

Skype Empresarial Server tiene tres características avanzadas Telefonía IP empresarial: [Planear el control](call-admission-control.md) de admisión de llamadas en Skype Empresarial Server, Planear servicios de emergencia [en Skype Empresarial Server](emergency-services.md) , y [Plan for media bypass in Skype Empresarial](media-bypass.md). Estas características comparten ciertos requisitos de configuración para las regiones de red, los sitios de red y la asociación de cada subred de la topología Skype Empresarial Server con un sitio de red.

En este tema se proporciona información general sobre los requisitos de configuración que son comunes a las tres características Telefonía IP empresarial avanzadas.

## <a name="network-regions"></a>Regiones de red

Una región de red es un concentrador de red o una red troncal de red que solo se usa en la configuración del servicio de control de admisión de llamadas (CAC), E9-1-1 y la omisión de medios.

> [!NOTE]
> Las regiones de red no son las mismas que Skype Empresarial Server las regiones de conferencia de acceso telefónico local, que son necesarias para asociar los números de acceso de conferencia de acceso telefónico local con uno o más planes de marcado Skype Empresarial Server acceso telefónico local. Para obtener más información acerca de las regiones de conferencia de acceso telefónico local, vea [Planning for Dial-In Conferencing](/previous-versions/office/lync-server-2013/lync-server-2013-dial-in-conferencing-requirements).

El CAC requiere que todas las regiones de red tengan asociado un sitio central de Skype Empresarial Server, que administra el tráfico de medios dentro de la región (es decir, toma decisiones en función de las directivas que haya configurado, con respecto a si se puede establecer una sesión de audio o vídeo en tiempo real). Skype Empresarial Server los sitios centrales no representan ubicaciones geográficas, sino grupos lógicos de servidores configurados como un grupo de servidores o un conjunto de grupos de servidores.

Para configurar una región de red, puede usar la pestaña **Regiones** de la sección  Configuración de red del Panel de control de Skype Empresarial Server o ejecutar los **cmdlets New-CsNetworkRegion** o **Set-CsNetworkRegion** Skype Empresarial Server Management Shell. Para obtener instrucciones, consulte [Deploy network regions, sites and subnets in Skype Empresarial](../../deploy/deploy-enterprise-voice/deploy-network.md) en la documentación de implementación, o consulte la documentación del Shell de administración Skype Empresarial Server administración.

Las tres características avanzadas comparten las mismas definiciones de Telefonía IP empresarial región de red. Si ya ha creado las regiones de red de una característica, no necesitará crear regiones de red nuevas para las otras características. Sin embargo, es posible que necesite modificar una definición de región de red existente para aplicar una configuración específica de una característica. Por ejemplo, si ha creado las regiones de red de E9-1-1 (que no necesitan tener asociado un sitio central) y, más tarde, implementa el control de admisión de llamadas, debe modificar cada una de las definiciones de las regiones de red para especificar un sitio central.

Para asociar un sitio central de Skype Empresarial Server con una región de red, especifique el nombre del sitio central mediante la sección Configuración de red  del Panel de control de Skype Empresarial Server o mediante la ejecución de los **cmdlets New-CsNetworkRegion** o **Set-CsNetworkRegion**. Para obtener instrucciones, consulte [Deploy network regions, sites and subnets in Skype Empresarial](../../deploy/deploy-enterprise-voice/deploy-network.md) en la documentación de implementación, o consulte la documentación del Shell de administración Skype Empresarial Server administración.

## <a name="network-sites"></a>Sitios de red

Un sitio de red representa una ubicación geográfica, como una oficina de sucursal, una oficina regional o una oficina principal. Cada sitio de red debe asociarse con una región de red determinada.

> [!NOTE]
> Los sitios de red solo los usan las características Telefonía IP empresarial avanzadas. No son los mismos que los sitios de sucursal que configure en la Skype Empresarial Server topología.

Para configurar un sitio de red y asociarlo a una región de red, puede usar la  sección Configuración de red del Panel de control de Skype Empresarial Server o ejecutar los cmdlets **New-CsNetworkSite** o **Set-CsNetworkSite** del Shell de administración de Skype Empresarial Server. Para obtener más información, consulte [Crear o modificar un](/previous-versions/office/lync-server-2013/lync-server-2013-create-or-modify-a-network-site) sitio de red en la documentación de implementación, o consulte la Skype Empresarial Server shell de administración.

## <a name="identify-ip-subnets"></a>Identificar subredes IP

Para cada sitio de red, tendrá que trabajar con el administrador de la red para determinar qué subredes IP están asignadas a cada sitio de red. Si el administrador de la red ya ha organizado las subredes IP en regiones de red y sitios de red, su trabajo se habrá simplificado en gran medida.

En nuestro ejemplo, el sitio Nueva York de la región Norteamérica puede tener asignadas las siguientes subredes IP: 172.29.80.0/23, 157.57.216.0/25, 172.29.91.0/23, 172.29.81.0/24. Si Bob, que suele trabajar en Detroit, viaja a la oficina de Nueva York para asistir a un curso enciende su equipo y se conecta a la red, su equipo obtendrá una dirección IP de uno de los cuatro rangos asignados a Nueva York, por ejemplo, 172.29.80.103.

> [!CAUTION]
> Las subredes IP especificadas durante la configuración de red del servidor deben coincidir con el formato que proporcionan los equipos cliente para que se puedan usar adecuadamente para la omisión de medios. Un Skype Empresarial toma su dirección IP local y enmascara la dirección IP con la máscara de subred asociada. Al determinar el identificador de omisión asociado a cada cliente, el registrador comparará la lista de subredes IP asociadas con cada sitio de red con la subred indicada por el cliente para comprobar que coincidan exactamente. Por este motivo, es importante que las subredes introducidas durante la configuración de la red del servidor sean subredes reales y no virtuales. (Si implementa el control de admisión de llamadas, pero no la omisión de medios, el control de admisión de llamadas funcionará correctamente incluso si configura subredes virtuales). Por ejemplo, si un cliente de Skype Empresarial inicia sesión en un equipo con una dirección IP de 172.29.81.57 con una máscara de subred IP de 255.255.255.0, solicitará el identificador de omisión asociado a la subred 172.29.81.0. Si la red se define como 172.29.0.0/16, aunque el cliente pertenezca a una subred virtual, el registrador no lo considerará una coincidencia debido a que el registrador está buscando específicamente la subred 172.29.81.0. Por lo tanto, es importante que el administrador escriba subredes exactamente como las proporcionan los clientes de Skype Empresarial (que se aprovisionan con subredes durante la configuración de red, ya sea de forma estática o mediante el Protocolo de configuración dinámica de host (DHCP).

## <a name="associating-subnets-with-network-sites"></a>Asociación de subredes con sitios de red

Cada subred de la red empresarial debe asociarse a un sitio de red (es decir, cada subred tiene que estar asociada a una ubicación geográfica). Esta asociación de subredes permite a las características Telefonía IP empresarial avanzadas localizar geográficamente los puntos de conexión. Por ejemplo, ubicar los extremos permite al CAC regular el flujo de datos de audio y vídeo que recibe y envía el sitio de red en tiempo real.

Para asociar subredes con sitios de red, puede usar la sección  Configuración de red de Skype Empresarial Server Panel de control o puede usar el Shell de administración Skype Empresarial Server red. Para obtener instrucciones, consulte Asociar una subred [con un](/previous-versions/office/lync-server-2013/lync-server-2013-associate-a-subnet-with-a-network-site) sitio de red en la documentación de implementación o consulte la documentación Skype Empresarial Server Shell de administración.

## <a name="see-also"></a>Vea también

[Planear el control de admisión de llamadas en Skype Empresarial Server](call-admission-control.md)

[Planeación de servicios de emergencia en Skype Empresarial Server](emergency-services.md)

[Planear la omisión de medios en Skype Empresarial](media-bypass.md)