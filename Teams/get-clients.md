---
title: Obtener clientes para Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 07/05/2018
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: vichau, majafry
localization_priority: Priority
description: Aprenda a usar los distintos clientes disponibles para Microsoft Teams, que incluyen web, escritorio (Windows y Mac) y móvil (Android, iOS y Windows Phone).
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 083e45097c7f2495bb73dc51a64d25202fafc13b
ms.sourcegitcommit: 247747ec19c0f5c1d45fea7e5ac5318e4d5127ea
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/02/2018
ms.locfileid: "21708363"
---
<a name="get-clients-for-microsoft-teams"></a><span data-ttu-id="24205-103">Obtener clientes para Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="24205-103">Get clients for Microsoft Teams</span></span> 
===========================

<span data-ttu-id="24205-104">Microsoft Teams tiene los clientes disponibles para escritorio web (Windows y Mac) y para dispositivos móviles (Android, iOS y Windows Phone).</span><span class="sxs-lookup"><span data-stu-id="24205-104">Microsoft Teams has clients available for desktop (Windows and Mac), web, and mobile (Android,  iOS, and Windows Phone).</span></span> <span data-ttu-id="24205-105">Todos estos clientes requieren una conexión a Internet activa y no admiten el modo sin conexión.</span><span class="sxs-lookup"><span data-stu-id="24205-105">These clients all require an active internet connection and do not support an offline mode.</span></span>

<a name="desktop-client"></a><span data-ttu-id="24205-106">Cliente de escritorio</span><span class="sxs-lookup"><span data-stu-id="24205-106">Desktop client</span></span>
--------------

<span data-ttu-id="24205-107">El cliente de escritorio de Microsoft Teams es una aplicación independiente y actualmente no forma parte de Office 365 ProPlus.</span><span class="sxs-lookup"><span data-stu-id="24205-107">The Microsoft Teams desktop client is a standalone application and currently not part of Office 365 ProPlus.</span></span> <span data-ttu-id="24205-108">Los equipos está disponible para Windows (7 +), versiones de 32 bits y 64 bits y Mac OS (10.10 +).</span><span class="sxs-lookup"><span data-stu-id="24205-108">Teams is available for both Windows (7+), both 32-bit and 64-bit versions, and macOS (10.10+).</span></span> <span data-ttu-id="24205-109">En Windows, los equipos requiere .NET framework 4.5 o posterior; el programa de instalación de los equipos ofrecerá a instalarlo automáticamente si no lo tiene.</span><span class="sxs-lookup"><span data-stu-id="24205-109">On Windows, Teams requires .NET framework 4.5 or later; the Teams installer will offer to install it for you if you don't have it.</span></span> 

<span data-ttu-id="24205-110">Los clientes de escritorio proporcionan compatibilidad con las comunicaciones en tiempo real (audio, vídeo y contenido de uso compartido) para las reuniones de equipo, grupo realiza la llamada y privada proporcionó las llamadas.</span><span class="sxs-lookup"><span data-stu-id="24205-110">The desktop clients provide real-time communications support (audio, video, and content sharing) for team meetings, group calling, and private one-on-one calls.</span></span>

