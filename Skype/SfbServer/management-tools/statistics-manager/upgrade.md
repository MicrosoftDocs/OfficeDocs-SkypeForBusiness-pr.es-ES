---
title: Actualizar el Administrador de estadísticas de Skype para Business Server
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 1/10/2017
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 71f5d0a0-ca81-4ac1-b590-8f854504f21f
description: 'Resumen: Lea este tema para obtener información sobre cómo actualizar las estadísticas de administrador de Skype para Business Server.'
ms.openlocfilehash: 13bb4a13d05f7c877c5dd62a9c17466389d0e564
ms.sourcegitcommit: 8a6bf02958436fcdeed336f09079bd3827e2fccb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/12/2018
ms.locfileid: "26283173"
---
# <a name="upgrade-statistics-manager-for-skype-for-business-server"></a>Actualizar el Administrador de estadísticas de Skype para Business Server
 
**Resumen:** Lea este tema para obtener información sobre cómo actualizar las estadísticas de administrador de Skype para Business Server.
  
En este tema se describe cómo actualizar una instalación existente de administrador de estadísticas de Skype para Business Server — una eficaz herramienta que le permite ver Skype para los datos de estado y rendimiento de servidor empresarial en tiempo real. Puede sondear los datos de rendimiento a través de cientos de servidores cada pocos segundos y ver los resultados al instante en el sitio Web de estadísticas de administrador. 
  
Para obtener más información acerca de las estadísticas de administrador y las nuevas características de la versión 2.0, vea [planear para el Administrador de estadísticas de Skype para Business Server](plan.md) e [Implementar el Administrador de estadísticas de Skype para Business Server](deploy.md).
  
Existen dos métodos para actualizar:
  
- **Actualización automática**. Este método usa una secuencia de comandos automatizada. Es el método más sencillo y deberán ser aplicable a todos los escenarios de actualización.
    
- **Actualización manual**. Este método se proporciona como un plan de copia de seguridad en el caso poco habitual que se produce un error en la actualización automática.
    
## <a name="prerequisites"></a>Requisitos previos

Antes de realizar la actualización, asegúrese de que tiene la siguiente información:
  
- Huella digital del certificado del agente de escucha activa
    
- Contraseña del servicio de escucha (introducida en la instalación de la escucha y de cada agente)
    
- Configuración del certificado SSL para el sitio web
    
## <a name="automated-upgrade"></a>Actualización automática

El script recopilará la información del certificado actual y la contraseña de escucha, desinstalará la versión anterior del producto y, a continuación, instalará la nueva versión del producto. La instancia Redis instalada en el servidor no se tocará, de modo que los datos almacenados en la caché se conservarán durante el proceso de actualización.
  
1. Coloque los archivos MSI para la nueva versión del agente, el agente de escucha y sitio Web junto con la secuencia de comandos de actualización StatsMan.ps1 en una sola carpeta en el equipo de agente de escucha.
    
2. Abra una ventana administrativa de PowerShell. Actualice el componente de escucha:
    
   ```
   .\Update-StatsMan.ps1 -Service Listener
   ```

> [!NOTE]
> La contraseña del servicio Administrador de estadísticas se mostrará en texto no cifrado en la línea de comandos tal como se pasa para el programa de instalación. Asegúrese de blindar el monitor según sea necesario. 
  
1. Al ejecutar el script, se le pedirá que desinstale la versión anterior del producto. Responda Sí.
    
2. Si el servicio de escucha se está ejecutando, se le pedirá que cierre la aplicación antes de continuar. Permitir que la aplicación se cierre (la escucha de las estadísticas de administrador se detendrá el servicio).
    
3. Continúe el proceso de instalación. Verá que la contraseña de servicio y la huella digital del certificado se han rellenado previamente. Si no es así, agregue los valores que guardó antes de continuar.
    
4. Abra una ventana administrativa de PowerShell. Actualice el componente del sitio web:
    
   ```
   .\Update-StatsMan.ps1 -Service Website
   ```

5. Al ejecutar el script, se le pedirá que desinstale la versión anterior del producto. Responda Sí.
    
6. Si el servicio de agente se está ejecutando, se le pedirá que cierre la aplicación antes de continuar. Permita el cierre de la aplicación (el servicio de agente StatsMan se detendrá).
    
7. Continúe el proceso de instalación. Verá que la contraseña de servicio y la huella digital del certificado se han rellenado previamente. Si no es así, agregue los valores que guardó antes de continuar.
    
8. Abra una ventana administrativa de PowerShell. Actualice el componente de agente:
    
   ```
   .\Update-StatsMan.ps1 -Service Agent
   ```

9. Al ejecutar el script, se le pedirá que desinstale la versión anterior del producto. Responda Sí.
    
10. Continúe el proceso de instalación. Verá que el puerto del sitio web se ha rellenado previamente. Si no es así, agregue el valor que guardó antes de continuar.
    
11. Compruebe que el sitio web funciona como se espera mediante el explorador.
    
> [!NOTE]
> La actualización del agente se puede usar con el conmutador -NoPrompt. Esto permitirá que el proceso de instalación/desinstalación se ejecute en silencio, lo que permite que herramientas como PSExec ejecuten la actualización de forma remota en un gran número de servidores. 
  
### <a name="manual-upgrade"></a>Actualización manual

Si, por algún motivo, se produce un error durante la actualización automática, puede realizar una actualización manual siguiendo estos pasos:
  
1. 	En el equipo de escucha, desinstale la escucha, el sitio web y el agente (si se instaló en este servidor) mediante el panel de control Programas y características.   
    
    > [!NOTE]
    >   Mantenga Redis instalado para que los datos de la caché se conserven durante el proceso de actualización.
  
2. 	Instale las nuevas versiones de los componentes, incluidos los valores que guardó anteriormente cuando se le pidan. Para obtener más información acerca de cómo instalar los componentes, vea [Implementar el administrador de estadísticas](deploy.md#BKMK_Deploy).

    
## <a name="for-more-information"></a>Para más información
<a name="BKMK_Fixed"> </a>

Para obtener más información, consulte lo siguiente:
  
- [Plan para el Administrador de estadísticas de Skype para Business Server](plan.md)
    
- [Implementar el Administrador de estadísticas de Skype para Business Server](deploy.md)
    
- [Solucionar problemas de administrador de estadísticas de Skype para Business Server](troubleshoot.md)
    
- [Blog del administrador de estadísticas de Skype Empresarial Server](https://blogs.technet.microsoft.com/skypestatsman/)
    

