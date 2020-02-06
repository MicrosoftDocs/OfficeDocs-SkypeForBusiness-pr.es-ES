---
title: Configuración de red para las características avanzadas de telefonía empresarial de Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 7f6de9e4-c8a4-44e4-8d14-21fe8c45283a
description: Información sobre regiones de red, sitios de red y subredes IP. Todas estas opciones deben estar configuradas para implementar el plan de omisión de medios en Skype empresarial, planear el control de admisión de llamadas en Skype empresarial Server) o planificar los servicios de emergencia en Skype empresarial Server en Skype empresarial Server Enterprise Voice.
ms.openlocfilehash: 25987630ae2082ca8805d87a988760296637d3f7
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802600"
---
# <a name="network-settings-for-the-advanced-enterprise-voice-features-in-skype-for-business-server"></a>Configuración de red para las características avanzadas de telefonía empresarial de Skype empresarial Server

Información sobre regiones de red, sitios de red y subredes IP. Todas estas opciones deben estar configuradas para implementar el [plan de omisión de medios en Skype empresarial](media-bypass.md), [planear el control de admisión de llamadas en Skype empresarial Server](call-admission-control.md)o [planificar los servicios de emergencia en Skype empresarial Server](emergency-services.md) en Skype empresarial Server Enterprise Voice.

Skype empresarial Server tiene tres características avanzadas de voz empresarial: [planear el control de admisión de llamadas en Skype empresarial Server](call-admission-control.md), [planear los servicios de emergencia en Skype empresarial Server](emergency-services.md)y [planear la omisión de medios en Skype empresarial](media-bypass.md). Estas características comparten determinados requisitos de configuración para regiones de red, sitios de red y Asociación de cada subred en la topología de servidor de Skype empresarial con un sitio de red.

Este tema proporciona una descripción general de los requisitos de configuración comunes a estas tres características avanzadas de telefonía por voz.

## <a name="network-regions"></a>Regiones de red

Una región de red es un concentrador de red o una red troncal de red que solo se usa en la configuración del servicio de control de admisión de llamadas (CAC), E9-1-1 y la omisión de medios.

