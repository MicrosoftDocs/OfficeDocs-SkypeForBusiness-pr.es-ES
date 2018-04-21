---
title: Utilizar la herramienta de recuperación de sistemas de salas de Skype v2
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 4/17/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: df418e25-81fd-474d-be16-5cd1ac8145cc
description: En este artículo se describe cómo utilizar la herramienta de recuperación de sistemas de salas de Skype v2, que se pueden utilizar para traer un sistema obsoleto en un estado admitido.
ms.openlocfilehash: 7c7a6188ec1cbd1153c09b768e81789fcffd266e
ms.sourcegitcommit: a72a1b71a8ef8e9581038503130c2c1a58a4abdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/20/2018
---
# <a name="use-the-skype-room-systems-v2-recovery-tool"></a><span data-ttu-id="1319a-103">Utilizar la herramienta de recuperación de sistemas de salas de Skype v2</span><span class="sxs-lookup"><span data-stu-id="1319a-103">Use the Skype Room Systems v2 recovery tool</span></span>
 
<span data-ttu-id="1319a-104">En este artículo se describe cómo utilizar la herramienta de recuperación de sistemas de salas de Skype v2, que se pueden utilizar para traer un sistema obsoleto en un estado admitido.</span><span class="sxs-lookup"><span data-stu-id="1319a-104">This article discusses how to use the recovery tool for Skype Room Systems v2, which you would use to bring an out of date system into a supported state.</span></span> <span data-ttu-id="1319a-105">Cuando la consola de sistemas de salas de Skype v2 muestra un error "config de sistema obsoleto", se utilizaría esta herramienta.</span><span class="sxs-lookup"><span data-stu-id="1319a-105">You would use this tool when the Skype Room Systems v2 console shows a "system config out of date" error.</span></span>
  

<span data-ttu-id="1319a-106"><a name="Prerequisites"> </a></span><span class="sxs-lookup"><span data-stu-id="1319a-106"></span></span>  
## <a name="prerequisites"></a><span data-ttu-id="1319a-107">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="1319a-107">Prerequisites</span></span>

