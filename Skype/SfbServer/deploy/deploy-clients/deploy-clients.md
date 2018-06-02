---
title: Implementar clientes para Skype Empresarial Server 2015
ms.author: chucked
author: chuckedmonson
manager: serdars
ms.date: 2/6/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3d10abf2-d484-4fa0-8f10-4a5f9dfba4f5
description: 'Resumen: Información general de los métodos de instalación de cliente de empresa de Skype para la empresa.'
ms.openlocfilehash: 4c1253613befd5bf71add33b7ab9cab826d4a490
ms.sourcegitcommit: a5b8b0a1e5ae5eb718e296ca6df6687368ee9174
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/02/2018
ms.locfileid: "19546472"
---
# <a name="deploy-clients-for-skype-for-business-server-2015"></a>Implementar clientes para Skype Empresarial Server 2015
 
**Resumen:** Información general de los métodos de instalación de cliente de empresa de Skype para la empresa.
  
Cómo implementar Skype para la empresa a los usuarios depende de si ha comprado Skype para la empresa como parte de un plan de Office 365 o ha comprado una versión con licencia por volumen de Skype para la empresa. 
  
- **Office 365** Si dispone de un plan de Office 365 que incluya Skype para la empresa, la tecnología de instalación que se utiliza se denomina Click-to-Run. Con Office 365, puede permitir a los usuarios instalar Skype para la empresa para sí mismos desde el portal de Office 365. O bien, puede implementar Skype para la empresa a los usuarios descargar el software en su red local y, a continuación, usando las herramientas de implementación de software existente, como con Microsoft System Center Configuration Manager. Para obtener información de instalación acerca de Skype para la empresa que se incluye con Office 365, vea [implementar el Skype para cliente empresarial en Office 365](https://support.office.com/article/8c563b81-22c9-4024-9efe-9fe28c7bbc96).
    
- **Con licencia por volumen** Si tiene una versión con licencia por volumen de Skype para la empresa, la tecnología de instalación que se utiliza es Windows Installer (MSI). Un paquete de instalación basada en Windows Installer consta de varios archivos MSI. Un paquete MSI principal independiente del idioma se combina con uno o más paquetes específicos del idioma para formar un producto completo. La instalación combina los paquetes individuales y realiza tareas de mantenimiento y personalización durante y después de finalizar la instalación de Office en los equipos de los usuarios.
    
En los temas de esta sección se describen cómo utilizar y personalizar Windows Installer para implementar la Skype para cliente de negocio para los usuarios a través de los procedimientos de normales.
  
> [!NOTE]
> El Online meeting Add-in para Skype para la empresa, cliente de mensajería y colaboración, que es compatible con administración desde dentro de Outlook de la reunión instala automáticamente con Skype para la empresa. 
  
> [!NOTE]
> El programa de instalación de Office 365 no desinstala las versiones anteriores de Lync u Office Communicator. El Skype para clientes empresariales instala en paralelo con otros clientes de Lync u Office Communicator. 
  
## <a name="installing-windows-clients"></a>Instalación de los clientes de Windows

- [Personalizar la instalación de cliente de Windows en Skype para Business Server 2015](customize-windows-client-installation.md)
    
- [Configurar la experiencia del cliente con Skype para la empresa](configure-the-client-experience.md)
    
- [Configuración de lista de contactos inteligente en Skype para Business Server](configure-smart-contacts-list.md)
    
## <a name="installing-device-clients"></a>Instalación de los clientes de dispositivos

- [Instalar y probar Skype para empresarial para Windows Phone](windows-phone.md)
    
- [Instalar y probar Skype para la empresa para iOS](ios.md)
    
- [Implementación del sistema de salas de Skype en Skype para Business Server](deploy-skype-room-system.md)
    
- [Implementación de salón de Skype v2 de sistemas](room-systems-v2.md)
    
- [Implementación del complemento Lync VDI con Skype para Business Server 2015](deploy-the-lync-vdi-plug-in.md)
    
- [Implementar a los clientes que se pueden descargar de Web en Skype para Business Server 2015](deploy-web-downloadable-clients.md)
    
- [Personalizar la experiencia del cliente Mac en Skype para la empresa](customize-the-mac-client-experience.md)
    
## <a name="see-also"></a>Vea también

[Implementar el Skype para cliente empresarial en Office 365](../../../SfbOnline/set-up-skype-for-business-online/deploy-the-skype-for-business-client-in-office-365.md)