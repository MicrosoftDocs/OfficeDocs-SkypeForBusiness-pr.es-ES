---
title: Herramientas de administración de Windows PowerShell y Skype Empresarial Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 12/20/2016
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6a285f7c-0ef5-4cab-9976-d03be276e35d
description: 'En Skype para Business Server 2015, herramientas de administración se implementan mediante Windows PowerShell. Windows PowerShell incluye un entorno de línea de comandos, comandos específicos del producto y un completo lenguaje de scripting. Skype para herramientas de 2015 de servidor empresariales que se implementan mediante Windows PowerShell son las siguientes:'
ms.openlocfilehash: 25631ce7acf59567b431d7eebdf190c4b63d7913
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="windows-powershell-and-skype-for-business-server-2015-management-tools"></a>Herramientas de administración de Windows PowerShell y Skype Empresarial Server 2015
 
En Skype para Business Server 2015, herramientas de administración se implementan mediante Windows PowerShell. Windows PowerShell incluye un entorno de línea de comandos, comandos específicos del producto y un completo lenguaje de scripting. Skype para herramientas de 2015 de servidor empresariales que se implementan mediante Windows PowerShell son las siguientes: 
  
- **El generador de topología**. Utilice el generador de topología para crear, ajustar y publicar su topología planeada y valida la topología antes de comenzar las instalaciones de servidor. Al instalar Skype para Business Server 2015 en servidores individuales, los servidores leen la topología publicada como parte del proceso de instalación y el programa de instalación implementa el servidor según lo indicado en la topología. Tras la instalación, se replica automáticamente la información de configuración a todos los servidores. Solo pueden agregarse componentes a la implementación utilizando el Generador de topologías.
    
- **Skype para el Shell de administración de servidor de empresa**. Puede utilizar Skype para negocios de Shell de administración de servidor para la administración de línea de comandos de su implementación.
    
- **Skype para Panel de Control del servidor de empresa**. Puede utilizar el Skype para la interfaz de usuario del Panel de Control de servidor empresarial para administrar las tareas más comunes en la implementación.
    
Estas herramientas usar cmdlets de Windows PowerShell para la administración de la implementación, incluyendo cerca de 550 cmdlets específicos para cada producto. Los cmdlets de seguridad incluidos en Skype para Business Server 2015 se utilizan principalmente para administrar la autenticación y derechos de usuario y los permisos. Hay una gran variedad de cmdlets para administrar la autenticación, por ejemplo cmdlets para certificado y autenticación del PIN. Además, un número de cmdlets permite utilizar la nueva característica de Control de acceso basado en roles (RBAC) para delegar el control administrativo de Skype para Business Server 2015. Para obtener información detallada sobre el Skype para Business Server cmdlets, vea [Skype para el Shell de administración de negocio servidor 2015](../../manage/management-shell.md).
  
Las características de seguridad de scripts de Windows PowerShell están diseñadas específicamente para ayudar a evitar algunos de los problemas de seguridad relacionados con scripts de tecnologías antiguas, incluido Microsoft Visual Basic Scripting Edition (VBScript). Las características de seguridad de Windows PowerShell se pretende crear un entorno en el que los usuarios no pueden fácilmente o sin saberlo ejecutar secuencias de comandos. De forma predeterminada, se habilitan las características de seguridad de Windows PowerShell. Puede modificar el estado de esas características para adaptarlo a sus necesidades de scripting y a una amplia variedad de objetivos de seguridad. Eso no significa que el shell impida a los usuarios ejecutar scripts. Lo que hace (de forma predeterminada) es que resulte difícil que los usuarios ejecuten scripts sin darse cuenta de que lo están haciendo. Para obtener más información, vea [Seguridad de secuencia de comandos de Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=213145).
  

