---
title: Actualizar el administrador de estadísticas para Skype Empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 71f5d0a0-ca81-4ac1-b590-8f854504f21f
description: 'Resumen: Lea este tema para obtener información sobre cómo actualizar statistic Manager para Skype empresarial Server.'
ms.openlocfilehash: 70826776e9dfacdef75c7084a9aba6f4eede940a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34299726"
---
# <a name="upgrade-statistics-manager-for-skype-for-business-server"></a>Actualizar el administrador de estadísticas para Skype Empresarial Server
 
**Resumen:** Lea este tema para obtener información sobre cómo actualizar statistic Manager para Skype empresarial Server.
  
En este tema se describe cómo actualizar una instalación existente de statistic Manager para Skype empresarial Server, una eficaz herramienta que le permite ver los datos de estado y rendimiento de Skype empresarial en tiempo real. Puede sondear los datos de rendimiento en cientos de servidores cada pocos segundos y ver los resultados al instante en el sitio web del administrador de estadísticas. 
  
Para obtener más información sobre statistic Manager y las nuevas características de la versión 2,0, consulte [Plan for Statistics Manager for Skype for Business Server](plan.md) e implantar [Statistics Manager para Skype empresarial Server](deploy.md).
  
Existen dos métodos para actualizar:
  
- **Actualización automática**. Este método usa un script automatizado. Es el método más sencillo y debe ser aplicable a todos los escenarios de actualización.
    
- **Actualización manual**. Este método se proporciona como un plan de copia de seguridad en el caso inusual de que se produzca un error en la actualización automática.
    
## <a name="prerequisites"></a>Requisitos previos

Antes de realizar la actualización, asegúrese de que tiene la siguiente información:
  
- Huella digital del certificado del agente de escucha activa
    
- Contraseña del servicio de escucha (introducida en la instalación de la escucha y de cada agente)
    
- Configuración del certificado SSL para el sitio web
    
## <a name="automated-upgrade"></a>Actualización automática

El script recopilará la información del certificado actual y la contraseña de escucha, desinstalará la versión anterior del producto y, a continuación, instalará la nueva versión del producto. La instancia Redis instalada en el servidor no se tocará, de modo que los datos almacenados en la caché se conservarán durante el proceso de actualización.
  
1. Coloque los archivos MSI de la nueva versión del agente, agente de escucha y sitio web, junto con el script Update-StatsMan. ps1, en una sola carpeta del equipo de escucha.
    
2. Abra una ventana administrativa de PowerShell. Actualice el componente de escucha:
    
   ```
   .\Update-StatsMan.ps1 -Service Listener
   ```

> [!NOTE]
> La contraseña del servicio de administrador de estadísticas se mostrará en texto no cifrado en la línea de comandos mientras se pasa al instalador. Asegúrese de blindar el monitor según sea necesario. 
  
1. Al ejecutar el script, se le pedirá que desinstale la versión anterior del producto. Responda Sí.
    
2. Si el servicio de escucha se está ejecutando, se le pedirá que cierre la aplicación antes de continuar. Permitir que se cierre la aplicación (el servicio de escucha del administrador de estadísticas se detendrá).
    
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

    
## <a name="for-more-information"></a>Más información
<a name="BKMK_Fixed"> </a>

Para obtener más información, vea los artículos siguientes:
  
- [Planear el administrador de estadísticas para Skype Empresarial Server](plan.md)
    
- [Implementar el administrador de estadísticas para Skype Empresarial Server](deploy.md)
    
- [Solucionar problemas del administrador de estadísticas para Skype Empresarial Server](troubleshoot.md)
