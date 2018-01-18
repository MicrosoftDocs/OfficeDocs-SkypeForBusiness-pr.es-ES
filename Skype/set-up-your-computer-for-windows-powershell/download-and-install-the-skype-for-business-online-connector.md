---
title: "Descargue e instale el Skype para el módulo de Business Connector en línea"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: 9c1cc3dc-7d6d-43ca-8e4a-7763a3f78cb3
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business
localization_priority: Normal
ROBOTS: None
f1keywords: None
ms.custom: PowerShell
description: "Descargar, instalar y, a continuación, utilizar el Skype para Business Connector en línea para crear una sesión remota de Windows PowerShell que se conecta a Skype para los negocios en línea. "
ms.openlocfilehash: b95b41937fea2ec87cb484cf557d85dcb3a77a8e
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/15/2017
---
# <a name="download-and-install-the-skype-for-business-online-connector-module"></a><span data-ttu-id="4bde2-103">Descargue e instale el Skype para el módulo de Business Connector en línea</span><span class="sxs-lookup"><span data-stu-id="4bde2-103">Download and install the Skype for Business Online Connector module</span></span>

<span data-ttu-id="4bde2-104">El Skype para el módulo de Business Connector en línea incluye el cmdlet **New-CsOnlineSession** , que le permite crear una sesión remota de Windows PowerShell que se conecta a Skype para los negocios en línea.</span><span class="sxs-lookup"><span data-stu-id="4bde2-104">The Skype for Business Online Connector module includes the **New-CsOnlineSession** cmdlet, which enables you to create a remote Windows PowerShell session that connects to Skype for Business Online.</span></span> <span data-ttu-id="4bde2-105">Este módulo, que sólo se admite en equipos de 64 bits (consulte [Configurar el equipo de Skype para la administración de negocios en línea mediante Windows PowerShell](set-up-your-computer-for-windows-powershell.md) para obtener más información), se puede descargar desde Microsoft Download Center en https:// [ www.Microsoft.com/en-us/download/details.aspx?id=39366](https://www.microsoft.com/en-us/download/details.aspx?id=39366).</span><span class="sxs-lookup"><span data-stu-id="4bde2-105">This module, which is supported only on 64-bit computers (see [Set up your computer for Skype for Business Online management using Windows PowerShell](set-up-your-computer-for-windows-powershell.md) for more information), can be downloaded from the Microsoft Download Center at [https://www.microsoft.com/en-us/download/details.aspx?id=39366](https://www.microsoft.com/en-us/download/details.aspx?id=39366).</span></span> <span data-ttu-id="4bde2-106">Descargue el archivo SkypeOnlinePowershell.exe y, a continuación, complete el procedimiento siguiente:</span><span class="sxs-lookup"><span data-stu-id="4bde2-106">Download the SkypeOnlinePowershell.exe file, and then complete the following procedure:</span></span>
  
1. <span data-ttu-id="4bde2-107">Haga doble clic en el archivo **SkypeOnlinePowershell.exe** .</span><span class="sxs-lookup"><span data-stu-id="4bde2-107">Double-click the **SkypeOnlinePowershell.exe** file.</span></span>
    
2. <span data-ttu-id="4bde2-108">En Skype para los negocios en línea, Asistente para la instalación de Windows PowerShell, en la página **Términos de licencia del Software de Microsoft** , seleccione **acepto los términos del contrato de licencia**y, a continuación, haga clic en **instalar**.</span><span class="sxs-lookup"><span data-stu-id="4bde2-108">In the Skype for Business Online, Windows PowerShell setup wizard, on the **Microsoft Software License Terms** page, select **I accept the terms in the License Agreement**, and then click **Install**.</span></span> <span data-ttu-id="4bde2-109">Si aparece el cuadro de diálogo **Control de cuentas de usuario** , haga clic en **Sí** para continuar con la instalación.</span><span class="sxs-lookup"><span data-stu-id="4bde2-109">If the **User Account Control** dialog box appears, click **Yes** to continue the installation.</span></span>
    
3. <span data-ttu-id="4bde2-110">En la página de **completado el Skype para los negocios en línea, módulo de Windows PowerShell** , haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="4bde2-110">On the **Completed the Skype for Business Online, Windows PowerShell Module** page, click **Finish**.</span></span>
    
<span data-ttu-id="4bde2-111">El programa de instalación copia el Skype para el módulo de Business Connector en línea (y el cmdlet **New-CsOnlineSession** ) en el equipo.</span><span class="sxs-lookup"><span data-stu-id="4bde2-111">The setup program copies the Skype for Business Online Connector module (and the **New-CsOnlineSession** cmdlet) to your computer.</span></span> <span data-ttu-id="4bde2-112">Para tener acceso al módulo, iniciar una sesión de Windows PowerShell con credenciales de administrador y, a continuación, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="4bde2-112">To access the module, start a Windows PowerShell session under administrator credentials, and then run the following command:</span></span>
  
