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
description: 'Summary: Learn about the servers and server roles you must configure before you install Skype for Business Server 2015. Download a free trial of Skype for Business Server 2015 from the Microsoft Evaluation center at: https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server.'
ms.openlocfilehash: 6f84b4f0a95c45297ad809e6b04217e711c3dd5e
ms.sourcegitcommit: dea27df69d948b7b9cc017b7023c4013cee8e4d1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/16/2018
---
# <a name="install-prerequisites-for-skype-for-business-server-2015"></a>Instalar requisitos previos para Skype Empresarial Server 2015
 
**Summary:** Learn about the servers and server roles you must configure before you install Skype for Business Server 2015. Download a free trial of Skype for Business Server 2015 from the [Microsoft Evaluation center](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).
  
Installing prerequisites consists of setting up Windows Server by installing the required roles and features on each of the servers in the topology. The requirements are based on the role the server will fulfill in the topology. You can do steps 1 through 5 in any order. However, you must do steps 6, 7, and 8 in order, and after steps 1 through 5, as outlined in the diagram. Installing prerequisites is step 1 of 8.
  
![Diagrama de información general: requisitos previos de instalación.](../../media/0a85349b-b398-4e04-8901-8f4bd25d8afe.png)
  
## <a name="setup-windows-server"></a>Configurar Windows Server

Skype for Business Server 2015 requires the Windows Server operating system and a number of prerequisites before it can be installed. For details on planning for prerequisites, see [Server requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md). 
  
> [!TIP]
> Este procedimiento utiliza Windows Server 2012 R2. Es posible que el procedimiento sea un poco diferente si usa una versión de Windows Server distinta. 
  
> [!IMPORTANT]
> Before you begin, make sure that Windows Server is up-to-date by using Windows Update. 
  
![Windows Server actualizado.](../../media/a8d57a97-a55e-443b-b304-c534ae9a71b2.png)
  
Vea los pasos del vídeo para **instalar los requisitos previos**:
  
> [!video https://www.microsoft.com/en-us/videoplayer/embed/02447c2a-5b26-432f-aad6-b9b05cc93478?autoplay=false]
  
### <a name="install-required-roles-and-features-for-front-end-servers"></a>Instalar las características y los roles necesarios para los servidores front-end

1. Abra el Administrador de servidores y haga clic en **Agregar roles y características**.
    
2. Lea la página **Antes de empezar** para conocer la instalación de los roles y las características de Windows Server y, luego, haga clic en **Siguiente**.
    
3. Seleccione **Instalación basada en características o en roles** y haga clic en **Siguiente**.
    
4. Select the server on which you will be installing Skype for Business Server 2015, and click **Next**.
    
5. Seleccione el rol **Servidor web (IIS)**. Cuando se abra la ventana de características necesarias, haga clic en **Agregar características** y, luego, haga clic en **Siguiente**.
    
6. Make sure the software features listed in [Software that should be installed before a Skype for Business Server 2015 deployment](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md#Software) are on the server that will run Skype for Business Server 2015. Here's an abbreviated list:
    
   - .NET Framework Features
    
   - Servicios de WCF
    
   - Activación HTTP
    
    > [!NOTE]
    > La activación HTTP necesita características adicionales. Haga clic en **Agregar características** en el cuadro de diálogo de advertencia que se abre al seleccionar Activación HTTP.
  
   - Media Foundation (required by Front End Servers and Standard Edition servers used for conferencing.)
    
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
    > De forma predeterminada, Windows Server 2012 R2 no instala todos los archivos de origen de las características necesarias. Si el servidor no está conectado a Internet, necesitará insertar el disco de Windows Server 2012 R2 y seleccionar **Especifique una ruta de acceso de origen alternativa** para instalar las características necesarias. Los archivos de origen se encuentran en el directorio sources\sxs. Por ejemplo, si el disco de Windows Server 2012 R2 se encuentra en la unidad D, la ruta de acceso será `d:\sources\sxs`. > It is important that you have the latest updates from Windows Update. Si no se encuentra conectado a Internet, necesitará instalar todas las actualizaciones relevantes de manera manual, así como también todos los requisitos previos de las actualizaciones necesarias. 
  
12. Cuando el cuadro de diálogo indica que se ha completado la instalación, necesitará reiniciar el servidor para completar el proceso.
    
13. Ejecute **Windows Update** nuevamente para comprobar si hay actualizaciones de los roles y los servicios que se instalaron.
    
14. If you will be using Skype for Business Server Control Panel on this server then you must also install Silverlight. To install Silverlight, see [Microsoft Silverlight](https://www.microsoft.com/silverlight/).
    
The prerequisites can be installed by running the following PowerShell command. Note that the command looks for source files in a specific order. If you are online, the command accesses Windows Update. However, if you are offline, you need to make sure the source files are available to the command. For more information about using PowerShell to install roles and features, see [Install or Uninstall Roles, Role Services, or Features](https://technet.microsoft.com/en-us/library/hh831809.aspx) and [Install-WindowsFeature](https://technet.microsoft.com/en-us/library/jj205467.aspx). Don't forget to run Windows Update again after you install prerequisites, even if you use the PowerShell command.
```
Add-WindowsFeature NET-Framework-Core, RSAT-ADDS, Windows-Identity-Foundation, Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Dir-Browsing, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, Web-Dyn-Compression, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Mgmt-Tools, Web-Scripting-Tools, Web-Mgmt-Compat, Server-Media-Foundation, BITS
```

> [!IMPORTANT]
> Los servidores que desempeñan roles distintos del de servidor front-end (como el rol de director, chat persistente o servidor perimetral) tienen sus propios requisitos previos. For details on the exact prerequisites required by each server type, see [Server requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md). 
  

