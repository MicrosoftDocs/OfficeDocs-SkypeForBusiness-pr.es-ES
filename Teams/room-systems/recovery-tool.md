---
title: Usar la herramienta de recuperación de Sala de Microsoft Teams
ms.author: v-lanac
author: lanachin
manager: serdars
ms.reviewer: sohailta
ms.date: 4/17/2018
audience: ITPro
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
localization_priority: Normal
description: En este artículo se describe cómo usar la herramienta de recuperación para salas de Microsoft Teams, que se usaría para poner un sistema obsoleto en un estado compatible.
ms.openlocfilehash: 04fd6b4b0786cffb4f1bb050a7b0bbdac8e2e653
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2019
ms.locfileid: "37573654"
---
# <a name="use-the-microsoft-teams-rooms-recovery-tool"></a><span data-ttu-id="a8e6c-103">Usar la herramienta de recuperación de Sala de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="a8e6c-103">Use the Microsoft Teams Rooms recovery tool</span></span>
 
<span data-ttu-id="a8e6c-104">En este artículo se describe cómo usar la herramienta de recuperación para salas de Microsoft Teams, que se usaría para poner un sistema obsoleto en un estado compatible.</span><span class="sxs-lookup"><span data-stu-id="a8e6c-104">This article discusses how to use the recovery tool for Microsoft Teams Rooms, which you would use to bring an out of date system into a supported state.</span></span> <span data-ttu-id="a8e6c-105">Usaría esta herramienta cuando la consola de Microsoft Teams Rooms muestre el error "configuración de sistema no actualizado".</span><span class="sxs-lookup"><span data-stu-id="a8e6c-105">You would use this tool when the Microsoft Teams Rooms console shows a "system config out of date" error.</span></span>
  

<span data-ttu-id="a8e6c-106"><a name="Prerequisites"> </a></span><span class="sxs-lookup"><span data-stu-id="a8e6c-106"></span></span>  
## <a name="prerequisites"></a><span data-ttu-id="a8e6c-107">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="a8e6c-107">Prerequisites</span></span>

