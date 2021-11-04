---
title: Skype Empresarial compatibilidad con Office aplicaciones
ms.author: v-mahoffman
author: cichur
ms.reviewer: PhillipGarding
manager: serdars
ms.date: 2/16/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ac3a1046-b438-4e21-9d4f-3b0057dd685d
description: Comprenda las formas en que puede obtener acceso Skype Empresarial características desde Outlook y otras Microsoft Office aplicaciones.
ms.openlocfilehash: e4b826cf6ba79b8db31ec5dec57c8d6bfca5280f
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/04/2021
ms.locfileid: "60773570"
---
# <a name="skype-for-business-compatibility-with-office-apps"></a>Skype Empresarial compatibilidad con Office aplicaciones
 
Comprenda las formas en que puede obtener acceso Skype Empresarial características desde Outlook y otras Microsoft Office aplicaciones.
  
En este tema se describe la compatibilidad de Skype Empresarial con varias versiones de Microsoft Office suites. 
  
## <a name="office-and-skype-for-business"></a>Office y Skype Empresarial

En la tabla siguiente se describen las características de Skype Empresarial compatibles con varias versiones de Office una vez que Exchange se implementa e integra como se describe en [Integrar Skype Empresarial Server](../../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md)con Exchange Server .
  
**Skype Empresarial y Microsoft Office compatibilidad**

|**Característica**|**Microsoft Office 2010**|**Microsoft Office 2013, 2015 y 2016**|**Office 2016 para Mac** &#x2776; |
|:-----|:-----|:-----|:-----|
|**Outlook características** ||||
|Personalizar Outlook de reunión (agregar logotipo, url de ayuda, declinación de responsabilidades, texto de pie de página)  |No  |Sí   |Sí|
|Configurar la opción de reunión para silenciar audio y vídeo de los asistentes de forma predeterminada    |No    |Sí    |No    |
|Almacén de contactos unificado para administrar listas de contactos en Office y Skype Empresarial    |No    |Sí (requiere Exchange 2013 o posterior)    |Sí    |
|Imágenes de perfil de alta resolución    |No    |Sí (requiere Exchange 2013 o posterior)    |Sí    |
|Estado de presencia en los campos Outlook, Para y Cc de Microsoft    |Sí    |Sí    |Sí    |
|Responder con mensajería instantánea o llamada desde el menú de disponibilidad    |Sí (desde la tarjeta de contacto)    |Sí (desde la tarjeta de contacto)    |Sí (desde la tarjeta de contacto)    |
|Estado de presencia en una solicitud de reunión en Asistente para programación pestaña    |Sí    |Sí    |No    |
|Responder con mensajería instantánea o llamada desde la barra de herramientas o la cinta de opciones en un mensaje de correo electrónico recibido    |Sí    |Sí    |Sí    |
|**Otras Office aplicaciones**   ||||
|OneNote notas compartidas    |No    |Sí    |No    |
|Configuración integrada en el Office de instalación    |No    |Sí    |No    |
|PowerPoint de presentación    |Sí    |Sí (VBSS también disponible)    |Sí    |
|Mensajería instantánea y presencia en Microsoft Word y Microsoft Excel (etiquetas inteligentes habilitadas)    |Microsoft Word solo    |Microsoft Word solo    |No    |
|Mensajería instantánea y presencia en los SharePoint de Microsoft (Outlook deben instalarse)    |Sí    |Sí    |No    |
   
&#x2776;: supone que ha instalado y que actualmente está ejecutando un Skype Empresarial cliente mac o el cliente de Lync 2011 para Mac.
  
## <a name="exchange-server-and-skype-for-business"></a>Exchange Server y Skype Empresarial

En la tabla siguiente se describe Skype Empresarial compatibilidad con varias versiones de Exchange Server. Outlook debe instalarse en el equipo cliente para controlar las llamadas MAPI extendidas y algunas características requieren el uso de Exchange Web Services (EWS).
  
**Skype Empresarial y Exchange Server compatibilidad**

|**Exchange Server versión**|**Skype Empresarial soporte técnico**|
|:-----|:-----|
|Exchange Server 2019 (solo Skype Empresarial Server 2019) |Igual que Exchange Server compatibilidad con 2013    |
|Exchange Server 2016    |Igual que Exchange Server compatibilidad con 2013  <br/> |
|Exchange Server 2013  <br/> |Igual que Exchange Server 2010, con la adición de  <br/>&bull;&nbsp;&nbsp;Almacén de contactos unificado  <br/>&bull;&nbsp;&nbsp;Imágenes de alta resolución  <br/>&bull;&nbsp;&nbsp;Integración de archivado  <br/> **Nota:** Para obtener más información, [vea Integrar Skype Empresarial Server con Exchange Server](../../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md).  <br/> |
|Exchange Server 2010  <br/>(solo Skype Empresarial Server 2015) |Las siguientes características solo están disponibles a través de EWS:  <br/>&bull;&nbsp;&nbsp;Leer o eliminar elementos de la carpeta Historial de conversaciones  <br/>&bull;&nbsp;&nbsp;Leer o eliminar elementos de correo de voz  <br/>&bull;&nbsp;&nbsp;Mostrar información de disponibilidad extendida y asunto y ubicación de la reunión  <br/>&bull;&nbsp;&nbsp;Exchange de contactos  <br/> Las carpetas públicas son opcionales Exchange Server 2010.  <br/> |
   
## <a name="see-also"></a>Consulte también
 
[Windows cliente y compatibilidad con software](windows-requirements.md)
  
[Plan for Meetings clients (Web App and Meetings App)](meetings-clients.md)

