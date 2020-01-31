---
title: Implementar salas de Microsoft Teams con el administrador de configuración de Microsoft Endpoint
author: lanachin
ms.author: v-lanac
ms.reviewer: Turgayo
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.service: msteams
localization_priority: Normal
ms.custom: Strat_SB_Admin
ms.assetid: 678689e4-d547-499b-be64-7d8f16dd8668
ms.collection:
- M365-collaboration
description: Lea este tema para obtener información sobre la implementación de salas de Microsoft Teams en implementaciones de gran escala.
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
ms.openlocfilehash: 3735553c1d2c0cc1b0d7e6065be606b69337e9cc
ms.sourcegitcommit: ed3a6789dedf54275e0b1ab41d4a4230eed6eb72
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2020
ms.locfileid: "41628646"
---
# <a name="deploy-microsoft-teams-rooms-by-using-microsoft-endpoint-configuration-manager"></a><span data-ttu-id="468b6-103">Implementar salas de Microsoft Teams con el administrador de configuración de Microsoft Endpoint</span><span class="sxs-lookup"><span data-stu-id="468b6-103">Deploy Microsoft Teams Rooms by using Microsoft Endpoint Configuration Manager</span></span>

<span data-ttu-id="468b6-104">Este artículo le proporciona toda la información necesaria para crear implementaciones de salas de Microsoft Teams mediante el uso de Microsoft Endpoint Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="468b6-104">This article gives you all the necessary information to create your Microsoft Teams Rooms deployments by using Microsoft Endpoint Configuration Manager.</span></span>

<span data-ttu-id="468b6-105">Con los métodos fáciles de usar proporcionados por Configuration Manager, puede implementar el sistema operativo y otras aplicaciones en varios dispositivos de destino.</span><span class="sxs-lookup"><span data-stu-id="468b6-105">With the easy-to-use methods provided by Configuration Manager, you can deploy the operating system and other applications to multiple target devices.</span></span>

<span data-ttu-id="468b6-106">Use el método que se muestra a continuación para guiarse a través de la configuración de Configuration Manager y personalizar los paquetes de ejemplo y los scripts proporcionados en esta guía según sea necesario para su organización.</span><span class="sxs-lookup"><span data-stu-id="468b6-106">Use the approach illustrated below to guide you through your Configuration Manager configuration, and customize the sample packages and scripts provided throughout this guidance as needed for your organization.</span></span>

![Proceso de implementación de salas de Microsoft Teams con Configuration Manager](../media/room-systems-scale-image1.png)

> [!IMPORTANT]
> <span data-ttu-id="468b6-108">Esta solución solo ha sido probada con implementaciones basadas en Surface Pro.</span><span class="sxs-lookup"><span data-stu-id="468b6-108">This solution has only been tested with Surface Pro–based deployments.</span></span> <span data-ttu-id="468b6-109">Siga las instrucciones del fabricante para configuraciones que no se basan en Surface Pro.</span><span class="sxs-lookup"><span data-stu-id="468b6-109">Follow the manufacturer’s guidelines for configurations that aren’t based on Surface Pro.</span></span>

## <a name="validate-prerequisites"></a><span data-ttu-id="468b6-110">Validar los requisitos previos</span><span class="sxs-lookup"><span data-stu-id="468b6-110">Validate prerequisites</span></span>

<span data-ttu-id="468b6-111">Para implementar salas de Microsoft Teams con Configuration Manager, asegúrese de cumplir los siguientes requisitos y requisitos.</span><span class="sxs-lookup"><span data-stu-id="468b6-111">To deploy Microsoft Teams Rooms with Configuration Manager, ensure that you meet the following prerequisites and requirements.</span></span>

### <a name="microsoft-endpoint-configuration-manager-requirements"></a><span data-ttu-id="468b6-112">Requisitos del administrador de configuración de Microsoft Endpoint</span><span class="sxs-lookup"><span data-stu-id="468b6-112">Microsoft Endpoint Configuration Manager requirements</span></span>

