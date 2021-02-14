---
title: Implementar salas de Microsoft Teams con Microsoft Endpoint Configuration Manager
author: dstrome
ms.author: dstrome
ms.reviewer: Turgayo
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.custom:
- Strat_SB_Admin
- seo-marvel-apr2020
ms.assetid: 678689e4-d547-499b-be64-7d8f16dd8668
ms.collection:
- M365-collaboration
description: Obtenga información sobre cómo implementar salas de Microsoft Teams en implementaciones a gran escala con Microsoft Endpoint Configuration Manager.
no-loc:
- Microsoft
- Microsoft Corporation
- Microsoft Teams Rooms
- Microsoft Teams Room
- System Center
- Configuration Manager
- Windows
- Surface
- Surface Pro
- Windows PE
- Windows 10
- Windows 10 Enterprise
- Azure
- Azure Monitor
- Log Analytics
- Operations Management Suite
ms.openlocfilehash: 1d8fc0090264a7a39051cfedb9c3584a08e3ebb9
ms.sourcegitcommit: 975f81d9e595dfb339550625d7cef8ad84449e20
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662425"
---
# <a name="deploy-microsoft-teams-rooms-by-using-microsoft-endpoint-configuration-manager"></a><span data-ttu-id="8bc24-103">Implementar salas de Microsoft Teams con Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="8bc24-103">Deploy Microsoft Teams Rooms by using Microsoft Endpoint Configuration Manager</span></span>

<span data-ttu-id="8bc24-104">En este artículo se proporciona toda la información necesaria para crear las implementaciones de Microsoft Teams Rooms con Microsoft Endpoint Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="8bc24-104">This article gives you all the necessary information to create your Microsoft Teams Rooms deployments by using Microsoft Endpoint Configuration Manager.</span></span>

<span data-ttu-id="8bc24-105">Con los métodos fáciles de usar proporcionados por Configuration Manager, puede implementar el sistema operativo y otras aplicaciones en varios dispositivos de destino.</span><span class="sxs-lookup"><span data-stu-id="8bc24-105">With the easy-to-use methods provided by Configuration Manager, you can deploy the operating system and other applications to multiple target devices.</span></span>

<span data-ttu-id="8bc24-106">Use el método que se muestra a continuación para guiarlo a través de la configuración de Configuration Manager y personalizar los paquetes y scripts de ejemplo proporcionados a lo largo de esta guía según sea necesario para su organización.</span><span class="sxs-lookup"><span data-stu-id="8bc24-106">Use the approach illustrated below to guide you through your Configuration Manager configuration, and customize the sample packages and scripts provided throughout this guidance as needed for your organization.</span></span>

![Proceso de implementación de salas de Microsoft Teams con Configuration Manager](../media/room-systems-scale-image1.png)

> [!IMPORTANT]
> <span data-ttu-id="8bc24-108">Esta solución solo se ha probado con implementaciones basadas en Surface Pro.</span><span class="sxs-lookup"><span data-stu-id="8bc24-108">This solution has only been tested with Surface Pro–based deployments.</span></span> <span data-ttu-id="8bc24-109">Sigue las instrucciones del fabricante para las configuraciones que no están basadas en Surface Pro.</span><span class="sxs-lookup"><span data-stu-id="8bc24-109">Follow the manufacturer's guidelines for configurations that aren't based on Surface Pro.</span></span>

## <a name="validate-prerequisites"></a><span data-ttu-id="8bc24-110">Validar requisitos previos</span><span class="sxs-lookup"><span data-stu-id="8bc24-110">Validate prerequisites</span></span>

<span data-ttu-id="8bc24-111">Para implementar salas de Microsoft Teams con Configuration Manager, asegúrese de que cumple los siguientes requisitos previos y requisitos.</span><span class="sxs-lookup"><span data-stu-id="8bc24-111">To deploy Microsoft Teams Rooms with Configuration Manager, ensure that you meet the following prerequisites and requirements.</span></span>

### <a name="microsoft-endpoint-configuration-manager-requirements"></a><span data-ttu-id="8bc24-112">Requisitos de Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="8bc24-112">Microsoft Endpoint Configuration Manager requirements</span></span>