<span data-ttu-id="24205-111">Los clientes de escritorio pueden ser descargados e instalados por los usuarios finales directamente desde [https://teams.microsoft.com/downloads](https://go.microsoft.com/fwlink/?linkid=855754) si tienen los permisos adecuados locales (derechos de administrador no son necesarios para instalar el cliente de los equipos en un PC pero se requieren en un Mac).</span><span class="sxs-lookup"><span data-stu-id="24205-111">Desktop clients can be downloaded and installed by end users directly from [https://teams.microsoft.com/downloads](https://go.microsoft.com/fwlink/?linkid=855754) if they have the appropriate local permissions (admin rights are not required to install the Teams client on a PC but are required on a Mac).</span></span>

<span data-ttu-id="24205-112">Los administradores de TI pueden elegir su método preferido para distribuir los archivos de instalación en los equipos de su organización, como System Center Configuration Manager (Windows) o Jamf Pro (Mac OS).</span><span class="sxs-lookup"><span data-stu-id="24205-112">IT admins can choose their preferred method to distribute the installation files to computers in their organization, such as System Center Configuration Manager (Windows) or Jamf Pro (macOS).</span></span> <span data-ttu-id="24205-113">Para obtener el paquete de MSI para la distribución de Windows, vea [instalar los equipos de Microsoft con MSI](msi-deployment.md).</span><span class="sxs-lookup"><span data-stu-id="24205-113">To get the MSI package for Windows distribution, see [Install Microsoft Teams using MSI](msi-deployment.md).</span></span>

> [!NOTE]
> <span data-ttu-id="24205-114">La distribución del cliente a través de estos mecanismos es solo para la instalación inicial de los clientes de Microsoft Teams y no para futuras actualizaciones.</span><span class="sxs-lookup"><span data-stu-id="24205-114">Distribution of the client via these mechanisms is only for the initial installation of Microsoft Team clients and not for future updates.</span></span>

### <a name="windows"></a><span data-ttu-id="24205-115">Windows</span><span class="sxs-lookup"><span data-stu-id="24205-115">Windows</span></span>

<span data-ttu-id="24205-116">La instalación de Microsoft Teams para Windows proporciona a instaladores que se pueden descargar en la arquitectura de 32 bits y 64 bits.</span><span class="sxs-lookup"><span data-stu-id="24205-116">The Microsoft Teams installation for Windows provides downloadable installers in 32-bit and 64-bit architecture.</span></span>

> [!NOTE]
> <span data-ttu-id="24205-117">La arquitectura (32 bits frente a 64 bits) de Microsoft Teams es independiente de la arquitectura de Windows y Office que está instalado.</span><span class="sxs-lookup"><span data-stu-id="24205-117">The architecture (32-bit vs. 64-bit) of Microsoft Teams is agnostic to the architecture of Windows and Office that is installed.</span></span>

<span data-ttu-id="24205-p104">El cliente de Windows se implementa en la carpeta AppData ubicada en el perfil del usuario. La implementación en el perfil local del usuario permite instalar el cliente sin que se requieran derechos elevados. El cliente de Windows se instala en las siguientes ubicaciones:</span><span class="sxs-lookup"><span data-stu-id="24205-p104">The Windows client is deployed to the AppData folder located in the user’s profile. Deploying to the user’s local profile allows the client to be installed without requiring elevated rights. The Windows client is installed in the following locations:</span></span>

- <span data-ttu-id="24205-121">%appdata%\\local\\Microsoft\\Teams</span><span class="sxs-lookup"><span data-stu-id="24205-121">%appdata%\\local\\Microsoft\\Teams</span></span>

- <span data-ttu-id="24205-122">%appdata%\\roaming\\Microsoft\\Teams</span><span class="sxs-lookup"><span data-stu-id="24205-122">%appdata%\\roaming\\Microsoft\\Teams</span></span>

<span data-ttu-id="24205-123">Cuando los usuarios inician una llamada mediante el cliente de Microsoft Teams por primera vez, es posible que observe el una advertencia con la configuración de firewall de Windows que se pregunta a los usuarios permitir la comunicación.</span><span class="sxs-lookup"><span data-stu-id="24205-123">When users initiate a call using the Microsoft Teams client for the first time, they might notice a warning with the Windows firewall settings that asks for users to allow communication.</span></span> <span data-ttu-id="24205-124">Los usuarios que se le indique para omitir este mensaje debido a que funcione la llamada, incluso cuando se descarta la advertencia.</span><span class="sxs-lookup"><span data-stu-id="24205-124">Users might be instructed to ignore this message because the call will work, even when the warning is dismissed.</span></span>

![Captura de pantalla de un cuadro de diálogo Alerta de seguridad de Windows.](media/Get_clients_for_Microsoft_Teams_image3.png)

> [!NOTE]
> <span data-ttu-id="24205-p106">La configuración del firewall de Windows se modificará incluso si el mensaje se descarta seleccionando "Cancelar". Se crearán dos reglas de entrada para teams.exe con la acción de bloqueo para los protocolos TCP y UDP.</span><span class="sxs-lookup"><span data-stu-id="24205-p106">Windows Firewall configuration will be altered even when the prompt is dismissed by selecting “Cancel”. Two inbound rules for teams.exe will be created with Block action for both TCP and UDP protocols.</span></span>

### <a name="mac"></a><span data-ttu-id="24205-128">Mac</span><span class="sxs-lookup"><span data-stu-id="24205-128">Mac</span></span>

<span data-ttu-id="24205-129">Los usuarios de Mac pueden instalar los equipos mediante un archivo de instalación del paquete para Mac OS equipos.</span><span class="sxs-lookup"><span data-stu-id="24205-129">Mac users can install Teams by using a PKG installation file for macOS computers.</span></span> <span data-ttu-id="24205-130">Se requiere acceso de administrador para instalar el cliente de Mac.</span><span class="sxs-lookup"><span data-stu-id="24205-130">Administrative access is required to install the Mac client.</span></span> <span data-ttu-id="24205-131">El cliente de Mac OS está instalado en la carpeta /Applications.</span><span class="sxs-lookup"><span data-stu-id="24205-131">The macOS client is installed to the /Applications folder.</span></span>

#### <a name="install-teams-by-using-the-pkg-file"></a><span data-ttu-id="24205-132">Instalación de los equipos mediante el archivo de paquete</span><span class="sxs-lookup"><span data-stu-id="24205-132">Install Teams by using the PKG file</span></span>

1. <span data-ttu-id="24205-133">Desde la [página de descarga de los equipos](https://teams.microsoft.com/downloads), en **Mac**, haga clic en **Descargar**.</span><span class="sxs-lookup"><span data-stu-id="24205-133">From the [Teams download page](https://teams.microsoft.com/downloads), under **Mac**, click **Download**.</span></span>
2. <span data-ttu-id="24205-134">Haga doble clic en el archivo de paquete.</span><span class="sxs-lookup"><span data-stu-id="24205-134">Double click the PKG file.</span></span>
3. <span data-ttu-id="24205-135">Siga el Asistente para instalación para completar la instalación.</span><span class="sxs-lookup"><span data-stu-id="24205-135">Follow the installation wizard to complete the installation.</span></span>
4. <span data-ttu-id="24205-136">Los equipos se instalará en la carpeta /Applications.</span><span class="sxs-lookup"><span data-stu-id="24205-136">Teams will be installed to /Applications folder.</span></span> <span data-ttu-id="24205-137">Se trata de una instalación de todo el equipo.</span><span class="sxs-lookup"><span data-stu-id="24205-137">It is a machine-wide installation.</span></span>

> [!NOTE]
> <span data-ttu-id="24205-138">Durante la instalación, el paquete solicitará las credenciales de administrador.</span><span class="sxs-lookup"><span data-stu-id="24205-138">During the installation, the PKG will prompt for admin credentials.</span></span> <span data-ttu-id="24205-139">El usuario debe escribir las credenciales de administrador, independientemente de si el usuario es un administrador.</span><span class="sxs-lookup"><span data-stu-id="24205-139">The user needs to enter the admin credentials, regardless of whether or not the user is an admin.</span></span>

<span data-ttu-id="24205-140">Si un usuario tiene una instalación de dmg para de los equipos y desea reemplazar con la instalación del paquete actualmente, el usuario debe:</span><span class="sxs-lookup"><span data-stu-id="24205-140">If a user currently has a DMG installation of Teams and wants to replace it with the PKG installation, the user should:</span></span>

1. <span data-ttu-id="24205-141">Salga de la aplicación de los equipos.</span><span class="sxs-lookup"><span data-stu-id="24205-141">Exit the Teams app.</span></span>
2. <span data-ttu-id="24205-142">Desinstalación de la aplicación de los equipos.</span><span class="sxs-lookup"><span data-stu-id="24205-142">Uninstall the Teams app.</span></span>
3. <span data-ttu-id="24205-143">Instalar el archivo de paquete.</span><span class="sxs-lookup"><span data-stu-id="24205-143">Install the PKG file.</span></span>

<span data-ttu-id="24205-144">Los administradores de TI pueden utilizar implementación administrada de los equipos para distribuir los archivos de instalación a todos los equipos Mac en su organización, como Jamf Pro.</span><span class="sxs-lookup"><span data-stu-id="24205-144">IT admins can use managed deployment of Teams to distribute the installation files to all Macs in their organization, such as Jamf Pro.</span></span>

> [!NOTE]
> <span data-ttu-id="24205-145">Si experimenta problemas al instalar el paquete, háganoslo saber.</span><span class="sxs-lookup"><span data-stu-id="24205-145">If you experience issues installing the PKG, let us know.</span></span> <span data-ttu-id="24205-146">En la sección de **comentarios** al final de este artículo, haga clic en **comentarios sobre el producto**.</span><span class="sxs-lookup"><span data-stu-id="24205-146">In the **Feedback** section at the end of this article, click **Product feedback**.</span></span>

<a name="web-client"></a><span data-ttu-id="24205-147">Cliente web</span><span class="sxs-lookup"><span data-stu-id="24205-147">Web client</span></span> 
----------

<span data-ttu-id="24205-148">El cliente web ([https://teams.microsoft.com](https://go.microsoft.com/fwlink/?linkid=855753)) es un cliente completo, funcional que se puede usar desde una variedad de exploradores.</span><span class="sxs-lookup"><span data-stu-id="24205-148">The web client ([https://teams.microsoft.com](https://go.microsoft.com/fwlink/?linkid=855753)) is a full, functional client that can be used from a variety of browsers.</span></span> <span data-ttu-id="24205-149">El cliente web admite llamadas y reuniones mediante webRTC, por lo que hay no complemento o descargar necesarios para ejecutar los equipos en un explorador web.</span><span class="sxs-lookup"><span data-stu-id="24205-149">The web client supports Calling and Meetings by using webRTC, so there is no plug-in or download required to run Teams in a web browser.</span></span> <span data-ttu-id="24205-150">El explorador debe configurarse para permitir que las cookies de terceros.</span><span class="sxs-lookup"><span data-stu-id="24205-150">The browser must be configured to allow third-party cookies.</span></span> 

[!INCLUDE [browser-support](includes/browser-support.md)]

<span data-ttu-id="24205-151">El cliente web realiza la detección de versión de explorador al conectarse a [https://teams.microsoft.com](https://go.microsoft.com/fwlink/?linkid=855753).</span><span class="sxs-lookup"><span data-stu-id="24205-151">The web client performs browser version detection upon connecting to [https://teams.microsoft.com](https://go.microsoft.com/fwlink/?linkid=855753).</span></span> <span data-ttu-id="24205-152">Si se detecta una versión de explorador incompatible, se bloquee el acceso a la interfaz web y se recomienda que el usuario descargue el cliente de escritorio o una aplicación móvil.</span><span class="sxs-lookup"><span data-stu-id="24205-152">If an unsupported browser version is detected, it will block access to the web interface and recommend that the user download the desktop client or mobile app.</span></span>

<a name="mobile-clients"></a><span data-ttu-id="24205-153">Clientes móviles</span><span class="sxs-lookup"><span data-stu-id="24205-153">Mobile clients</span></span>
--------------

<span data-ttu-id="24205-p113">Las aplicaciones móviles de Microsoft Teams están disponibles para Android, iOS y Windows Phone, y están pensadas para que los usuarios que no están en un lugar fijo participen en conversaciones basadas en chat y para permitir las llamadas de audio de par a par. Para las aplicaciones móviles, vaya a la tienda móvil correspondiente: Google Play, App Store de Apple o Microsoft Store.</span><span class="sxs-lookup"><span data-stu-id="24205-p113">The Microsoft Teams mobile apps are available for Android, iOS, and Windows Phones, and are geared for on-the-go users participating in chat-based conversations and allow peer-to-peer audio calls. For mobile apps, go to the relevant mobile store for Google Play, Apple App Store, and Microsoft Store.</span></span>

<span data-ttu-id="24205-156">Las siguientes son las plataformas móviles admitidas para Microsoft Teams:</span><span class="sxs-lookup"><span data-stu-id="24205-156">Supported mobile platforms for Microsoft Teams mobile apps are the following:</span></span>

-   <span data-ttu-id="24205-157">**Android** 4.4 o posterior</span><span class="sxs-lookup"><span data-stu-id="24205-157">**Android**: 4.4 or later</span></span>

-   <span data-ttu-id="24205-158">**iOS**: 10.0 o posterior</span><span class="sxs-lookup"><span data-stu-id="24205-158">**iOS**: 10.0 or later</span></span>

-   <span data-ttu-id="24205-159">**Windows Phone**: Windows 10 Mobile</span><span class="sxs-lookup"><span data-stu-id="24205-159">**Windows Phone**: Windows 10 Mobile</span></span>

> [!NOTE]
> <span data-ttu-id="24205-160">La versión móvil debe estar disponible al público en orden para los equipos para que funcione como se esperaba.</span><span class="sxs-lookup"><span data-stu-id="24205-160">The mobile version must be available to the public in order for Teams to work as expected.</span></span>

<span data-ttu-id="24205-161">Las aplicaciones móviles se distribuyen y actualizan solo a través de la correspondiente tienda de aplicaciones para la plataforma móvil y no están disponibles para su distribución a través de soluciones de administración de dispositivos móviles (MDM) o de transferencia local.</span><span class="sxs-lookup"><span data-stu-id="24205-161">Mobile apps are distributed and updated through the respective mobile platform’s app store only, and are not available to be distributed through MDM (mobile device management) solutions or side-loaded.</span></span>


| | | |
|---------|---------|---------|
|![Icono de Punto de decisión.](media/Get_clients_for_Microsoft_Teams_image4.png)      |<span data-ttu-id="24205-163">Punto de decisión</span><span class="sxs-lookup"><span data-stu-id="24205-163">Decision Point</span></span>         |<span data-ttu-id="24205-164">¿Hay alguna restricción que evite que los usuarios instalen el cliente de Microsoft Teams adecuado en sus dispositivos?</span><span class="sxs-lookup"><span data-stu-id="24205-164">Are there any restrictions preventing users from installing the appropriate Microsoft Teams client on their devices?</span></span>         |
|![Icono de Siguientes pasos.](media/Get_clients_for_Microsoft_Teams_image5.png)     |<span data-ttu-id="24205-166">Siguientes pasos</span><span class="sxs-lookup"><span data-stu-id="24205-166">Next Steps</span></span>         |<span data-ttu-id="24205-p114">Si su organización restringe la instalación de software, asegúrese de que el proceso sea compatible con Microsoft Teams. Nota: No se requieren derechos de administrador para instalar el cliente en PC, pero sí son necesarios para Mac.</span><span class="sxs-lookup"><span data-stu-id="24205-p114">If your organization restricts software installation, make sure that process is compatible with Microsoft Teams. Note: Admin rights are not required for PC client installation but are required for installation on a Mac.</span></span>         |


  <span data-ttu-id="24205-169"><span id="_Hlk477176062" class="anchor"></span>  Punto de decisión   ¿Hay alguna restricción que evite que los usuarios instalen el cliente de Microsoft Teams adecuado en sus dispositivos?</span><span class="sxs-lookup"><span data-stu-id="24205-169"><span id="_Hlk477176062" class="anchor"></span>  Decision Point   Are there any restrictions preventing users from installing the appropriate Microsoft Teams client on their devices?</span></span>

<a name="client-update-management"></a><span data-ttu-id="24205-170">Administración de actualizaciones del cliente</span><span class="sxs-lookup"><span data-stu-id="24205-170">Client update management</span></span>
------------------------

<span data-ttu-id="24205-p115">Actualmente, el servicio de Microsoft Teams actualiza los clientes en forma automática, sin que se necesite la intervención del administrador de TI. Si hay una actualización disponible, el cliente descargará automáticamente la actualización y, cuando la aplicación esté inactiva durante un tiempo, comenzará el proceso de actualización.</span><span class="sxs-lookup"><span data-stu-id="24205-p115">Clients are currently updated automatically by the Microsoft Teams service with no IT administrator intervention required. If an update is available, the client will automatically download the update and when the app has idled for a period of time, the update process will kick off.</span></span>

<a name="client-side-configurations"></a><span data-ttu-id="24205-173">Configuración del lado del cliente</span><span class="sxs-lookup"><span data-stu-id="24205-173">Client-side configurations</span></span>
---------------------------

<span data-ttu-id="24205-174">Actualmente, no hay opciones disponibles para configurar el cliente a través del administrador de inquilinos, PowerShell, Group Policy Objects ni el registro.</span><span class="sxs-lookup"><span data-stu-id="24205-174">Currently, there are no supported options available to configure the client either through the tenant admin, PowerShell, Group Policy Objects or the registry.</span></span>

<a name="notification-settings"></a><span data-ttu-id="24205-175">Configuración de notificaciones</span><span class="sxs-lookup"><span data-stu-id="24205-175">Notification settings</span></span>
----------------------------

<span data-ttu-id="24205-p116">En este momento, no hay opciones disponibles para que los administradores de TI puedan configurar las notificaciones para los clientes. Todas las opciones de notificaciones las establece el usuario. En la siguiente figura se detalla la configuración predeterminada del cliente.</span><span class="sxs-lookup"><span data-stu-id="24205-p116">There are currently no options available for IT administrators to configure client-side notification settings. All notification options are set by the user. The figure below outlines the default client settings.</span></span>

![Captura de pantalla de la configuración de Notificaciones.](media/Get_clients_for_Microsoft_Teams_image6.png)
