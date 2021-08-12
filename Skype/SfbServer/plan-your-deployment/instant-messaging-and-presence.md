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
ms.openlocfilehash: c58cfbfdc7fbfbdff01b1a122ad5cd94ee6a991ab90b52bf86bb62894e4b72a5
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54284640"
---
# <a name="plan-for-instant-messaging-and-presence-in-skype-for-business-server"></a>Planear la mensajería instantánea y la presencia en Skype Empresarial Server
 
**Resumen:** Obtenga información sobre cómo planear la mensajería instantánea y la presencia en Skype Empresarial Server.
  
Planee la mensajería instantánea y la presencia en Skype Empresarial Server. Para obtener información sobre opciones de implementación específicas, como habilitar o deshabilitar la mensajería instantánea sin conexión (MI), vea [Deploy instant messaging and presence in Skype Empresarial Server](../deploy/im-and-presence/im-and-presence.md).
  
## <a name="plan-for-instant-messaging-and-presence-in-skype-for-business-server"></a>Planear la mensajería instantánea y la presencia en Skype Empresarial Server

Los servidores front-end proporcionan funciones Skype Empresarial Server, como la mensajería instantánea (MI) y la presencia, y se incluyen en todas las Skype Empresarial Server implementación. Hay dos ediciones disponibles: Skype Empresarial Server Enterprise Edition, que está diseñada principalmente para organizaciones más grandes, y Skype Empresarial Server Standard Edition, que está diseñada principalmente para organizaciones más pequeñas que desean una inversión de hardware más pequeña y no requieren opciones de alta disponibilidad completa. Ambas ediciones admiten todas las Skype Empresarial Server de trabajo, incluidas mensajería instantánea, presencia, conferencia y Telefonía IP empresarial.
  
La mensajería instantánea (MI) permite a los usuarios comunicarse entre sí en tiempo real desde sus equipos y mediante mensajes basados en texto. Se admiten sesiones de mensajería instantánea con dos participantes y con varios participantes. Un participante de una conversación de mensajería instantánea entre dos participantes puede agregar a la conversación a un tercer participante en cualquier momento. Cuando esto ocurre, la ventana Conversación cambia para admitir características de conferencia.
  
La presencia proporciona información a los usuarios sobre el estado de otros usuarios en la red. El estado de presencia de un usuario proporciona información para ayudar a otros usuarios a decidir si deben intentar ponerse en contacto con el usuario y si deben usar mensajería instantánea, teléfono o correo electrónico. El estado de presencia fomenta la comunicación instantánea cada vez que sea posible, pero también proporciona información sobre si un usuario está en una reunión o fuera de la oficina, indicando que la comunicación instantánea no es posible. Este estado de presencia se muestra como un icono de presencia en Skype Empresarial y otras aplicaciones para la presencia, incluido el cliente de mensajería y colaboración de Microsoft Outlook, las tecnologías de Microsoft SharePoint y Microsoft Office. El icono de presencia representa la disponibilidad actual del usuario y su disposición a comunicarse. 
  
### <a name="technical-requirements"></a>Requisitos técnicos

La mensajería instantánea (MI) y la presencia siempre se ejecutan en Enterprise Edition servidores front-end y Standard Edition cliente. Para obtener información sobre el hardware, los sistemas operativos y el software de base de datos [admitidos,](../../SfbPartnerCertification/certification/infra-gateways.md)vea Certified Gateways , [Requirements for your Skype Empresarial 2015 environment](requirements-for-your-environment/requirements-for-your-environment.md)y Infrastructure requirements for Skype Empresarial Server [2019](../../SfBServer2019/plan/system-requirements.md).
  
### <a name="enabling-communication-with-external-users"></a>Habilitar la comunicación con usuarios externos

Puede aumentar considerablemente las ventajas de su inversión en Skype Empresarial Server permitir que los usuarios se comuniquen con usuarios externos. Entre los usuarios externos se pueden incluir:
  
- Usuarios remotos: los propios usuarios de la organización, cuando trabajan fuera de los firewalls y usan sus equipos portátiles u otros Skype Empresarial Server dispositivos.
    
- Usuarios federados: usuarios de empresas con las que trabaja que también ejecutan Skype Empresarial Server. Para habilitar a sus usuarios para que se pongan en contacto fácilmente con estos usuarios, cree relaciones federadas con estas compañías. 
    
- Skype usuarios: Skype Empresarial usuarios pueden llegar a los cientos de millones de usuarios en Skype con mensajería instantánea, voz y vídeo.
    
> [!NOTE]
> AOL, Yahoo y Google Talk ya no son compatibles. 
  
> [!NOTE]
> Para habilitar cualquiera o todos estos escenarios, debe implementar un servidor perimetral para ayudar a habilitar las comunicaciones seguras entre la implementación Skype Empresarial Server y los usuarios externos. Los usuarios remotos y los usuarios de la organización en organizaciones federadas podrán ver la presencia del otro y comunicarse mediante mensajería instantánea. 
  
> [!NOTE]
> El Protocolo extensible de mensajería y presencia (XMPP) solo es compatible con escenarios de certificación del Comando conjunto de pruebas de interoperabilidad (JITC) de la Plataforma de colaboración de capacidades unificadas (UCCP). 
  
### <a name="archiving-im-content"></a>Archivado de contenido de mensajería instantánea

Skype Empresarial Server proporciona características que puede usar si su organización debe seguir las normativas de cumplimiento. Puede usar el archivado para archivar el contenido de los mensajes de mensajería instantánea para todos los usuarios de la organización o solo para determinados usuarios que especifique. Para obtener más información, vea [Plan for archiving in Skype Empresarial Server](archiving/archiving.md). 
  
Si también ha implementado Microsoft Exchange Server 2013, puede integrar el archivado de datos de Exchange con el archivado de datos de Skype Empresarial Server y usar una sola herramienta para buscar en ambos tipos de datos archivados. Para obtener más información, vea [Configure Skype Empresarial Server to use Exchange Server archiving](../deploy/integrate-with-exchange-server/use-exchange-archiving.md).
  
### <a name="topologies-and-components"></a>Topologías y componentes

Los únicos componentes necesarios para la mensajería instantánea (MI) y la presencia son:
  
- Los servidores front-end de la organización (conocidos como un grupo de servidores) o un servidor Standard Edition cliente. Las capacidades de mensajería instantánea y presencia siempre están habilitadas en estos servidores. Para obtener más información sobre las topologías y la administración de grupos de servidores [front-end,](high-availability-and-disaster-recovery/high-availability.md)vea Front End Pool high availability and management .
    
- Un equilibrador de carga, si tiene un grupo Enterprise Edition front-end.
    
### <a name="supported-collocation"></a>Colocación compatible

La colocación se define como tener un único servidor o grupo de servidores con varios roles instalados. Para obtener más información sobre la colocación, vea [Topology Basics for Skype Empresarial Server](topology-basics/topology-basics.md). 
  

