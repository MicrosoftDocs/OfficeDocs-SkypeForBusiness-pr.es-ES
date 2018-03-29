---
title: Requisitos del cliente de Windows y soporte de software
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/16/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: a6851e38-ba9a-4f19-9aa7-d8accf4d62b3
description: 'Resumen: Revisar los requisitos de asistencia del cliente de Windows mientras se planea Skype para Business Server 2015.'
ms.openlocfilehash: 1a9af80b55073240a53843c9fee912c0c521ba73
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="windows-client-requirements-and-software-support"></a>Requisitos del cliente de Windows y soporte de software
 
**Resumen:** Revise los requisitos de asistencia del cliente de Windows mientras se planea Skype para Business Server 2015.
  
Esta sección resume el software necesario para admitir el Skype para 2015 de negocios y clientes de Windows de 2016.
  
Estos clientes se instalan cuando se instala Office 365 y también están disponibles en [Descargar Skype para el negocio a través de todos los dispositivos](https://products.office.com/en-us/skype-for-business/download-app?tab=tabs-3).
  
> [!NOTE]
> El complemento de reunión en línea para Skype para el negocio, que admite la administración de reuniones desde dentro del cliente de mensajería y colaboración de Outlook, se instala automáticamente con Skype para el negocio. 
  
**Software requerido para Skype para empresas y la reunión en línea complemento de Skype para empresas**


|**Componente del sistema**|**Versiones compatibles**|
|:-----|:-----|
|Sistema operativo Windows  <br/> |Windows 10  <br/> Windows 8.1  <br/> Windows 8  <br/> Sistema operativo Windows 7  <br/> Windows Server 2008 R2 con el service pack más reciente  <br/> **Nota:** Skype para el negocio y el complemento de reunión en línea para Skype para el negocio no se admiten en Windows Vista o Windows XP (cualquier versión). <br/> |
|Instalación y actualizaciones  <br/> |Permisos y derechos de administrador  <br/> |
|Explorador  <br/> |Microsoft Edge  <br/> Explorador de Internet de Internet Explorer 11  <br/>  Explorador de Internet de Internet Explorer 10 <br/> Explorador de Internet de Internet Explorer 9  <br/> Explorador de Internet de Internet Explorer 8  <br/> Explorador de Internet de Internet Explorer 7  <br/> Explorador web Mozilla Firefox  <br/> **Nota:** Si utiliza Skype para empresas con Microsoft Exchange Online y su organización ha implementado un servidor de proxy de autenticación HTTP, Internet Explorer 8 o posterior es necesario.           |
|Integración de Microsoft Office  <br/> |Para todo el conjunto de características de integración:  <br/> Cliente de mensajería y colaboración • outlook 2016  <br/> Cliente de mensajería y colaboración • outlook 2013  <br/> Cliente de mensajería y colaboración • outlook 2010  <br/> |
|Integración de Microsoft Exchange  <br/> |• Microsoft Exchange Server de 2016  <br/> • Microsoft Exchange Server de 2013  <br/> • Microsoft Exchange Server 2010  <br/> |
   
## <a name="hardware"></a>Hardware

Consulte los [requisitos del sistema](https://products.office.com/en-us/office-system-requirements) de Office 365 para el hardware necesario para ejecutar el Skype para el cliente de Business.
  
## <a name="skype-for-business-web-app-browsers"></a>Skype para exploradores Web App de negocio

Skype para el negocio de la aplicación Web admite combinaciones específicas de sistemas operativos y exploradores. Para obtener información detallada, consulte [Plan para clientes de reuniones (Web App y App de reuniones)](meetings-clients.md). 
  
## <a name="microsoft-office-supportability"></a>Compatibilidad con Microsoft Office

Skype para clientes Business Server 2015 admiten la integración con varias versiones de Microsoft Office.
  
- Skype para características de integración empresarial son compatibles con Outlook 2016 2013 de Outlook y Outlook 2010.
    
- Skype para características de integración empresarial son compatibles con Microsoft Exchange Server 2016 2013 de Microsoft Exchange Server y Microsoft Exchange Server 2010.
    
- El complemento de reunión en línea para Skype para empresas es compatible con Microsoft Office 2010, Office 2013 y 2016 de Office.
    
## <a name="using-mandatory-profiles"></a>Uso de perfiles obligatorios

Si piensa utilizar el Skype para las características de conferencia de negocios, evite utilizar perfiles obligatorios de servicios de dominio de Active Directory para iniciar sesión en el Skype para cliente de empresa. Dado que los perfiles obligatorios son perfiles de usuario de sólo lectura, las claves de la infraestructura de claves públicas (PKI) que se requieren para Skype para conferencias de empresa no se puede guardar en el perfil. 
  
## <a name="macintosh-operating-systems"></a>Sistemas operativos Macintosh

El Skype para el negocio en los requerimientos de soporte de Mac se detallan en [Skype para empresas sobre los requisitos de cliente de Mac](mac-requirements.md).
  
## <a name="see-also"></a>Vea también

#### 

[Plan para clientes de reuniones (Web App y App de reuniones)](meetings-clients.md)
  
[Skype para empresas sobre los requisitos del cliente Mac](mac-requirements.md)
#### 

[Descargar Skype para el negocio a través de todos los dispositivos](https://products.office.com/en-us/skype-for-business/download-app?tab=tabs-3)
  
[Requisitos del sistema de Office 365](https://products.office.com/en-us/office-system-requirements)

