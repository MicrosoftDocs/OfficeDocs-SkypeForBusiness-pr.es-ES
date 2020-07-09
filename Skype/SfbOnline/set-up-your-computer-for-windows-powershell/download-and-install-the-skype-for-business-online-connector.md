---
title: Descargar e instalar el módulo conector de Skype empresarial online
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
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- PowerShell
description: 'Descargue, instale y use el conector de Skype empresarial online para crear una sesión remota de Windows PowerShell que se conecte a Skype empresarial online. '
ms.openlocfilehash: 8c5068c221c46f7be0d9d97c1c3d515ae244b316
ms.sourcegitcommit: 90939ad992e65f840e4c2e7a6d18d821621319b4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/09/2020
ms.locfileid: "45085706"
---
# <a name="download-and-install-the-skype-for-business-online-connector-module"></a><span data-ttu-id="76c6c-103">Descargar e instalar el módulo conector de Skype empresarial online</span><span class="sxs-lookup"><span data-stu-id="76c6c-103">Download and install the Skype for Business Online Connector module</span></span>

> [!NOTE]
> <span data-ttu-id="76c6c-104">La versión más reciente de la [versión preliminar pública de Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/) está integrada en el conector de Skype empresarial online, que ofrece un único módulo para la administración de PowerShell de Teams.</span><span class="sxs-lookup"><span data-stu-id="76c6c-104">The latest [Teams PowerShell public preview release](https://www.powershellgallery.com/packages/MicrosoftTeams/) is integrated with Skype for Business Online Connector, providing a single module for Teams PowerShell management.</span></span>

<span data-ttu-id="76c6c-105">El módulo conector de Skype empresarial online incluye el cmdlet **New-CsOnlineSession** , que le permite crear una sesión remota de Windows PowerShell que se conecta a Skype empresarial online.</span><span class="sxs-lookup"><span data-stu-id="76c6c-105">The Skype for Business Online Connector module includes the **New-CsOnlineSession** cmdlet, which enables you to create a remote Windows PowerShell session that connects to Skype for Business Online.</span></span> <span data-ttu-id="76c6c-106">Este módulo, que solo es compatible con los equipos de 64 bits (consulte [configurar el equipo para la administración de Skype empresarial online con Windows PowerShell](set-up-your-computer-for-windows-powershell.md) para obtener más información), se puede descargar desde el centro de descarga de Microsoft en [https://www.microsoft.com/download/details.aspx?id=39366](https://www.microsoft.com/download/details.aspx?id=39366) .</span><span class="sxs-lookup"><span data-stu-id="76c6c-106">This module, which is supported only on 64-bit computers (see [Set up your computer for Skype for Business Online management using Windows PowerShell](set-up-your-computer-for-windows-powershell.md) for more information), can be downloaded from the Microsoft Download Center at [https://www.microsoft.com/download/details.aspx?id=39366](https://www.microsoft.com/download/details.aspx?id=39366).</span></span> <span data-ttu-id="76c6c-107">Descargue el archivo de SkypeOnlinePowershell.exe y, a continuación, realice el siguiente procedimiento:</span><span class="sxs-lookup"><span data-stu-id="76c6c-107">Download the SkypeOnlinePowershell.exe file, and then complete the following procedure:</span></span>
  
1. <span data-ttu-id="76c6c-108">Haga doble clic en el archivo **SkypeOnlinePowershell.exe** .</span><span class="sxs-lookup"><span data-stu-id="76c6c-108">Double-click the **SkypeOnlinePowershell.exe** file.</span></span>
    
2. <span data-ttu-id="76c6c-109">En el Asistente para la instalación de Skype empresarial online, en la página **términos de licencia del software de Microsoft** , seleccione Acepto **los términos del contrato de licencia**y, a continuación, haga clic en **instalar**.</span><span class="sxs-lookup"><span data-stu-id="76c6c-109">In the Skype for Business Online, Windows PowerShell setup wizard, on the **Microsoft Software License Terms** page, select **I accept the terms in the License Agreement**, and then click **Install**.</span></span> <span data-ttu-id="76c6c-110">Si aparece el cuadro de diálogo **control de cuentas de usuario** , haga clic en **sí** para continuar con la instalación.</span><span class="sxs-lookup"><span data-stu-id="76c6c-110">If the **User Account Control** dialog box appears, click **Yes** to continue the installation.</span></span>
    
3. <span data-ttu-id="76c6c-111">En la página **completado de Skype empresarial online, módulo de Windows PowerShell** , haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="76c6c-111">On the **Completed the Skype for Business Online, Windows PowerShell Module** page, click **Finish**.</span></span>
    
<span data-ttu-id="76c6c-112">El programa de instalación copia el módulo del conector de Skype empresarial online (y el cmdlet **New-CsOnlineSession** ) en el equipo.</span><span class="sxs-lookup"><span data-stu-id="76c6c-112">The setup program copies the Skype for Business Online Connector module (and the **New-CsOnlineSession** cmdlet) to your computer.</span></span> <span data-ttu-id="76c6c-113">Para acceder al módulo, inicie una sesión de Windows PowerShell con credenciales de administrador y, a continuación, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="76c6c-113">To access the module, start a Windows PowerShell session under administrator credentials, and then run the following command:</span></span>
  
```PowerShell
Import-Module "C:\Program Files\Common Files\Skype for Business Online\Modules\SkypeOnlineConnector\SkypeOnlineConnector.psd1"
```

<span data-ttu-id="76c6c-114">Si no desea escribir este comando cada vez que inicie Windows PowerShell, puede Agregar el comando a su perfil de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="76c6c-114">If you don't want to type this command every time you start Windows PowerShell, you can add the command to your Windows PowerShell profile.</span></span> <span data-ttu-id="76c6c-115">Para ello, escriba el siguiente comando en el símbolo del sistema de Windows PowerShell y, a continuación, presione ENTRAR:</span><span class="sxs-lookup"><span data-stu-id="76c6c-115">To do that, type the following command at the Windows PowerShell prompt and then press ENTER:</span></span>
  
```PowerShell
notepad.exe $profile
```

 <span data-ttu-id="76c6c-116">Cuando aparezca el Bloc de notas, agregue la línea siguiente en la parte inferior de los comandos que ya están en el perfil (si hay alguno):</span><span class="sxs-lookup"><span data-stu-id="76c6c-116">When Notepad appears, add the following line to the bottom of the commands that are already in the profile (if any):</span></span>
  
```PowerShell
Import-Module SkypeOnlineConnector
```

<span data-ttu-id="76c6c-117">Guarde el archivo.</span><span class="sxs-lookup"><span data-stu-id="76c6c-117">Save the file.</span></span> <span data-ttu-id="76c6c-118">La próxima vez que inicie Windows PowerShell, el módulo conector de Skype empresarial online se importará automáticamente.</span><span class="sxs-lookup"><span data-stu-id="76c6c-118">The next time you start Windows PowerShell, the Skype for Business Online Connector module will automatically be imported.</span></span> <span data-ttu-id="76c6c-119">Tenga en cuenta que recibirá un mensaje de error y el módulo no se cargará, si no está ejecutando Windows PowerShell con credenciales de administrador.</span><span class="sxs-lookup"><span data-stu-id="76c6c-119">Be aware that you will get an error message, and the module will not be loaded, if you are not running Windows PowerShell under administrator credentials.</span></span>
  
<span data-ttu-id="76c6c-120">Además de instalar el módulo conector de Skype empresarial online, SkypeOnlinePowershell.exe también instala tres componentes adicionales: 1) la biblioteca de tiempo de ejecución de cliente del servicio de identidad (IDCRL), que se usa para controlar la autenticación del cliente a Skype empresarial online. 2) .NET Framework 4,5; y 3) el paquete redistribuible de Microsoft Visual C++ 2012 (x64) (versión 11.0.50727).</span><span class="sxs-lookup"><span data-stu-id="76c6c-120">In addition to installing the Skype for Business Online Connector module, SkypeOnlinePowershell.exe also installs three additional components: 1) the Identity Service Client Runtime Library (IDCRL), used to handle client authentication to Skype for Business Online; 2) .NET Framework 4.5; and, 3) the Microsoft Visual C++ 2012 Redistributable (x64) package (version 11.0.50727).</span></span> <span data-ttu-id="76c6c-121">.NET Framework 4,5 proporciona la infraestructura que se usa para crear y ejecutar aplicaciones .NET, incluido Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="76c6c-121">.NET Framework 4.5 provides the infrastructure used for building and running .NET applications, including Windows PowerShell.</span></span> <span data-ttu-id="76c6c-122">El paquete redistribuible de Visual C++ instala componentes de tiempo de ejecución de Visual C++ para equipos que no tienen instalado Microsoft Visual Studio 2012.</span><span class="sxs-lookup"><span data-stu-id="76c6c-122">The Visual C++ Redistributable package installs Visual C++ runtime components for computers that do not have Microsoft Visual Studio 2012 installed.</span></span>
  
<span data-ttu-id="76c6c-123">Para comprobar el número de versión del módulo de conector instalado actualmente en el equipo, abra el panel de control, Abra **programas y características**y, a continuación, compruebe el número de versión de **Skype empresarial online, módulo de Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="76c6c-123">To verify the version number of the Connector module that is currently installed on your computer, open Control Panel, open **Programs and Features**, and then check the version number for the **Skype for Business Online, Windows PowerShell Module**.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="76c6c-124">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="76c6c-124">Related topics</span></span>
[<span data-ttu-id="76c6c-125">Configurar el equipo para la administración de Skype empresarial online con Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="76c6c-125">Set up your computer for skype for business online management using Windows PowerShell</span></span>](set-up-your-computer-for-windows-powershell.md)

  
 
