---
title: Windows cliente y compatibilidad con software
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
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a6851e38-ba9a-4f19-9aa7-d8accf4d62b3
description: 'Summary: Review the Windows client support requirements while planning Skype Empresarial Server.'
ms.openlocfilehash: 755f60030c905bfb5a5f488e2573c12b3396ab1e
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/26/2021
ms.locfileid: "58627952"
---
# <a name="windows-client-requirements-and-software-support"></a>Windows cliente y compatibilidad con software
 
**Resumen:** Revise los requisitos Windows soporte técnico del cliente mientras planea Skype Empresarial Server.
  
En esta sección se resume el software necesario para admitir los Skype Empresarial Windows cliente. Estos clientes se instalan Microsoft 365 o Office 365, y también están disponibles en [Descargar Skype Empresarial todos los dispositivos.](https://products.office.com/skype-for-business/download-app?tab=tabs-3)
  
> [!NOTE]
> El complemento de reunión en línea para Skype Empresarial, que admite la administración de reuniones desde el cliente de colaboración y mensajería de Outlook, se instala automáticamente con Skype Empresarial. 
  
**Software necesario para Skype Empresarial cliente y el complemento de reunión en línea**

|**Componente del sistema**|**Versiones compatibles**|
|:-----|:-----|
|Windows Sistema operativo  <br/> |Windows 10  <br/> Windows 8.1  <br/> Windows 8 <br/> Windows Server 2008 R2 o posterior con el service pack más reciente  <br/> **Nota:** Skype Empresarial y el complemento de reunión en línea para Skype Empresarial no se admiten en Windows Vista o Windows XP (cualquier versión). <br/> |
|Instalación y actualizaciones  <br/> |Permisos y derechos de administrador  <br/> |
|Explorador  <br/> |Microsoft Edge  <br/> Explorador de Internet Explorer 11  <br/>  Internet Explorer 10 Explorador de Internet <br/> Explorador de Internet Explorer 9  <br/> Explorador de Internet Explorer 8  <br/> Explorador de Internet Explorer 7  <br/> Explorador web Mozilla Firefox  <br/>  Explorador web de Google Chrome  <br/>**Nota:** Si está usando Skype Empresarial con Microsoft Exchange Online y su organización ha implementado un proxy HTTP de autenticación, se requiere Internet Explorer 8 o posterior.           |
|Integración de Microsoft Office  <br/> | Outlook 2010 o posterior |
|Integración de Microsoft Exchange  <br/> | Microsoft Exchange Server 2010 o posterior  | 
   
## <a name="hardware"></a>Hardware

Consulte los requisitos Microsoft 365 y Office [system](https://products.office.com/office-system-requirements) para el hardware necesario para ejecutar el Skype Empresarial cliente.
  
## <a name="skype-meetings-app-and-skype-for-business-web-app"></a>Skype Meetings App y aplicación web de Skype Empresarial 

La Skype Meetings App y aplicación web de Skype Empresarial combinaciones específicas de sistemas operativos y exploradores. Para obtener más información, vea [Plan for Meetings clients (Web App and Meetings App).](meetings-clients.md) 
  
## <a name="using-mandatory-profiles"></a>Uso de perfiles obligatorios

Si tiene previsto usar las Skype Empresarial de conferencia, evite usar perfiles obligatorios de Servicios de dominio de Active Directory para iniciar sesión en el Skype Empresarial cliente. Dado que los perfiles obligatorios son perfiles de usuario de solo lectura, las claves de infraestructura de clave pública (PKI) necesarias para las conferencias Skype Empresarial no se pueden guardar en el perfil. 
  
## <a name="system-requirements-for-skype-for-business-for-windows-phone"></a>Requisitos del sistema para Skype Empresarial para Windows Phone
 
 
Microsoft Skype Empresarial para Windows Phone proporciona mensajería instantánea (MI), presencia mejorada y telefonía para los usuarios de la organización que se conectan desde un smartphone o un Windows Professional móvil. Los dispositivos móviles permiten a los usuarios ampliar el alcance de Skype Empresarial. En este tema se describen las consideraciones de planeación Skype Empresarial para Windows Phone que incluyen la identificación de requisitos previos y requisitos técnicos, los componentes necesarios y las instrucciones de implementación.
  
### <a name="skype-for-business-for-windows-phone-prerequisites"></a>Skype Empresarial para Windows Phone Requisitos previos

A continuación se indican Skype Empresarial para Windows Phone requisitos previos.
  
- Windows Phone 8.1 o posterior.
    
- El Windows Phone dispositivo debe tener las actualizaciones más recientes disponibles de Microsoft. Para obtener más información, vea Windows Phone sección 8.1 en [Windows Phone historial de actualizaciones 8](https://go.microsoft.com/fwlink/p/?LinkID=281961).
    
- El dispositivo debe tener 22 MB de espacio en disco disponible.
    
- El usuario debe tener un plan de voz y de datos de un operador.


## <a name="see-also"></a>Consulte también

[Plan for Meetings clients (Web App and Meetings App)](meetings-clients.md)
  
[Skype Empresarial requisitos de cliente de Mac](mac-requirements.md)

[Descargar Skype Empresarial todos los dispositivos](https://products.office.com/skype-for-business/download-app?tab=tabs-3)
  
[Microsoft 365 y Office del sistema](https://products.office.com/office-system-requirements)
