---
title: Obtener clientes para Microsoft Teams
author: SerdarSoysal
ms.author: serdars
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
- m365initiative-deployteams
ms.reviewer: harij, rafarhi
localization_priority: Normal
search.appverid: MET150
description: Aprenda a usar los distintos clientes disponibles para Microsoft Teams, que incluyen web, escritorio (Windows y Mac) y móvil (iOS y Android).
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2cb28295b0a9700a0eb7531111022a9498517d93
ms.sourcegitcommit: 4386f4b89331112e0d54943dc3133791d5dca3fb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/09/2020
ms.locfileid: "49611594"
---
# <a name="get-clients-for-microsoft-teams"></a><span data-ttu-id="20aaf-103">Obtener clientes para Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="20aaf-103">Get clients for Microsoft Teams</span></span> 

<span data-ttu-id="20aaf-p101">Microsoft Teams tiene clientes disponibles para web, escritorio (Windows, Mac y Linux) y móvil (iOS y Android). Todos estos clientes requieren una conexión a Internet activa y no admiten el modo sin conexión.</span><span class="sxs-lookup"><span data-stu-id="20aaf-p101">Microsoft Teams has clients available for desktop (Windows, Mac, and Linux), web, and mobile (Android and iOS). These clients all require an active internet connection and do not support an offline mode.</span></span> 

> [!Note]
> <span data-ttu-id="20aaf-106">Para obtener más información sobre las capacidades de cada cliente en distintas plataformas, consulte [Características de Teams por plataforma.](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3)</span><span class="sxs-lookup"><span data-stu-id="20aaf-106">For details about each clients' capabilities on different platforms, see [Teams features by platform](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3).</span></span>

