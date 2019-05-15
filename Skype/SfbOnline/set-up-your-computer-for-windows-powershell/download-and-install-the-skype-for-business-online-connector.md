---
title: Descargue e instale el Skype para el módulo del conector en línea de negocio
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 9c1cc3dc-7d6d-43ca-8e4a-7763a3f78cb3
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- PowerShell
description: 'Descargar, instalar y, a continuación, use el Skype para Business Connector en línea para crear una sesión remota de Windows PowerShell que se conecta a Skype para profesionales en línea. '
ms.openlocfilehash: a93cf1d3d09910001f25619969b6d504e23ec36f
ms.sourcegitcommit: 85b135cf622c9e9eb1857ef953bc618dc2cdb51e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "34036696"
---
# <a name="download-and-install-the-skype-for-business-online-connector-module"></a><span data-ttu-id="965bb-103">Descargue e instale el Skype para el módulo del conector en línea de negocio</span><span class="sxs-lookup"><span data-stu-id="965bb-103">Download and install the Skype for Business Online Connector module</span></span>

<span data-ttu-id="965bb-104">El Skype para módulo Business Connector Online incluye el cmdlet **New-CsOnlineSession** , que le permite crear una sesión remota de Windows PowerShell que se conecta a Skype para profesionales en línea.</span><span class="sxs-lookup"><span data-stu-id="965bb-104">The Skype for Business Online Connector module includes the **New-CsOnlineSession** cmdlet, which enables you to create a remote Windows PowerShell session that connects to Skype for Business Online.</span></span> <span data-ttu-id="965bb-105">En este módulo, que sólo se admite en equipos de 64 bits (vea [Configurar el equipo para Skype para la administración en línea de negocio con Windows PowerShell](set-up-your-computer-for-windows-powershell.md) para obtener más información), se pueden descargar desde Microsoft Download Center en [https://www.microsoft.com/download/details.aspx?id=39366](https://www.microsoft.com/download/details.aspx?id=39366).</span><span class="sxs-lookup"><span data-stu-id="965bb-105">This module, which is supported only on 64-bit computers (see [Set up your computer for Skype for Business Online management using Windows PowerShell](set-up-your-computer-for-windows-powershell.md) for more information), can be downloaded from the Microsoft Download Center at [https://www.microsoft.com/download/details.aspx?id=39366](https://www.microsoft.com/download/details.aspx?id=39366).</span></span> <span data-ttu-id="965bb-106">Descargue el archivo SkypeOnlinePowershell.exe y, a continuación, complete el siguiente procedimiento:</span><span class="sxs-lookup"><span data-stu-id="965bb-106">Download the SkypeOnlinePowershell.exe file, and then complete the following procedure:</span></span>
  
1. <span data-ttu-id="965bb-107">Haga doble clic en el archivo **SkypeOnlinePowershell.exe** .</span><span class="sxs-lookup"><span data-stu-id="965bb-107">Double-click the **SkypeOnlinePowershell.exe** file.</span></span>
    
2. <span data-ttu-id="965bb-108">En Skype para profesionales en línea, Asistente de instalación de Windows PowerShell, en la página **Términos de licencia del Software de Microsoft** , seleccione **acepto los términos del contrato de licencia**y, a continuación, haga clic en **instalar**.</span><span class="sxs-lookup"><span data-stu-id="965bb-108">In the Skype for Business Online, Windows PowerShell setup wizard, on the **Microsoft Software License Terms** page, select **I accept the terms in the License Agreement**, and then click **Install**.</span></span> <span data-ttu-id="965bb-109">Si aparece el cuadro de diálogo **Control de cuentas de usuario** , haga clic en **Sí** para continuar con la instalación.</span><span class="sxs-lookup"><span data-stu-id="965bb-109">If the **User Account Control** dialog box appears, click **Yes** to continue the installation.</span></span>
    
3. <span data-ttu-id="965bb-110">En la página de **completado el Skype para Online de negocio, módulo de Windows PowerShell** , haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="965bb-110">On the **Completed the Skype for Business Online, Windows PowerShell Module** page, click **Finish**.</span></span>
    
<span data-ttu-id="965bb-111">El programa de instalación copia el Skype para el módulo del conector en línea de negocio (y el cmdlet **New-CsOnlineSession** ) a su equipo.</span><span class="sxs-lookup"><span data-stu-id="965bb-111">The setup program copies the Skype for Business Online Connector module (and the **New-CsOnlineSession** cmdlet) to your computer.</span></span> <span data-ttu-id="965bb-112">Para tener acceso al módulo, iniciar una sesión de Windows PowerShell con credenciales de administrador y, a continuación, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="965bb-112">To access the module, start a Windows PowerShell session under administrator credentials, and then run the following command:</span></span>
  
```
Import-Module "C:\\Program Files\\Common Files\\Skype for Business Online\\Modules\\SkypeOnlineConnector\\SkypeOnlineConnector.psd1"
```

<span data-ttu-id="965bb-113">Si no desea que se escriba este comando cada vez que inicie Windows PowerShell, puede agregar el comando a su perfil de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="965bb-113">If you don't want to type this command every time you start Windows PowerShell, you can add the command to your Windows PowerShell profile.</span></span> <span data-ttu-id="965bb-114">Para ello, escriba el siguiente comando en el símbolo del sistema de Windows PowerShell y, a continuación, presione ENTRAR:</span><span class="sxs-lookup"><span data-stu-id="965bb-114">To do that, type the following command at the Windows PowerShell prompt and then press ENTER:</span></span>
  
```
notepad.exe $profile
```

 <span data-ttu-id="965bb-115">Cuando aparezca el Bloc de notas, agregue la línea siguiente a la parte inferior de los comandos que ya están en el perfil (si hay alguno):</span><span class="sxs-lookup"><span data-stu-id="965bb-115">When Notepad appears, add the following line to the bottom of the commands that are already in the profile (if any):</span></span>
  
```
Import-Module SkypeOnlineConnector
```

<span data-ttu-id="965bb-116">Guarde el archivo.</span><span class="sxs-lookup"><span data-stu-id="965bb-116">Save the file.</span></span> <span data-ttu-id="965bb-117">La próxima vez que inicie Windows PowerShell, automáticamente se importará la Skype para el módulo del conector en línea de negocio.</span><span class="sxs-lookup"><span data-stu-id="965bb-117">The next time you start Windows PowerShell, the Skype for Business Online Connector module will automatically be imported.</span></span> <span data-ttu-id="965bb-118">Tenga en cuenta que recibirá un mensaje de error y no se cargará el módulo, si no se está ejecutando Windows PowerShell con credenciales de administrador.</span><span class="sxs-lookup"><span data-stu-id="965bb-118">Be aware that you will get an error message, and the module will not be loaded, if you are not running Windows PowerShell under administrator credentials.</span></span>
  
<span data-ttu-id="965bb-119">Además de instalar el Skype para el módulo del conector en línea de negocio, SkypeOnlinePowershell.exe también instala tres componentes adicionales: 1) la identidad de servicio de cliente en tiempo de ejecución biblioteca (IDCRL), usado para controlar la autenticación de cliente para Skype para la empresa En línea; (2) .NET framework 4.5; y, 3) el paquete de Microsoft Visual C++ 2012 redistribuible (x64) (versión 11.0.50727).</span><span class="sxs-lookup"><span data-stu-id="965bb-119">In addition to installing the Skype for Business Online Connector module, SkypeOnlinePowershell.exe also installs three additional components: 1) the Identity Service Client Runtime Library (IDCRL), used to handle client authentication to Skype for Business Online; 2) .NET Framework 4.5; and, 3) the Microsoft Visual C++ 2012 Redistributable (x64) package (version 11.0.50727).</span></span> <span data-ttu-id="965bb-120">.NET framework 4.5 proporciona la infraestructura que se usa para generar y ejecutar aplicaciones. NET, incluyendo Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="965bb-120">.NET Framework 4.5 provides the infrastructure used for building and running .NET applications, including Windows PowerShell.</span></span> <span data-ttu-id="965bb-121">El paquete redistribuible de Visual C++ instala los componentes de tiempo de ejecución de Visual C++ para equipos que no tienen instalado Microsoft Visual Studio 2012.</span><span class="sxs-lookup"><span data-stu-id="965bb-121">The Visual C++ Redistributable package installs Visual C++ runtime components for computers that do not have Microsoft Visual Studio 2012 installed.</span></span>
  
<span data-ttu-id="965bb-122">Para comprobar el número de versión del módulo de conector que actualmente está instalado en su equipo, abra el Panel de Control, abra **programas y características**y, a continuación, compruebe el número de versión para el **Skype para Online de negocio, módulo de Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="965bb-122">To verify the version number of the Connector module that is currently installed on your computer, open Control Panel, open **Programs and Features**, and then check the version number for the **Skype for Business Online, Windows PowerShell Module**.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="965bb-123">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="965bb-123">Related topics</span></span>
[<span data-ttu-id="965bb-124">Configurar el equipo para Skype para la administración en línea de negocio con Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="965bb-124">Set up your computer for skype for business online management using Windows PowerShell</span></span>](set-up-your-computer-for-windows-powershell.md)

  
 
