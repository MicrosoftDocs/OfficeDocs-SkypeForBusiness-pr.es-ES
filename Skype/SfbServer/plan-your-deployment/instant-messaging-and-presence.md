---
title: Planear la mensajería instantánea y la presencia en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 70d2151e-9382-485d-ab14-758597571a74
description: 'Resumen: Aprenda a planificar la mensajería instantánea y la presencia en Skype empresarial Server.'
ms.openlocfilehash: 29026a0b4ef7cce55f155f024efc9ccc84457906
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34297382"
---
# <a name="plan-for-instant-messaging-and-presence-in-skype-for-business-server"></a>Planear la mensajería instantánea y la presencia en Skype empresarial Server
 
**Resumen:** Aprenda a planificar la mensajería instantánea y la presencia en Skype empresarial Server.
  
Planear la mensajería instantánea y la presencia en Skype empresarial Server. Para obtener información sobre las opciones de implementación específicas, como habilitar o deshabilitar la mensajería instantánea sin conexión (mi), consulte [implementar la mensajería instantánea y la presencia en Skype empresarial Server](../deploy/im-and-presence/im-and-presence.md).
  
## <a name="plan-for-instant-messaging-and-presence-in-skype-for-business-server"></a>Planear la mensajería instantánea y la presencia en Skype empresarial Server

Los servidores front-end proporcionan funciones básicas de Skype empresarial Server, como la mensajería instantánea (mi) y la presencia, y se incluyen en todas las implementaciones de Skype empresarial Server. Hay dos ediciones disponibles: Skype empresarial Server Enterprise Edition, diseñado principalmente para organizaciones más grandes, y Skype empresarial Server Standard Edition, diseñado principalmente para organizaciones pequeñas que quieren un menor inversión en hardware y no requiere opciones de alta disponibilidad completas. Ambas ediciones admiten todas las cargas de trabajo de Skype empresarial Server incluidas la mensajería instantánea, presencia, Conferencia y telefonía IP empresarial.
  
La mensajería instantánea (MI) permite a los usuarios comunicarse entre sí en tiempo real desde sus equipos y por medio de mensajes basados en texto. Se admiten sesiones de mensajería instantánea con dos participantes y con varios participantes. Un participante de una conversación de mensajería instantánea entre dos participantes puede agregar a la conversación a un tercer participante en cualquier momento. Cuando esto ocurre, la ventana Conversación cambia para admitir características de conferencia.
  
La presencia proporciona información a los usuarios sobre el estado de los otros usuarios en la red. El estado de presencia de un usuario proporciona información para ayudar a otros usuarios a decidir si deben intentar ponerse en contacto con el usuario y si usar la mensajería instantánea, el teléfono o el correo electrónico. El estado de presencia fomenta la comunicación instantánea cada vez que sea posible, pero también proporciona información sobre si un usuario está en una reunión o fuera de la oficina, indicando que la comunicación instantánea no es posible. Este estado de presencia se visualiza como un icono de presencia en Skype Empresarial y otras aplicaciones con detección de presencia, incluido el cliente de colaboración y la mensajería de Microsoft Outlook, las tecnologías de Microsoft SharePoint y Microsoft Office. El icono de presencia representa la disponibilidad actual del usuario y su disposición para comunicarse. 
  
### <a name="technical-requirements"></a>Requisitos técnicos

La mensajería instantánea (MI) y la presencia siempre se ejecutan en los grupos de servidores front-end Enterprise Edition y en los servidores Standard Edition. Para obtener información sobre hardware, sistemas operativos y software de base de datos admitidos, consulte [puertas de enlace certificadas](../../SfbPartnerCertification/certification/infra-gateways.md), [requisitos para el entorno de Skype empresarial 2015](requirements-for-your-environment/requirements-for-your-environment.md)y [requisitos de infraestructura para Skype empresarial Server 2019 ](../../SfBServer2019/plan/system-requirements.md).
  
### <a name="enabling-communication-with-external-users"></a>Habilitar la comunicación con los usuarios externos

Puede aumentar enormemente los beneficios de su inversión en Skype empresarial Server al permitir que los usuarios se comuniquen con usuarios externos. Entre los usuarios externos se pueden incluir:
  
- Usuarios remotos: los usuarios de su organización, cuando trabajan fuera de los firewalls y usan sus equipos portátiles u otros dispositivos de Skype empresarial Server.
    
- Usuarios federados: usuarios de empresas con las que trabaja y que también ejecutan Skype empresarial Server. Si desea habilitar a sus usuarios para que se pongan en contacto fácilmente con estos otros usuarios, cree relaciones federadas con estas compañías. 
    
- Usuarios de Skype: los usuarios de Skype Empresarial pueden ponerse en contacto con cientos de millones de usuarios en Skype por medio de la mensajería instantánea, la voz y el vídeo.
    
> [!NOTE]
> AOL, Yahoo y Google Talk ya no son compatibles. 
  
> [!NOTE]
> Para habilitar cualquiera de estos escenarios o todos ellos, debe implementar un servidor perimetral que le ayude a habilitar las comunicaciones seguras entre su implementación de Skype empresarial Server y los usuarios externos. Los usuarios remotos de su organización y los usuarios de las organizaciones federadas podrán ver la presencia de los demás y comunicarse mediante mensajería instantánea. 
  
> [!NOTE]
> El protocolo de presencia y mensajería extensible (XMPP) es únicamente compatible con los escenarios de certificación de Unified Capabilities Collaboration Platform (UCCP) y Joint Interoperability Test Command (JITC). 
  
### <a name="archiving-im-content"></a>Archivar el contenido de la mensajería instantánea

Skype empresarial Server proporciona características que puede usar si su organización debe cumplir con las normas de cumplimiento. Puede usar el servidor de archivado para archivar el contenido de los mensajes de MI de todos los usuarios de la organización, o solamente de algunos específicos. Para obtener más información, consulte [planear el archivado en Skype empresarial Server](archiving/archiving.md). 
  
Si también ha implementado Microsoft Exchange Server 2013, puede integrar el archivado de datos de Exchange con el archivado de los datos de Skype empresarial Server y usar una única herramienta para buscar en los dos tipos de datos archivados. Para obtener más información, vea [configurar Skype empresarial Server para usar el archivado de Exchange Server](../deploy/integrate-with-exchange-server/use-exchange-archiving.md).
  
### <a name="topologies-and-components"></a>Topologías y componentes

Los únicos componentes necesarios para la mensajería instantánea (MI) y la presencia son:
  
- Los servidores front-end de su organización (conocidos como un grupo) o un servidor Standard Edition. Las capacidades de presencia y de mensajería instantánea (MI) siempre se encuentran habilitadas en estos servidores. Para obtener más información sobre las topologías y la administración del grupo de servidores front-end, consulte [alta disponibilidad y administración de la aplicación front end](high-availability-and-disaster-recovery/high-availability.md).
    
- Un equilibrador de carga, si se dispone de un grupo de servidores front-end Enterprise Edition.
    
### <a name="supported-collocation"></a>Combinación compatible

La combinación consiste en disponer de un único servidor o grupo de servidores con varios roles. Para obtener más información sobre collocation, consulte [aspectos básicos de la topología de Skype empresarial Server](topology-basics/topology-basics.md). 
  

