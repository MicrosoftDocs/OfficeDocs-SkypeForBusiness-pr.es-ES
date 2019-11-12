---
title: Integración con Exchange y SharePoint
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/13/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- Ent_O365_Hybrid_Top
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
- SPO_Content
ms.custom: ''
ms.assetid: 5d456d6c-ad71-420c-b6d8-4d9cd0324f86
description: 'Resumen: Obtenga información sobre la integración de Skype empresarial Server 2015 con Exchange y SharePoint.'
ms.openlocfilehash: 18839125faee2dfd27ad3843e37b723f56581ff3
ms.sourcegitcommit: ddb4eaf634476680494025a3aa1c91d15fb58413
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/11/2019
ms.locfileid: "38231151"
---
# <a name="integration-with-exchange-and-sharepoint"></a>Integración con Exchange y SharePoint

**Resumen:** Obtenga más información sobre la integración de Skype empresarial Server 2015 con Exchange y SharePoint.

Puede configurar las implementaciones de Skype empresarial Server 2015 para la integración con Microsoft Exchange Server 2016, Microsoft Exchange Server 2013, Microsoft Exchange Server 2010 y SharePoint Server, tanto local como en línea. Las características que se indican en la tabla siguiente son compatibles con todos los clientes, a menos que se indique lo contrario. Para obtener más información sobre la compatibilidad del cliente, vea [comparación de características de cliente de escritorio](../plan-your-deployment/clients-and-devices/desktop-feature-comparison.md) en las tablas de comparación de clientes de Skype empresarial y Skype empresarial online en [clientes de Skype empresarial online](https://go.microsoft.com/fwlink/p/?LinkId=281902).

## <a name="integration-with-exchange-server"></a>Integración con Exchange Server

En las siguientes tablas se enumeran las características compatibles con una implementación híbrida cuando se integra con Microsoft Exchange Server.

 **Skype empresarial Server local y Exchange local**


|**Característica**|**Notas**|
|:-----|:-----|
|Mensajería instantánea y presencia en Outlook  <br/> |Para obtener más información, consulte [mensajería instantánea y presencia](https://technet.microsoft.com/library/6a93ae95-3b64-410b-ab72-74dea232f065.aspx).  <br/> |
|Programar y unirse a reuniones en línea a través de Outlook  <br/> |Para obtener más información, consulte [integrar Skype empresarial server 2015 con Exchange Server](../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md).  <br/> |
|Mensajería instantánea en Outlook Web App  <br/> |Para obtener más información, vea [configurar un entorno híbrido en Skype empresarial Server 2015](../manage/authentication/configure-a-hybrid-environment.md).  <br/> |
|Programar y unirse a reuniones en línea a través de Outlook Web App  <br/> ||
|Mensajería instantánea y presencia en clientes móviles  <br/> ||
|Unirse a reuniones en línea en clientes móviles  <br/> |Para obtener más información, consulte [implementación de movilidad](https://technet.microsoft.com/library/f41e6b25-d2cd-43fd-a17b-22cfda8bcd4f.aspx).  <br/> |
|Publicar el estado según la información de disponibilidad del calendario de Outlook  <br/> ||
|Lista de contactos (por medio del almacén de contactos unificado)  <br/> |Requiere Exchange 2016 o Exchange 2013.  <br/> Se necesita un cliente de escritorio de Lync 2013 o Skype empresarial.  <br/>  Para obtener más información, consulte [configurar Skype empresarial Server 2015 para usar el almacén de contactos unificado](../deploy/integrate-with-exchange-server/use-the-unified-contact-store.md).  <br/> |
|Foto de contacto de alta resolución en el cliente de Lync 2013, el cliente de Skype empresarial y Lync Web App.  <br/> |Requiere Exchange 2016 o Exchange 2013.  <br/> Para obtener más información, consulte [configurar el uso de fotos de alta resolución en Skype empresarial Server 2015](../deploy/integrate-with-exchange-server/high-resolution-photos.md).  <br/> Para las fotos de la aplicación de Skype empresarial para MAC y Mobile, la integración entre Skype empresarial Server 2015 y Exchange Server se debe configurar como se describe en [Configurar aplicaciones de socio en Skype empresarial Server y en Exchange Server](../deploy/integrate-with-exchange-server/configure-partner-applications.md). <br/> |
|Delegación de reuniones  <br/> |Se admite solo cuando ambos usuarios están hospedados en línea en el mismo bosque o ambos están hospedados localmente. Para obtener más información, consulte [soluciones híbridas de Skype empresarial](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/skype-for-business-hybrid-solutions). <br/> |
|El historial de conversaciones perdidas y los registros de llamadas se escriben en el buzón de Exchange del usuario  <br/> ||
|Contenido de archivado (mensajería instantánea y reuniones) en Exchange  <br/> |Requiere Exchange 2016 o Exchange 2013.  <br/> Para obtener más información, vea [lista de comprobación de la implementación para archivar](https://technet.microsoft.com/library/7479734d-be01-40d9-ad82-320a09d19d04.aspx).  <br/> |
|Buscar contenido archivado  <br/> |Requiere Exchange 2016 o Exchange 2013.  <br/> |
|Correo de voz  <br/> |Para obtener más información, consulte [implementar la mensajería unificada de Exchange local para proporcionar el correo de voz de Lync Server 2013](https://technet.microsoft.com/library/9673bd73-a3a3-425d-870f-04d801c6d0d5.aspx).  <br/> |

 **Skype empresarial Server local y Exchange Online**


|**Característica**|**Notas**|
|:-----|:-----|
|Mensajería instantánea y presencia en Outlook  <br/> |Para obtener más información, consulte [configurar la integración entre Skype empresarial local Server 2015 y Outlook Web App](../deploy/integrate-with-exchange-server/outlook-web-app.md) <br/> |
|Programar y unirse a reuniones en línea a través de Outlook  <br/> ||
|Mensajería instantánea en Outlook Web App  <br/> |Para obtener más información, consulte [configurar la integración entre Skype empresarial local Server 2015 y Outlook Web App](../deploy/integrate-with-exchange-server/outlook-web-app.md) <br/> |
|Programar y unirse a la reunión en línea desde Outlook Web App  <br/> |Para obtener más información, consulte [configurar la integración entre Skype empresarial local Server 2015 y Outlook Web App](../deploy/integrate-with-exchange-server/outlook-web-app.md) <br/> |
|Mensajería instantánea y presencia en clientes móviles  <br/> ||
|Unirse a reuniones en línea en clientes móviles  <br/> ||
|Publicar el estado según la información de disponibilidad del calendario de Outlook  <br/> ||
|Lista de contactos (por medio del almacén de contactos unificado).  <br/> |Solo Lync Server 2013. Se necesita un cliente de escritorio de Lync 2013 o Skype empresarial.  <br/> Para obtener más información, consulte [configurar Skype empresarial Server 2015 para usar el almacén de contactos unificado](../deploy/integrate-with-exchange-server/use-the-unified-contact-store.md) <br/> |
|Foto de contacto de alta resolución en el cliente de Lync 2013, el cliente de Skype empresarial y Lync Web App.  <br/> |Para obtener más información, consulte [configurar el uso de fotos de alta resolución en Skype empresarial Server 2015](../deploy/integrate-with-exchange-server/high-resolution-photos.md).  <br/> Para las fotos de la aplicación de Skype empresarial para MAC y Mobile, la integración entre Skype empresarial Server 2015 y Exchange Server debe estar configurada según se describe en [configurar la integración entre Skype empresarial Server local y Outlook Web App](../deploy/integrate-with-exchange-server/outlook-web-app.md). <br/> |
|Delegación de reuniones  <br/> |Se admite solo cuando ambos usuarios están hospedados en línea en el mismo bosque o ambos están hospedados localmente. Para obtener más información, consulte [soluciones híbridas de Skype empresarial](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/skype-for-business-hybrid-solutions). <br/> |
|El historial de conversaciones perdidas y los registros de llamadas se escriben en el buzón de Exchange del usuario  <br/> ||
|Contenido de archivado (mensajería instantánea y reuniones) en Exchange  <br/> |Para obtener más información, vea [lista de comprobación de la implementación para archivar](https://technet.microsoft.com/library/7479734d-be01-40d9-ad82-320a09d19d04.aspx).  <br/> |
|Buscar contenido archivado  <br/> |Para obtener más información, consulte [configurar Exchange para el centro de exhibición de SharePoint](https://go.microsoft.com/fwlink/p/?LinkId=285448) <br/> |
|Correo de voz  <br/> |Para obtener más información, consulte [proporcionar a los usuarios de Lync Server 2013 correo de voz en mensajería unificada de Exchange hospedado](https://technet.microsoft.com/library/306d3fb5-231b-4f0b-b8d8-0d9083b5ed77.aspx).  <br/> |

 **Skype empresarial online y Exchange local**


|**Característica**|**Notas**|
|:-----|:-----|
|Presencia en Outlook  <br/> ||
|Responder a través de MI, llamadas RTC, llamadas de Skype o videollamadas desde un correo electrónico de Outlook  <br/> ||
|Programar y unirse a reuniones en línea a través de Outlook  <br/> ||
|Mensajería instantánea y presencia en clientes móviles  <br/> ||
|Unirse a reuniones en línea en clientes móviles  <br/> ||
|Publicar el estado según la información de disponibilidad del calendario de Outlook  <br/> ||
|El historial de conversaciones perdidas y los registros de llamadas se escriben en el buzón de Exchange del usuario  <br/> ||
|Foto de contacto de alta resolución en Lync 2013 o cliente de Skype empresarial.  <br/> |Requiere Exchange 2016 o Exchange 2013. Este no es compatible con Lync Web App cuando los usuarios están alojados en Skype empresarial online.  <br/> |
|Delegación de reuniones  <br/> |Se admite solo cuando ambos usuarios están hospedados en línea en el mismo bosque o ambos están hospedados localmente. Para obtener más información, consulte [soluciones híbridas de Skype empresarial](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/skype-for-business-hybrid-solutions). <br/> |
|El historial de conversaciones perdidas y los registros de llamadas se escriben en el buzón de Exchange del usuario  <br/> ||
|Historial de conversaciones en el servidor  <br/> ||

 **Skype empresarial online y Exchange Online**


|**Característica**|**Notas**|
|:-----|:-----|
|Mensajería instantánea y presencia en Outlook  <br/> ||
|Programar y unirse a reuniones en línea a través de Outlook  <br/> ||
|Mensajería instantánea en Outlook Web App  <br/> ||
|Programar y unirse a la reunión en línea desde Outlook Web App  <br/> ||
|Mensajería instantánea y presencia en clientes móviles  <br/> ||
|Unirse a reuniones en línea en clientes móviles  <br/> ||
|Publicar el estado según la información de disponibilidad del calendario de Outlook  <br/> ||
|El historial de conversaciones perdidas y los registros de llamadas se escriben en el buzón de Exchange del usuario  <br/> ||
|Lista de contactos (por medio del almacén de contactos unificado)  <br/> |Lync Server 2013 o cliente de Skype empresarial requerido  <br/> |
|Foto de contacto de alta resolución en Lync 2013, cliente de Skype empresarial y Lync Web App  <br/> ||
|Delegación de reuniones  <br/> |Se admite solo cuando ambos usuarios están hospedados en línea en el mismo bosque o ambos están hospedados localmente. Para obtener más información, consulte [soluciones híbridas de Skype empresarial](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/skype-for-business-hybrid-solutions). <br/> |
|Contenido de archivado (mensajería instantánea y reuniones) en Exchange  <br/> ||
|Buscar contenido archivado  <br/> ||
|Correo de voz  <br/> ||

## <a name="integration-with-sharepoint"></a>Integración con SharePoint

En la siguiente tabla se enumeran las características compatibles con una implementación híbrida cuando se integra con SharePoint.

||**SharePoint local**|**SharePoint Online**|
|:-----|:-----|:-----|
|**Skype empresarial Server 2015 local** <br/> | Búsqueda de aptitudes <br/>  Presencia en SharePoint <br/> | Presencia en SharePoint <br/> |
|**Skype Empresarial Online** <br/> | Presencia en SharePoint <br/> | Presencia en SharePoint <br/> |


