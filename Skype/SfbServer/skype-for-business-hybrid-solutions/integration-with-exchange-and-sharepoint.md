---
title: Integración con Exchange y SharePoint
ms.author: crowe
author: CarolynRowe
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
ms.custom: Strat_SB_Hybrid
ms.assetid: 5d456d6c-ad71-420c-b6d8-4d9cd0324f86
description: 'Resumen: Conozca Skype para Business Server 2015 integración con Exchange y SharePoint.'
ms.openlocfilehash: 5c266656e02113645fa2f8aaa2f28dc4953b4540
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="integration-with-exchange-and-sharepoint"></a>Integración con Exchange y SharePoint
 
**Resumen:** Obtenga información acerca de Skype para Business Server 2015 integración con Exchange y SharePoint.
  
Puede configurar Skype para implementaciones de servidor de negocios 2015 para la integración con Microsoft Exchange Server 2016, 2013 de Microsoft Exchange Server, Microsoft Exchange Server 2010 y SharePoint Server, tanto local y en línea. Las características que se indican en la tabla siguiente son compatibles con todos los clientes, a menos que se indique lo contrario. Para obtener más información acerca del cliente admite, vea [comparación de características de cliente de escritorio de Skype para empresas](../plan-your-deployment/clients-and-devices/desktop-feature-comparison.md) y Skype para los negocios en línea tablas de comparación de cliente en [clientes de Skype para los negocios en línea](https://go.microsoft.com/fwlink/p/?LinkId=281902).
  
## <a name="integration-with-exchange-server"></a>Integración con Exchange Server

En las tablas siguientes se enumeran las características que se admiten en una implementación híbrida cuando está integrado con Microsoft Exchange Server. 
  
 **Skype para Business Server en locales y Exchange en instalaciones**
  
| |
|**Característica**|**Notas**|
|:-----|:-----|
|Mensajería instantánea y presencia en Outlook  <br/> |Para obtener más información, vea [mensajería instantánea y presencia](http://technet.microsoft.com/library/6a93ae95-3b64-410b-ab72-74dea232f065.aspx).  <br/> |
|Programar y unirse a reuniones en línea a través de Outlook  <br/> |Para obtener más información, vea [Integrar Skype para Business Server 2015 con Exchange Server](../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md).  <br/> |
|Mensajería instantánea y presencia en Outlook Web App  <br/> |Para obtener más información, consulte [configurar un entorno híbrido en Skype para Business Server 2015](../manage/authentication/configure-a-hybrid-environment.md).  <br/> |
|Programar y unirse a conferencia en línea mediante Outlook Web App  <br/> ||
|Mensajería instantánea y presencia en clientes móviles  <br/> ||
|Unirse a reuniones en línea en clientes móviles  <br/> |Para obtener más información, vea [Implementación de movilidad](http://technet.microsoft.com/library/f41e6b25-d2cd-43fd-a17b-22cfda8bcd4f.aspx).  <br/> |
|Publicar el estado según la información de disponibilidad del calendario de Outlook  <br/> ||
|Lista de contactos (por medio del almacén de contactos unificado)  <br/> |Requiere 2016 Exchange o intercambio de 2013.  <br/> Se requiere un 2013 de Lync o Skype para cliente de escritorio de negocios.  <br/>  Para obtener más información, consulte [Configurar Skype para Business Server 2015 utilizar el almacén de contactos unificado](../deploy/integrate-with-exchange-server/use-the-unified-contact-store.md).  <br/> |
|Alta resolución foto de contacto en el cliente Lync 2013, Skype para Business client y Lync Web App.  <br/> |Requiere 2016 Exchange o intercambio de 2013.  <br/> Para obtener más información, consulte [Configurar el uso de fotografías de alta resolución en Skype para Business Server 2015](../deploy/integrate-with-exchange-server/high-resolution-photos.md).  <br/> |
|Delegación de reuniones  <br/> |Se admite solo cuando ambos usuarios están hospedados en línea en el mismo bosque o ambos están hospedados localmente.  <br/> |
|Registros de llamadas y el historial de conversaciones perdidas se escriben en el buzón de exchange del usuario  <br/> ||
|Contenido de archivado (mensajería instantánea y reuniones) en Exchange  <br/> |Requiere 2016 Exchange o intercambio de 2013.  <br/> Para obtener más información, vea [Lista de comprobación de implementación para Archiving](http://technet.microsoft.com/library/7479734d-be01-40d9-ad82-320a09d19d04.aspx).  <br/> |
|Buscar contenido archivado  <br/> |Requiere 2016 Exchange o intercambio de 2013.  <br/> |
|Correo de voz  <br/> |Para obtener más información, vea [Implementación local mensajería unificada de Exchange proporciona de correo de voz de Lync Server 2013](http://technet.microsoft.com/library/9673bd73-a3a3-425d-870f-04d801c6d0d5.aspx).  <br/> |
   
 **Skype para Business Server en locales y en línea de Exchange**
  
| |
|**Característica**|**Notas**|
|:-----|:-----|
|Mensajería instantánea y presencia en Outlook  <br/> |Para obtener más información, vea [Configurar la integración entre locales Skype para Business Server 2015 y Outlook Web App](../deploy/integrate-with-exchange-server/outlook-web-app.md) <br/> |
|Programar y unirse a reuniones en línea a través de Outlook  <br/> ||
|Mensajería instantánea y presencia en Outlook Web App  <br/> |Para obtener más información, vea [Configurar la integración entre locales Skype para Business Server 2015 y Outlook Web App](../deploy/integrate-with-exchange-server/outlook-web-app.md) <br/> |
|Programar y unirse a reuniones en línea desde Outlook Web App  <br/> |Para obtener más información, vea [Configurar la integración entre locales Skype para Business Server 2015 y Outlook Web App](../deploy/integrate-with-exchange-server/outlook-web-app.md) <br/> |
|Mensajería instantánea y presencia en clientes móviles  <br/> ||
|Unirse a reuniones en línea en clientes móviles  <br/> ||
|Publicar el estado según la información de disponibilidad del calendario de Outlook  <br/> ||
|Lista de contactos (por medio del almacén de contactos unificado).  <br/> |Lync Server 2013. Se requiere un 2013 de Lync o Skype para cliente de escritorio de negocios.  <br/> Para obtener más información, vea [Configurar Skype para Business Server 2015 utilizar el almacén de contactos unificado](../deploy/integrate-with-exchange-server/use-the-unified-contact-store.md) <br/> |
|Alta resolución foto de contacto en el cliente Lync 2013, Skype para Business client y Lync Web App.  <br/> |Para obtener más información, consulte [Configurar el uso de fotografías de alta resolución en Skype para Business Server 2015](../deploy/integrate-with-exchange-server/high-resolution-photos.md).  <br/> |
|Delegación de reuniones  <br/> |Se admite solo cuando ambos usuarios están hospedados en línea en el mismo bosque o ambos están hospedados localmente.  <br/> |
|Registros de llamadas y el historial de conversaciones perdidas se escriben en el buzón de Exchange del usuario  <br/> ||
|Contenido de archivado (mensajería instantánea y reuniones) en Exchange  <br/> |Para obtener más información, vea [Lista de comprobación de implementación para Archiving](http://technet.microsoft.com/library/7479734d-be01-40d9-ad82-320a09d19d04.aspx).  <br/> |
|Buscar contenido archivado  <br/> |Para obtener más información, consulte al [Configurar Exchange para SharePoint centro de eDiscovery](https://go.microsoft.com/fwlink/p/?LinkId=285448) <br/> |
|Correo de voz  <br/> |Para obtener más información, vea [Proporcionar Lync Server 2013 usuarios de correo de voz en alojado mensajería unificada de Exchange](http://technet.microsoft.com/library/306d3fb5-231b-4f0b-b8d8-0d9083b5ed77.aspx).  <br/> |
   
 **Skype para los negocios en línea y Exchange en instalaciones**
  
| |
|**Característica**|**Notas**|
|:-----|:-----|
|Presencia en Outlook  <br/> ||
|Responder a través de MI, llamadas RTC, llamadas de Skype o videollamadas desde un correo electrónico de Outlook  <br/> ||
|Programar y unirse a reuniones en línea a través de Outlook  <br/> ||
|Mensajería instantánea y presencia en clientes móviles  <br/> ||
|Unirse a reuniones en línea en clientes móviles  <br/> ||
|Publicar el estado según la información de disponibilidad del calendario de Outlook  <br/> ||
|Registros de llamadas y el historial de conversaciones perdidas se escriben en el buzón de exchange del usuario  <br/> ||
|Fotos de alta resolución contacto en Lync 2013 o Skype para Business client.  <br/> |Requiere 2016 Exchange o intercambio de 2013. No se admite en Lync Web App cuando los usuarios están alojados en Skype para los negocios en línea.  <br/> |
|Delegación de reuniones  <br/> |Se admite solo cuando ambos usuarios están hospedados en línea en el mismo bosque o ambos están hospedados localmente.  <br/> |
|Registros de llamadas y el historial de conversaciones perdidas se escriben en el buzón de Exchange del usuario  <br/> ||
|Historial de conversaciones en el servidor  <br/> ||
   
 **Skype para el negocio en línea y Exchange Online**
  
| |
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
|Lista de contactos (por medio del almacén de contactos unificado)  <br/> |Lync Server 2013 o Skype para cliente de negocios requerido  <br/> |
|Fotos de alta resolución contacto en Lync 2013, Skype para Business client y Lync Web App  <br/> ||
|Delegación de reuniones  <br/> |Se admite solo cuando ambos usuarios están hospedados en línea en el mismo bosque o ambos están hospedados localmente.  <br/> |
|Contenido de archivado (mensajería instantánea y reuniones) en Exchange  <br/> ||
|Buscar contenido archivado  <br/> ||
|Correo de voz  <br/> ||
   
## <a name="integration-with-sharepoint"></a>Integración con SharePoint

En la tabla siguiente enumera las características incorporadas en una implementación híbrida cuando está integrado con SharePoint.
  
||**SharePoint local**|**SharePoint Online**|
|:-----|:-----|:-----|
|**Skype para Business Server 2015 local** <br/> | Búsqueda de aptitudes <br/>  Presencia en SharePoint <br/> | Presencia en SharePoint <br/> |
|**Skype para el negocio en línea** <br/> | Presencia en SharePoint <br/> | Presencia en SharePoint <br/> |
   

