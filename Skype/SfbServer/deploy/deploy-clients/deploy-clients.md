---
title: Implementar a clientes de Skype para Business Server
ms.author: chucked
author: chuckedmonson
manager: serdars
ms.audience: ITPro
ms.reviewer: PhillipGarding
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3d10abf2-d484-4fa0-8f10-4a5f9dfba4f5
description: 'Resumen: Información general de los métodos de instalación de cliente de empresa de Skype para la empresa.'
ms.openlocfilehash: 49eff64918deefe2ec169993557dd0f9dfbf6955
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212722"
---
# <a name="deploy-clients-for-skype-for-business-server"></a>Implementar a clientes de Skype para Business Server
 
**Resumen:** Información general de los métodos de instalación de cliente de empresa de Skype para la empresa.
  
Cómo implementar Skype para la empresa a los usuarios depende de si ha comprado Skype para la empresa como parte de un plan de Office 365 o ha comprado una versión con licencia por volumen de Skype para la empresa. 
  
- **Office 365** Si dispone de un plan de Office 365 que incluya Skype para la empresa, la tecnología de instalación que se utiliza se denomina Click-to-Run. Con Office 365, puede permitir a los usuarios instalar Skype para la empresa para sí mismos desde el portal de Office 365. O bien, puede implementar Skype para la empresa a los usuarios descargar el software en su red local y, a continuación, usando las herramientas de implementación de software existente, como con Microsoft System Center Configuration Manager. Para obtener información de instalación acerca de Skype para la empresa que se incluye con Office 365, vea [implementar el Skype para cliente empresarial en Office 365](https://support.office.com/article/8c563b81-22c9-4024-9efe-9fe28c7bbc96).
    
- **Con licencia por volumen** Si tiene una versión con licencia de volumen de la Skype para 2015 empresarial o el cliente de 2016, la tecnología de instalación que se utiliza es Windows Installer (MSI). Un paquete de instalación basada en Windows Installer consta de varios archivos MSI. Un paquete MSI principal independiente del idioma se combina con uno o más paquetes específicos del idioma para formar un producto completo. La instalación combina los paquetes individuales y realiza tareas de mantenimiento y personalización durante y después de finalizar la instalación de Office en los equipos de los usuarios. El Skype para cliente empresarial 2019 usa a instaladores de Click-to-Run.
    
En los temas de esta sección se describen cómo utilizar y personalizar Windows Installer para implementar la Skype para cliente de negocio para los usuarios a través de los procedimientos de normales.
  
> [!NOTE]
> El complemento de Skype Meeting para Microsoft Office, que admite la administración de la reunión desde el cliente de mensajería y colaboración de Outlook, se instala automáticamente con Skype para clientes empresariales. 
  
> [!NOTE]
> El programa de instalación de Office 365 no desinstala las versiones anteriores de Lync. El Skype para clientes empresariales instala en paralelo con otros clientes de Lync. 
  
## <a name="installing-windows-clients"></a>Instalación de los clientes de Windows

- [Personalizar la instalación de cliente de Windows en Skype para Business Server](customize-windows-client-installation.md)
    
- [Configure the client experience with Skype for Business](configure-the-client-experience.md)
    
- [Configurar la lista de contactos inteligentes en Skype Empresarial Server](configure-smart-contacts-list.md)
    
## <a name="installing-device-clients"></a>Instalación de los clientes de dispositivos

- [Install and test Skype for Business for Windows Phone](windows-phone.md)
    
- [Install and test Skype for Business for iOS](ios.md)
    
- [Implementar el Sistema de salas de Skype en Skype Empresarial Server](deploy-skype-room-system.md)
    
- [Implementación de salas de equipos de Microsoft](room-systems-v2.md)
    
- [Implementación del complemento Lync VDI con Skype para Business Server](deploy-the-lync-vdi-plug-in.md)
    
- [Implementar a los clientes que se pueden descargar de Web en Skype para Business Server](deploy-web-downloadable-clients.md)
    
- [Personalizar la experiencia del cliente de Mac en Skype Empresarial](customize-the-mac-client-experience.md)
    
## <a name="see-also"></a>Vea también

[Implementar el Skype para cliente empresarial en Office 365](../../../SfbOnline/set-up-skype-for-business-online/deploy-the-skype-for-business-client-in-office-365.md)