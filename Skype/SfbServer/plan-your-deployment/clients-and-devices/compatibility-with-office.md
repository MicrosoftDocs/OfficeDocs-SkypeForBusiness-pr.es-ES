---
title: Skype para la compatibilidad de negocio con aplicaciones de Office
ms.author: jambirk
author: PhillipGarding
manager: serdars
ms.date: 2/16/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ac3a1046-b438-4e21-9d4f-3b0057dd685d
description: Comprender las formas que se puede tener acceso a Skype para las características empresariales de Outlook y otras aplicaciones de Microsoft Office.
ms.openlocfilehash: 22319a814ac1f09e67143f71a705c44b1e820e0e
ms.sourcegitcommit: 47f80b977fa7de3b83a521164f765623bffcf5c0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/13/2018
ms.locfileid: "22391843"
---
# <a name="skype-for-business-compatibility-with-office-apps"></a>Skype para la compatibilidad de negocio con aplicaciones de Office
 
Comprender las formas que se puede tener acceso a Skype para las características empresariales de Outlook y otras aplicaciones de Microsoft Office.
  
En este tema se describe la compatibilidad de Skype para la empresa con distintas versiones de conjuntos de aplicaciones de Microsoft Office. 
  
## <a name="office-and-skype-for-business"></a>Office y Skype para la empresa

En la siguiente tabla se describe la Skype para las características de negocio que son compatibles con las distintas versiones de Office una vez que Exchange se ha implementado e integrada tal como se describe en [Integrar Skype para Business Server con Exchange Server](../../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md).
  
**Skype para empresas y compatibilidad de Microsoft Office**

|**Característica**|**Microsoft Office 2010**|**Microsoft Office 2013, 2015 y 2016**|**2016 de Office para Mac** & #x 2776; |
|:-----|:-----|:-----|:-----|
|**Características de Outlook** ||||
|Personalizar invitaciones a reuniones de Outlook (agregar logotipo, URL de ayuda, declinación de responsabilidades, texto del pie de página)  |No  |Sí   |Sí|
|Configurar la opción de reunión para silenciar el audio y el vídeo de los asistentes de manera predeterminada    |No    |Sí    |No    |
|Almacén de contactos unificados para la administración de las listas de contactos a través de Office y Skype para la empresa    |No    |Sí (requiere Exchange 2013 o posterior)    |Sí    |
|Imágenes de perfil de alta resolución    |No    |Sí (requiere Exchange 2013 o posterior)    |Sí    |
|Estado de presencia en el Microsoft Outlook, en, campos y Cc    |Sí    |Sí    |Sí    |
|Responder con mensajería instantánea o llamar desde el menú de disponibilidad    |Sí (desde la tarjeta de contacto)    |Sí (desde la tarjeta de contacto)    |Sí (desde la tarjeta de contacto)    |
|Estado de presencia en una convocatoria de reunión en la pestaña Asistente para programación    |Sí    |Sí    |No    |
|Responder con mensajería instantánea o llamada desde la barra de herramientas o la cinta de opciones en un mensaje de correo electrónico recibido    |Sí    |Sí    |Sí    |
|**Otras aplicaciones de Office**   ||||
|Notas compartidas de OneNote    |No    |Sí    |No    |
|Configuración integrada en el programa de configuración de Office    |No    |Sí    |No    |
|Contenido de presentaciones de PowerPoint    |Sí    |Sí (VBSS también está disponible)    |Sí    |
|Mensajería instantánea y presencia en los archivos de Microsoft Word y Microsoft Excel (etiquetas inteligentes habilitadas)    |Solo Microsoft Word    |Solo Microsoft Word    |No    |
|Mensajería instantánea y presencia en los sitios de Microsoft SharePoint (debe instalarse Outlook)    |Sí    |Sí    |No    |
   
& #x 2776; -Se da por supuesto que ha instalado y se está ejecutando actualmente una Skype para la empresa en el cliente de Mac o el Lync 2011 para cliente de Mac.
  
## <a name="exchange-server-and-skype-for-business"></a>Exchange Server y Skype para la empresa

En la siguiente tabla se describe Skype para soporte del negocio para las distintas versiones de Exchange Server. Outlook debe instalarse en el equipo cliente para administrar las llamadas extendidas de MAPI y algunas características requieren el uso de servicios Web Exchange (EWS).
  
**Skype para empresas y compatibilidad de Exchange Server**

|**Versión de Exchange Server**|**Skype para soporte del negocio**|
|:-----|:-----|
|Exchange Server 2019 (Skype para Business Server 2019 sólo) |Igual que la compatibilidad con Exchange Server 2013    |
|Exchange Server 2016    |Igual que la compatibilidad con Exchange Server 2013  <br/> |
|Exchange Server 2013  <br/> |Igual que el soporte técnico de Exchange Server 2010, con la incorporación de  <br/>&bull;&nbsp;&nbsp;Almacén de contactos unificados  <br/>&bull;&nbsp;&nbsp;Imágenes de alta resolución  <br/>&bull;&nbsp;&nbsp;Integración de archivado  <br/> **Nota:** Para obtener información detallada, vea [Integrar Skype para Business Server con Exchange Server](../../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md).  <br/> |
|Exchange Server 2010  <br/>(Skype para Business Server 2015 sólo) |Las siguientes características solo están disponibles mediante EWS:  <br/>&bull;&nbsp;&nbsp;Leer o eliminar elementos en la carpeta Historial de conversaciones  <br/>&bull;&nbsp;&nbsp;Leer o eliminar elementos de correo de voz  <br/>&bull;&nbsp;&nbsp;Mostrar información de libre/ocupado extendida y el asunto de la reunión y la ubicación  <br/>&bull;&nbsp;&nbsp;Sincronización de contactos de Exchange  <br/> Las carpetas públicas son opcionales en Exchange Server 2010.  <br/> |
   
## <a name="see-also"></a>Vea también
 
[Los requisitos de cliente de Windows y la compatibilidad de software](windows-requirements.md)
  
[Planeación de los clientes de las reuniones (Web App y aplicación de las reuniones)](meetings-clients.md)

