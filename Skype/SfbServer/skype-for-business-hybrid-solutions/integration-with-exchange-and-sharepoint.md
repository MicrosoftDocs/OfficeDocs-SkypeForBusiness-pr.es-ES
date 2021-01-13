---
title: Integración con Exchange y SharePoint
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/13/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
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
description: 'Resumen: obtenga información sobre la integración de Skype Empresarial Server 2015 con Exchange y SharePoint.'
ms.openlocfilehash: 943392fbd63238621825edad380ac9c140935635
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821110"
---
# <a name="integration-with-exchange-and-sharepoint"></a>Integración con Exchange y SharePoint

**Resumen:** Obtenga información sobre la integración de Skype Empresarial Server 2015 con Exchange y SharePoint.

Puede configurar las implementaciones de Skype Empresarial Server 2015 para la integración con Microsoft Exchange Server 2016, Microsoft Exchange Server 2013, Microsoft Exchange Server 2010 y SharePoint Server, tanto local como en línea. Las características enumeradas en la tabla siguiente son compatibles con todos los clientes a menos que se especifique lo contrario. Para obtener más información acerca de la compatibilidad con clientes, vea la comparación de características de cliente de escritorio para [Skype](../plan-your-deployment/clients-and-devices/desktop-feature-comparison.md) Empresarial y las tablas de comparación de clientes de Skype Empresarial Online en [Clientes de Skype Empresarial Online.](https://go.microsoft.com/fwlink/p/?LinkId=281902)

## <a name="integration-with-exchange-server"></a>Integración con Exchange Server

En las tablas siguientes se muestran las características admitidas en una implementación híbrida cuando se integran con Microsoft Exchange Server.

 **Skype Empresarial Server local y Exchange local**


|**Característica**|**Notas**|
|:-----|:-----|
|Mensajería instantánea y presencia en Outlook  <br/> |Para obtener más información, vea [MENSAJERÍA instantánea y presencia.](https://technet.microsoft.com/library/6a93ae95-3b64-410b-ab72-74dea232f065.aspx)  <br/> |
|Programar y unirse a una reunión en línea a través de Outlook  <br/> |Para obtener más información, vea [Integrar Skype Empresarial Server 2015 con Exchange Server](../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md).  <br/> |
|Mensajería instantánea y presencia en Outlook Web App  <br/> |Para obtener más información, vea [Configurar un entorno híbrido en Skype Empresarial Server 2015.](../manage/authentication/configure-a-hybrid-environment.md)  <br/> |
|Programar y unirse a una reunión en línea a través de Outlook Web App  <br/> ||
|Mensajería instantánea/presencia en clientes móviles  <br/> ||
|Unirse a reuniones en línea en clientes móviles  <br/> |Para obtener más información, vea [Implementación de movilidad.](https://technet.microsoft.com/library/f41e6b25-d2cd-43fd-a17b-22cfda8bcd4f.aspx)  <br/> |
|Publicar el estado en función de la información de disponibilidad del calendario de Outlook  <br/> ||
|Lista de contactos (a través del almacén de contactos unificado)  <br/> |Requiere Exchange 2016 o Exchange 2013.  <br/> Se requiere un cliente de escritorio de Lync 2013 o Skype Empresarial.  <br/>  Para obtener más información, consulte [Configurar Skype Empresarial Server 2015 para usar el almacén de contactos unificado.](../deploy/integrate-with-exchange-server/use-the-unified-contact-store.md)  <br/> |
|Foto de contacto de alta resolución en el cliente de Lync 2013, el cliente de Skype Empresarial y Lync Web App.  <br/> |Requiere Exchange 2016 o Exchange 2013.  <br/> Para obtener más información, vea Configurar el uso de fotos de alta resolución [en Skype Empresarial Server 2015.](../deploy/integrate-with-exchange-server/high-resolution-photos.md)  <br/> Para las fotos en la aplicación skype empresarial para MAC y móviles, la integración entre Skype Empresarial Server 2015 y Exchange Server debe configurarse como se describe en Configurar aplicaciones de socio en Skype Empresarial [Server y Exchange Server](../deploy/integrate-with-exchange-server/configure-partner-applications.md). <br/> |
|Delegación de reuniones  <br/> |Solo se admite cuando ambos usuarios están en línea en el mismo bosque o ambos se encuentran en el entorno local. Para obtener más información, vea [soluciones híbridas de Skype Empresarial.](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/skype-for-business-hybrid-solutions) <br/> |
|El historial de conversaciones perdidas y los registros de llamadas se escriben en el buzón de exchange del usuario  <br/> ||
|Contenido de archivado (mensajería instantánea y reunión) en Exchange  <br/> |Requiere Exchange 2016 o Exchange 2013.  <br/> Para obtener más información, vea [Lista de comprobación de implementación para archivado.](https://technet.microsoft.com/library/7479734d-be01-40d9-ad82-320a09d19d04.aspx)  <br/> |
|Buscar contenido archivado  <br/> |Requiere Exchange 2016 o Exchange 2013.  <br/> |
|Correo de voz  <br/> |Para obtener más información, consulte Implementación de mensajería unificada de Exchange local para proporcionar correo de voz de [Lync Server 2013.](https://technet.microsoft.com/library/9673bd73-a3a3-425d-870f-04d801c6d0d5.aspx)  <br/> |

 **Skype Empresarial Server local y Exchange Online**


|**Característica**|**Notas**|
|:-----|:-----|
|Mensajería instantánea y presencia en Outlook  <br/> |Para obtener más información, vea Configurar la integración entre [Skype Empresarial Server 2015](../deploy/integrate-with-exchange-server/outlook-web-app.md) local y Outlook Web App <br/> |
|Programar y unirse a una reunión en línea a través de Outlook  <br/> ||
|Mensajería instantánea y presencia en Outlook Web App  <br/> |Para obtener más información, vea Configurar la integración entre [Skype Empresarial Server 2015](../deploy/integrate-with-exchange-server/outlook-web-app.md) local y Outlook Web App <br/> |
|Programar y unirse a una reunión en línea desde Outlook Web App  <br/> |Para obtener más información, vea Configurar la integración entre [Skype Empresarial Server 2015](../deploy/integrate-with-exchange-server/outlook-web-app.md) local y Outlook Web App <br/> |
|Mensajería instantánea y presencia en clientes móviles  <br/> ||
|Unirse a una reunión en línea en clientes móviles  <br/> ||
|Publicar el estado en función de la información de disponibilidad del calendario de Outlook  <br/> ||
|Lista de contactos (a través del almacén de contactos unificado).  <br/> |Solo Lync Server 2013. Se requiere un cliente de escritorio de Lync 2013 o Skype Empresarial.  <br/> Para obtener más información, consulte [Configurar Skype Empresarial Server 2015 para usar el almacén de contactos unificado](../deploy/integrate-with-exchange-server/use-the-unified-contact-store.md) <br/> |
|Foto de contacto de alta resolución en el cliente de Lync 2013, el cliente de Skype Empresarial y Lync Web App.  <br/> |Para obtener más información, vea Configurar el uso de fotos de alta resolución [en Skype Empresarial Server 2015.](../deploy/integrate-with-exchange-server/high-resolution-photos.md)  <br/> Para las fotos en la aplicación skype empresarial para MAC y móviles, la integración entre Skype Empresarial Server 2015 y Exchange Server debe configurarse como se describe en Configurar la integración entre Skype Empresarial Server local y [Outlook Web App.](../deploy/integrate-with-exchange-server/outlook-web-app.md) <br/> |
|Delegación de reuniones  <br/> |Solo se admite cuando ambos usuarios están en línea en el mismo bosque o ambos se encuentran en el entorno local. Para obtener más información, vea [soluciones híbridas de Skype Empresarial.](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/skype-for-business-hybrid-solutions) <br/> |
|El historial de conversaciones perdidas y los registros de llamadas se escriben en el buzón de Exchange del usuario  <br/> ||
|Contenido de archivado (mensajería instantánea y reunión) en Exchange  <br/> |Para obtener más información, vea [Lista de comprobación de implementación para archivado.](https://technet.microsoft.com/library/7479734d-be01-40d9-ad82-320a09d19d04.aspx)  <br/> |
|Buscar contenido archivado  <br/> |Para obtener más información, vea [Configurar Exchange para el Centro de exhibición de documentos](https://go.microsoft.com/fwlink/p/?LinkId=285448) electrónicos de SharePoint <br/> |
|Correo de voz  <br/> |Para obtener más información, consulte Proporcionar correo de voz de usuarios de [Lync Server 2013 en mensajería unificada hospedada de Exchange](https://technet.microsoft.com/library/306d3fb5-231b-4f0b-b8d8-0d9083b5ed77.aspx).  <br/> |

 **Skype Empresarial Online y Exchange local**


|**Característica**|**Notas**|
|:-----|:-----|
|Presencia en Outlook  <br/> ||
|Responder a través de mensajería instantánea, llamada RTC, llamada de Skype o videollamada desde un correo electrónico de Outlook  <br/> ||
|Programar y unirse a reuniones en línea a través de Outlook  <br/> ||
|Mensajería instantánea/presencia en clientes móviles  <br/> ||
|Unirse a reuniones en línea en clientes móviles  <br/> ||
|Publicar el estado en función de la información de disponibilidad del calendario de Outlook  <br/> ||
|El historial de conversaciones perdidas y los registros de llamadas se escriben en el buzón de exchange del usuario  <br/> ||
|Foto de contacto de alta resolución en el cliente de Lync 2013 o Skype Empresarial.  <br/> |Requiere Exchange 2016 o Exchange 2013. Esto no se admite en Lync Web App cuando los usuarios se encuentran en Skype Empresarial Online.  <br/> |
|Delegación de reuniones  <br/> |Solo se admite cuando ambos usuarios están en línea en el mismo bosque o ambos se encuentran en el entorno local. Para obtener más información, vea [soluciones híbridas de Skype Empresarial.](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/skype-for-business-hybrid-solutions) <br/> |
|El historial de conversaciones perdidas y los registros de llamadas se escriben en el buzón de Exchange del usuario  <br/> ||
|Historial de conversaciones del lado servidor  <br/> ||

 **Skype Empresarial Online y Exchange Online**


|**Característica**|**Notas**|
|:-----|:-----|
|Mensajería instantánea y presencia en Outlook  <br/> ||
|Programar y unirse a reuniones en línea a través de Outlook  <br/> ||
|Mensajería instantánea y presencia en Outlook Web App  <br/> ||
|Programar y unirse a una reunión en línea desde Outlook Web App  <br/> ||
|Mensajería instantánea y presencia en clientes móviles  <br/> ||
|Unirse a una reunión en línea en clientes móviles  <br/> ||
|Publicar el estado en función de la información de disponibilidad del calendario de Outlook  <br/> ||
|El historial de conversaciones perdidas y los registros de llamadas se escriben en el buzón de exchange del usuario  <br/> ||
|Lista de contactos (a través del almacén de contactos unificado)  <br/> |Se requiere el cliente de Lync Server 2013 o Skype Empresarial  <br/> |
|Foto de contacto de alta resolución en Lync 2013, cliente de Skype Empresarial y Lync Web App  <br/> ||
|Delegación de reuniones  <br/> |Solo se admite cuando ambos usuarios están en línea en el mismo bosque o ambos se encuentran en el entorno local. Para obtener más información, vea [soluciones híbridas de Skype Empresarial.](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/skype-for-business-hybrid-solutions) <br/> |
|Contenido de archivado (mensajería instantánea y reunión) en Exchange  <br/> ||
|Buscar contenido archivado  <br/> ||
|Correo de voz  <br/> ||

## <a name="integration-with-sharepoint"></a>Integración con SharePoint

En la tabla siguiente se enumeran las características admitidas en una implementación híbrida cuando se integran con SharePoint.

||**SharePoint local**|**SharePoint Online**|
|:-----|:-----|:-----|
|**Skype Empresarial Server 2015 local** <br/> | Búsqueda de aptitudes <br/>  Presencia en SharePoint <br/> | Presencia en SharePoint <br/> |
|**Skype Empresarial Online** <br/> | Presencia en SharePoint <br/> | Presencia en SharePoint <br/> |


