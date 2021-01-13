---
title: Compatibilidad de Skype Empresarial con aplicaciones de Office
ms.author: v-cichur
author: cichur
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
description: Comprenda las formas en que puede acceder a las características de Skype Empresarial desde Outlook y otras aplicaciones Microsoft Office cliente.
ms.openlocfilehash: b3d792d5e6376e4d845aa74f0585acf7d9a70d81
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802740"
---
# <a name="skype-for-business-compatibility-with-office-apps"></a>Compatibilidad de Skype Empresarial con aplicaciones de Office
 
Comprenda las formas en que puede acceder a las características de Skype Empresarial desde Outlook y otras aplicaciones Microsoft Office cliente.
  
En este tema se describe la compatibilidad de Skype Empresarial con varias versiones de Microsoft Office conjuntos de aplicaciones. 
  
## <a name="office-and-skype-for-business"></a>Office y Skype Empresarial

En la tabla siguiente se describen las características de Skype Empresarial que son compatibles con varias versiones de Office una vez que Exchange se implementa e integra como se describe en Integrar Skype Empresarial [Server con Exchange Server](../../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md).
  
**Compatibilidad de skype empresarial y Microsoft Office empresarial**

|**Característica**|**Microsoft Office 2010**|**Microsoft Office 2013, 2015 y 2016**|**Office 2016 para Mac &#x2776;** |
|:-----|:-----|:-----|:-----|
|**Características de Outlook** ||||
|Personalizar las invitaciones a reuniones de Outlook (agregar logotipo, dirección URL de ayuda, aviso de declinación de responsabilidades, texto del pie de página)  |No  |Sí   |Sí|
|Configurar la opción de reunión para silenciar el audio y el vídeo de los asistentes de forma predeterminada    |No    |Sí    |No    |
|Almacén de contactos unificado para administrar listas de contactos en Office y Skype Empresarial    |No    |Sí (requiere Exchange 2013 o posterior)    |Sí    |
|Imágenes de perfil de alta resolución    |No    |Sí (requiere Exchange 2013 o posterior)    |Sí    |
|Estado de presencia en los campos De, Para y CC de Microsoft Outlook    |Sí    |Sí    |Sí    |
|Responder con mensajería instantánea o llamada desde el menú de disponibilidad    |Sí (desde la tarjeta de contacto)    |Sí (desde la tarjeta de contacto)    |Sí (desde la tarjeta de contacto)    |
|Estado de presencia en una solicitud de reunión en la Asistente para programación local    |Sí    |Sí    |No    |
|Responder con mensajería instantánea o llamada desde la barra de herramientas o la cinta de opciones en un mensaje de correo electrónico recibido    |Sí    |Sí    |Sí    |
|**Otras aplicaciones de Office**   ||||
|Notas compartidas de OneNote    |No    |Sí    |No    |
|Instalación integrada en el programa de instalación de Office    |No    |Sí    |No    |
|Contenido de presentación de PowerPoint    |Sí    |Sí (VBSS también disponible)    |Sí    |
|Mensajería instantánea y presencia en archivos de Microsoft Word y Microsoft Excel (etiquetas inteligentes habilitadas)    |Solo Microsoft Word    |Solo Microsoft Word    |No    |
|Mensajería instantánea y presencia en sitios de Microsoft SharePoint (outlook debe estar instalado)    |Sí    |Sí    |No    |
   
&#x2776;: supone que ha instalado y está ejecutando actualmente un cliente de Skype Empresarial en Mac o el cliente de Lync 2011 para Mac.
  
## <a name="exchange-server-and-skype-for-business"></a>Exchange Server y Skype Empresarial

En la tabla siguiente se describe la compatibilidad de Skype Empresarial con varias versiones de Exchange Server. Outlook debe estar instalado en el equipo cliente para controlar las llamadas MAPI extendidas y algunas características requieren el uso de servicios Web Exchange (EWS).
  
**Compatibilidad de skype empresarial y Exchange Server empresarial**

|**Exchange Server versión**|**Soporte técnico de Skype Empresarial**|
|:-----|:-----|
|Exchange Server 2019 (solo Skype Empresarial Server 2019) |Igual que Exchange Server soporte técnico de 2013    |
|Exchange Server 2016    |Igual que Exchange Server soporte técnico de 2013  <br/> |
|Exchange Server 2013  <br/> |Igual que Exchange Server soporte técnico de 2010, con la adición de  <br/>&bull;&nbsp;&nbsp;Almacén de contactos unificado  <br/>&bull;&nbsp;&nbsp;Imágenes de alta resolución  <br/>&bull;&nbsp;&nbsp;Integración de archivado  <br/> **Nota:** Para obtener más información, [consulte Integrar Skype Empresarial Server con Exchange Server](../../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md).  <br/> |
|Exchange Server 2010  <br/>(Solo Skype Empresarial Server 2015) |Las siguientes características solo están disponibles a través de EWS:  <br/>&bull;&nbsp;&nbsp;Leer o eliminar elementos de la carpeta Historial de conversaciones  <br/>&bull;&nbsp;&nbsp;Leer o eliminar elementos de correo de voz  <br/>&bull;&nbsp;&nbsp;Mostrar información de disponibilidad extendida, asunto y ubicación de la reunión  <br/>&bull;&nbsp;&nbsp;Sincronización de contactos de Exchange  <br/> Las carpetas públicas son opcionales en Exchange Server 2010.  <br/> |
   
## <a name="see-also"></a>Ver también
 
[Requisitos de cliente de Windows y compatibilidad con software](windows-requirements.md)
  
[Planeación de clientes de reuniones (aplicación web y aplicación de reuniones)](meetings-clients.md)

