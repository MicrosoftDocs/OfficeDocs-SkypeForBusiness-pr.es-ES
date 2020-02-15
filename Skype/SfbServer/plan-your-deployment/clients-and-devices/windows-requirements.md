---
title: Requisitos del cliente de Windows y soporte técnico de software
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
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a6851e38-ba9a-4f19-9aa7-d8accf4d62b3
description: 'Resumen: Revise los requisitos de compatibilidad del cliente de Windows al planear Skype empresarial Server.'
ms.openlocfilehash: 0a556b2330427683c4d00577895f43f3cfede6d5
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42027961"
---
# <a name="windows-client-requirements-and-software-support"></a>Requisitos del cliente de Windows y soporte técnico de software
 
**Resumen:** Revise los requisitos de compatibilidad con el cliente de Windows al planear Skype empresarial Server.
  
En esta sección se resume el software necesario para admitir los clientes Windows de Skype empresarial.  Estos clientes se instalan cuando se instala Office 365 y también están disponibles en [descargar Skype empresarial en todos los dispositivos](https://products.office.com/skype-for-business/download-app?tab=tabs-3).
  
> [!NOTE]
> El complemento para reunión en línea de Skype empresarial, que admite la administración de reuniones desde dentro del cliente de colaboración y mensajería de Outlook, se instala automáticamente con Skype empresarial. 
  
**Software necesario para el cliente de Skype empresarial y el complemento para reunión en línea**

|**Componente del sistema**|**Versiones compatibles**|
|:-----|:-----|
|Sistema operativo Windows  <br/> |Windows 10  <br/> Windows 8.1  <br/> Windows 8  <br/> Sistema operativo Windows 7  <br/> Windows Server 2008 R2 o posterior con el Service Pack más reciente  <br/> **Nota:** Skype empresarial y el complemento para reunión en línea de Skype empresarial no son compatibles con Windows Vista o Windows XP (cualquier versión). <br/> |
|Instalación y actualizaciones  <br/> |Permisos y derechos de administrador  <br/> |
|Explorador  <br/> |Microsoft Edge  <br/> Explorador de Internet Internet Explorer 11  <br/>  Explorador de Internet de Internet Explorer 10 <br/> Explorador de Internet de Internet Explorer 9  <br/> Explorador de Internet Internet Explorer 8  <br/> Explorador de Internet Internet Explorer 7  <br/> Explorador web Mozilla Firefox  <br/>  Explorador web Google Chrome  <br/>**Nota:** Si usa Skype empresarial con Microsoft Exchange Online y su organización ha implementado un proxy HTTP de autenticación, se requiere Internet Explorer 8 o posterior.           |
|Integración de Microsoft Office  <br/> | Outlook 2010 o posterior |
|Integración de Microsoft Exchange  <br/> | Microsoft Exchange Server 2010 o posterior  | 
   
## <a name="hardware"></a>Hardware

Consulte los [requisitos del sistema](https://products.office.com/office-system-requirements) de Office 365 para el hardware necesario para ejecutar el cliente de Skype empresarial.
  
## <a name="skype-meetings-app-and-skype-for-business-web-app"></a>Aplicación de reuniones de Skype y aplicación Web de Skype empresarial 

La aplicación reuniones de Skype y la aplicación Web de Skype empresarial admiten combinaciones específicas de sistemas operativos y exploradores. Para obtener información detallada, consulte [Plan for Meetings clients (Web App and meettions APP)](meetings-clients.md). 
  
## <a name="using-mandatory-profiles"></a>Uso de perfiles obligatorios

Si planea usar las características de conferencia de Skype empresarial, evite usar perfiles obligatorios de servicios de dominio de Active Directory para iniciar sesión en el cliente de Skype empresarial. Debido a que los perfiles obligatorios son de solo lectura, las claves de infraestructura de clave pública (PKI) que se necesitan para las conferencias de Skype empresarial no se pueden guardar en el perfil. 
  
## <a name="system-requirements-for-skype-for-business-for-windows-phone"></a>Requisitos del sistema para Skype empresarial para Windows Phone
 
 
Microsoft Skype empresarial para Windows Phone ofrece mensajería instantánea, presencia mejorada y telefonía para los usuarios de la organización que se conectan desde un smartphone o un dispositivo móvil con Windows Professional. Los dispositivos móviles permiten a los usuarios ampliar el alcance de Skype empresarial. En este tema se describen las consideraciones de planeación de Skype empresarial para Windows Phone que incluyen la identificación de requisitos previos y requisitos técnicos, los componentes necesarios y la guía de implementación.
  
### <a name="skype-for-business-for-windows-phone-prerequisites"></a>Requisitos previos de Skype empresarial para Windows Phone

A continuación se muestran los requisitos previos de Skype empresarial para Windows Phone.
  
- Windows Phone 8,1 o posterior.
    
- El dispositivo Windows Phone debe tener las actualizaciones más recientes disponibles en Microsoft. Para obtener más información, consulte la sección de Windows Phone 8,1 en el [historial de actualizaciones de Windows Phone 8](https://go.microsoft.com/fwlink/p/?LinkID=281961).
    
- El dispositivo debe tener 22 MB de espacio disponible en disco.
    
- El usuario debe tener un plan de voz y de datos de un operador.


## <a name="see-also"></a>Consulte también

[Planeación de clientes de reuniones (aplicación web y aplicación de reuniones)](meetings-clients.md)
  
[Requisitos del cliente de Skype empresarial en Mac](mac-requirements.md)

[Descargar Skype empresarial en todos los dispositivos](https://products.office.com/skype-for-business/download-app?tab=tabs-3)
  
[Requisitos del sistema para Office 365](https://products.office.com/office-system-requirements)
