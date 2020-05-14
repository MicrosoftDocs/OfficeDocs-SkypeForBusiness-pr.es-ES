---
title: Implementación de clientes de Skype empresarial Server
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: PhillipGarding
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 3d10abf2-d484-4fa0-8f10-4a5f9dfba4f5
description: 'Resumen: información general sobre los métodos de instalación de cliente empresarial para Skype empresarial.'
ms.openlocfilehash: 8d6e59582c3c420d5752a84f793e6c3025b3c500
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/13/2020
ms.locfileid: "44220650"
---
# <a name="deploy-clients-for-skype-for-business-server"></a>Implementación de clientes de Skype empresarial Server
 
**Resumen:** Información general sobre los métodos de instalación de cliente empresarial para Skype empresarial.
  
La forma en que se implementa Skype empresarial para los usuarios depende de si compró Skype empresarial como parte de un plan de Microsoft 365 u Office 365 o si compró una versión de licencia por volumen de Skype empresarial. 
  
- **Microsoft 365 u Office 365** Si tiene un plan de Microsoft 365 u Office 365 que incluye Skype empresarial, la tecnología de instalación que se usa se llama hacer clic y ejecutar. Puede permitir que los usuarios instalen Skype empresarial por sí mismos desde el centro de administración de Microsoft 365. O bien, puede implementar Skype empresarial para los usuarios descargando el software en la red local y, a continuación, usando las herramientas de implementación de software existentes, como con Microsoft Endpoint Configuration Manager. Para obtener información sobre la instalación de Skype empresarial incluida con Microsoft 365 y Office 365, consulte [implementar el cliente de Skype empresarial en microsoft 365 u office 365](https://support.office.com/article/8c563b81-22c9-4024-9efe-9fe28c7bbc96).
    
- **Licencia por volumen** Si tiene una versión de licencia por volumen del cliente de Skype empresarial 2015 o 2016, la tecnología de instalación que se usa es Windows Installer (MSI). Un paquete de instalación basado en Windows Installer consta de varios archivos MSI. Un paquete MSI central de lenguaje neutral se combina con uno o más paquetes de lenguaje específico para hacer un producto completo. La instalación junta los paquetes individuales y realiza tareas de mantenimiento y personalización durante y tras finalizar la instalación de Office en los equipos de los usuarios. El cliente de Skype empresarial 2019 usa instaladores de hacer clic y ejecutar.
    
En los temas de esta sección se describe cómo usar y personalizar Windows Installer para implementar el cliente de Skype empresarial para los usuarios a través de los procedimientos normales.
  
> [!NOTE]
> El complemento de reunión de Skype para Microsoft Office, que admite la administración de reuniones desde el cliente de colaboración y mensajería de Outlook, se instala automáticamente con los clientes de Skype empresarial. 
  
> [!NOTE]
> Los programas de instalación de Microsoft 365 y Office 365 no desinstalan las versiones anteriores de Lync. El cliente de Skype empresarial se instala en paralelo con otros clientes de Lync. 
  
## <a name="installing-windows-clients"></a>Instalación de clientes de Windows

- [Personalización de la instalación del cliente de Windows en Skype empresarial Server](customize-windows-client-installation.md)
    
- [Configurar la experiencia de cliente con Skype empresarial](configure-the-client-experience.md)
    
- [Configurar la lista de contactos inteligentes en Skype empresarial Server](configure-smart-contacts-list.md)
    
## <a name="installing-device-clients"></a>Instalación de clientes de dispositivos

- [Instalar y probar Skype empresarial para Windows Phone](windows-phone.md)
    
- [Instalar y probar Skype empresarial para iOS](ios.md)
    
    
- [Implementar el complemento Lync VDI con Skype empresarial Server](deploy-the-lync-vdi-plug-in.md)
    
- [Implementar clientes Web descargables en Skype empresarial Server](deploy-web-downloadable-clients.md)
    
- [Personalización de la experiencia del cliente Mac en Skype empresarial](customize-the-mac-client-experience.md)
    
## <a name="see-also"></a>Vea también

[Implementar el cliente de Skype empresarial en Microsoft 365 u Office 365](../../../SfbOnline/set-up-skype-for-business-online/deploy-the-skype-for-business-client-in-office-365.md)