```
Import-Module "C:\\Program Files\\Common Files\\Skype for Business Online\\Modules\\SkypeOnlineConnector\\SkypeOnlineConnector.psd1"
```

<span data-ttu-id="4bde2-113">Si no desea escribir este comando cada vez que inicie Windows PowerShell, puede agregar el comando a su perfil de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4bde2-113">If you don't want to type this command every time you start Windows PowerShell, you can add the command to your Windows PowerShell profile.</span></span> <span data-ttu-id="4bde2-114">Para ello, escriba el comando siguiente en el símbolo del sistema de Windows PowerShell y, a continuación, presione ENTRAR:</span><span class="sxs-lookup"><span data-stu-id="4bde2-114">To do that, type the following command at the Windows PowerShell prompt and then press ENTER:</span></span>
  
```
notepad.exe $profile
```

 <span data-ttu-id="4bde2-115">Cuando aparezca el Bloc de notas, agregue la siguiente línea al final de los comandos que ya están en el perfil (si existe):</span><span class="sxs-lookup"><span data-stu-id="4bde2-115">When Notepad appears, add the following line to the bottom of the commands that are already in the profile (if any):</span></span>
  
```
Import-Module SkypeOnlineConnector
```

<span data-ttu-id="4bde2-116">Guarde el archivo.</span><span class="sxs-lookup"><span data-stu-id="4bde2-116">Save the file.</span></span> <span data-ttu-id="4bde2-117">La próxima vez que inicie Windows PowerShell, se importará automáticamente el Skype para el módulo de Business Connector en línea.</span><span class="sxs-lookup"><span data-stu-id="4bde2-117">The next time you start Windows PowerShell, the Skype for Business Online Connector module will automatically be imported.</span></span> <span data-ttu-id="4bde2-118">Tenga en cuenta que recibirá un mensaje de error y no se cargará el módulo, si no está ejecutando Windows PowerShell con credenciales de administrador.</span><span class="sxs-lookup"><span data-stu-id="4bde2-118">Be aware that you will get an error message, and the module will not be loaded, if you are not running Windows PowerShell under administrator credentials.</span></span>
  
<span data-ttu-id="4bde2-119">Además de instalar el Skype para el módulo de Business Connector en línea, SkypeOnlinePowershell.exe también instala tres componentes adicionales: 1) la identidad servicio cliente Runtime Library (IDCRL), utilizado para controlar la autenticación del cliente Skype para empresas En línea; 2).NET Framework 4.5; y, 3) Microsoft Visual C++ 2012 (x64) paquete redistribuible (versión 11.0.50727).</span><span class="sxs-lookup"><span data-stu-id="4bde2-119">In addition to installing the Skype for Business Online Connector module, SkypeOnlinePowershell.exe also installs three additional components: 1) the Identity Service Client Runtime Library (IDCRL), used to handle client authentication to Skype for Business Online; 2) .NET Framework 4.5; and, 3) the Microsoft Visual C++ 2012 Redistributable (x64) package (version 11.0.50727).</span></span> <span data-ttu-id="4bde2-120">.NET Framework 4.5 proporciona la infraestructura utilizada para generar y ejecutar aplicaciones. NET, incluidos Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4bde2-120">.NET Framework 4.5 provides the infrastructure used for building and running .NET applications, including Windows PowerShell.</span></span> <span data-ttu-id="4bde2-121">El paquete redistribuible de Visual C++ instala componentes de tiempo de ejecución de Visual C++ para equipos que no tienen instalado Microsoft Visual Studio 2012.</span><span class="sxs-lookup"><span data-stu-id="4bde2-121">The Visual C++ Redistributable package installs Visual C++ runtime components for computers that do not have Microsoft Visual Studio 2012 installed.</span></span>
  
<span data-ttu-id="4bde2-122">Para comprobar el número de versión del módulo de conector que está instalado actualmente en el equipo, abra Panel de Control, abra **programas y características**y, a continuación, compruebe el número de versión para el **Skype para los negocios en línea, módulo de Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="4bde2-122">To verify the version number of the Connector module that is currently installed on your computer, open Control Panel, open **Programs and Features**, and then check the version number for the **Skype for Business Online, Windows PowerShell Module**.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="4bde2-123">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="4bde2-123">Related topics</span></span>
[<span data-ttu-id="4bde2-124">Configurar el equipo de Skype para la administración de negocios en línea mediante Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="4bde2-124">Set up your computer for skype for business online management using Windows PowerShell</span></span>](set-up-your-computer-for-windows-powershell.md)
