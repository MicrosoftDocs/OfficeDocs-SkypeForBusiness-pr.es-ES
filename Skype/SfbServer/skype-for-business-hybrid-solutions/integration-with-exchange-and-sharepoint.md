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
description: 'Summary: Learn about Skype Empresarial Server 2015 integration with Exchange and SharePoint.'
ms.openlocfilehash: f8d57924d3a82effbc552de660b973aa36e7b8fe
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/06/2021
ms.locfileid: "52236996"
---
# <a name="integration-with-exchange-and-sharepoint"></a>Integración con Exchange y SharePoint

**Resumen:** Obtenga información Skype Empresarial Server integración de 2015 con Exchange y SharePoint.

Puede configurar Skype Empresarial Server 2015 para la integración con Microsoft Exchange Server 2016, Microsoft Exchange Server 2013, Microsoft Exchange Server 2010 y SharePoint Server, tanto local como en línea. Las características enumeradas en la tabla siguiente son compatibles con todos los clientes a menos que se especifique lo contrario. Para obtener más información [](../plan-your-deployment/clients-and-devices/desktop-feature-comparison.md) acerca de la compatibilidad con clientes, vea Comparación de características de cliente de escritorio para Skype Empresarial y Skype Empresarial Tablas de comparación de clientes en línea en [Clientes para Skype Empresarial Online](/office365/servicedescriptions/skype-for-business-online-service-description/skype-for-business-online-features).

[!INCLUDE [sfbo-retirement-skype](../../Hub/includes/sfbo-retirement.md)]

## <a name="integration-with-exchange-server"></a>Integración con Exchange Server

En las tablas siguientes se muestran las características admitidas en una implementación híbrida cuando se integran con Microsoft Exchange Server.

 **Skype Empresarial Server local y Exchange local**


|**Característica**|**Notas**|
|:-----|:-----|
|MI/Presencia en Outlook  <br/> |Para obtener más información, vea [MI y Presence](/previous-versions/office/lync-server-2013/lync-server-2013-im-and-presence).  <br/> |
|Programar y unirse a una reunión en línea Outlook  <br/> |Para obtener más información, [vea Integrar Skype Empresarial Server 2015 con Exchange Server](../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md).  <br/> |
|Mi/Presencia en Outlook Web App  <br/> |Para obtener más información, vea [Configure a hybrid environment in Skype Empresarial Server 2015](../manage/authentication/configure-a-hybrid-environment.md).  <br/> |
|Programar y unirse a una reunión en línea a través de Outlook Web App  <br/> ||
|Mensajería instantánea/presencia en clientes móviles  <br/> ||
|Unirse a reuniones en línea en clientes móviles  <br/> |Para obtener más información, vea [Deploying Mobility](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-mobility).  <br/> |
|Estado de publicación basado en Outlook de disponibilidad del calendario  <br/> ||
|Lista de contactos (a través del Almacén de contactos unificado)  <br/> |Requiere Exchange 2016 o Exchange 2013.  <br/> Se requiere un cliente de escritorio Skype Empresarial Lync 2013 o de escritorio.  <br/>  Para obtener más información, vea [Configure Skype Empresarial Server 2015 to use the unified contact store](../deploy/integrate-with-exchange-server/use-the-unified-contact-store.md).  <br/> |
|Foto de contacto de alta resolución en el cliente de Lync 2013, Skype Empresarial cliente y Lync Web App.  <br/> |Requiere Exchange 2016 o Exchange 2013.  <br/> Para obtener más información, vea [Configure the use of high-resolution photos in Skype Empresarial Server 2015](../deploy/integrate-with-exchange-server/high-resolution-photos.md).  <br/> Para las fotos de la aplicación Skype Empresarial para MAC y Móvil, la integración entre Skype Empresarial Server 2015 y Exchange Server debe configurarse como se describe en Configurar aplicaciones de partners en Skype Empresarial Server y [Exchange Server](../deploy/integrate-with-exchange-server/configure-partner-applications.md). <br/> |
|Delegación de reuniones  <br/> |Solo se admite cuando ambos usuarios se encuentran en línea en el mismo bosque o cuando ambos se encuentran en el entorno local. Para obtener más información, [vea Skype Empresarial soluciones híbridas](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/skype-for-business-hybrid-solutions). <br/> |
|El historial de conversaciones perdidas y los registros de llamadas se escriben en el buzón de exchange del usuario  <br/> ||
|Contenido de archivado (MI y reunión) en Exchange  <br/> |Requiere Exchange 2016 o Exchange 2013.  <br/> Para obtener más información, vea [Deployment Checklist for Archiving](/previous-versions/office/lync-server-2013/lync-server-2013-deployment-checklist-for-archiving).  <br/> |
|Buscar contenido archivado  <br/> |Requiere Exchange 2016 o Exchange 2013.  <br/> |
|Correo de voz  <br/> |Para obtener más información, vea [Deploying On-Premises Exchange UM to Provide Lync Server 2013 Voice Mail](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-on-premises-exchange-um-to-provide-lync-server-2013-voice-mail).  <br/> |

 **Skype Empresarial Server local y Exchange Online**


