---
title: Implementar clientes para Skype Empresarial Server
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: PhillipGarding
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 3d10abf2-d484-4fa0-8f10-4a5f9dfba4f5
description: 'Resumen: información general sobre los métodos de instalación de clientes empresariales para Skype Empresarial.'
ms.openlocfilehash: ccaed5620c7f524a5a39fc6a35e6d688cd97a0eb
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49805700"
---
# <a name="deploy-clients-for-skype-for-business-server"></a>Implementar clientes para Skype Empresarial Server
 
**Resumen:** Información general sobre los métodos de instalación de clientes empresariales para Skype Empresarial.
  
La forma de implementar Skype Empresarial para los usuarios depende de si compró Skype Empresarial como parte de un plan de Microsoft 365 u Office 365 o si compró una versión con licencia por volumen de Skype Empresarial. 
  
- **Microsoft 365 u Office 365** Si tiene un plan de Microsoft 365 u Office 365 que incluya Skype Empresarial, la tecnología de instalación que se usa se denomina Hacer clic y ejecutar. Puede permitir que los usuarios instalen Skype Empresarial por sí mismos desde el Centro de administración de Microsoft 365. O bien, puede implementar Skype Empresarial para sus usuarios descargando el software en la red local y, a continuación, usando las herramientas de implementación de software existentes, como con Microsoft Endpoint Configuration Manager. Para obtener información de instalación sobre Skype Empresarial que se incluye con Microsoft 365 y Office 365, vea Implementar el cliente de Skype Empresarial en [Microsoft 365 u Office 365.](https://support.office.com/article/8c563b81-22c9-4024-9efe-9fe28c7bbc96)
    
- **Licencia por volumen** Si tiene una versión con licencia por volumen del cliente de Skype Empresarial 2015 o 2016, la tecnología de instalación que se usa es Windows Installer (MSI). Un paquete de instalación basado en Windows Installer consta de varios archivos MSI. Un paquete MSI central de lenguaje neutral se combina con uno o más paquetes de lenguaje específico para hacer un producto completo. La instalación junta los paquetes individuales y realiza tareas de mantenimiento y personalización durante y tras finalizar la instalación de Office en los equipos de los usuarios. El cliente de Skype Empresarial 2019 usa instaladores de Hacer clic y ejecutar.
    
Los temas de esta sección describen cómo usar y personalizar Windows Installer para implementar el cliente de Skype Empresarial para los usuarios a través de sus procedimientos normales.
  
> [!NOTE]
> El complemento de reunión de Skype para Microsoft Office, que admite la administración de reuniones desde el cliente de mensajería y colaboración de Outlook, se instala automáticamente con clientes de Skype Empresarial. 
  
> [!NOTE]
> Los programas de instalación de Microsoft 365 y Office 365 no desinstalan versiones anteriores de Lync. El cliente de Skype Empresarial se instala en paralelo con otros clientes de Lync. 
  
## <a name="installing-windows-clients"></a>Instalación de clientes de Windows

- [Personalizar la instalación de cliente de Windows en Skype Empresarial Server](customize-windows-client-installation.md)
    
- [Configurar la experiencia del cliente con Skype Empresarial](configure-the-client-experience.md)
    
- [Configurar la lista de contactos inteligentes en Skype Empresarial Server](configure-smart-contacts-list.md)
    
## <a name="installing-device-clients"></a>Instalación de clientes de dispositivos

- [Instalar y probar Skype Empresarial para Windows Phone](windows-phone.md)
    
- [Instalar y probar Skype Empresarial para iOS](ios.md)
    
    
- [Implementar el complemento Lync VDI con Skype Empresarial Server](deploy-the-lync-vdi-plug-in.md)
    
- [Implementar clientes web descargables en Skype Empresarial Server](deploy-web-downloadable-clients.md)
    
- [Personalizar la experiencia de cliente mac en Skype Empresarial](customize-the-mac-client-experience.md)
    
## <a name="see-also"></a>Vea también

[Implementar el cliente de Skype Empresarial en Microsoft 365 u Office 365](../../../SfbOnline/set-up-skype-for-business-online/deploy-the-skype-for-business-client-in-office-365.md)
