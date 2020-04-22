---
title: Obtener clientes para Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
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
ms.openlocfilehash: d75a76ca7a98191f90005ebe6c1edf915fde4571
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/22/2020
ms.locfileid: "43778306"
---
# <a name="get-clients-for-microsoft-teams"></a><span data-ttu-id="8d07f-103">Obtener clientes para Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="8d07f-103">Get clients for Microsoft Teams</span></span> 


<span data-ttu-id="8d07f-p101">Microsoft Teams tiene clientes disponibles para web, escritorio (Windows, Mac y Linux) y móvil (iOS y Android). Todos estos clientes requieren una conexión a Internet activa y no admiten el modo sin conexión.</span><span class="sxs-lookup"><span data-stu-id="8d07f-p101">Microsoft Teams has clients available for desktop (Windows, Mac, and Linux), web, and mobile (Android and iOS). These clients all require an active internet connection and do not support an offline mode.</span></span>

> [!NOTE]
> <span data-ttu-id="8d07f-106">A partir del 29 de noviembre de 2018, ya no podrá usar la aplicación de Microsoft Teams para Windows 10 S (versión preliminar), disponible en Microsoft Store.</span><span class="sxs-lookup"><span data-stu-id="8d07f-106">Effective November 29, 2018, you'll no longer be able to use the Microsoft Teams for Windows 10 S (Preview) app, available from the Microsoft Store.</span></span> <span data-ttu-id="8d07f-107">En su lugar, ahora puede descargar e instalar el cliente de escritorio de Teams en los dispositivos que ejecutan Windows 10 en modo S.</span><span class="sxs-lookup"><span data-stu-id="8d07f-107">Instead, you can now download and install the Teams desktop client on devices running Windows 10 S mode.</span></span> <span data-ttu-id="8d07f-108">Para descargar el cliente de escritorio, vaya a [https://teams.microsoft.com/downloads](https://go.microsoft.com/fwlink/?linkid=855754).</span><span class="sxs-lookup"><span data-stu-id="8d07f-108">To download the desktop client, go to [https://teams.microsoft.com/downloads](https://go.microsoft.com/fwlink/?linkid=855754).</span></span> <span data-ttu-id="8d07f-109">Las compilaciones de MSI del cliente de escritorio de Teams aún no están disponibles para los dispositivos que ejecutan Windows 10 en modo S.</span><span class="sxs-lookup"><span data-stu-id="8d07f-109">MSI builds of the Teams desktop client are not yet available for devices running Windows 10 S mode.</span></span>
>
> <span data-ttu-id="8d07f-110">Para obtener más información sobre Windows 10 en modo S, consulte [Presentamos Windows 10 en modo S](https://www.microsoft.com/windows/s-mode).</span><span class="sxs-lookup"><span data-stu-id="8d07f-110">For more information about Windows 10 S mode, see [Introducing Windows 10 in S mode](https://www.microsoft.com/windows/s-mode).</span></span> 

## <a name="desktop-client"></a><span data-ttu-id="8d07f-111">Cliente de escritorio</span><span class="sxs-lookup"><span data-stu-id="8d07f-111">Desktop client</span></span>

> [!TIP]
> <span data-ttu-id="8d07f-112">Vea la sesión siguiente para conocer las ventajas del cliente de escritorio de Windows, y cómo planearlo e implementarlo: [Cliente de escritorio de Teams para Windows](https://aka.ms/teams-clients)</span><span class="sxs-lookup"><span data-stu-id="8d07f-112">Watch the following session to learn about the benefits of the Windows Desktop Client, how to plan for it, and how to deploy it: [Teams Windows Desktop Client](https://aka.ms/teams-clients)</span></span>

<span data-ttu-id="8d07f-113">El cliente de escritorio de Microsoft Teams es una aplicación independiente y también está [disponible en las aplicaciones de microsoft 365 para empresas](https://docs.microsoft.com/deployoffice/teams-install).</span><span class="sxs-lookup"><span data-stu-id="8d07f-113">The Microsoft Teams desktop client is a standalone application and is also [available in Microsoft 365 Apps for enterprise](https://docs.microsoft.com/deployoffice/teams-install).</span></span> <span data-ttu-id="8d07f-114">Teams está disponible para las versiones de 32 bits y 64 bits de Windows (8.1 o posterior) y Windows Server (2012 R2 o posterior), así como para macOS (10.10 o posterior) y Linux (en los formatos `.deb` y `.rpm`).</span><span class="sxs-lookup"><span data-stu-id="8d07f-114">Teams is available for 32-bit and 64-bit versions of Windows (8.1 or later) and Windows Server (2012 R2 or later), as well as for macOS (10.10 or later) and Linux (in `.deb` and `.rpm` formats).</span></span> <span data-ttu-id="8d07f-115">En Windows, Teams requiere .NET Framework 4.5 o posterior; el instalador de Teams le ofrecerá instalarlo si no lo tiene.</span><span class="sxs-lookup"><span data-stu-id="8d07f-115">On Windows, Teams requires .NET Framework 4.5 or later; the Teams installer will offer to install it for you if you don't have it.</span></span> <span data-ttu-id="8d07f-116">En Linux, los administradores de paquetes como `apt` y `yum` intentarán instalar los requisitos por usted.</span><span class="sxs-lookup"><span data-stu-id="8d07f-116">On Linux, package managers such as `apt` and `yum` will try to install any requirements for you.</span></span> <span data-ttu-id="8d07f-117">No obstante, si no lo hacen, deberá instalar todos los requisitos indicados antes de instalar Teams en Linux.</span><span class="sxs-lookup"><span data-stu-id="8d07f-117">However, if they don't then you will need to install any reported requirements before installing Teams on Linux.</span></span>

<span data-ttu-id="8d07f-118">Los clientes de escritorio brindan asistencia en tiempo real para las comunicaciones (audio, vídeo y contenido compartido) para las reuniones de equipo, las llamadas grupales y las llamadas de uno a uno.</span><span class="sxs-lookup"><span data-stu-id="8d07f-118">The desktop clients provide real-time communications support (audio, video, and content sharing) for team meetings, group calling, and private one-on-one calls.</span></span>

<span data-ttu-id="8d07f-119">Los usuarios pueden descargar e instalar los clientes de escritorio directamente desde [https://teams.microsoft.com/downloads](https://go.microsoft.com/fwlink/?linkid=855754) si tienen los permisos locales adecuados (no se requieren derechos de administrador para instalar el cliente de Teams en PC, pero sí son necesarios para Mac).</span><span class="sxs-lookup"><span data-stu-id="8d07f-119">Desktop clients can be downloaded and installed by end users directly from [https://teams.microsoft.com/downloads](https://go.microsoft.com/fwlink/?linkid=855754) if they have the appropriate local permissions (admin rights are not required to install the Teams client on a PC but are required on a Mac).</span></span>

> [!NOTE]
> <span data-ttu-id="8d07f-120">Para obtener más información sobre cómo instalar Teams en un Chromebook, vea [Cómo instalar y ejecutar Microsoft Office en un Chromebook](https://support.office.com/article/how-to-install-and-run-microsoft-office-on-a-chromebook-32f14a23-2c1a-4579-b973-d4b1d78561ad).</span><span class="sxs-lookup"><span data-stu-id="8d07f-120">For more details about installing Teams on a Chromebook, please see [How to install and run Microsoft Office on a Chromebook](https://support.office.com/article/how-to-install-and-run-microsoft-office-on-a-chromebook-32f14a23-2c1a-4579-b973-d4b1d78561ad).</span></span>

<span data-ttu-id="8d07f-121">Los administradores de TI pueden elegir el método que prefieran para distribuir los archivos de instalación en los equipos de su organización.</span><span class="sxs-lookup"><span data-stu-id="8d07f-121">IT admins can choose their preferred method to distribute the installation files to computers in their organization.</span></span> <span data-ttu-id="8d07f-122">Por ejemplo: Microsoft Endpoint Configuration Manager (Windows) o Jamf Pro (macOS).</span><span class="sxs-lookup"><span data-stu-id="8d07f-122">Some examples include Microsoft Endpoint Configuration Manager (Windows) or Jamf Pro (macOS).</span></span> <span data-ttu-id="8d07f-123">Para obtener el paquete de MSI de distribución de Windows, vea [Instalar Microsoft Teams con MSI](msi-deployment.md).</span><span class="sxs-lookup"><span data-stu-id="8d07f-123">To get the MSI package for Windows distribution, see [Install Microsoft Teams using MSI](msi-deployment.md).</span></span>  

> [!NOTE]
> <span data-ttu-id="8d07f-124">La distribución del cliente a través de estos mecanismos es solo para la instalación inicial de los clientes de Microsoft Teams y no para futuras actualizaciones.</span><span class="sxs-lookup"><span data-stu-id="8d07f-124">Distribution of the client via these mechanisms is only for the initial installation of Microsoft Team clients and not for future updates.</span></span>

### <a name="windows"></a><span data-ttu-id="8d07f-125">Windows</span><span class="sxs-lookup"><span data-stu-id="8d07f-125">Windows</span></span>

<span data-ttu-id="8d07f-126">La instalación de Microsoft Teams para Windows brinda instaladores que se pueden descargar en arquitecturas de 32 y 64 bits.</span><span class="sxs-lookup"><span data-stu-id="8d07f-126">The Microsoft Teams installation for Windows provides downloadable installers in 32-bit and 64-bit architecture.</span></span>

> [!NOTE]
> <span data-ttu-id="8d07f-127">La arquitectura (32 o 64 bits) de Microsoft Teams es independiente de la arquitectura de Windows y Office que esté instalada.</span><span class="sxs-lookup"><span data-stu-id="8d07f-127">The architecture (32-bit vs. 64-bit) of Microsoft Teams is agnostic to the architecture of Windows and Office that is installed.</span></span>

<span data-ttu-id="8d07f-128">El cliente de Windows se implementará en la carpeta AppData ubicada en el perfil del usuario.</span><span class="sxs-lookup"><span data-stu-id="8d07f-128">The Windows client is deployed to the AppData folder located in the user’s profile.</span></span> <span data-ttu-id="8d07f-129">Implementar en el perfil de usuario local permite instalar el cliente sin necesidad de tener permisos elevados.</span><span class="sxs-lookup"><span data-stu-id="8d07f-129">Deploying to the user’s local profile allows the client to be installed without requiring elevated rights.</span></span> <span data-ttu-id="8d07f-130">El cliente de Windows aprovecha las siguientes ubicaciones:</span><span class="sxs-lookup"><span data-stu-id="8d07f-130">The Windows client leverages the following locations:</span></span>

- <span data-ttu-id="8d07f-131">%LocalAppData%\\Microsoft\\Teams</span><span class="sxs-lookup"><span data-stu-id="8d07f-131">%LocalAppData%\\Microsoft\\Teams</span></span>

- <span data-ttu-id="8d07f-132">%LocalAppData%\\Microsoft\\TeamsMeetingAddin</span><span class="sxs-lookup"><span data-stu-id="8d07f-132">%LocalAppData%\\Microsoft\\TeamsMeetingAddin</span></span>

- <span data-ttu-id="8d07f-133">%AppData%\\Microsoft\\Teams</span><span class="sxs-lookup"><span data-stu-id="8d07f-133">%AppData%\\Microsoft\\Teams</span></span>

- <span data-ttu-id="8d07f-134">%LocalAppData%\\SquirrelTemp</span><span class="sxs-lookup"><span data-stu-id="8d07f-134">%LocalAppData%\\SquirrelTemp</span></span>

<span data-ttu-id="8d07f-135">Cuando los usuarios inician una llamada utilizando el cliente de Microsoft Teams, podrían recibir una advertencia con la configuración del firewall de Windows que les pide que permitan la comunicación.</span><span class="sxs-lookup"><span data-stu-id="8d07f-135">When users initiate a call using the Microsoft Teams client for the first time, they might notice a warning with the Windows firewall settings that asks for users to allow communication.</span></span> <span data-ttu-id="8d07f-136">Es posible que se indique a los usuarios que ignoren el mensaje porque la llamada funcionará, incluso si la advertencia se descarta.</span><span class="sxs-lookup"><span data-stu-id="8d07f-136">Users might be instructed to ignore this message because the call will work, even when the warning is dismissed.</span></span>

![Captura de pantalla de un cuadro de diálogo Alerta de seguridad de Windows.](media/Get_clients_for_Microsoft_Teams_image3.png)

> [!NOTE]
> <span data-ttu-id="8d07f-p107">La configuración del firewall de Windows se modificará incluso si el mensaje se descarta seleccionando "Cancelar". Se crearán dos reglas de entrada para teams.exe con la acción de bloqueo para los protocolos TCP y UDP.</span><span class="sxs-lookup"><span data-stu-id="8d07f-p107">Windows Firewall configuration will be altered even when the prompt is dismissed by selecting “Cancel”. Two inbound rules for teams.exe will be created with Block action for both TCP and UDP protocols.</span></span>

<span data-ttu-id="8d07f-140">Si quiere evitar que los equipos soliciten a los usuarios que creen reglas de Firewall cuando los usuarios hacen su primera llamada desde Teams, use la siguiente [regla de Firewall de entrada de script de PowerShell](#sample-powershell-script---inbound-firewall-rule) que se muestra a continuación.</span><span class="sxs-lookup"><span data-stu-id="8d07f-140">If you want to prevent Teams from prompting users to create firewall rules when the users make their first call from Teams, use the [Sample PowerShell script - inbound firewall rule](#sample-powershell-script---inbound-firewall-rule) below.</span></span> 

### <a name="mac"></a><span data-ttu-id="8d07f-141">Mac</span><span class="sxs-lookup"><span data-stu-id="8d07f-141">Mac</span></span>

<span data-ttu-id="8d07f-142">Los usuarios de Mac pueden instalar Teams mediante el uso de un archivo PKG de instalación para equipos macOS.</span><span class="sxs-lookup"><span data-stu-id="8d07f-142">Mac users can install Teams by using a PKG installation file for macOS computers.</span></span> <span data-ttu-id="8d07f-143">Se requiere acceso administrativo para instalar el cliente de Mac.</span><span class="sxs-lookup"><span data-stu-id="8d07f-143">Administrative access is required to install the Mac client.</span></span> <span data-ttu-id="8d07f-144">El cliente de macOS se instala en la carpeta /Applications.</span><span class="sxs-lookup"><span data-stu-id="8d07f-144">The macOS client is installed to the /Applications folder.</span></span>

#### <a name="install-teams-by-using-the-pkg-file"></a><span data-ttu-id="8d07f-145">Instalar Teams con el archivo PKG </span><span class="sxs-lookup"><span data-stu-id="8d07f-145">Install Teams by using the PKG file</span></span>

1. <span data-ttu-id="8d07f-146">Desde la [página de descarga de Teams](https://teams.microsoft.com/downloads), en **Mac**, haga clic en **Descargar**.</span><span class="sxs-lookup"><span data-stu-id="8d07f-146">From the [Teams download page](https://teams.microsoft.com/downloads), under **Mac**, click **Download**.</span></span>
2. <span data-ttu-id="8d07f-147">Haga doble clic en el archivo PKG.</span><span class="sxs-lookup"><span data-stu-id="8d07f-147">Double click the PKG file.</span></span>
3. <span data-ttu-id="8d07f-148">Siga los pasos del asistente de instalación para completar la instalación.</span><span class="sxs-lookup"><span data-stu-id="8d07f-148">Follow the installation wizard to complete the installation.</span></span>
4. <span data-ttu-id="8d07f-149">Se instalará Teams en la carpeta /Applications.</span><span class="sxs-lookup"><span data-stu-id="8d07f-149">Teams will be installed to /Applications folder.</span></span> <span data-ttu-id="8d07f-150">Es una instalación de todo el equipo.</span><span class="sxs-lookup"><span data-stu-id="8d07f-150">It is a machine-wide installation.</span></span>

> [!NOTE]
> <span data-ttu-id="8d07f-151">Durante la instalación, el PKG solicitará las credenciales de administrador.</span><span class="sxs-lookup"><span data-stu-id="8d07f-151">During the installation, the PKG will prompt for admin credentials.</span></span> <span data-ttu-id="8d07f-152">El usuario debe escribir las credenciales de administrador, independientemente de si el usuario es un administrador.</span><span class="sxs-lookup"><span data-stu-id="8d07f-152">The user needs to enter the admin credentials, regardless of whether or not the user is an admin.</span></span>

<span data-ttu-id="8d07f-153">Si un usuario actualmente tiene una instalación DMG de Teams y quiere reemplazarla con la instalación del PKG, el usuario debe:</span><span class="sxs-lookup"><span data-stu-id="8d07f-153">If a user currently has a DMG installation of Teams and wants to replace it with the PKG installation, the user should:</span></span>

1. <span data-ttu-id="8d07f-154">Salir de la aplicación de Teams.</span><span class="sxs-lookup"><span data-stu-id="8d07f-154">Exit the Teams app.</span></span>
2. <span data-ttu-id="8d07f-155">Desinstalar la aplicación de Teams.</span><span class="sxs-lookup"><span data-stu-id="8d07f-155">Uninstall the Teams app.</span></span>
3. <span data-ttu-id="8d07f-156">Instale el archivo PKG.</span><span class="sxs-lookup"><span data-stu-id="8d07f-156">Install the PKG file.</span></span>

<span data-ttu-id="8d07f-157">Los administradores de TI pueden usar la implementación administrada de Teams para distribuir los archivos de instalación en todos los equipos Mac en su organización, como Jamf Pro.</span><span class="sxs-lookup"><span data-stu-id="8d07f-157">IT admins can use managed deployment of Teams to distribute the installation files to all Macs in their organization, such as Jamf Pro.</span></span>

> [!NOTE]
> <span data-ttu-id="8d07f-158">Si tiene problemas para instalar el PKG, háganoslo saber.</span><span class="sxs-lookup"><span data-stu-id="8d07f-158">If you experience issues installing the PKG, let us know.</span></span> <span data-ttu-id="8d07f-159">En la sección **Comentarios** al final de este artículo, haga clic en **Comentarios sobre el producto**.</span><span class="sxs-lookup"><span data-stu-id="8d07f-159">In the **Feedback** section at the end of this article, click **Product feedback**.</span></span>

### <a name="linux"></a><span data-ttu-id="8d07f-160">Linux</span><span class="sxs-lookup"><span data-stu-id="8d07f-160">Linux</span></span>

<span data-ttu-id="8d07f-161">Los usuarios podrán instalar paquetes de Linux nativos en los formatos `.deb` y `.rpm`.</span><span class="sxs-lookup"><span data-stu-id="8d07f-161">Users will be able to install native Linux packages in `.deb` and `.rpm` formats.</span></span>
<span data-ttu-id="8d07f-162">Al instalar el paquete DEB o RPM, se instalará automáticamente el repositorio del paquete.</span><span class="sxs-lookup"><span data-stu-id="8d07f-162">Installing the DEB or RPM package will automatically install the package repository.</span></span>
- <span data-ttu-id="8d07f-163">DEB `https://packages.microsoft.com/repos/ms-teams stable main`</span><span class="sxs-lookup"><span data-stu-id="8d07f-163">DEB `https://packages.microsoft.com/repos/ms-teams stable main`</span></span>
- <span data-ttu-id="8d07f-164">RPM `https://packages.microsoft.com/yumrepos/ms-teams`</span><span class="sxs-lookup"><span data-stu-id="8d07f-164">RPM `https://packages.microsoft.com/yumrepos/ms-teams`</span></span> 

<span data-ttu-id="8d07f-165">La clave de firma para habilitar la actualización automática mediante el administrador de paquetes del sistema se instala automáticamente.</span><span class="sxs-lookup"><span data-stu-id="8d07f-165">The signing key to enable auto-updating using the system's package manager is installed automatically.</span></span> <span data-ttu-id="8d07f-166">No obstante, también se puede encontrar en: (https://packages.microsoft.com/keys/microsoft.asc).</span><span class="sxs-lookup"><span data-stu-id="8d07f-166">However, it can also be found at: (https://packages.microsoft.com/keys/microsoft.asc).</span></span> <span data-ttu-id="8d07f-167">Microsoft Teams se suministra mensualmente y, si el repositorio se ha instalado correctamente, el administrador de paquetes del sistema debería controlar la actualización automática de la misma manera que otros paquetes del sistema.</span><span class="sxs-lookup"><span data-stu-id="8d07f-167">Microsoft Teams ships monthly and if the repository was installed correctly, then your system package manager should handle auto-updating in the same way as other packages on the system.</span></span>

> [!NOTE] 
> <span data-ttu-id="8d07f-168">Si encuentra un error, envíelo mediante `Report a Problem` desde el cliente.</span><span class="sxs-lookup"><span data-stu-id="8d07f-168">If you find a bug, submit it using `Report a Problem` from within the client.</span></span> <span data-ttu-id="8d07f-169">Para ver los problemas conocidos, consulte [Problemas conocidos](Known-issues.md).</span><span class="sxs-lookup"><span data-stu-id="8d07f-169">For known issues, see [Known Issues](Known-issues.md).</span></span>
> <span data-ttu-id="8d07f-170">Para obtener soporte técnico de Teams para Linux, puede usar el [canal de soporte del foro de Linux en Preguntas y respuestas de Microsoft](https://docs.microsoft.com/answers/topics/teams.html).</span><span class="sxs-lookup"><span data-stu-id="8d07f-170">For Teams for Linux support you can use the [Linux forum support channel on Microsoft Q&A](https://docs.microsoft.com/answers/topics/teams.html).</span></span> <span data-ttu-id="8d07f-171">Asegúrese de usar la etiqueta `teams-linux` al publicar preguntas.</span><span class="sxs-lookup"><span data-stu-id="8d07f-171">Be sure to use the `teams-linux` tag when posting questions.</span></span> 

#### <a name="install-teams-using-deb-package"></a><span data-ttu-id="8d07f-172">Instalación de Teams con el paquete DEB</span><span class="sxs-lookup"><span data-stu-id="8d07f-172">Install Teams using DEB package</span></span>

1. <span data-ttu-id="8d07f-173">Descargue el paquete desde https://aka.ms/getteams.</span><span class="sxs-lookup"><span data-stu-id="8d07f-173">Download the package from https://aka.ms/getteams.</span></span>
2. <span data-ttu-id="8d07f-174">Instálelo mediante uno de los métodos siguientes:</span><span class="sxs-lookup"><span data-stu-id="8d07f-174">Install using one of the following:</span></span>  
    - <span data-ttu-id="8d07f-175">Abra la herramienta de administración del paquete correspondiente y siga el proceso autoguiado de instalación de aplicaciones Linux.</span><span class="sxs-lookup"><span data-stu-id="8d07f-175">Open the relevant package management tool and go through the self-guided Linux app installation process.</span></span>
    - <span data-ttu-id="8d07f-176">O bien, si le gusta Terminal, escriba lo siguiente: `sudo apt install **teams download file**`</span><span class="sxs-lookup"><span data-stu-id="8d07f-176">Or if you love Terminal, type: `sudo apt install **teams download file**`</span></span>

<span data-ttu-id="8d07f-177">Para iniciar Teams a través de Actividades o a través de Terminal, escriba `Teams`.</span><span class="sxs-lookup"><span data-stu-id="8d07f-177">You can launch Teams via Activities or via Terminal by typing `Teams`.</span></span> 

#### <a name="install-teams-using-rpm-package"></a><span data-ttu-id="8d07f-178">Instalación de Teams con el paquete RPM</span><span class="sxs-lookup"><span data-stu-id="8d07f-178">Install Teams using RPM package</span></span>

1. <span data-ttu-id="8d07f-179">Descargue el paquete desde https://aka.ms/getteams.</span><span class="sxs-lookup"><span data-stu-id="8d07f-179">Download the package from https://aka.ms/getteams.</span></span>
2. <span data-ttu-id="8d07f-180">Instálelo mediante uno de los métodos siguientes:</span><span class="sxs-lookup"><span data-stu-id="8d07f-180">Install using one of the following:</span></span>
    - <span data-ttu-id="8d07f-181">Abra la herramienta de administración del paquete correspondiente y siga el proceso autoguiado de instalación de aplicaciones Linux.</span><span class="sxs-lookup"><span data-stu-id="8d07f-181">Open the relevant package management tool and go through the self-guided Linux app installation process.</span></span>
    - <span data-ttu-id="8d07f-182">O bien, si le gusta Terminal, escriba lo siguiente: `sudo yum install **teams download file**`</span><span class="sxs-lookup"><span data-stu-id="8d07f-182">Or if you love Terminal, type: `sudo yum install **teams download file**`</span></span>

<span data-ttu-id="8d07f-183">Para iniciar Teams a través de Actividades o a través de Terminal, escriba `Teams`.</span><span class="sxs-lookup"><span data-stu-id="8d07f-183">You can launch Teams via Activities or via Terminal by typing `Teams`.</span></span>

#### <a name="install-manually-from-the-command-line"></a><span data-ttu-id="8d07f-184">Instalación manual mediante la línea de comandos</span><span class="sxs-lookup"><span data-stu-id="8d07f-184">Install manually from the command line</span></span>

<span data-ttu-id="8d07f-185">Instalación manual en las distribuciones de Debian y Ubuntu:</span><span class="sxs-lookup"><span data-stu-id="8d07f-185">Install manually on Debian and Ubuntu distributions:</span></span>
```
curl https://packages.microsoft.com/keys/microsoft.asc | sudo apt-key add -
 
sudo sh -c 'echo "deb [arch=amd64] https://packages.microsoft.com/repos/ms-teams stable main" > /etc/apt/sources.list.d/teams.list'
 
sudo apt update
sudo apt install teams
```

<span data-ttu-id="8d07f-186">Instalación manual en las distribuciones basadas en RHEL, Fedora y CentOS:</span><span class="sxs-lookup"><span data-stu-id="8d07f-186">Install manually on RHEL, Fedora and CentOS based distributions:</span></span>
```
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
 
sudo sh -c 'echo -e "[teams]\nname=teams\nbaseurl=https://packages.microsoft.com/yumrepos/ms-teams\nenabled=1\ngpgcheck=1\ngpgkey=https://packages.microsoft.com/keys/microsoft.asc" > /etc/yum.repos.d/teams.repo'
 
sudo dnf check-update
sudo dnf install teams
```

<span data-ttu-id="8d07f-187">También puede usar yum en lugar de dnf:</span><span class="sxs-lookup"><span data-stu-id="8d07f-187">Alternatively, to use yum instead of dnf:</span></span>
```
yum check-update
sudo yum install teams
```

<span data-ttu-id="8d07f-188">Instalación manual en las distribuciones basadas en openSUSE:</span><span class="sxs-lookup"><span data-stu-id="8d07f-188">Install manually on openSUSE based distributions:</span></span>
```
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
 
sudo sh -c 'echo -e "[teams]\nname=teams\nbaseurl=https://packages.microsoft.com/yumrepos/ms-teams\nenabled=1\nautorefresh=1\nkeeppackages=0\ntype=rpm-md\ngpgcheck=1\ngpgkey=https://packages.microsoft.com/keys/microsoft.asc" > /etc/zypp/repos.d/teams.repo'
 
sudo zypper refresh
sudo zypper install teams
```

## <a name="web-client"></a><span data-ttu-id="8d07f-189">Cliente Web</span><span class="sxs-lookup"><span data-stu-id="8d07f-189">Web client</span></span> 

<span data-ttu-id="8d07f-190">El cliente web ([https://teams.microsoft.com](https://go.microsoft.com/fwlink/?linkid=855753)) es un cliente completo y funcional que puede utilizarse desde una variedad de exploradores.</span><span class="sxs-lookup"><span data-stu-id="8d07f-190">The web client ([https://teams.microsoft.com](https://go.microsoft.com/fwlink/?linkid=855753)) is a full, functional client that can be used from a variety of browsers.</span></span> <span data-ttu-id="8d07f-191">El cliente web es compatible con Llamadas y Reuniones mediante webRTC, por lo que no se requiere ningún complemento o descarga para ejecutar Teams en un explorador web.</span><span class="sxs-lookup"><span data-stu-id="8d07f-191">The web client supports Calling and Meetings by using webRTC, so there is no plug-in or download required to run Teams in a web browser.</span></span> <span data-ttu-id="8d07f-192">El explorador debe configurarse para permitir cookies de terceros.</span><span class="sxs-lookup"><span data-stu-id="8d07f-192">The browser must be configured to allow third-party cookies.</span></span> 

[!INCLUDE [browser-support](includes/browser-support.md)]

<span data-ttu-id="8d07f-193">El cliente web detecta la versión del explorador al conectarse con [https://teams.microsoft.com](https://go.microsoft.com/fwlink/?linkid=855753).</span><span class="sxs-lookup"><span data-stu-id="8d07f-193">The web client performs browser version detection upon connecting to [https://teams.microsoft.com](https://go.microsoft.com/fwlink/?linkid=855753).</span></span> <span data-ttu-id="8d07f-194">Si se detecta una versión no admitida, se bloquea el acceso a la interfaz web y se recomienda al usuario que descargue el cliente de escritorio o la aplicación móvil.</span><span class="sxs-lookup"><span data-stu-id="8d07f-194">If an unsupported browser version is detected, it will block access to the web interface and recommend that the user download the desktop client or mobile app.</span></span>

## <a name="mobile-clients"></a><span data-ttu-id="8d07f-195">Clientes móviles</span><span class="sxs-lookup"><span data-stu-id="8d07f-195">Mobile clients</span></span>

<span data-ttu-id="8d07f-196">Las aplicaciones móviles de Microsoft Teams están disponibles para iOS y Android, y están pensadas para que los usuarios que no están en un lugar fijo participen en conversaciones basadas en chat y para permitir las llamadas de audio de par a par.</span><span class="sxs-lookup"><span data-stu-id="8d07f-196">The Microsoft Teams mobile apps are available for Android and iOS, and are geared for on-the-go users participating in chat-based conversations and allow peer-to-peer audio calls.</span></span> <span data-ttu-id="8d07f-197">Para las aplicaciones móviles, vaya a la tienda móvil correspondiente: Google Play y App Store de Apple.</span><span class="sxs-lookup"><span data-stu-id="8d07f-197">For mobile apps, go to the relevant mobile stores Google Play and the Apple App Store.</span></span> <span data-ttu-id="8d07f-198">La aplicación de Windows Phone se retiró el 20 de julio de 2018 y podría dejar de funcionar.</span><span class="sxs-lookup"><span data-stu-id="8d07f-198">The Windows Phone App was retired July 20, 2018 and may no longer work.</span></span> 

<span data-ttu-id="8d07f-199">Aquí puede ver cómo [obtener Teams para Android](get-teams-android-in-china.md) en China.</span><span class="sxs-lookup"><span data-stu-id="8d07f-199">In China, here's how to [get Teams for Android](get-teams-android-in-china.md).</span></span> 

<span data-ttu-id="8d07f-200">Las siguientes son las plataformas móviles admitidas para Microsoft Teams:</span><span class="sxs-lookup"><span data-stu-id="8d07f-200">Supported mobile platforms for Microsoft Teams mobile apps are the following:</span></span>

-   <span data-ttu-id="8d07f-201">**Android**: la compatibilidad está limitada a las cuatro versiones principales más recientes de Android.</span><span class="sxs-lookup"><span data-stu-id="8d07f-201">**Android**: Support is limited to the last four major versions of Android.</span></span> <span data-ttu-id="8d07f-202">Cuando se publica una nueva versión principal de Android, se admiten oficialmente la nueva versión y las tres versiones anteriores.</span><span class="sxs-lookup"><span data-stu-id="8d07f-202">When a new major version of Android is released, the new version and the previous three versions are officially supported.</span></span>

-   <span data-ttu-id="8d07f-203">**iOS**: la compatibilidad está limitada a las dos versiones principales más recientes de iOS.</span><span class="sxs-lookup"><span data-stu-id="8d07f-203">**iOS**: Support is limited to the two most recent major versions of iOS.</span></span> <span data-ttu-id="8d07f-204">Cuando se publica una nueva versión principal de iOS, se admiten oficialmente la nueva versión y las tres versiones anteriores de iOS.</span><span class="sxs-lookup"><span data-stu-id="8d07f-204">When a new major version of iOS is released, the new version of iOS and the previous version are officially supported.</span></span>

> [!NOTE]
> <span data-ttu-id="8d07f-205">La versión móvil debe estar disponible para el público para que Teams funcione según lo esperado.</span><span class="sxs-lookup"><span data-stu-id="8d07f-205">The mobile version must be available to the public in order for Teams to work as expected.</span></span>

<span data-ttu-id="8d07f-206">Las aplicaciones móviles solamente se distribuyen y actualizan en la tienda de aplicaciones de la plataforma móvil correspondiente.</span><span class="sxs-lookup"><span data-stu-id="8d07f-206">Mobile apps are distributed and updated through the respective mobile platform’s app store only.</span></span> <span data-ttu-id="8d07f-207">Microsoft no admite la distribución de las aplicaciones móviles mediante MDM ni instalación de prueba.</span><span class="sxs-lookup"><span data-stu-id="8d07f-207">Distribution of the mobile apps via MDM or side-loading is not supported by Microsoft.</span></span> <span data-ttu-id="8d07f-208">Una vez que se haya instalado la aplicación móvil en una plataforma móvil compatible, se admitirá la aplicación móvil de Teams, siempre y cuando la versión se encuentre dentro de los tres meses siguientes a la versión actual.</span><span class="sxs-lookup"><span data-stu-id="8d07f-208">Once the mobile app has been installed on a supported mobile platform, the Teams Mobile App itself will be supported provided the version is within three months of the current release.</span></span>


| | | |
|---------|---------|---------|
|![Un icono que representa un punto de decisión](media/Get_clients_for_Microsoft_Teams_image4.png)      |<span data-ttu-id="8d07f-210">Punto de decisión</span><span class="sxs-lookup"><span data-stu-id="8d07f-210">Decision Point</span></span>         |<span data-ttu-id="8d07f-211">¿Hay alguna restricción que evite que los usuarios instalen el cliente de Microsoft Teams adecuado en sus dispositivos?</span><span class="sxs-lookup"><span data-stu-id="8d07f-211">Are there any restrictions preventing users from installing the appropriate Microsoft Teams client on their devices?</span></span>         |
|![Un icono que representa los siguientes pasos](media/Get_clients_for_Microsoft_Teams_image5.png)     |<span data-ttu-id="8d07f-213">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="8d07f-213">Next Steps</span></span>         |<span data-ttu-id="8d07f-p121">Si su organización restringe la instalación de software, asegúrese de que el proceso sea compatible con Microsoft Teams. Nota: No se requieren derechos de administrador para instalar el cliente en PC, pero sí son necesarios para Mac.</span><span class="sxs-lookup"><span data-stu-id="8d07f-p121">If your organization restricts software installation, make sure that process is compatible with Microsoft Teams. Note: Admin rights are not required for PC client installation but are required for installation on a Mac.</span></span>         |

## <a name="client-update-management"></a><span data-ttu-id="8d07f-216">Administración de actualizaciones del cliente</span><span class="sxs-lookup"><span data-stu-id="8d07f-216">Client update management</span></span>

<span data-ttu-id="8d07f-217">Actualmente, el servicio de Microsoft Teams actualiza automáticamente los clientes sin que sea necesaria la intervención de los administradores de TI.</span><span class="sxs-lookup"><span data-stu-id="8d07f-217">Clients are currently updated automatically by the Microsoft Teams service with no IT administrator intervention required.</span></span> <span data-ttu-id="8d07f-218">Si hay una actualización disponible, el cliente descargará automáticamente la actualización y, si la aplicación ha estado inactiva durante un período de tiempo, se iniciará el proceso de actualización.</span><span class="sxs-lookup"><span data-stu-id="8d07f-218">If an update is available, the client will automatically download the update and when the app has idled for a period of time, the update process will begin.</span></span>

## <a name="client-side-configurations"></a><span data-ttu-id="8d07f-219">Configuración del lado del cliente</span><span class="sxs-lookup"><span data-stu-id="8d07f-219">Client-side configurations</span></span>

<span data-ttu-id="8d07f-220">Actualmente, no hay opciones disponibles para configurar el cliente a través del administrador de inquilinos, PowerShell, Group Policy Objects ni el registro.</span><span class="sxs-lookup"><span data-stu-id="8d07f-220">Currently, there are no supported options available to configure the client either through the tenant admin, PowerShell, Group Policy Objects or the registry.</span></span>

## <a name="notification-settings"></a><span data-ttu-id="8d07f-221">Configuración de notificaciones</span><span class="sxs-lookup"><span data-stu-id="8d07f-221">Notification settings</span></span>

<span data-ttu-id="8d07f-p123">En este momento, no hay opciones disponibles para que los administradores de TI puedan configurar las notificaciones para los clientes. Todas las opciones de notificaciones las establece el usuario. En la siguiente figura se detalla la configuración predeterminada del cliente.</span><span class="sxs-lookup"><span data-stu-id="8d07f-p123">There are currently no options available for IT administrators to configure client-side notification settings. All notification options are set by the user. The figure below outlines the default client settings.</span></span>

![Captura de pantalla de la configuración de Notificaciones.](media/Get_clients_for_Microsoft_Teams_image6.png)

## <a name="sample-powershell-script---inbound-firewall-rule"></a><span data-ttu-id="8d07f-226">Script de PowerShell de ejemplo: regla de Firewall entrante</span><span class="sxs-lookup"><span data-stu-id="8d07f-226">Sample PowerShell script - inbound firewall rule</span></span>

<span data-ttu-id="8d07f-227">Este script de ejemplo, que tiene que ejecutarse en los equipos de cliente en el contexto de una cuenta de administrador con privilegios elevados, creará una nueva regla de firewall de entrada para cada carpeta de usuario que se encuentra en c:\users.</span><span class="sxs-lookup"><span data-stu-id="8d07f-227">This sample script, which needs to run on client computers in the context of an elevated administrator account, will create a new inbound firewall rule for each user folder found in c:\users.</span></span> <span data-ttu-id="8d07f-228">Cuando Teams encuentra esta regla, impedirá que la aplicación de Teams solicite a los usuarios crear reglas de firewall cuando los usuarios realicen su primera llamada de Teams.</span><span class="sxs-lookup"><span data-stu-id="8d07f-228">When Teams finds this rule, it will prevent the Teams application from prompting users to create firewall rules when the users make their first call from Teams.</span></span> 

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
