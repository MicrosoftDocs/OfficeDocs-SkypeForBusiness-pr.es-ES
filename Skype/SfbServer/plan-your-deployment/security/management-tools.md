---
title: Windows PowerShell y Skype Empresarial Server de administración
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 6a285f7c-0ef5-4cab-9976-d03be276e35d
description: 'En Skype Empresarial Server, las herramientas de administración se implementan mediante Windows PowerShell. Windows PowerShell incluye un entorno de línea de comandos, comandos específicos del producto y un lenguaje de scripting completo. Skype Empresarial Server herramientas que se implementan mediante Windows PowerShell incluyen las siguientes:'
ms.openlocfilehash: 0c9707a9af4befc9a055021426ebd5041c534d7d
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/04/2021
ms.locfileid: "60767508"
---
# <a name="windows-powershell-and-skype-for-business-server-management-tools"></a>Windows PowerShell y Skype Empresarial Server de administración
 
En Skype Empresarial Server, las herramientas de administración se implementan mediante Windows PowerShell. Windows PowerShell incluye un entorno de línea de comandos, comandos específicos del producto y un lenguaje de scripting completo. Skype Empresarial Server herramientas que se implementan mediante Windows PowerShell incluyen las siguientes: 
  
- **Generador de topologías**. El Generador de topologías se usa para crear, ajustar y publicar la topología planeada y valida la topología antes de comenzar las instalaciones del servidor. Al instalar Skype Empresarial Server servidores individuales, los servidores leen la topología publicada como parte del proceso de instalación y el programa de instalación implementa el servidor como se indica en la topología. Después de la instalación, la información de configuración se replica automáticamente en todos los servidores. Los componentes solo se pueden agregar a la implementación mediante el Generador de topologías.
    
- **Skype Empresarial Server Shell de administración**. Puede usar el Shell Skype Empresarial Server administración para la administración completa de la línea de comandos de la implementación.
    
- **Skype Empresarial Server panel de control**. Puede usar la interfaz de usuario Skype Empresarial Server panel de control para administrar las tareas más comunes de la implementación.
    
Estas herramientas usan Windows PowerShell cmdlets para la administración de la implementación, incluidos cerca de 550 cmdlets específicos del producto. Los cmdlets de seguridad incluidos en Skype Empresarial Server se usan principalmente para administrar la autenticación y los permisos y derechos de usuario. Hay una gran variedad de cmdlets para administrar la autenticación, por ejemplo cmdlets para certificado y autenticación del PIN. Además, varios cmdlets permiten usar la nueva característica de control de acceso de Role-Based (RBAC) para delegar el control administrativo de Skype Empresarial Server. Para obtener más información sobre los cmdlets Skype Empresarial Server, [vea Skype Empresarial Server Shell de administración](../../manage/management-shell.md).
  
Las características de seguridad de scripts para Windows PowerShell están diseñadas específicamente para ayudar a evitar algunos de los problemas de seguridad relacionados con scripts de tecnologías anteriores, incluido Microsoft Visual Basic Scripting Edition (VBScript). Las Windows PowerShell de seguridad están diseñadas para crear un entorno en el que los usuarios no puedan ejecutar scripts fácilmente o sin conocimiento. De forma predeterminada, Windows PowerShell de seguridad están habilitadas. Puede modificar el estado de estas características para satisfacer sus necesidades de scripting y una variedad de objetivos de seguridad. Esto no quiere decir que el shell hace imposible que los usuarios ejecuten scripts. En su lugar, el shell dificulta (de forma predeterminada) que los usuarios ejecuten scripts sin darse cuenta de que lo están haciendo. Para obtener más información, [vea Windows PowerShell Script Security](/previous-versions/msdn10/gg261722(v=msdn.10)).
