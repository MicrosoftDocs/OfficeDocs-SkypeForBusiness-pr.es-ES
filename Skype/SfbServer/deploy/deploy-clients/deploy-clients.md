---
title: Implementar clientes para Skype Empresarial Server
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.reviewer: PhillipGarding
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 3d10abf2-d484-4fa0-8f10-4a5f9dfba4f5
description: 'Resumen: Información general sobre los métodos de instalación de cliente de empresa para Skype Empresarial.'
ms.openlocfilehash: 2e52de479b181e13be3124baeec0e76787b863a0
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/05/2022
ms.locfileid: "62399384"
---
# <a name="deploy-clients-for-skype-for-business-server"></a>Implementar clientes para Skype Empresarial Server
 
**Resumen:** Información general sobre los métodos de instalación de cliente de empresa Skype Empresarial.
  
La forma de implementar Skype Empresarial para los usuarios depende de si compró Skype Empresarial como parte de un plan de Microsoft 365 o Office 365 o si compró una versión con licencia por volumen de Skype Empresarial. 
  
- **Microsoft 365 o Office 365** Si tiene un plan de Microsoft 365 o Office 365 que incluya Skype Empresarial, la tecnología de instalación que se usa se denomina Hacer clic y ejecutar. Puede permitir que los usuarios instalen Skype Empresarial ellos mismos desde el Centro de administración de Microsoft 365. O bien, puede implementar Skype Empresarial a los usuarios descargando el software en la red local y, a continuación, usando las herramientas de implementación de software existentes, como con Microsoft Endpoint Configuration Manager. Para obtener información sobre la instalación Skype Empresarial que incluye Microsoft 365 y Office 365, vea [Deploy the Skype Empresarial client in Microsoft 365 or Office 365](https://support.office.com/article/8c563b81-22c9-4024-9efe-9fe28c7bbc96).
    
- **Licencia por volumen** Si tiene una versión con licencia por volumen del cliente Skype Empresarial 2015 o 2016, la tecnología de instalación que se usa es Windows Installer (MSI). Un Windows de instalación basado en instalador consta de varios archivos MSI. Un paquete MSI central de lenguaje neutral se combina con uno o más paquetes de lenguaje específico para hacer un producto completo. La instalación junta los paquetes individuales y realiza tareas de mantenimiento y personalización durante y tras finalizar la instalación de Office en los equipos de los usuarios. El Skype Empresarial 2019 usa instaladores de hacer clic y ejecutar.
    
En los temas de esta sección se describe cómo usar y personalizar el instalador de Windows para implementar el cliente Skype Empresarial a los usuarios a través de los procedimientos normales.
  
> [!NOTE]
> El Skype de reuniones para Microsoft Office, que admite la administración de reuniones desde el cliente de mensajería y colaboración de Outlook, se instala automáticamente con Skype Empresarial clientes. 
  
> [!NOTE]
> Los Microsoft 365 y Office 365 programa de instalación no desinstalan las versiones anteriores de Lync. El Skype Empresarial se instala en paralelo con otros clientes de Lync. 
  
## <a name="installing-windows-clients"></a>Instalación Windows clientes

- [Personalizar Windows de cliente en Skype Empresarial Server](customize-windows-client-installation.md)
    
- [Configurar la experiencia del cliente con Skype Empresarial](configure-the-client-experience.md)
    
- [Configurar lista de contactos inteligentes en Skype Empresarial Server](configure-smart-contacts-list.md)
    
## <a name="installing-device-clients"></a>Instalación de clientes de dispositivos

- [Instalar y probar Skype Empresarial para Windows Phone](windows-phone.md)
    
- [Instalar y probar Skype Empresarial para iOS](ios.md)
    
    
- [Implementar el complemento VDI de Lync con Skype Empresarial Server](deploy-the-lync-vdi-plug-in.md)
    
- [Implementar clientes descargables web en Skype Empresarial Server](deploy-web-downloadable-clients.md)
    
- [Personalizar la experiencia del cliente mac en Skype Empresarial](customize-the-mac-client-experience.md)
    
## <a name="see-also"></a>Vea también

[Implementar el Skype Empresarial en Microsoft 365 o Office 365](../../../SfbOnline/set-up-skype-for-business-online/deploy-the-skype-for-business-client-in-office-365.md)