<span data-ttu-id="1319a-108">Descargue el último [paquete de instalación de sistemas de salas de Skype v2](https://go.microsoft.com/fwlink/?linkid=851168) y extraerlo a un USB memory stick o recurso compartido accesible para el dispositivo de los sistemas de salas de Skype v2.</span><span class="sxs-lookup"><span data-stu-id="1319a-108">Download the latest [Skype Room Systems v2 installation package](https://go.microsoft.com/fwlink/?linkid=851168) and extract it to a USB memory stick or network share accessible to the Skype Room Systems v2 device.</span></span>

<span data-ttu-id="1319a-109">También debe instalar [KB4089848](http://download.windowsupdate.com/d/msdownload/update/software/updt/2018/03/windows10.0-kb4089848-x64_db7c5aad31c520c6983a937c3d53170e84372b11.msu).</span><span class="sxs-lookup"><span data-stu-id="1319a-109">You may also need to install [KB4089848](http://download.windowsupdate.com/d/msdownload/update/software/updt/2018/03/windows10.0-kb4089848-x64_db7c5aad31c520c6983a937c3d53170e84372b11.msu).</span></span>

<span data-ttu-id="1319a-110"><a name="Windows-ver"> </a></span><span class="sxs-lookup"><span data-stu-id="1319a-110"></span></span>
## <a name="verify-windows-version"></a><span data-ttu-id="1319a-111">Comprobar la versión de Windows</span><span class="sxs-lookup"><span data-stu-id="1319a-111">Verify Windows Version</span></span> 

1. <span data-ttu-id="1319a-112">Inicio de sesión a una cuenta de administrador yendo a **Configuración > configuración de Windows > Inicio de sesión de administrador en** desde el dispositivo de los sistemas de salas de Skype v2.</span><span class="sxs-lookup"><span data-stu-id="1319a-112">Login to an admin account by going to **Settings> Windows Setting> Admin Sign In** from the Skype Room Systems v2 device.</span></span> <span data-ttu-id="1319a-113">Esta opción le lleva a la pantalla de inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="1319a-113">This option brings you to the login screen.</span></span>
2. <span data-ttu-id="1319a-114">Inicie una sesión en una cuenta de administrador, el administrador predeterminado cuenta siendo `admin` con la contraseña `sfb`.</span><span class="sxs-lookup"><span data-stu-id="1319a-114">Sign into an admin account, the default admin account being `admin` with the password `sfb`.</span></span>
3. <span data-ttu-id="1319a-115">Haga clic en el menú Inicio y escriba `winver.exe` en el cuadro Buscar y haga clic en \**Comando ejecutar* en el resultado.</span><span class="sxs-lookup"><span data-stu-id="1319a-115">Click on the start menu and type `winver.exe` into the search box and click \**Run Command* on the result.</span></span>
4. <span data-ttu-id="1319a-116">Tome nota del número después de 'Versión' en la segunda línea del panel de información.</span><span class="sxs-lookup"><span data-stu-id="1319a-116">Make note of the number after 'Version' on the second line of the info pane.</span></span>

>[!NOTE]
><span data-ttu-id="1319a-117">Si la versión que se muestra es 1607 o anterior, siga los pasos en los pasos de <a href="#Windows-up">Windows Update antes de recuperación</a> antes de proceder con los pasos de <a href="#Perform">realizar una recuperación</a> .</span><span class="sxs-lookup"><span data-stu-id="1319a-117">If the Version shown is 1607 or earlier, follow the steps in the <a href="#Windows-up">Update Windows before recovery</a> steps before proceding to the <a href="#Perform">Perform a recovery</a> steps.</span></span> <span data-ttu-id="1319a-118">Si la versión que se muestra es mayor que 1607, siga sólo los pasos de <a href="#Perform">realizar una recuperación</a>.</span><span class="sxs-lookup"><span data-stu-id="1319a-118">If the Version shown is greater than 1607, follow only the steps in <a href="#Perform">Perform a recovery</a>.</span></span>

<span data-ttu-id="1319a-119"><a name="Windows-up"> </a></span><span class="sxs-lookup"><span data-stu-id="1319a-119"></span></span>
## <a name="update-windows-before-recovery-if-needed"></a><span data-ttu-id="1319a-120">Actualizar Windows antes de la recuperación (si es necesario)</span><span class="sxs-lookup"><span data-stu-id="1319a-120">Update Windows before recovery (if needed)</span></span>

1. <span data-ttu-id="1319a-121">Aún iniciar sesión como un usuario administrador, inicie un símbolo del sistema con privilegios elevados de Powershell.</span><span class="sxs-lookup"><span data-stu-id="1319a-121">While still logged in as an admin user, launch an elevated Powershell prompt.</span></span>
2. <span data-ttu-id="1319a-122">Ejecute el comando `Remove-Item -Path 'c:\Recovery\OEM\$oem$\$1\Rigel' -Force -Recurse`.</span><span class="sxs-lookup"><span data-stu-id="1319a-122">Run the command `Remove-Item -Path 'c:\Recovery\OEM\$oem$\$1\Rigel' -Force -Recurse`.</span></span>
3. <span data-ttu-id="1319a-123">Ejecute Windows Update e instale la actualización para Windows 1709.</span><span class="sxs-lookup"><span data-stu-id="1319a-123">Run Windows Update and install the update for Windows 1709.</span></span>
4. <span data-ttu-id="1319a-124">Después de la actualización a 1709 signo completa de nuevo en la cuenta de administrador e instale [KB4089848](http://download.windowsupdate.com/d/msdownload/update/software/updt/2018/03/windows10.0-kb4089848-x64_db7c5aad31c520c6983a937c3d53170e84372b11.msu).</span><span class="sxs-lookup"><span data-stu-id="1319a-124">After the update to 1709 is complete sign back into admin account and install [KB4089848](http://download.windowsupdate.com/d/msdownload/update/software/updt/2018/03/windows10.0-kb4089848-x64_db7c5aad31c520c6983a937c3d53170e84372b11.msu).</span></span> <span data-ttu-id="1319a-125">Se puede realizar la actualización desde el vínculo o mediante Windows Update.</span><span class="sxs-lookup"><span data-stu-id="1319a-125">The update may be done from the link or using Windows Update.</span></span>
5. <span data-ttu-id="1319a-126">De forma opcional, instalar cualquier actualización adicional disponible desde Windows Update.</span><span class="sxs-lookup"><span data-stu-id="1319a-126">As an optional step, install any additional updates available from Windows Update.</span></span>

<span data-ttu-id="1319a-127"><a name="Perform"> </a></span><span class="sxs-lookup"><span data-stu-id="1319a-127"></span></span>
## <a name="perform-a-recovery"></a><span data-ttu-id="1319a-128">Realizar una recuperación</span><span class="sxs-lookup"><span data-stu-id="1319a-128">Perform a recovery</span></span>

1. <span data-ttu-id="1319a-129">Iniciar sesión en la cuenta de administrador en el dispositivo de los sistemas de salas de Skype v2 y, inicie un símbolo del sistema con privilegios elevados.</span><span class="sxs-lookup"><span data-stu-id="1319a-129">Sign in to the admin account on your Skype Room Systems v2 device, and launch an elevated command prompt.</span></span>
2. <span data-ttu-id="1319a-130">Compruebe desde el dispositivo v2 de sistemas de salas de Skype que es capaz de acceder a la `RecoveryTool.ps1` archivo, que se incluye en los archivos extraídos desde el paquete de instalación de sistemas de salas de Skype v2.</span><span class="sxs-lookup"><span data-stu-id="1319a-130">Verify from the Skype Room Systems v2 device that you are able to access the `RecoveryTool.ps1` file, which is included in the files extracted from the Skype Room Systems v2 installation package.</span></span> <span data-ttu-id="1319a-131">El kit se puede encontrar en el recurso compartido de red o una unidad USB utilizado al preparar los requisitos previos.</span><span class="sxs-lookup"><span data-stu-id="1319a-131">The kit can be found on the network share or USB drive used when preparing prerequisites.</span></span>
3. <span data-ttu-id="1319a-132">Ejecute el comando Powershell.exe `-ExecutionPolicy Unrestricted -File "<path to RecoveryTool.ps1>"`.</span><span class="sxs-lookup"><span data-stu-id="1319a-132">Run the Powershell.exe command `-ExecutionPolicy Unrestricted -File "<path to RecoveryTool.ps1>"`.</span></span>
4. <span data-ttu-id="1319a-133">Cuando se lo pida la opción Seleccionar secuencia de comandos `1:"Repair System"`.</span><span class="sxs-lookup"><span data-stu-id="1319a-133">When prompted by the script select option `1:"Repair System"`.</span></span>
5. <span data-ttu-id="1319a-134">Al finalizar, reinicie el dispositivo v2 de sistemas de salas de Skype.</span><span class="sxs-lookup"><span data-stu-id="1319a-134">Upon completion, reboot the Skype Room Systems v2 device.</span></span> <span data-ttu-id="1319a-135">Se reiniciará automáticamente otra vez y elaborar totalmente recuperado la segunda vez.</span><span class="sxs-lookup"><span data-stu-id="1319a-135">It will reboot again automatically and come up fully recovered the second time.</span></span>



<span data-ttu-id="1319a-136"><a name="See"> </a></span><span class="sxs-lookup"><span data-stu-id="1319a-136"></span></span>  
## <a name="see-also"></a><span data-ttu-id="1319a-137">Vea también</span><span class="sxs-lookup"><span data-stu-id="1319a-137">See also</span></span>


#### 

[<span data-ttu-id="1319a-138">Administrar espacio de Skype v2 de sistemas</span><span class="sxs-lookup"><span data-stu-id="1319a-138">Manage Skype Room Systems v2</span></span>](skype-room-systems-v2.md)
#### 
