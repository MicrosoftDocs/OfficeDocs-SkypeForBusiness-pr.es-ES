---
title: Compatibilidad de Skype empresarial con las aplicaciones de Office
ms.author: v-lanac
author: lanachin
ms.reviewer: PhillipGarding
manager: serdars
ms.date: 2/16/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ac3a1046-b438-4e21-9d4f-3b0057dd685d
description: Comprender las formas en las que puede obtener acceso a las características de Skype empresarial desde Outlook y desde otras aplicaciones de Microsoft Office.
ms.openlocfilehash: e91174850cb82d325eb9a3f75577d3aaeb3b90f6
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41803690"
---
# <a name="skype-for-business-compatibility-with-office-apps"></a>Compatibilidad de Skype empresarial con las aplicaciones de Office
 
Comprender las formas en las que puede obtener acceso a las características de Skype empresarial desde Outlook y desde otras aplicaciones de Microsoft Office.
  
En este tema se describe la compatibilidad de Skype empresarial con varias versiones de los conjuntos de programas de Microsoft Office. 
  
## <a name="office-and-skype-for-business"></a>Office y Skype empresarial

En la siguiente tabla se describen las características de Skype empresarial compatibles con varias versiones de Office una vez implementado Exchange y integrado según se describe en [integrar Skype empresarial Server con Exchange Server](../../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md).
  
**Compatibilidad de Skype empresarial y Microsoft Office**

|**Característica**|**Microsoft Office 2010**|**Microsoft Office 2013, 2015 y 2016**|&#x2776; **de Office 2016 para Mac** |
|:-----|:-----|:-----|:-----|
|**Características de Outlook** ||||
|Personalizar invitaciones a reuniones de Outlook (agregar logotipo, URL de ayuda, declinación de responsabilidades, texto del pie de página)  |No  |Sí   |Sí|
|Configurar la opción de reunión para silenciar el audio y el vídeo de los asistentes de manera predeterminada    |No    |Sí    |No    |
|Almacén de contactos unificado para administrar listas de contactos en Office y Skype empresarial    |No    |Sí (requiere Exchange 2013 o posterior)    |Sí    |
|Imágenes de Perfil de alta resolución    |No    |Sí (requiere Exchange 2013 o posterior)    |Sí    |
|Estado de presencia en los campos de Microsoft Outlook de, para y CC    |Sí     |Sí     |Sí     |
|Responder con mensajes instantáneos o llamadas desde el menú de disponibilidad    |Sí (desde la tarjeta de contacto)    |Sí (desde la tarjeta de contacto)    |Sí (desde la tarjeta de contacto)    |
|Estado de presencia en una convocatoria de reunión en la pestaña Asistente para programación    |Sí     |Sí    |No    |
|Responder con mi o llamar desde la barra de herramientas o la cinta de opciones en un mensaje de correo electrónico recibido    |Sí     |Sí     |Sí     |
|**Otras aplicaciones de Office**   ||||
|Notas compartidas de OneNote    |No    |Sí    |No    |
|Configuración integrada en el programa de configuración de Office    |No    |Sí    |No    |
|Contenido de presentaciones de PowerPoint    |Sí    |Sí (VBSS también está disponible)    |Sí    |
|Mensajería instantánea y presencia en los archivos de Microsoft Word y Microsoft Excel (etiquetas inteligentes habilitadas)    |Solo Microsoft Word    |Solo Microsoft Word    |No    |
|Mensajería instantánea y presencia en los sitios de Microsoft SharePoint (debe instalarse Outlook)    |Sí    |Sí    |No    |
   
&#x2776;: se supone que ha instalado y ejecuta actualmente un cliente de Skype empresarial en Mac o el cliente de Lync 2011 para Mac.
  
## <a name="exchange-server-and-skype-for-business"></a>Exchange Server y Skype empresarial

En la siguiente tabla se describe la compatibilidad de Skype empresarial para varias versiones de Exchange Server. Outlook debe instalarse en el equipo cliente para administrar las llamadas extendidas de MAPI y algunas características requieren el uso de servicios Web Exchange (EWS).
  
**Compatibilidad de Skype empresarial y Exchange Server**

|**Versión de Exchange Server**|**Soporte técnico de Skype empresarial**|
|:-----|:-----|
|Exchange Server 2019 (solo Skype empresarial Server 2019) |Igual que la compatibilidad con Exchange Server 2013    |
|Exchange Server 2016    |Igual que la compatibilidad con Exchange Server 2013  <br/> |
|Exchange Server 2013  <br/> |Igual que la compatibilidad de Exchange Server 2010, con la incorporación de  <br/>&bull;&nbsp;&nbsp;Almacén de contactos unificado  <br/>&bull;&nbsp;&nbsp;Imágenes de alta resolución  <br/>&bull;&nbsp;&nbsp;Integración de archivado  <br/> **Nota:** Para obtener más información, consulte [integrar Skype empresarial Server con Exchange Server](../../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md).  <br/> |
|Exchange Server 2010  <br/>(Solo Skype empresarial Server 2015) |Las siguientes características solo están disponibles mediante EWS:  <br/>&bull;&nbsp;&nbsp;Leer o eliminar elementos de la carpeta Historial de conversaciones  <br/>&bull;&nbsp;&nbsp;Leer o eliminar elementos de correo de voz  <br/>&bull;&nbsp;&nbsp;Mostrar la información de disponibilidad extendida y la ubicación y el asunto de la reunión  <br/>&bull;&nbsp;&nbsp;Sincronización de contactos de Exchange  <br/> Las carpetas públicas son opcionales en Exchange Server 2010.  <br/> |
   
## <a name="see-also"></a>Vea también
 
[Requisitos del cliente de Windows y asistencia de software](windows-requirements.md)
  
[Planear clientes de reuniones (aplicación web y aplicación reuniones)](meetings-clients.md)