|**Característica**|**Notas**|
|:-----|:-----|
|MI/Presencia en Outlook  <br/> |Para obtener más información, vea [Configure integration between on-premises Skype Empresarial Server 2015 and Outlook Web App](../deploy/integrate-with-exchange-server/outlook-web-app.md) <br/> |
|Programar y unirse a una reunión en línea Outlook  <br/> ||
|Mi/Presencia en Outlook Web App  <br/> |Para obtener más información, vea [Configure integration between on-premises Skype Empresarial Server 2015 and Outlook Web App](../deploy/integrate-with-exchange-server/outlook-web-app.md) <br/> |
|Programar y unirse a una reunión en línea desde Outlook Web App  <br/> |Para obtener más información, vea [Configure integration between on-premises Skype Empresarial Server 2015 and Outlook Web App](../deploy/integrate-with-exchange-server/outlook-web-app.md) <br/> |
|Mensajería instantánea/presencia en clientes móviles  <br/> ||
|Unirse a una reunión en línea en clientes móviles  <br/> ||
|Estado de publicación basado en Outlook de disponibilidad del calendario  <br/> ||
|Lista de contactos (a través del Almacén de contactos unificado).  <br/> |Solo Lync Server 2013. Se requiere un cliente de escritorio Skype Empresarial Lync 2013 o de escritorio.  <br/> Para obtener más información, [vea Configure Skype Empresarial Server 2015 to use the unified contact store](../deploy/integrate-with-exchange-server/use-the-unified-contact-store.md) <br/> |
|Foto de contacto de alta resolución en el cliente de Lync 2013, Skype Empresarial cliente y Lync Web App.  <br/> |Para obtener más información, vea [Configure the use of high-resolution photos in Skype Empresarial Server 2015](../deploy/integrate-with-exchange-server/high-resolution-photos.md).  <br/> Para las fotos de la aplicación de Skype Empresarial para MAC y Móviles, la integración entre Skype Empresarial Server 2015 y Exchange Server debe configurarse como se describe en Configurar la integración entre Skype Empresarial Server local [y Outlook Web App](../deploy/integrate-with-exchange-server/outlook-web-app.md). <br/> |
|Delegación de reuniones  <br/> |Solo se admite cuando ambos usuarios se encuentran en línea en el mismo bosque o cuando ambos se encuentran en el entorno local. Para obtener más información, [vea Skype Empresarial soluciones híbridas](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/skype-for-business-hybrid-solutions). <br/> |
|El historial de conversaciones perdidas y los registros de llamadas se escriben en el buzón de correo Exchange usuario  <br/> ||
|Contenido de archivado (MI y reunión) en Exchange  <br/> |Para obtener más información, vea [Deployment Checklist for Archiving](/previous-versions/office/lync-server-2013/lync-server-2013-deployment-checklist-for-archiving).  <br/> |
|Buscar contenido archivado  <br/> |Para obtener más información, vea [Configure Exchange for SharePoint eDiscovery Center](/exchange/configure-exchange-for-sharepoint-ediscovery-center-exchange-2013-help) <br/> |
|Correo de voz  <br/> |Para obtener más información, vea [Providing Lync Server 2013 Users Voice Mail on Hosted Exchange UM](/previous-versions/office/lync-server-2013/lync-server-2013-providing-lync-server-users-voice-mail-on-hosted-exchange-um).  <br/> |

 **Skype Empresarial Online y Exchange local**


