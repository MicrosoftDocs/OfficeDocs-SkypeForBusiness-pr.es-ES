---
title: Windows PowerShell de administración de Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 6a285f7c-0ef5-4cab-9976-d03be276e35d
description: 'En Skype Empresarial Server, las herramientas de administración se implementan con Windows PowerShell. Windows PowerShell incluye un entorno de línea de comandos, comandos específicos del producto y un lenguaje de scripting completo. Entre las herramientas de Skype Empresarial Server que se implementan Windows PowerShell se incluyen las siguientes:'
ms.openlocfilehash: 740a5e3d7998523970e1b0adc1e72aa85d0b09c4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832160"
---
# <a name="windows-powershell-and-skype-for-business-server-management-tools"></a>Windows PowerShell de administración de Skype Empresarial Server
 
En Skype Empresarial Server, las herramientas de administración se implementan con Windows PowerShell. Windows PowerShell incluye un entorno de línea de comandos, comandos específicos del producto y un lenguaje de scripting completo. Entre las herramientas de Skype Empresarial Server que se implementan Windows PowerShell se incluyen las siguientes: 
  
- **Topology Builder**. El Generador de topologías se usa para crear, ajustar y publicar la topología planeada, y valida la topología antes de comenzar las instalaciones del servidor. Al instalar Skype Empresarial Server en servidores individuales, los servidores leen la topología publicada como parte del proceso de instalación y el programa de instalación implementa el servidor como se indica en la topología. Después de la instalación, la información de configuración se replica automáticamente en todos los servidores. Los componentes solo se pueden agregar a la implementación mediante el Generador de topologías.
    
- **Shell de administración de Skype Empresarial Server**. Puede usar el Shell de administración de Skype Empresarial Server para la administración completa de la línea de comandos de su implementación.
    
- **Panel de control de Skype Empresarial Server.** Puede usar la interfaz de usuario del Panel de control de Skype Empresarial Server para administrar las tareas más comunes de su implementación.
    
Estas herramientas usan Windows PowerShell cmdlets para la administración de la implementación, incluidos cerca de 550 cmdlets específicos del producto. Los cmdlets de seguridad incluidos en Skype Empresarial Server se usan principalmente para administrar la autenticación, así como los permisos y derechos de usuario. Hay una gran variedad de cmdlets para administrar la autenticación, por ejemplo cmdlets para certificado y autenticación del PIN. Además, una serie de cmdlets le permiten usar la nueva característica Role-Based Access Control (RBAC) para delegar el control administrativo de Skype Empresarial Server. Para obtener más información sobre los cmdlets de Skype Empresarial Server, consulte Shell de administración [de Skype Empresarial Server.](../../manage/management-shell.md)
  
Las características de seguridad de scripts para Windows PowerShell están diseñadas específicamente para ayudar a evitar algunos de los problemas de seguridad relacionados con scripts de tecnologías anteriores, como Microsoft Visual Basic Scripting Edition (VBScript). Las Windows PowerShell de seguridad están diseñadas para crear un entorno en el que los usuarios no puedan ejecutar scripts fácilmente o sin saberlo. De forma predeterminada, Windows PowerShell características de seguridad están habilitadas. Puede modificar el estado de estas características para adaptarse a sus necesidades de scripting y a una variedad de objetivos de seguridad. Esto no significa que el shell imposibilite a los usuarios ejecutar scripts. En su lugar, el shell dificulta (de forma predeterminada) que los usuarios ejecuten scripts sin darse cuenta de que lo están haciendo. Para obtener más información, [consulte Windows PowerShell Seguridad de scripts.](https://go.microsoft.com/fwlink/p/?LinkId=213145)
  

