---
title: Los requisitos de cliente de Windows y la compatibilidad de software
ms.author: jambirk
author: jambirk
ms.reviewer: PhillipGarding
manager: serdars
ms.date: 2/16/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a6851e38-ba9a-4f19-9aa7-d8accf4d62b3
description: 'Resumen: Revise los requisitos de soporte técnico de cliente de Windows durante la planeación de Skype para Business Server.'
ms.openlocfilehash: fec7996bccddf68fdeb59b8f9e0a185d5c5f18c7
ms.sourcegitcommit: b265545216ff36772d5dc2df381a9046bc71098e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/13/2018
ms.locfileid: "23965637"
---
# <a name="windows-client-requirements-and-software-support"></a>Los requisitos de cliente de Windows y la compatibilidad de software
 
**Resumen:** Revise los requisitos de soporte técnico de cliente de Windows cuando planee Skype para Business Server.
  
Esta sección resume el software necesario para admitir la Skype para clientes empresariales de Windows.  Estos clientes se instalan cuando se instala Office 365 y también están disponibles en [Descargar Skype para la empresa a través de todos los dispositivos](https://products.office.com/en-us/skype-for-business/download-app?tab=tabs-3).
  
> [!NOTE]
> El complemento de reunión en línea para Skype para la empresa, que admite la administración de la reunión desde el cliente de mensajería y colaboración de Outlook, se instala automáticamente con Skype para la empresa. 
  
**Software necesario para el complemento de reunión en línea y Skype para clientes empresariales**

|**Componente del sistema**|**Versiones compatibles**|
|:-----|:-----|
|Sistema operativo Windows  <br/> |Windows 10  <br/> Windows 8.1  <br/> Windows 8  <br/> Sistema operativo Windows 7  <br/> Windows Server 2008 R2 o posterior con el service pack más reciente  <br/> **Nota:** Skype para la empresa y el complemento de reunión en línea para Skype para la empresa no se admiten en Windows Vista o Windows XP (cualquier versión). <br/> |
|Instalación y actualizaciones  <br/> |Permisos y derechos de administrador  <br/> |
|Explorador  <br/> |Microsoft Edge  <br/> Explorador de Internet de Internet Explorer 11  <br/>  Explorador de Internet de Internet Explorer 10 <br/> Explorador de Internet de Internet Explorer 9  <br/> Explorador de Internet de Internet Explorer 8  <br/> Explorador de Internet de Internet Explorer 7  <br/> Explorador web Mozilla Firefox  <br/>  Explorador web de Google Chrome  <br/>**Nota:** Si usa Skype para la empresa con Microsoft Exchange Online y su organización ha implementado a un proxy HTTP de autenticación, Internet Explorer 8 o posterior es necesario.           |
|Integración de Microsoft Office  <br/> | Outlook 2010 o posterior |
|Integración de Microsoft Exchange  <br/> | Microsoft Exchange Server 2010 o posterior  | 
   
## <a name="hardware"></a>Hardware

Hacer referencia a los [requisitos del sistema](https://products.office.com/en-us/office-system-requirements) de Office 365 para el hardware necesario para ejecutar el Skype para clientes empresariales.
  
## <a name="skype-meetings-app-and-skype-for-business-web-app"></a>Aplicación de las reuniones de Skype y Skype para la aplicación empresarial de Web 

La aplicación de las reuniones de Skype y Skype para la aplicación empresarial de Web admiten combinaciones específicas de sistemas operativos y exploradores. Para obtener información detallada, consulte [Plan para clientes de las reuniones (Web App y aplicación de las reuniones)](meetings-clients.md). 
  
## <a name="using-mandatory-profiles"></a>Uso de perfiles obligatorios

Si planea usar el Skype para las características de conferencia de negocio, evitar el uso de perfiles obligatorios de servicios de dominio de Active Directory para iniciar sesión en el Skype para clientes empresariales. Dado que los perfiles obligatorios son los perfiles de usuario de sólo lectura, las claves de la infraestructura de clave pública (PKI) que son necesarias para Skype para conferencias de negocio no pueden guardarse en el perfil. 
  
## <a name="system-requirements-for-skype-for-business-for-windows-phone"></a>Requisitos del sistema para Skype Empresarial para Windows Phone
 
 
Microsoft Skype para empresarial para Windows Phone proporciona mensajería instantánea (IM), presencia ampliada y telefonía para usuarios de la organización que se conectan desde un smartphone o un dispositivo móvil Windows Professional. Los dispositivos móviles permiten a los usuarios ampliar el alcance de Skype para la empresa. En este tema se describe las consideraciones de planeación de Skype para empresarial para Windows Phone que incluyen la identificación de los requisitos previos y requisitos técnicos, componentes requeridos y orientación sobre la implementación.
  
### <a name="skype-for-business-for-windows-phone-prerequisites"></a>Requisitos previos de Skype Empresarial para Windows Phone

Los siguientes son los Skype para los requisitos previos de negocio para Windows Phone.
  
- Windows Phone 8.1 o posterior.
    
- El dispositivo Windows Phone necesita tener las últimas actualizaciones disponibles en Microsoft. Para obtener información detallada, vea la sección de Windows Phone 8.1 en [Windows Phone 8 historial de actualización](https://go.microsoft.com/fwlink/p/?LinkID=281961).
    
- El dispositivo necesita tener 22 MB de espacio disponible en disco.
    
- El usuario necesita tener un plan de voz y de datos de un operador.


## <a name="see-also"></a>Vea también

[Planeación de los clientes de las reuniones (Web App y aplicación de las reuniones)](meetings-clients.md)
  
[Skype para la empresa en los requisitos de cliente de Mac](mac-requirements.md)

[Descargar Skype para la empresa a través de todos los dispositivos](https://products.office.com/en-us/skype-for-business/download-app?tab=tabs-3)
  
[Requisitos del sistema de Office 365](https://products.office.com/en-us/office-system-requirements)