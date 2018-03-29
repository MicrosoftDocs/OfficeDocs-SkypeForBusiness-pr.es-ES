---
title: Configuración de red para las características avanzadas de telefonía IP empresarial en Skype Empresarial Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/16/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 7f6de9e4-c8a4-44e4-8d14-21fe8c45283a
description: Información sobre regiones de red, sitios de red y subredes IP. Todos se deben configurar para implementar el Plan de medios de derivación en Skype para el negocio de 2015, Plan de control de admisión de llamadas en Skype para Business Server 2015), o un Plan de servicios de emergencia en Skype para Business Server 2015 en Skype para Telefonía IP empresarial de Business Server.
ms.openlocfilehash: eb24dc5098fe71cecc8099c2949039a91e61ebd7
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="network-settings-for-the-advanced-enterprise-voice-features-in-skype-for-business-server-2015"></a>Configuración de red para las características avanzadas de telefonía IP empresarial en Skype Empresarial Server 2015
 
Información sobre regiones de red, sitios de red y subredes IP. Todos ellos deben estar configurados para implementar el [Plan para los medios de derivación en Skype para negocios 2015](media-bypass.md), [Plan de control de admisión de llamada en Skype para Business Server 2015](call-admission-control.md)), o el [Plan de servicios de emergencia en Skype para Business Server 2015](emergency-services.md) en Skype para Empresa de Telefonía IP empresarial de servidor.
  
Skype para Business Server tiene tres características avanzadas de Telefonía IP empresarial: [Plan de control de admisión de llamada en Skype para Business Server 2015](call-admission-control.md)), [planear servicios de emergencia en Skype para Business Server 2015](emergency-services.md)y bypass [Plan para medios en Skype para 2015 Business](media-bypass.md). Estas características comparten ciertos requisitos de configuración para las regiones de red, sitios de red y asociación de cada subred en el Skype para la topología de servidores de negocios con un sitio de red. 
  
Este tema proporciona una visión general de los requisitos de configuración que son comunes a las tres de estas características de Telefonía IP empresarial avanzadas.
  
## <a name="network-regions"></a>Regiones de red

Una región de red es un concentrador de red o una red troncal de red que solo se usa en la configuración del servicio de control de admisión de llamadas (CAC), E9-1-1 y la omisión de medios.
  
