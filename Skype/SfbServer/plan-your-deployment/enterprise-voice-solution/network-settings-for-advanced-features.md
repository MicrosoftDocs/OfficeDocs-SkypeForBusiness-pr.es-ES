---
title: Configuración de red para las características avanzadas de Enterprise Voice en Skype para Business Server
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 7f6de9e4-c8a4-44e4-8d14-21fe8c45283a
description: Información sobre regiones de red, sitios de red y subredes IP. Todos estos deben configurarse para implementar el Plan de desvío de medios en Skype para la empresa, Plan para llamar el control de admisión de Skype para Business Server), o un Plan de servicios de emergencia en Skype para Business Server en Skype para Business Server Enterprise Voice.
ms.openlocfilehash: 6dad93aa2d5ef235b07f2189329f94d94b1a3d02
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2018
ms.locfileid: "23885660"
---
# <a name="network-settings-for-the-advanced-enterprise-voice-features-in-skype-for-business-server"></a>Configuración de red para las características avanzadas de Enterprise Voice en Skype para Business Server

Información sobre regiones de red, sitios de red y subredes IP. Todas estas deben configurarse para implementar el [Plan para los medios de desvío en Skype para la empresa](media-bypass.md), [Plan de control de admisión de llamadas en Skype para Business Server](call-admission-control.md)o de [planeación para servicios de emergencia en Skype para Business Server](emergency-services.md) en Skype para Business Server Enterprise Voice.

Skype para Business Server tiene tres características avanzadas de Enterprise Voice: [Plan para el control de admisión de llamadas en Skype para Business Server](call-admission-control.md), la [planeación de servicios de emergencia en Skype para Business Server](emergency-services.md)y [planeación el desvío de medios en Skype para la empresa ](media-bypass.md). Estas características compartan determinados requisitos de configuración de regiones de red, sitios de red y asociación de cada subred de la Skype para la topología de servidor empresarial con un sitio de red.

En este tema se proporciona una visión general de los requisitos de configuración que son comunes a las tres de estas características de Enterprise Voice avanzadas.

## <a name="network-regions"></a>Regiones de red

Una región de red es un concentrador de red o una red troncal de red que solo se usa en la configuración del servicio de control de admisión de llamadas (CAC), E9-1-1 y la omisión de medios.

