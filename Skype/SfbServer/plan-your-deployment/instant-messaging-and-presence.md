---
title: Planeación de la mensajería instantánea y presencia en Skype para Business Server
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 70d2151e-9382-485d-ab14-758597571a74
description: 'Resumen: Aprenda a planear para mensajería instantánea y presencia en Skype para Business Server.'
ms.openlocfilehash: 8d26ad08242248f08e2e54ba7e46d2aa112e362a
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30898211"
---
# <a name="plan-for-instant-messaging-and-presence-in-skype-for-business-server"></a>Planeación de la mensajería instantánea y presencia en Skype para Business Server
 
**Resumen:** Obtenga información sobre cómo planear para mensajería instantánea y presencia en Skype Business Server.
  
Plan para mensajería instantánea y presencia en Skype para Business Server. Para obtener información acerca de las opciones de implementación específicas, como habilitar o deshabilitar sin conexión mensajería instantánea (mi), vea [implementación de mensajería instantánea y presencia en Skype para Business Server](../deploy/im-and-presence/im-and-presence.md).
  
## <a name="plan-for-instant-messaging-and-presence-in-skype-for-business-server"></a>Planeación de la mensajería instantánea y presencia en Skype para Business Server

Front-End servidores proporcionan básicas de Skype para la funcionalidad del servidor de negocio, como mensajería instantánea (IM) y presencia y se incluyen en cada Skype para la implementación de Business Server. Hay dos ediciones disponibles: Skype para Business Server Enterprise Edition, que se han diseñado principalmente para organizaciones de gran tamaño, y Skype para Business Server Standard Edition, que se han diseñado principalmente para organizaciones más pequeñas que desean un más pequeños inversión en hardware y no requieren opciones completa de alta disponibilidad. Ambas ediciones admiten todos los Skype para las cargas de trabajo Business Server, incluida la mensajería instantánea, presencia, conferencias y Enterprise Voice.
  
La mensajería instantánea (MI) permite a los usuarios comunicarse entre sí en tiempo real desde sus equipos y por medio de mensajes basados en texto. Se admiten sesiones de mensajería instantánea con dos participantes y con varios participantes. Un participante de una conversación de mensajería instantánea entre dos participantes puede agregar a la conversación a un tercer participante en cualquier momento. Cuando esto ocurre, la ventana Conversación cambia para admitir características de conferencia.
  
La presencia proporciona información a los usuarios sobre el estado de los otros usuarios en la red. El estado de presencia de un usuario proporciona información para ayudar a otros usuarios a decidir si deben intentar ponerse en contacto con el usuario y si se debe usar la mensajería instantánea, teléfono o correo electrónico. El estado de presencia fomenta la comunicación instantánea cada vez que sea posible, pero también proporciona información sobre si un usuario está en una reunión o fuera de la oficina, indicando que la comunicación instantánea no es posible. Este estado de presencia se visualiza como un icono de presencia en Skype Empresarial y otras aplicaciones con detección de presencia, incluido el cliente de colaboración y la mensajería de Microsoft Outlook, las tecnologías de Microsoft SharePoint y Microsoft Office. El icono de presencia representa la disponibilidad actual y la disposición de comunicación del usuario. 
  
### <a name="technical-requirements"></a>Requisitos técnicos

La mensajería instantánea (MI) y la presencia siempre se ejecutan en los grupos de servidores front-end Enterprise Edition y en los servidores Standard Edition. Para obtener información sobre el hardware admitido, sistemas operativos y el software de base de datos, vea [Certified puertas de enlace](../../SfbPartnerCertification/certification/infra-gateways.md), [los requisitos para su Skype para entorno empresarial 2015](requirements-for-your-environment/requirements-for-your-environment.md)y requisitos de infraestructura de [de Skype para Business Server 2019 ](../../SfBServer2019/plan/system-requirements.md).
  
### <a name="enabling-communication-with-external-users"></a>Habilitar la comunicación con los usuarios externos

Puede aumentar considerablemente los beneficios de su inversión en Skype para Business Server mediante la habilitación de los usuarios puedan comunicarse con usuarios externos. Entre los usuarios externos se pueden incluir:
  
- Los usuarios remotos: los usuarios de la organización, cuando están trabajando desde fuera de los firewalls y están usando sus equipos portátiles u otro Skype para dispositivos de Business Server.
    
- Los usuarios federados: los usuarios de empresas trabajar con que también ejecutan Skype para Business Server. Si desea habilitar a sus usuarios para que se pongan en contacto fácilmente con estos otros usuarios, cree relaciones federadas con estas compañías. 
    
- Usuarios de Skype: los usuarios de Skype Empresarial pueden ponerse en contacto con cientos de millones de usuarios en Skype por medio de la mensajería instantánea, la voz y el vídeo.
    
> [!NOTE]
> AOL, Yahoo y Google Talk ya no son compatibles. 
  
> [!NOTE]
> Para habilitar cualquier o todos estos escenarios, debe implementar un servidor perimetral para ayudar a permitir las comunicaciones seguras entre su Skype para la implementación de servidor empresarial y los usuarios externos. Los usuarios remotos y los usuarios de organizaciones federadas de la organización podrán ver estado de presencia del otro y comunicarse mediante mensajería instantánea. 
  
> [!NOTE]
> El protocolo de presencia y mensajería extensible (XMPP) es únicamente compatible con los escenarios de certificación de Unified Capabilities Collaboration Platform (UCCP) y Joint Interoperability Test Command (JITC). 
  
### <a name="archiving-im-content"></a>Archivar el contenido de la mensajería instantánea

Skype para Business Server proporciona características que puede usar si la organización debe seguir normativas de cumplimiento. Puede usar el servidor de archivado para archivar el contenido de los mensajes de MI de todos los usuarios de la organización, o solamente de algunos específicos. Para obtener información detallada, consulte [Plan para el archivado en Skype para Business Server](archiving/archiving.md). 
  
Si también ha implementado Microsoft Exchange Server 2013, puede integrar el archivado de datos de Exchange con el archivado de Skype para los datos de Business Server y usar una sola herramienta para buscar ambos tipos de datos archivados. Para obtener más información, vea [Configurar Skype para Business Server usar el archivado de Exchange Server](../deploy/integrate-with-exchange-server/use-exchange-archiving.md).
  
### <a name="topologies-and-components"></a>Topologías y componentes

Los únicos componentes necesarios para la mensajería instantánea (MI) y la presencia son:
  
- Servidores Front-End de la organización (conocidos como un grupo de servidores) o un servidor Standard Edition. Las capacidades de presencia y de mensajería instantánea (MI) siempre se encuentran habilitadas en estos servidores. Para obtener más información sobre las topologías de grupo de servidores Front-End y administración, consulte [administración y una alta disponibilidad de grupo de servidores Front-End](high-availability-and-disaster-recovery/high-availability.md).
    
- Un equilibrador de carga, si se dispone de un grupo de servidores front-end Enterprise Edition.
    
### <a name="supported-collocation"></a>Combinación compatible

La combinación consiste en disponer de un único servidor o grupo de servidores con varios roles. Para obtener información detallada en combinación, vea [Conceptos básicos de la topología de Skype para Business Server](topology-basics/topology-basics.md). 
  

