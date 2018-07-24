---
title: Windows PowerShell y Skype para herramientas de administración de Business Server
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6a285f7c-0ef5-4cab-9976-d03be276e35d
description: 'En Skype para Business Server, las herramientas de administración se implementan mediante Windows PowerShell. Windows PowerShell incluye un entorno de línea de comandos, comandos específicos del producto y un lenguaje de scripting completo. Skype para las herramientas de Business Server que se implementan mediante Windows PowerShell se incluyen los siguientes:'
ms.openlocfilehash: 4811f8fb6e4db1003e367a9cc99feb92a2928d5f
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2018
ms.locfileid: "21007291"
---
# <a name="windows-powershell-and-skype-for-business-server-management-tools"></a>Windows PowerShell y Skype para herramientas de administración de Business Server
 
En Skype para Business Server, las herramientas de administración se implementan mediante Windows PowerShell. Windows PowerShell incluye un entorno de línea de comandos, comandos específicos del producto y un lenguaje de scripting completo. Skype para las herramientas de Business Server que se implementan mediante Windows PowerShell se incluyen los siguientes: 
  
- **Generador de topología**. Use el generador de topología para crear, ajustar y publicar su topología planeada y valida la topología antes de comenzar las instalaciones de servidor. Al instalar Skype para Business Server en servidores individuales, los servidores leen la topología publicada como parte del proceso de instalación, y el programa de instalación implementa el servidor como se indica en la topología. Tras la instalación, se replica automáticamente la información de configuración a todos los servidores. Solo pueden agregarse componentes a la implementación utilizando el Generador de topologías.
    
- **Skype para Shell de administración de servidor empresarial**. Puede usar Skype para Shell de administración de servidor empresarial para administración de línea de comandos de su implementación.
    
- **Skype para el Panel de Control de servidor empresarial**. Puede usar el Skype para la interfaz de usuario del Panel de Control de servidor empresarial para administrar las tareas más comunes en la implementación.
    
Estas herramientas usar cmdlets de Windows PowerShell para la administración de la implementación, incluidos cerca de 550 cmdlets específicos de cada producto. Los cmdlets de seguridad incluidos en Skype para Business Server se usan principalmente para administrar la autenticación y derechos de usuario y los permisos. Hay una gran variedad de cmdlets para administrar la autenticación, por ejemplo cmdlets para certificado y autenticación del PIN. Además, un número de cmdlets permiten usar la nueva característica de Control de acceso basado en roles (RBAC) para delegar el control administrativo de Skype para Business Server. Para obtener información detallada sobre la Skype para Business Server cmdlets, consulte [Skype para Shell de administración de servidor empresarial](../../manage/management-shell.md).
  
Las características de seguridad de scripts de Windows PowerShell están diseñadas específicamente para ayudar a evitar algunos de los problemas de seguridad relacionados con scripts de tecnologías antiguas, incluido Microsoft Visual Basic Scripting Edition (VBScript). Las características de seguridad de Windows PowerShell están diseñadas para crear un entorno en el que los usuarios no pueden fácilmente o sin darse cuenta ejecutar secuencias de comandos. De forma predeterminada, se habilitan las características de seguridad de Windows PowerShell. Puede modificar el estado de esas características para adaptarlo a sus necesidades de scripting y a una amplia variedad de objetivos de seguridad. Eso no significa que el shell impida a los usuarios ejecutar scripts. Lo que hace (de forma predeterminada) es que resulte difícil que los usuarios ejecuten scripts sin darse cuenta de que lo están haciendo. Para obtener más información, vea [Seguridad de secuencia de comandos de Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=213145).
  