> [!NOTE]
> Regiones de red no son los mismos que Skype para regiones de conferencia de acceso telefónico de Business Server, que son necesarias para asociar los números de acceso telefónico con Skype uno o varios planes de marcado de Business Server. Para obtener información detallada acerca de las regiones de conferencia de acceso telefónico, consulte [Planning for conferencia de acceso telefónico](https://technet.microsoft.com/library/9aff949e-3dac-481a-be46-a180c72e8066.aspx).

CAC requiere que cada región de red tienen un Skype asociado para el sitio central de Business Server, que administra el tráfico de medios dentro de la región (es decir, toma decisiones basándose en las directivas que se han configurado, con respecto a o no un audio en tiempo real o sesión de vídeo puede establecerse). Skype para sitios centrales de Business Server no representan ubicaciones geográficas, pero en su lugar lógicos grupos de servidores que están configurados como un grupo de servidores o un conjunto de grupos de servidores.

Para configurar una región de red, puede usar la ficha **regiones** en la sección **Configuración de red** de Skype para el Panel de Control de servidor empresarial o ejecutar el **Nuevo-CsNetworkRegion** o Skype **Set-CsNetworkRegion** para la empresa Cmdlets del Shell de administración de servidor. Para obtener instrucciones, consulte [Deploy regiones de red, sitios y las subredes de Skype para la empresa](../../deploy/deploy-enterprise-voice/deploy-network.md) en la documentación de implementación o hacer referencia a la Skype para la documentación del Shell de administración de servidor empresarial.

Todas las características de Enterprise Voice avanzadas tres comparten las mismas definiciones de región de red. Si ya has creado las regiones de red de una característica, no necesitarás crear regiones de red para las otras características. Pero, es posible que necesites modificar una definición de región de red existente para aplicar una configuración específica de una característica. Por ejemplo, si has creado las regiones de red de E9-1-1 (que no necesitan tener asociado un sitio central) y, más tarde, implementas el servicio de control de admisión de llamadas, necesitas modificar cada una de las definiciones de las regiones de red para especificar un sitio central.

Para asociar un Skype para sitio central Business Server con una región de red, especifica el nombre del sitio central, ya sea mediante el uso de la sección de **Configuración de red** de Skype para el Panel de Control de servidor empresarial o mediante la ejecución de la **New-CsNetworkRegion** o cmdlets **Set-CsNetworkRegion** . Para obtener instrucciones, consulte [Deploy regiones de red, sitios y las subredes de Skype para la empresa](../../deploy/deploy-enterprise-voice/deploy-network.md) en la documentación de implementación o hacer referencia a la Skype para la documentación del Shell de administración de servidor empresarial.

## <a name="network-sites"></a>Sitios de red

Un sitio de red representa una ubicación geográfica, como una oficina de sucursal, una oficina regional o una oficina principal. Cada sitio de red necesita asociarse con una región de red determinada.

> [!NOTE]
> Sitios de red se usan sólo en las características avanzadas de Enterprise Voice. No son los mismos que los sitios de sucursal que configurar en su Skype de topología de servidores de negocio.

Para configurar un sitio de red y asociarla a una región de red, puede usar la sección de **Configuración de red** de Skype para el Panel de Control de servidor empresarial o ejecutar el Skype para Shell de administración de servidor empresarial **New-CsNetworkSite** o ** Set-CsNetworkSite** cmdlets. Para obtener información detallada, vea [creación o modificación de un sitio de red](https://technet.microsoft.com/library/14e24856-9996-4da4-9f31-300940bdf5aa.aspx) en la documentación de implementación o hacer referencia a la Skype para la documentación del Shell de administración de servidor empresarial.

## <a name="identify-ip-subnets"></a>Identificar subredes IP

Para cada sitio de red, tendrás que trabajar con el administrador de la red para determinar qué subredes IP están asignadas a cada sitio de red. Si el administrador de la red ya ha organizado las subredes IP en regiones de red y sitios de red, tu trabajo se habrá simplificado en gran medida.

Por ejemplo, el sitio Nueva York de la región Norteamérica puede tener asignadas las siguientes subredes IP: 172.29.80.0/23, 157.57.216.0/25, 172.29.91.0/23, 172.29.81.0/24. Si Alberto, que normalmente trabaja en Detroit, viaja a la oficina de Nueva York para recibir formación, y enciende su PC y se conecta a la red, su PC obtendrá una dirección IP de uno de los cuatro rangos asignados a Nueva York, por ejemplo, 172.29.80.103.

> [!CAUTION]
> Las subredes IP especificadas durante la configuración de red del servidor necesitan coincidir con el formato que proporcionan los equipos cliente para que se puedan usar adecuadamente para la omisión de medios. Un Skype para clientes empresariales toma su dirección IP local y enmascara la dirección IP con la máscara de subred asociada. Al determinar el identificador de omisión asociado a cada cliente, el registrador comparará la lista de subredes IP asociadas con cada sitio de red con la subred indicada por el cliente para comprobar que coincidan exactamente. Por este motivo, es importante que las subredes introducidas durante la configuración de la red del servidor sean subredes reales y no virtuales. (Si implementar el control de admisión de llamadas, pero el desvío de medios no, el control de admisión de llamadas funcionará correctamente incluso si configurar virtuales subredes.) Por ejemplo, si un Skype para clientes empresariales que se inicia sesión en un equipo con una dirección IP de 172.29.81.57 con una máscara de subred de 255.255.255.0, solicitará el identificador de desvío que está asociado a la subred 172.29.81.0. Si la red se define como 172.29.0.0/16, aunque el cliente pertenezca a una subred virtual, el registrador no lo considerará una coincidencia porque el registrador está buscando específicamente la subred 172.29.81.0. Por lo tanto, es importante que el administrador introduce subredes exactamente como proporcionado por Skype para clientes empresariales (que se aprovisionan con subredes durante la configuración de red, estáticamente o por el protocolo de configuración dinámica de Host (DHCP).)

## <a name="associating-subnets-with-network-sites"></a>Asociar subredes con sitios de red

Cada subred de la red empresarial necesita asociarse a un sitio de red (es decir, cada subred tiene que estar asociada a una ubicación geográfica). Esta asociación de subredes habilita las características avanzadas de Enterprise Voice localizar los extremos geográficamente. Por ejemplo, ubicar los extremos permite al CAC regular el flujo de datos de audio y vídeo que recibe y envía el sitio de red en tiempo real.

Para asociar subredes a sitios de red, puede usar la sección de **Configuración de red** de Skype para el Panel de Control de Business Server o puede usar el Skype para Shell de administración de servidor empresarial. Para obtener instrucciones, consulte [asociar una subred a un sitio de red](https://technet.microsoft.com/library/aa69e3ac-542a-4ba1-9582-2e6bee29f633.aspx) en la documentación de implementación o hacer referencia a la Skype para la documentación del Shell de administración de servidor empresarial.

## <a name="see-also"></a>Vea también

[Planeación de control de admisión de llamadas en Skype para Business Server](call-admission-control.md)

[Planeación de servicios de emergencia en Skype para Business Server](emergency-services.md)

[Planear el desvío de medios en Skype para la empresa](media-bypass.md)

