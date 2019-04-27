---
title: Usar la herramienta de recuperación de Sala de Microsoft Teams
ms.author: jambirk
author: jambirk
manager: serdars
ms.reviewer: davgroom
ms.date: 4/17/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
ms.collection: M365-voice
localization_priority: Normal
description: En este artículo se describe cómo usar la herramienta de recuperación para salas de equipos de Microsoft, que se pueden utilizar para incorporar un sistema caducado en un estado admitido.
ms.openlocfilehash: 9580a94c96b7982a3030ccc0435be8e05f7c4a25
ms.sourcegitcommit: 79ec789a22acf1686c33a5cc8ba3bd50049f94b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/26/2019
ms.locfileid: "33363010"
---
# <a name="use-the-microsoft-teams-rooms-recovery-tool"></a><span data-ttu-id="4ab9e-103">Usar la herramienta de recuperación de Sala de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="4ab9e-103">Use the Microsoft Teams Rooms recovery tool</span></span>
 
<span data-ttu-id="4ab9e-104">En este artículo se describe cómo usar la herramienta de recuperación para salas de equipos de Microsoft, que se pueden utilizar para incorporar un sistema caducado en un estado admitido.</span><span class="sxs-lookup"><span data-stu-id="4ab9e-104">This article discusses how to use the recovery tool for Microsoft Teams Rooms, which you would use to bring an out of date system into a supported state.</span></span> <span data-ttu-id="4ab9e-105">¿Utilizar esta herramienta cuando la consola de salas de equipos de Microsoft muestra un error "sistema config caducada".</span><span class="sxs-lookup"><span data-stu-id="4ab9e-105">You would use this tool when the Microsoft Teams Rooms console shows a "system config out of date" error.</span></span>
  

<span data-ttu-id="4ab9e-106"><a name="Prerequisites"> </a></span><span class="sxs-lookup"><span data-stu-id="4ab9e-106"></span></span>  
## <a name="prerequisites"></a><span data-ttu-id="4ab9e-107">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="4ab9e-107">Prerequisites</span></span>

