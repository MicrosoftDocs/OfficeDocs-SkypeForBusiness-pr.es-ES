---
title: Actualizar el administrador de estadísticas para Skype Empresarial Server 2015
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
description: 'Resumen: Leer este tema para aprender a actualizar estadísticas Manager para Skype para Business Server 2015.'
ms.openlocfilehash: e5a9dd230f16313388cbb9a51e50910979e6c79c
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="upgrade-statistics-manager-for-skype-for-business-server-2015"></a>Actualizar el administrador de estadísticas para Skype Empresarial Server 2015
 
**Resumen:** Lea este tema para aprender a actualizar estadísticas Manager para Skype para Business Server 2015.
  
Este tema describe cómo actualizar una instalación existente del Administrador de estadísticas de Skype para Business Server, una potente herramienta que le permite ver Skype para los datos de rendimiento y la salud de Business Server en tiempo real. Puede sondear los datos de rendimiento a través de cientos de servidores cada pocos segundos y ver los resultados al instante en el sitio Web del Administrador de estadísticas. 
  
Para obtener más información acerca del Administrador de las estadísticas y las nuevas características de la versión 1.1, vea [Planear Administrador de estadísticas para Skype para Business Server 2015](plan.md) e [Implementar Administrador de estadísticas de Skype para Business Server 2015](deploy.md). Para obtener información acerca de los problemas conocidos que se han corregido en la versión 1.1, vea [Problemas conocidos corregidos en la versión 1.1](upgrade.md#BKMK_Fixed).
  
Existen dos métodos para actualizar:
  
- **Actualización automática**. Este método utiliza una secuencia de comandos automatizada. Es el método más sencillo y debe ser aplicable a todos los escenarios de actualización.
    
- **Actualización manual**. Este método se proporciona como un plan de copia de seguridad en el caso inusual que se produce un error en la actualización automática.
    
## <a name="prerequisites"></a>Requisitos previos

Antes de realizar la actualización, asegúrese de que tiene la siguiente información:
  
- Huella digital del certificado del agente de escucha activa
    
- Contraseña del servicio de escucha (introducida en la instalación de la escucha y de cada agente)
    
- Configuración del certificado SSL para el sitio web
    
## <a name="automated-upgrade"></a>Actualización automática

El script recopilará la información del certificado actual y la contraseña de escucha, desinstalará la versión anterior del producto y, a continuación, instalará la nueva versión del producto. La instancia Redis instalada en el servidor no se tocará, de modo que los datos almacenados en la caché se conservarán durante el proceso de actualización.
  
1. Coloque los archivos MSI para la nueva versión del agente, agente de escucha y sitio Web junto con la secuencia de comandos de actualización StatsMan.ps1 en una sola carpeta en el equipo del agente de escucha.
    
2. Abra una ventana administrativa de PowerShell. Actualice el componente de escucha:
    
  ```
  .\Update-StatsMan.ps1 -Service Listener
  ```

> [!NOTE]
> La contraseña del servicio Administrador de estadísticas se mostrará en texto sin cifrar en la línea de comandos que se pasa al instalador. Asegúrese de blindar el monitor según sea necesario. 
  
1. Al ejecutar el script, se le pedirá que desinstale la versión anterior del producto. Responda Sí.
    
2. Si el servicio de escucha se está ejecutando, se le pedirá que cierre la aplicación antes de continuar. Permitir que la aplicación se cierre (el oyente Gestor de estadísticas se detendrá el servicio).
    
3. Continúe el proceso de instalación. Verá que la contraseña de servicio y la huella digital del certificado se han rellenado previamente. Si no es así, agregue los valores que guardó antes de continuar.
    
3. Abra una ventana administrativa de PowerShell. Actualice el componente del sitio web:
    
  ```
  .\Update-StatsMan.ps1 -Service Website
  ```

1. Al ejecutar el script, se le pedirá que desinstale la versión anterior del producto. Responda Sí.
    
2. Si el servicio de agente se está ejecutando, se le pedirá que cierre la aplicación antes de continuar. Permita el cierre de la aplicación (el servicio de agente StatsMan se detendrá).
    
3. Continúe el proceso de instalación. Verá que la contraseña de servicio y la huella digital del certificado se han rellenado previamente. Si no es así, agregue los valores que guardó antes de continuar.
    
4. Abra una ventana administrativa de PowerShell. Actualice el componente de agente:
    
  ```
  .\Update-StatsMan.ps1 -Service Agent
  ```

1. Al ejecutar el script, se le pedirá que desinstale la versión anterior del producto. Responda Sí.
    
2. Continúe el proceso de instalación. Verá que el puerto del sitio web se ha rellenado previamente. Si no es así, agregue el valor que guardó antes de continuar.
    
3. Compruebe que el sitio web funciona como se espera mediante el explorador.
    
> [!NOTE]
> La actualización del agente se puede usar con el conmutador -NoPrompt. Esto permitirá que el proceso de instalación/desinstalación se ejecute en silencio, lo que permite que herramientas como PSExec ejecuten la actualización de forma remota en un gran número de servidores. 
  
### <a name="manual-upgrade"></a>Actualización manual

Si, por algún motivo, se produce un error durante la actualización automática, puede realizar una actualización manual siguiendo estos pasos:
  
1. 	En el equipo de escucha, desinstale la escucha, el sitio web y el agente (si se instaló en este servidor) mediante el panel de control Programas y características.   
    
    > [!NOTE]
    >   Mantenga Redis instalado para que los datos de la caché se conserven durante el proceso de actualización.
  
2. 	Instale las nuevas versiones de los componentes, incluidos los valores que guardó anteriormente cuando se le pidan. Para obtener más información acerca de cómo instalar los componentes, vea [Implementar el administrador de estadísticas](deploy.md#BKMK_Deploy).
    
## <a name="known-issues-fixed-in-release-11"></a>Problemas conocidos corregidos en la versión 1.1
<a name="BKMK_Fixed"> </a>

En la versión 1.1 se han corregido los siguientes problemas conocidos:
  
- Interfaz de usuario/servidor/agente - numerosos confiabilidad significativa y mejoras en el rendimiento
    
- Interfaz de usuario: control de filtro principal ahora ordena correctamente con diferentes casos (se otorga gente piense determinados servidores no estaban en el sistema cuando eran)
    
- Servidor: los componentes de servidor ahora se instalarán en servidores que no sean en inglés
    
- Servidor/Agente: en algunos casos, los componentes de agente y servidor no se instalaban con errores .NET debido a una versión concreta de .NET 4.0. Se ha solucionado este problema.
    
- Agente: registro de eventos extendidos agregado para el agente de StatsMan. El agente ya no se bloqueará cuando se instale en un servidor que no esté en la topología y esto no se registrará en el registro de eventos, junto con muchas otras posibles condiciones de error.
    
- Interfaz de usuario - clientes Web mediante el Explorador de Chrome vería varias solicitudes de inicio de sesión cuando utiliza un equipo de cliente no unido al mismo grupo de trabajo o dominio que el servidor Manager de estadísticas Web. Ahora solo se requiere un único inicio de sesión por cada sesión.
    
## <a name="for-more-information"></a>Para más información
<a name="BKMK_Fixed"> </a>

Para obtener más información, consulte lo siguiente:
  
- [Plan para el Gestor de estadísticas de Skype para Business Server 2015](plan.md)
    
- [Implementar el administrador estadísticas de Skype para Business Server 2015](deploy.md)
    
- [Solucionar problemas de administrador de estadísticas de Skype para Business Server 2015](troubleshoot.md)
    
- [Skype para blog Business Manager de estadísticas de servidor](https://blogs.technet.microsoft.com/skypestatsman/)
    