> [!NOTE]
> <span data-ttu-id="20aaf-107">A partir del 29 de noviembre de 2018, ya no podrá usar la aplicación de Microsoft Teams para Windows 10 S (versión preliminar), disponible en Microsoft Store.</span><span class="sxs-lookup"><span data-stu-id="20aaf-107">Effective November 29, 2018, you'll no longer be able to use the Microsoft Teams for Windows 10 S (Preview) app, available from the Microsoft Store.</span></span> <span data-ttu-id="20aaf-108">En su lugar, ahora puede descargar e instalar el cliente de escritorio de Teams en los dispositivos que ejecutan Windows 10 en modo S.</span><span class="sxs-lookup"><span data-stu-id="20aaf-108">Instead, you can now download and install the Teams desktop client on devices running Windows 10 S mode.</span></span> <span data-ttu-id="20aaf-109">Para descargar el cliente de escritorio, vaya a [https://teams.microsoft.com/downloads](https://go.microsoft.com/fwlink/?linkid=855754).</span><span class="sxs-lookup"><span data-stu-id="20aaf-109">To download the desktop client, go to [https://teams.microsoft.com/downloads](https://go.microsoft.com/fwlink/?linkid=855754).</span></span> <span data-ttu-id="20aaf-110">Las compilaciones de MSI del cliente de escritorio de Teams aún no están disponibles para los dispositivos que ejecutan Windows 10 en modo S.</span><span class="sxs-lookup"><span data-stu-id="20aaf-110">MSI builds of the Teams desktop client are not yet available for devices running Windows 10 S mode.</span></span>
>
> <span data-ttu-id="20aaf-111">Para obtener más información sobre Windows 10 en modo S, consulte [Presentamos Windows 10 en modo S](https://www.microsoft.com/windows/s-mode).</span><span class="sxs-lookup"><span data-stu-id="20aaf-111">For more information about Windows 10 S mode, see [Introducing Windows 10 in S mode](https://www.microsoft.com/windows/s-mode).</span></span> 

## <a name="desktop-client"></a><span data-ttu-id="20aaf-112">Cliente de escritorio</span><span class="sxs-lookup"><span data-stu-id="20aaf-112">Desktop client</span></span>

> [!TIP]
> <span data-ttu-id="20aaf-113">Vea la sesión siguiente para conocer las ventajas del cliente de escritorio de Windows, y cómo planearlo e implementarlo: [Cliente de escritorio de Teams para Windows](https://aka.ms/teams-clients)</span><span class="sxs-lookup"><span data-stu-id="20aaf-113">Watch the following session to learn about the benefits of the Windows Desktop Client, how to plan for it, and how to deploy it: [Teams Windows Desktop Client](https://aka.ms/teams-clients)</span></span>

<span data-ttu-id="20aaf-114">El cliente de escritorio de Microsoft Teams es una aplicación independiente y también está disponible en las aplicaciones de [Microsoft 365 para empresas.](https://docs.microsoft.com/deployoffice/teams-install)</span><span class="sxs-lookup"><span data-stu-id="20aaf-114">The Microsoft Teams desktop client is a standalone application and is also [available in Microsoft 365 Apps for enterprise](https://docs.microsoft.com/deployoffice/teams-install).</span></span> <span data-ttu-id="20aaf-115">Teams está disponible para las versiones de 32 y 64 bits de Windows (8.1 o posterior), ARM64 para Windows 10 en ARM y Windows Server (2012 R2 o posterior), así como para macOS y Linux (en `.deb` y formatos). `.rpm`</span><span class="sxs-lookup"><span data-stu-id="20aaf-115">Teams is available for 32-bit and 64-bit versions of Windows (8.1 or later), ARM64 for Windows 10 on ARM, and Windows Server (2012 R2 or later), as well as for macOS and Linux (in `.deb` and `.rpm` formats).</span></span> <span data-ttu-id="20aaf-116">En Windows, Teams requiere .NET Framework 4.5 o posterior; el instalador de Teams le ofrecerá instalarlo si no lo tiene.</span><span class="sxs-lookup"><span data-stu-id="20aaf-116">On Windows, Teams requires .NET Framework 4.5 or later; the Teams installer will offer to install it for you if you don't have it.</span></span> <span data-ttu-id="20aaf-117">En Linux, los administradores de paquetes como `apt` y `yum` intentarán instalar los requisitos por usted.</span><span class="sxs-lookup"><span data-stu-id="20aaf-117">On Linux, package managers such as `apt` and `yum` will try to install any requirements for you.</span></span> <span data-ttu-id="20aaf-118">No obstante, si no lo hacen, deberá instalar todos los requisitos indicados antes de instalar Teams en Linux.</span><span class="sxs-lookup"><span data-stu-id="20aaf-118">However, if they don't then you will need to install any reported requirements before installing Teams on Linux.</span></span>

<span data-ttu-id="20aaf-119">Los clientes de escritorio brindan asistencia en tiempo real para las comunicaciones (audio, vídeo y contenido compartido) para las reuniones de equipo, las llamadas grupales y las llamadas de uno a uno.</span><span class="sxs-lookup"><span data-stu-id="20aaf-119">The desktop clients provide real-time communications support (audio, video, and content sharing) for team meetings, group calling, and private one-on-one calls.</span></span>

<span data-ttu-id="20aaf-120">Los usuarios pueden descargar e instalar los clientes de escritorio directamente desde [https://teams.microsoft.com/downloads](https://go.microsoft.com/fwlink/?linkid=855754) si tienen los permisos locales adecuados (no se requieren derechos de administrador para instalar el cliente de Teams en PC, pero sí son necesarios para Mac).</span><span class="sxs-lookup"><span data-stu-id="20aaf-120">Desktop clients can be downloaded and installed by end users directly from [https://teams.microsoft.com/downloads](https://go.microsoft.com/fwlink/?linkid=855754) if they have the appropriate local permissions (admin rights are not required to install the Teams client on a PC but are required on a Mac).</span></span>

> [!NOTE]
> <span data-ttu-id="20aaf-121">Para obtener más información sobre cómo instalar Teams en un Chromebook, consulte Cómo instalar y ejecutar [Microsoft Office en un Chromebook.](https://support.office.com/article/how-to-install-and-run-microsoft-office-on-a-chromebook-32f14a23-2c1a-4579-b973-d4b1d78561ad)</span><span class="sxs-lookup"><span data-stu-id="20aaf-121">For more details about installing Teams on a Chromebook, please see [How to install and run Microsoft Office on a Chromebook](https://support.office.com/article/how-to-install-and-run-microsoft-office-on-a-chromebook-32f14a23-2c1a-4579-b973-d4b1d78561ad).</span></span>

<span data-ttu-id="20aaf-122">Los administradores de TI pueden elegir el método que prefieran para distribuir los archivos de instalación en los equipos de su organización.</span><span class="sxs-lookup"><span data-stu-id="20aaf-122">IT admins can choose their preferred method to distribute the installation files to computers in their organization.</span></span> <span data-ttu-id="20aaf-123">Por ejemplo: Microsoft Endpoint Configuration Manager (Windows) o Jamf Pro (macOS).</span><span class="sxs-lookup"><span data-stu-id="20aaf-123">Some examples include Microsoft Endpoint Configuration Manager (Windows) or Jamf Pro (macOS).</span></span> <span data-ttu-id="20aaf-124">Para obtener el paquete de MSI de distribución de Windows, vea [Instalar Microsoft Teams con MSI](msi-deployment.md).</span><span class="sxs-lookup"><span data-stu-id="20aaf-124">To get the MSI package for Windows distribution, see [Install Microsoft Teams using MSI](msi-deployment.md).</span></span>  

> [!NOTE]
> <span data-ttu-id="20aaf-125">La distribución del cliente a través de estos mecanismos es solo para la instalación inicial de los clientes de Microsoft Teams y no para futuras actualizaciones.</span><span class="sxs-lookup"><span data-stu-id="20aaf-125">Distribution of the client via these mechanisms is only for the initial installation of Microsoft Team clients and not for future updates.</span></span>

### <a name="windows"></a><span data-ttu-id="20aaf-126">Windows</span><span class="sxs-lookup"><span data-stu-id="20aaf-126">Windows</span></span>

<span data-ttu-id="20aaf-127">La instalación de Microsoft Teams para Windows brinda instaladores que se pueden descargar en arquitecturas de 32 y 64 bits.</span><span class="sxs-lookup"><span data-stu-id="20aaf-127">The Microsoft Teams installation for Windows provides downloadable installers in 32-bit and 64-bit architecture.</span></span>

> [!NOTE]
> <span data-ttu-id="20aaf-128">La arquitectura (32 o 64 bits) de Microsoft Teams es independiente de la arquitectura de Windows y Office que esté instalada.</span><span class="sxs-lookup"><span data-stu-id="20aaf-128">The architecture (32-bit vs. 64-bit) of Microsoft Teams is agnostic to the architecture of Windows and Office that is installed.</span></span>

<span data-ttu-id="20aaf-129">El cliente de Windows se implementará en la carpeta AppData ubicada en el perfil del usuario.</span><span class="sxs-lookup"><span data-stu-id="20aaf-129">The Windows client is deployed to the AppData folder located in the user’s profile.</span></span> <span data-ttu-id="20aaf-130">Implementar en el perfil de usuario local permite instalar el cliente sin necesidad de tener permisos elevados.</span><span class="sxs-lookup"><span data-stu-id="20aaf-130">Deploying to the user’s local profile allows the client to be installed without requiring elevated rights.</span></span> <span data-ttu-id="20aaf-131">El cliente de Windows aprovecha las siguientes ubicaciones:</span><span class="sxs-lookup"><span data-stu-id="20aaf-131">The Windows client leverages the following locations:</span></span>

- <span data-ttu-id="20aaf-132">%LocalAppData%\\Microsoft\\Teams</span><span class="sxs-lookup"><span data-stu-id="20aaf-132">%LocalAppData%\\Microsoft\\Teams</span></span>

- <span data-ttu-id="20aaf-133">%LocalAppData%\\Microsoft\\TeamsMeetingAddin</span><span class="sxs-lookup"><span data-stu-id="20aaf-133">%LocalAppData%\\Microsoft\\TeamsMeetingAddin</span></span>

- <span data-ttu-id="20aaf-134">%AppData%\\Microsoft\\Teams</span><span class="sxs-lookup"><span data-stu-id="20aaf-134">%AppData%\\Microsoft\\Teams</span></span>

- <span data-ttu-id="20aaf-135">%LocalAppData%\\SquirrelTemp</span><span class="sxs-lookup"><span data-stu-id="20aaf-135">%LocalAppData%\\SquirrelTemp</span></span>

<span data-ttu-id="20aaf-136">Cuando los usuarios inician una llamada utilizando el cliente de Microsoft Teams, podrían recibir una advertencia con la configuración del firewall de Windows que les pide que permitan la comunicación.</span><span class="sxs-lookup"><span data-stu-id="20aaf-136">When users initiate a call using the Microsoft Teams client for the first time, they might notice a warning with the Windows firewall settings that asks for users to allow communication.</span></span> <span data-ttu-id="20aaf-137">Es posible que se indique a los usuarios que ignoren el mensaje porque la llamada funcionará, incluso si la advertencia se descarta.</span><span class="sxs-lookup"><span data-stu-id="20aaf-137">Users might be instructed to ignore this message because the call will work, even when the warning is dismissed.</span></span>

![Captura de pantalla de un cuadro de diálogo Alerta de seguridad de Windows.](media/Get_clients_for_Microsoft_Teams_image3.png)

> [!NOTE]
> <span data-ttu-id="20aaf-139">La configuración del Firewall de Windows se modificará incluso cuando se descarte el mensaje seleccionando "Cancelar".</span><span class="sxs-lookup"><span data-stu-id="20aaf-139">Windows Firewall configuration will be altered even when the prompt is dismissed by selecting “Cancel”.</span></span> <span data-ttu-id="20aaf-140">Se crearán dos reglas de entrada teams.exe con la acción Permitir para los protocolos TCP y UDP.</span><span class="sxs-lookup"><span data-stu-id="20aaf-140">Two inbound rules for teams.exe will be created with Allow action for both TCP and UDP protocols.</span></span>

<span data-ttu-id="20aaf-141">Si quiere evitar que Teams pida a los usuarios que creen reglas de firewall cuando los usuarios realicen su primera llamada desde Teams, use el script de [PowerShell](#sample-powershell-script---inbound-firewall-rule) de ejemplo: siguiente regla de firewall de entrada.</span><span class="sxs-lookup"><span data-stu-id="20aaf-141">If you want to prevent Teams from prompting users to create firewall rules when the users make their first call from Teams, use the [Sample PowerShell script - inbound firewall rule](#sample-powershell-script---inbound-firewall-rule) below.</span></span> 

### <a name="mac"></a><span data-ttu-id="20aaf-142">Mac</span><span class="sxs-lookup"><span data-stu-id="20aaf-142">Mac</span></span>

<span data-ttu-id="20aaf-143">Los usuarios de Mac pueden instalar Teams mediante el uso de un archivo PKG de instalación para equipos macOS.</span><span class="sxs-lookup"><span data-stu-id="20aaf-143">Mac users can install Teams by using a PKG installation file for macOS computers.</span></span> <span data-ttu-id="20aaf-144">Se requiere acceso administrativo para instalar el cliente de Mac.</span><span class="sxs-lookup"><span data-stu-id="20aaf-144">Administrative access is required to install the Mac client.</span></span> <span data-ttu-id="20aaf-145">El cliente de macOS se instala en la carpeta /Applications.</span><span class="sxs-lookup"><span data-stu-id="20aaf-145">The macOS client is installed to the /Applications folder.</span></span>

#### <a name="install-teams-by-using-the-pkg-file"></a><span data-ttu-id="20aaf-146">Instalar Teams con el archivo PKG </span><span class="sxs-lookup"><span data-stu-id="20aaf-146">Install Teams by using the PKG file</span></span>

1. <span data-ttu-id="20aaf-147">Desde la [página de descarga de Teams](https://teams.microsoft.com/downloads), en **Mac**, haga clic en **Descargar**.</span><span class="sxs-lookup"><span data-stu-id="20aaf-147">From the [Teams download page](https://teams.microsoft.com/downloads), under **Mac**, click **Download**.</span></span>
2. <span data-ttu-id="20aaf-148">Haga doble clic en el archivo PKG.</span><span class="sxs-lookup"><span data-stu-id="20aaf-148">Double click the PKG file.</span></span>
3. <span data-ttu-id="20aaf-149">Siga los pasos del asistente de instalación para completar la instalación.</span><span class="sxs-lookup"><span data-stu-id="20aaf-149">Follow the installation wizard to complete the installation.</span></span>
4. <span data-ttu-id="20aaf-150">Se instalará Teams en la carpeta /Applications.</span><span class="sxs-lookup"><span data-stu-id="20aaf-150">Teams will be installed to /Applications folder.</span></span> <span data-ttu-id="20aaf-151">Es una instalación de todo el equipo.</span><span class="sxs-lookup"><span data-stu-id="20aaf-151">It is a machine-wide installation.</span></span>

> [!NOTE]
> <span data-ttu-id="20aaf-152">Durante la instalación, el PKG solicitará las credenciales de administrador.</span><span class="sxs-lookup"><span data-stu-id="20aaf-152">During the installation, the PKG will prompt for admin credentials.</span></span> <span data-ttu-id="20aaf-153">El usuario debe escribir las credenciales de administrador, independientemente de si el usuario es un administrador.</span><span class="sxs-lookup"><span data-stu-id="20aaf-153">The user needs to enter the admin credentials, regardless of whether or not the user is an admin.</span></span>

<span data-ttu-id="20aaf-154">Si un usuario actualmente tiene una instalación DMG de Teams y quiere reemplazarla con la instalación del PKG, el usuario debe:</span><span class="sxs-lookup"><span data-stu-id="20aaf-154">If a user currently has a DMG installation of Teams and wants to replace it with the PKG installation, the user should:</span></span>

1. <span data-ttu-id="20aaf-155">Salir de la aplicación de Teams.</span><span class="sxs-lookup"><span data-stu-id="20aaf-155">Exit the Teams app.</span></span>
2. <span data-ttu-id="20aaf-156">Desinstalar la aplicación de Teams.</span><span class="sxs-lookup"><span data-stu-id="20aaf-156">Uninstall the Teams app.</span></span>
3. <span data-ttu-id="20aaf-157">Instale el archivo PKG.</span><span class="sxs-lookup"><span data-stu-id="20aaf-157">Install the PKG file.</span></span>

<span data-ttu-id="20aaf-158">Los administradores de TI pueden usar la implementación administrada de Teams para distribuir los archivos de instalación en todos los equipos Mac en su organización, como Jamf Pro.</span><span class="sxs-lookup"><span data-stu-id="20aaf-158">IT admins can use managed deployment of Teams to distribute the installation files to all Macs in their organization, such as Jamf Pro.</span></span>

> [!NOTE]
> <span data-ttu-id="20aaf-159">Si tiene problemas para instalar el PKG, háganoslo saber.</span><span class="sxs-lookup"><span data-stu-id="20aaf-159">If you experience issues installing the PKG, let us know.</span></span> <span data-ttu-id="20aaf-160">En la sección **Comentarios** al final de este artículo, haga clic en **Comentarios sobre el producto**.</span><span class="sxs-lookup"><span data-stu-id="20aaf-160">In the **Feedback** section at the end of this article, click **Product feedback**.</span></span>

### <a name="linux"></a><span data-ttu-id="20aaf-161">Linux</span><span class="sxs-lookup"><span data-stu-id="20aaf-161">Linux</span></span>

<span data-ttu-id="20aaf-162">Los usuarios podrán instalar paquetes de Linux nativos en los formatos `.deb` y `.rpm`.</span><span class="sxs-lookup"><span data-stu-id="20aaf-162">Users will be able to install native Linux packages in `.deb` and `.rpm` formats.</span></span>
<span data-ttu-id="20aaf-163">Al instalar el paquete DEB o RPM, se instalará automáticamente el repositorio de paquetes.</span><span class="sxs-lookup"><span data-stu-id="20aaf-163">Installing the DEB or RPM package will automatically install the package repository.</span></span>
- <span data-ttu-id="20aaf-164">DEB `https://packages.microsoft.com/repos/ms-teams stable main`</span><span class="sxs-lookup"><span data-stu-id="20aaf-164">DEB `https://packages.microsoft.com/repos/ms-teams stable main`</span></span>
- <span data-ttu-id="20aaf-165">RPM `https://packages.microsoft.com/yumrepos/ms-teams`</span><span class="sxs-lookup"><span data-stu-id="20aaf-165">RPM `https://packages.microsoft.com/yumrepos/ms-teams`</span></span> 

<span data-ttu-id="20aaf-166">La clave de firma para habilitar la actualización automática mediante el administrador de paquetes del sistema se instala automáticamente.</span><span class="sxs-lookup"><span data-stu-id="20aaf-166">The signing key to enable auto-updating using the system's package manager is installed automatically.</span></span> <span data-ttu-id="20aaf-167">No obstante, también se puede encontrar en: (https://packages.microsoft.com/keys/microsoft.asc).</span><span class="sxs-lookup"><span data-stu-id="20aaf-167">However, it can also be found at: (https://packages.microsoft.com/keys/microsoft.asc).</span></span> <span data-ttu-id="20aaf-168">Microsoft Teams se suministra mensualmente y, si el repositorio se ha instalado correctamente, el administrador de paquetes del sistema debería controlar la actualización automática de la misma manera que otros paquetes del sistema.</span><span class="sxs-lookup"><span data-stu-id="20aaf-168">Microsoft Teams ships monthly and if the repository was installed correctly, then your system package manager should handle auto-updating in the same way as other packages on the system.</span></span>

> [!NOTE] 
> <span data-ttu-id="20aaf-169">Si encuentra un error, envíelo mediante `Report a Problem` desde el cliente.</span><span class="sxs-lookup"><span data-stu-id="20aaf-169">If you find a bug, submit it using `Report a Problem` from within the client.</span></span> <span data-ttu-id="20aaf-170">Para ver problemas conocidos, consulte [Equipos de soporte técnico de su organización.](Known-issues.md)</span><span class="sxs-lookup"><span data-stu-id="20aaf-170">For known issues, see [Support Teams in your organization](Known-issues.md).</span></span>
> <span data-ttu-id="20aaf-171">Para obtener soporte técnico de Teams para Linux, puede usar el [canal de soporte del foro de Linux en Preguntas y respuestas de Microsoft](https://docs.microsoft.com/answers/topics/teams.html).</span><span class="sxs-lookup"><span data-stu-id="20aaf-171">For Teams for Linux support you can use the [Linux forum support channel on Microsoft Q&A](https://docs.microsoft.com/answers/topics/teams.html).</span></span> <span data-ttu-id="20aaf-172">Asegúrese de usar la etiqueta `teams-linux` al publicar preguntas.</span><span class="sxs-lookup"><span data-stu-id="20aaf-172">Be sure to use the `teams-linux` tag when posting questions.</span></span> 

#### <a name="install-teams-using-deb-package"></a><span data-ttu-id="20aaf-173">Instalación de Teams con el paquete DEB</span><span class="sxs-lookup"><span data-stu-id="20aaf-173">Install Teams using DEB package</span></span>

1. <span data-ttu-id="20aaf-174">Descargue el paquete desde https://aka.ms/getteams.</span><span class="sxs-lookup"><span data-stu-id="20aaf-174">Download the package from https://aka.ms/getteams.</span></span>
2. <span data-ttu-id="20aaf-175">Instálelo mediante uno de los métodos siguientes:</span><span class="sxs-lookup"><span data-stu-id="20aaf-175">Install using one of the following:</span></span>  
    - <span data-ttu-id="20aaf-176">Abra la herramienta de administración del paquete correspondiente y siga el proceso autoguiado de instalación de aplicaciones Linux.</span><span class="sxs-lookup"><span data-stu-id="20aaf-176">Open the relevant package management tool and go through the self-guided Linux app installation process.</span></span>
    - <span data-ttu-id="20aaf-177">O bien, si le gusta Terminal, escriba lo siguiente: `sudo dpkg -i **teams download file**`</span><span class="sxs-lookup"><span data-stu-id="20aaf-177">Or if you love Terminal, type: `sudo dpkg -i **teams download file**`</span></span>

<span data-ttu-id="20aaf-178">Para iniciar Teams a través de Actividades o a través de Terminal, escriba `teams`.</span><span class="sxs-lookup"><span data-stu-id="20aaf-178">You can launch Teams via Activities or via Terminal by typing `teams`.</span></span> 

#### <a name="install-teams-using-rpm-package"></a><span data-ttu-id="20aaf-179">Instalación de Teams con el paquete RPM</span><span class="sxs-lookup"><span data-stu-id="20aaf-179">Install Teams using RPM package</span></span>

1. <span data-ttu-id="20aaf-180">Descargue el paquete desde https://aka.ms/getteams.</span><span class="sxs-lookup"><span data-stu-id="20aaf-180">Download the package from https://aka.ms/getteams.</span></span>
2. <span data-ttu-id="20aaf-181">Instálelo mediante uno de los métodos siguientes:</span><span class="sxs-lookup"><span data-stu-id="20aaf-181">Install using one of the following:</span></span>
    - <span data-ttu-id="20aaf-182">Abra la herramienta de administración del paquete correspondiente y siga el proceso autoguiado de instalación de aplicaciones Linux.</span><span class="sxs-lookup"><span data-stu-id="20aaf-182">Open the relevant package management tool and go through the self-guided Linux app installation process.</span></span>
    - <span data-ttu-id="20aaf-183">O bien, si le gusta Terminal, escriba lo siguiente: `sudo yum install **teams download file**`</span><span class="sxs-lookup"><span data-stu-id="20aaf-183">Or if you love Terminal, type: `sudo yum install **teams download file**`</span></span>

<span data-ttu-id="20aaf-184">Para iniciar Teams a través de Actividades o a través de Terminal, escriba `teams`.</span><span class="sxs-lookup"><span data-stu-id="20aaf-184">You can launch Teams via Activities or via Terminal by typing `teams`.</span></span>

#### <a name="install-manually-from-the-command-line"></a><span data-ttu-id="20aaf-185">Instalación manual mediante la línea de comandos</span><span class="sxs-lookup"><span data-stu-id="20aaf-185">Install manually from the command line</span></span>

<span data-ttu-id="20aaf-186">Instalación manual en las distribuciones de Debian y Ubuntu:</span><span class="sxs-lookup"><span data-stu-id="20aaf-186">Install manually on Debian and Ubuntu distributions:</span></span>

```bash
curl https://packages.microsoft.com/keys/microsoft.asc | sudo apt-key add -
 
sudo sh -c 'echo "deb [arch=amd64] https://packages.microsoft.com/repos/ms-teams stable main" > /etc/apt/sources.list.d/teams.list'
 
sudo apt update
sudo apt install teams
```

<span data-ttu-id="20aaf-187">Instalación manual en las distribuciones basadas en RHEL, Fedora y CentOS:</span><span class="sxs-lookup"><span data-stu-id="20aaf-187">Install manually on RHEL, Fedora and CentOS based distributions:</span></span>

```bash
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
 
sudo sh -c 'echo -e "[teams]\nname=teams\nbaseurl=https://packages.microsoft.com/yumrepos/ms-teams\nenabled=1\ngpgcheck=1\ngpgkey=https://packages.microsoft.com/keys/microsoft.asc" > /etc/yum.repos.d/teams.repo'
 
sudo dnf check-update
sudo dnf install teams
```

<span data-ttu-id="20aaf-188">También puede usar yum en lugar de dnf:</span><span class="sxs-lookup"><span data-stu-id="20aaf-188">Alternatively, to use yum instead of dnf:</span></span>

```bash
yum check-update
sudo yum install teams
```

<span data-ttu-id="20aaf-189">Instalación manual en las distribuciones basadas en openSUSE:</span><span class="sxs-lookup"><span data-stu-id="20aaf-189">Install manually on openSUSE based distributions:</span></span>

```bash
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
 
sudo sh -c 'echo -e "[teams]\nname=teams\nbaseurl=https://packages.microsoft.com/yumrepos/ms-teams\nenabled=1\nautorefresh=1\nkeeppackages=0\ntype=rpm-md\ngpgcheck=1\ngpgkey=https://packages.microsoft.com/keys/microsoft.asc" > /etc/zypp/repos.d/teams.repo'
 
sudo zypper refresh
sudo zypper install teams
```

## <a name="web-client"></a><span data-ttu-id="20aaf-190">Cliente Web</span><span class="sxs-lookup"><span data-stu-id="20aaf-190">Web client</span></span> 

<span data-ttu-id="20aaf-191">El cliente web ([https://teams.microsoft.com](https://go.microsoft.com/fwlink/?linkid=855753)) es un cliente completo y funcional que puede utilizarse desde una variedad de exploradores.</span><span class="sxs-lookup"><span data-stu-id="20aaf-191">The web client ([https://teams.microsoft.com](https://go.microsoft.com/fwlink/?linkid=855753)) is a full, functional client that can be used from a variety of browsers.</span></span> <span data-ttu-id="20aaf-192">El cliente web es compatible con Llamadas y Reuniones mediante webRTC, por lo que no se requiere ningún complemento o descarga para ejecutar Teams en un explorador web.</span><span class="sxs-lookup"><span data-stu-id="20aaf-192">The web client supports Calling and Meetings by using webRTC, so there is no plug-in or download required to run Teams in a web browser.</span></span> <span data-ttu-id="20aaf-193">El explorador debe configurarse para permitir cookies de terceros.</span><span class="sxs-lookup"><span data-stu-id="20aaf-193">The browser must be configured to allow third-party cookies.</span></span> 

[!INCLUDE [browser-support](includes/browser-support.md)]

<span data-ttu-id="20aaf-194">El cliente web detecta la versión del explorador al conectarse con [https://teams.microsoft.com](https://go.microsoft.com/fwlink/?linkid=855753).</span><span class="sxs-lookup"><span data-stu-id="20aaf-194">The web client performs browser version detection upon connecting to [https://teams.microsoft.com](https://go.microsoft.com/fwlink/?linkid=855753).</span></span> <span data-ttu-id="20aaf-195">Si se detecta una versión no admitida, se bloquea el acceso a la interfaz web y se recomienda al usuario que descargue el cliente de escritorio o la aplicación móvil.</span><span class="sxs-lookup"><span data-stu-id="20aaf-195">If an unsupported browser version is detected, it will block access to the web interface and recommend that the user download the desktop client or mobile app.</span></span>

## <a name="mobile-clients"></a><span data-ttu-id="20aaf-196">Clientes móviles</span><span class="sxs-lookup"><span data-stu-id="20aaf-196">Mobile clients</span></span>

<span data-ttu-id="20aaf-197">Las aplicaciones móviles de Microsoft Teams están disponibles para iOS y Android, y están pensadas para que los usuarios que no están en un lugar fijo participen en conversaciones basadas en chat y para permitir las llamadas de audio de par a par.</span><span class="sxs-lookup"><span data-stu-id="20aaf-197">The Microsoft Teams mobile apps are available for Android and iOS, and are geared for on-the-go users participating in chat-based conversations and allow peer-to-peer audio calls.</span></span> <span data-ttu-id="20aaf-198">Para las aplicaciones móviles, vaya a la tienda móvil correspondiente: Google Play y App Store de Apple.</span><span class="sxs-lookup"><span data-stu-id="20aaf-198">For mobile apps, go to the relevant mobile stores Google Play and the Apple App Store.</span></span> <span data-ttu-id="20aaf-199">La aplicación de Windows Phone se retiró el 20 de julio de 2018 y podría dejar de funcionar.</span><span class="sxs-lookup"><span data-stu-id="20aaf-199">The Windows Phone App was retired July 20, 2018 and may no longer work.</span></span> 

<span data-ttu-id="20aaf-200">Aquí puede ver cómo [obtener Teams para Android](get-teams-android-in-china.md) en China.</span><span class="sxs-lookup"><span data-stu-id="20aaf-200">In China, here's how to [get Teams for Android](get-teams-android-in-china.md).</span></span> 

<span data-ttu-id="20aaf-201">Las siguientes son las plataformas móviles admitidas para Microsoft Teams:</span><span class="sxs-lookup"><span data-stu-id="20aaf-201">Supported mobile platforms for Microsoft Teams mobile apps are the following:</span></span>

-   <span data-ttu-id="20aaf-202">**Android**: la compatibilidad está limitada a las cuatro versiones principales más recientes de Android.</span><span class="sxs-lookup"><span data-stu-id="20aaf-202">**Android**: Support is limited to the last four major versions of Android.</span></span> <span data-ttu-id="20aaf-203">Cuando se publica una nueva versión principal de Android, se admiten oficialmente la nueva versión y las tres versiones anteriores.</span><span class="sxs-lookup"><span data-stu-id="20aaf-203">When a new major version of Android is released, the new version and the previous three versions are officially supported.</span></span>

-   <span data-ttu-id="20aaf-204">**iOS**: la compatibilidad está limitada a las dos versiones principales más recientes de iOS.</span><span class="sxs-lookup"><span data-stu-id="20aaf-204">**iOS**: Support is limited to the two most recent major versions of iOS.</span></span> <span data-ttu-id="20aaf-205">Cuando se publica una nueva versión principal de iOS, se admiten oficialmente la nueva versión y las tres versiones anteriores de iOS.</span><span class="sxs-lookup"><span data-stu-id="20aaf-205">When a new major version of iOS is released, the new version of iOS and the previous version are officially supported.</span></span>

> [!NOTE]
> <span data-ttu-id="20aaf-206">La versión móvil debe estar disponible para el público para que Teams funcione según lo esperado.</span><span class="sxs-lookup"><span data-stu-id="20aaf-206">The mobile version must be available to the public in order for Teams to work as expected.</span></span>

<span data-ttu-id="20aaf-207">Las aplicaciones móviles solamente se distribuyen y actualizan en la tienda de aplicaciones de la plataforma móvil correspondiente.</span><span class="sxs-lookup"><span data-stu-id="20aaf-207">Mobile apps are distributed and updated through the respective mobile platform’s app store only.</span></span> <span data-ttu-id="20aaf-208">Microsoft no admite la distribución de las aplicaciones móviles mediante MDM ni instalación de prueba.</span><span class="sxs-lookup"><span data-stu-id="20aaf-208">Distribution of the mobile apps via MDM or side-loading is not supported by Microsoft.</span></span> <span data-ttu-id="20aaf-209">Una vez que se haya instalado la aplicación móvil en una plataforma móvil compatible, se admitirá la aplicación móvil de Teams, siempre y cuando la versión se encuentre dentro de los tres meses siguientes a la versión actual.</span><span class="sxs-lookup"><span data-stu-id="20aaf-209">Once the mobile app has been installed on a supported mobile platform, the Teams Mobile App itself will be supported provided the version is within three months of the current release.</span></span>


| | | |
|---------|---------|---------|
|![Un icono que representa un punto de decisión](media/Get_clients_for_Microsoft_Teams_image4.png)      |<span data-ttu-id="20aaf-211">Punto de decisión</span><span class="sxs-lookup"><span data-stu-id="20aaf-211">Decision Point</span></span>         |<span data-ttu-id="20aaf-212">¿Hay alguna restricción que evite que los usuarios instalen el cliente de Microsoft Teams adecuado en sus dispositivos?</span><span class="sxs-lookup"><span data-stu-id="20aaf-212">Are there any restrictions preventing users from installing the appropriate Microsoft Teams client on their devices?</span></span>         |
|![Un icono que representa los siguientes pasos](media/Get_clients_for_Microsoft_Teams_image5.png)     |<span data-ttu-id="20aaf-214">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="20aaf-214">Next Steps</span></span>         |<span data-ttu-id="20aaf-p121">Si su organización restringe la instalación de software, asegúrese de que el proceso sea compatible con Microsoft Teams. Nota: No se requieren derechos de administrador para instalar el cliente en PC, pero sí son necesarios para Mac.</span><span class="sxs-lookup"><span data-stu-id="20aaf-p121">If your organization restricts software installation, make sure that process is compatible with Microsoft Teams. Note: Admin rights are not required for PC client installation but are required for installation on a Mac.</span></span>         |

## <a name="client-update-management"></a><span data-ttu-id="20aaf-217">Administración de actualizaciones del cliente</span><span class="sxs-lookup"><span data-stu-id="20aaf-217">Client update management</span></span>

<span data-ttu-id="20aaf-218">Actualmente, el servicio de Microsoft Teams actualiza automáticamente los clientes sin que sea necesaria la intervención de los administradores de TI.</span><span class="sxs-lookup"><span data-stu-id="20aaf-218">Clients are currently updated automatically by the Microsoft Teams service with no IT administrator intervention required.</span></span> <span data-ttu-id="20aaf-219">Si hay una actualización disponible, el cliente descargará automáticamente la actualización y, si la aplicación ha estado inactiva durante un período de tiempo, se iniciará el proceso de actualización.</span><span class="sxs-lookup"><span data-stu-id="20aaf-219">If an update is available, the client will automatically download the update and when the app has idled for a period of time, the update process will begin.</span></span>

## <a name="client-side-configurations"></a><span data-ttu-id="20aaf-220">Configuración del lado del cliente</span><span class="sxs-lookup"><span data-stu-id="20aaf-220">Client-side configurations</span></span>

<span data-ttu-id="20aaf-221">Actualmente, no hay opciones disponibles para configurar el cliente a través del administrador de inquilinos, PowerShell, Group Policy Objects ni el registro.</span><span class="sxs-lookup"><span data-stu-id="20aaf-221">Currently, there are no supported options available to configure the client either through the tenant admin, PowerShell, Group Policy Objects or the registry.</span></span>

## <a name="notification-settings"></a><span data-ttu-id="20aaf-222">Configuración de notificaciones</span><span class="sxs-lookup"><span data-stu-id="20aaf-222">Notification settings</span></span>

<span data-ttu-id="20aaf-p123">En este momento, no hay opciones disponibles para que los administradores de TI puedan configurar las notificaciones para los clientes. Todas las opciones de notificaciones las establece el usuario. En la siguiente figura se detalla la configuración predeterminada del cliente.</span><span class="sxs-lookup"><span data-stu-id="20aaf-p123">There are currently no options available for IT administrators to configure client-side notification settings. All notification options are set by the user. The figure below outlines the default client settings.</span></span>

![Captura de pantalla de la configuración de Notificaciones.](media/Get_clients_for_Microsoft_Teams_image6.png)

## <a name="sample-powershell-script---inbound-firewall-rule"></a><span data-ttu-id="20aaf-227">Script de PowerShell de ejemplo: regla de firewall de entrada</span><span class="sxs-lookup"><span data-stu-id="20aaf-227">Sample PowerShell script - inbound firewall rule</span></span>

<span data-ttu-id="20aaf-228">Este script de ejemplo, que tiene que ejecutarse en los equipos de cliente en el contexto de una cuenta de administrador con privilegios elevados, creará una nueva regla de firewall de entrada para cada carpeta de usuario que se encuentra en c:\users.</span><span class="sxs-lookup"><span data-stu-id="20aaf-228">This sample script, which needs to run on client computers in the context of an elevated administrator account, will create a new inbound firewall rule for each user folder found in c:\users.</span></span> <span data-ttu-id="20aaf-229">Cuando Teams encuentra esta regla, impedirá que la aplicación de Teams solicite a los usuarios crear reglas de firewall cuando los usuarios realicen su primera llamada de Teams.</span><span class="sxs-lookup"><span data-stu-id="20aaf-229">When Teams finds this rule, it will prevent the Teams application from prompting users to create firewall rules when the users make their first call from Teams.</span></span> 

```powershell
<#
.SYNOPSIS
   Creates firewall rules for Teams.
.DESCRIPTION
   (c) Microsoft Corporation 2018. All rights reserved. Script provided as-is without any warranty of any kind. Use it freely at your own risks.
   Must be run with elevated permissions. Can be run as a GPO Computer Startup script, or as a Scheduled Task with elevated permissions. 
   The script will create a new inbound firewall rule for each user folder found in c:\users. 
   Requires PowerShell 3.0.
#>

#Requires -Version 3

$users = Get-ChildItem (Join-Path -Path $env:SystemDrive -ChildPath 'Users') -Exclude 'Public', 'ADMINI~*'
if ($null -ne $users) {
    foreach ($user in $users) {
        $progPath = Join-Path -Path $user.FullName -ChildPath "AppData\Local\Microsoft\Teams\Current\Teams.exe"
        if (Test-Path $progPath) {
            if (-not (Get-NetFirewallApplicationFilter -Program $progPath -ErrorAction SilentlyContinue)) {
                $ruleName = "Teams.exe for user $($user.Name)"
                "UDP", "TCP" | ForEach-Object { New-NetFirewallRule -DisplayName $ruleName -Direction Inbound -Profile Domain -Program $progPath -Action Allow -Protocol $_ }
                Clear-Variable ruleName
            }
        }
        Clear-Variable progPath
    }
}
```
