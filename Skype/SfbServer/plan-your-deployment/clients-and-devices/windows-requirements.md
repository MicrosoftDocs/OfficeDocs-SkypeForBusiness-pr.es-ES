---
title: Requisitos de cliente de Windows y compatibilidad con software
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
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a6851e38-ba9a-4f19-9aa7-d8accf4d62b3
description: 'Resumen: revise los requisitos de soporte técnico del cliente de Windows al planear Skype Empresarial Server.'
ms.openlocfilehash: 105c4ec8824b2b6f5f7a68349659ca10bb82c737
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816070"
---
# <a name="windows-client-requirements-and-software-support"></a>Requisitos de cliente de Windows y compatibilidad con software
 
**Resumen:** Revise los requisitos de soporte técnico del cliente de Windows al planear Skype Empresarial Server.
  
En esta sección se resume el software necesario para admitir los clientes de Windows de Skype Empresarial. Estos clientes se instalan cuando se instala Microsoft 365 u Office 365, y también están disponibles en Descargar Skype Empresarial en todos [los dispositivos.](https://products.office.com/skype-for-business/download-app?tab=tabs-3)
  
> [!NOTE]
> El complemento de reunión en línea para Skype Empresarial, que admite la administración de reuniones desde el cliente de mensajería y colaboración de Outlook, se instala automáticamente con Skype Empresarial. 
  
**Software necesario para el cliente de Skype Empresarial y el complemento de reunión en línea**

|**Componente del sistema**|**Versiones compatibles**|
|:-----|:-----|
|Sistema operativo Windows  <br/> |Windows 10  <br/> Windows 8.1  <br/> Windows 8 <br/> Windows Server 2008 R2 o posterior con el service pack más reciente  <br/> **Nota:** Skype Empresarial y el complemento de reunión en línea para Skype Empresarial no se admiten en Windows Vista o Windows XP (ninguna versión). <br/> |
|Instalación y actualizaciones  <br/> |Permisos y derechos de administrador  <br/> |
|Explorador  <br/> |Microsoft Edge  <br/> Explorador de Internet Internet Internet Explorer 11  <br/>  Explorador internet Internet Explorer 10 <br/> Explorador internet Internet Explorer 9  <br/> Explorador de Internet Internet Explorer 8  <br/> Explorador internet Internet Explorer 7  <br/> Explorador web Mozilla Firefox  <br/>  Explorador web Google Chrome  <br/>**Nota:** Si usa Skype Empresarial con Microsoft Exchange Online y su organización ha implementado un proxy HTTP de autenticación, se requiere Internet Explorer 8 o posterior.           |
|Integración de Microsoft Office  <br/> | Outlook 2010 o posterior |
|Integración de Microsoft Exchange  <br/> | Microsoft Exchange Server 2010 o posterior  | 
   
## <a name="hardware"></a>Hardware

Consulte los requisitos de Microsoft 365 y Office [System](https://products.office.com/office-system-requirements) para el hardware necesario para ejecutar el cliente de Skype Empresarial.
  
## <a name="skype-meetings-app-and-skype-for-business-web-app"></a>Aplicación reuniones de Skype y aplicación web de Skype Empresarial 

La aplicación Reuniones de Skype y la aplicación web de Skype Empresarial admiten combinaciones específicas de sistemas operativos y exploradores. Para obtener más información, consulte [Plan for Meetings clients (Web App and Meetings App).](meetings-clients.md) 
  
## <a name="using-mandatory-profiles"></a>Uso de perfiles obligatorios

Si tiene previsto usar las características de conferencia de Skype Empresarial, evite usar perfiles obligatorios de Servicios de dominio de Active Directory para iniciar sesión en el cliente de Skype Empresarial. Dado que los perfiles obligatorios son perfiles de usuario de solo lectura, las claves de infraestructura de clave pública (PKI) necesarias para las conferencias de Skype Empresarial no se pueden guardar en el perfil. 
  
## <a name="system-requirements-for-skype-for-business-for-windows-phone"></a>Requisitos del sistema para Skype Empresarial para Windows Phone
 
 
Microsoft Skype Empresarial para Windows Phone proporciona mensajería instantánea (MI), presencia mejorada y telefonía para los usuarios de su organización que se conectan desde un smartphone o un dispositivo móvil Windows Professional. Los dispositivos móviles permiten a los usuarios ampliar el alcance de Skype Empresarial. En este tema se describen las consideraciones de planeación para Skype Empresarial para Windows Phone que incluyen la identificación de requisitos previos y requisitos técnicos, los componentes necesarios y las instrucciones de implementación.
  
### <a name="skype-for-business-for-windows-phone-prerequisites"></a>Requisitos previos de Skype Empresarial para Windows Phone

A continuación se indican los requisitos previos de Skype Empresarial para Windows Phone.
  
- Windows Phone 8.1 o posterior.
    
- El dispositivo Windows Phone debe tener las últimas actualizaciones disponibles de Microsoft. Para obtener más información, consulte la sección Windows Phone 8.1 en el historial de actualizaciones [de Windows Phone 8.](https://go.microsoft.com/fwlink/p/?LinkID=281961)
    
- El dispositivo debe tener 22 MB de espacio disponible en disco.
    
- El usuario debe tener un plan de voz y de datos de un operador.


## <a name="see-also"></a>Vea también

[Planeación de clientes de reuniones (aplicación web y aplicación reuniones)](meetings-clients.md)
  
[Requisitos de cliente de Skype Empresarial en Mac](mac-requirements.md)

[Descargar Skype Empresarial en todos los dispositivos](https://products.office.com/skype-for-business/download-app?tab=tabs-3)
  
[Requisitos del sistema de Microsoft 365 y Office](https://products.office.com/office-system-requirements)
