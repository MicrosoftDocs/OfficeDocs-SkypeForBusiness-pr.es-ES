---
title: Herramientas de administración de Windows PowerShell y Skype empresarial
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 6a285f7c-0ef5-4cab-9976-d03be276e35d
description: 'En Skype empresarial Server, las herramientas de administración se implementan con Windows PowerShell. Windows PowerShell incluye un entorno de línea de comandos, comandos específicos de productos y un lenguaje de scripting completo. Entre las herramientas de Skype empresarial que se implementan con Windows PowerShell se incluyen las siguientes:'
ms.openlocfilehash: f20a78729e778b069f7e84c9b7ed53e8564d2516
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815648"
---
# <a name="windows-powershell-and-skype-for-business-server-management-tools"></a>Herramientas de administración de Windows PowerShell y Skype empresarial
 
En Skype empresarial Server, las herramientas de administración se implementan con Windows PowerShell. Windows PowerShell incluye un entorno de línea de comandos, comandos específicos de productos y un lenguaje de scripting completo. Entre las herramientas de Skype empresarial que se implementan con Windows PowerShell se incluyen las siguientes: 
  
- **Generador de topología**. El generador de topología se usa para crear, ajustar y publicar su topología planeada, y valida su topología antes de empezar con las instalaciones del servidor. Al instalar Skype empresarial Server en servidores individuales, los servidores leen la topología publicada como parte del proceso de instalación y el programa de instalación implementa el servidor tal como se indica en la topología. After setup, configuration information is automatically replicated to all servers. Components can be added to your deployment only by using Topology Builder.
    
- **Consola de administración de Skype empresarial Server**. Puede usar el shell de administración de Skype empresarial Server para la administración de la línea de comandos completa de su implementación.
    
- **Panel de control de Skype empresarial Server**. Puede usar la interfaz de usuario del panel de control de Skype empresarial Server para administrar las tareas más comunes en su implementación.
    
Estas herramientas usan cmdlets de Windows PowerShell para administrar su implementación, incluidos los cmdlets específicos de 550 de producto. Los cmdlets de seguridad incluidos en Skype empresarial Server se usan principalmente para administrar la autenticación y los permisos y derechos de los usuarios. Hay una gran variedad de cmdlets para administrar la autenticación, por ejemplo cmdlets para certificado y autenticación del PIN. Además, varios cmdlets permiten usar la nueva característica de control de acceso basado en roles (RBAC) para delegar el control administrativo de Skype empresarial Server. Para obtener más información sobre los cmdlets de Skype empresarial Server, consulte [Shell de administración de Skype empresarial Server](../../manage/management-shell.md).
  
Las características de seguridad de scripts de Windows PowerShell están diseñadas específicamente para ayudar a evitar algunos de los problemas de seguridad relacionados con scripts de tecnologías antiguas, incluido Microsoft Visual Basic Scripting Edition (VBScript). Las características de seguridad de Windows PowerShell se han diseñado para crear un entorno en el que los usuarios no pueden ejecutar scripts de manera sencilla o sin problemas. De forma predeterminada, las características de seguridad de Windows PowerShell están habilitadas. Puede modificar el estado de esas características para adaptarlo a sus necesidades de scripting y a una amplia variedad de objetivos de seguridad. Eso no significa que el shell impida a los usuarios ejecutar scripts. Lo que hace (de forma predeterminada) es que resulte difícil que los usuarios ejecuten scripts sin darse cuenta de que lo están haciendo. Para obtener más información, consulte [seguridad de scripts de Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=213145).
  

