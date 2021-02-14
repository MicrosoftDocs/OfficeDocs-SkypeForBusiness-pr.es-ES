---
title: Planear la mensajería instantánea y la presencia en Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 70d2151e-9382-485d-ab14-758597571a74
description: 'Resumen: obtenga información sobre cómo planear la mensajería instantánea y la presencia en Skype Empresarial Server.'
ms.openlocfilehash: a29d68cc66e0ac4a70fc759283646fc3ce49cdf5
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816280"
---
# <a name="plan-for-instant-messaging-and-presence-in-skype-for-business-server"></a>Planear la mensajería instantánea y la presencia en Skype Empresarial Server
 
**Resumen:** Obtenga información sobre cómo planear la mensajería instantánea y la presencia en Skype Empresarial Server.
  
Planee la mensajería instantánea y la presencia en Skype Empresarial Server. Para obtener información sobre opciones de implementación específicas, como habilitar o deshabilitar la mensajería instantánea sin conexión, consulte Implementar la mensajería instantánea y la presencia [en Skype Empresarial Server.](../deploy/im-and-presence/im-and-presence.md)
  
## <a name="plan-for-instant-messaging-and-presence-in-skype-for-business-server"></a>Planear la mensajería instantánea y la presencia en Skype Empresarial Server

Los servidores front-end proporcionan la funcionalidad principal de Skype Empresarial Server, como la mensajería instantánea (MI) y la presencia, y se incluyen en todas las implementaciones de Skype Empresarial Server. Hay dos ediciones disponibles: Skype Empresarial Server Enterprise Edition, que está diseñado principalmente para organizaciones más grandes, y Skype Empresarial Server Standard Edition, que está diseñado principalmente para organizaciones más pequeñas que desean una inversión de hardware más pequeña y no requieren opciones de alta disponibilidad completa. Ambas ediciones admiten todas las cargas de trabajo de Skype Empresarial Server, incluidas la mensajería instantánea, la presencia, las conferencias y Telefonía IP empresarial.
  
La mensajería instantánea (MI) permite a los usuarios comunicarse entre sí en tiempo real desde sus equipos y mediante mensajes basados en texto. Se admiten sesiones de mensajería instantánea con dos participantes y con varios participantes. Un participante de una conversación de mensajería instantánea entre dos participantes puede agregar a la conversación a un tercer participante en cualquier momento. Cuando esto ocurre, la ventana Conversación cambia para admitir características de conferencia.
  
La presencia proporciona información a los usuarios sobre el estado de otros usuarios en la red. El estado de presencia de un usuario proporciona información para ayudar a otras personas a decidir si deben intentar ponerse en contacto con el usuario y si deben usar mensajería instantánea, teléfono o correo electrónico. El estado de presencia fomenta la comunicación instantánea cada vez que sea posible, pero también proporciona información sobre si un usuario está en una reunión o fuera de la oficina, indicando que la comunicación instantánea no es posible. Este estado de presencia se muestra como un icono de presencia en Skype Empresarial y otras aplicaciones para la presencia, incluido el cliente de mensajería y colaboración de Microsoft Outlook, las tecnologías de Microsoft SharePoint y Microsoft Office. El icono de presencia representa la disponibilidad actual del usuario y su disposición para comunicarse. 
  
### <a name="technical-requirements"></a>Requisitos técnicos

La mensajería instantánea (MI) y la presencia siempre se ejecutan en grupos de servidores front-end Enterprise Edition y servidores Standard Edition. Para obtener información sobre el hardware, los sistemas operativos y el software de base de datos admitidos, consulte Puertas de enlace [certificadas, requisitos](../../SfbPartnerCertification/certification/infra-gateways.md)para su entorno de [Skype Empresarial 2015](requirements-for-your-environment/requirements-for-your-environment.md)y requisitos de infraestructura para [Skype Empresarial Server 2019.](../../SfBServer2019/plan/system-requirements.md)
  
### <a name="enabling-communication-with-external-users"></a>Habilitar la comunicación con usuarios externos

Puede aumentar considerablemente las ventajas de su inversión en Skype Empresarial Server al permitir que los usuarios se comuniquen con usuarios externos. Entre los usuarios externos se pueden incluir:
  
- Usuarios remotos: los propios usuarios de su organización, cuando trabajan fuera de los firewalls y usan sus equipos portátiles u otros dispositivos de Skype Empresarial Server.
    
- Usuarios federados: usuarios de empresas con las que trabaja y que también ejecutan Skype Empresarial Server. Para habilitar a sus usuarios para que se pongan en contacto fácilmente con estos usuarios, cree relaciones federadas con estas compañías. 
    
- Usuarios de Skype: los usuarios de Skype Empresarial pueden llegar a los cientos de millones de usuarios de Skype con mensajería instantánea, voz y vídeo.
    
> [!NOTE]
> Ya no se admiten AOL, Yahoo y Google Talk. 
  
> [!NOTE]
> Para habilitar cualquiera o todos estos escenarios, debe implementar un servidor perimetral para ayudar a habilitar comunicaciones seguras entre la implementación de Skype Empresarial Server y los usuarios externos. Los usuarios remotos y los usuarios de las organizaciones federadas de su organización podrán ver la presencia de los demás y comunicarse mediante mensajería instantánea. 
  
> [!NOTE]
> El Protocolo extensible de mensajería y presencia (XMPP) solo es compatible con escenarios de certificación del Comando conjunto de pruebas de interoperabilidad (JITC) de la Plataforma de colaboración de funcionalidades unificadas (UCCP). 
  
### <a name="archiving-im-content"></a>Archivado de contenido de mensajería instantánea

Skype Empresarial Server proporciona características que puede usar si su organización debe seguir las normativas de cumplimiento. Puede usar el archivado para archivar el contenido de los mensajes de mensajería instantánea para todos los usuarios de la organización o solo para determinados usuarios que especifique. Para obtener más información, consulte [Plan for archiving in Skype for Business Server](archiving/archiving.md). 
  
Si también ha implementado Microsoft Exchange Server 2013, puede integrar el archivado de datos de Exchange con el archivado de datos de Skype Empresarial Server y usar una sola herramienta para buscar en ambos tipos de datos archivados. Para obtener más información, vea [Configurar Skype Empresarial Server para usar Exchange Server archivado.](../deploy/integrate-with-exchange-server/use-exchange-archiving.md)
  
### <a name="topologies-and-components"></a>Topologías y componentes

Los únicos componentes necesarios para la mensajería instantánea (MI) y la presencia son:
  
- Los servidores front-end de la organización (conocidos como un grupo de servidores) o un servidor Standard Edition. Las capacidades de mensajería instantánea y presencia siempre están habilitadas en estos servidores. Para obtener más información sobre las topologías y la administración de grupos de servidores front-end, vea administración y alta disponibilidad [del grupo de servidores front-end.](high-availability-and-disaster-recovery/high-availability.md)
    
- Un equilibrador de carga, si tiene un grupo de servidores front-end Enterprise Edition.
    
### <a name="supported-collocation"></a>Colocación compatible

La colocación se define como tener un único servidor, o grupo de servidores, con varios roles instalados. Para obtener más información sobre la colocación, consulte [Topology Basics for Skype for Business Server](topology-basics/topology-basics.md). 
  

