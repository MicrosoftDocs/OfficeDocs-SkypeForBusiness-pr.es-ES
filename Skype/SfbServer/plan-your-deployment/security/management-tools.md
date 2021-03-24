---
title: Windows PowerShell y herramientas de administración de Skype Empresarial Server
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
description: 'En Skype Empresarial Server, las herramientas de administración se implementan mediante Windows PowerShell. Windows PowerShell incluye un entorno de línea de comandos, comandos específicos del producto y un lenguaje de scripting completo. Las herramientas de Skype Empresarial Server que se implementan mediante Windows PowerShell incluyen lo siguiente:'
ms.openlocfilehash: 61f5acdacc1a401a3541ba9d08213ad7f054374a
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51104206"
---
# <a name="windows-powershell-and-skype-for-business-server-management-tools"></a>Windows PowerShell y herramientas de administración de Skype Empresarial Server
 
En Skype Empresarial Server, las herramientas de administración se implementan mediante Windows PowerShell. Windows PowerShell incluye un entorno de línea de comandos, comandos específicos del producto y un lenguaje de scripting completo. Las herramientas de Skype Empresarial Server que se implementan mediante Windows PowerShell incluyen lo siguiente: 
  
- **Generador de topologías**. El Generador de topologías se usa para crear, ajustar y publicar la topología planeada y valida la topología antes de comenzar las instalaciones del servidor. Al instalar Skype Empresarial Server en servidores individuales, los servidores leen la topología publicada como parte del proceso de instalación y el programa de instalación implementa el servidor como se indica en la topología. Después de la instalación, la información de configuración se replica automáticamente en todos los servidores. Los componentes solo se pueden agregar a la implementación mediante el Generador de topologías.
    
- **Shell de administración de Skype Empresarial Server**. Puede usar el Shell de administración de Skype Empresarial Server para la administración completa de la línea de comandos de la implementación.
    
- **Panel de control de Skype Empresarial Server**. Puede usar la interfaz de usuario del Panel de control de Skype Empresarial Server para administrar las tareas más comunes de la implementación.
    
Estas herramientas usan Windows PowerShell cmdlets para la administración de la implementación, incluidos cerca de 550 cmdlets específicos del producto. Los cmdlets de seguridad incluidos en Skype Empresarial Server se usan principalmente para administrar la autenticación y los permisos y derechos de usuario. Hay una gran variedad de cmdlets para administrar la autenticación, por ejemplo cmdlets para certificado y autenticación del PIN. Además, varios cmdlets permiten usar la nueva característica de control de acceso de Role-Based (RBAC) para delegar el control administrativo de Skype Empresarial Server. Para obtener más información acerca de los cmdlets de Skype Empresarial Server, vea [Shell de administración de Skype Empresarial Server](../../manage/management-shell.md).
  
Las características de seguridad de scripts para Windows PowerShell están diseñadas específicamente para ayudar a evitar algunos de los problemas de seguridad relacionados con scripts de tecnologías anteriores, incluido Microsoft Visual Basic Scripting Edition (VBScript). Las Windows PowerShell de seguridad están diseñadas para crear un entorno en el que los usuarios no puedan ejecutar scripts fácilmente o sin conocimiento. De forma predeterminada, Windows PowerShell de seguridad están habilitadas. Puede modificar el estado de estas características para satisfacer sus necesidades de scripting y una variedad de objetivos de seguridad. Esto no quiere decir que el shell hace imposible que los usuarios ejecuten scripts. En su lugar, el shell dificulta (de forma predeterminada) que los usuarios ejecuten scripts sin darse cuenta de que lo están haciendo. Para obtener más información, [vea Windows PowerShell Script Security](/previous-versions/msdn10/gg261722(v=msdn.10)).
