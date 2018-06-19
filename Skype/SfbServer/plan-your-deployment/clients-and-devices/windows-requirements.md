---
title: Los requisitos de cliente de Windows y la compatibilidad de software
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/16/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a6851e38-ba9a-4f19-9aa7-d8accf4d62b3
description: 'Resumen: Revise los requisitos de soporte técnico de cliente de Windows durante la planeación de Skype para Business Server 2015.'
ms.openlocfilehash: bbfdef4a9ed811ca0bae7e07a45dbf24aa48d4cb
ms.sourcegitcommit: b14cfca231b618ec28cf9f4efe11cb3e8aceb34b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/19/2018
ms.locfileid: "19504085"
---
# <a name="windows-client-requirements-and-software-support"></a>Los requisitos de cliente de Windows y la compatibilidad de software
 
**Resumen:** Revise los requisitos de soporte técnico de cliente de Windows durante la planeación de Skype para Business Server 2015.
  
Esta sección resume el software necesario para admitir la Skype para 2015 empresarial y los clientes de Windows de 2016.
  
Estos clientes se instalan cuando se instala Office 365 y también están disponibles en [Descargar Skype para la empresa a través de todos los dispositivos](https://products.office.com/en-us/skype-for-business/download-app?tab=tabs-3).
  
> [!NOTE]
> El complemento de reunión en línea para Skype para la empresa, que admite la administración de la reunión desde el cliente de mensajería y colaboración de Outlook, se instala automáticamente con Skype para la empresa. 
  
**Software necesario para Skype para empresas y el Online Meeting Add-in para Skype para la empresa**


|**Componente del sistema**|**Versiones compatibles**|
|:-----|:-----|
|Sistema operativo Windows  <br/> |Windows 10  <br/> Windows 8.1  <br/> Windows 8  <br/> Sistema operativo Windows 7  <br/> Windows Server 2008 R2 con service pack más reciente  <br/> **Nota:** Skype para la empresa y el complemento de reunión en línea para Skype para la empresa no se admiten en Windows Vista o Windows XP (cualquier versión). <br/> |
|Instalación y actualizaciones  <br/> |Permisos y derechos de administrador  <br/> |
|Explorador  <br/> |Microsoft Edge  <br/> Explorador de Internet de Internet Explorer 11  <br/>  Explorador de Internet de Internet Explorer 10 <br/> Explorador de Internet de Internet Explorer 9  <br/> Explorador de Internet de Internet Explorer 8  <br/> Explorador de Internet de Internet Explorer 7  <br/> Explorador web Mozilla Firefox  <br/> **Nota:** Si usa Skype para la empresa con Microsoft Exchange Online y su organización ha implementado a un proxy HTTP de autenticación, Internet Explorer 8 o posterior es necesario.           |
|Integración de Microsoft Office  <br/> |Para todo el conjunto de características de integración:  <br/> Cliente de mensajería y colaboración • 2016 de outlook  <br/> Cliente de mensajería y colaboración • outlook 2013  <br/> Cliente de mensajería y colaboración • outlook 2010  <br/> |
|Integración de Microsoft Exchange  <br/> |• Microsoft Exchange Server 2016  <br/> • Microsoft Exchange Server 2013  <br/> • Microsoft Exchange Server 2010  <br/> |
   
## <a name="hardware"></a>Hardware

Hacer referencia a los [requisitos del sistema](https://products.office.com/en-us/office-system-requirements) de Office 365 para el hardware necesario para ejecutar el Skype para clientes empresariales.
  
## <a name="skype-for-business-web-app-browsers"></a>Skype para exploradores de aplicación Web de negocio

Skype para la aplicación empresarial de Web admite combinaciones específicas de sistemas operativos y exploradores. Para obtener información detallada, consulte [Plan para clientes de las reuniones (Web App y aplicación de las reuniones)](meetings-clients.md). 
  
## <a name="microsoft-office-supportability"></a>Compatibilidad con Microsoft Office

Skype para clientes empresariales Server 2015 admite la integración con distintas versiones de Microsoft Office.
  
- Skype para las características de integración empresarial son compatibles con Outlook 2016, Outlook 2013 y Outlook 2010.
    
- Skype para las características de integración empresarial son compatibles con Microsoft Exchange Server 2016, Microsoft Exchange Server 2013 y Microsoft Exchange Server 2010.
    
- El complemento de reunión en línea para Skype para la empresa es compatible con Office 2016, Office 2013 y Microsoft Office 2010.
    
## <a name="using-mandatory-profiles"></a>Uso de perfiles obligatorios

Si planea usar el Skype para las características de conferencia de negocio, evitar el uso de perfiles obligatorios de servicios de dominio de Active Directory para iniciar sesión en el Skype para clientes empresariales. Dado que los perfiles obligatorios son los perfiles de usuario de sólo lectura, las claves de la infraestructura de clave pública (PKI) que son necesarias para Skype para conferencias de negocio no pueden guardarse en el perfil. 
  
## <a name="macintosh-operating-systems"></a>Sistemas operativos Macintosh

El Skype para la empresa en los requisitos de compatibilidad con Mac se detallan en [Skype para la empresa en los requisitos de cliente de Mac](mac-requirements.md).
  
## <a name="see-also"></a>Vea también

[Planeación de los clientes de las reuniones (Web App y aplicación de las reuniones)](meetings-clients.md)
  
[Skype para la empresa en los requisitos de cliente de Mac](mac-requirements.md)

[Descargar Skype para la empresa a través de todos los dispositivos](https://products.office.com/en-us/skype-for-business/download-app?tab=tabs-3)
  
[Requisitos del sistema de Office 365](https://products.office.com/en-us/office-system-requirements)