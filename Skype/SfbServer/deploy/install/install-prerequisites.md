---
title: Instalar requisitos previos para Skype Empresarial Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 2/7/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 2ef91a1e-2899-44c8-8e2c-527cb9114a0a
description: 'Resumen: Conozca los servidores y roles de servidor que debe configurar antes de instalar Skype para Business Server 2015. Descargue una prueba gratuita de Skype para Business Server 2015 desde el centro de Evaluation de Microsoft en: https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server.'
ms.openlocfilehash: 350f64a2808e51866cd5720cb1955259ff773c81
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="install-prerequisites-for-skype-for-business-server-2015"></a>Instalar requisitos previos para Skype Empresarial Server 2015
 
**Resumen:** Obtenga información sobre los servidores y roles de servidor que debe configurar antes de instalar Skype para Business Server 2015. Descargue una prueba gratuita de Skype para Business Server 2015 desde el [Centro de evaluación de Microsoft](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).
  
Instalar los requisitos previos consiste en configurar el servidor de Windows mediante la instalación de las características y funciones requeridas en cada uno de los servidores de la topología. Los requisitos se basan en la función que cumpliría el servidor en la topología. Puede realizar los pasos 1 a 5 en cualquier orden. Sin embargo, debe realizar los pasos 6, 7 y 8 en orden y después los pasos del 1 al 5, tal como se indica en el diagrama. Instalar los requisitos previos es el paso 1 de 8.
  
![Diagrama de información general: requisitos previos de instalación.](../../media/0a85349b-b398-4e04-8901-8f4bd25d8afe.png)
  
## <a name="setup-windows-server"></a>Configurar Windows Server

Skype para Business Server 2015 requiere el sistema operativo Windows Server y una serie de requisitos previos para poder instalar. Para obtener más información acerca de cómo planear los requisitos previos, consulte [requisitos del servidor para Skype para Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md). 
  
> [!TIP]
> Este procedimiento utiliza Windows Server 2012 R2. Es posible que el procedimiento sea un poco diferente si usa una versión de Windows Server distinta. 
  
> [!IMPORTANT]
> Antes de comenzar, asegúrese de que Windows Server está actualizado con Windows Update. 
  
![Windows Server actualizado.](../../media/a8d57a97-a55e-443b-b304-c534ae9a71b2.png)
  
Vea los pasos del vídeo para **instalar los requisitos previos**:
  
![Su explorador no admite vídeo. Instale Microsoft Silverlight, Adobe Flash Player o Internet Explorer 9.](../../media/MSN_Video_Widget.gif)
  
### <a name="install-required-roles-and-features-for-front-end-servers"></a>Instalar las características y los roles necesarios para los servidores front-end

1. Abra el Administrador de servidores y haga clic en **Agregar roles y características**.
    
2. Lea la página **Antes de empezar** para conocer la instalación de los roles y las características de Windows Server y, luego, haga clic en **Siguiente**.
    
3. Seleccione **Instalación basada en características o en roles** y haga clic en **Siguiente**.
    
4. Seleccione el servidor en el que se puede instalar Skype para Business Server 2015 y haga clic en **siguiente**.
    
5. Seleccione el rol **Servidor web (IIS)**. Cuando se abra la ventana de características necesarias, haga clic en **Agregar características** y, luego, haga clic en **Siguiente**.
    
