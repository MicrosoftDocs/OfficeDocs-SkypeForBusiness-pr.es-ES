---
title: Actualizar el administrador de estadísticas para Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 71f5d0a0-ca81-4ac1-b590-8f854504f21f
description: 'Resumen: lea este tema para obtener información sobre cómo actualizar el Administrador de estadísticas para Skype Empresarial Server.'
ms.openlocfilehash: 6f2f0b885faad7bd650b3ff90650b64af98e9eee
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821770"
---
# <a name="upgrade-statistics-manager-for-skype-for-business-server"></a>Actualizar el administrador de estadísticas para Skype Empresarial Server
 
**Resumen:** Lea este tema para obtener información sobre cómo actualizar el Administrador de estadísticas para Skype Empresarial Server.
  
En este tema se describe cómo actualizar una instalación existente del Administrador de estadísticas para Skype Empresarial Server, una herramienta eficaz que le permite ver datos de rendimiento y estado de Skype Empresarial Server en tiempo real. Puede sondear los datos de rendimiento en cientos de servidores cada pocos segundos y ver los resultados al instante en el sitio web del Administrador de estadísticas. 
  
Para obtener más información sobre el Administrador de estadísticas y las nuevas características de la versión 2.0, vea [Plan for Statistics Manager for Skype for Business Server](plan.md) and Deploy [Statistics Manager for Skype for Business Server](deploy.md).
  
Existen dos métodos para actualizar:
  
- **Actualización automatizada.** Este método usa un script automatizado. Es el método más sencillo y debe aplicarse a todos los escenarios de actualización.
    
- **Actualización manual.** Este método se proporciona como un plan de copia de seguridad en el caso inusual de que se produce un error en la actualización automatizada.
    
## <a name="prerequisites"></a>Requisitos previos

Antes de actualizar, asegúrese de que tiene la siguiente información:
  
- Huella digital del certificado de escucha activa
    
- Contraseña del servicio de escucha (especificada al instalar el agente de escucha y todos los agentes)
    
- Configuración del certificado SSL para el sitio web
    
## <a name="automated-upgrade"></a>Actualización automatizada

El script recopilará la información del certificado actual y la contraseña de escucha, desinstalará la versión anterior del producto y, a continuación, instalará la nueva versión del producto. La instancia redis instalada en el servidor no se tocará, por lo que los datos almacenados en la memoria caché se conservarán durante el proceso de actualización.
  
1. Coloque los archivos MSI para la nueva versión del agente, el agente de escucha y el sitio web junto con el script Update-StatsMan.ps1 en una sola carpeta en el equipo de escucha.
    
2. Abra una ventana administrativa de PowerShell. Actualice el componente de escucha:
    
   ```PowerShell
   .\Update-StatsMan.ps1 -Service Listener
   ```

> [!NOTE]
> La contraseña del servicio administrador de estadísticas se mostrará en texto no especificado en la línea de comandos mientras se pasa al instalador. Asegúrate de blindar el monitor según sea necesario. 
  
1. Al ejecutar el script, se le pedirá que desinstale la versión anterior del producto. Respuesta Sí.
    
2. Si el servicio de escucha se está ejecutando, se le pedirá que cierre la aplicación antes de continuar. Permitir que se cierre la aplicación (se detendrán el servicio de escucha del Administrador de estadísticas).
    
3. Continúe el proceso de instalación. Debe observar que la contraseña de servicio y la huella digital del certificado están rellenadas previamente. Si no es así, agregue los valores que guardó antes de continuar.
    
4. Abra una ventana administrativa de PowerShell. Actualice el componente de sitio web:
    
   ```PowerShell
   .\Update-StatsMan.ps1 -Service Website
   ```

5. Al ejecutar el script, se le pedirá que desinstale la versión anterior del producto. Respuesta Sí.
    
6. Si el servicio de agente se está ejecutando, se le pedirá que cierre la aplicación antes de continuar. Permitir que se cierre la aplicación (se detendrán el servicio de agente StatsMan).
    
7. Continúe el proceso de instalación. Debe observar que la contraseña de servicio y la huella digital del certificado están rellenadas previamente. Si no es así, agregue los valores que guardó antes de continuar.
    
8. Abra una ventana administrativa de PowerShell. Actualice el componente de agente:
    
   ```PowerShell
   .\Update-StatsMan.ps1 -Service Agent
   ```

9. Al ejecutar el script, se le pedirá que desinstale la versión anterior del producto. Respuesta Sí.
    
10. Continúe el proceso de instalación. Debe observar que el puerto del sitio web está rellenado previamente. Si no es así, agregue el valor que guardó antes de continuar.
    
11. Compruebe que el sitio web funciona según lo esperado con el explorador.
    
> [!NOTE]
> La actualización del agente se puede usar con el modificador -NoPrompt. Esto permitirá que el proceso de desinstalación/instalación se ejecute en modo silencioso, lo que permite que herramientas como PSExec ejecuten la actualización de forma remota en un gran número de servidores. 
  
### <a name="manual-upgrade"></a>Actualización manual

Si, por algún motivo, se produce un error en la actualización automatizada, siempre puede realizar una actualización manual de la siguiente manera:
  
1. En el equipo de escucha, desinstale el agente de escucha, el sitio web y el agente (si se instaló en este servidor) a través del panel de control Programas y características. 
    
    > [!NOTE]
    >  Mantenga Redis instalado para que los datos de la memoria caché se mantengan a lo largo del proceso de actualización.
  
2. Instale las nuevas versiones de los componentes, incluidos los valores que guardó anteriormente cuando se le soliciten. Para obtener más información acerca de la instalación de componentes, vea [Deploy Statistics Manager](deploy.md#BKMK_Deploy)

    
## <a name="for-more-information"></a>Más información
<a name="BKMK_Fixed"> </a>

Para obtener más información, vea los artículos siguientes: 
  
- [Planear el administrador de estadísticas para Skype Empresarial Server](plan.md)
    
- [Implementar el administrador de estadísticas para Skype Empresarial Server](deploy.md)
    
- [Solucionar problemas del administrador de estadísticas para Skype Empresarial Server](troubleshoot.md)
