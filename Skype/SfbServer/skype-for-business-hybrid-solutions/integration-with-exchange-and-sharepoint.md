---
title: Integración con Exchange y SharePoint
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/13/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- Ent_O365_Hybrid_Top
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 5d456d6c-ad71-420c-b6d8-4d9cd0324f86
description: 'Resumen: Conozca Skype para la integración de Business Server 2015 con Exchange y SharePoint.'
ms.openlocfilehash: 3031fa042a25895c7b398d88d1ff62b1b023b2e8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33919335"
---
# <a name="integration-with-exchange-and-sharepoint"></a>Integración con Exchange y SharePoint

**Resumen:** Obtenga información acerca de Skype para la integración de Business Server 2015 con Exchange y SharePoint.

Puede configurar Skype para las implementaciones empresariales Server 2015 para la integración con Microsoft Exchange Server 2016, Microsoft Exchange Server 2013, Microsoft Exchange Server 2010 y SharePoint Server, tanto local y en línea. Las características que se indican en la tabla siguiente son compatibles con todos los clientes, a menos que se indique lo contrario. Para obtener más información acerca del cliente admite, vea [comparación de características de cliente de escritorio de Skype para la empresa](../plan-your-deployment/clients-and-devices/desktop-feature-comparison.md) y Skype para tablas de comparación de cliente en línea de negocio en [los clientes de Skype para profesionales en línea](https://go.microsoft.com/fwlink/p/?LinkId=281902).

## <a name="integration-with-exchange-server"></a>Integración con Exchange Server

Las siguientes tablas enumeran las características admitidas en una implementación híbrida cuando se integra con Microsoft Exchange Server.

 **Skype para Business Server local y Exchange local**


|**Característica**|**Notas**|
|:-----|:-----|
|Mensajería instantánea y presencia en Outlook  <br/> |Para obtener más información, vea [mensajería instantánea y presencia](https://technet.microsoft.com/library/6a93ae95-3b64-410b-ab72-74dea232f065.aspx).  <br/> |
|Programar y unirse a reuniones en línea a través de Outlook  <br/> |Para obtener más información, vea [Integrar Skype para profesionales de 2015 servidor con Exchange Server](../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md).  <br/> |
|Mensajería instantánea y presencia en Outlook Web App  <br/> |Para obtener más información, vea [Configure un entorno híbrido de Skype para Business Server 2015](../manage/authentication/configure-a-hybrid-environment.md).  <br/> |
|Programar y unirse a reuniones en línea a través de Outlook Web App  <br/> ||
|Mensajería instantánea y presencia en clientes móviles  <br/> ||
|Unirse a reuniones en línea en clientes móviles  <br/> |Para obtener más información, vea [Implementación de movilidad](https://technet.microsoft.com/library/f41e6b25-d2cd-43fd-a17b-22cfda8bcd4f.aspx).  <br/> |
|Publicar el estado según la información de disponibilidad del calendario de Outlook  <br/> ||
|Lista de contactos (por medio del almacén de contactos unificado)  <br/> |Requiere Exchange 2016 o Exchange 2013.  <br/> Se requiere un Lync 2013 o Skype para el cliente de escritorio empresarial.  <br/>  Para obtener más información, vea [Configurar Skype para Business Server 2015 usar el almacén de contactos unificados](../deploy/integrate-with-exchange-server/use-the-unified-contact-store.md).  <br/> |
|Alta resolución foto del contacto en el cliente Lync 2013, Skype para clientes empresariales y Lync Web App.  <br/> |Requiere Exchange 2016 o Exchange 2013.  <br/> Para obtener más información, vea [Configurar el uso de fotografías de alta resolución en Skype para Business Server 2015](../deploy/integrate-with-exchange-server/high-resolution-photos.md).  <br/> Fotos en el Skype para la aplicación empresarial para MAC y Mobile, integración entre Skype para Business Server 2015 y Exchange Server debe establecerse tal como se describe en [configurar las aplicaciones de socio en Skype para Business Server y Exchange Server](../deploy/integrate-with-exchange-server/configure-partner-applications.md). <br/> |
|Delegación de reuniones  <br/> |Se admite solo cuando ambos usuarios están hospedados en línea en el mismo bosque o ambos están hospedados localmente. Para obtener más información, vea [Skype para soluciones híbridas de negocio](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/skype-for-business-hybrid-solutions). <br/> |
|Registros de llamadas y el historial de conversaciones perdidas se escriben en el buzón de exchange del usuario  <br/> ||
|Contenido de archivado (mensajería instantánea y reuniones) en Exchange  <br/> |Requiere Exchange 2016 o Exchange 2013.  <br/> Para obtener más información, vea [Lista de comprobación de implementación para el archivado](https://technet.microsoft.com/library/7479734d-be01-40d9-ad82-320a09d19d04.aspx).  <br/> |
|Buscar contenido archivado  <br/> |Requiere Exchange 2016 o Exchange 2013.  <br/> |
|Correo de voz  <br/> |Para obtener más información, vea [Implementación local mensajería unificada de Exchange para proporcionar de correo de voz de Lync Server 2013](https://technet.microsoft.com/library/9673bd73-a3a3-425d-870f-04d801c6d0d5.aspx).  <br/> |

 **Skype para Business Server local y Exchange Online**


|**Característica**|**Notas**|
|:-----|:-----|
|Mensajería instantánea y presencia en Outlook  <br/> |Para obtener más información, vea [Configurar la integración entre local Skype para Business Server 2015 y Outlook Web App](../deploy/integrate-with-exchange-server/outlook-web-app.md) <br/> |
|Programar y unirse a reuniones en línea a través de Outlook  <br/> ||
|Mensajería instantánea y presencia en Outlook Web App  <br/> |Para obtener más información, vea [Configurar la integración entre local Skype para Business Server 2015 y Outlook Web App](../deploy/integrate-with-exchange-server/outlook-web-app.md) <br/> |
|Programar y unirse a reuniones en línea desde Outlook Web App  <br/> |Para obtener más información, vea [Configurar la integración entre local Skype para Business Server 2015 y Outlook Web App](../deploy/integrate-with-exchange-server/outlook-web-app.md) <br/> |
|Mensajería instantánea y presencia en clientes móviles  <br/> ||
|Unirse a reuniones en línea en clientes móviles  <br/> ||
|Publicar el estado según la información de disponibilidad del calendario de Outlook  <br/> ||
|Lista de contactos (por medio del almacén de contactos unificado).  <br/> |Lync Server 2013. Se requiere un Lync 2013 o Skype para el cliente de escritorio empresarial.  <br/> Para obtener más información, vea [Configurar Skype para Business Server 2015 usar el almacén de contactos unificados](../deploy/integrate-with-exchange-server/use-the-unified-contact-store.md) <br/> |
|Alta resolución foto del contacto en el cliente Lync 2013, Skype para clientes empresariales y Lync Web App.  <br/> |Para obtener más información, vea [Configurar el uso de fotografías de alta resolución en Skype para Business Server 2015](../deploy/integrate-with-exchange-server/high-resolution-photos.md).  <br/> Fotos en el Skype para la aplicación empresarial para MAC y Mobile, integración entre Skype para Business Server 2015 y Exchange Server debe establecerse tal como se describe en [Configurar la integración entre local Skype para Business Server y Outlook Web App](../deploy/integrate-with-exchange-server/outlook-web-app.md). <br/> |
|Delegación de reuniones  <br/> |Se admite solo cuando ambos usuarios están hospedados en línea en el mismo bosque o ambos están hospedados localmente. Para obtener más información, vea [Skype para soluciones híbridas de negocio](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/skype-for-business-hybrid-solutions). <br/> |
|Registros de llamadas y el historial de conversaciones perdidas se escriben en el buzón de Exchange del usuario  <br/> ||
|Contenido de archivado (mensajería instantánea y reuniones) en Exchange  <br/> |Para obtener más información, vea [Lista de comprobación de implementación para el archivado](https://technet.microsoft.com/library/7479734d-be01-40d9-ad82-320a09d19d04.aspx).  <br/> |
|Buscar contenido archivado  <br/> |Para obtener más información, consulte en [Configurar Exchange para el centro de exhibición de documentos electrónicos de SharePoint](https://go.microsoft.com/fwlink/p/?LinkId=285448) <br/> |
|Correo de voz  <br/> |Para obtener más información, vea [Proporcionar Lync Server 2013 los usuarios de correo de voz en hospedado mensajería unificada de Exchange](https://technet.microsoft.com/library/306d3fb5-231b-4f0b-b8d8-0d9083b5ed77.aspx).  <br/> |

 **Skype para profesionales en línea y de Exchange local**


|**Característica**|**Notas**|
|:-----|:-----|
|Presencia en Outlook  <br/> ||
|Responder a través de MI, llamadas RTC, llamadas de Skype o videollamadas desde un correo electrónico de Outlook  <br/> ||
|Programar y unirse a reuniones en línea a través de Outlook  <br/> ||
|Mensajería instantánea y presencia en clientes móviles  <br/> ||
|Unirse a reuniones en línea en clientes móviles  <br/> ||
|Publicar el estado según la información de disponibilidad del calendario de Outlook  <br/> ||
|Registros de llamadas y el historial de conversaciones perdidas se escriben en el buzón de exchange del usuario  <br/> ||
|Fotografías de alta resolución contacto en Lync 2013 o Skype para clientes empresariales.  <br/> |Requiere Exchange 2016 o Exchange 2013. No se admite en Lync Web App cuando los usuarios están hospedados en Skype para profesionales en línea.  <br/> |
|Delegación de reuniones  <br/> |Se admite solo cuando ambos usuarios están hospedados en línea en el mismo bosque o ambos están hospedados localmente. Para obtener más información, vea [Skype para soluciones híbridas de negocio](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/skype-for-business-hybrid-solutions). <br/> |
|Registros de llamadas y el historial de conversaciones perdidas se escriben en el buzón de Exchange del usuario  <br/> ||
|Historial de conversaciones en el servidor  <br/> ||

 **Skype para la empresa en línea y Exchange Online**


|**Característica**|**Notas**|
|:-----|:-----|
|Mensajería instantánea y presencia en Outlook  <br/> ||
|Programar y unirse a reuniones en línea a través de Outlook  <br/> ||
|Mensajería instantánea y presencia en Outlook Web App  <br/> ||
|Programar y unirse a reuniones en línea desde Outlook Web App  <br/> ||
|Mensajería instantánea y presencia en clientes móviles  <br/> ||
|Unirse a reuniones en línea en clientes móviles  <br/> ||
|Publicar el estado según la información de disponibilidad del calendario de Outlook  <br/> ||
|Registros de llamadas y el historial de conversaciones perdidas se escriben en el buzón de exchange del usuario  <br/> ||
|Lista de contactos (por medio del almacén de contactos unificado)  <br/> |Lync Server 2013 o Skype para clientes empresariales necesarios  <br/> |
|Fotografías de alta resolución contacto en Lync 2013, Skype para clientes empresariales y Lync Web App  <br/> ||
|Delegación de reuniones  <br/> |Se admite solo cuando ambos usuarios están hospedados en línea en el mismo bosque o ambos están hospedados localmente. Para obtener más información, vea [Skype para soluciones híbridas de negocio](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/skype-for-business-hybrid-solutions). <br/> |
|Contenido de archivado (mensajería instantánea y reuniones) en Exchange  <br/> ||
|Buscar contenido archivado  <br/> ||
|Correo de voz  <br/> ||

## <a name="integration-with-sharepoint"></a>Integración con SharePoint

En la siguiente tabla se enumera las características admitidas en una implementación híbrida cuando integrado con SharePoint.

||**SharePoint local**|**SharePoint Online**|
|:-----|:-----|:-----|
|**Skype para Business Server 2015 local** <br/> | Búsqueda de aptitudes <br/>  Presencia en SharePoint <br/> | Presencia en SharePoint <br/> |
|**Skype Empresarial Online** <br/> | Presencia en SharePoint <br/> | Presencia en SharePoint <br/> |