6. Asegúrese de que las características de software enumeradas en [Software que debe instalarse antes un Skype para la implementación de Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md#Software) están en el servidor que ejecutará Skype para Business Server 2015. Aquí está una lista abreviada:
    
   - Características de.NET Framework
    
   - Servicios de WCF
    
   - Activación HTTP
    
    > [!NOTE]
    > La activación HTTP necesita características adicionales. Haga clic en **Agregar características** en el cuadro de diálogo de advertencia que se abre al seleccionar Activación HTTP.
  
   - Media Foundation (requerido por servidores de servidores frontales y Standard Edition utilizados para conferencias).
    
   - Herramientas de administración remota del servidor
    
   - Herramientas de administración de roles
    
   - AD DS 
    
   - AD LDS
    
   - Windows Identity Foundation 3.5
    
7. Haga clic en **Siguiente** para continuar con el asistente.
    
8. Lea las notas sobre el **Rol de servidor web (IIS)** y, luego, haga clic en **Siguiente**.
    
9. Seleccione los siguientes **Servicios de rol de servidor web (IIS)**.
    
   - Características HTTP comunes
    
   - Documento predeterminado
    
   - Examen de directorios
    
   - Errores HTTP
    
   - Contenido estático
    
   - Estado y diagnóstico
    
   - Registro HTTP
    
   - Herramientas de registro
    
   - Seguimiento
    
   - Rendimiento
    
   - Compresión de contenido estático
    
   - Compresión de contenido dinámico
    
   - Seguridad
    
   - Filtro de solicitudes
    
   - Autenticación por asignación de certificados de clientes
    
   - Autenticación de Windows
    
   - Desarrollo de aplicaciones
    
   - Extensibilidad de .NET 3.5
    
   - Extensibilidad de .NET 4.5
    
   - ASP.NET 3.5
    
   - ASP.NET 4.5
    
   - Extensiones ISAPI
    
   - Filtros ISAPI
    
   - Herramientas de administración
    
   - Consola de administración de IIS
    
   - Scripts y herramientas de administración de IIS
    
10. Haga clic en **Siguiente** para continuar con el asistente.
    
11. Revise las selecciones de la instalación para asegurarse de haber seleccionado todos los requisitos y, luego, haga clic en **Instalar**.
    
    > [!CAUTION]
    > De forma predeterminada, Windows Server 2012 R2 no instala todos los archivos de origen de las características necesarias. Si el servidor no está conectado a Internet, necesitará insertar el disco de Windows Server 2012 R2 y seleccionar **Especifique una ruta de acceso de origen alternativa** para instalar las características necesarias. Los archivos de origen se encuentran en el directorio sources\sxs. Por ejemplo, si el disco de Windows Server 2012 R2 se encuentra en la unidad D, la ruta de acceso será `d:\sources\sxs`. > Es importante que tiene las actualizaciones más recientes de Windows Update. Si no se encuentra conectado a Internet, necesitará instalar todas las actualizaciones relevantes de manera manual, así como también todos los requisitos previos de las actualizaciones necesarias. 
  
12. Cuando el cuadro de diálogo indica que se ha completado la instalación, necesitará reiniciar el servidor para completar el proceso.
    
13. Ejecute **Windows Update** nuevamente para comprobar si hay actualizaciones de los roles y los servicios que se instalaron.
    
14. Si va a utilizar Skype para Panel de Control de servidor empresarial en este servidor también debe instalar Silverlight. Para instalar Silverlight, vea [Microsoft Silverlight](https://www.microsoft.com/silverlight/).
    
Los requisitos previos pueden instalarse ejecutando el siguiente comando de PowerShell. Tenga en cuenta que el comando busca los archivos de código fuente en un orden específico. Si está conectado, el comando tiene acceso a Windows Update. Sin embargo, si está desconectado, debe asegurarse de que los archivos de origen están disponibles para el comando. Para obtener más información sobre cómo usar PowerShell para instalar funciones y características, vea [instalar o desinstalar las funciones, servicios de rol o características](https://technet.microsoft.com/en-us/library/hh831809.aspx) y [Install-WindowsFeature](https://technet.microsoft.com/en-us/library/jj205467.aspx). No olvide volver a ejecutar Windows Update después de instalar los requisitos previos, incluso si se utiliza el comando de PowerShell.
```
Add-WindowsFeature NET-Framework-Core, RSAT-ADDS, Windows-Identity-Foundation, Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Dir-Browsing, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, Web-Dyn-Compression, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Mgmt-Tools, Web-Scripting-Tools, Web-Mgmt-Compat, Server-Media-Foundation, BITS
```

> [!IMPORTANT]
> Los servidores que desempeñan roles distintos del de servidor front-end (como el rol de director, chat persistente o servidor perimetral) tienen sus propios requisitos previos. Para obtener detalles sobre los requisitos previos exactos necesarios para cada tipo de servidor, consulte [requisitos del servidor para Skype para Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md). 
  