-   <span data-ttu-id="468b6-113">La versión del administrador de configuración de Microsoft Endpoint debe ser de al menos 1706 o superior.</span><span class="sxs-lookup"><span data-stu-id="468b6-113">Microsoft Endpoint Configuration Manager version must be at least 1706 or above.</span></span> <span data-ttu-id="468b6-114">Le recomendamos que use 1710 o una versión posterior.</span><span class="sxs-lookup"><span data-stu-id="468b6-114">We recommend using 1710 or later.</span></span> <span data-ttu-id="468b6-115">Consulte [soporte técnico para Windows 10 en Configuration Manager](https://docs.microsoft.com/configmgr/core/plan-design/configs/support-for-windows-10#windows-10-as-a-client) para obtener información sobre las versiones de Windows 10 compatibles con Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="468b6-115">Check out [Support for Windows 10 in Configuration Manager](https://docs.microsoft.com/configmgr/core/plan-design/configs/support-for-windows-10#windows-10-as-a-client) to learn about the Windows 10 versions that Configuration Manager supports.</span></span>

-   <span data-ttu-id="468b6-116">Debe instalarse una versión compatible de Windows Assessment and Deployment Kit (ADK) para Windows 10.</span><span class="sxs-lookup"><span data-stu-id="468b6-116">A supported version of Windows Assessment and Deployment Kit (ADK) for Windows 10 must be installed.</span></span> <span data-ttu-id="468b6-117">Vea las versiones de [Windows 10 ADK](https://docs.microsoft.com/configmgr/core/plan-design/configs/support-for-windows-10#windows-10-adk) que puede usar con diferentes versiones de Configuration Manager y asegúrese de que su implementación incluya la versión correcta.</span><span class="sxs-lookup"><span data-stu-id="468b6-117">See the versions of the [Windows 10 ADK](https://docs.microsoft.com/configmgr/core/plan-design/configs/support-for-windows-10#windows-10-adk) that you can use with different versions of Configuration Manager, and ensure that your deployment includes the correct version.</span></span>

-   <span data-ttu-id="468b6-118">Los servidores del sistema de sitio deben tener asignado el rol de punto de distribución y las imágenes de arranque deben estar habilitadas para [admitir el entorno de ejecución de inicio previo (PXE)](https://docs.microsoft.com/configmgr/osd/deploy-use/use-pxe-to-deploy-windows-over-the-network) para habilitar implementaciones iniciadas por la red.</span><span class="sxs-lookup"><span data-stu-id="468b6-118">The site system servers must have been assigned the distribution point role, and the boot images should be enabled for [preboot execution environment (PXE) support](https://docs.microsoft.com/configmgr/osd/deploy-use/use-pxe-to-deploy-windows-over-the-network) to enable network-initiated deployments.</span></span> <span data-ttu-id="468b6-119">Si la compatibilidad con PXE no está habilitada, puede usar [medios de arranque](https://docs.microsoft.com/configmgr/osd/deploy-use/use-bootable-media-to-deploy-windows-over-the-network) para las implementaciones.</span><span class="sxs-lookup"><span data-stu-id="468b6-119">If PXE support isn’t enabled, you can use [bootable media](https://docs.microsoft.com/configmgr/osd/deploy-use/use-bootable-media-to-deploy-windows-over-the-network) for your deployments.</span></span>

-   <span data-ttu-id="468b6-120">Una cuenta de acceso a la red debe estar configurada para admitir nuevos escenarios de implementación de equipos.</span><span class="sxs-lookup"><span data-stu-id="468b6-120">A network access account must be configured to support new computer (bare metal) deployment scenarios.</span></span> <span data-ttu-id="468b6-121">Para obtener más información sobre la configuración de una cuenta de acceso de red, consulte [cuentas usadas en el administrador de configuración](https://docs.microsoft.com/configmgr/core/plan-design/hierarchy/manage-accounts-to-access-content#bkmk_NAA).</span><span class="sxs-lookup"><span data-stu-id="468b6-121">To learn more about the configuration of a network access account, see [Accounts used in Configuration Manager](https://docs.microsoft.com/configmgr/core/plan-design/hierarchy/manage-accounts-to-access-content#bkmk_NAA).</span></span>

-   <span data-ttu-id="468b6-122">Le recomendamos que habilite la [compatibilidad con multidifusión](https://docs.microsoft.com/configmgr/osd/deploy-use/use-multicast-to-deploy-windows-over-the-network), si es probable que implemente la misma imagen de salas de Microsoft Teams en varias unidades al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="468b6-122">We recommend that you enable [multicast support](https://docs.microsoft.com/configmgr/osd/deploy-use/use-multicast-to-deploy-windows-over-the-network), if you’re likely to deploy the same Microsoft Teams Rooms image to multiple units at the same time.</span></span>

### <a name="networking-requirements"></a><span data-ttu-id="468b6-123">Requisitos de red</span><span class="sxs-lookup"><span data-stu-id="468b6-123">Networking requirements</span></span>

-   <span data-ttu-id="468b6-124">Su red debe tener un servidor de protocolo de configuración dinámica de host (DHCP), configurado para la distribución automática de direcciones IP a las subredes donde se implementarán las unidades de salas de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="468b6-124">Your network should have a Dynamic Host Configuration Protocol (DHCP) server, configured for automatic IP address distribution to the subnets where Microsoft Teams Rooms units will be deployed.</span></span>

    > [!NOTE]
    > <span data-ttu-id="468b6-125">La duración de la concesión DHCP debe establecerse en un valor superior a la duración de la implementación de la imagen.</span><span class="sxs-lookup"><span data-stu-id="468b6-125">DHCP lease duration must be set to a value longer than the image deployment duration.</span></span> <span data-ttu-id="468b6-126">De lo contrario, la implementación podría fallar.</span><span class="sxs-lookup"><span data-stu-id="468b6-126">Otherwise, the deployment might fail.</span></span>

-   <span data-ttu-id="468b6-127">Su red, incluidos los conmutadores y las LANs virtuales (VLAN), debe estar configurada para admitir PXE.</span><span class="sxs-lookup"><span data-stu-id="468b6-127">Your network, including switches and virtual LANs (VLANs), should be configured to support PXE.</span></span> <span data-ttu-id="468b6-128">Para obtener más información sobre la ayuda de IP y la configuración de PXE, consulte su proveedor de red.</span><span class="sxs-lookup"><span data-stu-id="468b6-128">Refer to your network vendor for more information about IP Helper and PXE configuration.</span></span> <span data-ttu-id="468b6-129">Como alternativa, puede usar [medios de arranque](https://docs.microsoft.com/configmgr/osd/deploy-use/use-bootable-media-to-deploy-windows-over-the-network) para las implementaciones, si la compatibilidad con PXE no está habilitada.</span><span class="sxs-lookup"><span data-stu-id="468b6-129">Alternatively, you can use [bootable media](https://docs.microsoft.com/configmgr/osd/deploy-use/use-bootable-media-to-deploy-windows-over-the-network) for your deployments, if PXE support isn’t enabled.</span></span>

    > [!NOTE]
    > <span data-ttu-id="468b6-130">Para los dispositivos Surface Pro, el arranque desde la red (arranque PXE) solo se admite al usar un adaptador Ethernet o una estación de acoplamiento de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="468b6-130">For Surface Pro devices, booting from the network (PXE boot) is only supported when you use an Ethernet adapter or docking station from Microsoft.</span></span> <span data-ttu-id="468b6-131">Los adaptadores Ethernet de terceros no admiten el arranque PXE con Surface Pro.</span><span class="sxs-lookup"><span data-stu-id="468b6-131">Third-party Ethernet adapters don’t support PXE boot with Surface Pro.</span></span> <span data-ttu-id="468b6-132">Para obtener más información [, consulte adaptadores de Ethernet e implementación de superficies](https://docs.microsoft.com/surface/ethernet-adapters-and-surface-device-deployment) .</span><span class="sxs-lookup"><span data-stu-id="468b6-132">See [Ethernet adapters and Surface deployment](https://docs.microsoft.com/surface/ethernet-adapters-and-surface-device-deployment) for more information.</span></span>

## <a name="configure-microsoft-endpoint-configuration-manager-for-operating-system-deployment"></a><span data-ttu-id="468b6-133">Configurar Microsoft Endpoint Configuration Manager para la implementación de sistemas operativos</span><span class="sxs-lookup"><span data-stu-id="468b6-133">Configure Microsoft Endpoint Configuration Manager for operating system deployment</span></span>

<span data-ttu-id="468b6-134">En este artículo se supone que ya tiene una implementación correcta de Configuration Manager y no se detallan todos los pasos necesarios para implementar y configurar Configuration Manager desde cero.</span><span class="sxs-lookup"><span data-stu-id="468b6-134">This article assumes you already have a healthy Configuration Manager deployment, and doesn’t detail all the steps required to deploy and configure Configuration Manager from scratch.</span></span> <span data-ttu-id="468b6-135">La [documentación y las instrucciones de configuración](https://docs.microsoft.com/configmgr/) del Microsoft Endpoint Configuration Manager es un excelente recurso; le recomendamos que comience con estos recursos si todavía no ha implementado Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="468b6-135">The [documentation and the configuration guidance](https://docs.microsoft.com/configmgr/) on the Microsoft Endpoint Configuration Manager is a great resource; we recommend you start with these resources if you haven’t yet deployed Configuration Manager.</span></span>

<span data-ttu-id="468b6-136">Use las siguientes instrucciones para comprobar que las características de la implementación del sistema operativo (OSD) están configuradas correctamente.</span><span class="sxs-lookup"><span data-stu-id="468b6-136">Use the following instructions to verify that the operating system deployment (OSD) features are configured properly.</span></span>

### <a name="validate-and-upgrade-configuration-manager"></a><span data-ttu-id="468b6-137">Validar y actualizar Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="468b6-137">Validate and upgrade Configuration Manager</span></span>

1.  <span data-ttu-id="468b6-138">En la consola del administrador de configuración, vaya a **actualizaciones y mantenimiento**de la **Administración** \> .</span><span class="sxs-lookup"><span data-stu-id="468b6-138">In the Configuration Manager console, go to **Administration** \> **Updates and Servicing**.</span></span>

2.  <span data-ttu-id="468b6-139">Compruebe la compilación instalada y las actualizaciones aplicables que aún no se han instalado.</span><span class="sxs-lookup"><span data-stu-id="468b6-139">Check the installed build and applicable updates that haven’t been installed yet.</span></span>

3.  <span data-ttu-id="468b6-140">Revise el [soporte técnico para Windows 10 en el administrador de configuración](https://docs.microsoft.com/configmgr/core/plan-design/configs/support-for-windows-10#windows-10-as-a-client). Si necesita actualizar su implementación, seleccione la actualización que quiera instalar y, después, haga clic en **Descargar**.</span><span class="sxs-lookup"><span data-stu-id="468b6-140">Review [Support for Windows 10 in Configuration Manager](https://docs.microsoft.com/configmgr/core/plan-design/configs/support-for-windows-10#windows-10-as-a-client); if you need to upgrade your deployment, select the update you want to install, and then select **Download**.</span></span>

4.  <span data-ttu-id="468b6-141">Una vez completada la descarga, seleccione la actualización y, a continuación, seleccione **instalar paquete de actualización**.</span><span class="sxs-lookup"><span data-stu-id="468b6-141">After the download is complete, select the update, and then select **Install Update Pack**.</span></span>

### <a name="configure-distribution-points-to-support-pxe-and-multicast"></a><span data-ttu-id="468b6-142">Configurar puntos de distribución para admitir PXE y multicast</span><span class="sxs-lookup"><span data-stu-id="468b6-142">Configure distribution points to support PXE and multicast</span></span>

1.  <span data-ttu-id="468b6-143">En la consola del administrador de configuración, vaya a **puntos de distribución**de **Administración** \> .</span><span class="sxs-lookup"><span data-stu-id="468b6-143">In the Configuration Manager console, go to **Administration** \> **Distribution Points**.</span></span>

2.  <span data-ttu-id="468b6-144">Seleccione el servidor del punto de distribución que servirá a la implementación de salas de Microsoft Teams y, a continuación, seleccione **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="468b6-144">Select the distribution point server that will serve the Microsoft Teams Rooms deployment, and then select **Properties**.</span></span>

3.  <span data-ttu-id="468b6-145">Seleccione la pestaña **PXE** y asegúrese de que estén habilitadas las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="468b6-145">Select the **PXE** tab, and ensure that the following settings are enabled:</span></span>
    -   <span data-ttu-id="468b6-146">Habilitar la compatibilidad con PXE para clientes</span><span class="sxs-lookup"><span data-stu-id="468b6-146">Enable PXE support for clients</span></span>
    -   <span data-ttu-id="468b6-147">Permitir que este punto de distribución responda a solicitudes PXE entrantes</span><span class="sxs-lookup"><span data-stu-id="468b6-147">Allow this distribution point to respond to incoming PXE requests</span></span>
    -   <span data-ttu-id="468b6-148">Habilitar compatibilidad con equipos desconocidos</span><span class="sxs-lookup"><span data-stu-id="468b6-148">Enable unknown computer support</span></span>

4.  <span data-ttu-id="468b6-149">*Opcional:* Para habilitar la compatibilidad con multidifusión, seleccione la pestaña **multidifusión** y asegúrese de que estén habilitadas las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="468b6-149">*Optional:* To enable multicast support, select the **Multicast** tab, and ensure that the following settings are enabled:</span></span>
    -   <span data-ttu-id="468b6-150">Habilitar la multidifusión para enviar datos simultáneamente a varios clientes</span><span class="sxs-lookup"><span data-stu-id="468b6-150">Enable multicast to simultaneously send data to multiple clients</span></span>
    -   <span data-ttu-id="468b6-151">Configurar el intervalo de puertos UDP según la recomendación del equipo de red</span><span class="sxs-lookup"><span data-stu-id="468b6-151">Configure the UDP port range as per your network team’s recommendation</span></span>

### <a name="configure-the-network-access-account"></a><span data-ttu-id="468b6-152">Configurar la cuenta de acceso a la red</span><span class="sxs-lookup"><span data-stu-id="468b6-152">Configure the Network Access Account</span></span>

1.  <span data-ttu-id="468b6-153">En la consola del administrador de configuración, vaya a **sitios**de **configuración** \> del sitio de **Administración** \> y, después, seleccione el sitio.</span><span class="sxs-lookup"><span data-stu-id="468b6-153">In the Configuration Manager console, go to **Administration** \> **Site Configuration** \> **Sites**, and then select the site.</span></span>

2.  <span data-ttu-id="468b6-154">En el grupo **configuración** , seleccione **Configurar componentes** \> de sitio de **distribución de software**.</span><span class="sxs-lookup"><span data-stu-id="468b6-154">In the **Settings** group, select **Configure Site Components** \> **Software Distribution**.</span></span>

3.  <span data-ttu-id="468b6-155">Seleccione la pestaña **cuenta de acceso a la red** . configure una o más cuentas y, a continuación, seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="468b6-155">Select the **Network Access Account** tab. Set up one or more accounts, and then select **OK**.</span></span>

> [!NOTE]
> <span data-ttu-id="468b6-156">Las cuentas no necesitan derechos especiales, excepto **tener acceso a este equipo desde la red** en el servidor del punto de distribución.</span><span class="sxs-lookup"><span data-stu-id="468b6-156">The accounts don’t need any special rights, except for the **Access this computer from the network** right on the distribution point server.</span></span> <span data-ttu-id="468b6-157">Una cuenta de usuario de dominio genérico será adecuada.</span><span class="sxs-lookup"><span data-stu-id="468b6-157">A generic domain user account will be appropriate.</span></span> <span data-ttu-id="468b6-158">Para obtener más información, consulte [cuentas usadas en el administrador de configuración](https://docs.microsoft.com/configmgr/core/plan-design/hierarchy/manage-accounts-to-access-content#bkmk_NAA).</span><span class="sxs-lookup"><span data-stu-id="468b6-158">For more information, see [Accounts used in Configuration Manager](https://docs.microsoft.com/configmgr/core/plan-design/hierarchy/manage-accounts-to-access-content#bkmk_NAA).</span></span>

### <a name="configure-a-boot-image"></a><span data-ttu-id="468b6-159">Configurar una imagen de arranque</span><span class="sxs-lookup"><span data-stu-id="468b6-159">Configure a boot image</span></span>

1.  <span data-ttu-id="468b6-160">En la consola del administrador de configuración, vaya a **imágenes de inicio** **del sistema** \> operativo de la **biblioteca** \> de software.</span><span class="sxs-lookup"><span data-stu-id="468b6-160">In the Configuration Manager console, go to **Software Library** \> **Operating System** \> **Boot Images**.</span></span>

2.  <span data-ttu-id="468b6-161">Seleccione **imagen de arranque (x64)** y, a continuación, haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="468b6-161">Select **Boot image (x64)**, and then select **Properties**.</span></span>

3.  <span data-ttu-id="468b6-162">Seleccione la pestaña **origen de datos** y habilite **implementar esta imagen de inicio desde el punto de distribución habilitado para PXE**.</span><span class="sxs-lookup"><span data-stu-id="468b6-162">Select the **Data Source** tab, and enable **Deploy this boot image from the PXE-enabled distribution point**.</span></span>

4.  <span data-ttu-id="468b6-163">Seleccione la pestaña **componentes opcionales** para instalar los componentes necesarios:</span><span class="sxs-lookup"><span data-stu-id="468b6-163">Select the **Optional Components** tab to install required components:</span></span>

    1.  <span data-ttu-id="468b6-164">Seleccione el icono de estrella y busque **HTML (WinPE-HTA)** .</span><span class="sxs-lookup"><span data-stu-id="468b6-164">Select the star icon, and search for **HTML (WinPE-HTA)**</span></span>

    2.  <span data-ttu-id="468b6-165">Seleccione **Aceptar** para agregar compatibilidad de aplicaciones HTML en la imagen de inicio.</span><span class="sxs-lookup"><span data-stu-id="468b6-165">Select **OK** to add HTML application support in to the boot image.</span></span>

5.  <span data-ttu-id="468b6-166">*Opcional:* Para personalizar la experiencia de implementación, seleccione la pestaña **Personalización** .</span><span class="sxs-lookup"><span data-stu-id="468b6-166">*Optional:* To customize the deployment experience, select the **Customization** tab.</span></span>
    -   <span data-ttu-id="468b6-167">Habilite la **compatibilidad con comandos (solo pruebas)** si desea tener acceso a un símbolo del sistema durante la implementación.</span><span class="sxs-lookup"><span data-stu-id="468b6-167">Enable **command support (testing only)** if you want to have access to a command prompt during the deployment.</span></span> <span data-ttu-id="468b6-168">Cuando esta opción está habilitada, puede iniciar un símbolo del sistema seleccionando **F8** en cualquier momento de la implementación.</span><span class="sxs-lookup"><span data-stu-id="468b6-168">When this is enabled, you can start a command prompt by selecting **F8** at any time during the deployment.</span></span>
    -   <span data-ttu-id="468b6-169">También puede especificar una imagen de fondo personalizada para que se muestre durante la implementación.</span><span class="sxs-lookup"><span data-stu-id="468b6-169">You can also specify a custom background image to be displayed during the deployment.</span></span> <span data-ttu-id="468b6-170">Para establecer una imagen, habilite **especificar el archivo de imagen de fondo personalizado (ruta de acceso UNC** y seleccione el fondo.</span><span class="sxs-lookup"><span data-stu-id="468b6-170">To set an image, enable **Specify the custom background image file (UNC path** and select your background.</span></span>

6.  <span data-ttu-id="468b6-171">Cuando se le pida, seleccione **sí** y distribuir la imagen de arranque actualizada a los puntos de distribución.</span><span class="sxs-lookup"><span data-stu-id="468b6-171">When asked, select **Yes** and distribute the updated boot image to your distribution points.</span></span>

<span data-ttu-id="468b6-172">Para obtener más información, vea [administrar imágenes de arranque con Configuration Manager](https://docs.microsoft.com/configmgr/osd/get-started/manage-boot-images).</span><span class="sxs-lookup"><span data-stu-id="468b6-172">For more information, see [Manage boot images with Configuration Manager](https://docs.microsoft.com/configmgr/osd/get-started/manage-boot-images).</span></span>

> [!NOTE]
> <span data-ttu-id="468b6-173">Puede crear un medio USB de arranque para iniciar implementaciones basadas en secuencias de tareas de Configuration Manager para entornos que no tienen compatibilidad con PXE.</span><span class="sxs-lookup"><span data-stu-id="468b6-173">You can create a bootable USB media to initiate Configuration Manager task sequence–based deployments for environments that have no PXE support.</span></span> <span data-ttu-id="468b6-174">El medio de arranque contiene solo la imagen de arranque, los comandos de preinicio opcionales y los archivos necesarios, y los binarios de Configuration Manager para admitir el inicio en Windows PE y la conexión con Configuration Manager durante el resto del proceso de implementación.</span><span class="sxs-lookup"><span data-stu-id="468b6-174">The bootable media contains only the boot image, optional prestart commands and their required files, and Configuration Manager binaries to support booting into Windows PE and connecting to Configuration Manager for the rest of the deployment process.</span></span> <span data-ttu-id="468b6-175">Para obtener más información, consulte [creación de medios de arranque](https://docs.microsoft.com/configmgr/osd/deploy-use/create-bootable-media#BKMK_CreateBootableMedia).</span><span class="sxs-lookup"><span data-stu-id="468b6-175">For more information, see [Create bootable media](https://docs.microsoft.com/configmgr/osd/deploy-use/create-bootable-media#BKMK_CreateBootableMedia).</span></span>

## <a name="create-configuration-manager-packages"></a><span data-ttu-id="468b6-176">Crear paquetes de Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="468b6-176">Create Configuration Manager packages</span></span>

> [!IMPORTANT]
> <span data-ttu-id="468b6-177">La versión del sistema operativo necesaria para cada versión del instalador de SRS cambia con cada versión de MSI.</span><span class="sxs-lookup"><span data-stu-id="468b6-177">The required operating system version for each SRS installer version changes with every MSI release.</span></span> <span data-ttu-id="468b6-178">Para determinar la mejor versión del sistema operativo para un MSI determinado, ejecute la secuencia de comandos de configuración de consola una vez.</span><span class="sxs-lookup"><span data-stu-id="468b6-178">To determine the best operating system version for a given MSI, run the console setup script once.</span></span> <span data-ttu-id="468b6-179">Para obtener más información, consulte [implementar salas de Microsoft Teams mediante Microsoft Endpoint Configuration Manager](rooms-scale.md).</span><span class="sxs-lookup"><span data-stu-id="468b6-179">To learn more, see [Deploy Microsoft Teams Rooms by using Microsoft Endpoint Configuration Manager](rooms-scale.md).</span></span>

<span data-ttu-id="468b6-180">Configuration Manager requiere varios paquetes para implementar y configurar las unidades de salas de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="468b6-180">Configuration Manager requires a number of packages to deploy and configure the Microsoft Teams Rooms units.</span></span>

<span data-ttu-id="468b6-181">Debe crear y configurar los siguientes paquetes y, a continuación, distribuirlos a los sistemas de sitio de Configuration Manager a los que se les haya asignado el rol de servidor del punto de distribución.</span><span class="sxs-lookup"><span data-stu-id="468b6-181">You need to create and configure the following packages, and then distribute them to the Configuration Manager site systems that have been assigned the distribution point server role.</span></span>

| <span data-ttu-id="468b6-182">**Nombre del paquete**</span><span class="sxs-lookup"><span data-stu-id="468b6-182">**Package name**</span></span>                     | <span data-ttu-id="468b6-183">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="468b6-183">**Type**</span></span>               | <span data-ttu-id="468b6-184">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="468b6-184">**Description**</span></span>                                                                           |
|--------------------------------------|------------------------|-------------------------------------------------------------------------------------------|
| <span data-ttu-id="468b6-185">SRS V2: paquete de aplicaciones para SRS</span><span class="sxs-lookup"><span data-stu-id="468b6-185">SRS v2 - SRS Application Package</span></span>     | <span data-ttu-id="468b6-186">Paquete de software</span><span class="sxs-lookup"><span data-stu-id="468b6-186">Software package</span></span>       | <span data-ttu-id="468b6-187">Paquete para el kit de implementación de Microsoft Teams Rooms</span><span class="sxs-lookup"><span data-stu-id="468b6-187">Package for the Microsoft Teams Rooms deployment kit</span></span>                                      |
| <span data-ttu-id="468b6-188">SRS V2: paquete de Sysprep</span><span class="sxs-lookup"><span data-stu-id="468b6-188">SRS v2 - Sysprep Package</span></span>             | <span data-ttu-id="468b6-189">Paquete de software</span><span class="sxs-lookup"><span data-stu-id="468b6-189">Software package</span></span>       | <span data-ttu-id="468b6-190">Paquete para el. XML personalizado desatendido para configurar las unidades de salas de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="468b6-190">Package for the custom Unattended.xml to configure Microsoft Teams Rooms units</span></span>            |
| <span data-ttu-id="468b6-191">SRS V2-Set-SRSComputerName</span><span class="sxs-lookup"><span data-stu-id="468b6-191">SRS v2 - Set-SRSComputerName Package</span></span> | <span data-ttu-id="468b6-192">Paquete de software</span><span class="sxs-lookup"><span data-stu-id="468b6-192">Software package</span></span>       | <span data-ttu-id="468b6-193">Paquete para la aplicación HTML (HTA) para asignar un nombre de equipo durante la implementación</span><span class="sxs-lookup"><span data-stu-id="468b6-193">Package for the HTML application (HTA) to assign a computer name during the deployment</span></span>    |
| <span data-ttu-id="468b6-194">SRS V2: configurar la configuración de SRS</span><span class="sxs-lookup"><span data-stu-id="468b6-194">SRS v2 - Configure SRS Setup</span></span>         | <span data-ttu-id="468b6-195">Paquete de software</span><span class="sxs-lookup"><span data-stu-id="468b6-195">Software package</span></span>       | <span data-ttu-id="468b6-196">Paquete para configurar la implementación de la aplicación salas de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="468b6-196">Package to configure deployment of the Microsoft Teams Rooms app</span></span>                          |
| <span data-ttu-id="468b6-197">Paquete de actualizaciones para SRS V2-OS</span><span class="sxs-lookup"><span data-stu-id="468b6-197">SRS v2 - OS Updates Package</span></span>          | <span data-ttu-id="468b6-198">Paquete de software</span><span class="sxs-lookup"><span data-stu-id="468b6-198">Software package</span></span>       | <span data-ttu-id="468b6-199">Paquete para implementar actualizaciones obligatorias del sistema operativo</span><span class="sxs-lookup"><span data-stu-id="468b6-199">Package to deploy mandatory operating system updates</span></span>                                      |
| <span data-ttu-id="468b6-200">SRS V2: paquete de certificados raíz</span><span class="sxs-lookup"><span data-stu-id="468b6-200">SRS v2 - Root Certificate Package</span></span>    | <span data-ttu-id="468b6-201">Paquete de software</span><span class="sxs-lookup"><span data-stu-id="468b6-201">Software package</span></span>       | <span data-ttu-id="468b6-202">Paquete opcional para implementar el certificado raíz (no es necesario para las unidades Unidas al dominio)</span><span class="sxs-lookup"><span data-stu-id="468b6-202">Optional - Package to deploy the root certificate (not required for domain-joined units)</span></span>  |
| <span data-ttu-id="468b6-203">SRS V2-paquete de Microsoft Monitoring Agent</span><span class="sxs-lookup"><span data-stu-id="468b6-203">SRS v2 - Microsoft Monitoring Agent Package</span></span> | <span data-ttu-id="468b6-204">Paquete de software</span><span class="sxs-lookup"><span data-stu-id="468b6-204">Software package</span></span>       | <span data-ttu-id="468b6-205">Opcional: paquete para implementar y configurar el agente de Microsoft Operations Management Suite</span><span class="sxs-lookup"><span data-stu-id="468b6-205">Optional - Package to deploy and configure the Microsoft Operations Management Suite agent</span></span>|
| <span data-ttu-id="468b6-206">SRS V2: paquete de fondo WinPE</span><span class="sxs-lookup"><span data-stu-id="468b6-206">SRS v2 - WinPE Background Package</span></span>    | <span data-ttu-id="468b6-207">Paquete de software</span><span class="sxs-lookup"><span data-stu-id="468b6-207">Software package</span></span>       | <span data-ttu-id="468b6-208">Paquete para la imagen de fondo personalizada que se usa con imágenes de arranque</span><span class="sxs-lookup"><span data-stu-id="468b6-208">Package for the custom background image to use with boot images</span></span>                           |
| <span data-ttu-id="468b6-209">Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="468b6-209">Windows 10 Enterprise</span></span>                | <span data-ttu-id="468b6-210">Imagen de sistema operativo</span><span class="sxs-lookup"><span data-stu-id="468b6-210">Operating system image</span></span> | <span data-ttu-id="468b6-211">Paquete para el archivo de instalación del sistema operativo (install. wim)</span><span class="sxs-lookup"><span data-stu-id="468b6-211">Package for the operating system installation file (install.wim)</span></span>                          |
| <span data-ttu-id="468b6-212">Surface Pro</span><span class="sxs-lookup"><span data-stu-id="468b6-212">Surface Pro</span></span>                          | <span data-ttu-id="468b6-213">Paquete de controladores</span><span class="sxs-lookup"><span data-stu-id="468b6-213">Driver package</span></span>         | <span data-ttu-id="468b6-214">Paquete para los drivers de dispositivo y firmware para Microsoft Surface Pro</span><span class="sxs-lookup"><span data-stu-id="468b6-214">Package for the device drivers and firmware for Microsoft Surface Pro</span></span>                     |
| <span data-ttu-id="468b6-215">Surface Pro 4</span><span class="sxs-lookup"><span data-stu-id="468b6-215">Surface Pro 4</span></span>                        | <span data-ttu-id="468b6-216">Paquete de controladores</span><span class="sxs-lookup"><span data-stu-id="468b6-216">Driver package</span></span>         | <span data-ttu-id="468b6-217">Paquete para los drivers de dispositivo y firmware para Microsoft Surface Pro 4</span><span class="sxs-lookup"><span data-stu-id="468b6-217">Package for the device drivers and firmware for Microsoft Surface Pro 4</span></span>                   |

<span data-ttu-id="468b6-218">Para obtener más información, vea [paquetes y programas en Configuration Manager](https://docs.microsoft.com/configmgr/apps/deploy-use/packages-and-programs).</span><span class="sxs-lookup"><span data-stu-id="468b6-218">For more information, see [Packages and programs in Configuration Manager](https://docs.microsoft.com/configmgr/apps/deploy-use/packages-and-programs).</span></span>

### <a name="create-folders-for-the-package-source-files"></a><span data-ttu-id="468b6-219">Crear carpetas para los archivos de origen del paquete</span><span class="sxs-lookup"><span data-stu-id="468b6-219">Create folders for the package source files</span></span>

<span data-ttu-id="468b6-220">El administrador de configuración requiere que los archivos de origen del paquete se organicen en una estructura de carpetas específica cuando se crean por primera vez y cuando se actualizan.</span><span class="sxs-lookup"><span data-stu-id="468b6-220">Configuration Manager requires package source files to be organized in a specific folder structure when they’re first created and when they’re updated.</span></span>

<span data-ttu-id="468b6-221">Cree la siguiente estructura de carpetas en el sitio principal o en el sitio principal de administración de Microsoft Endpoint Configuration Manager, o en un recurso compartido de servidor que esté usando para hospedar los archivos de origen del paquete:</span><span class="sxs-lookup"><span data-stu-id="468b6-221">Create the following folder structure on the Microsoft Endpoint Configuration Manager central administration site or primary site, or on a server share you’re using to host package source files:</span></span>

-   <span data-ttu-id="468b6-222">SRS V2-paquete de Microsoft Monitoring Agent</span><span class="sxs-lookup"><span data-stu-id="468b6-222">SRS v2 - Microsoft Monitoring Agent Package</span></span>
-   <span data-ttu-id="468b6-223">Paquete de actualizaciones para SRS V2-OS</span><span class="sxs-lookup"><span data-stu-id="468b6-223">SRS v2 - OS Updates Package</span></span>
-   <span data-ttu-id="468b6-224">SRS V2: paquete de certificados raíz</span><span class="sxs-lookup"><span data-stu-id="468b6-224">SRS v2 - Root Certificate Package</span></span>
-   <span data-ttu-id="468b6-225">SRS V2-Set-SRSComputerName</span><span class="sxs-lookup"><span data-stu-id="468b6-225">SRS v2 - Set-SRSComputerName Package</span></span>
-   <span data-ttu-id="468b6-226">SRS V2: paquete de aplicaciones para SRS</span><span class="sxs-lookup"><span data-stu-id="468b6-226">SRS v2 - SRS Application Package</span></span>
-   <span data-ttu-id="468b6-227">SRS V2: configurar la configuración de SRS</span><span class="sxs-lookup"><span data-stu-id="468b6-227">SRS v2 - Configure SRS Setup</span></span>
-   <span data-ttu-id="468b6-228">SRS V2: paquete de Sysprep</span><span class="sxs-lookup"><span data-stu-id="468b6-228">SRS v2 - Sysprep Package</span></span>
-   <span data-ttu-id="468b6-229">Conductores</span><span class="sxs-lookup"><span data-stu-id="468b6-229">Drivers</span></span>
    -   <span data-ttu-id="468b6-230">Surface Pro</span><span class="sxs-lookup"><span data-stu-id="468b6-230">Surface Pro</span></span>
    -   <span data-ttu-id="468b6-231">Surface Pro 4</span><span class="sxs-lookup"><span data-stu-id="468b6-231">Surface Pro 4</span></span>
-   <span data-ttu-id="468b6-232">Sistemas operativos</span><span class="sxs-lookup"><span data-stu-id="468b6-232">Operating Systems</span></span>
    -   <span data-ttu-id="468b6-233">Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="468b6-233">Windows 10 Enterprise</span></span>

> [!TIP]
> <span data-ttu-id="468b6-234">También puede [Descargar](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true) y usar el archivo zip que incluye la estructura de carpetas de los paquetes, los scripts que necesita usar y la plantilla de secuencia de tareas que necesita importar.</span><span class="sxs-lookup"><span data-stu-id="468b6-234">You may also [download](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true) and use the zip file that includes the folder structure for the packages, the scripts that you need to use, and the task sequence template, that you need to import.</span></span>

### <a name="create-the-monitoring-agent-package"></a><span data-ttu-id="468b6-235">Crear el paquete del agente de supervisión</span><span class="sxs-lookup"><span data-stu-id="468b6-235">Create the Monitoring agent package</span></span>

1. <span data-ttu-id="468b6-236">Descarga el agente de supervisión <https://go.microsoft.com/fwlink/?LinkId=828603>de.</span><span class="sxs-lookup"><span data-stu-id="468b6-236">Download the Monitoring agent from <https://go.microsoft.com/fwlink/?LinkId=828603>.</span></span>

2. <span data-ttu-id="468b6-237">Extraiga el paquete a la carpeta del **paquete SRS V2-Microsoft Monitoring Agent** abriendo una ventana del símbolo del sistema y escribiendo **MMASetup-AMD64. exe/c:** en el símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="468b6-237">Extract the package into the **SRS v2 - Microsoft Monitoring Agent Package** folder by opening a Command Prompt window and entering **MMASetup-AMD64.exe /C:**     at the command prompt.</span></span>

3. <span data-ttu-id="468b6-238">En la consola del administrador de configuración, vaya a **paquetes**de **Administración** \> de aplicaciones de la **biblioteca** \> de software y, después, seleccione **crear paquete**.</span><span class="sxs-lookup"><span data-stu-id="468b6-238">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**, and then select **Create Package**.</span></span>

4. <span data-ttu-id="468b6-239">Escriba la siguiente información para crear el paquete:</span><span class="sxs-lookup"><span data-stu-id="468b6-239">Enter the following information to create the package:</span></span>

   - <span data-ttu-id="468b6-240">Nombre<strong>: SRS V2: paquete del agente de supervisión de Microsoft</strong></span><span class="sxs-lookup"><span data-stu-id="468b6-240">Name<strong>: SRS v2 - Microsoft Monitoring Agent Package</strong></span></span>

   - <span data-ttu-id="468b6-241">Fabricante<strong>: Microsoft Corporation</strong></span><span class="sxs-lookup"><span data-stu-id="468b6-241">Manufacturer<strong>: Microsoft Corporation</strong></span></span>

   - <span data-ttu-id="468b6-242">Versión<strong>: 8.1.11081.0</strong> (escriba la versión del archivo de instalación descargado)</span><span class="sxs-lookup"><span data-stu-id="468b6-242">Version<strong>: 8.1.11081.0</strong> (enter the version of the downloaded installation file)</span></span>

   - <span data-ttu-id="468b6-243">Seleccione la casilla **este paquete contiene archivos de origen** , escriba la ruta de acceso a la carpeta del **paquete SRS V2-Microsoft Monitoring Agent** y, a continuación, seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="468b6-243">Select the **This package contains source files** check box, enter the path to the **SRS v2 - Microsoft Monitoring Agent Package** folder, and then select **Next**.</span></span>

5. <span data-ttu-id="468b6-244">Seleccione no **crear un programa**y, a continuación, seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="468b6-244">Select **Do not create a program**, and then select **Next**.</span></span>

6. <span data-ttu-id="468b6-245">Revise la página **confirmar la configuración** y, a continuación, seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="468b6-245">Review the **Confirm the settings** page, and then select **Next**.</span></span>

7. <span data-ttu-id="468b6-246">Seleccione **cerrar**.</span><span class="sxs-lookup"><span data-stu-id="468b6-246">Select **Close**.</span></span>

### <a name="create-the-operating-system-updates-package"></a><span data-ttu-id="468b6-247">Crear el paquete de actualizaciones del sistema operativo</span><span class="sxs-lookup"><span data-stu-id="468b6-247">Create the operating system updates package</span></span>

1. <span data-ttu-id="468b6-248">En la carpeta del **paquete de actualizaciones de SRS V2-os** , cree un nuevo script de PowerShell denominado **install-SRSv2-os-updates. PS1**.</span><span class="sxs-lookup"><span data-stu-id="468b6-248">In the **SRS v2 - OS Updates Package** folder, create a new PowerShell script named **Install-SRSv2-OS-Updates.ps1**.</span></span>

2. <span data-ttu-id="468b6-249">Copie el script siguiente en el script **install-SRSv2-os-updates. PS1** .</span><span class="sxs-lookup"><span data-stu-id="468b6-249">Copy the script below into the **Install-SRSv2-OS-Updates.ps1** script.</span></span> <span data-ttu-id="468b6-250">Como alternativa, puedes descargar el script Install-SRSv2-OS-Updates. PS1 desde [aquí](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true).</span><span class="sxs-lookup"><span data-stu-id="468b6-250">Alternatively, you can download the Install-SRSv2-OS-Updates.ps1 script from [here](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true).</span></span>
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
3. <span data-ttu-id="468b6-251">Descargue los paquetes de Windows Update obligatorios en la misma carpeta.</span><span class="sxs-lookup"><span data-stu-id="468b6-251">Download the mandatory Windows Update packages into the same folder.</span></span>
   > [!NOTE]
   > <span data-ttu-id="468b6-252">En el momento en que se publicó este artículo, solo se necesitaba [KB4056892](http://download.windowsupdate.com/c/msdownload/update/software/secu/2018/01/windows10.0-kb4056892-x64_a41a378cf9ae609152b505c40e691ca1228e28ea.msu) .</span><span class="sxs-lookup"><span data-stu-id="468b6-252">At the time this article was published, only [KB4056892](http://download.windowsupdate.com/c/msdownload/update/software/secu/2018/01/windows10.0-kb4056892-x64_a41a378cf9ae609152b505c40e691ca1228e28ea.msu) was required.</span></span> <span data-ttu-id="468b6-253">Marque [configurar una consola de salas de Microsoft Teams](console.md)para ver si se necesitan otras actualizaciones.</span><span class="sxs-lookup"><span data-stu-id="468b6-253">Check [Configure a Microsoft Teams Rooms console](console.md), to see whether any other updates are required.</span></span>

4. <span data-ttu-id="468b6-254">En la consola del administrador de configuración, vaya a **paquetes**de **Administración** \> de aplicaciones de la **biblioteca** \> de software y, después, seleccione **crear paquete**.</span><span class="sxs-lookup"><span data-stu-id="468b6-254">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**, and then select **Create Package**.</span></span>

5. <span data-ttu-id="468b6-255">Escriba la siguiente información para crear el paquete:</span><span class="sxs-lookup"><span data-stu-id="468b6-255">Enter the following information to create the package:</span></span>
   -   <span data-ttu-id="468b6-256">Nombre: **SRS V2: paquete de actualizaciones del sistema operativo**</span><span class="sxs-lookup"><span data-stu-id="468b6-256">Name: **SRS v2 – OS Updates Package**</span></span>
   -   <span data-ttu-id="468b6-257">Fabricante: **Microsoft Corporation**</span><span class="sxs-lookup"><span data-stu-id="468b6-257">Manufacturer: **Microsoft Corporation**</span></span>
   -   <span data-ttu-id="468b6-258">Versión: **1.0.0**</span><span class="sxs-lookup"><span data-stu-id="468b6-258">Version: **1.0.0**</span></span>
   -   <span data-ttu-id="468b6-259">Seleccione la casilla **este paquete contiene archivos de origen** , escriba la ruta de acceso a la carpeta del **paquete de actualizaciones de SRS V2-os** y, a continuación, seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="468b6-259">Select the **This package contains source files** check box, enter the path to the **SRS v2 - OS Updates Package** folder, and then select **Next**.</span></span>

6. <span data-ttu-id="468b6-260">Seleccione no **crear un programa**y, a continuación, seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="468b6-260">Select **Do not create a program**, and then select **Next**.</span></span>

7. <span data-ttu-id="468b6-261">Revise la página **confirmar la configuración** y, a continuación, seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="468b6-261">Review the **Confirm the settings** page, and then select **Next**.</span></span>

8. <span data-ttu-id="468b6-262">Seleccione **cerrar**.</span><span class="sxs-lookup"><span data-stu-id="468b6-262">Select **Close**.</span></span>

### <a name="create-the-root-certificate-package-optional"></a><span data-ttu-id="468b6-263">Crear el paquete de certificados raíz (opcional)</span><span class="sxs-lookup"><span data-stu-id="468b6-263">Create the root certificate package (optional)</span></span>

<span data-ttu-id="468b6-264">Cree este paquete para distribuir el certificado raíz de los dispositivos que no se unirán a un dominio de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="468b6-264">You create this package to distribute the root certificate for devices that won’t be joined to an Active Directory domain.</span></span> <span data-ttu-id="468b6-265">Cree este paquete solo si se aplican las dos condiciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="468b6-265">Create this package only if both the following conditions apply:</span></span>
-   <span data-ttu-id="468b6-266">Su implementación incluye Lync local o Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="468b6-266">Your deployment includes on-premises Lync or Skype for Business Server.</span></span>
-   <span data-ttu-id="468b6-267">Las unidades de salas de Microsoft Teams están configuradas para trabajar en un grupo de trabajo en lugar de un miembro del dominio.</span><span class="sxs-lookup"><span data-stu-id="468b6-267">Microsoft Teams Rooms units are configured to work in a workgroup instead of a domain member.</span></span>

1.  <span data-ttu-id="468b6-268">Copie el certificado raíz en la carpeta del **paquete de certificados raíz de SRS V2** .</span><span class="sxs-lookup"><span data-stu-id="468b6-268">Copy the root certificate into the **SRS v2 – Root Certificate Package** folder.</span></span>

2.  <span data-ttu-id="468b6-269">En la consola del administrador de configuración, vaya a **paquetes**de **Administración** \> de aplicaciones de la **biblioteca** \> de software y, después, seleccione **crear paquete**.</span><span class="sxs-lookup"><span data-stu-id="468b6-269">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**, and then select **Create Package**.</span></span>

3.  <span data-ttu-id="468b6-270">Escriba la siguiente información para crear el paquete:</span><span class="sxs-lookup"><span data-stu-id="468b6-270">Enter the following information to create the package:</span></span>
    -   <span data-ttu-id="468b6-271">Nombre: **SRS V2: paquete de certificados raíz**</span><span class="sxs-lookup"><span data-stu-id="468b6-271">Name: **SRS v2 – Root Certificate Package**</span></span>
    -   <span data-ttu-id="468b6-272">Fabricante: *nombre de la organización*</span><span class="sxs-lookup"><span data-stu-id="468b6-272">Manufacturer: *Your organization’s name*</span></span>
    -   <span data-ttu-id="468b6-273">Versión: **1.0.0**</span><span class="sxs-lookup"><span data-stu-id="468b6-273">Version: **1.0.0**</span></span>
    -   <span data-ttu-id="468b6-274">Seleccione la casilla **este paquete contiene archivos de origen** , escriba la ruta de acceso a la carpeta del **paquete de certificados raíz** y, a continuación, seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="468b6-274">Select the **This package contains source files** check box, enter the path to the **SRS v2 – Root Certificate Package** folder, and then select **Next**.</span></span>

4.  <span data-ttu-id="468b6-275">Seleccione no **crear un programa**y, a continuación, seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="468b6-275">Select **Do not create a program**, and then select **Next**.</span></span>

5.  <span data-ttu-id="468b6-276">Revise la página **confirmar la configuración** y, a continuación, seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="468b6-276">Review the **Confirm the settings** page, and then select **Next**.</span></span>

6.  <span data-ttu-id="468b6-277">Seleccione **cerrar**.</span><span class="sxs-lookup"><span data-stu-id="468b6-277">Select **Close**.</span></span>

### <a name="create-the-microsoft-teams-rooms-deployment-kit-package"></a><span data-ttu-id="468b6-278">Crear el paquete del kit de implementación de Microsoft Teams Rooms</span><span class="sxs-lookup"><span data-stu-id="468b6-278">Create the Microsoft Teams Rooms deployment kit package</span></span>

1.  <span data-ttu-id="468b6-279">Descargue la versión más reciente del **Kit de implementación de Microsoft Teams Rooms** desde e instálela en una estación de <https://go.microsoft.com/fwlink/?linkid=851168>trabajo.</span><span class="sxs-lookup"><span data-stu-id="468b6-279">Download the latest version of the **Microsoft Teams Rooms deployment kit** from <https://go.microsoft.com/fwlink/?linkid=851168>, and install it to a workstation.</span></span>

2.  <span data-ttu-id="468b6-280">Copie el contenido de **C:\\archivos de programa (x86\\) kit de implementación de sistemas de salas de Skype** en la carpeta del **paquete de la aplicación SRS V2** .</span><span class="sxs-lookup"><span data-stu-id="468b6-280">Copy the content from **C:\\Program Files (x86)\\Skype Room System Deployment Kit** to the **SRS v2 - SRS Application Package** folder.</span></span>

3.  <span data-ttu-id="468b6-281">En la consola del administrador de configuración, vaya a **paquetes**de **Administración** \> de aplicaciones de la **biblioteca** \> de software y, después, seleccione **crear paquete**.</span><span class="sxs-lookup"><span data-stu-id="468b6-281">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**, and then select **Create Package**.</span></span>

4.  <span data-ttu-id="468b6-282">Escriba la siguiente información para crear el paquete:</span><span class="sxs-lookup"><span data-stu-id="468b6-282">Enter the following information to create the package:</span></span>
    -   <span data-ttu-id="468b6-283">Nombre: **SRS V2: paquete de aplicación para SRS**</span><span class="sxs-lookup"><span data-stu-id="468b6-283">Name: **SRS v2 – SRS Application Package**</span></span>
    -   <span data-ttu-id="468b6-284">Fabricante: **Microsoft Corporation**</span><span class="sxs-lookup"><span data-stu-id="468b6-284">Manufacturer: **Microsoft Corporation**</span></span>
    -   <span data-ttu-id="468b6-285">Versión: **3.1.104.0** (escriba la versión del archivo de instalación descargado)</span><span class="sxs-lookup"><span data-stu-id="468b6-285">Version: **3.1.104.0** (enter the version of the downloaded installation file)</span></span>
    -   <span data-ttu-id="468b6-286">Seleccione la casilla **este paquete contiene archivos de origen** , escriba la ruta de acceso a la carpeta **SRS V2 – paquete de la aplicación SRS** y, a continuación, seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="468b6-286">Select the **This package contains source files** check box, enter the path to the **SRS v2 – SRS Application Package** folder, and then select **Next**.</span></span>
5.  <span data-ttu-id="468b6-287">Seleccione no **crear un programa**y, a continuación, seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="468b6-287">Select **Do not create a program**, and then select **Next**.</span></span>

6.  <span data-ttu-id="468b6-288">Revise la página **confirmar la configuración** y, a continuación, seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="468b6-288">Review the **Confirm the settings** page, and then select **Next**.</span></span>

7.  <span data-ttu-id="468b6-289">Seleccione **cerrar**.</span><span class="sxs-lookup"><span data-stu-id="468b6-289">Select **Close**.</span></span>

### <a name="create-the-computer-name-assignment-package"></a><span data-ttu-id="468b6-290">Crear el paquete de asignación de nombre de equipo</span><span class="sxs-lookup"><span data-stu-id="468b6-290">Create the computer name assignment package</span></span>

1.  <span data-ttu-id="468b6-291">En la carpeta del **paquete SRS V2-Set-SRSComputerName** , cree una nueva aplicación HTML denominada **set-SRSComputerName. HTA** .</span><span class="sxs-lookup"><span data-stu-id="468b6-291">In the **SRS v2 - Set-SRSComputerName Package** folder, create a new HTML application named **Set-SRSComputerName.hta** .</span></span>

2.  <span data-ttu-id="468b6-292">Copie el script siguiente en el archivo **set-SRSComputerName. HTA** .</span><span class="sxs-lookup"><span data-stu-id="468b6-292">Copy the following script into the **Set-SRSComputerName.hta** file.</span></span> <span data-ttu-id="468b6-293">También puedes descargar el archivo Set-SRSComputerName. HTA desde [aquí](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true).</span><span class="sxs-lookup"><span data-stu-id="468b6-293">Alternatively, you can download the Set-SRSComputerName.hta file from [here](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true).</span></span>
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
3.  <span data-ttu-id="468b6-294">En la consola del administrador de configuración, vaya a **paquetes**de **Administración** \> de aplicaciones de la **biblioteca** \> de software y, después, seleccione **crear paquete**.</span><span class="sxs-lookup"><span data-stu-id="468b6-294">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**, and then select **Create Package**.</span></span>

4.  <span data-ttu-id="468b6-295">Escriba la siguiente información para crear el paquete:</span><span class="sxs-lookup"><span data-stu-id="468b6-295">Enter the following information to create the package:</span></span>

    -   <span data-ttu-id="468b6-296">Nombre: **SRS V2-Set-SRSComputerName paquete**</span><span class="sxs-lookup"><span data-stu-id="468b6-296">Name: **SRS v2 - Set-SRSComputerName Package**</span></span>

    -   <span data-ttu-id="468b6-297">Fabricante: **Microsoft Corporation**</span><span class="sxs-lookup"><span data-stu-id="468b6-297">Manufacturer: **Microsoft Corporation**</span></span>

    -   <span data-ttu-id="468b6-298">Versión: **1.0.0**</span><span class="sxs-lookup"><span data-stu-id="468b6-298">Version: **1.0.0**</span></span>

    -   <span data-ttu-id="468b6-299">Active la casilla de verificación **este paquete contiene archivos de origen** , escriba la ruta de acceso a la carpeta de **paquete SRSComputerName SRS V2** y, a continuación, seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="468b6-299">Select the **This package contains source files** check box, enter the path to the **SRS v2 - Set-SRSComputerName Package** folder, and then select **Next**.</span></span>

5.  <span data-ttu-id="468b6-300">Seleccione no **crear un programa**y, a continuación, seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="468b6-300">Select **Do not create a program**, and then select **Next**.</span></span>

6.  <span data-ttu-id="468b6-301">Revise la página **confirmar la configuración** y, a continuación, seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="468b6-301">Review the **Confirm the settings** page, and then select **Next**.</span></span>

7.  <span data-ttu-id="468b6-302">Seleccione **cerrar**.</span><span class="sxs-lookup"><span data-stu-id="468b6-302">Select **Close**.</span></span>

### <a name="create-the-sysprep-package"></a><span data-ttu-id="468b6-303">Crear el paquete de Sysprep</span><span class="sxs-lookup"><span data-stu-id="468b6-303">Create the Sysprep package</span></span>

1. <span data-ttu-id="468b6-304">En la carpeta del **paquete SRS V2-Sysprep** , cree un nuevo archivo XML denominado **Unattend. XML** .</span><span class="sxs-lookup"><span data-stu-id="468b6-304">In the **SRS v2 – Sysprep Package** folder, create a new XML file named **Unattend.xml** .</span></span>

2. <span data-ttu-id="468b6-305">Copie el texto siguiente en el archivo **Unattend. XML** .</span><span class="sxs-lookup"><span data-stu-id="468b6-305">Copy the following text into the **Unattend.xml** file.</span></span> <span data-ttu-id="468b6-306">También puede descargar el archivo Unattend. XML desde [aquí](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true).</span><span class="sxs-lookup"><span data-stu-id="468b6-306">Alternatively, you can download the Unattend.xml file from [here](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true).</span></span>
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
3. <span data-ttu-id="468b6-307">En la consola del administrador de configuración, vaya a **paquetes**de **Administración** \> de aplicaciones de la **biblioteca** \> de software y, después, seleccione **crear paquete**.</span><span class="sxs-lookup"><span data-stu-id="468b6-307">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**, and then select **Create Package**.</span></span>

4. <span data-ttu-id="468b6-308">Escriba la siguiente información para crear el paquete:</span><span class="sxs-lookup"><span data-stu-id="468b6-308">Enter the following information to create the package:</span></span>
   -   <span data-ttu-id="468b6-309">Nombre: **SRS V2-paquete de Sysprep**</span><span class="sxs-lookup"><span data-stu-id="468b6-309">Name: **SRS v2 - Sysprep Package**</span></span>
   -   <span data-ttu-id="468b6-310">Fabricante: **Microsoft Corporation**</span><span class="sxs-lookup"><span data-stu-id="468b6-310">Manufacturer: **Microsoft Corporation**</span></span>
   -   <span data-ttu-id="468b6-311">Versión: **1.0.0**</span><span class="sxs-lookup"><span data-stu-id="468b6-311">Version: **1.0.0**</span></span>
   -   <span data-ttu-id="468b6-312">Seleccione la casilla **este paquete contiene archivos de origen** , escriba la ruta de acceso a la carpeta del **paquete SRS V2-Sysprep** y, a continuación, seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="468b6-312">Select the **This package contains source files** check box, enter the path to the **SRS v2 – Sysprep Package** folder, and then select **Next**.</span></span>
5. <span data-ttu-id="468b6-313">Seleccione no **crear un programa**y, a continuación, seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="468b6-313">Select **Do not create a program**, and then select **Next**.</span></span>

6. <span data-ttu-id="468b6-314">Revise la página **confirmar la configuración** y, a continuación, seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="468b6-314">Review the **Confirm the settings** page, and then select **Next**.</span></span>

7. <span data-ttu-id="468b6-315">Seleccione **cerrar**.</span><span class="sxs-lookup"><span data-stu-id="468b6-315">Select **Close**.</span></span>

### <a name="create-the-windows-10-enterprise-package"></a><span data-ttu-id="468b6-316">Crear el paquete de Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="468b6-316">Create the Windows 10 Enterprise package</span></span>

1.  <span data-ttu-id="468b6-317">Obtenga un medio de Windows 10 Enterprise x64 y copie el archivo **install. Wim** en la carpeta **sistemas\\operativos de Windows 10 Enterprise** .</span><span class="sxs-lookup"><span data-stu-id="468b6-317">Obtain a Windows 10 Enterprise x64 media, and copy the **install.wim** file to the **Operating Systems\\Windows 10 Enterprise** folder.</span></span>

2.  <span data-ttu-id="468b6-318">En la consola del administrador de configuración, vaya a **imágenes del sistema**operativo de **sistemas** \> operativos de la **biblioteca** \> de software y, a continuación, seleccione **Agregar imagen de sistema operativo**.</span><span class="sxs-lookup"><span data-stu-id="468b6-318">In the Configuration Manager console, go to **Software Library** \> **Operating Systems** \> **Operating System Images**, and then select **Add Operating System Image**.</span></span>

3.  <span data-ttu-id="468b6-319">Especifique la ruta de acceso al archivo **install. Wim** que acaba de copiar y, a continuación, seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="468b6-319">Specify the path to the **install.wim** file you just copied, and then select **Next**.</span></span>

4.  <span data-ttu-id="468b6-320">Actualice el campo de **versión** para que coincida con el número de compilación de la imagen de Windows 10 Enterprise y, a continuación, seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="468b6-320">Update the **Version** field to match the build number of the Windows 10 Enterprise image, and then select **Next**.</span></span>

5.  <span data-ttu-id="468b6-321">Revise la página **detalles** y, a continuación, seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="468b6-321">Review the **Details** page, and then select **Next**.</span></span>

6.  <span data-ttu-id="468b6-322">Seleccione **cerrar**.</span><span class="sxs-lookup"><span data-stu-id="468b6-322">Select **Close**.</span></span>

<span data-ttu-id="468b6-323">Para obtener más información, consulte [administrar imágenes del sistema operativo con Configuration Manager](https://docs.microsoft.com/configmgr/osd/get-started/manage-operating-system-images).</span><span class="sxs-lookup"><span data-stu-id="468b6-323">For more information, see [Manage OS images with Configuration Manager](https://docs.microsoft.com/configmgr/osd/get-started/manage-operating-system-images).</span></span>

### <a name="create-surface-pro-device-driver-packages"></a><span data-ttu-id="468b6-324">Crear paquetes de controladores de dispositivo Surface Pro</span><span class="sxs-lookup"><span data-stu-id="468b6-324">Create Surface Pro device driver packages</span></span>

<span data-ttu-id="468b6-325">Las salas de Microsoft Teams son compatibles con Surface Pro y Surface Pro 4.</span><span class="sxs-lookup"><span data-stu-id="468b6-325">Microsoft Teams Rooms is supported for both Surface Pro and Surface Pro 4.</span></span> <span data-ttu-id="468b6-326">Necesita crear un paquete de controladores para cada modelo de Surface Pro que tenga en su entorno.</span><span class="sxs-lookup"><span data-stu-id="468b6-326">You need to create a driver package for each Surface Pro model you have in your environment.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="468b6-327">Los drivers deben ser compatibles con la compilación de Windows 10 Enterprise y la versión del kit de implementación de Microsoft Teams Rooms.</span><span class="sxs-lookup"><span data-stu-id="468b6-327">The drivers must be compatible with the Windows 10 Enterprise build and the Microsoft Teams Rooms deployment kit version.</span></span> <span data-ttu-id="468b6-328">Para obtener más información, vea [descargar el firmware y los drivers más recientes para dispositivos de Surface](https://docs.microsoft.com/surface/deploy-the-latest-firmware-and-drivers-for-surface-devices) y [configurar una consola](console.md).</span><span class="sxs-lookup"><span data-stu-id="468b6-328">For more information, see [Download the latest firmware and drivers for Surface devices](https://docs.microsoft.com/surface/deploy-the-latest-firmware-and-drivers-for-surface-devices) and [Configure a console](console.md).</span></span>

1.  <span data-ttu-id="468b6-329">Descargar los últimos drivers y firmware.</span><span class="sxs-lookup"><span data-stu-id="468b6-329">Download the latest drivers and firmware.</span></span>
    -   <span data-ttu-id="468b6-330">Para Surface Pro:<https://www.microsoft.com/download/details.aspx?id=55484></span><span class="sxs-lookup"><span data-stu-id="468b6-330">For Surface Pro: <https://www.microsoft.com/download/details.aspx?id=55484></span></span>
    -   <span data-ttu-id="468b6-331">Para Surface Pro 4:<https://www.microsoft.com/download/details.aspx?id=49498></span><span class="sxs-lookup"><span data-stu-id="468b6-331">For Surface Pro 4: <https://www.microsoft.com/download/details.aspx?id=49498></span></span>

2.  <span data-ttu-id="468b6-332">Extraiga el controlador y el firmware descargados.</span><span class="sxs-lookup"><span data-stu-id="468b6-332">Extract the downloaded driver and firmware.</span></span> <span data-ttu-id="468b6-333">Abra una ventana del símbolo del sistema y, en el símbolo del sistema, escriba uno de los siguientes comandos:</span><span class="sxs-lookup"><span data-stu-id="468b6-333">Open a Command Prompt window and at the command prompt, enter one of the following commands:</span></span>
    -   `msiexec /a C:\SurfacePro_Win10.msi /passive TARGETDIR="C:\_Sources\\Drivers\Surface Pro"`
    -   `msiexec /a C:\SurfacePro4_Win10.msi /passive TARGETDIR="C:\_Sources\\Drivers\Surface Pro 4"`

3.  <span data-ttu-id="468b6-334">En la consola del administrador de configuración, vaya a \> **drivers**de **sistemas operativos** de la **biblioteca** \> de software y, después, seleccione **importar controlador**.</span><span class="sxs-lookup"><span data-stu-id="468b6-334">In the Configuration Manager console, go to **Software Library** \> **Operating Systems** \> **Drivers**, and then select **Import Driver**.</span></span>

4.  <span data-ttu-id="468b6-335">Seleccione **importar todos los drivers en la siguiente ruta de acceso de red (UNC)**, seleccione la carpeta de origen (\\por\\ejemplo\\, C: _Sources drivers Surface Pro) y, a continuación, seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="468b6-335">Select **Import all drivers in the following network path (UNC)**, select the source folder (for example, C:\\_Sources\\Drivers\\Surface Pro), and then select **Next**.</span></span>

5.  <span data-ttu-id="468b6-336">En la página **especifique los detalles de los drivers importados** , seleccione todos los drivers que aparecen en la lista y, a continuación, seleccione **Habilitar estos drivers y permitir que los equipos los instalen**.</span><span class="sxs-lookup"><span data-stu-id="468b6-336">On the **Specify the details for the imported drivers** page, select all the listed drivers, and then select **Enable these drivers and allow computers to install them**.</span></span>

6.  <span data-ttu-id="468b6-337">Seleccione **categorías**, cree una nueva categoría que coincida con el modelo de superficie, seleccione **Aceptar**y, a continuación, seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="468b6-337">Select **Categories**, create a new category that matches the Surface model, select **OK**, and then select **Next**.</span></span>

7.  <span data-ttu-id="468b6-338">Seleccione **nuevo paquete**.</span><span class="sxs-lookup"><span data-stu-id="468b6-338">Select **New Package**.</span></span>

8.  <span data-ttu-id="468b6-339">Especifique el nombre del paquete que coincida con el modelo de Surface Pro, escriba una ruta de carpeta para almacenar los archivos de paquete de controladores en, seleccione **Aceptar**y, a continuación, seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="468b6-339">Specify the package name that matches the Surface Pro model, enter a folder path to store the driver package files in, select **OK**, and then select **Next**.</span></span>

9.  <span data-ttu-id="468b6-340">En la página **imágenes de arranque** , asegúrese de que no hay ninguna imagen de inicio seleccionada y, a continuación, seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="468b6-340">On the **boot images** page, ensure that no boot images are selected, and then select **Next**.</span></span>

10. <span data-ttu-id="468b6-341">Seleccione **cerrar**.</span><span class="sxs-lookup"><span data-stu-id="468b6-341">Select **Close**.</span></span>

11. <span data-ttu-id="468b6-342">Vaya a los **drivers**de **los sistemas** \> operativos de la **biblioteca** \> de software, seleccione \*\* \> crear carpeta\*\*y escriba un nombre de carpeta que coincida con el modelo de Surface Pro para el que ha importado los drivers.</span><span class="sxs-lookup"><span data-stu-id="468b6-342">Go to **Software Library** \> **Operating Systems** \> **Drivers**, select **Folder \> Create Folder**, and enter a folder name that matches the Surface Pro model that you just imported the drivers for.</span></span>

12. <span data-ttu-id="468b6-343">Mueva todos los drivers importados a la carpeta recién creada para facilitar la navegación y la operación.</span><span class="sxs-lookup"><span data-stu-id="468b6-343">Move all the imported drivers to the newly created folder for easier navigation and operation.</span></span>

> [!NOTE]
> <span data-ttu-id="468b6-344">Repita los mismos pasos para otros modelos de Surface Pro que pueda tener.</span><span class="sxs-lookup"><span data-stu-id="468b6-344">Repeat the same steps for other Surface Pro models you might have.</span></span> <span data-ttu-id="468b6-345">Para obtener más información, vea [administrar drivers en Configuration Manager](https://docs.microsoft.com/configmgr/osd/get-started/manage-drivers).</span><span class="sxs-lookup"><span data-stu-id="468b6-345">For more information, see [Manage drivers in Configuration Manager](https://docs.microsoft.com/configmgr/osd/get-started/manage-drivers).</span></span>

### <a name="create-microsoft-teams-rooms-configuration-package"></a><span data-ttu-id="468b6-346">Crear un paquete de configuración de Microsoft Teams Rooms</span><span class="sxs-lookup"><span data-stu-id="468b6-346">Create Microsoft Teams Rooms Configuration Package</span></span>

1.  <span data-ttu-id="468b6-347">En la consola del administrador de configuración, vaya a **paquetes**de **Administración** \> de aplicaciones de la **biblioteca** \> de software y, después, seleccione **crear paquete**.</span><span class="sxs-lookup"><span data-stu-id="468b6-347">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**, and then select **Create Package**.</span></span>

2.  <span data-ttu-id="468b6-348">Escriba la siguiente información para crear el paquete:</span><span class="sxs-lookup"><span data-stu-id="468b6-348">Enter the following information to create the package:</span></span>

    -   <span data-ttu-id="468b6-349">Nombre: **SRS V2-configurar el paquete de instalación de SRS**</span><span class="sxs-lookup"><span data-stu-id="468b6-349">Name: **SRS v2 - Configure SRS Setup Package**</span></span>

    -   <span data-ttu-id="468b6-350">Fabricante: **Microsoft Corporation**</span><span class="sxs-lookup"><span data-stu-id="468b6-350">Manufacturer: **Microsoft Corporation**</span></span>

    -   <span data-ttu-id="468b6-351">Versión: **1.0.0**</span><span class="sxs-lookup"><span data-stu-id="468b6-351">Version: **1.0.0**</span></span>

    -   <span data-ttu-id="468b6-352">Seleccione la casilla **este paquete contiene archivos de origen** , escriba la ruta de acceso a la carpeta **SRS V2-configure SRS Setup** y, a continuación, seleccione **Next**.</span><span class="sxs-lookup"><span data-stu-id="468b6-352">Select the **This package contains source files** check box, enter the path to the **SRS v2 - Configure SRS Setup** folder, and then select **Next**.</span></span>

3.  <span data-ttu-id="468b6-353">Seleccione no **crear un programa**y, a continuación, seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="468b6-353">Select **Do not create a program**, and then select **Next**.</span></span>

4.  <span data-ttu-id="468b6-354">Revise la página **confirmar la configuración** y, a continuación, seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="468b6-354">Review the **Confirm the settings** page, and then select **Next**.</span></span>

5.  <span data-ttu-id="468b6-355">Seleccione **cerrar**.</span><span class="sxs-lookup"><span data-stu-id="468b6-355">Select **Close**.</span></span>



## <a name="distribute-configuration-manager-packages"></a><span data-ttu-id="468b6-356">Distribuir paquetes de Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="468b6-356">Distribute Configuration Manager packages</span></span>

<span data-ttu-id="468b6-357">Todos los paquetes deben distribuirse a los servidores a los que se les ha asignado el rol de punto de distribución en la jerarquía de Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="468b6-357">All the packages must be distributed to the servers that have been assigned the distribution point role in the Configuration Manager hierarchy.</span></span> <span data-ttu-id="468b6-358">Siga las instrucciones a continuación para iniciar la distribución del paquete.</span><span class="sxs-lookup"><span data-stu-id="468b6-358">Follow the instructions below to initiate package distribution.</span></span>

1.  <span data-ttu-id="468b6-359">Distribuir paquetes de software.</span><span class="sxs-lookup"><span data-stu-id="468b6-359">Distribute software packages.</span></span>

    1.  <span data-ttu-id="468b6-360">En la consola del administrador de configuración, vaya a **paquetes**de **Administración** \> de aplicaciones de la **biblioteca** \> de software.</span><span class="sxs-lookup"><span data-stu-id="468b6-360">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**.</span></span> <span data-ttu-id="468b6-361">Seleccione todos los paquetes de software que desea distribuir y, a continuación, seleccione **distribuir contenido**.</span><span class="sxs-lookup"><span data-stu-id="468b6-361">Select all the software packages you want to distribute, and then select **Distribute Content**.</span></span>

    2.  <span data-ttu-id="468b6-362">Revise la lista de paquetes y, a continuación, seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="468b6-362">Review the list of packages, and then select **Next**.</span></span>

    3.  <span data-ttu-id="468b6-363">Agregue a la lista todos los servidores de puntos de distribución (o grupos de puntos de distribución, según la jerarquía de Configuration Manager) y, a continuación, seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="468b6-363">Add all the distribution point servers (or distribution point groups, depending on your Configuration Manager hierarchy) to the list, and then select **Next**.</span></span>

    4.  <span data-ttu-id="468b6-364">Seleccione **siguiente**y, después, haga clic en **cerrar**.</span><span class="sxs-lookup"><span data-stu-id="468b6-364">Select **Next**, and then select **Close**.</span></span>

2.  <span data-ttu-id="468b6-365">Distribuir paquetes de controladores.</span><span class="sxs-lookup"><span data-stu-id="468b6-365">Distribute driver packages.</span></span>

    1.  <span data-ttu-id="468b6-366">En la consola del administrador de configuración, vaya a **paquetes de controladores**de **sistemas** \> operativos de la **biblioteca** \> de software.</span><span class="sxs-lookup"><span data-stu-id="468b6-366">In the Configuration Manager console, go to **Software Library** \> **Operating Systems** \> **Driver Packages**.</span></span> <span data-ttu-id="468b6-367">Seleccione todos los paquetes de controladores que desea distribuir y, a continuación, seleccione **distribuir contenido**.</span><span class="sxs-lookup"><span data-stu-id="468b6-367">Select all the driver packages you want to distribute, and then select **Distribute Content**.</span></span>

    2.  <span data-ttu-id="468b6-368">Revise la lista de paquetes y, a continuación, seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="468b6-368">Review the list of packages, and then select **Next**.</span></span>

    3.  <span data-ttu-id="468b6-369">Agregue a la lista todos los servidores de puntos de distribución (o grupos de puntos de distribución, según la jerarquía de Configuration Manager) y, a continuación, seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="468b6-369">Add all the distribution point servers (or distribution point groups, depending on your Configuration Manager hierarchy) to the list, and then select **Next**.</span></span>

    4.  <span data-ttu-id="468b6-370">Seleccione **siguiente**y, después, haga clic en **cerrar**.</span><span class="sxs-lookup"><span data-stu-id="468b6-370">Select **Next**, and then select **Close**.</span></span>

3.  <span data-ttu-id="468b6-371">Distribuir paquetes del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="468b6-371">Distribute operating system packages.</span></span>

    1.  <span data-ttu-id="468b6-372">En la consola del administrador de configuración, vaya a **imágenes del sistema**operativo de **los sistemas** \> operativos de la **biblioteca** \> de software.</span><span class="sxs-lookup"><span data-stu-id="468b6-372">In the Configuration Manager console, go to **Software Library** \> **Operating Systems** \> **Operating System Images**.</span></span> <span data-ttu-id="468b6-373">Seleccione todas las imágenes del sistema operativo que desea distribuir y, a continuación, seleccione **distribuir contenido**.</span><span class="sxs-lookup"><span data-stu-id="468b6-373">Select all the operating system images you want to distribute, and then select **Distribute Content**.</span></span>

    2.  <span data-ttu-id="468b6-374">Revise la lista de paquetes y, a continuación, seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="468b6-374">Review the list of packages, and then select **Next**.</span></span>

    3.  <span data-ttu-id="468b6-375">Agregue a la lista todos los servidores de puntos de distribución (o grupos de puntos de distribución, según la jerarquía de Configuration Manager) y, a continuación, seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="468b6-375">Add all the distribution point servers (or distribution point groups, depending on your Configuration Manager hierarchy) to the list, and then select **Next**.</span></span>

    4.  <span data-ttu-id="468b6-376">Seleccione **siguiente**y, después, haga clic en **cerrar**.</span><span class="sxs-lookup"><span data-stu-id="468b6-376">Select **Next**, and then select **Close**.</span></span>

> [!NOTE]
> <span data-ttu-id="468b6-377">La distribución de paquetes puede llevar algún tiempo, según el tamaño del paquete, la jerarquía del administrador de configuración, el número de servidores de punto de distribución y el ancho de banda disponible en la red.</span><span class="sxs-lookup"><span data-stu-id="468b6-377">Package distribution might take some time, depending on the package size, Configuration Manager hierarchy, number of distribution point servers, and the bandwidth available in your network.</span></span>
> 
> <span data-ttu-id="468b6-378">Todos los paquetes deben distribuirse antes de que pueda empezar a implementar una unidad de salas de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="468b6-378">All the packages must be distributed before you can start deploying a Microsoft Teams Rooms unit.</span></span>
> 
> <span data-ttu-id="468b6-379">Puede revisar el estado de la distribución de paquetes en la consola de Configuration Manager si va a **supervisar** \> el **Estado de contenido**de estado \> de **distribución** .</span><span class="sxs-lookup"><span data-stu-id="468b6-379">You can review the status of your package distribution in the Configuration Manager console by going to **Monitoring** \> **Distribution Status** \> **Content Status**.</span></span>

## <a name="configuration-manager-task-sequences"></a><span data-ttu-id="468b6-380">Secuencias de tareas de Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="468b6-380">Configuration Manager task sequences</span></span>

<span data-ttu-id="468b6-381">Use las secuencias de tareas con Configuration Manager para automatizar los pasos para implementar una imagen de sistema operativo en un equipo de destino.</span><span class="sxs-lookup"><span data-stu-id="468b6-381">You use task sequences with Configuration Manager to automate the steps for deploying an operating system image to a destination computer.</span></span> <span data-ttu-id="468b6-382">Para implementar una unidad de salas de Microsoft Teams en un modo automatizado, cree una secuencia de tareas que haga referencia a la imagen de arranque utilizada para iniciar el equipo de destino Microsoft Team salas, la imagen del sistema operativo Windows 10 Enterprise que desea instalar y cualquier otro contenido adicional, como otras aplicaciones o actualizaciones de software.</span><span class="sxs-lookup"><span data-stu-id="468b6-382">To deploy a Microsoft Teams Rooms unit in an automated fashion, you create a task sequence that references the boot image used to start the destination Microsoft Teams Rooms computer, the Windows 10 Enterprise operating system image that you want to install, and any other additional content, such as other applications or software updates.</span></span>

### <a name="import-the-sample-task-sequence"></a><span data-ttu-id="468b6-383">Importar la secuencia de tareas de ejemplo</span><span class="sxs-lookup"><span data-stu-id="468b6-383">Import the sample task sequence</span></span>

<span data-ttu-id="468b6-384">Puede descargar y importar fácilmente una secuencia de tareas de muestra y personalizarla para satisfacer sus necesidades.</span><span class="sxs-lookup"><span data-stu-id="468b6-384">You can download and easily import a sample task sequence and customize it to meet your needs.</span></span>

1.  <span data-ttu-id="468b6-385">[**Descargue**](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true) la secuencia de tareas de ejemplo y copie el archivo zip descargado en una ubicación compartida.</span><span class="sxs-lookup"><span data-stu-id="468b6-385">[**Download**](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true) the sample task sequence, and copy the downloaded zip file to a shared location.</span></span>
2.  <span data-ttu-id="468b6-386">En la consola del administrador de configuración, vaya a **secuencias de tareas**de **sistemas** \> operativos de **bibliotecas** \> de software y, a continuación, seleccione **importar secuencia de tareas**.</span><span class="sxs-lookup"><span data-stu-id="468b6-386">In the Configuration Manager console, go to **Software Library** \> **Operating Systems** \> **Task Sequences**, and then select **Import Task Sequence**.</span></span>

3.  <span data-ttu-id="468b6-387">Seleccione **examinar**, vaya a la ubicación de la carpeta compartida que usó en el paso 1, seleccione el archivo **. zip Microsoft Team Rooms Deployment (en-EE.UU.)** y, a continuación, seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="468b6-387">Select **Browse**, go to the shared folder location you used in step 1, select the **Microsoft Teams Rooms Deployment (EN-US).zip** file, and then select **Next**.</span></span>

4.  <span data-ttu-id="468b6-388">Establezca **acción** como **crear nueva**y, a continuación, seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="468b6-388">Set **Action** to **Create New**, and then select **Next**.</span></span>

5.  <span data-ttu-id="468b6-389">Confirme la configuración y, a continuación, seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="468b6-389">Confirm the settings, and then select **Next**.</span></span>

6.  <span data-ttu-id="468b6-390">Seleccione **cerrar**.</span><span class="sxs-lookup"><span data-stu-id="468b6-390">Select **Close**.</span></span>

### <a name="validate-that-the-reference-packages-are-correctly-linked-to-each-task-sequence-step"></a><span data-ttu-id="468b6-391">Valide que los paquetes de referencia estén vinculados correctamente a cada paso de secuencia de tareas.</span><span class="sxs-lookup"><span data-stu-id="468b6-391">Validate that the reference packages are correctly linked to each task sequence step.</span></span>

1. <span data-ttu-id="468b6-392">Seleccione la secuencia de tareas importada y, después, haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="468b6-392">Select the imported task sequence, and then select **Edit**.</span></span>

    <span data-ttu-id="468b6-393">El editor de secuencias de tareas se abrirá y mostrará cada paso secuencial que necesita implementar y configurar una unidad de salas de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="468b6-393">The Task Sequence Editor opens and displays each sequential step that you need to deploy and configure a Microsoft Teams Rooms unit.</span></span>

2. <span data-ttu-id="468b6-394">Recorra cada paso y complete las actualizaciones recomendadas:</span><span class="sxs-lookup"><span data-stu-id="468b6-394">Walk through each step and complete the recommended updates:</span></span>

   1. <span data-ttu-id="468b6-395">**Reiniciar en Windows PE**: este paso se reiniciará y arrancará el equipo en Windows PXE.</span><span class="sxs-lookup"><span data-stu-id="468b6-395">**Restart in Windows PE**: This step restarts and then boots the computer into Windows PXE.</span></span> <span data-ttu-id="468b6-396">No es necesario realizar cambios en este paso.</span><span class="sxs-lookup"><span data-stu-id="468b6-396">No changes are required for this step.</span></span>

   2. <span data-ttu-id="468b6-397">**Partición disco 0: UEFI**: este paso borra la configuración del disco y crea particiones basadas en la configuración configurada.</span><span class="sxs-lookup"><span data-stu-id="468b6-397">**Partition Disk 0 – UEFI**: This step wipes the disk configuration and creates partitions based on the configured settings.</span></span> <span data-ttu-id="468b6-398">Le recomendamos que no realice ningún cambio en este paso.</span><span class="sxs-lookup"><span data-stu-id="468b6-398">We recommend that you not make any changes to this step.</span></span>

   3. <span data-ttu-id="468b6-399">**Establecer el nombre del equipo SRS**: este paso incluye una aplicación HTML para proporcionar una interfaz de usuario para establecer un nombre de equipo para la unidad de salas de Microsoft Teams durante la implementación.</span><span class="sxs-lookup"><span data-stu-id="468b6-399">**Set SRS Computer Name**: This step includes an HTML application to provide a UI to set a computer name for the Microsoft Teams Rooms unit during the deployment.</span></span>
      -  <span data-ttu-id="468b6-400">Este paso es opcional, pero solo se puede deshabilitar si desea administrar el nombre del equipo mediante un proceso alternativo.</span><span class="sxs-lookup"><span data-stu-id="468b6-400">This is an optional step, but it can only be disabled if you want to manage computer naming through an alternate process.</span></span>
      -  <span data-ttu-id="468b6-401">Compruebe que está seleccionado el paquete de **SRS V2-Set-SRSComputerName** .</span><span class="sxs-lookup"><span data-stu-id="468b6-401">Verify that the **SRS v2 - Set-SRSComputerName** package is selected.</span></span> <span data-ttu-id="468b6-402">Si no lo está, vaya al paquete y selecciónelo.</span><span class="sxs-lookup"><span data-stu-id="468b6-402">If it isn’t, browse to the package and select it.</span></span>

   4. <span data-ttu-id="468b6-403">**Aplicar sistema operativo**: este paso especifica la imagen del sistema operativo que se va a implementar y el archivo de respuesta de Sysprep desatendida que se va a usar.</span><span class="sxs-lookup"><span data-stu-id="468b6-403">**Apply Operating System**: This step specifies the operating system image to be deployed and the unattended Sysprep answer file to use.</span></span>
      -  <span data-ttu-id="468b6-404">Compruebe que esté seleccionada la imagen correcta del sistema operativo Windows 10 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="468b6-404">Verify that the correct Windows 10 Enterprise operating system image file is selected.</span></span>
      -  <span data-ttu-id="468b6-405">Compruebe que está habilitado el **uso de un archivo de respuesta Sysprep o desatendida para una instalación personalizada** y que el **paquete SRS V2-Sysprep** está seleccionado.</span><span class="sxs-lookup"><span data-stu-id="468b6-405">Verify that **Use an unattended or Sysprep answer file for a custom installation** is enabled, and the **SRS v2 - Sysprep Package** is selected.</span></span> <span data-ttu-id="468b6-406">Asegúrese también de que **nombre de archivo** está establecido en **Unattend. XML**.</span><span class="sxs-lookup"><span data-stu-id="468b6-406">Also ensure that **File Name** is set to **unattend.xml**.</span></span>

   5. <span data-ttu-id="468b6-407">**Aplicar configuración de Windows**: este paso recopila información sobre la instalación de Windows.</span><span class="sxs-lookup"><span data-stu-id="468b6-407">**Apply Windows Settings**: This step gathers information about the Windows installation.</span></span>
      -  <span data-ttu-id="468b6-408">Proporcione la información de licencias y registro, incluida la clave de producto, la contraseña de la cuenta de administrador local y la zona horaria (según sus necesidades).</span><span class="sxs-lookup"><span data-stu-id="468b6-408">Provide licensing and registration information including the product key, local administrator account password, and time zone (depending on your needs).</span></span>

   6. <span data-ttu-id="468b6-409">**Aplicar configuración de red**: este paso le permite especificar un grupo de trabajo o un nombre de dominio de Active Directory y una unidad organizativa.</span><span class="sxs-lookup"><span data-stu-id="468b6-409">**Apply Network Settings**: This step allows you to specify a workgroup or Active Directory domain name and organizational unit.</span></span>
      > [!NOTE]
      > <span data-ttu-id="468b6-410">Consulta el [dominio del sistema de la sala de Skype consideraciones](domain-joining-considerations.md) para la Unión de las acciones recomendadas que necesita tomar en la implementación de las unidades de salas de Microsoft Teams como miembros de un dominio de directorio de actve.</span><span class="sxs-lookup"><span data-stu-id="468b6-410">See [Skype Room System domain joining considerations](domain-joining-considerations.md) for recommended actions you need to take in deploying Microsoft Teams Rooms units as members of an Actve Directory domain.</span></span>
   7. <span data-ttu-id="468b6-411">**Aplicar drivers:** Este paso y sus subpasos se usan para implementar el firmware y los drivers de dispositivos aplicables según el modelo Surface Pro que tenga.</span><span class="sxs-lookup"><span data-stu-id="468b6-411">**Apply Drivers:** This step and its sub-steps are used to deploy applicable device drivers and firmware based on the Surface Pro model you have.</span></span> <span data-ttu-id="468b6-412">Actualice cada paso para especificar el paquete de controladores correspondiente asociado a esta implementación.</span><span class="sxs-lookup"><span data-stu-id="468b6-412">Update each step to specify the relevant driver package associated with this deployment.</span></span>
      -   <span data-ttu-id="468b6-413">Cada paquete de controladores está configurado para aprovechar los filtros de instrumental de administración de Windows (WMI) para implementar drivers y firmware relevantes en función de la marca y el modelo de Surface Pro.</span><span class="sxs-lookup"><span data-stu-id="468b6-413">Each driver package is configured to leverage Windows Management Instrumentation (WMI) filters to deploy relevant drivers and firmware based on the Surface Pro make and model.</span></span>
      -   <span data-ttu-id="468b6-414">Le recomendamos encarecidamente que no modifique la configuración de estos drivers; de lo contrario, la implementación podría fallar.</span><span class="sxs-lookup"><span data-stu-id="468b6-414">We highly recommend that you not alter the configuration of these drivers, otherwise deployment might fail.</span></span>

   8. <span data-ttu-id="468b6-415">**Configurar Windows y el administrador de configuración**: este paso implementa y configura el cliente de Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="468b6-415">**Set up Windows and Configuration Manager**: This step deploys and configures the Configuration Manager client.</span></span> <span data-ttu-id="468b6-416">Actualice este paso para especificar el paquete de cliente de Configuration Manager integrado.</span><span class="sxs-lookup"><span data-stu-id="468b6-416">Update this step to specify the built-in Configuration Manager Client Package.</span></span>

   9. <span data-ttu-id="468b6-417">**Instalar certificado raíz**: este paso distribuye el certificado raíz para los dispositivos que no están Unidos a un dominio y, por lo tanto, es opcional y está deshabilitado de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="468b6-417">**Install Root Certificate**: This step distributes the root certificate for non–domain-joined devices, and therefore is optional and disabled by default.</span></span>
      -   <span data-ttu-id="468b6-418">Habilite este paso si necesita implementar un certificado raíz en las unidades de salas de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="468b6-418">Enable this step if you need to deploy a root certificate to the Microsoft Teams Rooms units.</span></span>
      -   <span data-ttu-id="468b6-419">Si necesita realizar este paso, compruebe que esté seleccionada la redirección del sistema de archivos del servicio **raíz SRS V2** y **deshabilite el redireccionamiento del sistema de archivos de 64 bits** .</span><span class="sxs-lookup"><span data-stu-id="468b6-419">If you do need to perform this step, verify that the **SRS v2 – Root Certificate Package** and **Disable 64-bit file system redirection** are selected.</span></span>

   10. <span data-ttu-id="468b6-420">**Instalar y configurar el agente de supervisión**: este paso instala la versión de 64 bits del agente de Microsoft Azure monitor y configura el agente para que se conecte al área de trabajo del análisis de registros.</span><span class="sxs-lookup"><span data-stu-id="468b6-420">**Install and Configure Monitoring Agent**: This step installs the 64-bit version of the Microsoft Azure Monitor agent and configures the agent to connect to your Log Analytics workspace.</span></span>
       -   <span data-ttu-id="468b6-421">Este paso está deshabilitado de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="468b6-421">This step is disabled by default.</span></span> <span data-ttu-id="468b6-422">Habilite este paso solo si va a usar el agente de supervisión para supervisar el estado de las unidades de salas de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="468b6-422">Enable this step only if you’re going to use the Monitoring Agent to monitor the health of your Microsoft Teams Rooms units.</span></span>
       -   <span data-ttu-id="468b6-423">Edite este paso y actualice los parámetros de la línea de comandos para especificar el **identificador del área de trabajo** y la **clave del área de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="468b6-423">Edit this step and update the command-line parameters to specify your **Workspace ID** and **Workspace Key**.</span></span>
       -   <span data-ttu-id="468b6-424">Vea [configurar dispositivos de prueba para la supervisión de Azure](azure-monitor-deploy.md#configure-test-devices-for-azure-monitoring) para obtener más información sobre cómo obtener el identificador del área de trabajo de Operations Management Suite y la clave principal.</span><span class="sxs-lookup"><span data-stu-id="468b6-424">See [Configure test devices for Azure Monitoring](azure-monitor-deploy.md#configure-test-devices-for-azure-monitoring) for more information about obtaining the Operations Management Suite Workspace ID and the primary key.</span></span>
       -   <span data-ttu-id="468b6-425">Compruebe que esté seleccionada la redirección del sistema de archivos de **SRS V2-Microsoft Monitoring Agent** y **deshabilitar el redireccionamiento del sistema de archivos de 64** bits.</span><span class="sxs-lookup"><span data-stu-id="468b6-425">Verify that the **SRS v2 – Microsoft Monitoring Agent Package** and **Disable 64-bit file system redirection** are selected.</span></span>
       -   <span data-ttu-id="468b6-426">Para obtener más información sobre cómo supervisar el estado de la implementación de salas de Microsoft Teams, vea [planear la administración de salas de Microsoft Teams con Azure monitor](azure-monitor-plan.md), [implementar la administración de](azure-monitor-deploy.md) salas de Microsoft Teams con el monitor de Azure y [administrar dispositivos de salas de Microsoft Teams con el monitor de Azure](azure-monitor-manage.md).</span><span class="sxs-lookup"><span data-stu-id="468b6-426">For more information about monitoring the health of your Microsoft Teams Rooms deployment, see [Plan Microsoft Teams Rooms management with Azure Monitor](azure-monitor-plan.md), [Deploy Microsoft Teams Rooms management with Azure Monitor](azure-monitor-deploy.md) and [Manage Microsoft Teams Rooms devices with Azure Monitor](azure-monitor-manage.md).</span></span>

   11. <span data-ttu-id="468b6-427">**Copie los archivos de configuración de SRS V2**: en este paso, se copian los archivos de configuración y configuración necesarios del kit de implementación de Microsoft Teams Rooms en la unidad de disco duro local.</span><span class="sxs-lookup"><span data-stu-id="468b6-427">**Copy SRS v2 Configuration Files**: This step copies the required setup and configuration files from the Microsoft Teams Rooms deployment kit to the local hard drive.</span></span> <span data-ttu-id="468b6-428">No se necesita ninguna personalización para este paso.</span><span class="sxs-lookup"><span data-stu-id="468b6-428">No customization is required for this step.</span></span>
       -   <span data-ttu-id="468b6-429">Compruebe que se seleccione el **paquete de aplicación SRS V2-SRS** y **deshabilitar el redireccionamiento del sistema de archivos de 64 bits** .</span><span class="sxs-lookup"><span data-stu-id="468b6-429">Verify that the **SRS v2 – SRS Application Package** and **Disable 64-bit file system redirection** are selected.</span></span>

   12. <span data-ttu-id="468b6-430">**Install-SRSv2-os-updates**: este paso implementa todas las actualizaciones de sistema operativo obligatorias necesarias para la implementación de salas de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="468b6-430">**Install-SRSv2-OS-Updates**: This step deploys any mandatory operating system updates required with the Microsoft Teams Rooms deployment.</span></span> <span data-ttu-id="468b6-431">Siga este procedimiento:</span><span class="sxs-lookup"><span data-stu-id="468b6-431">Do the following:</span></span>
       -   <span data-ttu-id="468b6-432">Marque [configurar una consola de salones de Microsoft Teams](console.md) para ver qué actualizaciones son necesarias.</span><span class="sxs-lookup"><span data-stu-id="468b6-432">Check [Configure a Microsoft Teams Rooms console](console.md) to see which updates are required.</span></span>
       -   <span data-ttu-id="468b6-433">Compruebe que el **paquete de actualizaciones para el sistema operativo SRS V2** incluye todas las actualizaciones necesarias.</span><span class="sxs-lookup"><span data-stu-id="468b6-433">Verify that your **SRS v2 – OS Updates Package** includes all the required updates.</span></span>
       -   <span data-ttu-id="468b6-434">Compruebe que esté seleccionado el **paquete SRS V2 – os updates** .</span><span class="sxs-lookup"><span data-stu-id="468b6-434">Verify that the **SRS v2 – OS Updates Package** is selected.</span></span>
       -   <span data-ttu-id="468b6-435">Compruebe que la Directiva de ejecución de PowerShell esté configurada para **omitir**.</span><span class="sxs-lookup"><span data-stu-id="468b6-435">Verify that the PowerShell execution policy is set to **Bypass**.</span></span>

   13. <span data-ttu-id="468b6-436">**Reiniciar equipo**: este paso reinicia el equipo después de instalar las actualizaciones obligatorias del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="468b6-436">**Restart Computer**: This step reboots the computer after the mandatory operating system updates are installed.</span></span> <span data-ttu-id="468b6-437">No se necesita ninguna personalización para este paso.</span><span class="sxs-lookup"><span data-stu-id="468b6-437">No customization is required for this step.</span></span>

   14. <span data-ttu-id="468b6-438">**Configurar componentes de Windows**: este paso configura las características necesarias de Windows.</span><span class="sxs-lookup"><span data-stu-id="468b6-438">**Configure Windows Components**: This step configures the required Windows features.</span></span> <span data-ttu-id="468b6-439">No se necesita ninguna personalización para este paso.</span><span class="sxs-lookup"><span data-stu-id="468b6-439">No customization is required for this step.</span></span>

   15. <span data-ttu-id="468b6-440">**Reiniciar equipo**: este paso reinicia el equipo después de configurar las características de Windows.</span><span class="sxs-lookup"><span data-stu-id="468b6-440">**Restart Computer**: This step reboots the computer after the Windows features are configured.</span></span> <span data-ttu-id="468b6-441">No se necesita ninguna personalización para este paso.</span><span class="sxs-lookup"><span data-stu-id="468b6-441">No customization is required for this step.</span></span>

   16. <span data-ttu-id="468b6-442">**Agregar usuario local de Skype**: este paso crea la cuenta de Skype local que se usa para iniciar sesión automáticamente en Windows e iniciar la aplicación salas de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="468b6-442">**Add Local Skype User**: This step creates the local Skype account used to automatically sign in to Windows and start the Microsoft Teams Rooms application.</span></span> <span data-ttu-id="468b6-443">Este paso no tiene ningún paquete de software asociado, y no se necesita ninguna personalización para él.</span><span class="sxs-lookup"><span data-stu-id="468b6-443">This step doesn’t have any software package associated with it, and no customization is required for it.</span></span>

   17. <span data-ttu-id="468b6-444">**Instalar y configurar la aplicación SRS**: este paso configura la instalación de la aplicación salas de Microsoft Teams para el siguiente arranque del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="468b6-444">**Set up and configure SRS application**: This step configures the Microsoft Teams Rooms application installation for the next boot of the operating system.</span></span>
       -   <span data-ttu-id="468b6-445">Compruebe que esté seleccionada la **configuración de SRS V2-configure SRS Setup Package** and **Disable 64-bit File System** .</span><span class="sxs-lookup"><span data-stu-id="468b6-445">Verify that the **SRS v2 – Configure SRS Setup Package** and **Disable 64-bit file system redirection** are selected.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="468b6-446">Es muy importante que los pasos de la secuencia de tareas estén en el orden indicado.</span><span class="sxs-lookup"><span data-stu-id="468b6-446">It is very important that the task sequence steps must be in the provided order.</span></span> <span data-ttu-id="468b6-447">Modificar el orden de los pasos o configurar pasos adicionales puede estropear la implementación.</span><span class="sxs-lookup"><span data-stu-id="468b6-447">Modifying the order of steps, or configuring additional steps might break the deployment.</span></span>
>
> <span data-ttu-id="468b6-448">**Configurar y configurar** el paso de la aplicación SRS debe ser el último paso de la secuencia de tareas; de lo contrario, la implementación podría fallar.</span><span class="sxs-lookup"><span data-stu-id="468b6-448">**Set up and configure SRS application** step must be the last step in the task sequence, otherwise the deployment might fail.</span></span>

### <a name="create-deployment-for-the-task-sequence"></a><span data-ttu-id="468b6-449">Crear una implementación para la secuencia de tareas</span><span class="sxs-lookup"><span data-stu-id="468b6-449">Create deployment for the task sequence</span></span>

1. <span data-ttu-id="468b6-450">Seleccione la secuencia de tareas y, a continuación, seleccione **implementar**.</span><span class="sxs-lookup"><span data-stu-id="468b6-450">Select the task sequence, and then select **Deploy**.</span></span>

2. <span data-ttu-id="468b6-451">Seleccione **examinar** para seleccionar recopilación de destino para la implementación.</span><span class="sxs-lookup"><span data-stu-id="468b6-451">Select **Browse** to select target collection for deployment.</span></span>

3. <span data-ttu-id="468b6-452">Seleccione **todos los equipos desconocidos** y, después, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="468b6-452">Select **All Unknown Computers** and then select **OK**.</span></span>

4. <span data-ttu-id="468b6-453">Seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="468b6-453">Select **Next**.</span></span>

5. <span data-ttu-id="468b6-454">Seleccione **disponible** en la lista desplegable **propósito** .</span><span class="sxs-lookup"><span data-stu-id="468b6-454">Select **Available** on the **Purpose** drop down list.</span></span>

6. <span data-ttu-id="468b6-455">Seleccione **solo medios y PXE** en la lista **hacer disponible hasta el siguiente** y, a continuación, seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="468b6-455">Select **Only Media and PXE** in the **Make available to the following** list, and then select **Next**.</span></span>
   > [!WARNING]
   > <span data-ttu-id="468b6-456">Es muy importante que el **propósito** esté establecido en **disponible**.</span><span class="sxs-lookup"><span data-stu-id="468b6-456">It is very important that **Purpose** is set to **Available**.</span></span> <span data-ttu-id="468b6-457">Asegúrese de que el **propósito** **no** esté establecido en **requerido**.</span><span class="sxs-lookup"><span data-stu-id="468b6-457">Make sure that the **Purpose** is **NOT** set to **Required**.</span></span> <span data-ttu-id="468b6-458">Además, asegúrese de que selecciona **solo medios y PXE** en la forma **disponible para lo siguiente**.</span><span class="sxs-lookup"><span data-stu-id="468b6-458">Also make sure that you select **Only Media and PXE** in the **Make available to the following**.</span></span>
   >
   > <span data-ttu-id="468b6-459">La configuración de estos valores en algo diferente puede hacer que todos los equipos obtengan la imagen de implementación de salas de Microsoft Teams al arrancar.</span><span class="sxs-lookup"><span data-stu-id="468b6-459">Setting these values to something else might cause all computers to get the Microsoft Teams Rooms deployment image when booted.</span></span>
7. <span data-ttu-id="468b6-460">No especifique ninguna programación y seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="468b6-460">Do not specify any schedule and select **Next**.</span></span>

8. <span data-ttu-id="468b6-461">No cambie nada en la sección **experiencia del usuario** y seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="468b6-461">Do not change anything within the **User Experience** section and select **Next**.</span></span>

9. <span data-ttu-id="468b6-462">No cambie nada dentro de la sección **alertas** y seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="468b6-462">Do not change anything within the **Alerts** section and select **Next**.</span></span>

10. <span data-ttu-id="468b6-463">No cambie nada en la sección de **puntos de distribución** y seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="468b6-463">Do not change anything within the **Distribution Points** section and select **Next**.</span></span>

11. <span data-ttu-id="468b6-464">Confirme la configuración y, a continuación, seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="468b6-464">Confirm the settings and then select **Next**.</span></span>

12. <span data-ttu-id="468b6-465">Seleccione **cerrar**.</span><span class="sxs-lookup"><span data-stu-id="468b6-465">Select **Close**.</span></span>

<a name="validate-and-troubleshoot-the-solution"></a><span data-ttu-id="468b6-466">Validar y solucionar problemas de la solución</span><span class="sxs-lookup"><span data-stu-id="468b6-466">Validate and troubleshoot the solution</span></span>
--------------------------------------

<span data-ttu-id="468b6-467">Después de completar las secuencias de tareas de Microsoft Endpoint Configuration Manager, tendrá que realizar una ejecución de prueba para validar que la secuencia de tareas puede implementar y configurar las unidades de salas de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="468b6-467">After you’ve completed the Microsoft Endpoint Configuration Manager task sequences, you’ll need to perform a test run to validate that the task sequence can deploy and configure Microsoft Teams Rooms units.</span></span>

1.  <span data-ttu-id="468b6-468">Conecte el dispositivo de prueba a la red cableada mediante uno de los adaptadores Ethernet compatibles o usando la superficie del Dock.</span><span class="sxs-lookup"><span data-stu-id="468b6-468">Connect the test device to the wired network by using one of the supported Ethernet adapters or using the Surface dock.</span></span> <span data-ttu-id="468b6-469">Si la funcionalidad de arranque PXE no se ha configurado para su entorno, puede usar la imagen de arranque de la unidad flash USB [que creó anteriormente](https://docs.microsoft.com/configmgr/osd/deploy-use/create-bootable-media) para arrancar desde USB y conectarse a Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="468b6-469">If PXE boot functionality hasn’t been configured for your environment, you can use the boot image on the USB flash drive [that you created earlier](https://docs.microsoft.com/configmgr/osd/deploy-use/create-bootable-media) to boot from USB and connect to Configuration Manager.</span></span>

2.  <span data-ttu-id="468b6-470">Acceda al firmware e inicie el inicio PXE:</span><span class="sxs-lookup"><span data-stu-id="468b6-470">Access the firmware and initiate PXE boot:</span></span>

    1.  <span data-ttu-id="468b6-471">Cerciórese de que el dispositivo Surface esté apagado.</span><span class="sxs-lookup"><span data-stu-id="468b6-471">Ensure the Surface device is powered off.</span></span>

    2.  <span data-ttu-id="468b6-472">Mantén pulsado el botón **subir volumen** .</span><span class="sxs-lookup"><span data-stu-id="468b6-472">Press and hold the **Volume Up** button.</span></span>

    3.  <span data-ttu-id="468b6-473">Presione y suelte el botón **Power (encendido** ).</span><span class="sxs-lookup"><span data-stu-id="468b6-473">Press and release the **Power** button.</span></span>

    4.  <span data-ttu-id="468b6-474">Cuando el dispositivo empiece a arrancar, suelte el botón **subir volumen** .</span><span class="sxs-lookup"><span data-stu-id="468b6-474">After the device begins to boot, release the **Volume Up** button.</span></span>

    5.  <span data-ttu-id="468b6-475">Seleccione **configuración de arranque**.</span><span class="sxs-lookup"><span data-stu-id="468b6-475">Select **Boot configuration**.</span></span>

    6.  <span data-ttu-id="468b6-476">Siga uno de estos pasos:</span><span class="sxs-lookup"><span data-stu-id="468b6-476">Do one of the following:</span></span>

        -   <span data-ttu-id="468b6-477">Seleccione **arranque PXE**y arrástrelo hasta la parte superior de la lista.</span><span class="sxs-lookup"><span data-stu-id="468b6-477">Select **PXE boot**, and drag it to the top of the list.</span></span> <span data-ttu-id="468b6-478">Como alternativa, puedes deslizar el dedo hacia la izquierda en el adaptador de red para arrancar el dispositivo inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="468b6-478">Alternatively, you can swipe left on the network adapter to boot to the device immediately.</span></span> <span data-ttu-id="468b6-479">Esto no afectará el orden de inicio.</span><span class="sxs-lookup"><span data-stu-id="468b6-479">This won’t affect the boot order.</span></span>
        -   <span data-ttu-id="468b6-480">Seleccione la unidad flash USB que contiene el medio de inicio.</span><span class="sxs-lookup"><span data-stu-id="468b6-480">Select the USB flash drive that holds the boot media.</span></span>

3.  <span data-ttu-id="468b6-481">Seleccione **salir**y, a continuación, **reiniciar ahora**.</span><span class="sxs-lookup"><span data-stu-id="468b6-481">Select **Exit**, and then select **Restart Now**.</span></span>

4.  <span data-ttu-id="468b6-482">Cuando se le solicite, seleccione **entrar** para el servicio de inicio de red.</span><span class="sxs-lookup"><span data-stu-id="468b6-482">When prompted, select **Enter** for network boot service.</span></span>

5.  <span data-ttu-id="468b6-483">Windows PE se cargará en la memoria y se iniciará el Asistente para secuencia de tareas.</span><span class="sxs-lookup"><span data-stu-id="468b6-483">Windows PE will load into memory, and the Task Sequence Wizard will start.</span></span> <span data-ttu-id="468b6-484">Seleccione **siguiente** para continuar.</span><span class="sxs-lookup"><span data-stu-id="468b6-484">Select **Next** to continue.</span></span>

6.  <span data-ttu-id="468b6-485">Seleccione la secuencia de tareas que importó anteriormente y, a continuación, seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="468b6-485">Select the task sequence that you imported earlier, and then select **Next**.</span></span>

7.  <span data-ttu-id="468b6-486">Después de aplicar la configuración del disco, se le pedirá que especifique un nombre de equipo para el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="468b6-486">After the disk configuration is applied, you’ll be prompted to specify a computer name for the device.</span></span> <span data-ttu-id="468b6-487">La interfaz de usuario mostrará un nombre de equipo recomendado según el número de serie del dispositivo Surface Pro.</span><span class="sxs-lookup"><span data-stu-id="468b6-487">The user interface will display a recommended computer name based on the serial number of the Surface Pro device.</span></span> <span data-ttu-id="468b6-488">Puede aceptar el nombre propuesto o especificar uno nuevo.</span><span class="sxs-lookup"><span data-stu-id="468b6-488">You can either accept the proposed name or specify a new one.</span></span> <span data-ttu-id="468b6-489">Siga las instrucciones de la pantalla asignación de nombre de equipo.</span><span class="sxs-lookup"><span data-stu-id="468b6-489">Follow the instructions on the computer name assignment screen.</span></span> <span data-ttu-id="468b6-490">Al seleccionar **Aceptar**, comienza la implementación.</span><span class="sxs-lookup"><span data-stu-id="468b6-490">When you select **Accept**, the deployment begins.</span></span>

8.  <span data-ttu-id="468b6-491">El resto del proceso de implementación es automático y no pide más entradas del usuario.</span><span class="sxs-lookup"><span data-stu-id="468b6-491">The rest of the deployment process is automatic and doesn’t ask for any more user input.</span></span>

9.  <span data-ttu-id="468b6-492">Después de que la secuencia de tareas de implementación termine de configurar el dispositivo, verá la siguiente pantalla de configuración que le pedirá que configure las opciones de la aplicación salas de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="468b6-492">After the deployment task sequence finishes configuring the device, you’ll see the following configuration screen that asks you to configure the Microsoft Teams Rooms application settings.</span></span>

    ![Pantalla inicial de la aplicación salas de Microsoft Teams](../media/room-systems-scale-image2.png)

10.  <span data-ttu-id="468b6-494">Conecte la Surface Pro a la consola de salas de Microsoft Teams y configure las opciones de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="468b6-494">Plug the Surface Pro into the Microsoft Teams Rooms console, and configure the application settings.</span></span>

11.  <span data-ttu-id="468b6-495">Compruebe que las capacidades enumeradas en la [ayuda de Microsoft Teams Rooms](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2) estén funcionando en el dispositivo implementado.</span><span class="sxs-lookup"><span data-stu-id="468b6-495">Validate that the capabilities listed in [Microsoft Teams Rooms help](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2) are working on the deployed device.</span></span>


<span data-ttu-id="468b6-496">Para solucionar un error de instalación, consulte el archivo **SMSTS. log** , en el que se registran todos los pasos ejecutados en una secuencia de tareas de Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="468b6-496">To troubleshoot a failed installation, check the **SMSTS.log** file, which logs all the steps executed in a Configuration Manager task sequence.</span></span>

<span data-ttu-id="468b6-497">El archivo SMSTS. log se almacena en una de varias rutas, dependiendo de la fase del proceso de compilación.</span><span class="sxs-lookup"><span data-stu-id="468b6-497">The SMSTS.log file is stored on one of a number of paths, depending on the stage of the build process.</span></span> <span data-ttu-id="468b6-498">Consulte la tabla siguiente para identificar la ruta de acceso al archivo SMSTS. log.</span><span class="sxs-lookup"><span data-stu-id="468b6-498">Check the following table to identify the path to the SMSTS.log file.</span></span>


| <span data-ttu-id="468b6-499">**Fase de implementación**</span><span class="sxs-lookup"><span data-stu-id="468b6-499">**Deployment phase**</span></span>                                                            | <span data-ttu-id="468b6-500">**Ruta de registro de secuencia de tareas**</span><span class="sxs-lookup"><span data-stu-id="468b6-500">**Task sequence log path**</span></span>                         |
|---------------------------------------------------------------------------------|----------------------------------------------------|
| <span data-ttu-id="468b6-501">WinPE, antes del formato HDD</span><span class="sxs-lookup"><span data-stu-id="468b6-501">WinPE, before HDD format</span></span>                                                        | <span data-ttu-id="468b6-502">X:\\Windows\\Temp\\smstslog\\smsts. log</span><span class="sxs-lookup"><span data-stu-id="468b6-502">X:\\Windows\\Temp\\smstslog\\smsts.log</span></span>             |
| <span data-ttu-id="468b6-503">WinPE, después de formato HDD</span><span class="sxs-lookup"><span data-stu-id="468b6-503">WinPE, after HDD format</span></span>                                                         | <span data-ttu-id="468b6-504">C:\\registros\\\\de _SMSTaskSequence\\Smstslog smsts. log</span><span class="sxs-lookup"><span data-stu-id="468b6-504">C:\\_SMSTaskSequence\\Logs\\Smstslog\\smsts.log</span></span>    |
| <span data-ttu-id="468b6-505">Sistema operativo implementado antes de instalar el agente de administrador de configuración</span><span class="sxs-lookup"><span data-stu-id="468b6-505">Operating system deployed, before the Configuration Manager agent was installed</span></span> | <span data-ttu-id="468b6-506">c:\\registros\\\\de _SMSTaskSequence\\Smstslog smsts. log</span><span class="sxs-lookup"><span data-stu-id="468b6-506">c:\\_SMSTaskSequence\\Logs\\Smstslog\\smsts.log</span></span>    |
| <span data-ttu-id="468b6-507">Sistema operativo y el agente de Configuration Manager implementado</span><span class="sxs-lookup"><span data-stu-id="468b6-507">Operating system and the Configuration Manager agent deployed</span></span>                   | <span data-ttu-id="468b6-508">% WINDIR%\\system32\\CCM\\registra\\Smstslog\\smsts. log</span><span class="sxs-lookup"><span data-stu-id="468b6-508">%windir%\\System32\\ccm\\logs\\Smstslog\\smsts.log</span></span> |
| <span data-ttu-id="468b6-509">Ejecución de la secuencia de tareas completada</span><span class="sxs-lookup"><span data-stu-id="468b6-509">Task sequence execution complete</span></span>                                                | <span data-ttu-id="468b6-510">% WINDIR%\\system32\\CCM\\registra\\smsts. log</span><span class="sxs-lookup"><span data-stu-id="468b6-510">%windir%\\System32\\ccm\\logs\\smsts.log</span></span>           |

> [!TIP]
> <span data-ttu-id="468b6-511">Puede seleccionar **F8** en cualquier momento durante la secuencia de tareas para abrir una consola de comandos y, a continuación, obtener acceso al archivo SMSTS. log.</span><span class="sxs-lookup"><span data-stu-id="468b6-511">You can select **F8** at any time during the task sequence to open a command console, and then get access to the SMSTS.log file.</span></span>

<span data-ttu-id="468b6-512">Para solucionar problemas de inicio PXE, consulte los dos archivos de registro en el servidor de Configuration Manager que son específicos de las acciones de PXE:</span><span class="sxs-lookup"><span data-stu-id="468b6-512">To troubleshoot PXE boot issues, check the two log files on the Configuration Manager server that are specific to PXE actions:</span></span>

-   <span data-ttu-id="468b6-513">**Pxecontrol. log**, ubicado en el directorio de registros de instalación de Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="468b6-513">**Pxecontrol.log**, located in the Configuration Manager installation logs directory</span></span>

-   <span data-ttu-id="468b6-514">**Smspxe. log**, que se encuentra en el directorio de registros del punto de administración de Configuration Manager (MP)</span><span class="sxs-lookup"><span data-stu-id="468b6-514">**Smspxe.log**, located in Configuration Manager Management Point (MP) logs directory</span></span>

<span data-ttu-id="468b6-515">Para obtener una lista completa de los archivos de registro que puede usar para solucionar problemas en la instalación de Configuration Manager, consulte la [Referencia del archivo de registro](https://docs.microsoft.com/configmgr/core/plan-design/hierarchy/log-files)del administrador de configuración de Microsoft Endpoint.</span><span class="sxs-lookup"><span data-stu-id="468b6-515">For a complete list of the log files that you can use to further troubleshoot your Configuration Manager installation, see the Microsoft Endpoint Configuration Manager [Log file reference](https://docs.microsoft.com/configmgr/core/plan-design/hierarchy/log-files).</span></span>