<span data-ttu-id="a8e6c-108">Descargue el [paquete de instalación de Microsoft Team Rooms](https://go.microsoft.com/fwlink/?linkid=851168) más reciente y extráigalo en un Memory stick USB o en un recurso compartido de red accesible para el dispositivo de salas de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="a8e6c-108">Download the latest [Microsoft Teams Rooms installation package](https://go.microsoft.com/fwlink/?linkid=851168) and extract it to a USB memory stick or network share accessible to the Microsoft Teams Rooms device.</span></span>

<span data-ttu-id="a8e6c-109">Es posible que también tenga que instalar [KB4089848](http://download.windowsupdate.com/d/msdownload/update/software/updt/2018/03/windows10.0-kb4089848-x64_db7c5aad31c520c6983a937c3d53170e84372b11.msu).</span><span class="sxs-lookup"><span data-stu-id="a8e6c-109">You may also need to install [KB4089848](http://download.windowsupdate.com/d/msdownload/update/software/updt/2018/03/windows10.0-kb4089848-x64_db7c5aad31c520c6983a937c3d53170e84372b11.msu).</span></span>

<span data-ttu-id="a8e6c-110"><a name="Windows-ver"> </a></span><span class="sxs-lookup"><span data-stu-id="a8e6c-110"></span></span>
## <a name="verify-windows-version"></a><span data-ttu-id="a8e6c-111">Comprobar la versión de Windows</span><span class="sxs-lookup"><span data-stu-id="a8e6c-111">Verify Windows Version</span></span> 

1. <span data-ttu-id="a8e6c-112">Inicie sesión en una cuenta de administrador yendo a **configuración> configuración de Windows> iniciar sesión en** el dispositivo de salas de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="a8e6c-112">Login to an admin account by going to **Settings> Windows Setting> Admin Sign In** from the Microsoft Teams Rooms device.</span></span> <span data-ttu-id="a8e6c-113">Esta opción te lleva a la pantalla de inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="a8e6c-113">This option brings you to the login screen.</span></span>
2. <span data-ttu-id="a8e6c-114">Inicie sesión en una cuenta de administrador, la cuenta de `admin` administrador predeterminada con `sfb`la contraseña.</span><span class="sxs-lookup"><span data-stu-id="a8e6c-114">Sign into an admin account, the default admin account being `admin` with the password `sfb`.</span></span>
3. <span data-ttu-id="a8e6c-115">Haga clic en el menú Inicio y `winver.exe` escriba en el cuadro de búsqueda y haga clic en el*comando \* ejecutar* en el resultado.</span><span class="sxs-lookup"><span data-stu-id="a8e6c-115">Click on the start menu and type `winver.exe` into the search box and click \**Run Command* on the result.</span></span>
4. <span data-ttu-id="a8e6c-116">Anote el número que hay después de ' versión ' en la segunda línea del panel de información.</span><span class="sxs-lookup"><span data-stu-id="a8e6c-116">Make note of the number after 'Version' on the second line of the info pane.</span></span>

>[!NOTE]
><span data-ttu-id="a8e6c-117">Si la versión mostrada es 1607 o anterior, siga los pasos que se indican en los pasos de <a href="#Windows-up">actualización de Windows antes</a> de la recuperación antes de <a href="#Perform">llevar a cabo una recuperación</a> .</span><span class="sxs-lookup"><span data-stu-id="a8e6c-117">If the Version shown is 1607 or earlier, follow the steps in the <a href="#Windows-up">Update Windows before recovery</a> steps before proceding to the <a href="#Perform">Perform a recovery</a> steps.</span></span> <span data-ttu-id="a8e6c-118">Si la versión mostrada es mayor que 1607, siga los pasos que se indican en <a href="#Perform">realizar una recuperación</a>.</span><span class="sxs-lookup"><span data-stu-id="a8e6c-118">If the Version shown is greater than 1607, follow only the steps in <a href="#Perform">Perform a recovery</a>.</span></span>

<span data-ttu-id="a8e6c-119"><a name="Windows-up"> </a></span><span class="sxs-lookup"><span data-stu-id="a8e6c-119"></span></span>
## <a name="update-windows-before-recovery-if-needed"></a><span data-ttu-id="a8e6c-120">Actualizar Windows antes de la recuperación (si es necesario)</span><span class="sxs-lookup"><span data-stu-id="a8e6c-120">Update Windows before recovery (if needed)</span></span>

1. <span data-ttu-id="a8e6c-121">Mientras está conectado como usuario administrador, inicie un símbolo del sistema de PowerShell con privilegios elevados.</span><span class="sxs-lookup"><span data-stu-id="a8e6c-121">While still logged in as an admin user, launch an elevated Powershell prompt.</span></span>
2. <span data-ttu-id="a8e6c-122">Ejecute el comando `Remove-Item -Path 'c:\Recovery\OEM\$oem$\$1\Rigel' -Force -Recurse`.</span><span class="sxs-lookup"><span data-stu-id="a8e6c-122">Run the command `Remove-Item -Path 'c:\Recovery\OEM\$oem$\$1\Rigel' -Force -Recurse`.</span></span>
3. <span data-ttu-id="a8e6c-123">Ejecute Windows Update e instale la actualización de Windows 1709.</span><span class="sxs-lookup"><span data-stu-id="a8e6c-123">Run Windows Update and install the update for Windows 1709.</span></span>
4. <span data-ttu-id="a8e6c-124">Una vez completada la actualización a 1709, vuelva a iniciar sesión en la cuenta de administrador e instale [KB4089848](http://download.windowsupdate.com/d/msdownload/update/software/updt/2018/03/windows10.0-kb4089848-x64_db7c5aad31c520c6983a937c3d53170e84372b11.msu).</span><span class="sxs-lookup"><span data-stu-id="a8e6c-124">After the update to 1709 is complete sign back into admin account and install [KB4089848](http://download.windowsupdate.com/d/msdownload/update/software/updt/2018/03/windows10.0-kb4089848-x64_db7c5aad31c520c6983a937c3d53170e84372b11.msu).</span></span> <span data-ttu-id="a8e6c-125">La actualización puede realizarse desde el vínculo o mediante Windows Update.</span><span class="sxs-lookup"><span data-stu-id="a8e6c-125">The update may be done from the link or using Windows Update.</span></span>
5. <span data-ttu-id="a8e6c-126">Como paso opcional, instale las actualizaciones adicionales disponibles en Windows Update.</span><span class="sxs-lookup"><span data-stu-id="a8e6c-126">As an optional step, install any additional updates available from Windows Update.</span></span>

<span data-ttu-id="a8e6c-127"><a name="Perform"> </a></span><span class="sxs-lookup"><span data-stu-id="a8e6c-127"></span></span>
## <a name="perform-a-recovery"></a><span data-ttu-id="a8e6c-128">Realizar una recuperación</span><span class="sxs-lookup"><span data-stu-id="a8e6c-128">Perform a recovery</span></span>

1. <span data-ttu-id="a8e6c-129">Inicie sesión en la cuenta de administrador en el dispositivo de salas de Microsoft Teams e inicie un símbolo del sistema con privilegios elevados.</span><span class="sxs-lookup"><span data-stu-id="a8e6c-129">Sign in to the admin account on your Microsoft Teams Rooms device, and launch an elevated command prompt.</span></span>
2. <span data-ttu-id="a8e6c-130">Compruebe en el dispositivo salas de Microsoft teams que tiene acceso al `RecoveryTool.ps1` archivo, que está incluido en los archivos extraídos del paquete de instalación salas de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="a8e6c-130">Verify from the Microsoft Teams Rooms device that you are able to access the `RecoveryTool.ps1` file, which is included in the files extracted from the Microsoft Teams Rooms installation package.</span></span> <span data-ttu-id="a8e6c-131">El kit puede encontrarse en el recurso compartido de red o en la unidad USB que se usa al preparar los requisitos previos.</span><span class="sxs-lookup"><span data-stu-id="a8e6c-131">The kit can be found on the network share or USB drive used when preparing prerequisites.</span></span>
3. <span data-ttu-id="a8e6c-132">Ejecute el comando `-ExecutionPolicy Unrestricted -File "<path to RecoveryTool.ps1>"`PowerShell. exe.</span><span class="sxs-lookup"><span data-stu-id="a8e6c-132">Run the Powershell.exe command `-ExecutionPolicy Unrestricted -File "<path to RecoveryTool.ps1>"`.</span></span>
4. <span data-ttu-id="a8e6c-133">Cuando se le solicite mediante la opción de `1:"Repair System"`la secuencia de comandos, seleccione.</span><span class="sxs-lookup"><span data-stu-id="a8e6c-133">When prompted by the script select option `1:"Repair System"`.</span></span>
5. <span data-ttu-id="a8e6c-134">Al finalizar, reinicie el dispositivo de salas de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="a8e6c-134">Upon completion, reboot the Microsoft Teams Rooms device.</span></span> <span data-ttu-id="a8e6c-135">Se reiniciará de nuevo automáticamente y se recargará por completo la segunda vez.</span><span class="sxs-lookup"><span data-stu-id="a8e6c-135">It will reboot again automatically and come up fully recovered the second time.</span></span>



<span data-ttu-id="a8e6c-136"><a name="See"> </a></span><span class="sxs-lookup"><span data-stu-id="a8e6c-136"></span></span>  
## <a name="see-also"></a><span data-ttu-id="a8e6c-137">Vea también</span><span class="sxs-lookup"><span data-stu-id="a8e6c-137">See also</span></span>
 
[<span data-ttu-id="a8e6c-138">Ayuda de Salas de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="a8e6c-138">Microsoft Teams Rooms help</span></span>](https://support.office.com/en-us/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[<span data-ttu-id="a8e6c-139">Administrar Salas de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="a8e6c-139">Manage Microsoft Teams Rooms</span></span>](skype-room-systems-v2.md)