|**Característica**|**Notas**|
|:-----|:-----|
|Presencia en Outlook  <br/> ||
|Responder a través de mensajería instantánea, llamada RTC, Skype o videollamada desde un correo Outlook correo electrónico  <br/> ||
|Programar y unirse a reuniones en línea a través de Outlook  <br/> ||
|Mensajería instantánea/presencia en clientes móviles  <br/> ||
|Unirse a reuniones en línea en clientes móviles  <br/> ||
|Estado de publicación basado en Outlook de disponibilidad del calendario  <br/> ||
|El historial de conversaciones perdidas y los registros de llamadas se escriben en el buzón de exchange del usuario  <br/> ||
|Foto de contacto de alta resolución en Lync 2013 o Skype Empresarial cliente.  <br/> |Requiere Exchange 2016 o Exchange 2013. Esto no se admite en Lync Web App cuando los usuarios se encuentran en Skype Empresarial Online.  <br/> |
|Delegación de reuniones  <br/> |Solo se admite cuando ambos usuarios se encuentran en línea en el mismo bosque o cuando ambos se encuentran en el entorno local. Para obtener más información, [vea Skype Empresarial soluciones híbridas](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/skype-for-business-hybrid-solutions). <br/> |
|El historial de conversaciones perdidas y los registros de llamadas se escriben en el buzón de correo Exchange usuario  <br/> ||
|Historial de conversaciones del lado servidor  <br/> ||

 **Skype Empresarial En línea y Exchange Online**


|**Característica**|**Notas**|
|:-----|:-----|
|MI/Presencia en Outlook  <br/> ||
|Programar y unirse a reuniones en línea a través de Outlook  <br/> ||
|Mi/Presencia en Outlook Web App  <br/> ||
|Programar y unirse a una reunión en línea desde Outlook Web App  <br/> ||
|Mensajería instantánea/presencia en clientes móviles  <br/> ||
|Unirse a una reunión en línea en clientes móviles  <br/> ||
|Estado de publicación basado en Outlook de disponibilidad del calendario  <br/> ||
|El historial de conversaciones perdidas y los registros de llamadas se escriben en el buzón de exchange del usuario  <br/> ||
|Lista de contactos (a través del Almacén de contactos unificado)  <br/> |Lync Server 2013 o Skype Empresarial cliente necesario  <br/> |
|Foto de contacto de alta resolución en Lync 2013, Skype Empresarial cliente y Lync Web App  <br/> ||
|Delegación de reuniones  <br/> |Solo se admite cuando ambos usuarios se encuentran en línea en el mismo bosque o cuando ambos se encuentran en el entorno local. Para obtener más información, [vea Skype Empresarial soluciones híbridas](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/skype-for-business-hybrid-solutions). <br/> |
|Contenido de archivado (MI y reunión) en Exchange  <br/> ||
|Buscar contenido archivado  <br/> ||
|Correo de voz  <br/> ||

## <a name="integration-with-sharepoint"></a>Integración con SharePoint

En la tabla siguiente se enumeran las características admitidas en una implementación híbrida cuando se integran con SharePoint.

||**SharePoint local**|**SharePoint Online**|
|:-----|:-----|:-----|
|**Skype Empresarial Server 2015 local** <br/> | Búsqueda de aptitudes <br/>  Presencia en SharePoint <br/> | Presencia en SharePoint <br/> |
|**Skype Empresarial Online** <br/> | Presencia en SharePoint <br/> | Presencia en SharePoint <br/> |