<span data-ttu-id="4ab9e-108">Descargue el último [paquete de instalación de salas de equipos de Microsoft](https://go.microsoft.com/fwlink/?linkid=851168) y extraer a un USB memoria pincel recurso compartido de red accesible para el dispositivo de salas de equipos de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="4ab9e-108">Download the latest [Microsoft Teams Rooms installation package](https://go.microsoft.com/fwlink/?linkid=851168) and extract it to a USB memory stick or network share accessible to the Microsoft Teams Rooms device.</span></span>

<span data-ttu-id="4ab9e-109">También es posible que necesite instalar [KB4089848](http://download.windowsupdate.com/d/msdownload/update/software/updt/2018/03/windows10.0-kb4089848-x64_db7c5aad31c520c6983a937c3d53170e84372b11.msu).</span><span class="sxs-lookup"><span data-stu-id="4ab9e-109">You may also need to install [KB4089848](http://download.windowsupdate.com/d/msdownload/update/software/updt/2018/03/windows10.0-kb4089848-x64_db7c5aad31c520c6983a937c3d53170e84372b11.msu).</span></span>

<span data-ttu-id="4ab9e-110"><a name="Windows-ver"> </a></span><span class="sxs-lookup"><span data-stu-id="4ab9e-110"></span></span>
## <a name="verify-windows-version"></a><span data-ttu-id="4ab9e-111">Comprobar la versión de Windows</span><span class="sxs-lookup"><span data-stu-id="4ab9e-111">Verify Windows Version</span></span> 

1. <span data-ttu-id="4ab9e-112">Inicio de sesión a una cuenta de administración, vaya a **Settings> Setting> Administrador de inicio de sesión de Windows** desde el dispositivo de salas de equipos de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="4ab9e-112">Login to an admin account by going to **Settings> Windows Setting> Admin Sign In** from the Microsoft Teams Rooms device.</span></span> <span data-ttu-id="4ab9e-113">Esta opción le lleva a la pantalla de inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="4ab9e-113">This option brings you to the login screen.</span></span>
2. <span data-ttu-id="4ab9e-114">Cuenta de inicio de sesión a una cuenta de administrador, el administrador predeterminado bienestar `admin` con la contraseña `sfb`.</span><span class="sxs-lookup"><span data-stu-id="4ab9e-114">Sign into an admin account, the default admin account being `admin` with the password `sfb`.</span></span>
3. <span data-ttu-id="4ab9e-115">Haga clic en el menú Inicio y el tipo `winver.exe` en el cuadro de búsqueda y haga clic en \**Run Command* en el resultado.</span><span class="sxs-lookup"><span data-stu-id="4ab9e-115">Click on the start menu and type `winver.exe` into the search box and click \**Run Command* on the result.</span></span>
4. <span data-ttu-id="4ab9e-116">Tome nota del número después de 'Versión' en la segunda línea del panel de información.</span><span class="sxs-lookup"><span data-stu-id="4ab9e-116">Make note of the number after 'Version' on the second line of the info pane.</span></span>

>[!NOTE]
><span data-ttu-id="4ab9e-117">Si la versión que se muestra es 1607 o anterior, siga los pasos descritos en los pasos de <a href="#Windows-up">Actualización de Windows antes de recuperación</a> antes de comenzar a los pasos de <a href="#Perform">realizar una recuperación</a> .</span><span class="sxs-lookup"><span data-stu-id="4ab9e-117">If the Version shown is 1607 or earlier, follow the steps in the <a href="#Windows-up">Update Windows before recovery</a> steps before proceding to the <a href="#Perform">Perform a recovery</a> steps.</span></span> <span data-ttu-id="4ab9e-118">Si la versión que se muestra es mayor que 1607, siga sólo los pasos de <a href="#Perform">realizar una recuperación</a>.</span><span class="sxs-lookup"><span data-stu-id="4ab9e-118">If the Version shown is greater than 1607, follow only the steps in <a href="#Perform">Perform a recovery</a>.</span></span>

<span data-ttu-id="4ab9e-119"><a name="Windows-up"> </a></span><span class="sxs-lookup"><span data-stu-id="4ab9e-119"></span></span>
## <a name="update-windows-before-recovery-if-needed"></a><span data-ttu-id="4ab9e-120">Actualizar Windows antes de la recuperación (si es necesario)</span><span class="sxs-lookup"><span data-stu-id="4ab9e-120">Update Windows before recovery (if needed)</span></span>

1. <span data-ttu-id="4ab9e-121">Mientras sigue iniciado sesión como un usuario con permisos de administrador, inicie un símbolo del sistema con privilegios elevados de Powershell.</span><span class="sxs-lookup"><span data-stu-id="4ab9e-121">While still logged in as an admin user, launch an elevated Powershell prompt.</span></span>
2. <span data-ttu-id="4ab9e-122">Ejecute el comando `Remove-Item -Path 'c:\Recovery\OEM\$oem$\$1\Rigel' -Force -Recurse`.</span><span class="sxs-lookup"><span data-stu-id="4ab9e-122">Run the command `Remove-Item -Path 'c:\Recovery\OEM\$oem$\$1\Rigel' -Force -Recurse`.</span></span>
3. <span data-ttu-id="4ab9e-123">Ejecute Windows Update e instale la actualización de Windows 1709.</span><span class="sxs-lookup"><span data-stu-id="4ab9e-123">Run Windows Update and install the update for Windows 1709.</span></span>
4. <span data-ttu-id="4ab9e-124">Después de la actualización a 1709 inicio de sesión completo de nuevo en la cuenta de administrador e instale [KB4089848](http://download.windowsupdate.com/d/msdownload/update/software/updt/2018/03/windows10.0-kb4089848-x64_db7c5aad31c520c6983a937c3d53170e84372b11.msu).</span><span class="sxs-lookup"><span data-stu-id="4ab9e-124">After the update to 1709 is complete sign back into admin account and install [KB4089848](http://download.windowsupdate.com/d/msdownload/update/software/updt/2018/03/windows10.0-kb4089848-x64_db7c5aad31c520c6983a937c3d53170e84372b11.msu).</span></span> <span data-ttu-id="4ab9e-125">Se puede realizar la actualización desde el vínculo o mediante Windows Update.</span><span class="sxs-lookup"><span data-stu-id="4ab9e-125">The update may be done from the link or using Windows Update.</span></span>
5. <span data-ttu-id="4ab9e-126">Como un paso opcional, instale las actualizaciones adicionales disponibles desde Windows Update.</span><span class="sxs-lookup"><span data-stu-id="4ab9e-126">As an optional step, install any additional updates available from Windows Update.</span></span>

<span data-ttu-id="4ab9e-127"><a name="Perform"> </a></span><span class="sxs-lookup"><span data-stu-id="4ab9e-127"></span></span>
## <a name="perform-a-recovery"></a><span data-ttu-id="4ab9e-128">Realizar una recuperación</span><span class="sxs-lookup"><span data-stu-id="4ab9e-128">Perform a recovery</span></span>

1. <span data-ttu-id="4ab9e-129">Inicie sesión en la cuenta de administrador en el dispositivo de salas de equipos de Microsoft y, inicie un símbolo del sistema con privilegios elevados.</span><span class="sxs-lookup"><span data-stu-id="4ab9e-129">Sign in to the admin account on your Microsoft Teams Rooms device, and launch an elevated command prompt.</span></span>
2. <span data-ttu-id="4ab9e-130">Compruebe desde el dispositivo de salas de equipos de Microsoft que pueden tener acceso a la `RecoveryTool.ps1` archivo, que se incluye en los archivos extraídos desde el paquete de instalación de salas de equipos de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="4ab9e-130">Verify from the Microsoft Teams Rooms device that you are able to access the `RecoveryTool.ps1` file, which is included in the files extracted from the Microsoft Teams Rooms installation package.</span></span> <span data-ttu-id="4ab9e-131">El kit de puede encontrarse en el recurso compartido de red o una unidad USB utilizado al preparar los requisitos previos.</span><span class="sxs-lookup"><span data-stu-id="4ab9e-131">The kit can be found on the network share or USB drive used when preparing prerequisites.</span></span>
3. <span data-ttu-id="4ab9e-132">Ejecute el comando Powershell.exe `-ExecutionPolicy Unrestricted -File "<path to RecoveryTool.ps1>"`.</span><span class="sxs-lookup"><span data-stu-id="4ab9e-132">Run the Powershell.exe command `-ExecutionPolicy Unrestricted -File "<path to RecoveryTool.ps1>"`.</span></span>
4. <span data-ttu-id="4ab9e-133">Cuando se le solicite mediante la opción Seleccionar de secuencia de comandos `1:"Repair System"`.</span><span class="sxs-lookup"><span data-stu-id="4ab9e-133">When prompted by the script select option `1:"Repair System"`.</span></span>
5. <span data-ttu-id="4ab9e-134">Al finalizar, reinicie el dispositivo de salas de equipos de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="4ab9e-134">Upon completion, reboot the Microsoft Teams Rooms device.</span></span> <span data-ttu-id="4ab9e-135">Se reiniciará automáticamente nuevo y surgen recuperado totalmente la segunda vez.</span><span class="sxs-lookup"><span data-stu-id="4ab9e-135">It will reboot again automatically and come up fully recovered the second time.</span></span>



<span data-ttu-id="4ab9e-136"><a name="See"> </a></span><span class="sxs-lookup"><span data-stu-id="4ab9e-136"></span></span>  
## <a name="see-also"></a><span data-ttu-id="4ab9e-137">Vea también</span><span class="sxs-lookup"><span data-stu-id="4ab9e-137">See also</span></span>
 
[<span data-ttu-id="4ab9e-138">Ayuda de Salas de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="4ab9e-138">Microsoft Teams Rooms help</span></span>](https://support.office.com/en-us/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[<span data-ttu-id="4ab9e-139">Administrar Salas de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="4ab9e-139">Manage Microsoft Teams Rooms</span></span>](skype-room-systems-v2.md)