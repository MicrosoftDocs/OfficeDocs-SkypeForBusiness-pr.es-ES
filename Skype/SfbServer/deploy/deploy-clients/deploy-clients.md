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
description: 'Resumen: Resumen de métodos de instalación de cliente de empresa de Skype para el negocio.'
ms.openlocfilehash: d41ce5b2fe9b4717a9af78fb3072ae0da48b72ec
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="deploy-clients-for-skype-for-business-server-2015"></a>Implementar clientes para Skype Empresarial Server 2015
 
**Resumen:** Resumen de métodos de instalación de cliente de empresa de Skype para el negocio.
  
Cómo implementar Skype para el negocio a los usuarios depende de si ha adquirido Skype para el negocio como parte de un plan de Office 365 o adquirir una versión con licencia de volumen de Skype para el negocio. 
  
- **Office 365** Si tienes un plan de Office 365 que incluye Skype para el negocio, la tecnología de instalación que se utiliza se llama hacer clic para ejecutar. Con Office 365, puede permitir a los usuarios instalar Skype para el negocio por sí mismos desde el portal de Office 365. O bien, puede implementar Skype para el negocio a los usuarios descargar el software en la red local y utilizando las herramientas de despliegue de software existente, como con Microsoft System Center Configuration Manager. Para obtener información de instalación acerca de Skype para el negocio que viene con Office 365, vea [implementar el Skype para cliente de negocio de Office 365](https://support.office.com/article/8c563b81-22c9-4024-9efe-9fe28c7bbc96).
    
- **Con licencia por volumen** Si tiene una versión de licencia por volumen de Skype para el negocio, la tecnología de instalación que se utiliza es Windows Installer (MSI). Un paquete de instalación basada en Windows Installer consta de varios archivos MSI. Un paquete MSI principal independiente del idioma se combina con uno o más paquetes específicos del idioma para formar un producto completo. La instalación combina los paquetes individuales y realiza tareas de mantenimiento y personalización durante y después de finalizar la instalación de Office en los equipos de los usuarios.
    
En los temas de esta sección describen cómo utilizar y personalizar Windows Installer para implementar el Skype para cliente de negocio a los usuarios a través de los procedimientos normales.
  
> [!NOTE]
> La reunión complemento de Skype para el negocio, el cliente de mensajería y colaboración, que admite reunión administración desde dentro de Outlook instala automáticamente con Skype para el negocio en línea. 
  
> [!NOTE]
> El programa de instalación de Office 365 desinstalar versiones anteriores de Lync o Office Communicator. El Skype para Business client instala side-by-side con otros clientes de Office Communicator o de Lync. 
  
## <a name="installing-windows-clients"></a>Instalar los clientes de Windows

- [Personalizar la instalación de cliente de Windows en Skype para Business Server 2015](customize-windows-client-installation.md)
    
- [Configurar la experiencia del cliente con Skype para empresas](configure-the-client-experience.md)
    
- [Configurar la lista de contactos inteligente de Skype para Business Server](configure-smart-contacts-list.md)
    
## <a name="installing-device-clients"></a>Instalar clientes de dispositivo

- [Instalar y probar Skype para negocios para Windows Phone](windows-phone.md)
    
- [Instalar y probar Skype para empresas para iOS](ios.md)
    
- [Implementar sistema de sala de Skype en Skype para Business Server](deploy-skype-room-system.md)
    
- [Implementar sala de Skype v2 de sistemas](room-systems-v2.md)
    
- [Implementar la VDI Lync complemento con Skype para Business Server 2015](deploy-the-lync-vdi-plug-in.md)
    
- [Implementar a clientes de Web descargables en Skype para Business Server 2015](deploy-web-downloadable-clients.md)
    
- [Personalizar la experiencia del cliente de Mac en Skype para empresas](customize-the-mac-client-experience.md)
    
## <a name="see-also"></a>Vea también

#### 

[Implementar el Skype para el cliente de negocio para su organización](https://support.officeppe.com/en-us/article/Deploy-the-Skype-for-Business-client-for-your-organization-8c563b81-22c9-4024-9efe-9fe28c7bbc96?ui=en-US&amp;rs=en-US&amp;ad=US)

