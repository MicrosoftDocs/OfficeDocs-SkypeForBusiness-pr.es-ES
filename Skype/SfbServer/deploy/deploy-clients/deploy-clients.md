---
title: Implementar clientes para Skype empresarial Server
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: PhillipGarding
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3d10abf2-d484-4fa0-8f10-4a5f9dfba4f5
description: 'Resumen: información general sobre los métodos de instalación de clientes empresariales para Skype empresarial.'
ms.openlocfilehash: df9ac5356c05001df09168ca619ffc200b35ea4f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34282447"
---
# <a name="deploy-clients-for-skype-for-business-server"></a>Implementar clientes para Skype empresarial Server
 
**Resumen:** Información general sobre los métodos de instalación de clientes empresariales para Skype empresarial.
  
La forma de implementar Skype empresarial para sus usuarios depende de si compró Skype empresarial como parte de un plan de Office 365 o si compró una versión de licencia por volumen de Skype empresarial. 
  
- **Office 365** Si tiene un plan 365 de Office que incluye Skype empresarial, la tecnología de instalación que se usa se denomina hacer clic y ejecutar. Con Office 365, puede permitir que los usuarios instalen Skype empresarial por sí mismos desde el portal de Office 365. O bien, puede implementar Skype empresarial para sus usuarios descargando el software en la red local y, a continuación, usando las herramientas de implementación de software existentes, como Microsoft System Center Configuration Manager. Para obtener información sobre la instalación de Skype empresarial que se incluye con Office 365, consulte [implementar el cliente de Skype empresarial en office 365](https://support.office.com/article/8c563b81-22c9-4024-9efe-9fe28c7bbc96).
    
- **Licencias por volumen** Si tiene una versión de licencia por volumen del cliente de Skype empresarial 2015 o 2016, la tecnología de instalación que se usa es Windows Installer (MSI). Un paquete de instalación basado en Windows Installer consta de varios archivos MSI. Un paquete MSI principal independiente del idioma se combina con uno o más paquetes específicos del idioma para formar un producto completo. La instalación combina los paquetes individuales y realiza tareas de mantenimiento y personalización durante y después de finalizar la instalación de Office en los equipos de los usuarios. El cliente de Skype empresarial 2019 usa instaladores de hacer clic y ejecutar.
    
En los temas de esta sección se describe cómo usar y personalizar Windows Installer para implementar el cliente de Skype empresarial a los usuarios a través de los procedimientos normales.
  
> [!NOTE]
> El complemento de reunión de Skype para Microsoft Office, que admite la administración de reuniones desde el cliente de mensajería y colaboración de Outlook, se instala automáticamente con los clientes de Skype empresarial. 
  
> [!NOTE]
> El programa de instalación de Office 365 no desinstala versiones anteriores de Lync. El cliente de Skype empresarial se instala en paralelo con otros clientes de Lync. 
  
## <a name="installing-windows-clients"></a>Instalación de clientes de Windows

- [Personalizar la instalación del cliente de Windows en Skype empresarial Server](customize-windows-client-installation.md)
    
- [Configure the client experience with Skype for Business](configure-the-client-experience.md)
    
- [Configurar la lista de contactos inteligentes en Skype Empresarial Server](configure-smart-contacts-list.md)
    
## <a name="installing-device-clients"></a>Instalar clientes de dispositivos

- [Install and test Skype for Business for Windows Phone](windows-phone.md)
    
- [Install and test Skype for Business for iOS](ios.md)
    
    
- [Implementar el complemento VDI para Lync con Skype empresarial Server](deploy-the-lync-vdi-plug-in.md)
    
- [Implementar clientes descargables en Internet en Skype empresarial Server](deploy-web-downloadable-clients.md)
    
- [Personalizar la experiencia del cliente de Mac en Skype Empresarial](customize-the-mac-client-experience.md)
    
## <a name="see-also"></a>Vea también

[Implementar el cliente de Skype empresarial en Office 365](../../../SfbOnline/set-up-skype-for-business-online/deploy-the-skype-for-business-client-in-office-365.md)