> [!NOTE]
> Las regiones de red no son las mismas que las regiones de conferencia de acceso telefónico local de Skype empresarial Server, que son necesarias para asociar los números de acceso de las conferencias de acceso telefónico local a uno o varios planes de marcado de Skype empresarial Server. Para obtener más información sobre las regiones de conferencias de acceso telefónico, mira [Planning for Dial-In Conferencing](https://technet.microsoft.com/library/9aff949e-3dac-481a-be46-a180c72e8066.aspx).

CAC requiere que cada región de la red tenga un sitio central de Skype empresarial Server asociado, que administra el tráfico de los medios de la región (es decir, toma decisiones basadas en las directivas que haya configurado, con respecto a si un audio en tiempo real o no o se puede establecer una sesión de video). Los sitios centrales de Skype empresarial Server no representan ubicaciones geográficas, sino grupos lógicos de servidores que están configurados como un grupo o un conjunto de grupos.

Para configurar una región de red, puede usar la pestaña **regiones** de la sección **configuración de red** del panel de control de Skype empresarial Server o ejecutar los cmdlets del shell de administración de Skype empresarial **New-CsNetworkRegion** o **set-CsNetworkRegion** . Para obtener instrucciones, consulte [implementar regiones, sitios y subredes de red en Skype empresarial](../../deploy/deploy-enterprise-voice/deploy-network.md) en la documentación de implementación o consulte la documentación del shell de administración de Skype empresarial.

Las mismas definiciones de regiones de red son compartidas por las tres características avanzadas de Enterprise Voice. Si ya has creado las regiones de red de una característica, no necesitarás crear regiones de red para las otras características. Pero, es posible que necesites modificar una definición de región de red existente para aplicar una configuración específica de una característica. Por ejemplo, si has creado las regiones de red de E9-1-1 (que no necesitan tener asociado un sitio central) y, más tarde, implementas el servicio de control de admisión de llamadas, necesitas modificar cada una de las definiciones de las regiones de red para especificar un sitio central.

Para asociar un sitio central de Skype empresarial Server a una región de red, especifique el nombre del sitio central, ya sea mediante la sección de **configuración de red** del panel de control de Skype empresarial Server, o ejecutando los cmdlets **New-CsNetworkRegion** o **set-CsNetworkRegion** . Para obtener instrucciones, consulte [implementar regiones, sitios y subredes de red en Skype empresarial](../../deploy/deploy-enterprise-voice/deploy-network.md) en la documentación de implementación o consulte la documentación del shell de administración de Skype empresarial.

## <a name="network-sites"></a>Sitios de red

Un sitio de red representa una ubicación geográfica, como una oficina de sucursal, una oficina regional o una oficina principal. Cada sitio de red necesita asociarse con una región de red determinada.

> [!NOTE]
> Los sitios de red solo se usan con las características avanzadas de telefonía IP empresarial. No son iguales a los sitios de sucursales que se configuran en la topología de servidores de Skype empresarial.

Para configurar un sitio de red y asociarlo a una región de red, puede usar la sección **configuración de red** del panel de control de Skype empresarial Server o ejecutar el shell de administración de Skype empresarial **New-CsNetworkSite** o **set-CsNetworkSite** . Para obtener más información, vea [crear o modificar un sitio de red](https://technet.microsoft.com/library/14e24856-9996-4da4-9f31-300940bdf5aa.aspx) en la documentación de implementación o consulte la documentación del shell de administración de Skype empresarial Server.

## <a name="identify-ip-subnets"></a>Identificar subredes IP

Para cada sitio de red, tendrás que trabajar con el administrador de la red para determinar qué subredes IP están asignadas a cada sitio de red. Si el administrador de la red ya ha organizado las subredes IP en regiones de red y sitios de red, tu trabajo se habrá simplificado en gran medida.

Por ejemplo, el sitio Nueva York de la región Norteamérica puede tener asignadas las siguientes subredes IP: 172.29.80.0/23, 157.57.216.0/25, 172.29.91.0/23, 172.29.81.0/24. Si Alberto, que normalmente trabaja en Detroit, viaja a la oficina de Nueva York para recibir formación, y enciende su PC y se conecta a la red, su PC obtendrá una dirección IP de uno de los cuatro rangos asignados a Nueva York, por ejemplo, 172.29.80.103.

> [!CAUTION]
> Las subredes IP especificadas durante la configuración de red del servidor necesitan coincidir con el formato que proporcionan los equipos cliente para que se puedan usar adecuadamente para la omisión de medios. Un cliente de Skype empresarial toma su dirección IP local y enmascara la dirección IP con la máscara de subred asociada. Al determinar el identificador de omisión asociado a cada cliente, el registrador comparará la lista de subredes IP asociadas con cada sitio de red con la subred indicada por el cliente para comprobar que coincidan exactamente. Por este motivo, es importante que las subredes introducidas durante la configuración de la red del servidor sean subredes reales y no virtuales. (Si implementas el control de admisión de llamadas, pero no la omisión de medios, el control de admisión de llamadas funcionará correctamente incluso si configuras las subredes virtuales). Por ejemplo, si un cliente de Skype empresarial inicia sesión en un equipo con una dirección IP de 172.29.81.57 con una máscara de subred IP 255.255.255.0, se le solicitará la identificación de omisión asociada con la subred 172.29.81.0. Si la red se define como 172.29.0.0/16, aunque el cliente pertenezca a una subred virtual, el registrador no lo considerará una coincidencia porque el registrador está buscando específicamente la subred 172.29.81.0. Por lo tanto, es importante que el administrador escriba las subredes exactamente como se proporciona en los clientes de Skype empresarial (que se aprovisionan con subredes durante la configuración de red, ya sea de forma estática o mediante el protocolo de configuración dinámica de host (DHCP)).

## <a name="associating-subnets-with-network-sites"></a>Asociar subredes con sitios de red

Cada subred de la red empresarial necesita asociarse a un sitio de red (es decir, cada subred tiene que estar asociada a una ubicación geográfica). Esta asociación de subredes permite a las características avanzadas de telefonía a empresas ubicar los puntos de conexión geográficamente. Por ejemplo, ubicar los extremos permite al CAC regular el flujo de datos de audio y vídeo que recibe y envía el sitio de red en tiempo real.

Para asociar subredes a sitios de red, puede usar la sección **configuración de red** del panel de control de Skype empresarial Server, o bien, puede usar el shell de administración de Skype empresarial Server. Para obtener instrucciones, consulte [asociar una subred con un sitio de red](https://technet.microsoft.com/library/aa69e3ac-542a-4ba1-9582-2e6bee29f633.aspx) en la documentación de implementación o consulte la documentación del shell de administración de Skype empresarial Server.

## <a name="see-also"></a>Vea también

[Plan para el control de admisión de llamadas en Skype empresarial Server](call-admission-control.md)

[Planear los servicios de emergencia en Skype empresarial Server](emergency-services.md)

[Plan de omisión de multimedia en Skype empresarial](media-bypass.md)

