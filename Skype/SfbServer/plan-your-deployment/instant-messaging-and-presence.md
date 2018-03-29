---
title: Planificar la presencia y la mensajería instantánea en Skype Empresarial Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 6/28/2016
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 70d2151e-9382-485d-ab14-758597571a74
description: 'Resumen: Conozca cómo planear para mensajería instantánea y presencia en Skype Business Server 2015.'
ms.openlocfilehash: 1934f0308cda59b52073c47d1652ad2286bd6977
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="plan-for-instant-messaging-and-presence-in-skype-for-business-server-2015"></a>Planificar la presencia y la mensajería instantánea en Skype Empresarial Server 2015
 
**Resumen:** información sobre cómo planificar la mensajería instantánea y la presencia en Skype Empresarial Server 2015.
  
Planifique la presencia y la mensajería instantánea en Skype Empresarial Server 2015. Para obtener información acerca de las opciones de implementación específicas, como habilitar o deshabilitar sin conexión mensajería instantánea (IM), vea [implementación de mensajería instantánea y presencia en Skype para Business Server 2015](../deploy/im-and-presence/im-and-presence.md).
  
## <a name="plan-for-instant-messaging-and-presence-in-skype-for-business-server-2015"></a>Planificar la presencia y la mensajería instantánea en Skype Empresarial Server 2015

Frontal servidores proporcionan básicas de Skype para funcionalidad de Business Server como mensajería instantánea (IM) y presencia y se incluyen en cada Skype para la implementación de Business Server. Existen dos ediciones disponibles: Skype para Business Server Enterprise Edition, que está diseñado principalmente para las organizaciones más grandes, y Skype para Business Server Standard Edition, que está diseñado principalmente para organizaciones más pequeñas que desee un menor inversión en hardware y no requieren opciones completa de alta disponibilidad. Ambas ediciones admiten todos los Skype para cargas de trabajo de servidor empresarial incluida mensajería instantánea, presencia, conferencias y Telefonía IP empresarial.
  
La mensajería instantánea (MI) permite a los usuarios comunicarse entre sí en tiempo real desde sus equipos y por medio de mensajes basados en texto. Se admiten sesiones de mensajería instantánea con dos participantes y con varios participantes. Un participante de una conversación de mensajería instantánea entre dos participantes puede agregar a la conversación a un tercer participante en cualquier momento. Cuando esto ocurre, la ventana Conversación cambia para admitir características de conferencia.
  
La presencia proporciona información a los usuarios sobre el estado de los otros usuarios en la red. Estado de presencia del usuario proporciona información para ayudar a otros a decidir si debe intentar ponerse en contacto con el usuario y si se utiliza la mensajería instantánea, teléfono o correo electrónico. El estado de presencia fomenta la comunicación instantánea cada vez que sea posible, pero también proporciona información sobre si un usuario está en una reunión o fuera de la oficina, indicando que la comunicación instantánea no es posible. Este estado de presencia se visualiza como un icono de presencia en Skype Empresarial y otras aplicaciones con detección de presencia, incluido el cliente de colaboración y la mensajería de Microsoft Outlook, las tecnologías de Microsoft SharePoint y Microsoft Office. El icono de presencia representa al usuario actual disponibilidad y predisposición de comunicación. 
  
### <a name="technical-requirements"></a>Requisitos técnicos

La mensajería instantánea (MI) y la presencia siempre se ejecutan en los grupos de servidores front-end Enterprise Edition y en los servidores Standard Edition. Para obtener información sobre hardware compatible, sistemas operativos y software de base de datos, vea [infraestructura de Skype para el negocio](https://technet.microsoft.com/en-us/office/dn947483) y los [requisitos para su Skype para el entorno empresarial](requirements-for-your-environment/requirements-for-your-environment.md).
  
### <a name="enabling-communication-with-external-users"></a>Habilitar la comunicación con los usuarios externos

Puede aumentar los beneficios de su inversión considerablemente en Skype Empresarial Server si habilita la comunicación entre sus usuarios y los usuarios externos. Entre los usuarios externos se pueden incluir:
  
- Los usuarios remotos: los usuarios de la organización, cuando están trabajando fuera de los servidores de seguridad y está usando sus equipos portátiles u otro Skype para dispositivos Business Server.
    
- Los usuarios federados: los usuarios de empresas trabaja con quien también ejecutan Skype para Business Server. Si desea habilitar a sus usuarios para que se pongan en contacto fácilmente con estos otros usuarios, cree relaciones federadas con estas compañías. 
    
- Usuarios de Skype: los usuarios de Skype Empresarial pueden ponerse en contacto con cientos de millones de usuarios en Skype por medio de la mensajería instantánea, la voz y el vídeo.
    
> [!NOTE]
> AOL, Yahoo y Google Talk ya no son compatibles. 
  
> [!NOTE]
> Para habilitar uno de estos escenarios, o todos, es preciso implementar un servidor perimetral que facilite la habilitación de comunicaciones seguras entre la implementación de Skype Empresarial Server y los usuarios externos. Los usuarios remotos y los usuarios de organizaciones federadas de la organización podrán ver la presencia de los demás y comunicarse mediante mensajería instantánea. 
  
> [!NOTE]
> El protocolo de presencia y mensajería extensible (XMPP) es únicamente compatible con los escenarios de certificación de Unified Capabilities Collaboration Platform (UCCP) y Joint Interoperability Test Command (JITC). 
  
### <a name="archiving-im-content"></a>Archivar el contenido de la mensajería instantánea

Skype Empresarial Server proporciona características que se pueden usar si la organización necesita seguir regulaciones de conformidad. Puede usar el archivado para archivar el contenido de los mensajes de mensajería instantánea (MI) de todos los usuarios de la organización, o solamente de algunos específicos. Para más detalles, consulte Planificar el archivado en Skype Empresarial Server 2015 en la documentación de planeación. 
  
Si también ha implementado Microsoft Exchange Server 2013, puede integrar el archivado de los datos de Exchange con el archivado de los datos de Skype Empresarial Server al usar una única herramienta para buscar en ambos tipos de datos archivados. Para obtener más información, consulte Configuración de Skype para Business Server 2015 utilizar el archivado de 2013 de Microsoft Exchange Server.
  
### <a name="topologies-and-components"></a>Topologías y componentes

Son los únicos componentes requeridos para la mensajería instantánea (IM) y presencia:
  
- Servidores de Front-End de su organización (conocidos como un grupo) o un servidor Standard Edition. Las capacidades de presencia y de mensajería instantánea (MI) siempre se encuentran habilitadas en estos servidores. Para obtener más información sobre topologías de grupo de servidores Front-End y administración, consulte [administración y alta disponibilidad de grupo de servidores frontales](high-availability-and-disaster-recovery/high-availability.md).
    
- Un equilibrador de carga, si se dispone de un grupo de servidores front-end Enterprise Edition.
    
### <a name="supported-collocation"></a>Combinación compatible

La combinación consiste en disponer de un único servidor o grupo de servidores con varios roles. Para obtener más información sobre la colocación, consulte [Aspectos básicos de la topología para Skype para Business Server 2015](topology-basics/topology-basics.md). 
  

