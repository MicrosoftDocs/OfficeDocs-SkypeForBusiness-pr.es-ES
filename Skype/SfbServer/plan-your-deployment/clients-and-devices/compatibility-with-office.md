---
title: Skype para la compatibilidad de negocio con aplicaciones de Office
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/16/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.custom: Strat_SB_Admin
ms.assetid: ac3a1046-b438-4e21-9d4f-3b0057dd685d
description: Comprender las formas en que puede tener acceso a Skype para funciones de negocio desde Outlook y otras aplicaciones de Microsoft Office.
ms.openlocfilehash: 2b58c9f8decef9be329dbb3f9e77422b3f0a59c0
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="skype-for-business-compatibility-with-office-apps"></a>Skype para la compatibilidad de negocio con aplicaciones de Office
 
Comprender las formas en que puede tener acceso a Skype para funciones de negocio desde Outlook y otras aplicaciones de Microsoft Office.
  
Este tema describe la compatibilidad de Skype para empresas con varias versiones de los conjuntos de aplicaciones de Microsoft Office. 
  
## <a name="office-and-skype-for-business"></a>Office y Skype para empresas

La tabla siguiente describe el Skype para funciones de negocio que son compatibles con varias versiones de Office una vez que se ha implementado e integrado como se describe en [Integrar Skype para Business Server 2015 con Exchange Server](../../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md)Exchange.
  
**Skype para el negocio y la compatibilidad de Microsoft Office**

|**Característica**|**Microsoft Office 2010**|**Microsoft Office 2013, 2015 y 2016**|**2016 de Office para Mac** & #x 2776; |
|:-----|:-----|:-----|:-----|
|**Características de Outlook** <br/> ||||
|Personalizar invitaciones a reuniones de Outlook (agregar logotipo, URL de ayuda, declinación de responsabilidades, texto del pie de página)  <br/> |No  <br/> |Sí  <br/> |No  <br/> |
|Configurar la opción de reunión para silenciar el audio y el vídeo de los asistentes de manera predeterminada  <br/> |No  <br/> |Sí  <br/> |No  <br/> |
|Almacén de contacto unificado para administrar listas de contactos en Office y Skype para empresas  <br/> |No  <br/> |Sí (requiere Exchange 2013 o posterior)  <br/> |Sí  <br/> |
|Imágenes de alta resolución de perfil  <br/> |No  <br/> |Sí (requiere Exchange 2013 o posterior)  <br/> |Sí  <br/> |
|Estado de presencia en el Microsoft Outlook, campos y Cc  <br/> |Sí  <br/> |Sí  <br/> |Sí  <br/> |
|Responder con IM o llamar desde el menú de disponibilidad  <br/> |Sí (desde la tarjeta de contacto)  <br/> |Sí (desde la tarjeta de contacto)  <br/> |Sí (desde la tarjeta de contacto)  <br/> |
|Estado de presencia en una convocatoria de reunión en la pestaña Asistente para programación  <br/> |Sí  <br/> |Sí  <br/> |No  <br/> |
|Responder con mensaje instantáneo o llamada desde la barra de herramientas o la cinta de opciones en un mensaje de correo electrónico recibidos  <br/> |Sí  <br/> |Sí  <br/> |Sí  <br/> |
|**Otras aplicaciones de Office** <br/> ||||
|Notas compartidas de OneNote  <br/> |No  <br/> |Sí  <br/> |No  <br/> |
|Configuración integrada en el programa de configuración de Office  <br/> |No  <br/> |Sí  <br/> |No  <br/> |
|Contenido de presentaciones de PowerPoint  <br/> |Sí  <br/> |Sí  <br/> (VBSS también disponible)  <br/> |Sí  <br/> |
|Mensajería instantánea y presencia en los archivos de Microsoft Word y Microsoft Excel (etiquetas inteligentes habilitadas)  <br/> |Solo Microsoft Word  <br/> |Solo Microsoft Word  <br/> |No  <br/> |
|Mensajería instantánea y presencia en los sitios de Microsoft SharePoint (debe instalarse Outlook)  <br/> |Sí  <br/> |Sí  <br/> |No  <br/> |
   
& #x 2776; -Se supone que ha instalado y se está ejecutando actualmente un Skype para empresas en cliente de Mac o el 2011 Lync para cliente de Mac.
  
## <a name="exchange-server-and-skype-for-business"></a>Exchange Server y Skype para empresas

La tabla siguiente describe Skype para soporte del negocio para las distintas versiones de Exchange Server. Outlook debe instalarse en el equipo cliente para administrar las llamadas extendidas de MAPI y algunas características requieren el uso de servicios Web Exchange (EWS).
  
**Skype para el negocio y la compatibilidad de Exchange Server**

|**Versión de Exchange Server**|**Skype para soporte del negocio**|
|:-----|:-----|
|Exchange Server 2016  <br/> |Igual que la compatibilidad con Exchange Server 2013  <br/> |
|Exchange Server 2013  <br/> |Igual que la compatibilidad de Exchange Server 2010, con la adición de  <br/>&bull;&nbsp;&nbsp;Almacén de contacto unificado  <br/>&bull;&nbsp;&nbsp;Imágenes de alta resolución  <br/>&bull;&nbsp;&nbsp;Integración de archiving  <br/> **Nota:** Para obtener más información, vea [Integrar Skype para Business Server 2015 con Exchange Server](../../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md).  <br/> |
|Exchange Server 2010  <br/> |Las siguientes características solo están disponibles mediante EWS:  <br/>&bull;&nbsp;&nbsp;Leer o eliminar elementos de la carpeta Historial de conversaciones  <br/>&bull;&nbsp;&nbsp;Leer o eliminar elementos de correo de voz  <br/>&bull;&nbsp;&nbsp;Mostrar la información de disponibilidad ampliada y asunto de la reunión y ubicación  <br/>&bull;&nbsp;&nbsp;Sincronización de contactos de Exchange  <br/> Las carpetas públicas son opcionales en Exchange Server 2010.  <br/> |
   
## <a name="see-also"></a>Vea también
 

[Requisitos del cliente de Windows y soporte de software](windows-requirements.md)
  
[Plan para clientes de reuniones (Web App y App de reuniones)](meetings-clients.md)
#### 

[Interoperabilidad de cliente Lync 2013](http://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx)
  
[Requisitos del sistema cliente](http://technet.microsoft.com/library/38f3a465-dac1-4381-bc59-270a4ef07ced.aspx)
  
[Requisitos de la aplicación Lync Windows Store](http://technet.microsoft.com/library/5f2e0a40-8450-4f61-b6f6-913fc1906020.aspx)