-   <span data-ttu-id="8bc24-113">La versión de Microsoft Endpoint Configuration Manager debe ser de al menos 1706 o superior.</span><span class="sxs-lookup"><span data-stu-id="8bc24-113">Microsoft Endpoint Configuration Manager version must be at least 1706 or above.</span></span> <span data-ttu-id="8bc24-114">Se recomienda usar 1710 o posterior.</span><span class="sxs-lookup"><span data-stu-id="8bc24-114">We recommend using 1710 or later.</span></span> <span data-ttu-id="8bc24-115">Consulte la [compatibilidad con Windows 10 en Configuration Manager](https://docs.microsoft.com/configmgr/core/plan-design/configs/support-for-windows-10#windows-10-as-a-client) para obtener información sobre las versiones de Windows 10 que admite Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="8bc24-115">Check out [Support for Windows 10 in Configuration Manager](https://docs.microsoft.com/configmgr/core/plan-design/configs/support-for-windows-10#windows-10-as-a-client) to learn about the Windows 10 versions that Configuration Manager supports.</span></span>

-   <span data-ttu-id="8bc24-116">Es necesario instalar una versión compatible del Kit de implementación y evaluación de Windows (ADK) para Windows 10.</span><span class="sxs-lookup"><span data-stu-id="8bc24-116">A supported version of Windows Assessment and Deployment Kit (ADK) for Windows 10 must be installed.</span></span> <span data-ttu-id="8bc24-117">Consulta las versiones del [ADK de Windows 10](https://docs.microsoft.com/configmgr/core/plan-design/configs/support-for-windows-10#windows-10-adk) que puedes usar con diferentes versiones de Configuration Manager y asegúrate de que la implementación incluye la versión correcta.</span><span class="sxs-lookup"><span data-stu-id="8bc24-117">See the versions of the [Windows 10 ADK](https://docs.microsoft.com/configmgr/core/plan-design/configs/support-for-windows-10#windows-10-adk) that you can use with different versions of Configuration Manager, and ensure that your deployment includes the correct version.</span></span>

-   <span data-ttu-id="8bc24-118">Los servidores del sistema del sitio deben tener asignado el rol de punto de distribución y las imágenes de arranque deben habilitarse para la compatibilidad con el entorno de ejecución [preboot (PXE)](https://docs.microsoft.com/configmgr/osd/deploy-use/use-pxe-to-deploy-windows-over-the-network) para habilitar implementaciones iniciadas por la red.</span><span class="sxs-lookup"><span data-stu-id="8bc24-118">The site system servers must have been assigned the distribution point role, and the boot images should be enabled for [preboot execution environment (PXE) support](https://docs.microsoft.com/configmgr/osd/deploy-use/use-pxe-to-deploy-windows-over-the-network) to enable network-initiated deployments.</span></span> <span data-ttu-id="8bc24-119">Si la compatibilidad con PXE no está habilitada, puede usar medios [de arranque](https://docs.microsoft.com/configmgr/osd/deploy-use/use-bootable-media-to-deploy-windows-over-the-network) para las implementaciones.</span><span class="sxs-lookup"><span data-stu-id="8bc24-119">If PXE support isn't enabled, you can use [bootable media](https://docs.microsoft.com/configmgr/osd/deploy-use/use-bootable-media-to-deploy-windows-over-the-network) for your deployments.</span></span>

-   <span data-ttu-id="8bc24-120">Es necesario configurar una cuenta de acceso a la red para que admita nuevos escenarios de implementación en equipos (metálicos vacíos).</span><span class="sxs-lookup"><span data-stu-id="8bc24-120">A network access account must be configured to support new computer (bare metal) deployment scenarios.</span></span> <span data-ttu-id="8bc24-121">Para obtener más información sobre la configuración de una cuenta de acceso de red, vea [Cuentas usadas en Configuration Manager.](https://docs.microsoft.com/configmgr/core/plan-design/hierarchy/manage-accounts-to-access-content#bkmk_NAA)</span><span class="sxs-lookup"><span data-stu-id="8bc24-121">To learn more about the configuration of a network access account, see [Accounts used in Configuration Manager](https://docs.microsoft.com/configmgr/core/plan-design/hierarchy/manage-accounts-to-access-content#bkmk_NAA).</span></span>

-   <span data-ttu-id="8bc24-122">Le recomendamos que habilite [el](https://docs.microsoft.com/configmgr/osd/deploy-use/use-multicast-to-deploy-windows-over-the-network)soporte técnico técnico, si es probable que implemente la misma imagen de Microsoft Teams Rooms en varias unidades al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="8bc24-122">We recommend that you enable [multicast support](https://docs.microsoft.com/configmgr/osd/deploy-use/use-multicast-to-deploy-windows-over-the-network), if you're likely to deploy the same Microsoft Teams Rooms image to multiple units at the same time.</span></span>

### <a name="networking-requirements"></a><span data-ttu-id="8bc24-123">Requisitos de redes</span><span class="sxs-lookup"><span data-stu-id="8bc24-123">Networking requirements</span></span>

-   <span data-ttu-id="8bc24-124">La red debe tener un servidor de Protocolo de configuración de host dinámico (KERBEROS) configurado para la distribución automática de direcciones IP a las subredes donde se implementarán las unidades de Salas de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="8bc24-124">Your network should have a Dynamic Host Configuration Protocol (DHCP) server, configured for automatic IP address distribution to the subnets where Microsoft Teams Rooms units will be deployed.</span></span>

    > [!NOTE]
    > <span data-ttu-id="8bc24-125">La duración de la concesión de BOOLEAN debe establecerse en un valor superior a la duración de la implementación de imágenes.</span><span class="sxs-lookup"><span data-stu-id="8bc24-125">DHCP lease duration must be set to a value longer than the image deployment duration.</span></span> <span data-ttu-id="8bc24-126">En caso contrario, puede producirse un error en la implementación.</span><span class="sxs-lookup"><span data-stu-id="8bc24-126">Otherwise, the deployment might fail.</span></span>

-   <span data-ttu-id="8bc24-127">La red, incluidos los conmutadores y las laN virtuales (VLANs), debe configurarse para que admita PXE.</span><span class="sxs-lookup"><span data-stu-id="8bc24-127">Your network, including switches and virtual LANs (VLANs), should be configured to support PXE.</span></span> <span data-ttu-id="8bc24-128">Consulte a su proveedor de red para obtener más información sobre la configuración de IP Helper y PXE.</span><span class="sxs-lookup"><span data-stu-id="8bc24-128">Refer to your network vendor for more information about IP Helper and PXE configuration.</span></span> <span data-ttu-id="8bc24-129">Como alternativa, puede usar medios [de arranque](https://docs.microsoft.com/configmgr/osd/deploy-use/use-bootable-media-to-deploy-windows-over-the-network) para las implementaciones, si la compatibilidad con PXE no está habilitada.</span><span class="sxs-lookup"><span data-stu-id="8bc24-129">Alternatively, you can use [bootable media](https://docs.microsoft.com/configmgr/osd/deploy-use/use-bootable-media-to-deploy-windows-over-the-network) for your deployments, if PXE support isn't enabled.</span></span>

    > [!NOTE]
    > <span data-ttu-id="8bc24-130">Para dispositivos Surface Pro, solo se admite el inicio desde la red (arranque PXE) cuando se usa un adaptador Ethernet o una estación de acoplamiento de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="8bc24-130">For Surface Pro devices, booting from the network (PXE boot) is only supported when you use an Ethernet adapter or docking station from Microsoft.</span></span> <span data-ttu-id="8bc24-131">Los adaptadores de Ethernet de terceros no admiten el arranque PXE con Surface Pro.</span><span class="sxs-lookup"><span data-stu-id="8bc24-131">Third-party Ethernet adapters don't support PXE boot with Surface Pro.</span></span> <span data-ttu-id="8bc24-132">Para [obtener más información, consulta adaptadores de Ethernet](https://docs.microsoft.com/surface/ethernet-adapters-and-surface-device-deployment) e implementación de Surface.</span><span class="sxs-lookup"><span data-stu-id="8bc24-132">See [Ethernet adapters and Surface deployment](https://docs.microsoft.com/surface/ethernet-adapters-and-surface-device-deployment) for more information.</span></span>

## <a name="configure-microsoft-endpoint-configuration-manager-for-operating-system-deployment"></a><span data-ttu-id="8bc24-133">Configurar Microsoft Endpoint Configuration Manager para la implementación de sistemas operativos</span><span class="sxs-lookup"><span data-stu-id="8bc24-133">Configure Microsoft Endpoint Configuration Manager for operating system deployment</span></span>

<span data-ttu-id="8bc24-134">En este artículo se supone que ya tiene una implementación correcta de Configuration Manager y no detalla todos los pasos necesarios para implementar y configurar Configuration Manager desde cero.</span><span class="sxs-lookup"><span data-stu-id="8bc24-134">This article assumes you already have a healthy Configuration Manager deployment, and doesn't detail all the steps required to deploy and configure Configuration Manager from scratch.</span></span> <span data-ttu-id="8bc24-135">La [documentación y las instrucciones de configuración](https://docs.microsoft.com/configmgr/) de Microsoft Endpoint Configuration Manager son un gran recurso; le recomendamos que empiece con estos recursos si aún no ha implementado Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="8bc24-135">The [documentation and the configuration guidance](https://docs.microsoft.com/configmgr/) on the Microsoft Endpoint Configuration Manager is a great resource; we recommend you start with these resources if you haven't yet deployed Configuration Manager.</span></span>

<span data-ttu-id="8bc24-136">Use las siguientes instrucciones para comprobar que las características de implementación de sistema operativo (OSD) están configuradas correctamente.</span><span class="sxs-lookup"><span data-stu-id="8bc24-136">Use the following instructions to verify that the operating system deployment (OSD) features are configured properly.</span></span>

### <a name="validate-and-upgrade-configuration-manager"></a><span data-ttu-id="8bc24-137">Validar y actualizar Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="8bc24-137">Validate and upgrade Configuration Manager</span></span>

1.  <span data-ttu-id="8bc24-138">En la consola de Configuration Manager, vaya **a Actualizaciones** y mantenimiento \> **de administración.**</span><span class="sxs-lookup"><span data-stu-id="8bc24-138">In the Configuration Manager console, go to **Administration** \> **Updates and Servicing**.</span></span>

2.  <span data-ttu-id="8bc24-139">Compruebe la compilación instalada y las actualizaciones aplicables que aún no se han instalado.</span><span class="sxs-lookup"><span data-stu-id="8bc24-139">Check the installed build and applicable updates that haven't been installed yet.</span></span>

3.  <span data-ttu-id="8bc24-140">Revise [la compatibilidad con Windows 10 en Configuration Manager;](https://docs.microsoft.com/configmgr/core/plan-design/configs/support-for-windows-10#windows-10-as-a-client) si necesita actualizar la implementación, seleccione la actualización que desea instalar y, a continuación, seleccione **Descargar.**</span><span class="sxs-lookup"><span data-stu-id="8bc24-140">Review [Support for Windows 10 in Configuration Manager](https://docs.microsoft.com/configmgr/core/plan-design/configs/support-for-windows-10#windows-10-as-a-client); if you need to upgrade your deployment, select the update you want to install, and then select **Download**.</span></span>

4.  <span data-ttu-id="8bc24-141">Una vez completada la descarga, seleccione la actualización y, después, **instale el paquete de actualización.**</span><span class="sxs-lookup"><span data-stu-id="8bc24-141">After the download is complete, select the update, and then select **Install Update Pack**.</span></span>

### <a name="configure-distribution-points-to-support-pxe-and-multicast"></a><span data-ttu-id="8bc24-142">Configurar puntos de distribución para que admitan PXE y grupos</span><span class="sxs-lookup"><span data-stu-id="8bc24-142">Configure distribution points to support PXE and multicast</span></span>

1.  <span data-ttu-id="8bc24-143">En la consola de Configuration Manager, vaya a Puntos **de distribución** \> **de administración.**</span><span class="sxs-lookup"><span data-stu-id="8bc24-143">In the Configuration Manager console, go to **Administration** \> **Distribution Points**.</span></span>

2.  <span data-ttu-id="8bc24-144">Seleccione el servidor de punto de distribución que va a servir a la implementación de salas de Microsoft Teams y, a continuación, **seleccione Propiedades.**</span><span class="sxs-lookup"><span data-stu-id="8bc24-144">Select the distribution point server that will serve the Microsoft Teams Rooms deployment, and then select **Properties**.</span></span>

3.  <span data-ttu-id="8bc24-145">Seleccione la **pestaña PXE** y asegúrese de que la siguiente configuración está habilitada:</span><span class="sxs-lookup"><span data-stu-id="8bc24-145">Select the **PXE** tab, and ensure that the following settings are enabled:</span></span>
    -   <span data-ttu-id="8bc24-146">Habilitar la compatibilidad con PXE para clientes</span><span class="sxs-lookup"><span data-stu-id="8bc24-146">Enable PXE support for clients</span></span>
    -   <span data-ttu-id="8bc24-147">Permitir que este punto de distribución responda a solicitudes PXE entrantes</span><span class="sxs-lookup"><span data-stu-id="8bc24-147">Allow this distribution point to respond to incoming PXE requests</span></span>
    -   <span data-ttu-id="8bc24-148">Habilitar la compatibilidad con equipos desconocidos</span><span class="sxs-lookup"><span data-stu-id="8bc24-148">Enable unknown computer support</span></span>

4.  <span data-ttu-id="8bc24-149">*Opcional:* Para habilitar la compatibilidad con opciones de soporte técnico, seleccione la pestaña **Privacidad** y asegúrese de que las siguientes opciones de configuración están habilitadas:</span><span class="sxs-lookup"><span data-stu-id="8bc24-149">*Optional:* To enable multicast support, select the **Multicast** tab, and ensure that the following settings are enabled:</span></span>
    -   <span data-ttu-id="8bc24-150">Habilitar la opción para enviar datos a varios clientes de forma simultánea</span><span class="sxs-lookup"><span data-stu-id="8bc24-150">Enable multicast to simultaneously send data to multiple clients</span></span>
    -   <span data-ttu-id="8bc24-151">Configure el intervalo de puertos UDP según lo recomendado por su equipo de red.</span><span class="sxs-lookup"><span data-stu-id="8bc24-151">Configure the UDP port range as per your network team's recommendation</span></span>

### <a name="configure-the-network-access-account"></a><span data-ttu-id="8bc24-152">Configurar la cuenta de acceso de red</span><span class="sxs-lookup"><span data-stu-id="8bc24-152">Configure the Network Access Account</span></span>

1.  <span data-ttu-id="8bc24-153">En la consola del Administrador de configuración, vaya a Sitios **de** configuración del sitio de administración \>  \> y, a continuación, seleccione el sitio.</span><span class="sxs-lookup"><span data-stu-id="8bc24-153">In the Configuration Manager console, go to **Administration** \> **Site Configuration** \> **Sites**, and then select the site.</span></span>

2.  <span data-ttu-id="8bc24-154">En el **grupo Configuración,** seleccione **Configurar distribución de** software de componentes del \> **sitio.**</span><span class="sxs-lookup"><span data-stu-id="8bc24-154">In the **Settings** group, select **Configure Site Components** \> **Software Distribution**.</span></span>

3.  <span data-ttu-id="8bc24-155">Seleccione la pestaña **Cuenta de acceso de** red. Configure una o más cuentas y, a continuación, seleccione **Aceptar.**</span><span class="sxs-lookup"><span data-stu-id="8bc24-155">Select the **Network Access Account** tab. Set up one or more accounts, and then select **OK**.</span></span>

> [!NOTE]
> <span data-ttu-id="8bc24-156">Las cuentas no necesitan ningún derecho especial, excepto para **obtener Acceso** a este equipo desde la red directamente en el servidor del punto de distribución.</span><span class="sxs-lookup"><span data-stu-id="8bc24-156">The accounts don't need any special rights, except for the **Access this computer from the network** right on the distribution point server.</span></span> <span data-ttu-id="8bc24-157">Una cuenta de usuario de dominio genérica será apropiada.</span><span class="sxs-lookup"><span data-stu-id="8bc24-157">A generic domain user account will be appropriate.</span></span> <span data-ttu-id="8bc24-158">Para obtener más información, vea [Cuentas usadas en Configuration Manager.](https://docs.microsoft.com/configmgr/core/plan-design/hierarchy/manage-accounts-to-access-content#bkmk_NAA)</span><span class="sxs-lookup"><span data-stu-id="8bc24-158">For more information, see [Accounts used in Configuration Manager](https://docs.microsoft.com/configmgr/core/plan-design/hierarchy/manage-accounts-to-access-content#bkmk_NAA).</span></span>

### <a name="configure-a-boot-image"></a><span data-ttu-id="8bc24-159">Configurar una imagen de arranque</span><span class="sxs-lookup"><span data-stu-id="8bc24-159">Configure a boot image</span></span>

1.  <span data-ttu-id="8bc24-160">En la consola de Configuration Manager, vaya a imágenes **de** arranque del sistema operativo de la biblioteca \>  \> **de software.**</span><span class="sxs-lookup"><span data-stu-id="8bc24-160">In the Configuration Manager console, go to **Software Library** \> **Operating System** \> **Boot Images**.</span></span>

2.  <span data-ttu-id="8bc24-161">Seleccione **Imagen de arranque (x64) y,** a continuación, seleccione **Propiedades.**</span><span class="sxs-lookup"><span data-stu-id="8bc24-161">Select **Boot image (x64)**, and then select **Properties**.</span></span>

3.  <span data-ttu-id="8bc24-162">Seleccione la **pestaña Origen de** datos y habilite Implementar esta imagen de inicio desde el punto de distribución habilitado para **PXE.**</span><span class="sxs-lookup"><span data-stu-id="8bc24-162">Select the **Data Source** tab, and enable **Deploy this boot image from the PXE-enabled distribution point**.</span></span>

4.  <span data-ttu-id="8bc24-163">Seleccione la **pestaña Componentes opcionales** para instalar los componentes necesarios:</span><span class="sxs-lookup"><span data-stu-id="8bc24-163">Select the **Optional Components** tab to install required components:</span></span>

    1.  <span data-ttu-id="8bc24-164">Seleccione el icono de estrella y busque **HTML (WinPE-HTA).**</span><span class="sxs-lookup"><span data-stu-id="8bc24-164">Select the star icon, and search for **HTML (WinPE-HTA)**</span></span>

    2.  <span data-ttu-id="8bc24-165">Seleccione **Aceptar para** agregar compatibilidad con la aplicación HTML a la imagen de inicio.</span><span class="sxs-lookup"><span data-stu-id="8bc24-165">Select **OK** to add HTML application support in to the boot image.</span></span>

5.  <span data-ttu-id="8bc24-166">*Opcional:* Para personalizar la experiencia de implementación, seleccione la **pestaña Personalización.**</span><span class="sxs-lookup"><span data-stu-id="8bc24-166">*Optional:* To customize the deployment experience, select the **Customization** tab.</span></span>
    -   <span data-ttu-id="8bc24-167">Habilite **la compatibilidad de comandos (solo pruebas)** si quiere tener acceso a un símbolo del sistema durante la implementación.</span><span class="sxs-lookup"><span data-stu-id="8bc24-167">Enable **command support (testing only)** if you want to have access to a command prompt during the deployment.</span></span> <span data-ttu-id="8bc24-168">Cuando está habilitado, puede iniciar un símbolo del sistema **seleccionando F8** en cualquier momento durante la implementación.</span><span class="sxs-lookup"><span data-stu-id="8bc24-168">When this is enabled, you can start a command prompt by selecting **F8** at any time during the deployment.</span></span>
    -   <span data-ttu-id="8bc24-169">También puede especificar una imagen de fondo personalizada que se mostrará durante la implementación.</span><span class="sxs-lookup"><span data-stu-id="8bc24-169">You can also specify a custom background image to be displayed during the deployment.</span></span> <span data-ttu-id="8bc24-170">Para establecer una imagen, habilite Especificar el archivo de imagen de **fondo personalizado (ruta de acceso UNC** y seleccione el fondo.</span><span class="sxs-lookup"><span data-stu-id="8bc24-170">To set an image, enable **Specify the custom background image file (UNC path** and select your background.</span></span>

6.  <span data-ttu-id="8bc24-171">Cuando se le pida, **seleccione Sí** y distribuya la imagen de arranque actualizada en los puntos de distribución.</span><span class="sxs-lookup"><span data-stu-id="8bc24-171">When asked, select **Yes** and distribute the updated boot image to your distribution points.</span></span>

<span data-ttu-id="8bc24-172">Para obtener más información, vea [Administrar imágenes de arranque con Configuration Manager.](https://docs.microsoft.com/configmgr/osd/get-started/manage-boot-images)</span><span class="sxs-lookup"><span data-stu-id="8bc24-172">For more information, see [Manage boot images with Configuration Manager](https://docs.microsoft.com/configmgr/osd/get-started/manage-boot-images).</span></span>

> [!NOTE]
> <span data-ttu-id="8bc24-173">Puede crear un medio USB de arranque para iniciar implementaciones basadas en secuencia de tareas de Configuration Manager para entornos que no admiten PXE.</span><span class="sxs-lookup"><span data-stu-id="8bc24-173">You can create a bootable USB media to initiate Configuration Manager task sequence–based deployments for environments that have no PXE support.</span></span> <span data-ttu-id="8bc24-174">Los elementos multimedia de arranque solo contienen la imagen de arranque, los comandos de arranque opcionales y sus archivos necesarios, y los archivos binarios de Configuration Manager para admitir el inicio en Windows PE y la conexión a Configuration Manager durante el resto del proceso de implementación.</span><span class="sxs-lookup"><span data-stu-id="8bc24-174">The bootable media contains only the boot image, optional prestart commands and their required files, and Configuration Manager binaries to support booting into Windows PE and connecting to Configuration Manager for the rest of the deployment process.</span></span> <span data-ttu-id="8bc24-175">Para obtener más información, vea [Crear medios de arranque.](https://docs.microsoft.com/configmgr/osd/deploy-use/create-bootable-media#BKMK_CreateBootableMedia)</span><span class="sxs-lookup"><span data-stu-id="8bc24-175">For more information, see [Create bootable media](https://docs.microsoft.com/configmgr/osd/deploy-use/create-bootable-media#BKMK_CreateBootableMedia).</span></span>

## <a name="create-configuration-manager-packages"></a><span data-ttu-id="8bc24-176">Crear paquetes de Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="8bc24-176">Create Configuration Manager packages</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8bc24-177">La versión de sistema operativo necesaria para cada versión del instalador SRS cambia con cada versión de MSI.</span><span class="sxs-lookup"><span data-stu-id="8bc24-177">The required operating system version for each SRS installer version changes with every MSI release.</span></span> <span data-ttu-id="8bc24-178">Para determinar la mejor versión de sistema operativo para un MSI determinado, ejecute el script de configuración de la consola una vez.</span><span class="sxs-lookup"><span data-stu-id="8bc24-178">To determine the best operating system version for a given MSI, run the console setup script once.</span></span> <span data-ttu-id="8bc24-179">Para obtener más información, vea [Implementar salas de Microsoft Teams con Microsoft Endpoint Configuration Manager.](rooms-scale.md)</span><span class="sxs-lookup"><span data-stu-id="8bc24-179">To learn more, see [Deploy Microsoft Teams Rooms by using Microsoft Endpoint Configuration Manager](rooms-scale.md).</span></span>

<span data-ttu-id="8bc24-180">Configuration Manager requiere una serie de paquetes para implementar y configurar las unidades de Microsoft Teams Rooms.</span><span class="sxs-lookup"><span data-stu-id="8bc24-180">Configuration Manager requires a number of packages to deploy and configure the Microsoft Teams Rooms units.</span></span>

<span data-ttu-id="8bc24-181">Necesita crear y configurar los paquetes siguientes y, después, distribuirlos a los sistemas de sitio de Configuration Manager a los que se les ha asignado el rol de servidor de punto de distribución.</span><span class="sxs-lookup"><span data-stu-id="8bc24-181">You need to create and configure the following packages, and then distribute them to the Configuration Manager site systems that have been assigned the distribution point server role.</span></span>

| <span data-ttu-id="8bc24-182">**Nombre del paquete**</span><span class="sxs-lookup"><span data-stu-id="8bc24-182">**Package name**</span></span>                     | <span data-ttu-id="8bc24-183">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="8bc24-183">**Type**</span></span>               | <span data-ttu-id="8bc24-184">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="8bc24-184">**Description**</span></span>                                                                           |
|--------------------------------------|------------------------|-------------------------------------------------------------------------------------------|
| <span data-ttu-id="8bc24-185">SRS v2 - Paquete de aplicaciones SRS</span><span class="sxs-lookup"><span data-stu-id="8bc24-185">SRS v2 - SRS Application Package</span></span>     | <span data-ttu-id="8bc24-186">Paquete de software</span><span class="sxs-lookup"><span data-stu-id="8bc24-186">Software package</span></span>       | <span data-ttu-id="8bc24-187">Paquete del kit de implementación de Salas de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="8bc24-187">Package for the Microsoft Teams Rooms deployment kit</span></span>                                      |
| <span data-ttu-id="8bc24-188">SRS v2 - Paquete Sysprep</span><span class="sxs-lookup"><span data-stu-id="8bc24-188">SRS v2 - Sysprep Package</span></span>             | <span data-ttu-id="8bc24-189">Paquete de software</span><span class="sxs-lookup"><span data-stu-id="8bc24-189">Software package</span></span>       | <span data-ttu-id="8bc24-190">Empaquetar el paquete para el Unattended.xml para configurar unidades de salas de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="8bc24-190">Package for the custom Unattended.xml to configure Microsoft Teams Rooms units</span></span>            |
| <span data-ttu-id="8bc24-191">SRS v2 - Set-SRSComputerName paquete</span><span class="sxs-lookup"><span data-stu-id="8bc24-191">SRS v2 - Set-SRSComputerName Package</span></span> | <span data-ttu-id="8bc24-192">Paquete de software</span><span class="sxs-lookup"><span data-stu-id="8bc24-192">Software package</span></span>       | <span data-ttu-id="8bc24-193">Empaquetar para la aplicación HTML (HTA) para asignar un nombre de equipo durante la implementación</span><span class="sxs-lookup"><span data-stu-id="8bc24-193">Package for the HTML application (HTA) to assign a computer name during the deployment</span></span>    |
| <span data-ttu-id="8bc24-194">SRS v2- Configurar el programa de instalación srs</span><span class="sxs-lookup"><span data-stu-id="8bc24-194">SRS v2 - Configure SRS Setup</span></span>         | <span data-ttu-id="8bc24-195">Paquete de software</span><span class="sxs-lookup"><span data-stu-id="8bc24-195">Software package</span></span>       | <span data-ttu-id="8bc24-196">Paquete para configurar la implementación de la aplicación Salas de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="8bc24-196">Package to configure deployment of the Microsoft Teams Rooms app</span></span>                          |
| <span data-ttu-id="8bc24-197">SRS v2: paquete de actualizaciones del sistema operativo</span><span class="sxs-lookup"><span data-stu-id="8bc24-197">SRS v2 - OS Updates Package</span></span>          | <span data-ttu-id="8bc24-198">Paquete de software</span><span class="sxs-lookup"><span data-stu-id="8bc24-198">Software package</span></span>       | <span data-ttu-id="8bc24-199">Paquete para implementar actualizaciones obligatorias del sistema operativo</span><span class="sxs-lookup"><span data-stu-id="8bc24-199">Package to deploy mandatory operating system updates</span></span>                                      |
| <span data-ttu-id="8bc24-200">SRS v2 - Paquete de certificados raíz</span><span class="sxs-lookup"><span data-stu-id="8bc24-200">SRS v2 - Root Certificate Package</span></span>    | <span data-ttu-id="8bc24-201">Paquete de software</span><span class="sxs-lookup"><span data-stu-id="8bc24-201">Software package</span></span>       | <span data-ttu-id="8bc24-202">Opcional: paquete para implementar el certificado raíz (no necesario para las unidades unida a un dominio)</span><span class="sxs-lookup"><span data-stu-id="8bc24-202">Optional - Package to deploy the root certificate (not required for domain-joined units)</span></span>  |
| <span data-ttu-id="8bc24-203">SRS v2: paquete de agente de supervisión de Microsoft</span><span class="sxs-lookup"><span data-stu-id="8bc24-203">SRS v2 - Microsoft Monitoring Agent Package</span></span> | <span data-ttu-id="8bc24-204">Paquete de software</span><span class="sxs-lookup"><span data-stu-id="8bc24-204">Software package</span></span>       | <span data-ttu-id="8bc24-205">Opcional: paquete para implementar y configurar el agente de Microsoft Operations Management Suite</span><span class="sxs-lookup"><span data-stu-id="8bc24-205">Optional - Package to deploy and configure the Microsoft Operations Management Suite agent</span></span>|
| <span data-ttu-id="8bc24-206">SRS v2 - Paquete de fondo de WinPE</span><span class="sxs-lookup"><span data-stu-id="8bc24-206">SRS v2 - WinPE Background Package</span></span>    | <span data-ttu-id="8bc24-207">Paquete de software</span><span class="sxs-lookup"><span data-stu-id="8bc24-207">Software package</span></span>       | <span data-ttu-id="8bc24-208">Empaquetar para que la imagen de fondo personalizada se use con imágenes de arranque</span><span class="sxs-lookup"><span data-stu-id="8bc24-208">Package for the custom background image to use with boot images</span></span>                           |
| <span data-ttu-id="8bc24-209">Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="8bc24-209">Windows 10 Enterprise</span></span>                | <span data-ttu-id="8bc24-210">Imagen de sistema operativo</span><span class="sxs-lookup"><span data-stu-id="8bc24-210">Operating system image</span></span> | <span data-ttu-id="8bc24-211">Paquete para el archivo de instalación del sistema operativo (install.wim)</span><span class="sxs-lookup"><span data-stu-id="8bc24-211">Package for the operating system installation file (install.wim)</span></span>                          |
| <span data-ttu-id="8bc24-212">Surface Pro</span><span class="sxs-lookup"><span data-stu-id="8bc24-212">Surface Pro</span></span>                          | <span data-ttu-id="8bc24-213">Paquete de controlador</span><span class="sxs-lookup"><span data-stu-id="8bc24-213">Driver package</span></span>         | <span data-ttu-id="8bc24-214">Paquete para los controladores de dispositivo y firmware para Microsoft Surface Pro</span><span class="sxs-lookup"><span data-stu-id="8bc24-214">Package for the device drivers and firmware for Microsoft Surface Pro</span></span>                     |
| <span data-ttu-id="8bc24-215">Surface Pro 4</span><span class="sxs-lookup"><span data-stu-id="8bc24-215">Surface Pro 4</span></span>                        | <span data-ttu-id="8bc24-216">Paquete de controlador</span><span class="sxs-lookup"><span data-stu-id="8bc24-216">Driver package</span></span>         | <span data-ttu-id="8bc24-217">Paquete para los controladores de dispositivo y firmware para Microsoft Surface Pro 4</span><span class="sxs-lookup"><span data-stu-id="8bc24-217">Package for the device drivers and firmware for Microsoft Surface Pro 4</span></span>                   |

<span data-ttu-id="8bc24-218">Para obtener más información, consulta [Paquetes y programas en Configuration Manager.](https://docs.microsoft.com/configmgr/apps/deploy-use/packages-and-programs)</span><span class="sxs-lookup"><span data-stu-id="8bc24-218">For more information, see [Packages and programs in Configuration Manager](https://docs.microsoft.com/configmgr/apps/deploy-use/packages-and-programs).</span></span>

### <a name="create-folders-for-the-package-source-files"></a><span data-ttu-id="8bc24-219">Crear carpetas para los archivos de origen del paquete</span><span class="sxs-lookup"><span data-stu-id="8bc24-219">Create folders for the package source files</span></span>

<span data-ttu-id="8bc24-220">Configuration Manager requiere que los archivos de origen del paquete se organice en una estructura de carpetas específica cuando se crean por primera vez y cuando se actualizan.</span><span class="sxs-lookup"><span data-stu-id="8bc24-220">Configuration Manager requires package source files to be organized in a specific folder structure when they're first created and when they're updated.</span></span>

<span data-ttu-id="8bc24-221">Cree la siguiente estructura de carpetas en el sitio de administración central o el sitio principal de Microsoft Endpoint Configuration Manager, o en un recurso compartido de servidor que use para hospedar archivos de origen del paquete:</span><span class="sxs-lookup"><span data-stu-id="8bc24-221">Create the following folder structure on the Microsoft Endpoint Configuration Manager central administration site or primary site, or on a server share you're using to host package source files:</span></span>

-   <span data-ttu-id="8bc24-222">SRS v2: paquete de agente de supervisión de Microsoft</span><span class="sxs-lookup"><span data-stu-id="8bc24-222">SRS v2 - Microsoft Monitoring Agent Package</span></span>
-   <span data-ttu-id="8bc24-223">SRS v2: paquete de actualizaciones del sistema operativo</span><span class="sxs-lookup"><span data-stu-id="8bc24-223">SRS v2 - OS Updates Package</span></span>
-   <span data-ttu-id="8bc24-224">SRS v2 - Paquete de certificados raíz</span><span class="sxs-lookup"><span data-stu-id="8bc24-224">SRS v2 - Root Certificate Package</span></span>
-   <span data-ttu-id="8bc24-225">SRS v2 - Set-SRSComputerName paquete</span><span class="sxs-lookup"><span data-stu-id="8bc24-225">SRS v2 - Set-SRSComputerName Package</span></span>
-   <span data-ttu-id="8bc24-226">SRS v2 - Paquete de aplicaciones SRS</span><span class="sxs-lookup"><span data-stu-id="8bc24-226">SRS v2 - SRS Application Package</span></span>
-   <span data-ttu-id="8bc24-227">SRS v2- Configurar el programa de instalación srs</span><span class="sxs-lookup"><span data-stu-id="8bc24-227">SRS v2 - Configure SRS Setup</span></span>
-   <span data-ttu-id="8bc24-228">SRS v2 - Paquete Sysprep</span><span class="sxs-lookup"><span data-stu-id="8bc24-228">SRS v2 - Sysprep Package</span></span>
-   <span data-ttu-id="8bc24-229">Controladores</span><span class="sxs-lookup"><span data-stu-id="8bc24-229">Drivers</span></span>
    -   <span data-ttu-id="8bc24-230">Surface Pro</span><span class="sxs-lookup"><span data-stu-id="8bc24-230">Surface Pro</span></span>
    -   <span data-ttu-id="8bc24-231">Surface Pro 4</span><span class="sxs-lookup"><span data-stu-id="8bc24-231">Surface Pro 4</span></span>
-   <span data-ttu-id="8bc24-232">Sistemas operativos</span><span class="sxs-lookup"><span data-stu-id="8bc24-232">Operating Systems</span></span>
    -   <span data-ttu-id="8bc24-233">Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="8bc24-233">Windows 10 Enterprise</span></span>

> [!TIP]
> <span data-ttu-id="8bc24-234">También puede [descargar](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true) y usar el archivo zip que incluye la estructura de carpetas de los paquetes, los scripts que necesita usar y la plantilla de secuencia de tareas que necesita importar.</span><span class="sxs-lookup"><span data-stu-id="8bc24-234">You may also [download](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true) and use the zip file that includes the folder structure for the packages, the scripts that you need to use, and the task sequence template, that you need to import.</span></span>

### <a name="create-the-monitoring-agent-package"></a><span data-ttu-id="8bc24-235">Crear el paquete de agente de supervisión</span><span class="sxs-lookup"><span data-stu-id="8bc24-235">Create the Monitoring agent package</span></span>

1. <span data-ttu-id="8bc24-236">Descargue el agente de supervisión <https://go.microsoft.com/fwlink/?LinkId=828603> desde.</span><span class="sxs-lookup"><span data-stu-id="8bc24-236">Download the Monitoring agent from <https://go.microsoft.com/fwlink/?LinkId=828603>.</span></span>

2. <span data-ttu-id="8bc24-237">Extraiga el paquete en **la srs v2:** carpeta paquete de agente de supervisión de Microsoft abriendo una ventana del símbolo del sistema y especificando **MMASetup-AMD64.exe /C:**     en el símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="8bc24-237">Extract the package into the **SRS v2 - Microsoft Monitoring Agent Package** folder by opening a Command Prompt window and entering **MMASetup-AMD64.exe /C:**     at the command prompt.</span></span>

3. <span data-ttu-id="8bc24-238">En la consola del Administrador de configuración, ve a Paquetes de administración de aplicaciones de biblioteca de **software** y, a \>  \> continuación, selecciona **Crear paquete.**</span><span class="sxs-lookup"><span data-stu-id="8bc24-238">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**, and then select **Create Package**.</span></span>

4. <span data-ttu-id="8bc24-239">Escribe la siguiente información para crear el paquete:</span><span class="sxs-lookup"><span data-stu-id="8bc24-239">Enter the following information to create the package:</span></span>

   - <span data-ttu-id="8bc24-240">Nombre<strong>: SRS v2 - Paquete de agente de supervisión de Microsoft</strong></span><span class="sxs-lookup"><span data-stu-id="8bc24-240">Name<strong>: SRS v2 - Microsoft Monitoring Agent Package</strong></span></span>

   - <span data-ttu-id="8bc24-241">Fabricante:<strong>Microsoft Corporation</strong></span><span class="sxs-lookup"><span data-stu-id="8bc24-241">Manufacturer<strong>: Microsoft Corporation</strong></span></span>

   - <span data-ttu-id="8bc24-242">Versión:<strong>8.1.11081.0</strong> (escriba la versión del archivo de instalación descargado)</span><span class="sxs-lookup"><span data-stu-id="8bc24-242">Version<strong>: 8.1.11081.0</strong> (enter the version of the downloaded installation file)</span></span>

   - <span data-ttu-id="8bc24-243">Selecciona la **casilla Este paquete contiene** archivos de origen, escribe la ruta de acceso a la carpeta **SRS v2-** Paquete del agente de supervisión de Microsoft y, a continuación, **selecciona Siguiente.**</span><span class="sxs-lookup"><span data-stu-id="8bc24-243">Select the **This package contains source files** check box, enter the path to the **SRS v2 - Microsoft Monitoring Agent Package** folder, and then select **Next**.</span></span>

5. <span data-ttu-id="8bc24-244">Seleccione **No crear un programa y, a** continuación, seleccione **Siguiente.**</span><span class="sxs-lookup"><span data-stu-id="8bc24-244">Select **Do not create a program**, and then select **Next**.</span></span>

6. <span data-ttu-id="8bc24-245">Revise la **página Confirmar la** configuración y, a continuación, seleccione **Siguiente.**</span><span class="sxs-lookup"><span data-stu-id="8bc24-245">Review the **Confirm the settings** page, and then select **Next**.</span></span>

7. <span data-ttu-id="8bc24-246">Seleccione **Cerrar.**</span><span class="sxs-lookup"><span data-stu-id="8bc24-246">Select **Close**.</span></span>

### <a name="create-the-operating-system-updates-package"></a><span data-ttu-id="8bc24-247">Crear el paquete de actualizaciones del sistema operativo</span><span class="sxs-lookup"><span data-stu-id="8bc24-247">Create the operating system updates package</span></span>

1. <span data-ttu-id="8bc24-248">En la carpeta del paquete de actualizaciones del sistema operativo **SRS v2,** cree un nuevo script de PowerShell denominado **Install-SRSv2-OS-Updates.ps1.**</span><span class="sxs-lookup"><span data-stu-id="8bc24-248">In the **SRS v2 - OS Updates Package** folder, create a new PowerShell script named **Install-SRSv2-OS-Updates.ps1**.</span></span>

2. <span data-ttu-id="8bc24-249">Copie el script siguiente en el **Install-SRSv2-OS-Updates.ps1** script.</span><span class="sxs-lookup"><span data-stu-id="8bc24-249">Copy the script below into the **Install-SRSv2-OS-Updates.ps1** script.</span></span> <span data-ttu-id="8bc24-250">Como alternativa, puede descargar el script Install-SRSv2-OS-Updates.ps1 desde [aquí.](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="8bc24-250">Alternatively, you can download the Install-SRSv2-OS-Updates.ps1 script from [here](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true).</span></span>
   ```
   # Install-SRSv2-OS-Updates.ps1
   $strPath = split-path -parent $MyInvocation.MyCommand.Definition
   $total = gci $strPath *.msu | measure | Select-Object -expand Count
   $i = 0
   gci $strPath *.msu | ForEach-Object {
     $i++
     WUSA ""$_.FullName /quiet /norestart""
     Write-Progress -activity "Applying Mandatory Updates" -status "Installing
     $_ .. $i of $total" -percentComplete (($i / $total) * 100)
     Wait-Process -name wusa
   }
   ```
3. <span data-ttu-id="8bc24-251">Descarga los paquetes de Windows Update obligatorios en la misma carpeta.</span><span class="sxs-lookup"><span data-stu-id="8bc24-251">Download the mandatory Windows Update packages into the same folder.</span></span>
   > [!NOTE]
   > <span data-ttu-id="8bc24-252">En el momento en que se publicó este artículo, solo se requería [KB4056892.](http://download.windowsupdate.com/c/msdownload/update/software/secu/2018/01/windows10.0-kb4056892-x64_a41a378cf9ae609152b505c40e691ca1228e28ea.msu)</span><span class="sxs-lookup"><span data-stu-id="8bc24-252">At the time this article was published, only [KB4056892](http://download.windowsupdate.com/c/msdownload/update/software/secu/2018/01/windows10.0-kb4056892-x64_a41a378cf9ae609152b505c40e691ca1228e28ea.msu) was required.</span></span> <span data-ttu-id="8bc24-253">Compruebe [Configurar una consola de Salas de Microsoft Teams](console.md)para ver si se necesitan otras actualizaciones.</span><span class="sxs-lookup"><span data-stu-id="8bc24-253">Check [Configure a Microsoft Teams Rooms console](console.md), to see whether any other updates are required.</span></span>

4. <span data-ttu-id="8bc24-254">En la consola del Administrador de configuración, ve a Paquetes de administración de aplicaciones de biblioteca de **software** y, a \>  \> continuación, selecciona **Crear paquete.**</span><span class="sxs-lookup"><span data-stu-id="8bc24-254">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**, and then select **Create Package**.</span></span>

5. <span data-ttu-id="8bc24-255">Escribe la siguiente información para crear el paquete:</span><span class="sxs-lookup"><span data-stu-id="8bc24-255">Enter the following information to create the package:</span></span>
   -   <span data-ttu-id="8bc24-256">Nombre: **SRS v2 - Paquete de actualizaciones del sistema operativo**</span><span class="sxs-lookup"><span data-stu-id="8bc24-256">Name: **SRS v2 – OS Updates Package**</span></span>
   -   <span data-ttu-id="8bc24-257">Fabricante: **Microsoft Corporation**</span><span class="sxs-lookup"><span data-stu-id="8bc24-257">Manufacturer: **Microsoft Corporation**</span></span>
   -   <span data-ttu-id="8bc24-258">Versión: **1.0.0**</span><span class="sxs-lookup"><span data-stu-id="8bc24-258">Version: **1.0.0**</span></span>
   -   <span data-ttu-id="8bc24-259">Seleccione la **casilla Este paquete contiene** archivos de origen, escriba la ruta de acceso a la carpeta **SRS v2 - Paquete** de actualizaciones del sistema operativo y, a continuación, seleccione **Siguiente.**</span><span class="sxs-lookup"><span data-stu-id="8bc24-259">Select the **This package contains source files** check box, enter the path to the **SRS v2 - OS Updates Package** folder, and then select **Next**.</span></span>

6. <span data-ttu-id="8bc24-260">Seleccione **No crear un programa y, a** continuación, seleccione **Siguiente.**</span><span class="sxs-lookup"><span data-stu-id="8bc24-260">Select **Do not create a program**, and then select **Next**.</span></span>

7. <span data-ttu-id="8bc24-261">Revise la **página Confirmar la** configuración y, a continuación, seleccione **Siguiente.**</span><span class="sxs-lookup"><span data-stu-id="8bc24-261">Review the **Confirm the settings** page, and then select **Next**.</span></span>

8. <span data-ttu-id="8bc24-262">Seleccione **Cerrar.**</span><span class="sxs-lookup"><span data-stu-id="8bc24-262">Select **Close**.</span></span>

### <a name="create-the-root-certificate-package-optional"></a><span data-ttu-id="8bc24-263">Crear el paquete de certificado raíz (opcional)</span><span class="sxs-lookup"><span data-stu-id="8bc24-263">Create the root certificate package (optional)</span></span>

<span data-ttu-id="8bc24-264">Cree este paquete para distribuir el certificado raíz de los dispositivos que no se unirán a un dominio de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="8bc24-264">You create this package to distribute the root certificate for devices that won't be joined to an Active Directory domain.</span></span> <span data-ttu-id="8bc24-265">Crea este paquete solo si se cumplen las dos condiciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="8bc24-265">Create this package only if both the following conditions apply:</span></span>
-   <span data-ttu-id="8bc24-266">La implementación incluye Lync local o Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="8bc24-266">Your deployment includes on-premises Lync or Skype for Business Server.</span></span>
-   <span data-ttu-id="8bc24-267">Las unidades de salas de Microsoft Teams están configuradas para trabajar en un grupo de trabajo en lugar de en un miembro del dominio.</span><span class="sxs-lookup"><span data-stu-id="8bc24-267">Microsoft Teams Rooms units are configured to work in a workgroup instead of a domain member.</span></span>

1.  <span data-ttu-id="8bc24-268">Copie el certificado raíz en la **SRS v2: carpeta Paquete de certificados raíz.**</span><span class="sxs-lookup"><span data-stu-id="8bc24-268">Copy the root certificate into the **SRS v2 – Root Certificate Package** folder.</span></span>

2.  <span data-ttu-id="8bc24-269">En la consola del Administrador de configuración, ve a Paquetes de administración de aplicaciones de biblioteca de **software** y, a \>  \> continuación, selecciona **Crear paquete.**</span><span class="sxs-lookup"><span data-stu-id="8bc24-269">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**, and then select **Create Package**.</span></span>

3.  <span data-ttu-id="8bc24-270">Escribe la siguiente información para crear el paquete:</span><span class="sxs-lookup"><span data-stu-id="8bc24-270">Enter the following information to create the package:</span></span>
    -   <span data-ttu-id="8bc24-271">Nombre: **SRS v2 - Paquete de certificados raíz**</span><span class="sxs-lookup"><span data-stu-id="8bc24-271">Name: **SRS v2 – Root Certificate Package**</span></span>
    -   <span data-ttu-id="8bc24-272">Fabricante: *el nombre de su organización*</span><span class="sxs-lookup"><span data-stu-id="8bc24-272">Manufacturer: *Your organization's name*</span></span>
    -   <span data-ttu-id="8bc24-273">Versión: **1.0.0**</span><span class="sxs-lookup"><span data-stu-id="8bc24-273">Version: **1.0.0**</span></span>
    -   <span data-ttu-id="8bc24-274">Seleccione la **casilla Este paquete contiene** archivos de origen, escriba la ruta de acceso a la carpeta **SRS v2 -** Paquete de certificados raíz y, a continuación, seleccione **Siguiente.**</span><span class="sxs-lookup"><span data-stu-id="8bc24-274">Select the **This package contains source files** check box, enter the path to the **SRS v2 – Root Certificate Package** folder, and then select **Next**.</span></span>

4.  <span data-ttu-id="8bc24-275">Seleccione **No crear un programa y, a** continuación, seleccione **Siguiente.**</span><span class="sxs-lookup"><span data-stu-id="8bc24-275">Select **Do not create a program**, and then select **Next**.</span></span>

5.  <span data-ttu-id="8bc24-276">Revise la **página Confirmar la** configuración y, a continuación, seleccione **Siguiente.**</span><span class="sxs-lookup"><span data-stu-id="8bc24-276">Review the **Confirm the settings** page, and then select **Next**.</span></span>

6.  <span data-ttu-id="8bc24-277">Seleccione **Cerrar.**</span><span class="sxs-lookup"><span data-stu-id="8bc24-277">Select **Close**.</span></span>

### <a name="create-the-microsoft-teams-rooms-deployment-kit-package"></a><span data-ttu-id="8bc24-278">Crear el paquete de kit de implementación de salas de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="8bc24-278">Create the Microsoft Teams Rooms deployment kit package</span></span>

1.  <span data-ttu-id="8bc24-279">Descargue la última versión del kit de implementación de Salas de **Microsoft Teams desde** e <https://go.microsoft.com/fwlink/?linkid=851168> instálelo en una estación de trabajo.</span><span class="sxs-lookup"><span data-stu-id="8bc24-279">Download the latest version of the **Microsoft Teams Rooms deployment kit** from <https://go.microsoft.com/fwlink/?linkid=851168>, and install it to a workstation.</span></span>

2.  <span data-ttu-id="8bc24-280">Copie el contenido de **C: \\ Program Files (x86) \\ del Kit** de implementación de Sistemas de sala de Skype en la carpeta paquete de aplicaciones **SRS v2 - SRS.**</span><span class="sxs-lookup"><span data-stu-id="8bc24-280">Copy the content from **C:\\Program Files (x86)\\Skype Room System Deployment Kit** to the **SRS v2 - SRS Application Package** folder.</span></span>

3.  <span data-ttu-id="8bc24-281">En la consola del Administrador de configuración, ve a Paquetes de administración de aplicaciones de biblioteca de **software** y, a \>  \> continuación, selecciona **Crear paquete.**</span><span class="sxs-lookup"><span data-stu-id="8bc24-281">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**, and then select **Create Package**.</span></span>

4.  <span data-ttu-id="8bc24-282">Escribe la siguiente información para crear el paquete:</span><span class="sxs-lookup"><span data-stu-id="8bc24-282">Enter the following information to create the package:</span></span>
    -   <span data-ttu-id="8bc24-283">Nombre: **SRS v2 – Paquete de aplicaciones SRS**</span><span class="sxs-lookup"><span data-stu-id="8bc24-283">Name: **SRS v2 – SRS Application Package**</span></span>
    -   <span data-ttu-id="8bc24-284">Fabricante: **Microsoft Corporation**</span><span class="sxs-lookup"><span data-stu-id="8bc24-284">Manufacturer: **Microsoft Corporation**</span></span>
    -   <span data-ttu-id="8bc24-285">Versión: **3.1.104.0** (escriba la versión del archivo de instalación descargado)</span><span class="sxs-lookup"><span data-stu-id="8bc24-285">Version: **3.1.104.0** (enter the version of the downloaded installation file)</span></span>
    -   <span data-ttu-id="8bc24-286">Seleccione la **casilla Este paquete contiene** archivos de origen, escriba la ruta de acceso a la carpeta del paquete de aplicaciones **SRS v2 – SRS** y, a continuación, **seleccione Siguiente.**</span><span class="sxs-lookup"><span data-stu-id="8bc24-286">Select the **This package contains source files** check box, enter the path to the **SRS v2 – SRS Application Package** folder, and then select **Next**.</span></span>
5.  <span data-ttu-id="8bc24-287">Seleccione **No crear un programa y, a** continuación, seleccione **Siguiente.**</span><span class="sxs-lookup"><span data-stu-id="8bc24-287">Select **Do not create a program**, and then select **Next**.</span></span>

6.  <span data-ttu-id="8bc24-288">Revise la **página Confirmar la** configuración y, a continuación, seleccione **Siguiente.**</span><span class="sxs-lookup"><span data-stu-id="8bc24-288">Review the **Confirm the settings** page, and then select **Next**.</span></span>

7.  <span data-ttu-id="8bc24-289">Seleccione **Cerrar.**</span><span class="sxs-lookup"><span data-stu-id="8bc24-289">Select **Close**.</span></span>

### <a name="create-the-computer-name-assignment-package"></a><span data-ttu-id="8bc24-290">Crear el paquete de asignación de nombres de equipo</span><span class="sxs-lookup"><span data-stu-id="8bc24-290">Create the computer name assignment package</span></span>

1.  <span data-ttu-id="8bc24-291">En **srs v2 - Set-SRSComputerName carpeta** paquete, cree una nueva aplicación HTML denominada **Set-SRSComputerName.hta** .</span><span class="sxs-lookup"><span data-stu-id="8bc24-291">In the **SRS v2 - Set-SRSComputerName Package** folder, create a new HTML application named **Set-SRSComputerName.hta** .</span></span>

2.  <span data-ttu-id="8bc24-292">Copie el script siguiente en **el archivo Set-SRSComputerName.hta.**</span><span class="sxs-lookup"><span data-stu-id="8bc24-292">Copy the following script into the **Set-SRSComputerName.hta** file.</span></span> <span data-ttu-id="8bc24-293">Como alternativa, puede descargar el archivo Set-SRSComputerName.hta desde [aquí.](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="8bc24-293">Alternatively, you can download the Set-SRSComputerName.hta file from [here](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true).</span></span>
    ```HTML
    <!DOCTYPE HTML>
    <html>
    <head>
    <title>Set SRS Computer Name</title>
    <HTA:APPLICATION
      APPLICATIONNAME="Set SRS Computer Name"
      ID="SetSRSComputerName"
      VERSION="1.0"
      SCROLL="no"
      SINGLEINSTANCE="yes"
      WINDOWSTATE="maximize"
      MaximizeButton="no"
      MinimizeButton="no"
      SysMenu="no"
      ShowInTaskbar="no"
      Caption="no"
      />
    <style type="text/css">
    body {
        background-color: #fdfeff;
        color: darkblue;
        font-family: Calibri;
        font-size: 12pt;
        margin: 4em 3em;
    }
    </style>
    </head>
    <script language="VBScript">
    Public strNewComputerName
    Sub GenerateComputerName()
        strComputer = "."
        Set objWMIService = GetObject("winmgmts:\\" & strComputer & "\root\cimv2")
        Set colItems = objWMIService.ExecQuery("Select * from Win32_BIOS",,48)
        For Each objItem in colItems
            strSerialNumber = objItem.SerialNumber
        Next
        strNewComputerName = "SRS-"  & right(replace(strSerialNumber, "-","") ,10)
        TextArea1.innerHTML = "The serial number of the device: " & strSerialNumber
        strHTMLText = strHTMLText & "<br> Computer name to be assigned: <font color = red>" & strNewComputerName & "</font>"
        strHTMLText = strHTMLText & "<br><br> Click Accept to use this as the computer name and continue deployment, or Change to set a new name."
        strHTMLText = strHTMLText & "<p><input type=""button"" value=""Accept"" name = ""Accept_Button"" onclick=""SetComputerName"" />"
        strHTMLText = strHTMLText & " <input type=""button"" value=""Change"" name = ""Change_Button"" onclick=""ChangeComputerName"" />"
        TextArea2.innerHTML = strHTMLText
    End Sub

    Sub SetComputerName()
        dim result
        result = MsgBox("Computer Name to be assigned: " & strNewComputerName &vbcrlf & "Are you sure you want to continue?", 36)
        If (result = vbYes) then
            SET env = CreateObject("Microsoft.SMS.TSEnvironment")
            env("OSDComputerName") = strNewComputerName
            self.close
        elseif (result = vbNo) then
            Window_OnLoad
        End If
    End Sub

    Sub UpdateComputerName()
        strNewComputerName = newcomputername.value
        if len(trim(strNewComputerName)) = 0 then
            MsgBox "Computer name cannot be empty." &vbcrlf & "Update and try again.",16
            exit sub
        end if
        SetComputerName
    End Sub

    Sub ChangeComputerName()
        TextArea2.innerHTML = "<p>Type the new computer name and click Accept:  <input type=""text"" name=""newcomputername"" value =" & strNewComputerName & " />"
        TextArea2.innerHTML = TextArea2.innerHTML & "<br><input type=""button"" value=""Update"" name = ""Update_Button"" onclick=""UpdateComputerName"" />"
    End Sub

    Sub Window_OnLoad
        Set oTSProgressUI = CreateObject("Microsoft.SMS.TsProgressUI")
        oTSProgressUI.CloseProgressDialog
        GenerateComputerName
    End Sub
    </script>

    <body>
    <span id = "TextArea1"></span>
    <span id = "TextArea2">
    </span>
    </body>
    </html>

    ```
3.  <span data-ttu-id="8bc24-294">En la consola del Administrador de configuración, ve a Paquetes de administración de aplicaciones de biblioteca de **software** y, a \>  \> continuación, selecciona **Crear paquete.**</span><span class="sxs-lookup"><span data-stu-id="8bc24-294">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**, and then select **Create Package**.</span></span>

4.  <span data-ttu-id="8bc24-295">Escribe la siguiente información para crear el paquete:</span><span class="sxs-lookup"><span data-stu-id="8bc24-295">Enter the following information to create the package:</span></span>

    -   <span data-ttu-id="8bc24-296">Nombre: **SRS v2 - Set-SRSComputerName paquete**</span><span class="sxs-lookup"><span data-stu-id="8bc24-296">Name: **SRS v2 - Set-SRSComputerName Package**</span></span>

    -   <span data-ttu-id="8bc24-297">Fabricante: **Microsoft Corporation**</span><span class="sxs-lookup"><span data-stu-id="8bc24-297">Manufacturer: **Microsoft Corporation**</span></span>

    -   <span data-ttu-id="8bc24-298">Versión: **1.0.0**</span><span class="sxs-lookup"><span data-stu-id="8bc24-298">Version: **1.0.0**</span></span>

    -   <span data-ttu-id="8bc24-299">Selecciona la **casilla Este paquete contiene** archivos de origen, escribe la ruta de acceso a **SRS v2 - Set-SRSComputerName** del paquete y, a continuación, selecciona **Siguiente.**</span><span class="sxs-lookup"><span data-stu-id="8bc24-299">Select the **This package contains source files** check box, enter the path to the **SRS v2 - Set-SRSComputerName Package** folder, and then select **Next**.</span></span>

5.  <span data-ttu-id="8bc24-300">Seleccione **No crear un programa y, a** continuación, seleccione **Siguiente.**</span><span class="sxs-lookup"><span data-stu-id="8bc24-300">Select **Do not create a program**, and then select **Next**.</span></span>

6.  <span data-ttu-id="8bc24-301">Revise la **página Confirmar la** configuración y, a continuación, seleccione **Siguiente.**</span><span class="sxs-lookup"><span data-stu-id="8bc24-301">Review the **Confirm the settings** page, and then select **Next**.</span></span>

7.  <span data-ttu-id="8bc24-302">Seleccione **Cerrar.**</span><span class="sxs-lookup"><span data-stu-id="8bc24-302">Select **Close**.</span></span>

### <a name="create-the-sysprep-package"></a><span data-ttu-id="8bc24-303">Crear el paquete Sysprep</span><span class="sxs-lookup"><span data-stu-id="8bc24-303">Create the Sysprep package</span></span>

1. <span data-ttu-id="8bc24-304">En la **carpeta del paquete SRS v2 – Sysprep,** cree un nuevo archivo XML denominado **Unattend.xml.**</span><span class="sxs-lookup"><span data-stu-id="8bc24-304">In the **SRS v2 – Sysprep Package** folder, create a new XML file named **Unattend.xml** .</span></span>

2. <span data-ttu-id="8bc24-305">Copie el siguiente texto en el **Unattend.xml** archivo.</span><span class="sxs-lookup"><span data-stu-id="8bc24-305">Copy the following text into the **Unattend.xml** file.</span></span> <span data-ttu-id="8bc24-306">Como alternativa, puede descargar el archivo Unattend.xml desde [aquí.](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="8bc24-306">Alternatively, you can download the Unattend.xml file from [here](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true).</span></span>
   ```XML
   <?xml version="1.0" encoding="utf-8"?>
   <unattend xmlns="urn:schemas-microsoft-com:unattend">
   <settings pass="specialize">
       <component name="Microsoft-Windows-Embedded-BootExp" processorArchitecture="amd64" publicKeyToken="31bf3856ad364e35" language="neutral" versionScope="NonSxS" xmlns:wcm="https://schemas.microsoft.com/WMIConfig/2002/State" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
           <DisableBootMenu>1</DisableBootMenu>
           <DisplayDisabled>1</DisplayDisabled>
       </component>
       <component name="Microsoft-Windows-powercpl" processorArchitecture="amd64" publicKeyToken="31bf3856ad364e35" language="neutral" versionScope="nonSxS" xmlns:wcm="https://schemas.microsoft.com/WMIConfig/2002/State" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
           <PreferredPlan>8c5e7fda-e8bf-4a96-9a85-a6e23a8c635c</PreferredPlan>
       </component>
   </settings>
   <settings pass="oobeSystem">
       <component name="Microsoft-Windows-Shell-Setup" processorArchitecture="amd64" publicKeyToken="31bf3856ad364e35" language="neutral" versionScope="nonSxS" xmlns:wcm="https://schemas.microsoft.com/WMIConfig/2002/State" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
           <OOBE>
               <HideEULAPage>true</HideEULAPage>
               <HideLocalAccountScreen>true</HideLocalAccountScreen>
               <HideOEMRegistrationScreen>true</HideOEMRegistrationScreen>
               <HideOnlineAccountScreens>true</HideOnlineAccountScreens>
               <HideWirelessSetupInOOBE>true</HideWirelessSetupInOOBE>
               <SkipMachineOOBE>true</SkipMachineOOBE>
               <SkipUserOOBE>true</SkipUserOOBE>
               <ProtectYourPC>1</ProtectYourPC>
           </OOBE>
           <AutoLogon>
               <Enabled>true</Enabled>
               <Username>Skype</Username>
               <Password>
                   <Value>UABhAHMAcwB3AG8AcgBkAA==</Value>
                   <PlainText>false</PlainText>
               </Password>
           </AutoLogon>
           <UserAccounts>
               <LocalAccounts>
                   <LocalAccount wcm:action="add">
                       <Password>
                           <Value>cwBmAGIAUABhAHMAcwB3AG8AcgBkAA==</Value>
                           <PlainText>false</PlainText>
                       </Password>
                       <Name>Admin</Name>
                       <Group>Administrators</Group>
                       <DisplayName>Administrator</DisplayName>
                       <Description>Administrator</Description>
                   </LocalAccount>
               </LocalAccounts>
           </UserAccounts>
       </component>
   </settings>
   <cpi:offlineImage cpi:source="wim:h:/install.wim#Windows 10 Enterprise" xmlns:cpi="urn:schemas-microsoft-com:cpi" />
   </unattend>
   ```
3. <span data-ttu-id="8bc24-307">En la consola del Administrador de configuración, ve a Paquetes de administración de aplicaciones de biblioteca de **software** y, a \>  \> continuación, selecciona **Crear paquete.**</span><span class="sxs-lookup"><span data-stu-id="8bc24-307">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**, and then select **Create Package**.</span></span>

4. <span data-ttu-id="8bc24-308">Escribe la siguiente información para crear el paquete:</span><span class="sxs-lookup"><span data-stu-id="8bc24-308">Enter the following information to create the package:</span></span>
   -   <span data-ttu-id="8bc24-309">Nombre: **SRS v2 - paquete Sysprep**</span><span class="sxs-lookup"><span data-stu-id="8bc24-309">Name: **SRS v2 - Sysprep Package**</span></span>
   -   <span data-ttu-id="8bc24-310">Fabricante: **Microsoft Corporation**</span><span class="sxs-lookup"><span data-stu-id="8bc24-310">Manufacturer: **Microsoft Corporation**</span></span>
   -   <span data-ttu-id="8bc24-311">Versión: **1.0.0**</span><span class="sxs-lookup"><span data-stu-id="8bc24-311">Version: **1.0.0**</span></span>
   -   <span data-ttu-id="8bc24-312">Seleccione la **casilla Este paquete contiene** archivos de origen, escriba la ruta de acceso a la carpeta del paquete **SRS v2 – Sysprep** y, a continuación, **seleccione Siguiente.**</span><span class="sxs-lookup"><span data-stu-id="8bc24-312">Select the **This package contains source files** check box, enter the path to the **SRS v2 – Sysprep Package** folder, and then select **Next**.</span></span>
5. <span data-ttu-id="8bc24-313">Seleccione **No crear un programa y, a** continuación, seleccione **Siguiente.**</span><span class="sxs-lookup"><span data-stu-id="8bc24-313">Select **Do not create a program**, and then select **Next**.</span></span>

6. <span data-ttu-id="8bc24-314">Revise la **página Confirmar la** configuración y, a continuación, seleccione **Siguiente.**</span><span class="sxs-lookup"><span data-stu-id="8bc24-314">Review the **Confirm the settings** page, and then select **Next**.</span></span>

7. <span data-ttu-id="8bc24-315">Seleccione **Cerrar.**</span><span class="sxs-lookup"><span data-stu-id="8bc24-315">Select **Close**.</span></span>

### <a name="create-the-windows-10-enterprise-package"></a><span data-ttu-id="8bc24-316">Crear el paquete de Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="8bc24-316">Create the Windows 10 Enterprise package</span></span>

1.  <span data-ttu-id="8bc24-317">Obtenga un medio x64 de Windows 10 Enterprise y copie el archivo **install.wim** en la carpeta Sistemas operativos **\\ windows 10 Enterprise.**</span><span class="sxs-lookup"><span data-stu-id="8bc24-317">Obtain a Windows 10 Enterprise x64 media, and copy the **install.wim** file to the **Operating Systems\\Windows 10 Enterprise** folder.</span></span>

2.  <span data-ttu-id="8bc24-318">En la consola del Administrador de configuración, vaya a Imágenes de sistema operativo de la biblioteca de **software** y, a continuación, \>  \> seleccione Agregar **imagen de sistema operativo.**</span><span class="sxs-lookup"><span data-stu-id="8bc24-318">In the Configuration Manager console, go to **Software Library** \> **Operating Systems** \> **Operating System Images**, and then select **Add Operating System Image**.</span></span>

3.  <span data-ttu-id="8bc24-319">Especifique la ruta de acceso al **archivo install.wim** que acaba de copiar y, a continuación, seleccione **Siguiente.**</span><span class="sxs-lookup"><span data-stu-id="8bc24-319">Specify the path to the **install.wim** file you just copied, and then select **Next**.</span></span>

4.  <span data-ttu-id="8bc24-320">Actualice el **campo** Versión para que coincida con el número de compilación de la imagen de Windows 10 Enterprise y, a continuación, **seleccione Siguiente.**</span><span class="sxs-lookup"><span data-stu-id="8bc24-320">Update the **Version** field to match the build number of the Windows 10 Enterprise image, and then select **Next**.</span></span>

5.  <span data-ttu-id="8bc24-321">Revise la **página** detalles y, a continuación, seleccione **Siguiente.**</span><span class="sxs-lookup"><span data-stu-id="8bc24-321">Review the **Details** page, and then select **Next**.</span></span>

6.  <span data-ttu-id="8bc24-322">Seleccione **Cerrar.**</span><span class="sxs-lookup"><span data-stu-id="8bc24-322">Select **Close**.</span></span>

<span data-ttu-id="8bc24-323">Para obtener más información, vea [Administrar imágenes del sistema operativo con Configuration Manager.](https://docs.microsoft.com/configmgr/osd/get-started/manage-operating-system-images)</span><span class="sxs-lookup"><span data-stu-id="8bc24-323">For more information, see [Manage OS images with Configuration Manager](https://docs.microsoft.com/configmgr/osd/get-started/manage-operating-system-images).</span></span>

### <a name="create-surface-pro-device-driver-packages"></a><span data-ttu-id="8bc24-324">Crear paquetes de controlador de dispositivo Surface Pro</span><span class="sxs-lookup"><span data-stu-id="8bc24-324">Create Surface Pro device driver packages</span></span>

<span data-ttu-id="8bc24-325">Salas de Microsoft Teams es compatible tanto con Surface Pro como con Surface Pro 4.</span><span class="sxs-lookup"><span data-stu-id="8bc24-325">Microsoft Teams Rooms is supported for both Surface Pro and Surface Pro 4.</span></span> <span data-ttu-id="8bc24-326">Debes crear un paquete de controlador para cada modelo de Surface Pro que tienes en tu entorno.</span><span class="sxs-lookup"><span data-stu-id="8bc24-326">You need to create a driver package for each Surface Pro model you have in your environment.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8bc24-327">Los controladores deben ser compatibles con la compilación de Windows 10 Enterprise y la versión del kit de implementación de Microsoft Teams Rooms.</span><span class="sxs-lookup"><span data-stu-id="8bc24-327">The drivers must be compatible with the Windows 10 Enterprise build and the Microsoft Teams Rooms deployment kit version.</span></span> <span data-ttu-id="8bc24-328">Para obtener más información, consulte Descargar el firmware y los controladores más recientes para [dispositivos Surface](https://docs.microsoft.com/surface/deploy-the-latest-firmware-and-drivers-for-surface-devices) y [Configurar una consola.](console.md)</span><span class="sxs-lookup"><span data-stu-id="8bc24-328">For more information, see [Download the latest firmware and drivers for Surface devices](https://docs.microsoft.com/surface/deploy-the-latest-firmware-and-drivers-for-surface-devices) and [Configure a console](console.md).</span></span>

1.  <span data-ttu-id="8bc24-329">Descargue los controladores y el firmware más recientes.</span><span class="sxs-lookup"><span data-stu-id="8bc24-329">Download the latest drivers and firmware.</span></span>
    -   <span data-ttu-id="8bc24-330">Para Surface Pro: <https://www.microsoft.com/download/details.aspx?id=55484></span><span class="sxs-lookup"><span data-stu-id="8bc24-330">For Surface Pro: <https://www.microsoft.com/download/details.aspx?id=55484></span></span>
    -   <span data-ttu-id="8bc24-331">Para Surface Pro 4: <https://www.microsoft.com/download/details.aspx?id=49498></span><span class="sxs-lookup"><span data-stu-id="8bc24-331">For Surface Pro 4: <https://www.microsoft.com/download/details.aspx?id=49498></span></span>

2.  <span data-ttu-id="8bc24-332">Extraiga el controlador y el firmware descargados.</span><span class="sxs-lookup"><span data-stu-id="8bc24-332">Extract the downloaded driver and firmware.</span></span> <span data-ttu-id="8bc24-333">Abra una ventana del símbolo del sistema y, en el símbolo del sistema, escriba uno de los siguientes comandos:</span><span class="sxs-lookup"><span data-stu-id="8bc24-333">Open a Command Prompt window and at the command prompt, enter one of the following commands:</span></span>
    -   `msiexec /a C:\SurfacePro_Win10.msi /passive TARGETDIR="C:\_Sources\\Drivers\Surface Pro"`
    -   `msiexec /a C:\SurfacePro4_Win10.msi /passive TARGETDIR="C:\_Sources\\Drivers\Surface Pro 4"`

3.  <span data-ttu-id="8bc24-334">En la consola del Administrador de configuración, vaya **a Controladores** de sistemas operativos de la biblioteca de software y, a \>  \> continuación, seleccione **Importar controlador.**</span><span class="sxs-lookup"><span data-stu-id="8bc24-334">In the Configuration Manager console, go to **Software Library** \> **Operating Systems** \> **Drivers**, and then select **Import Driver**.</span></span>

4.  <span data-ttu-id="8bc24-335">Seleccione Importar todos los controladores en la siguiente ruta de red **(UNC),** seleccione la carpeta de origen (por ejemplo, C: _Sources Controladores surface Pro) y, a continuación, \\ \\ seleccione \\ **Siguiente.**</span><span class="sxs-lookup"><span data-stu-id="8bc24-335">Select **Import all drivers in the following network path (UNC)**, select the source folder (for example, C:\\_Sources\\Drivers\\Surface Pro), and then select **Next**.</span></span>

5.  <span data-ttu-id="8bc24-336">En la **página Especificar los detalles** de los controladores importados, seleccione todos los controladores de la lista y, a continuación, seleccione Habilitar estos controladores y permitir que los equipos los **instalen.**</span><span class="sxs-lookup"><span data-stu-id="8bc24-336">On the **Specify the details for the imported drivers** page, select all the listed drivers, and then select **Enable these drivers and allow computers to install them**.</span></span>

6.  <span data-ttu-id="8bc24-337">Selecciona **Categorías,** crea una nueva categoría que coincida con el modelo de Surface, **selecciona** Aceptar y, a continuación, selecciona **Siguiente.**</span><span class="sxs-lookup"><span data-stu-id="8bc24-337">Select **Categories**, create a new category that matches the Surface model, select **OK**, and then select **Next**.</span></span>

7.  <span data-ttu-id="8bc24-338">Seleccione **Nuevo paquete.**</span><span class="sxs-lookup"><span data-stu-id="8bc24-338">Select **New Package**.</span></span>

8.  <span data-ttu-id="8bc24-339">Especifica el nombre del paquete que coincida con el modelo de Surface Pro, escribe una ruta de carpeta en la que almacenar los archivos del paquete del controlador, selecciona Aceptar **y,** a continuación, **selecciona Siguiente.**</span><span class="sxs-lookup"><span data-stu-id="8bc24-339">Specify the package name that matches the Surface Pro model, enter a folder path to store the driver package files in, select **OK**, and then select **Next**.</span></span>

9.  <span data-ttu-id="8bc24-340">En la **página de imágenes de** arranque, asegúrese de que no haya imágenes de arranque seleccionadas y, después, seleccione **Siguiente.**</span><span class="sxs-lookup"><span data-stu-id="8bc24-340">On the **boot images** page, ensure that no boot images are selected, and then select **Next**.</span></span>

10. <span data-ttu-id="8bc24-341">Seleccione **Cerrar.**</span><span class="sxs-lookup"><span data-stu-id="8bc24-341">Select **Close**.</span></span>

11. <span data-ttu-id="8bc24-342">Ve a **Controladores de** sistemas operativos de biblioteca de \>  \> **software,** selecciona **\>** Crear carpeta y escribe un nombre de carpeta que coincida con el modelo de Surface Pro del que has importado los controladores.</span><span class="sxs-lookup"><span data-stu-id="8bc24-342">Go to **Software Library** \> **Operating Systems** \> **Drivers**, select **Folder \> Create Folder**, and enter a folder name that matches the Surface Pro model that you just imported the drivers for.</span></span>

12. <span data-ttu-id="8bc24-343">Mueva todos los controladores importados a la carpeta recién creada para facilitar la navegación y la operación.</span><span class="sxs-lookup"><span data-stu-id="8bc24-343">Move all the imported drivers to the newly created folder for easier navigation and operation.</span></span>

> [!NOTE]
> <span data-ttu-id="8bc24-344">Repite los mismos pasos para otros modelos de Surface Pro que podrías tener.</span><span class="sxs-lookup"><span data-stu-id="8bc24-344">Repeat the same steps for other Surface Pro models you might have.</span></span> <span data-ttu-id="8bc24-345">Para obtener más información, vea [Administrar controladores en Configuration Manager.](https://docs.microsoft.com/configmgr/osd/get-started/manage-drivers)</span><span class="sxs-lookup"><span data-stu-id="8bc24-345">For more information, see [Manage drivers in Configuration Manager](https://docs.microsoft.com/configmgr/osd/get-started/manage-drivers).</span></span>

### <a name="create-microsoft-teams-rooms-configuration-package"></a><span data-ttu-id="8bc24-346">Paquete de configuración Crear salas de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="8bc24-346">Create Microsoft Teams Rooms Configuration Package</span></span>

1.  <span data-ttu-id="8bc24-347">En la consola del Administrador de configuración, ve a Paquetes de administración de aplicaciones de biblioteca de **software** y, a \>  \> continuación, selecciona **Crear paquete.**</span><span class="sxs-lookup"><span data-stu-id="8bc24-347">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**, and then select **Create Package**.</span></span>

2.  <span data-ttu-id="8bc24-348">Escribe la siguiente información para crear el paquete:</span><span class="sxs-lookup"><span data-stu-id="8bc24-348">Enter the following information to create the package:</span></span>

    -   <span data-ttu-id="8bc24-349">Nombre: **SRS v2 - Configurar paquete de instalación SRS**</span><span class="sxs-lookup"><span data-stu-id="8bc24-349">Name: **SRS v2 - Configure SRS Setup Package**</span></span>

    -   <span data-ttu-id="8bc24-350">Fabricante: **Microsoft Corporation**</span><span class="sxs-lookup"><span data-stu-id="8bc24-350">Manufacturer: **Microsoft Corporation**</span></span>

    -   <span data-ttu-id="8bc24-351">Versión: **1.0.0**</span><span class="sxs-lookup"><span data-stu-id="8bc24-351">Version: **1.0.0**</span></span>

    -   <span data-ttu-id="8bc24-352">Seleccione la **casilla Este paquete contiene** archivos de origen, escriba la ruta de acceso a la carpeta configuración SRS v2 - Configurar **SRS y,** a continuación, **seleccione Siguiente.**</span><span class="sxs-lookup"><span data-stu-id="8bc24-352">Select the **This package contains source files** check box, enter the path to the **SRS v2 - Configure SRS Setup** folder, and then select **Next**.</span></span>

3.  <span data-ttu-id="8bc24-353">Seleccione **No crear un programa y, a** continuación, seleccione **Siguiente.**</span><span class="sxs-lookup"><span data-stu-id="8bc24-353">Select **Do not create a program**, and then select **Next**.</span></span>

4.  <span data-ttu-id="8bc24-354">Revise la **página Confirmar la** configuración y, a continuación, seleccione **Siguiente.**</span><span class="sxs-lookup"><span data-stu-id="8bc24-354">Review the **Confirm the settings** page, and then select **Next**.</span></span>

5.  <span data-ttu-id="8bc24-355">Seleccione **Cerrar.**</span><span class="sxs-lookup"><span data-stu-id="8bc24-355">Select **Close**.</span></span>



## <a name="distribute-configuration-manager-packages"></a><span data-ttu-id="8bc24-356">Distribuir paquetes de Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="8bc24-356">Distribute Configuration Manager packages</span></span>

<span data-ttu-id="8bc24-357">Todos los paquetes deben distribuirse a los servidores a los que se les haya asignado el rol de punto de distribución en la jerarquía de Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="8bc24-357">All the packages must be distributed to the servers that have been assigned the distribution point role in the Configuration Manager hierarchy.</span></span> <span data-ttu-id="8bc24-358">Siga las instrucciones siguientes para iniciar la distribución de paquetes.</span><span class="sxs-lookup"><span data-stu-id="8bc24-358">Follow the instructions below to initiate package distribution.</span></span>

1.  <span data-ttu-id="8bc24-359">Distribuir paquetes de software.</span><span class="sxs-lookup"><span data-stu-id="8bc24-359">Distribute software packages.</span></span>

    1.  <span data-ttu-id="8bc24-360">En la consola del Administrador de configuración, vaya a Paquetes **de administración** de aplicaciones de \> **biblioteca de** \> **software.**</span><span class="sxs-lookup"><span data-stu-id="8bc24-360">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**.</span></span> <span data-ttu-id="8bc24-361">Selecciona todos los paquetes de software que quieras distribuir y, a continuación, **selecciona Distribuir contenido.**</span><span class="sxs-lookup"><span data-stu-id="8bc24-361">Select all the software packages you want to distribute, and then select **Distribute Content**.</span></span>

    2.  <span data-ttu-id="8bc24-362">Revisa la lista de paquetes y, a continuación, selecciona **Siguiente.**</span><span class="sxs-lookup"><span data-stu-id="8bc24-362">Review the list of packages, and then select **Next**.</span></span>

    3.  <span data-ttu-id="8bc24-363">Agregue todos los servidores de puntos de distribución (o grupos de puntos de distribución, según la jerarquía de Configuration Manager) a la lista y, después, seleccione **Siguiente.**</span><span class="sxs-lookup"><span data-stu-id="8bc24-363">Add all the distribution point servers (or distribution point groups, depending on your Configuration Manager hierarchy) to the list, and then select **Next**.</span></span>

    4.  <span data-ttu-id="8bc24-364">Seleccione **Siguiente** y, a continuación, **seleccione Cerrar.**</span><span class="sxs-lookup"><span data-stu-id="8bc24-364">Select **Next**, and then select **Close**.</span></span>

2.  <span data-ttu-id="8bc24-365">Distribuir paquetes de controlador.</span><span class="sxs-lookup"><span data-stu-id="8bc24-365">Distribute driver packages.</span></span>

    1.  <span data-ttu-id="8bc24-366">En la consola de Configuration Manager, vaya a paquetes **de** controlador \> **de sistemas operativos de biblioteca** \> **de software.**</span><span class="sxs-lookup"><span data-stu-id="8bc24-366">In the Configuration Manager console, go to **Software Library** \> **Operating Systems** \> **Driver Packages**.</span></span> <span data-ttu-id="8bc24-367">Selecciona todos los paquetes de controlador que quieras distribuir y, a continuación, **selecciona Distribuir contenido.**</span><span class="sxs-lookup"><span data-stu-id="8bc24-367">Select all the driver packages you want to distribute, and then select **Distribute Content**.</span></span>

    2.  <span data-ttu-id="8bc24-368">Revisa la lista de paquetes y, a continuación, selecciona **Siguiente.**</span><span class="sxs-lookup"><span data-stu-id="8bc24-368">Review the list of packages, and then select **Next**.</span></span>

    3.  <span data-ttu-id="8bc24-369">Agregue todos los servidores de puntos de distribución (o grupos de puntos de distribución, según la jerarquía de Configuration Manager) a la lista y, después, seleccione **Siguiente.**</span><span class="sxs-lookup"><span data-stu-id="8bc24-369">Add all the distribution point servers (or distribution point groups, depending on your Configuration Manager hierarchy) to the list, and then select **Next**.</span></span>

    4.  <span data-ttu-id="8bc24-370">Seleccione **Siguiente** y, a continuación, **seleccione Cerrar.**</span><span class="sxs-lookup"><span data-stu-id="8bc24-370">Select **Next**, and then select **Close**.</span></span>

3.  <span data-ttu-id="8bc24-371">Distribuir paquetes de sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="8bc24-371">Distribute operating system packages.</span></span>

    1.  <span data-ttu-id="8bc24-372">En la consola de Configuration Manager, vaya **a** Imágenes de sistema operativo de la biblioteca de \>  \> **software.**</span><span class="sxs-lookup"><span data-stu-id="8bc24-372">In the Configuration Manager console, go to **Software Library** \> **Operating Systems** \> **Operating System Images**.</span></span> <span data-ttu-id="8bc24-373">Seleccione todas las imágenes del sistema operativo que quiera distribuir y, después, **seleccione Distribuir contenido.**</span><span class="sxs-lookup"><span data-stu-id="8bc24-373">Select all the operating system images you want to distribute, and then select **Distribute Content**.</span></span>

    2.  <span data-ttu-id="8bc24-374">Revisa la lista de paquetes y, a continuación, selecciona **Siguiente.**</span><span class="sxs-lookup"><span data-stu-id="8bc24-374">Review the list of packages, and then select **Next**.</span></span>

    3.  <span data-ttu-id="8bc24-375">Agregue todos los servidores de puntos de distribución (o grupos de puntos de distribución, según la jerarquía de Configuration Manager) a la lista y, después, seleccione **Siguiente.**</span><span class="sxs-lookup"><span data-stu-id="8bc24-375">Add all the distribution point servers (or distribution point groups, depending on your Configuration Manager hierarchy) to the list, and then select **Next**.</span></span>

    4.  <span data-ttu-id="8bc24-376">Seleccione **Siguiente** y, a continuación, **seleccione Cerrar.**</span><span class="sxs-lookup"><span data-stu-id="8bc24-376">Select **Next**, and then select **Close**.</span></span>

> [!NOTE]
> <span data-ttu-id="8bc24-377">La distribución de paquetes puede tardar algún tiempo, dependiendo del tamaño del paquete, la jerarquía de Configuration Manager, el número de servidores de puntos de distribución y el ancho de banda disponible en su red.</span><span class="sxs-lookup"><span data-stu-id="8bc24-377">Package distribution might take some time, depending on the package size, Configuration Manager hierarchy, number of distribution point servers, and the bandwidth available in your network.</span></span>
> 
> <span data-ttu-id="8bc24-378">Todos los paquetes deben distribuirse antes de empezar a implementar una unidad de Microsoft Teams Rooms.</span><span class="sxs-lookup"><span data-stu-id="8bc24-378">All the packages must be distributed before you can start deploying a Microsoft Teams Rooms unit.</span></span>
> 
> <span data-ttu-id="8bc24-379">Para revisar el estado de la distribución de paquetes en la consola de Configuration Manager, vaya a Supervisar **el estado** \> **del contenido de la** \> **distribución.**</span><span class="sxs-lookup"><span data-stu-id="8bc24-379">You can review the status of your package distribution in the Configuration Manager console by going to **Monitoring** \> **Distribution Status** \> **Content Status**.</span></span>

## <a name="configuration-manager-task-sequences"></a><span data-ttu-id="8bc24-380">Secuencias de tareas de Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="8bc24-380">Configuration Manager task sequences</span></span>

<span data-ttu-id="8bc24-381">Use secuencias de tareas con Configuration Manager para automatizar los pasos para implementar una imagen de sistema operativo en un equipo de destino.</span><span class="sxs-lookup"><span data-stu-id="8bc24-381">You use task sequences with Configuration Manager to automate the steps for deploying an operating system image to a destination computer.</span></span> <span data-ttu-id="8bc24-382">Para implementar una unidad de Salas de Microsoft Teams de forma automatizada, cree una secuencia de tareas que haga referencia a la imagen de arranque usada para iniciar el equipo de Microsoft Teams Rooms de destino, la imagen del sistema operativo Windows 10 Enterprise que desea instalar y cualquier otro contenido adicional, como otras aplicaciones o actualizaciones de software.</span><span class="sxs-lookup"><span data-stu-id="8bc24-382">To deploy a Microsoft Teams Rooms unit in an automated fashion, you create a task sequence that references the boot image used to start the destination Microsoft Teams Rooms computer, the Windows 10 Enterprise operating system image that you want to install, and any other additional content, such as other applications or software updates.</span></span>

### <a name="import-the-sample-task-sequence"></a><span data-ttu-id="8bc24-383">Importar la secuencia de tareas de ejemplo</span><span class="sxs-lookup"><span data-stu-id="8bc24-383">Import the sample task sequence</span></span>

<span data-ttu-id="8bc24-384">Puede descargar e importar fácilmente una secuencia de tareas de ejemplo y personalizarla para satisfacer sus necesidades.</span><span class="sxs-lookup"><span data-stu-id="8bc24-384">You can download and easily import a sample task sequence and customize it to meet your needs.</span></span>

1.  <span data-ttu-id="8bc24-385">[**Descargue**](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true) la secuencia de tareas de ejemplo y copie el archivo zip descargado en una ubicación compartida.</span><span class="sxs-lookup"><span data-stu-id="8bc24-385">[**Download**](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true) the sample task sequence, and copy the downloaded zip file to a shared location.</span></span>
2.  <span data-ttu-id="8bc24-386">En la consola del Administrador de configuración, vaya **a** Secuencias de tareas de sistemas operativos de la biblioteca de software y, a \>  \> continuación, seleccione **Importar secuencia de tareas.**</span><span class="sxs-lookup"><span data-stu-id="8bc24-386">In the Configuration Manager console, go to **Software Library** \> **Operating Systems** \> **Task Sequences**, and then select **Import Task Sequence**.</span></span>

3.  <span data-ttu-id="8bc24-387">Seleccione **Examinar,** vaya a la ubicación de la carpeta compartida que usó en el paso 1, seleccione el archivo zip Implementación de Salas de **Microsoft Teams (EN-US)** y, después, seleccione **Siguiente.**</span><span class="sxs-lookup"><span data-stu-id="8bc24-387">Select **Browse**, go to the shared folder location you used in step 1, select the **Microsoft Teams Rooms Deployment (EN-US).zip** file, and then select **Next**.</span></span>

4.  <span data-ttu-id="8bc24-388">Establezca **la** acción **en Crear** nuevo y, a continuación, seleccione **Siguiente.**</span><span class="sxs-lookup"><span data-stu-id="8bc24-388">Set **Action** to **Create New**, and then select **Next**.</span></span>

5.  <span data-ttu-id="8bc24-389">Confirme la configuración y, a continuación, seleccione **Siguiente.**</span><span class="sxs-lookup"><span data-stu-id="8bc24-389">Confirm the settings, and then select **Next**.</span></span>

6.  <span data-ttu-id="8bc24-390">Seleccione **Cerrar.**</span><span class="sxs-lookup"><span data-stu-id="8bc24-390">Select **Close**.</span></span>

### <a name="validate-that-the-reference-packages-are-correctly-linked-to-each-task-sequence-step"></a><span data-ttu-id="8bc24-391">Valide que los paquetes de referencia están vinculados correctamente a cada paso de secuencia de tareas.</span><span class="sxs-lookup"><span data-stu-id="8bc24-391">Validate that the reference packages are correctly linked to each task sequence step.</span></span>

1. <span data-ttu-id="8bc24-392">Seleccione la secuencia de tareas importada y, a continuación, **seleccione Editar.**</span><span class="sxs-lookup"><span data-stu-id="8bc24-392">Select the imported task sequence, and then select **Edit**.</span></span>

    <span data-ttu-id="8bc24-393">El Editor de secuencia de tareas se abre y muestra cada paso secuencial que necesita para implementar y configurar una unidad de Salas de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="8bc24-393">The Task Sequence Editor opens and displays each sequential step that you need to deploy and configure a Microsoft Teams Rooms unit.</span></span>

2. <span data-ttu-id="8bc24-394">Siga cada paso y complete las actualizaciones recomendadas:</span><span class="sxs-lookup"><span data-stu-id="8bc24-394">Walk through each step and complete the recommended updates:</span></span>

   1. <span data-ttu-id="8bc24-395">**Reiniciar en Windows PE:** este paso se reinicia y, a continuación, se reactiva el equipo a PXE de Windows.</span><span class="sxs-lookup"><span data-stu-id="8bc24-395">**Restart in Windows PE**: This step restarts and then boots the computer into Windows PXE.</span></span> <span data-ttu-id="8bc24-396">No es necesario realizar ningún cambio en este paso.</span><span class="sxs-lookup"><span data-stu-id="8bc24-396">No changes are required for this step.</span></span>

   2. <span data-ttu-id="8bc24-397">**Partición del disco 0 - UEFI:** este paso borra la configuración del disco y crea particiones según la configuración configurada.</span><span class="sxs-lookup"><span data-stu-id="8bc24-397">**Partition Disk 0 – UEFI**: This step wipes the disk configuration and creates partitions based on the configured settings.</span></span> <span data-ttu-id="8bc24-398">Le recomendamos que no realice ningún cambio en este paso.</span><span class="sxs-lookup"><span data-stu-id="8bc24-398">We recommend that you not make any changes to this step.</span></span>

   3. <span data-ttu-id="8bc24-399">Establecer el nombre del equipo **SRS:** en este paso se incluye una aplicación HTML para proporcionar una interfaz de usuario con el fin de establecer un nombre de equipo para las unidades de salas de Microsoft Teams durante la implementación.</span><span class="sxs-lookup"><span data-stu-id="8bc24-399">**Set SRS Computer Name**: This step includes an HTML application to provide a UI to set a computer name for the Microsoft Teams Rooms unit during the deployment.</span></span>
      -  <span data-ttu-id="8bc24-400">Este paso es opcional, pero solo se puede deshabilitar si desea administrar los nombres del equipo a través de un proceso alternativo.</span><span class="sxs-lookup"><span data-stu-id="8bc24-400">This is an optional step, but it can only be disabled if you want to manage computer naming through an alternate process.</span></span>
      -  <span data-ttu-id="8bc24-401">Compruebe que el **paquete SRS v2 - Set-SRSComputerName** está seleccionado.</span><span class="sxs-lookup"><span data-stu-id="8bc24-401">Verify that the **SRS v2 - Set-SRSComputerName** package is selected.</span></span> <span data-ttu-id="8bc24-402">Si no es así, busca el paquete y selecciónelo.</span><span class="sxs-lookup"><span data-stu-id="8bc24-402">If it isn't, browse to the package and select it.</span></span>

   4. <span data-ttu-id="8bc24-403">**Aplicar sistema operativo:** en este paso se especifica la imagen del sistema operativo que se va a implementar y el archivo de respuesta Sysprep desatendida que se usará.</span><span class="sxs-lookup"><span data-stu-id="8bc24-403">**Apply Operating System**: This step specifies the operating system image to be deployed and the unattended Sysprep answer file to use.</span></span>
      -  <span data-ttu-id="8bc24-404">Compruebe que está seleccionado el archivo de imagen del sistema operativo Windows 10 Enterprise correcto.</span><span class="sxs-lookup"><span data-stu-id="8bc24-404">Verify that the correct Windows 10 Enterprise operating system image file is selected.</span></span>
      -  <span data-ttu-id="8bc24-405">Compruebe que está habilitado el uso de un archivo de respuesta **de sysprep** o desatendida para una instalación personalizada y que el **paquete SRS v2 - Sysprep** está seleccionado.</span><span class="sxs-lookup"><span data-stu-id="8bc24-405">Verify that **Use an unattended or Sysprep answer file for a custom installation** is enabled, and the **SRS v2 - Sysprep Package** is selected.</span></span> <span data-ttu-id="8bc24-406">Asegúrese también de que **el nombre de** archivo esté **unattend.xml.**</span><span class="sxs-lookup"><span data-stu-id="8bc24-406">Also ensure that **File Name** is set to **unattend.xml**.</span></span>

   5. <span data-ttu-id="8bc24-407">**Aplicar la configuración de Windows:** este paso recopila información sobre la instalación de Windows.</span><span class="sxs-lookup"><span data-stu-id="8bc24-407">**Apply Windows Settings**: This step gathers information about the Windows installation.</span></span>
      -  <span data-ttu-id="8bc24-408">Proporcione información de licencias y registro, incluida la clave de producto, la contraseña de la cuenta de administrador local y la zona horaria (según sus necesidades).</span><span class="sxs-lookup"><span data-stu-id="8bc24-408">Provide licensing and registration information including the product key, local administrator account password, and time zone (depending on your needs).</span></span>

   6. <span data-ttu-id="8bc24-409">**Aplicar la configuración de** red: este paso le permite especificar un grupo de trabajo o un nombre de dominio de Active Directory y una unidad organizativa.</span><span class="sxs-lookup"><span data-stu-id="8bc24-409">**Apply Network Settings**: This step allows you to specify a workgroup or Active Directory domain name and organizational unit.</span></span>
      > [!NOTE]
      > <span data-ttu-id="8bc24-410">Consulte [consideraciones para unirse](domain-joining-considerations.md) a un dominio de Sistema de salas de Skype para conocer las acciones recomendadas que debe realizar al implementar unidades de Salas de Microsoft Teams como miembros de un dominio del directorio de Actve.</span><span class="sxs-lookup"><span data-stu-id="8bc24-410">See [Skype Room System domain joining considerations](domain-joining-considerations.md) for recommended actions you need to take in deploying Microsoft Teams Rooms units as members of an Actve Directory domain.</span></span>
   7. <span data-ttu-id="8bc24-411">**Aplicar controladores:** Este paso y sus sub steps se usan para implementar el firmware y los controladores de dispositivo aplicables en función del modelo de Surface Pro que tenga.</span><span class="sxs-lookup"><span data-stu-id="8bc24-411">**Apply Drivers:** This step and its sub-steps are used to deploy applicable device drivers and firmware based on the Surface Pro model you have.</span></span> <span data-ttu-id="8bc24-412">Actualice cada paso para especificar el paquete de controlador relevante asociado a esta implementación.</span><span class="sxs-lookup"><span data-stu-id="8bc24-412">Update each step to specify the relevant driver package associated with this deployment.</span></span>
      -   <span data-ttu-id="8bc24-413">Cada paquete de controlador se configura para aprovechar los filtros de Windows Management Se ha personalizado (ODBC) para implementar controladores y firmware relevantes en función de la marca y el modelo de Surface Pro.</span><span class="sxs-lookup"><span data-stu-id="8bc24-413">Each driver package is configured to leverage Windows Management Instrumentation (WMI) filters to deploy relevant drivers and firmware based on the Surface Pro make and model.</span></span>
      -   <span data-ttu-id="8bc24-414">Recomendamos encarecidamente no modificar la configuración de estos controladores, de lo contrario, la implementación podría producir un error.</span><span class="sxs-lookup"><span data-stu-id="8bc24-414">We highly recommend that you not alter the configuration of these drivers, otherwise deployment might fail.</span></span>

   8. <span data-ttu-id="8bc24-415">**Configurar Windows y Configuration Manager:** este paso implementa y configura el cliente de Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="8bc24-415">**Set up Windows and Configuration Manager**: This step deploys and configures the Configuration Manager client.</span></span> <span data-ttu-id="8bc24-416">Actualice este paso para especificar el paquete de cliente integrado de Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="8bc24-416">Update this step to specify the built-in Configuration Manager Client Package.</span></span>

   9. <span data-ttu-id="8bc24-417">**Instalar certificado raíz:** este paso distribuye el certificado raíz para dispositivos que no están unidos a un dominio y, por lo tanto, es opcional e deshabilitado de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="8bc24-417">**Install Root Certificate**: This step distributes the root certificate for non–domain-joined devices, and therefore is optional and disabled by default.</span></span>
      -   <span data-ttu-id="8bc24-418">Habilite este paso si necesita implementar un certificado raíz en las unidades de Salas de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="8bc24-418">Enable this step if you need to deploy a root certificate to the Microsoft Teams Rooms units.</span></span>
      -   <span data-ttu-id="8bc24-419">Si necesita realizar este paso, compruebe que la **srs v2 :** paquete de certificado raíz y deshabilitar el redireccionamiento del sistema de archivos de **64** bits están seleccionados.</span><span class="sxs-lookup"><span data-stu-id="8bc24-419">If you do need to perform this step, verify that the **SRS v2 – Root Certificate Package** and **Disable 64-bit file system redirection** are selected.</span></span>

   10. <span data-ttu-id="8bc24-420">**Instalar y configurar** el agente de supervisión: este paso instala la versión de 64 bits del agente de Microsoft Azure Monitor y configura el agente para conectarse a su área de trabajo de Log Analytics.</span><span class="sxs-lookup"><span data-stu-id="8bc24-420">**Install and Configure Monitoring Agent**: This step installs the 64-bit version of the Microsoft Azure Monitor agent and configures the agent to connect to your Log Analytics workspace.</span></span>
       -   <span data-ttu-id="8bc24-421">Este paso está deshabilitado de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="8bc24-421">This step is disabled by default.</span></span> <span data-ttu-id="8bc24-422">Habilite este paso solo si va a usar el agente de supervisión para supervisar el estado de las unidades de Microsoft Teams Rooms.</span><span class="sxs-lookup"><span data-stu-id="8bc24-422">Enable this step only if you're going to use the Monitoring Agent to monitor the health of your Microsoft Teams Rooms units.</span></span>
       -   <span data-ttu-id="8bc24-423">Edite este paso y actualice los parámetros de la línea de comandos para especificar el **id. del área de trabajo y** la clave del área de **trabajo.**</span><span class="sxs-lookup"><span data-stu-id="8bc24-423">Edit this step and update the command-line parameters to specify your **Workspace ID** and **Workspace Key**.</span></span>
       -   <span data-ttu-id="8bc24-424">Vea [Configurar dispositivos de prueba de Azure Monitoring para](azure-monitor-deploy.md#configure-test-devices-for-azure-monitoring) obtener más información sobre cómo obtener el id. de área de trabajo del conjunto de aplicaciones de administración de operaciones y la clave principal.</span><span class="sxs-lookup"><span data-stu-id="8bc24-424">See [Configure test devices for Azure Monitoring](azure-monitor-deploy.md#configure-test-devices-for-azure-monitoring) for more information about obtaining the Operations Management Suite Workspace ID and the primary key.</span></span>
       -   <span data-ttu-id="8bc24-425">Compruebe que las **funciones SRS v2 : Paquete del agente** de supervisión de Microsoft y Deshabilitar el redireccionamiento del sistema de archivos de **64** bits están seleccionadas.</span><span class="sxs-lookup"><span data-stu-id="8bc24-425">Verify that the **SRS v2 – Microsoft Monitoring Agent Package** and **Disable 64-bit file system redirection** are selected.</span></span>
       -   <span data-ttu-id="8bc24-426">Para obtener más información sobre cómo supervisar el mantenimiento de la implementación de salas de Microsoft Teams, vea Planear la administración de salas de Microsoft Teams con [Azure Monitor,](azure-monitor-plan.md)Implementar la administración de salas de Microsoft Teams con [Azure Monitor](azure-monitor-deploy.md) y administrar dispositivos de Salas de Microsoft Teams con [Azure Monitor.](azure-monitor-manage.md)</span><span class="sxs-lookup"><span data-stu-id="8bc24-426">For more information about monitoring the health of your Microsoft Teams Rooms deployment, see [Plan Microsoft Teams Rooms management with Azure Monitor](azure-monitor-plan.md), [Deploy Microsoft Teams Rooms management with Azure Monitor](azure-monitor-deploy.md) and [Manage Microsoft Teams Rooms devices with Azure Monitor](azure-monitor-manage.md).</span></span>

   11. <span data-ttu-id="8bc24-427">**Copiar archivos de configuración SRS v2:** este paso copia los archivos de configuración y configuración necesarios del kit de implementación de Salas de Microsoft Teams en la unidad de disco duro local.</span><span class="sxs-lookup"><span data-stu-id="8bc24-427">**Copy SRS v2 Configuration Files**: This step copies the required setup and configuration files from the Microsoft Teams Rooms deployment kit to the local hard drive.</span></span> <span data-ttu-id="8bc24-428">No se requiere personalización para este paso.</span><span class="sxs-lookup"><span data-stu-id="8bc24-428">No customization is required for this step.</span></span>
       -   <span data-ttu-id="8bc24-429">Compruebe que las **aplicaciones SRS v2 – SRS Application Package** y Disable **64-bit file system redirection** are selected.</span><span class="sxs-lookup"><span data-stu-id="8bc24-429">Verify that the **SRS v2 – SRS Application Package** and **Disable 64-bit file system redirection** are selected.</span></span>

   12. <span data-ttu-id="8bc24-430">**Install-SRSv2-OS-Updates:** en este paso se implementan las actualizaciones obligatorias del sistema operativo necesarias en la implementación de Salas de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="8bc24-430">**Install-SRSv2-OS-Updates**: This step deploys any mandatory operating system updates required with the Microsoft Teams Rooms deployment.</span></span> <span data-ttu-id="8bc24-431">Haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="8bc24-431">Do the following:</span></span>
       -   <span data-ttu-id="8bc24-432">Compruebe [Configurar una consola de Salas de Microsoft Teams](console.md) para ver qué actualizaciones son necesarias.</span><span class="sxs-lookup"><span data-stu-id="8bc24-432">Check [Configure a Microsoft Teams Rooms console](console.md) to see which updates are required.</span></span>
       -   <span data-ttu-id="8bc24-433">Compruebe que el paquete de actualizaciones del sistema operativo **SRS v2** incluye todas las actualizaciones necesarias.</span><span class="sxs-lookup"><span data-stu-id="8bc24-433">Verify that your **SRS v2 – OS Updates Package** includes all the required updates.</span></span>
       -   <span data-ttu-id="8bc24-434">Compruebe que el **paquete de actualizaciones de SRS v2 - OS está** seleccionado.</span><span class="sxs-lookup"><span data-stu-id="8bc24-434">Verify that the **SRS v2 – OS Updates Package** is selected.</span></span>
       -   <span data-ttu-id="8bc24-435">Compruebe que la directiva de ejecución de PowerShell esté establecida en **Omitir.**</span><span class="sxs-lookup"><span data-stu-id="8bc24-435">Verify that the PowerShell execution policy is set to **Bypass**.</span></span>

   13. <span data-ttu-id="8bc24-436">**Reiniciar Equipo:** este paso reinicia el equipo después de instalar las actualizaciones de sistema operativo obligatorias.</span><span class="sxs-lookup"><span data-stu-id="8bc24-436">**Restart Computer**: This step reboots the computer after the mandatory operating system updates are installed.</span></span> <span data-ttu-id="8bc24-437">No se requiere personalización para este paso.</span><span class="sxs-lookup"><span data-stu-id="8bc24-437">No customization is required for this step.</span></span>

   14. <span data-ttu-id="8bc24-438">**Configurar componentes de Windows:** este paso configura las características de Windows necesarias.</span><span class="sxs-lookup"><span data-stu-id="8bc24-438">**Configure Windows Components**: This step configures the required Windows features.</span></span> <span data-ttu-id="8bc24-439">No se requiere personalización para este paso.</span><span class="sxs-lookup"><span data-stu-id="8bc24-439">No customization is required for this step.</span></span>

   15. <span data-ttu-id="8bc24-440">**Reiniciar Equipo:** este paso reinicia el equipo después de configurar las características de Windows.</span><span class="sxs-lookup"><span data-stu-id="8bc24-440">**Restart Computer**: This step reboots the computer after the Windows features are configured.</span></span> <span data-ttu-id="8bc24-441">No se requiere personalización para este paso.</span><span class="sxs-lookup"><span data-stu-id="8bc24-441">No customization is required for this step.</span></span>

   16. <span data-ttu-id="8bc24-442">**Agregar usuario de Skype local:** este paso crea la cuenta de Skype local que se usa para iniciar sesión automáticamente en Windows e iniciar la aplicación Salas de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="8bc24-442">**Add Local Skype User**: This step creates the local Skype account used to automatically sign in to Windows and start the Microsoft Teams Rooms application.</span></span> <span data-ttu-id="8bc24-443">Este paso no tiene ningún paquete de software asociado y no se requiere personalización para él.</span><span class="sxs-lookup"><span data-stu-id="8bc24-443">This step doesn't have any software package associated with it, and no customization is required for it.</span></span>

   17. <span data-ttu-id="8bc24-444">**Configurar y configurar la aplicación SRS:** este paso configura la instalación de la aplicación Salas de Microsoft Teams para el próximo arranque del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="8bc24-444">**Set up and configure SRS application**: This step configures the Microsoft Teams Rooms application installation for the next boot of the operating system.</span></span>
       -   <span data-ttu-id="8bc24-445">Compruebe que la **versión SRS v2:** configurar el paquete de instalación SRS y deshabilitar el redireccionamiento del sistema de archivos de **64** bits están seleccionadas.</span><span class="sxs-lookup"><span data-stu-id="8bc24-445">Verify that the **SRS v2 – Configure SRS Setup Package** and **Disable 64-bit file system redirection** are selected.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8bc24-446">Es muy importante que los pasos de la secuencia de tareas deben estar en el orden proporcionado.</span><span class="sxs-lookup"><span data-stu-id="8bc24-446">It is very important that the task sequence steps must be in the provided order.</span></span> <span data-ttu-id="8bc24-447">Modificar el orden de los pasos o configurar pasos adicionales puede interrumpir la implementación.</span><span class="sxs-lookup"><span data-stu-id="8bc24-447">Modifying the order of steps, or configuring additional steps might break the deployment.</span></span>
>
> <span data-ttu-id="8bc24-448">**El paso de la aplicación SRS** de configuración y configuración debe ser el último paso de la secuencia de tareas; de lo contrario, podría producirse un error en la implementación.</span><span class="sxs-lookup"><span data-stu-id="8bc24-448">**Set up and configure SRS application** step must be the last step in the task sequence, otherwise the deployment might fail.</span></span>

### <a name="create-deployment-for-the-task-sequence"></a><span data-ttu-id="8bc24-449">Crear una implementación para la secuencia de tareas</span><span class="sxs-lookup"><span data-stu-id="8bc24-449">Create deployment for the task sequence</span></span>

1. <span data-ttu-id="8bc24-450">Seleccione la secuencia de tareas y, después, seleccione **Implementar.**</span><span class="sxs-lookup"><span data-stu-id="8bc24-450">Select the task sequence, and then select **Deploy**.</span></span>

2. <span data-ttu-id="8bc24-451">Seleccione **Examinar para** seleccionar una colección de destino para la implementación.</span><span class="sxs-lookup"><span data-stu-id="8bc24-451">Select **Browse** to select target collection for deployment.</span></span>

3. <span data-ttu-id="8bc24-452">Seleccione **Todos los equipos desconocidos** y, después, haga clic en **Aceptar.**</span><span class="sxs-lookup"><span data-stu-id="8bc24-452">Select **All Unknown Computers** and then select **OK**.</span></span>

4. <span data-ttu-id="8bc24-453">Seleccione **Siguiente.**</span><span class="sxs-lookup"><span data-stu-id="8bc24-453">Select **Next**.</span></span>

5. <span data-ttu-id="8bc24-454">Seleccione **Disponible** en la **lista desplegable** Propósito.</span><span class="sxs-lookup"><span data-stu-id="8bc24-454">Select **Available** on the **Purpose** drop down list.</span></span>

6. <span data-ttu-id="8bc24-455">Seleccione **Solo multimedia y PXE** en Hacer que esté disponible en la **siguiente** lista y, a continuación, seleccione **Siguiente.**</span><span class="sxs-lookup"><span data-stu-id="8bc24-455">Select **Only Media and PXE** in the **Make available to the following** list, and then select **Next**.</span></span>
   > [!WARNING]
   > <span data-ttu-id="8bc24-456">Es muy importante que **Purpose se** establezca en **Disponible.**</span><span class="sxs-lookup"><span data-stu-id="8bc24-456">It is very important that **Purpose** is set to **Available**.</span></span> <span data-ttu-id="8bc24-457">Asegúrese de que **la finalidad** **no esté** establecida en **Obligatorio.**</span><span class="sxs-lookup"><span data-stu-id="8bc24-457">Make sure that the **Purpose** is **NOT** set to **Required**.</span></span> <span data-ttu-id="8bc24-458">Asegúrese también de seleccionar Solo **multimedia y PXE** en **Hacer disponible para lo siguiente.**</span><span class="sxs-lookup"><span data-stu-id="8bc24-458">Also make sure that you select **Only Media and PXE** in the **Make available to the following**.</span></span>
   >
   > <span data-ttu-id="8bc24-459">Si establece estos valores en otra cosa, es posible que todos los equipos obtengan la imagen de implementación de Salas de Microsoft Teams al iniciarse.</span><span class="sxs-lookup"><span data-stu-id="8bc24-459">Setting these values to something else might cause all computers to get the Microsoft Teams Rooms deployment image when booted.</span></span>
7. <span data-ttu-id="8bc24-460">No especifique ninguna programación y seleccione **Siguiente.**</span><span class="sxs-lookup"><span data-stu-id="8bc24-460">Do not specify any schedule and select **Next**.</span></span>

8. <span data-ttu-id="8bc24-461">No cambie nada en la sección **Experiencia del** usuario y seleccione **Siguiente.**</span><span class="sxs-lookup"><span data-stu-id="8bc24-461">Do not change anything within the **User Experience** section and select **Next**.</span></span>

9. <span data-ttu-id="8bc24-462">No cambie nada en la sección **Alertas** y seleccione **Siguiente.**</span><span class="sxs-lookup"><span data-stu-id="8bc24-462">Do not change anything within the **Alerts** section and select **Next**.</span></span>

10. <span data-ttu-id="8bc24-463">No cambie nada en la sección **Puntos de distribución** y seleccione **Siguiente.**</span><span class="sxs-lookup"><span data-stu-id="8bc24-463">Do not change anything within the **Distribution Points** section and select **Next**.</span></span>

11. <span data-ttu-id="8bc24-464">Confirme la configuración y, a continuación, **seleccione Siguiente.**</span><span class="sxs-lookup"><span data-stu-id="8bc24-464">Confirm the settings and then select **Next**.</span></span>

12. <span data-ttu-id="8bc24-465">Seleccione **Cerrar.**</span><span class="sxs-lookup"><span data-stu-id="8bc24-465">Select **Close**.</span></span>

<a name="validate-and-troubleshoot-the-solution"></a><span data-ttu-id="8bc24-466">Validar y solucionar problemas de la solución</span><span class="sxs-lookup"><span data-stu-id="8bc24-466">Validate and troubleshoot the solution</span></span>
--------------------------------------

<span data-ttu-id="8bc24-467">Después de completar las secuencias de tareas de Microsoft Endpoint Configuration Manager, deberá realizar una ejecución de prueba para validar que la secuencia de tareas pueda implementar y configurar unidades de Salas de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="8bc24-467">After you've completed the Microsoft Endpoint Configuration Manager task sequences, you'll need to perform a test run to validate that the task sequence can deploy and configure Microsoft Teams Rooms units.</span></span>

1.  <span data-ttu-id="8bc24-468">Conecta el dispositivo de prueba a la red cableada usando uno de los adaptadores Ethernet compatibles o mediante Surface Dock.</span><span class="sxs-lookup"><span data-stu-id="8bc24-468">Connect the test device to the wired network by using one of the supported Ethernet adapters or using the Surface dock.</span></span> <span data-ttu-id="8bc24-469">Si la funcionalidad de arranque PXE no se ha configurado para su [](https://docs.microsoft.com/configmgr/osd/deploy-use/create-bootable-media) entorno, puede usar la imagen de arranque en la unidad flash USB que creó anteriormente para iniciar desde USB y conectarse a Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="8bc24-469">If PXE boot functionality hasn't been configured for your environment, you can use the boot image on the USB flash drive [that you created earlier](https://docs.microsoft.com/configmgr/osd/deploy-use/create-bootable-media) to boot from USB and connect to Configuration Manager.</span></span>

2.  <span data-ttu-id="8bc24-470">Obtenga acceso al firmware e inicie el inicio de PXE:</span><span class="sxs-lookup"><span data-stu-id="8bc24-470">Access the firmware and initiate PXE boot:</span></span>

    1.  <span data-ttu-id="8bc24-471">Asegúrate de que el dispositivo Surface esté apagado.</span><span class="sxs-lookup"><span data-stu-id="8bc24-471">Ensure the Surface device is powered off.</span></span>

    2.  <span data-ttu-id="8bc24-472">Mantenga presionado el botón **Subir** volumen.</span><span class="sxs-lookup"><span data-stu-id="8bc24-472">Press and hold the **Volume Up** button.</span></span>

    3.  <span data-ttu-id="8bc24-473">Presione y suelte el **botón Inicio/Apagado.**</span><span class="sxs-lookup"><span data-stu-id="8bc24-473">Press and release the **Power** button.</span></span>

    4.  <span data-ttu-id="8bc24-474">Cuando se empiece a iniciar el dispositivo, suelta el **botón Subir** volumen.</span><span class="sxs-lookup"><span data-stu-id="8bc24-474">After the device begins to boot, release the **Volume Up** button.</span></span>

    5.  <span data-ttu-id="8bc24-475">Seleccione **Configuración de arranque.**</span><span class="sxs-lookup"><span data-stu-id="8bc24-475">Select **Boot configuration**.</span></span>

    6.  <span data-ttu-id="8bc24-476">Realice una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="8bc24-476">Do one of the following:</span></span>

        -   <span data-ttu-id="8bc24-477">Seleccione **el arranque PXE** y arrástrelo hasta la parte superior de la lista.</span><span class="sxs-lookup"><span data-stu-id="8bc24-477">Select **PXE boot**, and drag it to the top of the list.</span></span> <span data-ttu-id="8bc24-478">Como alternativa, puedes deslizar a la izquierda en el adaptador de red para iniciar en el dispositivo inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="8bc24-478">Alternatively, you can swipe left on the network adapter to boot to the device immediately.</span></span> <span data-ttu-id="8bc24-479">Esto no afectará al orden de arranque.</span><span class="sxs-lookup"><span data-stu-id="8bc24-479">This won't affect the boot order.</span></span>
        -   <span data-ttu-id="8bc24-480">Selecciona la unidad flash USB que contiene el medio de arranque.</span><span class="sxs-lookup"><span data-stu-id="8bc24-480">Select the USB flash drive that holds the boot media.</span></span>

3.  <span data-ttu-id="8bc24-481">Seleccione **Salir** y, a continuación, **seleccione Reiniciar ahora.**</span><span class="sxs-lookup"><span data-stu-id="8bc24-481">Select **Exit**, and then select **Restart Now**.</span></span>

4.  <span data-ttu-id="8bc24-482">Cuando se le solicite, seleccione **Entrar para el** servicio de arranque de red.</span><span class="sxs-lookup"><span data-stu-id="8bc24-482">When prompted, select **Enter** for network boot service.</span></span>

5.  <span data-ttu-id="8bc24-483">Windows PE se cargará en la memoria y se iniciará el Asistente para secuencia de tareas.</span><span class="sxs-lookup"><span data-stu-id="8bc24-483">Windows PE will load into memory, and the Task Sequence Wizard will start.</span></span> <span data-ttu-id="8bc24-484">Selecciona **Siguiente** para continuar.</span><span class="sxs-lookup"><span data-stu-id="8bc24-484">Select **Next** to continue.</span></span>

6.  <span data-ttu-id="8bc24-485">Seleccione la secuencia de tareas que importó anteriormente y, a continuación, seleccione **Siguiente.**</span><span class="sxs-lookup"><span data-stu-id="8bc24-485">Select the task sequence that you imported earlier, and then select **Next**.</span></span>

7.  <span data-ttu-id="8bc24-486">Después de aplicar la configuración de disco, se le pedirá que especifique un nombre de equipo para el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="8bc24-486">After the disk configuration is applied, you'll be prompted to specify a computer name for the device.</span></span> <span data-ttu-id="8bc24-487">La interfaz de usuario mostrará un nombre de equipo recomendado según el número de serie del dispositivo Surface Pro.</span><span class="sxs-lookup"><span data-stu-id="8bc24-487">The user interface will display a recommended computer name based on the serial number of the Surface Pro device.</span></span> <span data-ttu-id="8bc24-488">Puede aceptar el nombre propuesto o especificar uno nuevo.</span><span class="sxs-lookup"><span data-stu-id="8bc24-488">You can either accept the proposed name or specify a new one.</span></span> <span data-ttu-id="8bc24-489">Siga las instrucciones que aparecen en la pantalla de asignación de nombres de equipo.</span><span class="sxs-lookup"><span data-stu-id="8bc24-489">Follow the instructions on the computer name assignment screen.</span></span> <span data-ttu-id="8bc24-490">Al seleccionar **Aceptar,** se inicia la implementación.</span><span class="sxs-lookup"><span data-stu-id="8bc24-490">When you select **Accept**, the deployment begins.</span></span>

8.  <span data-ttu-id="8bc24-491">El resto del proceso de implementación es automático y no pide más entrada de usuarios.</span><span class="sxs-lookup"><span data-stu-id="8bc24-491">The rest of the deployment process is automatic and doesn't ask for any more user input.</span></span>

9.  <span data-ttu-id="8bc24-492">Cuando la secuencia de tareas de implementación termine de configurar el dispositivo, verá la pantalla de configuración siguiente que le pide que configure las opciones de la aplicación Microsoft Teams Rooms.</span><span class="sxs-lookup"><span data-stu-id="8bc24-492">After the deployment task sequence finishes configuring the device, you'll see the following configuration screen that asks you to configure the Microsoft Teams Rooms application settings.</span></span>

    ![Pantalla de configuración inicial de la aplicación Salas de Microsoft Teams](../media/room-systems-scale-image2.png)

10.  <span data-ttu-id="8bc24-494">Conecte Surface Pro a la consola Microsoft Teams Rooms y configure la configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="8bc24-494">Plug the Surface Pro into the Microsoft Teams Rooms console, and configure the application settings.</span></span>

11.  <span data-ttu-id="8bc24-495">Valide que las funcionalidades enumeradas [en salas de Microsoft Teams funcionan](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2) en el dispositivo implementado.</span><span class="sxs-lookup"><span data-stu-id="8bc24-495">Validate that the capabilities listed in [Microsoft Teams Rooms help](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2) are working on the deployed device.</span></span>


<span data-ttu-id="8bc24-496">Para solucionar problemas de instalación con errores, consulte el **archivo SMSTS.log,** que registra todos los pasos ejecutados en una secuencia de tareas de Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="8bc24-496">To troubleshoot a failed installation, check the **SMSTS.log** file, which logs all the steps executed in a Configuration Manager task sequence.</span></span>

<span data-ttu-id="8bc24-497">El archivo SMSTS.log se almacena en una de varias rutas de acceso, según la fase del proceso de compilación.</span><span class="sxs-lookup"><span data-stu-id="8bc24-497">The SMSTS.log file is stored on one of a number of paths, depending on the stage of the build process.</span></span> <span data-ttu-id="8bc24-498">Compruebe la tabla siguiente para identificar la ruta de acceso al archivo SMSTS.log.</span><span class="sxs-lookup"><span data-stu-id="8bc24-498">Check the following table to identify the path to the SMSTS.log file.</span></span>


| <span data-ttu-id="8bc24-499">**Fase de implementación**</span><span class="sxs-lookup"><span data-stu-id="8bc24-499">**Deployment phase**</span></span>                                                            | <span data-ttu-id="8bc24-500">**Ruta de registro de secuencia de tareas**</span><span class="sxs-lookup"><span data-stu-id="8bc24-500">**Task sequence log path**</span></span>                         |
|---------------------------------------------------------------------------------|----------------------------------------------------|
| <span data-ttu-id="8bc24-501">WinPE, antes del formato JPEG</span><span class="sxs-lookup"><span data-stu-id="8bc24-501">WinPE, before HDD format</span></span>                                                        | <span data-ttu-id="8bc24-502">X: \\ Windows \\ Temp \\ smstslog \\ smsts.log</span><span class="sxs-lookup"><span data-stu-id="8bc24-502">X:\\Windows\\Temp\\smstslog\\smsts.log</span></span>             |
| <span data-ttu-id="8bc24-503">WinPE, después del formato JPEG</span><span class="sxs-lookup"><span data-stu-id="8bc24-503">WinPE, after HDD format</span></span>                                                         | <span data-ttu-id="8bc24-504">C: \\ _SMSTaskSequence \\ Registros \\ smstslog \\ smsts.log</span><span class="sxs-lookup"><span data-stu-id="8bc24-504">C:\\_SMSTaskSequence\\Logs\\Smstslog\\smsts.log</span></span>    |
| <span data-ttu-id="8bc24-505">Sistema operativo implementado, antes de instalar el agente de Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="8bc24-505">Operating system deployed, before the Configuration Manager agent was installed</span></span> | <span data-ttu-id="8bc24-506">c: \\ _SMSTaskSequence \\ Registros \\ smstslog \\ smsts.log</span><span class="sxs-lookup"><span data-stu-id="8bc24-506">c:\\_SMSTaskSequence\\Logs\\Smstslog\\smsts.log</span></span>    |
| <span data-ttu-id="8bc24-507">Sistema operativo y agente de Configuration Manager implementados</span><span class="sxs-lookup"><span data-stu-id="8bc24-507">Operating system and the Configuration Manager agent deployed</span></span>                   | <span data-ttu-id="8bc24-508">%windir% \\ System32 \\ ccm logs \\ \\ Smstslog \\ smsts.log</span><span class="sxs-lookup"><span data-stu-id="8bc24-508">%windir%\\System32\\ccm\\logs\\Smstslog\\smsts.log</span></span> |
| <span data-ttu-id="8bc24-509">Ejecución completada de la secuencia de tareas</span><span class="sxs-lookup"><span data-stu-id="8bc24-509">Task sequence execution complete</span></span>                                                | <span data-ttu-id="8bc24-510">%windir% \\ System32 \\ ccm logs \\ \\ smsts.log</span><span class="sxs-lookup"><span data-stu-id="8bc24-510">%windir%\\System32\\ccm\\logs\\smsts.log</span></span>           |

> [!TIP]
> <span data-ttu-id="8bc24-511">Puedes seleccionar **F8 en cualquier** momento durante la secuencia de tareas para abrir una consola de comandos y, a continuación, obtener acceso al archivo SMSTS.log.</span><span class="sxs-lookup"><span data-stu-id="8bc24-511">You can select **F8** at any time during the task sequence to open a command console, and then get access to the SMSTS.log file.</span></span>

<span data-ttu-id="8bc24-512">Para solucionar problemas de arranque pxe, compruebe los dos archivos de registro en el servidor de Configuration Manager que son específicos de las acciones de PXE:</span><span class="sxs-lookup"><span data-stu-id="8bc24-512">To troubleshoot PXE boot issues, check the two log files on the Configuration Manager server that are specific to PXE actions:</span></span>

-   <span data-ttu-id="8bc24-513">**Pxecontrol.log,** ubicado en el directorio de registros de instalación de Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="8bc24-513">**Pxecontrol.log**, located in the Configuration Manager installation logs directory</span></span>

-   <span data-ttu-id="8bc24-514">**Smspxe.log,** ubicado en el directorio de registros del Punto de administración del Administrador de configuración (MP).</span><span class="sxs-lookup"><span data-stu-id="8bc24-514">**Smspxe.log**, located in Configuration Manager Management Point (MP) logs directory</span></span>

<span data-ttu-id="8bc24-515">Para obtener una lista completa de los archivos de registro que puede usar para solucionar más problemas en la instalación de Configuration Manager, consulte la referencia del archivo de registro de Microsoft Endpoint Configuration [Manager.](https://docs.microsoft.com/configmgr/core/plan-design/hierarchy/log-files)</span><span class="sxs-lookup"><span data-stu-id="8bc24-515">For a complete list of the log files that you can use to further troubleshoot your Configuration Manager installation, see the Microsoft Endpoint Configuration Manager [Log file reference](https://docs.microsoft.com/configmgr/core/plan-design/hierarchy/log-files).</span></span>