> [!NOTE]
> Regiones de red no son los mismos que Skype para regiones de conferencia telefónica de Business Server, que son necesarios para asociar números de acceso de acceso telefónico de la conferencia con Skype de uno o más de los planes de marcado de Business Server. Para obtener más información sobre las áreas de la conferencia de acceso telefónico, vea [Planear conferencias de acceso telefónico](http://technet.microsoft.com/library/9aff949e-3dac-481a-be46-a180c72e8066.aspx). 
  
CAC requiere que cada región de red tenga un Skype asociado para el sitio central de Business Server, que administra el tráfico de medios dentro de la región (es decir, toma decisiones basándose en las directivas que ha configurado, acerca de si es o no un sonido en tiempo real o sesión de video se puede establecer). Skype para sitios centrales Business Server no representan ubicaciones geográficas, pero algo lógicos grupos de servidores que están configurados como un grupo o un conjunto de grupos. 
  
Para configurar una región de la red, puede utilizar la ficha de **regiones** en la sección **Configuración de la red** de Skype para Panel de Control de servidor de Business, o ejecutar el **Nuevo CsNetworkRegion** o **Conjunto CsNetworkRegion** Skype para empresas Cmdlets del Shell de administración de servidor. Para obtener instrucciones, vea [implementar regiones de red, sitios y subredes en Skype para el año 2015 de negocio](../../deploy/deploy-enterprise-voice/deploy-network.md) en la documentación de implementación o consulte el Skype para la documentación del Shell de administración de servidor empresarial.
  
Todas las características de Telefonía IP empresarial avanzadas tres comparten las mismas definiciones de región de la red. Si ya has creado las regiones de red de una característica, no necesitarás crear regiones de red para las otras características. Pero, es posible que necesites modificar una definición de región de red existente para aplicar una configuración específica de una característica. Por ejemplo, si has creado las regiones de red de E9-1-1 (que no necesitan tener asociado un sitio central) y, más tarde, implementas el servicio de control de admisión de llamadas, necesitas modificar cada una de las definiciones de las regiones de red para especificar un sitio central.
  
Para asociar un Skype para el sitio central de Business Server con una región de la red, especifique el nombre del sitio central, utilizando la sección de **Configuración de la red** de Skype para Business Server Control Panel o ejecutando el **Nuevo CsNetworkRegion** o **CsNetworkRegion del conjunto de** cmdlets. Para obtener instrucciones, vea [implementar regiones de red, sitios y subredes en Skype para el año 2015 de negocio](../../deploy/deploy-enterprise-voice/deploy-network.md) en la documentación de implementación o consulte el Skype para la documentación del Shell de administración de servidor empresarial.
  
## <a name="network-sites"></a>Sitios de red

Un sitio de red representa una ubicación geográfica, como una oficina de sucursal, una oficina regional o una oficina principal. Cada sitio de red necesita asociarse con una región de red determinada.
  
> [!NOTE]
> Sitios de red se utilizan sólo por las características avanzadas de Telefonía IP empresarial. No son lo mismo que las sucursales que configure en su Skype para la topología de servidores de empresa. 
  
Para configurar un sitio de red y asociarla a una región de la red, puede utilizar la sección de **Configuración de la red** de Skype para el Panel de Control de servidor de Business, o ejecutar el Skype para el Shell de administración de servidor empresarial **Nuevo CsNetworkSite** o ** Conjunto CsNetworkSite** cmdlets. Para obtener información detallada, vea [creación o modificación de un sitio de red](http://technet.microsoft.com/library/14e24856-9996-4da4-9f31-300940bdf5aa.aspx) en la documentación de implementación o consulte el Skype para la documentación del Shell de administración de servidor empresarial.
  
## <a name="identify-ip-subnets"></a>Identificar subredes IP

Para cada sitio de red, tendrás que trabajar con el administrador de la red para determinar qué subredes IP están asignadas a cada sitio de red. Si el administrador de la red ya ha organizado las subredes IP en regiones de red y sitios de red, tu trabajo se habrá simplificado en gran medida.
  
Por ejemplo, el sitio Nueva York de la región Norteamérica puede tener asignadas las siguientes subredes IP: 172.29.80.0/23, 157.57.216.0/25, 172.29.91.0/23, 172.29.81.0/24. Si Alberto, que normalmente trabaja en Detroit, viaja a la oficina de Nueva York para recibir formación, y enciende su PC y se conecta a la red, su PC obtendrá una dirección IP de uno de los cuatro rangos asignados a Nueva York, por ejemplo, 172.29.80.103.
  
> [!CAUTION]
> Las subredes IP especificadas durante la configuración de red del servidor necesitan coincidir con el formato que proporcionan los equipos cliente para que se puedan usar adecuadamente para la omisión de medios. Un Skype para Business client toma su dirección IP local y enmascara la dirección IP con la máscara de subred asociada. Al determinar el identificador de omisión asociado a cada cliente, el registrador comparará la lista de subredes IP asociadas con cada sitio de red con la subred indicada por el cliente para comprobar que coincidan exactamente. Por este motivo, es importante que las subredes introducidas durante la configuración de la red del servidor sean subredes reales y no virtuales. (Si se implementa el control de admisión de llamada, pero medios no omitir, control de admisión de llamada funcionará correctamente incluso si configura las subredes virtuales.) Por ejemplo, si un Skype para el cliente de Business inicia sesión en un equipo con una dirección IP de 172.29.81.57 con una máscara de subred de 255.255.255.0, solicitará el identificador de omisión que está asociado con la subred 172.29.81.0. Si la red se define como 172.29.0.0/16, aunque el cliente pertenezca a una subred virtual, el registrador no lo considerará una coincidencia porque el registrador está buscando específicamente la subred 172.29.81.0. Por lo tanto, es importante que el administrador introduce subredes exactamente como proporcionada por Skype para clientes de empresa (que se suministran con subredes durante la configuración de red, estática o mediante Protocolo de configuración dinámica de Host (DHCP).) 
  
## <a name="associating-subnets-with-network-sites"></a>Asociar subredes con sitios de red

Cada subred de la red empresarial necesita asociarse a un sitio de red (es decir, cada subred tiene que estar asociada a una ubicación geográfica). Esta asociación de subredes habilita las características avanzadas de Telefonía IP empresarial localizar geográficamente los extremos. Por ejemplo, ubicar los extremos permite al CAC regular el flujo de datos de audio y vídeo que recibe y envía el sitio de red en tiempo real.
  
Para asociar subredes a sitios de red, puede utilizar la sección de **Configuración de la red** de Skype para el Panel de Control de servidor de negocios o puede utilizar el Skype para el Shell de administración de servidor empresarial. Para obtener instrucciones, vea [asociar una subred a un sitio de red](http://technet.microsoft.com/library/aa69e3ac-542a-4ba1-9582-2e6bee29f633.aspx) en la documentación de implementación o consulte el Skype para la documentación del Shell de administración de servidor empresarial.
  
## <a name="see-also"></a>Vea también

#### 

[Plan de control de admisión de llamadas en Skype para Business Server 2015](call-admission-control.md)
  
[Plan de servicios de emergencia en Skype para Business Server 2015](emergency-services.md)
  
[Planear la omisión de medios en Skype para negocios 2015](media-bypass.md)

