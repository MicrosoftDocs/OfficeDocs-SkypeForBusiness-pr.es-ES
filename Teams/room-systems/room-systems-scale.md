---
title: Implementar salas de Microsoft Teams con System Center Configuration Manager
author: lanachin
ms.author: v-lanac
ms.reviewer: Turgayo
manager: serdars
ms.date: 5/10/2018
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.custom: Strat_SB_Admin
ms.assetid: 678689e4-d547-499b-be64-7d8f16dd8668
ms.collection: M365-voice
description: Lea este tema para obtener información sobre la implementación de salas de Microsoft Teams en implementaciones de gran escala.
ms.openlocfilehash: 34bd984d16da4eeb1934c7fda7bbadb0837240be
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34305446"
---
# <a name="deploy-microsoft-teams-rooms-by-using-system-center-configuration-manager"></a><span data-ttu-id="eefb5-103">Implementar salas de Microsoft Teams con System Center Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="eefb5-103">Deploy Microsoft Teams Rooms by using System Center Configuration Manager</span></span>

<span data-ttu-id="eefb5-104">Este artículo le proporciona toda la información necesaria para crear implementaciones de salas de Microsoft Teams mediante System Center Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="eefb5-104">This article gives you all the necessary information to create your Microsoft Teams Rooms deployments by using System Center Configuration Manager.</span></span>

<span data-ttu-id="eefb5-105">Con los métodos fáciles de usar proporciona System Center Configuration Manager, puede implementar el sistema operativo y otras aplicaciones en varios dispositivos de destino.</span><span class="sxs-lookup"><span data-stu-id="eefb5-105">With the easy-to-use methods provided by System Center Configuration Manager, you can deploy the operating system and other applications to multiple target devices.</span></span>

<span data-ttu-id="eefb5-106">Use el método que se muestra a continuación para guiarse a través de la configuración de Configuration Manager y personalizar los paquetes de ejemplo y los scripts proporcionados en esta guía según sea necesario para su organización.</span><span class="sxs-lookup"><span data-stu-id="eefb5-106">Use the approach illustrated below to guide you through your Configuration Manager configuration, and customize the sample packages and scripts provided throughout this guidance as needed for your organization.</span></span>

![Proceso de implementación de salas de Microsoft Teams con Configuration Manager](../media/room-systems-scale-image1.png)

> [!IMPORTANT]
> <span data-ttu-id="eefb5-108">Esta solución solo ha sido probada con implementaciones basadas en Surface Pro.</span><span class="sxs-lookup"><span data-stu-id="eefb5-108">This solution has only been tested with Surface Pro–based deployments.</span></span> <span data-ttu-id="eefb5-109">Siga las instrucciones del fabricante para configuraciones que no se basan en Surface Pro.</span><span class="sxs-lookup"><span data-stu-id="eefb5-109">Follow the manufacturer’s guidelines for configurations that aren’t based on Surface Pro.</span></span>

## <a name="validate-prerequisites"></a><span data-ttu-id="eefb5-110">Validar los requisitos previos</span><span class="sxs-lookup"><span data-stu-id="eefb5-110">Validate prerequisites</span></span>

<span data-ttu-id="eefb5-111">Para implementar salas de Microsoft Teams con Configuration Manager, asegúrese de cumplir los siguientes requisitos y requisitos.</span><span class="sxs-lookup"><span data-stu-id="eefb5-111">To deploy Microsoft Teams Rooms with Configuration Manager, ensure that you meet the following prerequisites and requirements.</span></span>

### <a name="system-center-configuration-manager-requirements"></a><span data-ttu-id="eefb5-112">Requisitos de System Center Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="eefb5-112">System Center Configuration Manager requirements</span></span>

-   <span data-ttu-id="eefb5-113">La versión de System Center Configuration Manager debe tener al menos 1706 o superior.</span><span class="sxs-lookup"><span data-stu-id="eefb5-113">System Center Configuration Manager version must be at least 1706 or above.</span></span> <span data-ttu-id="eefb5-114">Le recomendamos que use 1710 o una versión posterior.</span><span class="sxs-lookup"><span data-stu-id="eefb5-114">We recommend using 1710 or later.</span></span> <span data-ttu-id="eefb5-115">Consulte [soporte técnico para Windows 10 en System Center Configuration Manager](https://docs.microsoft.com/sccm/core/plan-design/configs/support-for-windows-10#windows-10-as-a-client) para obtener información sobre las versiones de Windows 10 compatibles con Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="eefb5-115">Check out [Support for Windows 10 in System Center Configuration Manager](https://docs.microsoft.com/sccm/core/plan-design/configs/support-for-windows-10#windows-10-as-a-client) to learn about the Windows 10 versions that Configuration Manager supports.</span></span>

-   <span data-ttu-id="eefb5-116">Debe instalarse una versión compatible de Windows Assessment and Deployment Kit (ADK) para Windows 10.</span><span class="sxs-lookup"><span data-stu-id="eefb5-116">A supported version of Windows Assessment and Deployment Kit (ADK) for Windows 10 must be installed.</span></span> <span data-ttu-id="eefb5-117">Vea las versiones de [Windows 10 ADK](https://docs.microsoft.com/sccm/core/plan-design/configs/support-for-windows-10#windows-10-adk) que puede usar con diferentes versiones de Configuration Manager y asegúrese de que su implementación incluya la versión correcta.</span><span class="sxs-lookup"><span data-stu-id="eefb5-117">See the versions of the [Windows 10 ADK](https://docs.microsoft.com/sccm/core/plan-design/configs/support-for-windows-10#windows-10-adk) that you can use with different versions of Configuration Manager, and ensure that your deployment includes the correct version.</span></span>

-   <span data-ttu-id="eefb5-118">Los servidores del sistema de sitio deben tener asignado el rol de punto de distribución y las imágenes de arranque deben estar habilitadas para [admitir el entorno de ejecución de inicio previo (PXE)](https://docs.microsoft.com/sccm/osd/deploy-use/use-pxe-to-deploy-windows-over-the-network) para habilitar implementaciones iniciadas por la red.</span><span class="sxs-lookup"><span data-stu-id="eefb5-118">The site system servers must have been assigned the distribution point role, and the boot images should be enabled for [preboot execution environment (PXE) support](https://docs.microsoft.com/sccm/osd/deploy-use/use-pxe-to-deploy-windows-over-the-network) to enable network-initiated deployments.</span></span> <span data-ttu-id="eefb5-119">Si la compatibilidad con PXE no está habilitada, puede usar [medios de arranque](https://docs.microsoft.com/sccm/osd/deploy-use/use-bootable-media-to-deploy-windows-over-the-network) para las implementaciones.</span><span class="sxs-lookup"><span data-stu-id="eefb5-119">If PXE support isn’t enabled, you can use [bootable media](https://docs.microsoft.com/sccm/osd/deploy-use/use-bootable-media-to-deploy-windows-over-the-network) for your deployments.</span></span>

-   <span data-ttu-id="eefb5-120">Una cuenta de acceso a la red debe estar configurada para admitir nuevos escenarios de implementación de equipos.</span><span class="sxs-lookup"><span data-stu-id="eefb5-120">A network access account must be configured to support new computer (bare metal) deployment scenarios.</span></span> <span data-ttu-id="eefb5-121">Para obtener más información sobre la configuración de una cuenta de acceso a la red, consulte [administrar cuentas para obtener acceso al contenido en System Center Configuration Manager](https://docs.microsoft.com/sccm/core/plan-design/hierarchy/manage-accounts-to-access-content#bkmk_NAA).</span><span class="sxs-lookup"><span data-stu-id="eefb5-121">To learn more about the configuration of a network access account, see [Manage accounts to access content in System Center Configuration Manager](https://docs.microsoft.com/sccm/core/plan-design/hierarchy/manage-accounts-to-access-content#bkmk_NAA).</span></span>

-   <span data-ttu-id="eefb5-122">Le recomendamos que habilite la [compatibilidad con multidifusión](https://docs.microsoft.com/sccm/osd/deploy-use/use-multicast-to-deploy-windows-over-the-network), si es probable que implemente la misma imagen de salas de Microsoft Teams en varias unidades al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="eefb5-122">We recommend that you enable [multicast support](https://docs.microsoft.com/sccm/osd/deploy-use/use-multicast-to-deploy-windows-over-the-network), if you’re likely to deploy the same Microsoft Teams Rooms image to multiple units at the same time.</span></span>

### <a name="networking-requirements"></a><span data-ttu-id="eefb5-123">Requisitos de red</span><span class="sxs-lookup"><span data-stu-id="eefb5-123">Networking requirements</span></span>

-   <span data-ttu-id="eefb5-124">Su red debe tener un servidor de protocolo de configuración dinámica de host (DHCP), configurado para la distribución automática de direcciones IP a las subredes donde se implementarán las unidades de salas de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="eefb5-124">Your network should have a Dynamic Host Configuration Protocol (DHCP) server, configured for automatic IP address distribution to the subnets where Microsoft Teams Rooms units will be deployed.</span></span>

    > [!NOTE]
    > <span data-ttu-id="eefb5-125">La duración de la concesión DHCP debe establecerse en un valor superior a la duración de la implementación de la imagen.</span><span class="sxs-lookup"><span data-stu-id="eefb5-125">DHCP lease duration must be set to a value longer than the image deployment duration.</span></span> <span data-ttu-id="eefb5-126">De lo contrario, la implementación podría fallar.</span><span class="sxs-lookup"><span data-stu-id="eefb5-126">Otherwise, the deployment might fail.</span></span>

-   <span data-ttu-id="eefb5-127">Su red, incluidos los conmutadores y las LANs virtuales (VLAN), debe estar configurada para admitir PXE.</span><span class="sxs-lookup"><span data-stu-id="eefb5-127">Your network, including switches and virtual LANs (VLANs), should be configured to support PXE.</span></span> <span data-ttu-id="eefb5-128">Para obtener más información sobre la ayuda de IP y la configuración de PXE, consulte su proveedor de red.</span><span class="sxs-lookup"><span data-stu-id="eefb5-128">Refer to your network vendor for more information about IP Helper and PXE configuration.</span></span> <span data-ttu-id="eefb5-129">Como alternativa, puede usar [medios de arranque](https://docs.microsoft.com/sccm/osd/deploy-use/use-bootable-media-to-deploy-windows-over-the-network) para las implementaciones, si la compatibilidad con PXE no está habilitada.</span><span class="sxs-lookup"><span data-stu-id="eefb5-129">Alternatively, you can use [bootable media](https://docs.microsoft.com/sccm/osd/deploy-use/use-bootable-media-to-deploy-windows-over-the-network) for your deployments, if PXE support isn’t enabled.</span></span>

    > [!NOTE]
    > <span data-ttu-id="eefb5-130">Para los dispositivos Surface Pro, el arranque desde la red (arranque PXE) solo se admite al usar un adaptador Ethernet o una estación de acoplamiento de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="eefb5-130">For Surface Pro devices, booting from the network (PXE boot) is only supported when you use an Ethernet adapter or docking station from Microsoft.</span></span> <span data-ttu-id="eefb5-131">Los adaptadores Ethernet de terceros no admiten el arranque PXE con Surface Pro.</span><span class="sxs-lookup"><span data-stu-id="eefb5-131">Third-party Ethernet adapters don’t support PXE boot with Surface Pro.</span></span> <span data-ttu-id="eefb5-132">Para obtener más información [, consulte adaptadores de Ethernet e implementación de superficies](https://docs.microsoft.com/surface/ethernet-adapters-and-surface-device-deployment) .</span><span class="sxs-lookup"><span data-stu-id="eefb5-132">See [Ethernet adapters and Surface deployment](https://docs.microsoft.com/surface/ethernet-adapters-and-surface-device-deployment) for more information.</span></span>

## <a name="configure-system-center-configuration-manager-for-operating-system-deployment"></a><span data-ttu-id="eefb5-133">Configurar System Center Configuration Manager para la implementación de sistemas operativos</span><span class="sxs-lookup"><span data-stu-id="eefb5-133">Configure System Center Configuration Manager for operating system deployment</span></span>

<span data-ttu-id="eefb5-134">En este artículo se supone que ya tiene una implementación correcta de System Center Configuration Manager y no se detallan todos los pasos necesarios para implementar y configurar Configuration Manager desde cero.</span><span class="sxs-lookup"><span data-stu-id="eefb5-134">This article assumes you already have a healthy System Center Configuration Manager deployment, and doesn’t detail all the steps required to deploy and configure Configuration Manager from scratch.</span></span> <span data-ttu-id="eefb5-135">La [documentación y la guía de configuración](https://docs.microsoft.com/sccm/) de System Center Configuration Manager es un excelente recurso; le recomendamos que comience con estos recursos si todavía no ha implementado Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="eefb5-135">The [documentation and the configuration guidance](https://docs.microsoft.com/sccm/) on the System Center Configuration Manager is a great resource; we recommend you start with these resources if you haven’t yet deployed Configuration Manager.</span></span>

<span data-ttu-id="eefb5-136">Use las siguientes instrucciones para comprobar que las características de la implementación del sistema operativo (OSD) están configuradas correctamente.</span><span class="sxs-lookup"><span data-stu-id="eefb5-136">Use the following instructions to verify that the operating system deployment (OSD) features are configured properly.</span></span>

### <a name="validate-and-upgrade-configuration-manager"></a><span data-ttu-id="eefb5-137">Validar y actualizar Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="eefb5-137">Validate and upgrade Configuration Manager</span></span>

1.  <span data-ttu-id="eefb5-138">En la consola del administrador de configuración, vaya a **actualizaciones y mantenimiento**de la **Administración** \> .</span><span class="sxs-lookup"><span data-stu-id="eefb5-138">In the Configuration Manager console, go to **Administration** \> **Updates and Servicing**.</span></span>

2.  <span data-ttu-id="eefb5-139">Compruebe la compilación instalada y las actualizaciones aplicables que aún no se han instalado.</span><span class="sxs-lookup"><span data-stu-id="eefb5-139">Check the installed build and applicable updates that haven’t been installed yet.</span></span>

3.  <span data-ttu-id="eefb5-140">Revise el [soporte técnico para Windows 10 en System Center Configuration Manager](https://docs.microsoft.com/sccm/core/plan-design/configs/support-for-windows-10#windows-10-as-a-client). Si necesita actualizar su implementación, seleccione la actualización que quiera instalar y, después, haga clic en **Descargar**.</span><span class="sxs-lookup"><span data-stu-id="eefb5-140">Review [Support for Windows 10 in System Center Configuration Manager](https://docs.microsoft.com/sccm/core/plan-design/configs/support-for-windows-10#windows-10-as-a-client); if you need to upgrade your deployment, select the update you want to install, and then select **Download**.</span></span>

4.  <span data-ttu-id="eefb5-141">Una vez completada la descarga, seleccione la actualización y, a continuación, seleccione **instalar paquete de actualización**.</span><span class="sxs-lookup"><span data-stu-id="eefb5-141">After the download is complete, select the update, and then select **Install Update Pack**.</span></span>

### <a name="configure-distribution-points-to-support-pxe-and-multicast"></a><span data-ttu-id="eefb5-142">Configurar puntos de distribución para admitir PXE y multicast</span><span class="sxs-lookup"><span data-stu-id="eefb5-142">Configure distribution points to support PXE and multicast</span></span>

1.  <span data-ttu-id="eefb5-143">En la consola del administrador de configuración, vaya a **puntos de distribución**de **Administración** \> .</span><span class="sxs-lookup"><span data-stu-id="eefb5-143">In the Configuration Manager console, go to **Administration** \> **Distribution Points**.</span></span>

2.  <span data-ttu-id="eefb5-144">Seleccione el servidor del punto de distribución que servirá a la implementación de salas de Microsoft Teams y, a continuación, seleccione **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="eefb5-144">Select the distribution point server that will serve the Microsoft Teams Rooms deployment, and then select **Properties**.</span></span>

3.  <span data-ttu-id="eefb5-145">Seleccione la pestaña **PXE** y asegúrese de que estén habilitadas las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="eefb5-145">Select the **PXE** tab, and ensure that the following settings are enabled:</span></span>
    -   <span data-ttu-id="eefb5-146">Habilitar la compatibilidad con PXE para clientes</span><span class="sxs-lookup"><span data-stu-id="eefb5-146">Enable PXE support for clients</span></span>
    -   <span data-ttu-id="eefb5-147">Permitir que este punto de distribución responda a solicitudes PXE entrantes</span><span class="sxs-lookup"><span data-stu-id="eefb5-147">Allow this distribution point to respond to incoming PXE requests</span></span>
    -   <span data-ttu-id="eefb5-148">Habilitar compatibilidad con equipos desconocidos</span><span class="sxs-lookup"><span data-stu-id="eefb5-148">Enable unknown computer support</span></span>

4.  <span data-ttu-id="eefb5-149">*Opcional:* Para habilitar la compatibilidad con multidifusión \*\*\*\* , seleccione la pestaña multidifusión y asegúrese de que estén habilitadas las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="eefb5-149">*Optional:* To enable multicast support, select the **Multicast** tab, and ensure that the following settings are enabled:</span></span>
    -   <span data-ttu-id="eefb5-150">Habilitar la multidifusión para enviar datos simultáneamente a varios clientes</span><span class="sxs-lookup"><span data-stu-id="eefb5-150">Enable multicast to simultaneously send data to multiple clients</span></span>
    -   <span data-ttu-id="eefb5-151">Configurar el intervalo de puertos UDP según la recomendación del equipo de red</span><span class="sxs-lookup"><span data-stu-id="eefb5-151">Configure the UDP port range as per your network team’s recommendation</span></span>

### <a name="configure-the-network-access-account"></a><span data-ttu-id="eefb5-152">Configurar la cuenta de acceso a la red</span><span class="sxs-lookup"><span data-stu-id="eefb5-152">Configure the Network Access Account</span></span>

1.  <span data-ttu-id="eefb5-153">En la consola del administrador de configuración, vaya a **sitios**de **configuración** \> del sitio de **Administración** \> y, después, seleccione el sitio.</span><span class="sxs-lookup"><span data-stu-id="eefb5-153">In the Configuration Manager console, go to **Administration** \> **Site Configuration** \> **Sites**, and then select the site.</span></span>

2.  <span data-ttu-id="eefb5-154">En el grupo **configuración** , seleccione **Configurar componentes** \> de sitio de **distribución de software**.</span><span class="sxs-lookup"><span data-stu-id="eefb5-154">In the **Settings** group, select **Configure Site Components** \> **Software Distribution**.</span></span>

3.  <span data-ttu-id="eefb5-155">Seleccione la pestaña **cuenta de acceso a la red** . configure una o más cuentas y, a continuación, seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="eefb5-155">Select the **Network Access Account** tab. Set up one or more accounts, and then select **OK**.</span></span>

> [!NOTE]
> <span data-ttu-id="eefb5-156">Las cuentas no necesitan derechos especiales, excepto **tener acceso a este equipo desde la red** en el servidor del punto de distribución.</span><span class="sxs-lookup"><span data-stu-id="eefb5-156">The accounts don’t need any special rights, except for the **Access this computer from the network** right on the distribution point server.</span></span> <span data-ttu-id="eefb5-157">Una cuenta de usuario de dominio genérico será adecuada.</span><span class="sxs-lookup"><span data-stu-id="eefb5-157">A generic domain user account will be appropriate.</span></span> <span data-ttu-id="eefb5-158">Para obtener más información, vea [administrar cuentas para obtener acceso al contenido de System Center Configuration Manager](https://docs.microsoft.com/sccm/core/plan-design/hierarchy/manage-accounts-to-access-content#bkmk_NAA).</span><span class="sxs-lookup"><span data-stu-id="eefb5-158">For more information, see [Manage accounts to access content in System Center Configuration Manager](https://docs.microsoft.com/sccm/core/plan-design/hierarchy/manage-accounts-to-access-content#bkmk_NAA).</span></span>

### <a name="configure-a-boot-image"></a><span data-ttu-id="eefb5-159">Configurar una imagen de arranque</span><span class="sxs-lookup"><span data-stu-id="eefb5-159">Configure a boot image</span></span>

1.  <span data-ttu-id="eefb5-160">En la consola del administrador de configuración, vaya a **imágenes de inicio** **del sistema** \> operativo de la **biblioteca** \> de software.</span><span class="sxs-lookup"><span data-stu-id="eefb5-160">In the Configuration Manager console, go to **Software Library** \> **Operating System** \> **Boot Images**.</span></span>

2.  <span data-ttu-id="eefb5-161">Seleccione **imagen de arranque (x64)** y, a continuación, haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="eefb5-161">Select **Boot image (x64)**, and then select **Properties**.</span></span>

3.  <span data-ttu-id="eefb5-162">Seleccione la pestaña **origen de datos** y habilite **implementar esta imagen de inicio desde el punto de distribución habilitado para PXE**.</span><span class="sxs-lookup"><span data-stu-id="eefb5-162">Select the **Data Source** tab, and enable **Deploy this boot image from the PXE-enabled distribution point**.</span></span>

4.  <span data-ttu-id="eefb5-163">Seleccione la pestaña **componentes opcionales** para instalar los componentes necesarios:</span><span class="sxs-lookup"><span data-stu-id="eefb5-163">Select the **Optional Components** tab to install required components:</span></span>

    1.  <span data-ttu-id="eefb5-164">Seleccione el icono de estrella y busque **HTML (WinPE-HTA)** .</span><span class="sxs-lookup"><span data-stu-id="eefb5-164">Select the star icon, and search for **HTML (WinPE-HTA)**</span></span>

    2.  <span data-ttu-id="eefb5-165">Seleccione **Aceptar** para agregar compatibilidad de aplicaciones HTML en la imagen de inicio.</span><span class="sxs-lookup"><span data-stu-id="eefb5-165">Select **OK** to add HTML application support in to the boot image.</span></span>

5.  <span data-ttu-id="eefb5-166">*Opcional:* Para personalizar la experiencia de implementación, seleccione \*\*\*\* la pestaña personalización.</span><span class="sxs-lookup"><span data-stu-id="eefb5-166">*Optional:* To customize the deployment experience, select the **Customization** tab.</span></span>
    -   <span data-ttu-id="eefb5-167">Habilite la **compatibilidad con comandos (solo pruebas)** si desea tener acceso a un símbolo del sistema durante la implementación.</span><span class="sxs-lookup"><span data-stu-id="eefb5-167">Enable **command support (testing only)** if you want to have access to a command prompt during the deployment.</span></span> <span data-ttu-id="eefb5-168">Cuando esta opción está habilitada, puede iniciar un símbolo del sistema seleccionando **F8** en cualquier momento de la implementación.</span><span class="sxs-lookup"><span data-stu-id="eefb5-168">When this is enabled, you can start a command prompt by selecting **F8** at any time during the deployment.</span></span>
    -   <span data-ttu-id="eefb5-169">También puede especificar una imagen de fondo personalizada para que se muestre durante la implementación.</span><span class="sxs-lookup"><span data-stu-id="eefb5-169">You can also specify a custom background image to be displayed during the deployment.</span></span> <span data-ttu-id="eefb5-170">Para establecer una imagen, habilite **especificar el archivo de imagen de fondo personalizado (ruta de acceso UNC** y seleccione el fondo.</span><span class="sxs-lookup"><span data-stu-id="eefb5-170">To set an image, enable **Specify the custom background image file (UNC path** and select your background.</span></span>

6.  <span data-ttu-id="eefb5-171">Cuando se le pida, seleccione **sí** y distribuir la imagen de arranque actualizada a los puntos de distribución.</span><span class="sxs-lookup"><span data-stu-id="eefb5-171">When asked, select **Yes** and distribute the updated boot image to your distribution points.</span></span>

<span data-ttu-id="eefb5-172">Para obtener más información, consulte [Manage boot images with System Center Configuration Manager](https://docs.microsoft.com/sccm/osd/get-started/manage-boot-images).</span><span class="sxs-lookup"><span data-stu-id="eefb5-172">For more information, see [Manage boot images with System Center Configuration Manager](https://docs.microsoft.com/sccm/osd/get-started/manage-boot-images).</span></span>

> [!NOTE]
> <span data-ttu-id="eefb5-173">Puede crear un medio USB de arranque para iniciar implementaciones basadas en secuencias de tareas de Configuration Manager para entornos que no tienen compatibilidad con PXE.</span><span class="sxs-lookup"><span data-stu-id="eefb5-173">You can create a bootable USB media to initiate Configuration Manager task sequence–based deployments for environments that have no PXE support.</span></span> <span data-ttu-id="eefb5-174">El medio de arranque contiene solo la imagen de arranque, los comandos de preinicio opcionales y los archivos necesarios, y los binarios de Configuration Manager para admitir el inicio en Windows PE y la conexión con Configuration Manager durante el resto del proceso de implementación.</span><span class="sxs-lookup"><span data-stu-id="eefb5-174">The bootable media contains only the boot image, optional prestart commands and their required files, and Configuration Manager binaries to support booting into Windows PE and connecting to Configuration Manager for the rest of the deployment process.</span></span> <span data-ttu-id="eefb5-175">Para obtener más información, consulte [Cómo crear medios de arranque](https://docs.microsoft.com/sccm/osd/deploy-use/create-bootable-media#BKMK_CreateBootableMedia).</span><span class="sxs-lookup"><span data-stu-id="eefb5-175">For more information, see [How to Create Bootable Media](https://docs.microsoft.com/sccm/osd/deploy-use/create-bootable-media#BKMK_CreateBootableMedia).</span></span>

## <a name="create-configuration-manager-packages"></a><span data-ttu-id="eefb5-176">Crear paquetes de Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="eefb5-176">Create Configuration Manager packages</span></span>

<span data-ttu-id="eefb5-177">Configuration Manager requiere varios paquetes para implementar y configurar las unidades de salas de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="eefb5-177">Configuration Manager requires a number of packages to deploy and configure the Microsoft Teams Rooms units.</span></span>

<span data-ttu-id="eefb5-178">Debe crear y configurar los siguientes paquetes y, a continuación, distribuirlos a los sistemas de sitio de Configuration Manager a los que se les haya asignado el rol de servidor del punto de distribución.</span><span class="sxs-lookup"><span data-stu-id="eefb5-178">You need to create and configure the following packages, and then distribute them to the Configuration Manager site systems that have been assigned the distribution point server role.</span></span>

| <span data-ttu-id="eefb5-179">**Nombre del paquete**</span><span class="sxs-lookup"><span data-stu-id="eefb5-179">**Package name**</span></span>                     | <span data-ttu-id="eefb5-180">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="eefb5-180">**Type**</span></span>               | <span data-ttu-id="eefb5-181">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="eefb5-181">**Description**</span></span>                                                                           |
|--------------------------------------|------------------------|-------------------------------------------------------------------------------------------|
| <span data-ttu-id="eefb5-182">SRS V2: paquete de aplicaciones para SRS</span><span class="sxs-lookup"><span data-stu-id="eefb5-182">SRS v2 - SRS Application Package</span></span>     | <span data-ttu-id="eefb5-183">Paquete de software</span><span class="sxs-lookup"><span data-stu-id="eefb5-183">Software package</span></span>       | <span data-ttu-id="eefb5-184">Paquete para el kit de implementación de Microsoft Teams Rooms</span><span class="sxs-lookup"><span data-stu-id="eefb5-184">Package for the Microsoft Teams Rooms deployment kit</span></span>                                      |
| <span data-ttu-id="eefb5-185">SRS V2: paquete de Sysprep</span><span class="sxs-lookup"><span data-stu-id="eefb5-185">SRS v2 - Sysprep Package</span></span>             | <span data-ttu-id="eefb5-186">Paquete de software</span><span class="sxs-lookup"><span data-stu-id="eefb5-186">Software package</span></span>       | <span data-ttu-id="eefb5-187">Paquete para el. XML personalizado desatendido para configurar las unidades de salas de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="eefb5-187">Package for the custom Unattended.xml to configure Microsoft Teams Rooms units</span></span>            |
| <span data-ttu-id="eefb5-188">SRS V2-Set-SRSComputerName</span><span class="sxs-lookup"><span data-stu-id="eefb5-188">SRS v2 - Set-SRSComputerName Package</span></span> | <span data-ttu-id="eefb5-189">Paquete de software</span><span class="sxs-lookup"><span data-stu-id="eefb5-189">Software package</span></span>       | <span data-ttu-id="eefb5-190">Paquete para la aplicación HTML (HTA) para asignar un nombre de equipo durante la implementación</span><span class="sxs-lookup"><span data-stu-id="eefb5-190">Package for the HTML application (HTA) to assign a computer name during the deployment</span></span>    |
| <span data-ttu-id="eefb5-191">SRS V2: configurar la configuración de SRS</span><span class="sxs-lookup"><span data-stu-id="eefb5-191">SRS v2 - Configure SRS Setup</span></span>         | <span data-ttu-id="eefb5-192">Paquete de software</span><span class="sxs-lookup"><span data-stu-id="eefb5-192">Software package</span></span>       | <span data-ttu-id="eefb5-193">Paquete para configurar la implementación de la aplicación salas de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="eefb5-193">Package to configure deployment of the Microsoft Teams Rooms app</span></span>                          |
| <span data-ttu-id="eefb5-194">Paquete de actualizaciones para SRS V2-OS</span><span class="sxs-lookup"><span data-stu-id="eefb5-194">SRS v2 - OS Updates Package</span></span>          | <span data-ttu-id="eefb5-195">Paquete de software</span><span class="sxs-lookup"><span data-stu-id="eefb5-195">Software package</span></span>       | <span data-ttu-id="eefb5-196">Paquete para implementar actualizaciones obligatorias del sistema operativo</span><span class="sxs-lookup"><span data-stu-id="eefb5-196">Package to deploy mandatory operating system updates</span></span>                                      |
| <span data-ttu-id="eefb5-197">SRS V2: paquete de certificados raíz</span><span class="sxs-lookup"><span data-stu-id="eefb5-197">SRS v2 - Root Certificate Package</span></span>    | <span data-ttu-id="eefb5-198">Paquete de software</span><span class="sxs-lookup"><span data-stu-id="eefb5-198">Software package</span></span>       | <span data-ttu-id="eefb5-199">Paquete opcional para implementar el certificado raíz (no es necesario para las unidades Unidas al dominio)</span><span class="sxs-lookup"><span data-stu-id="eefb5-199">Optional - Package to deploy the root certificate (not required for domain-joined units)</span></span>  |
| <span data-ttu-id="eefb5-200">SRS V2-paquete de Microsoft Monitoring Agent</span><span class="sxs-lookup"><span data-stu-id="eefb5-200">SRS v2 - Microsoft Monitoring Agent Package</span></span> | <span data-ttu-id="eefb5-201">Paquete de software</span><span class="sxs-lookup"><span data-stu-id="eefb5-201">Software package</span></span>       | <span data-ttu-id="eefb5-202">Opcional: paquete para implementar y configurar el agente de Microsoft Operations Management Suite</span><span class="sxs-lookup"><span data-stu-id="eefb5-202">Optional - Package to deploy and configure the Microsoft Operations Management Suite agent</span></span>|
| <span data-ttu-id="eefb5-203">SRS V2: paquete de fondo WinPE</span><span class="sxs-lookup"><span data-stu-id="eefb5-203">SRS v2 - WinPE Background Package</span></span>    | <span data-ttu-id="eefb5-204">Paquete de software</span><span class="sxs-lookup"><span data-stu-id="eefb5-204">Software package</span></span>       | <span data-ttu-id="eefb5-205">Paquete para la imagen de fondo personalizada que se usa con imágenes de arranque</span><span class="sxs-lookup"><span data-stu-id="eefb5-205">Package for the custom background image to use with boot images</span></span>                           |
| <span data-ttu-id="eefb5-206">Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="eefb5-206">Windows 10 Enterprise</span></span>                | <span data-ttu-id="eefb5-207">Imagen de sistema operativo</span><span class="sxs-lookup"><span data-stu-id="eefb5-207">Operating system image</span></span> | <span data-ttu-id="eefb5-208">Paquete para el archivo de instalación del sistema operativo (install. wim)</span><span class="sxs-lookup"><span data-stu-id="eefb5-208">Package for the operating system installation file (install.wim)</span></span>                          |
| <span data-ttu-id="eefb5-209">Surface Pro</span><span class="sxs-lookup"><span data-stu-id="eefb5-209">Surface Pro</span></span>                          | <span data-ttu-id="eefb5-210">Paquete de controladores</span><span class="sxs-lookup"><span data-stu-id="eefb5-210">Driver package</span></span>         | <span data-ttu-id="eefb5-211">Paquete para los drivers de dispositivo y firmware para Microsoft Surface Pro</span><span class="sxs-lookup"><span data-stu-id="eefb5-211">Package for the device drivers and firmware for Microsoft Surface Pro</span></span>                     |
| <span data-ttu-id="eefb5-212">Surface Pro 4</span><span class="sxs-lookup"><span data-stu-id="eefb5-212">Surface Pro 4</span></span>                        | <span data-ttu-id="eefb5-213">Paquete de controladores</span><span class="sxs-lookup"><span data-stu-id="eefb5-213">Driver package</span></span>         | <span data-ttu-id="eefb5-214">Paquete para los drivers de dispositivo y firmware para Microsoft Surface Pro 4</span><span class="sxs-lookup"><span data-stu-id="eefb5-214">Package for the device drivers and firmware for Microsoft Surface Pro 4</span></span>                   |

<span data-ttu-id="eefb5-215">Para obtener más información, consulte [paquetes y programas en System Center Configuration Manager](https://docs.microsoft.com/sccm/apps/deploy-use/packages-and-programs).</span><span class="sxs-lookup"><span data-stu-id="eefb5-215">For more information, see [Packages and programs in System Center Configuration Manager](https://docs.microsoft.com/sccm/apps/deploy-use/packages-and-programs).</span></span>

### <a name="create-folders-for-the-package-source-files"></a><span data-ttu-id="eefb5-216">Crear carpetas para los archivos de origen del paquete</span><span class="sxs-lookup"><span data-stu-id="eefb5-216">Create folders for the package source files</span></span>

<span data-ttu-id="eefb5-217">El administrador de configuración requiere que los archivos de origen del paquete se organicen en una estructura de carpetas específica cuando se crean por primera vez y cuando se actualizan.</span><span class="sxs-lookup"><span data-stu-id="eefb5-217">Configuration Manager requires package source files to be organized in a specific folder structure when they’re first created and when they’re updated.</span></span>

<span data-ttu-id="eefb5-218">Cree la siguiente estructura de carpetas en el sitio de administración central de System Center Configuration Manager o en el sitio primario, o en un recurso compartido de servidor que esté usando para hospedar los archivos de origen del paquete:</span><span class="sxs-lookup"><span data-stu-id="eefb5-218">Create the following folder structure on the System Center Configuration Manager central administration site or primary site, or on a server share you’re using to host package source files:</span></span>

-   <span data-ttu-id="eefb5-219">SRS V2-paquete de Microsoft Monitoring Agent</span><span class="sxs-lookup"><span data-stu-id="eefb5-219">SRS v2 - Microsoft Monitoring Agent Package</span></span>
-   <span data-ttu-id="eefb5-220">Paquete de actualizaciones para SRS V2-OS</span><span class="sxs-lookup"><span data-stu-id="eefb5-220">SRS v2 - OS Updates Package</span></span>
-   <span data-ttu-id="eefb5-221">SRS V2: paquete de certificados raíz</span><span class="sxs-lookup"><span data-stu-id="eefb5-221">SRS v2 - Root Certificate Package</span></span>
-   <span data-ttu-id="eefb5-222">SRS V2-Set-SRSComputerName</span><span class="sxs-lookup"><span data-stu-id="eefb5-222">SRS v2 - Set-SRSComputerName Package</span></span>
-   <span data-ttu-id="eefb5-223">SRS V2: paquete de aplicaciones para SRS</span><span class="sxs-lookup"><span data-stu-id="eefb5-223">SRS v2 - SRS Application Package</span></span>
-   <span data-ttu-id="eefb5-224">SRS V2: configurar la configuración de SRS</span><span class="sxs-lookup"><span data-stu-id="eefb5-224">SRS v2 - Configure SRS Setup</span></span>
-   <span data-ttu-id="eefb5-225">SRS V2: paquete de Sysprep</span><span class="sxs-lookup"><span data-stu-id="eefb5-225">SRS v2 - Sysprep Package</span></span>
-   <span data-ttu-id="eefb5-226">Conductores</span><span class="sxs-lookup"><span data-stu-id="eefb5-226">Drivers</span></span>
    -   <span data-ttu-id="eefb5-227">Surface Pro</span><span class="sxs-lookup"><span data-stu-id="eefb5-227">Surface Pro</span></span>
    -   <span data-ttu-id="eefb5-228">Surface Pro 4</span><span class="sxs-lookup"><span data-stu-id="eefb5-228">Surface Pro 4</span></span>
-   <span data-ttu-id="eefb5-229">Sistemas operativos</span><span class="sxs-lookup"><span data-stu-id="eefb5-229">Operating Systems</span></span>
    -   <span data-ttu-id="eefb5-230">Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="eefb5-230">Windows 10 Enterprise</span></span>

> [!TIP]
> <span data-ttu-id="eefb5-231">También puede [Descargar](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true) y usar el archivo zip que incluye la estructura de carpetas de los paquetes, los scripts que necesita usar y la plantilla de secuencia de tareas que necesita importar.</span><span class="sxs-lookup"><span data-stu-id="eefb5-231">You may also [download](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true) and use the zip file that includes the folder structure for the packages, the scripts that you need to use, and the task sequence template, that you need to import.</span></span>

### <a name="create-the-monitoring-agent-package"></a><span data-ttu-id="eefb5-232">Crear el paquete del agente de supervisión</span><span class="sxs-lookup"><span data-stu-id="eefb5-232">Create the Monitoring agent package</span></span>

1. <span data-ttu-id="eefb5-233">Descarga el agente de supervisión <https://go.microsoft.com/fwlink/?LinkId=828603>de.</span><span class="sxs-lookup"><span data-stu-id="eefb5-233">Download the Monitoring agent from <https://go.microsoft.com/fwlink/?LinkId=828603>.</span></span>

2. <span data-ttu-id="eefb5-234">Extraiga el paquete a la carpeta del **paquete SRS V2-Microsoft Monitoring Agent** abriendo una ventana del símbolo del sistema y escribiendo **MMASetup-AMD64. exe/c:** en el símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="eefb5-234">Extract the package into the **SRS v2 - Microsoft Monitoring Agent Package** folder by opening a Command Prompt window and entering **MMASetup-AMD64.exe /C:**     at the command prompt.</span></span>

3. <span data-ttu-id="eefb5-235">En la consola del administrador de configuración, vaya a **paquetes**de **Administración** \> de aplicaciones de la **biblioteca** \> de software y, después, seleccione **crear paquete**.</span><span class="sxs-lookup"><span data-stu-id="eefb5-235">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**, and then select **Create Package**.</span></span>

4. <span data-ttu-id="eefb5-236">Escriba la siguiente información para crear el paquete:</span><span class="sxs-lookup"><span data-stu-id="eefb5-236">Enter the following information to create the package:</span></span>

   - <span data-ttu-id="eefb5-237">Nombre<strong>: SRS V2: paquete del agente de supervisión de Microsoft</strong></span><span class="sxs-lookup"><span data-stu-id="eefb5-237">Name<strong>: SRS v2 - Microsoft Monitoring Agent Package</strong></span></span>

   - <span data-ttu-id="eefb5-238">Fabricante<strong>: Microsoft Corporation</strong></span><span class="sxs-lookup"><span data-stu-id="eefb5-238">Manufacturer<strong>: Microsoft Corporation</strong></span></span>

   - <span data-ttu-id="eefb5-239">Versión<strong>: 8.1.11081.0</strong> (escriba la versión del archivo de instalación descargado)</span><span class="sxs-lookup"><span data-stu-id="eefb5-239">Version<strong>: 8.1.11081.0</strong> (enter the version of the downloaded installation file)</span></span>

   - <span data-ttu-id="eefb5-240">Seleccione la casilla **este paquete contiene archivos de origen** , escriba la ruta de acceso a la carpeta del **paquete SRS V2-Microsoft Monitoring Agent** y, a continuación, seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="eefb5-240">Select the **This package contains source files** check box, enter the path to the **SRS v2 - Microsoft Monitoring Agent Package** folder, and then select **Next**.</span></span>

5. <span data-ttu-id="eefb5-241">Seleccione no **crear un programa**y, a continuación, seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="eefb5-241">Select **Do not create a program**, and then select **Next**.</span></span>

6. <span data-ttu-id="eefb5-242">Revise la página **confirmar la configuración** y, a continuación, seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="eefb5-242">Review the **Confirm the settings** page, and then select **Next**.</span></span>

7. <span data-ttu-id="eefb5-243">Seleccione **cerrar**.</span><span class="sxs-lookup"><span data-stu-id="eefb5-243">Select **Close**.</span></span>

### <a name="create-the-operating-system-updates-package"></a><span data-ttu-id="eefb5-244">Crear el paquete de actualizaciones del sistema operativo</span><span class="sxs-lookup"><span data-stu-id="eefb5-244">Create the operating system updates package</span></span>

1. <span data-ttu-id="eefb5-245">En la carpeta del **paquete de actualizaciones de SRS V2-os** , cree un nuevo script de PowerShell denominado **install-SRSv2-os-updates. PS1**.</span><span class="sxs-lookup"><span data-stu-id="eefb5-245">In the **SRS v2 - OS Updates Package** folder, create a new PowerShell script named **Install-SRSv2-OS-Updates.ps1**.</span></span>

2. <span data-ttu-id="eefb5-246">Copie el script siguiente en el script **install-SRSv2-os-updates. PS1** .</span><span class="sxs-lookup"><span data-stu-id="eefb5-246">Copy the script below into the **Install-SRSv2-OS-Updates.ps1** script.</span></span> <span data-ttu-id="eefb5-247">Como alternativa, puedes descargar el script Install-SRSv2-OS-Updates. PS1 desde [aquí](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true).</span><span class="sxs-lookup"><span data-stu-id="eefb5-247">Alternatively, you can download the Install-SRSv2-OS-Updates.ps1 script from [here](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true).</span></span>
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
3. <span data-ttu-id="eefb5-248">Descargue los paquetes de Windows Update obligatorios en la misma carpeta.</span><span class="sxs-lookup"><span data-stu-id="eefb5-248">Download the mandatory Windows Update packages into the same folder.</span></span>
   > [!NOTE]
   > <span data-ttu-id="eefb5-249">En el momento en que se publicó este artículo, solo se necesitaba [KB4056892](http://download.windowsupdate.com/c/msdownload/update/software/secu/2018/01/windows10.0-kb4056892-x64_a41a378cf9ae609152b505c40e691ca1228e28ea.msu) .</span><span class="sxs-lookup"><span data-stu-id="eefb5-249">At the time this article was published, only [KB4056892](http://download.windowsupdate.com/c/msdownload/update/software/secu/2018/01/windows10.0-kb4056892-x64_a41a378cf9ae609152b505c40e691ca1228e28ea.msu) was required.</span></span> <span data-ttu-id="eefb5-250">Marque [configurar una consola de salas de Microsoft Teams](console.md)para ver si se necesitan otras actualizaciones.</span><span class="sxs-lookup"><span data-stu-id="eefb5-250">Check [Configure a Microsoft Teams Rooms console](console.md), to see whether any other updates are required.</span></span>

4. <span data-ttu-id="eefb5-251">En la consola del administrador de configuración, vaya a **paquetes**de **Administración** \> de aplicaciones de la **biblioteca** \> de software y, después, seleccione **crear paquete**.</span><span class="sxs-lookup"><span data-stu-id="eefb5-251">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**, and then select **Create Package**.</span></span>

5. <span data-ttu-id="eefb5-252">Escriba la siguiente información para crear el paquete:</span><span class="sxs-lookup"><span data-stu-id="eefb5-252">Enter the following information to create the package:</span></span>
   -   <span data-ttu-id="eefb5-253">Nombre: **SRS V2: paquete de actualizaciones del sistema operativo**</span><span class="sxs-lookup"><span data-stu-id="eefb5-253">Name: **SRS v2 – OS Updates Package**</span></span>
   -   <span data-ttu-id="eefb5-254">Fabricante: **Microsoft Corporation**</span><span class="sxs-lookup"><span data-stu-id="eefb5-254">Manufacturer: **Microsoft Corporation**</span></span>
   -   <span data-ttu-id="eefb5-255">Versión: **1.0.0**</span><span class="sxs-lookup"><span data-stu-id="eefb5-255">Version: **1.0.0**</span></span>
   -   <span data-ttu-id="eefb5-256">Seleccione la casilla **este paquete contiene archivos de origen** , escriba la ruta de acceso a la carpeta del **paquete de actualizaciones de SRS V2-os** y, a continuación, seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="eefb5-256">Select the **This package contains source files** check box, enter the path to the **SRS v2 - OS Updates Package** folder, and then select **Next**.</span></span>

6. <span data-ttu-id="eefb5-257">Seleccione no **crear un programa**y, a continuación, seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="eefb5-257">Select **Do not create a program**, and then select **Next**.</span></span>

7. <span data-ttu-id="eefb5-258">Revise la página **confirmar la configuración** y, a continuación, seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="eefb5-258">Review the **Confirm the settings** page, and then select **Next**.</span></span>

8. <span data-ttu-id="eefb5-259">Seleccione **cerrar**.</span><span class="sxs-lookup"><span data-stu-id="eefb5-259">Select **Close**.</span></span>

### <a name="create-the-root-certificate-package-optional"></a><span data-ttu-id="eefb5-260">Crear el paquete de certificados raíz (opcional)</span><span class="sxs-lookup"><span data-stu-id="eefb5-260">Create the root certificate package (optional)</span></span>

<span data-ttu-id="eefb5-261">Cree este paquete para distribuir el certificado raíz de los dispositivos que no se unirán a un dominio de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="eefb5-261">You create this package to distribute the root certificate for devices that won’t be joined to an Active Directory domain.</span></span> <span data-ttu-id="eefb5-262">Cree este paquete solo si se aplican las dos condiciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="eefb5-262">Create this package only if both the following conditions apply:</span></span>
-   <span data-ttu-id="eefb5-263">Su implementación incluye Lync local o Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="eefb5-263">Your deployment includes on-premises Lync or Skype for Business Server.</span></span>
-   <span data-ttu-id="eefb5-264">Las unidades de salas de Microsoft Teams están configuradas para trabajar en un grupo de trabajo en lugar de un miembro del dominio.</span><span class="sxs-lookup"><span data-stu-id="eefb5-264">Microsoft Teams Rooms units are configured to work in a workgroup instead of a domain member.</span></span>

1.  <span data-ttu-id="eefb5-265">Copie el certificado raíz en la carpeta del **paquete de certificados raíz de SRS V2** .</span><span class="sxs-lookup"><span data-stu-id="eefb5-265">Copy the root certificate into the **SRS v2 – Root Certificate Package** folder.</span></span>

2.  <span data-ttu-id="eefb5-266">En la consola del administrador de configuración, vaya a **paquetes**de **Administración** \> de aplicaciones de la **biblioteca** \> de software y, después, seleccione **crear paquete**.</span><span class="sxs-lookup"><span data-stu-id="eefb5-266">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**, and then select **Create Package**.</span></span>

3.  <span data-ttu-id="eefb5-267">Escriba la siguiente información para crear el paquete:</span><span class="sxs-lookup"><span data-stu-id="eefb5-267">Enter the following information to create the package:</span></span>
    -   <span data-ttu-id="eefb5-268">Nombre: **SRS V2: paquete de certificados raíz**</span><span class="sxs-lookup"><span data-stu-id="eefb5-268">Name: **SRS v2 – Root Certificate Package**</span></span>
    -   <span data-ttu-id="eefb5-269">Fabricante: *nombre de la organización*</span><span class="sxs-lookup"><span data-stu-id="eefb5-269">Manufacturer: *Your organization’s name*</span></span>
    -   <span data-ttu-id="eefb5-270">Versión: **1.0.0**</span><span class="sxs-lookup"><span data-stu-id="eefb5-270">Version: **1.0.0**</span></span>
    -   <span data-ttu-id="eefb5-271">Seleccione la casilla **este paquete contiene archivos de origen** , escriba la ruta de acceso a la carpeta del **paquete de certificados raíz** y, a continuación, seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="eefb5-271">Select the **This package contains source files** check box, enter the path to the **SRS v2 – Root Certificate Package** folder, and then select **Next**.</span></span>

4.  <span data-ttu-id="eefb5-272">Seleccione no **crear un programa**y, a continuación, seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="eefb5-272">Select **Do not create a program**, and then select **Next**.</span></span>

5.  <span data-ttu-id="eefb5-273">Revise la página **confirmar la configuración** y, a continuación, seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="eefb5-273">Review the **Confirm the settings** page, and then select **Next**.</span></span>

6.  <span data-ttu-id="eefb5-274">Seleccione **cerrar**.</span><span class="sxs-lookup"><span data-stu-id="eefb5-274">Select **Close**.</span></span>

### <a name="create-the-microsoft-teams-rooms-deployment-kit-package"></a><span data-ttu-id="eefb5-275">Crear el paquete del kit de implementación de Microsoft Teams Rooms</span><span class="sxs-lookup"><span data-stu-id="eefb5-275">Create the Microsoft Teams Rooms deployment kit package</span></span>

1.  <span data-ttu-id="eefb5-276">Descargue la versión más reciente del **Kit de implementación de Microsoft Teams Rooms** desde e instálela en una estación de <https://go.microsoft.com/fwlink/?linkid=851168>trabajo.</span><span class="sxs-lookup"><span data-stu-id="eefb5-276">Download the latest version of the **Microsoft Teams Rooms deployment kit** from <https://go.microsoft.com/fwlink/?linkid=851168>, and install it to a workstation.</span></span>

2.  <span data-ttu-id="eefb5-277">Copie el contenido de **C:\\archivos de programa (x86\\) kit de implementación de sistemas de salas de Skype** en la carpeta del **paquete de la aplicación SRS V2** .</span><span class="sxs-lookup"><span data-stu-id="eefb5-277">Copy the content from **C:\\Program Files (x86)\\Skype Room System Deployment Kit** to the **SRS v2 - SRS Application Package** folder.</span></span>

3.  <span data-ttu-id="eefb5-278">En la consola del administrador de configuración, vaya a **paquetes**de **Administración** \> de aplicaciones de la **biblioteca** \> de software y, después, seleccione **crear paquete**.</span><span class="sxs-lookup"><span data-stu-id="eefb5-278">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**, and then select **Create Package**.</span></span>

4.  <span data-ttu-id="eefb5-279">Escriba la siguiente información para crear el paquete:</span><span class="sxs-lookup"><span data-stu-id="eefb5-279">Enter the following information to create the package:</span></span>
    -   <span data-ttu-id="eefb5-280">Nombre: **SRS V2: paquete de aplicación para SRS**</span><span class="sxs-lookup"><span data-stu-id="eefb5-280">Name: **SRS v2 – SRS Application Package**</span></span>
    -   <span data-ttu-id="eefb5-281">Fabricante: **Microsoft Corporation**</span><span class="sxs-lookup"><span data-stu-id="eefb5-281">Manufacturer: **Microsoft Corporation**</span></span>
    -   <span data-ttu-id="eefb5-282">Versión: **3.1.104.0** (escriba la versión del archivo de instalación descargado)</span><span class="sxs-lookup"><span data-stu-id="eefb5-282">Version: **3.1.104.0** (enter the version of the downloaded installation file)</span></span>
    -   <span data-ttu-id="eefb5-283">Seleccione la casilla **este paquete contiene archivos de origen** , escriba la ruta de acceso a la carpeta **SRS V2 – paquete de la aplicación SRS** y, a continuación, seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="eefb5-283">Select the **This package contains source files** check box, enter the path to the **SRS v2 – SRS Application Package** folder, and then select **Next**.</span></span>
5.  <span data-ttu-id="eefb5-284">Seleccione no **crear un programa**y, a continuación, seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="eefb5-284">Select **Do not create a program**, and then select **Next**.</span></span>

6.  <span data-ttu-id="eefb5-285">Revise la página **confirmar la configuración** y, a continuación, seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="eefb5-285">Review the **Confirm the settings** page, and then select **Next**.</span></span>

7.  <span data-ttu-id="eefb5-286">Seleccione **cerrar**.</span><span class="sxs-lookup"><span data-stu-id="eefb5-286">Select **Close**.</span></span>

### <a name="create-the-computer-name-assignment-package"></a><span data-ttu-id="eefb5-287">Crear el paquete de asignación de nombre de equipo</span><span class="sxs-lookup"><span data-stu-id="eefb5-287">Create the computer name assignment package</span></span>

1.  <span data-ttu-id="eefb5-288">En la carpeta del **paquete SRS V2-Set-SRSComputerName** , cree una nueva aplicación HTML denominada **set-SRSComputerName. HTA** .</span><span class="sxs-lookup"><span data-stu-id="eefb5-288">In the **SRS v2 - Set-SRSComputerName Package** folder, create a new HTML application named **Set-SRSComputerName.hta** .</span></span>

2.  <span data-ttu-id="eefb5-289">Copie el script siguiente en el archivo **set-SRSComputerName. HTA** .</span><span class="sxs-lookup"><span data-stu-id="eefb5-289">Copy the following script into the **Set-SRSComputerName.hta** file.</span></span> <span data-ttu-id="eefb5-290">También puedes descargar el archivo Set-SRSComputerName. HTA desde [aquí](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true).</span><span class="sxs-lookup"><span data-stu-id="eefb5-290">Alternatively, you can download the Set-SRSComputerName.hta file from [here](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true).</span></span>
    ```
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
3.  <span data-ttu-id="eefb5-291">En la consola del administrador de configuración, vaya a **paquetes**de **Administración** \> de aplicaciones de la **biblioteca** \> de software y, después, seleccione **crear paquete**.</span><span class="sxs-lookup"><span data-stu-id="eefb5-291">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**, and then select **Create Package**.</span></span>

4.  <span data-ttu-id="eefb5-292">Escriba la siguiente información para crear el paquete:</span><span class="sxs-lookup"><span data-stu-id="eefb5-292">Enter the following information to create the package:</span></span>

    -   <span data-ttu-id="eefb5-293">Nombre: **SRS V2-Set-SRSComputerName paquete**</span><span class="sxs-lookup"><span data-stu-id="eefb5-293">Name: **SRS v2 - Set-SRSComputerName Package**</span></span>

    -   <span data-ttu-id="eefb5-294">Fabricante: **Microsoft Corporation**</span><span class="sxs-lookup"><span data-stu-id="eefb5-294">Manufacturer: **Microsoft Corporation**</span></span>

    -   <span data-ttu-id="eefb5-295">Versión: **1.0.0**</span><span class="sxs-lookup"><span data-stu-id="eefb5-295">Version: **1.0.0**</span></span>

    -   <span data-ttu-id="eefb5-296">Active la casilla de verificación **este paquete contiene archivos de origen** , escriba la ruta de acceso a la carpeta de **paquete SRSComputerName SRS V2** y, a continuación, seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="eefb5-296">Select the **This package contains source files** check box, enter the path to the **SRS v2 - Set-SRSComputerName Package** folder, and then select **Next**.</span></span>

5.  <span data-ttu-id="eefb5-297">Seleccione no **crear un programa**y, a continuación, seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="eefb5-297">Select **Do not create a program**, and then select **Next**.</span></span>

6.  <span data-ttu-id="eefb5-298">Revise la página **confirmar la configuración** y, a continuación, seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="eefb5-298">Review the **Confirm the settings** page, and then select **Next**.</span></span>

7.  <span data-ttu-id="eefb5-299">Seleccione **cerrar**.</span><span class="sxs-lookup"><span data-stu-id="eefb5-299">Select **Close**.</span></span>

### <a name="create-the-sysprep-package"></a><span data-ttu-id="eefb5-300">Crear el paquete de Sysprep</span><span class="sxs-lookup"><span data-stu-id="eefb5-300">Create the Sysprep package</span></span>

1. <span data-ttu-id="eefb5-301">En la carpeta del **paquete SRS V2-Sysprep** , cree un nuevo archivo XML denominado Unattend **. XML** .</span><span class="sxs-lookup"><span data-stu-id="eefb5-301">In the **SRS v2 – Sysprep Package** folder, create a new XML file named **Unattend.xml** .</span></span>

2. <span data-ttu-id="eefb5-302">Copie el texto siguiente en el archivo Unattend **. XML** .</span><span class="sxs-lookup"><span data-stu-id="eefb5-302">Copy the following text into the **Unattend.xml** file.</span></span> <span data-ttu-id="eefb5-303">También puede descargar el archivo Unattend. XML desde [aquí](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true).</span><span class="sxs-lookup"><span data-stu-id="eefb5-303">Alternatively, you can download the Unattend.xml file from [here](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true).</span></span>
   ```
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
3. <span data-ttu-id="eefb5-304">En la consola del administrador de configuración, vaya a **paquetes**de **Administración** \> de aplicaciones de la **biblioteca** \> de software y, después, seleccione **crear paquete**.</span><span class="sxs-lookup"><span data-stu-id="eefb5-304">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**, and then select **Create Package**.</span></span>

4. <span data-ttu-id="eefb5-305">Escriba la siguiente información para crear el paquete:</span><span class="sxs-lookup"><span data-stu-id="eefb5-305">Enter the following information to create the package:</span></span>
   -   <span data-ttu-id="eefb5-306">Nombre: **SRS V2-paquete de Sysprep**</span><span class="sxs-lookup"><span data-stu-id="eefb5-306">Name: **SRS v2 - Sysprep Package**</span></span>
   -   <span data-ttu-id="eefb5-307">Fabricante: **Microsoft Corporation**</span><span class="sxs-lookup"><span data-stu-id="eefb5-307">Manufacturer: **Microsoft Corporation**</span></span>
   -   <span data-ttu-id="eefb5-308">Versión: **1.0.0**</span><span class="sxs-lookup"><span data-stu-id="eefb5-308">Version: **1.0.0**</span></span>
   -   <span data-ttu-id="eefb5-309">Seleccione la casilla **este paquete contiene archivos de origen** , escriba la ruta de acceso a la carpeta del **paquete SRS V2-Sysprep** y, a continuación, seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="eefb5-309">Select the **This package contains source files** check box, enter the path to the **SRS v2 – Sysprep Package** folder, and then select **Next**.</span></span>
5. <span data-ttu-id="eefb5-310">Seleccione no **crear un programa**y, a continuación, seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="eefb5-310">Select **Do not create a program**, and then select **Next**.</span></span>

6. <span data-ttu-id="eefb5-311">Revise la página **confirmar la configuración** y, a continuación, seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="eefb5-311">Review the **Confirm the settings** page, and then select **Next**.</span></span>

7. <span data-ttu-id="eefb5-312">Seleccione **cerrar**.</span><span class="sxs-lookup"><span data-stu-id="eefb5-312">Select **Close**.</span></span>

### <a name="create-the-windows-10-enterprise-package"></a><span data-ttu-id="eefb5-313">Crear el paquete de Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="eefb5-313">Create the Windows 10 Enterprise package</span></span>

1.  <span data-ttu-id="eefb5-314">Obtenga un medio de Windows 10 Enterprise x64 y copie el archivo **install. Wim** en la carpeta **sistemas\\operativos de Windows 10 Enterprise** .</span><span class="sxs-lookup"><span data-stu-id="eefb5-314">Obtain a Windows 10 Enterprise x64 media, and copy the **install.wim** file to the **Operating Systems\\Windows 10 Enterprise** folder.</span></span>

2.  <span data-ttu-id="eefb5-315">En la consola del administrador de configuración, vaya a **imágenes del sistema**operativo de **sistemas** \> operativos de la **biblioteca** \> de software y, a continuación, seleccione **Agregar imagen de sistema operativo**.</span><span class="sxs-lookup"><span data-stu-id="eefb5-315">In the Configuration Manager console, go to **Software Library** \> **Operating Systems** \> **Operating System Images**, and then select **Add Operating System Image**.</span></span>

3.  <span data-ttu-id="eefb5-316">Especifique la ruta de acceso al archivo **install. Wim** que acaba de copiar y, a continuación, seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="eefb5-316">Specify the path to the **install.wim** file you just copied, and then select **Next**.</span></span>

4.  <span data-ttu-id="eefb5-317">Actualice el campo de **versión** para que coincida con el número de compilación de la imagen de Windows 10 Enterprise y, a continuación, seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="eefb5-317">Update the **Version** field to match the build number of the Windows 10 Enterprise image, and then select **Next**.</span></span>

5.  <span data-ttu-id="eefb5-318">Revise la página **detalles** y, a continuación, seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="eefb5-318">Review the **Details** page, and then select **Next**.</span></span>

6.  <span data-ttu-id="eefb5-319">Seleccione **cerrar**.</span><span class="sxs-lookup"><span data-stu-id="eefb5-319">Select **Close**.</span></span>

<span data-ttu-id="eefb5-320">Para obtener más información, vea [administrar imágenes del sistema operativo con System Center Configuration Manager](https://docs.microsoft.com/sccm/osd/get-started/manage-operating-system-images).</span><span class="sxs-lookup"><span data-stu-id="eefb5-320">For more information, see [Manage operating system images with System Center Configuration Manager](https://docs.microsoft.com/sccm/osd/get-started/manage-operating-system-images).</span></span>

### <a name="create-surface-pro-device-driver-packages"></a><span data-ttu-id="eefb5-321">Crear paquetes de controladores de dispositivo Surface Pro</span><span class="sxs-lookup"><span data-stu-id="eefb5-321">Create Surface Pro device driver packages</span></span>

<span data-ttu-id="eefb5-322">Las salas de Microsoft Teams son compatibles con Surface Pro y Surface Pro 4.</span><span class="sxs-lookup"><span data-stu-id="eefb5-322">Microsoft Teams Rooms is supported for both Surface Pro and Surface Pro 4.</span></span> <span data-ttu-id="eefb5-323">Necesita crear un paquete de controladores para cada modelo de Surface Pro que tenga en su entorno.</span><span class="sxs-lookup"><span data-stu-id="eefb5-323">You need to create a driver package for each Surface Pro model you have in your environment.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="eefb5-324">Los drivers deben ser compatibles con la compilación de Windows 10 Enterprise y la versión del kit de implementación de Microsoft Teams Rooms.</span><span class="sxs-lookup"><span data-stu-id="eefb5-324">The drivers must be compatible with the Windows 10 Enterprise build and the Microsoft Teams Rooms deployment kit version.</span></span> <span data-ttu-id="eefb5-325">Para obtener más información, vea [descargar el firmware y los drivers más recientes para dispositivos de Surface](https://docs.microsoft.com/surface/deploy-the-latest-firmware-and-drivers-for-surface-devices) y [configurar una consola](console.md).</span><span class="sxs-lookup"><span data-stu-id="eefb5-325">For more information, see [Download the latest firmware and drivers for Surface devices](https://docs.microsoft.com/surface/deploy-the-latest-firmware-and-drivers-for-surface-devices) and [Configure a console](console.md).</span></span>

1.  <span data-ttu-id="eefb5-326">Descargar los últimos drivers y firmware.</span><span class="sxs-lookup"><span data-stu-id="eefb5-326">Download the latest drivers and firmware.</span></span>
    -   <span data-ttu-id="eefb5-327">Para Surface Pro:<https://www.microsoft.com/download/details.aspx?id=55484></span><span class="sxs-lookup"><span data-stu-id="eefb5-327">For Surface Pro: <https://www.microsoft.com/download/details.aspx?id=55484></span></span>
    -   <span data-ttu-id="eefb5-328">Para Surface Pro 4:<https://www.microsoft.com/download/details.aspx?id=49498></span><span class="sxs-lookup"><span data-stu-id="eefb5-328">For Surface Pro 4: <https://www.microsoft.com/download/details.aspx?id=49498></span></span>

2.  <span data-ttu-id="eefb5-329">Extraiga el controlador y el firmware descargados.</span><span class="sxs-lookup"><span data-stu-id="eefb5-329">Extract the downloaded driver and firmware.</span></span> <span data-ttu-id="eefb5-330">Abra una ventana del símbolo del sistema y, en el símbolo del sistema, escriba uno de los siguientes comandos:</span><span class="sxs-lookup"><span data-stu-id="eefb5-330">Open a Command Prompt window and at the command prompt, enter one of the following commands:</span></span>
    -   `msiexec /a C:\SurfacePro_Win10.msi /passive TARGETDIR="C:\_Sources\\Drivers\Surface Pro"`
    -   `msiexec /a C:\SurfacePro4_Win10.msi /passive TARGETDIR="C:\_Sources\\Drivers\Surface Pro 4"`

3.  <span data-ttu-id="eefb5-331">En la consola del administrador de configuración, vaya a \> **drivers**de **sistemas operativos** de la **biblioteca** \> de software y, después, seleccione **importar controlador**.</span><span class="sxs-lookup"><span data-stu-id="eefb5-331">In the Configuration Manager console, go to **Software Library** \> **Operating Systems** \> **Drivers**, and then select **Import Driver**.</span></span>

4.  <span data-ttu-id="eefb5-332">Seleccione **importar todos los drivers en la siguiente ruta de acceso de red (UNC)**, seleccione la carpeta de origen (\\por\\ejemplo\\, C: _Sources drivers Surface Pro) y, a continuación, seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="eefb5-332">Select **Import all drivers in the following network path (UNC)**, select the source folder (for example, C:\\_Sources\\Drivers\\Surface Pro), and then select **Next**.</span></span>

5.  <span data-ttu-id="eefb5-333">En la página **especifique los detalles de los drivers importados** , seleccione todos los drivers que aparecen en la lista y, a continuación, seleccione **Habilitar estos drivers y permitir que los equipos los instalen**.</span><span class="sxs-lookup"><span data-stu-id="eefb5-333">On the **Specify the details for the imported drivers** page, select all the listed drivers, and then select **Enable these drivers and allow computers to install them**.</span></span>

6.  <span data-ttu-id="eefb5-334">Seleccione **categorías**, cree una nueva categoría que coincida con el modelo de superficie, seleccione **Aceptar**y, a continuación, seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="eefb5-334">Select **Categories**, create a new category that matches the Surface model, select **OK**, and then select **Next**.</span></span>

7.  <span data-ttu-id="eefb5-335">Seleccione **nuevo paquete**.</span><span class="sxs-lookup"><span data-stu-id="eefb5-335">Select **New Package**.</span></span>

8.  <span data-ttu-id="eefb5-336">Especifique el nombre del paquete que coincida con el modelo de Surface Pro, escriba una ruta de carpeta para almacenar los archivos de paquete de controladores en, seleccione **Aceptar**y, a continuación, seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="eefb5-336">Specify the package name that matches the Surface Pro model, enter a folder path to store the driver package files in, select **OK**, and then select **Next**.</span></span>

9.  <span data-ttu-id="eefb5-337">En la página **imágenes de arranque** , asegúrese de que no hay ninguna imagen de inicio seleccionada y, a continuación, seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="eefb5-337">On the **boot images** page, ensure that no boot images are selected, and then select **Next**.</span></span>

10. <span data-ttu-id="eefb5-338">Seleccione **cerrar**.</span><span class="sxs-lookup"><span data-stu-id="eefb5-338">Select **Close**.</span></span>

11. <span data-ttu-id="eefb5-339">Vaya a los **drivers**de **los sistemas** \> operativos de la **biblioteca** \> de software, seleccione \*\* \> crear carpeta\*\*y escriba un nombre de carpeta que coincida con el modelo de Surface Pro para el que ha importado los drivers.</span><span class="sxs-lookup"><span data-stu-id="eefb5-339">Go to **Software Library** \> **Operating Systems** \> **Drivers**, select **Folder \> Create Folder**, and enter a folder name that matches the Surface Pro model that you just imported the drivers for.</span></span>

12. <span data-ttu-id="eefb5-340">Mueva todos los drivers importados a la carpeta recién creada para facilitar la navegación y la operación.</span><span class="sxs-lookup"><span data-stu-id="eefb5-340">Move all the imported drivers to the newly created folder for easier navigation and operation.</span></span>

> [!NOTE]
> <span data-ttu-id="eefb5-341">Repita los mismos pasos para otros modelos de Surface Pro que pueda tener.</span><span class="sxs-lookup"><span data-stu-id="eefb5-341">Repeat the same steps for other Surface Pro models you might have.</span></span> <span data-ttu-id="eefb5-342">Para obtener más información, vea [administrar drivers en System Center Configuration Manager](https://docs.microsoft.com/sccm/osd/get-started/manage-drivers).</span><span class="sxs-lookup"><span data-stu-id="eefb5-342">For more information, see [Manage drivers in System Center Configuration Manager](https://docs.microsoft.com/sccm/osd/get-started/manage-drivers).</span></span>

### <a name="create-microsoft-teams-rooms-configuration-package"></a><span data-ttu-id="eefb5-343">Crear un paquete de configuración de Microsoft Teams Rooms</span><span class="sxs-lookup"><span data-stu-id="eefb5-343">Create Microsoft Teams Rooms Configuration Package</span></span>

1.  <span data-ttu-id="eefb5-344">En la consola del administrador de configuración, vaya a **paquetes**de **Administración** \> de aplicaciones de la **biblioteca** \> de software y, después, seleccione **crear paquete**.</span><span class="sxs-lookup"><span data-stu-id="eefb5-344">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**, and then select **Create Package**.</span></span>

2.  <span data-ttu-id="eefb5-345">Escriba la siguiente información para crear el paquete:</span><span class="sxs-lookup"><span data-stu-id="eefb5-345">Enter the following information to create the package:</span></span>

    -   <span data-ttu-id="eefb5-346">Nombre: **SRS V2-configurar el paquete de instalación de SRS**</span><span class="sxs-lookup"><span data-stu-id="eefb5-346">Name: **SRS v2 - Configure SRS Setup Package**</span></span>

    -   <span data-ttu-id="eefb5-347">Fabricante: **Microsoft Corporation**</span><span class="sxs-lookup"><span data-stu-id="eefb5-347">Manufacturer: **Microsoft Corporation**</span></span>

    -   <span data-ttu-id="eefb5-348">Versión: **1.0.0**</span><span class="sxs-lookup"><span data-stu-id="eefb5-348">Version: **1.0.0**</span></span>

    -   <span data-ttu-id="eefb5-349">Seleccione la casilla **este paquete contiene archivos de origen** , escriba la ruta de acceso a la carpeta **SRS V2-configure SRS Setup** y, a continuación, seleccione **Next**.</span><span class="sxs-lookup"><span data-stu-id="eefb5-349">Select the **This package contains source files** check box, enter the path to the **SRS v2 - Configure SRS Setup** folder, and then select **Next**.</span></span>

3.  <span data-ttu-id="eefb5-350">Seleccione no **crear un programa**y, a continuación, seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="eefb5-350">Select **Do not create a program**, and then select **Next**.</span></span>

4.  <span data-ttu-id="eefb5-351">Revise la página **confirmar la configuración** y, a continuación, seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="eefb5-351">Review the **Confirm the settings** page, and then select **Next**.</span></span>

5.  <span data-ttu-id="eefb5-352">Seleccione **cerrar**.</span><span class="sxs-lookup"><span data-stu-id="eefb5-352">Select **Close**.</span></span>



## <a name="distribute-configuration-manager-packages"></a><span data-ttu-id="eefb5-353">Distribuir paquetes de Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="eefb5-353">Distribute Configuration Manager packages</span></span>

<span data-ttu-id="eefb5-354">Todos los paquetes deben distribuirse a los servidores a los que se les ha asignado el rol de punto de distribución en la jerarquía de Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="eefb5-354">All the packages must be distributed to the servers that have been assigned the distribution point role in the Configuration Manager hierarchy.</span></span> <span data-ttu-id="eefb5-355">Siga las instrucciones a continuación para iniciar la distribución del paquete.</span><span class="sxs-lookup"><span data-stu-id="eefb5-355">Follow the instructions below to initiate package distribution.</span></span>

1.  <span data-ttu-id="eefb5-356">Distribuir paquetes de software.</span><span class="sxs-lookup"><span data-stu-id="eefb5-356">Distribute software packages.</span></span>

    1.  <span data-ttu-id="eefb5-357">En la consola del administrador de configuración, vaya a **paquetes**de **Administración** \> de aplicaciones de la **biblioteca** \> de software.</span><span class="sxs-lookup"><span data-stu-id="eefb5-357">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**.</span></span> <span data-ttu-id="eefb5-358">Seleccione todos los paquetes de software que desea distribuir y, a continuación, seleccione **distribuir contenido**.</span><span class="sxs-lookup"><span data-stu-id="eefb5-358">Select all the software packages you want to distribute, and then select **Distribute Content**.</span></span>

    2.  <span data-ttu-id="eefb5-359">Revise la lista de paquetes y, a continuación, seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="eefb5-359">Review the list of packages, and then select **Next**.</span></span>

    3.  <span data-ttu-id="eefb5-360">Agregue a la lista todos los servidores de puntos de distribución (o grupos de puntos de distribución, según la jerarquía de Configuration Manager) y, a continuación, seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="eefb5-360">Add all the distribution point servers (or distribution point groups, depending on your Configuration Manager hierarchy) to the list, and then select **Next**.</span></span>

    4.  <span data-ttu-id="eefb5-361">Seleccione **siguiente**y, después, haga clic en **cerrar**.</span><span class="sxs-lookup"><span data-stu-id="eefb5-361">Select **Next**, and then select **Close**.</span></span>

2.  <span data-ttu-id="eefb5-362">Distribuir paquetes de controladores.</span><span class="sxs-lookup"><span data-stu-id="eefb5-362">Distribute driver packages.</span></span>

    1.  <span data-ttu-id="eefb5-363">En la consola del administrador de configuración, vaya a **paquetes de controladores**de **sistemas** \> operativos de la **biblioteca** \> de software.</span><span class="sxs-lookup"><span data-stu-id="eefb5-363">In the Configuration Manager console, go to **Software Library** \> **Operating Systems** \> **Driver Packages**.</span></span> <span data-ttu-id="eefb5-364">Seleccione todos los paquetes de controladores que desea distribuir y, a continuación, seleccione **distribuir contenido**.</span><span class="sxs-lookup"><span data-stu-id="eefb5-364">Select all the driver packages you want to distribute, and then select **Distribute Content**.</span></span>

    2.  <span data-ttu-id="eefb5-365">Revise la lista de paquetes y, a continuación, seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="eefb5-365">Review the list of packages, and then select **Next**.</span></span>

    3.  <span data-ttu-id="eefb5-366">Agregue a la lista todos los servidores de puntos de distribución (o grupos de puntos de distribución, según la jerarquía de Configuration Manager) y, a continuación, seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="eefb5-366">Add all the distribution point servers (or distribution point groups, depending on your Configuration Manager hierarchy) to the list, and then select **Next**.</span></span>

    4.  <span data-ttu-id="eefb5-367">Seleccione **siguiente**y, después, haga clic en **cerrar**.</span><span class="sxs-lookup"><span data-stu-id="eefb5-367">Select **Next**, and then select **Close**.</span></span>

3.  <span data-ttu-id="eefb5-368">Distribuir paquetes del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="eefb5-368">Distribute operating system packages.</span></span>

    1.  <span data-ttu-id="eefb5-369">En la consola del administrador de configuración, vaya a **imágenes del sistema**operativo de **los sistemas** \> operativos de la **biblioteca** \> de software.</span><span class="sxs-lookup"><span data-stu-id="eefb5-369">In the Configuration Manager console, go to **Software Library** \> **Operating Systems** \> **Operating System Images**.</span></span> <span data-ttu-id="eefb5-370">Seleccione todas las imágenes del sistema operativo que desea distribuir y, a continuación, seleccione **distribuir contenido**.</span><span class="sxs-lookup"><span data-stu-id="eefb5-370">Select all the operating system images you want to distribute, and then select **Distribute Content**.</span></span>

    2.  <span data-ttu-id="eefb5-371">Revise la lista de paquetes y, a continuación, seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="eefb5-371">Review the list of packages, and then select **Next**.</span></span>

    3.  <span data-ttu-id="eefb5-372">Agregue a la lista todos los servidores de puntos de distribución (o grupos de puntos de distribución, según la jerarquía de Configuration Manager) y, a continuación, seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="eefb5-372">Add all the distribution point servers (or distribution point groups, depending on your Configuration Manager hierarchy) to the list, and then select **Next**.</span></span>

    4.  <span data-ttu-id="eefb5-373">Seleccione **siguiente**y, después, haga clic en **cerrar**.</span><span class="sxs-lookup"><span data-stu-id="eefb5-373">Select **Next**, and then select **Close**.</span></span>

> [!NOTE]
> <span data-ttu-id="eefb5-374">La distribución de paquetes puede llevar algún tiempo, según el tamaño del paquete, la jerarquía del administrador de configuración, el número de servidores de punto de distribución y el ancho de banda disponible en la red.</span><span class="sxs-lookup"><span data-stu-id="eefb5-374">Package distribution might take some time, depending on the package size, Configuration Manager hierarchy, number of distribution point servers, and the bandwidth available in your network.</span></span>
> 
> <span data-ttu-id="eefb5-375">Todos los paquetes deben distribuirse antes de que pueda empezar a implementar una unidad de salas de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="eefb5-375">All the packages must be distributed before you can start deploying a Microsoft Teams Rooms unit.</span></span>
> 
> <span data-ttu-id="eefb5-376">Puede revisar el estado de la distribución de paquetes en la consola de Configuration Manager si va a **supervisar** \> el **Estado de contenido**de estado \> de **distribución** .</span><span class="sxs-lookup"><span data-stu-id="eefb5-376">You can review the status of your package distribution in the Configuration Manager console by going to **Monitoring** \> **Distribution Status** \> **Content Status**.</span></span>

## <a name="configuration-manager-task-sequences"></a><span data-ttu-id="eefb5-377">Secuencias de tareas de Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="eefb5-377">Configuration Manager task sequences</span></span>

<span data-ttu-id="eefb5-378">Use las secuencias de tareas con System Center Configuration Manager para automatizar los pasos para implementar una imagen de sistema operativo en un equipo de destino.</span><span class="sxs-lookup"><span data-stu-id="eefb5-378">You use task sequences with System Center Configuration Manager to automate the steps for deploying an operating system image to a destination computer.</span></span> <span data-ttu-id="eefb5-379">Para implementar una unidad de salas de Microsoft Teams en un modo automatizado, cree una secuencia de tareas que haga referencia a la imagen de arranque utilizada para iniciar el equipo de destino Microsoft Team salas, la imagen del sistema operativo Windows 10 Enterprise que desea instalar y cualquier otro contenido adicional, como otras aplicaciones o actualizaciones de software.</span><span class="sxs-lookup"><span data-stu-id="eefb5-379">To deploy a Microsoft Teams Rooms unit in an automated fashion, you create a task sequence that references the boot image used to start the destination Microsoft Teams Rooms computer, the Windows 10 Enterprise operating system image that you want to install, and any other additional content, such as other applications or software updates.</span></span>

### <a name="import-the-sample-task-sequence"></a><span data-ttu-id="eefb5-380">Importar la secuencia de tareas de ejemplo</span><span class="sxs-lookup"><span data-stu-id="eefb5-380">Import the sample task sequence</span></span>

<span data-ttu-id="eefb5-381">Puede descargar y importar fácilmente una secuencia de tareas de muestra y personalizarla para satisfacer sus necesidades.</span><span class="sxs-lookup"><span data-stu-id="eefb5-381">You can download and easily import a sample task sequence and customize it to meet your needs.</span></span>

1.  <span data-ttu-id="eefb5-382">[**Descargue**](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true) la secuencia de tareas de ejemplo y copie el archivo zip descargado en una ubicación compartida.</span><span class="sxs-lookup"><span data-stu-id="eefb5-382">[**Download**](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true) the sample task sequence, and copy the downloaded zip file to a shared location.</span></span>
2.  <span data-ttu-id="eefb5-383">En la consola del administrador de configuración, vaya a **secuencias de tareas**de **sistemas** \> operativos de **bibliotecas** \> de software y, a continuación, seleccione **importar secuencia de tareas**.</span><span class="sxs-lookup"><span data-stu-id="eefb5-383">In the Configuration Manager console, go to **Software Library** \> **Operating Systems** \> **Task Sequences**, and then select **Import Task Sequence**.</span></span>

3.  <span data-ttu-id="eefb5-384">Seleccione **examinar**, vaya a la ubicación de la carpeta compartida que usó en el paso 1, seleccione el archivo **. zip Microsoft Team Rooms Deployment (en-EE.UU.)** y, a continuación, seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="eefb5-384">Select **Browse**, go to the shared folder location you used in step 1, select the **Microsoft Teams Rooms Deployment (EN-US).zip** file, and then select **Next**.</span></span>

4.  <span data-ttu-id="eefb5-385">Establezca **acción** como **crear nueva**y, a continuación, seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="eefb5-385">Set **Action** to **Create New**, and then select **Next**.</span></span>

5.  <span data-ttu-id="eefb5-386">Confirme la configuración y, a continuación, seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="eefb5-386">Confirm the settings, and then select **Next**.</span></span>

6.  <span data-ttu-id="eefb5-387">Seleccione **cerrar**.</span><span class="sxs-lookup"><span data-stu-id="eefb5-387">Select **Close**.</span></span>

### <a name="validate-that-the-reference-packages-are-correctly-linked-to-each-task-sequence-step"></a><span data-ttu-id="eefb5-388">Valide que los paquetes de referencia estén vinculados correctamente a cada paso de secuencia de tareas.</span><span class="sxs-lookup"><span data-stu-id="eefb5-388">Validate that the reference packages are correctly linked to each task sequence step.</span></span>

1. <span data-ttu-id="eefb5-389">Seleccione la secuencia de tareas importada y, después, haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="eefb5-389">Select the imported task sequence, and then select **Edit**.</span></span>

    <span data-ttu-id="eefb5-390">El editor de secuencias de tareas se abrirá y mostrará cada paso secuencial que necesita implementar y configurar una unidad de salas de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="eefb5-390">The Task Sequence Editor opens and displays each sequential step that you need to deploy and configure a Microsoft Teams Rooms unit.</span></span>

2. <span data-ttu-id="eefb5-391">Recorra cada paso y complete las actualizaciones recomendadas:</span><span class="sxs-lookup"><span data-stu-id="eefb5-391">Walk through each step and complete the recommended updates:</span></span>

   1. <span data-ttu-id="eefb5-392">**Reiniciar en Windows PE**: este paso se reiniciará y arrancará el equipo en Windows PXE.</span><span class="sxs-lookup"><span data-stu-id="eefb5-392">**Restart in Windows PE**: This step restarts and then boots the computer into Windows PXE.</span></span> <span data-ttu-id="eefb5-393">No es necesario realizar cambios en este paso.</span><span class="sxs-lookup"><span data-stu-id="eefb5-393">No changes are required for this step.</span></span>

   2. <span data-ttu-id="eefb5-394">**Partición disco 0: UEFI**: este paso borra la configuración del disco y crea particiones basadas en la configuración configurada.</span><span class="sxs-lookup"><span data-stu-id="eefb5-394">**Partition Disk 0 – UEFI**: This step wipes the disk configuration and creates partitions based on the configured settings.</span></span> <span data-ttu-id="eefb5-395">Le recomendamos que no realice ningún cambio en este paso.</span><span class="sxs-lookup"><span data-stu-id="eefb5-395">We recommend that you not make any changes to this step.</span></span>

   3. <span data-ttu-id="eefb5-396">**Establecer el nombre del equipo SRS**: este paso incluye una aplicación HTML para proporcionar una interfaz de usuario para establecer un nombre de equipo para la unidad de salas de Microsoft Teams durante la implementación.</span><span class="sxs-lookup"><span data-stu-id="eefb5-396">**Set SRS Computer Name**: This step includes an HTML application to provide a UI to set a computer name for the Microsoft Teams Rooms unit during the deployment.</span></span>
      -  <span data-ttu-id="eefb5-397">Este paso es opcional, pero solo se puede deshabilitar si desea administrar el nombre del equipo mediante un proceso alternativo.</span><span class="sxs-lookup"><span data-stu-id="eefb5-397">This is an optional step, but it can only be disabled if you want to manage computer naming through an alternate process.</span></span>
      -  <span data-ttu-id="eefb5-398">Compruebe que está seleccionado el paquete de **SRS V2-Set-SRSComputerName** .</span><span class="sxs-lookup"><span data-stu-id="eefb5-398">Verify that the **SRS v2 - Set-SRSComputerName** package is selected.</span></span> <span data-ttu-id="eefb5-399">Si no lo está, vaya al paquete y selecciónelo.</span><span class="sxs-lookup"><span data-stu-id="eefb5-399">If it isn’t, browse to the package and select it.</span></span>

   4. <span data-ttu-id="eefb5-400">**Aplicar sistema operativo**: este paso especifica la imagen del sistema operativo que se va a implementar y el archivo de respuesta de Sysprep desatendida que se va a usar.</span><span class="sxs-lookup"><span data-stu-id="eefb5-400">**Apply Operating System**: This step specifies the operating system image to be deployed and the unattended Sysprep answer file to use.</span></span>
      -  <span data-ttu-id="eefb5-401">Compruebe que esté seleccionada la imagen correcta del sistema operativo Windows 10 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="eefb5-401">Verify that the correct Windows 10 Enterprise operating system image file is selected.</span></span>
      -  <span data-ttu-id="eefb5-402">Compruebe que está habilitado el **uso de un archivo de respuesta Sysprep o desatendida para una instalación personalizada** y que el **paquete SRS V2-Sysprep** está seleccionado.</span><span class="sxs-lookup"><span data-stu-id="eefb5-402">Verify that **Use an unattended or Sysprep answer file for a custom installation** is enabled, and the **SRS v2 - Sysprep Package** is selected.</span></span> <span data-ttu-id="eefb5-403">Asegúrese también de que **nombre de archivo** está establecido en Unattend **. XML**.</span><span class="sxs-lookup"><span data-stu-id="eefb5-403">Also ensure that **File Name** is set to **unattend.xml**.</span></span>

   5. <span data-ttu-id="eefb5-404">**Aplicar configuración de Windows**: este paso recopila información sobre la instalación de Windows.</span><span class="sxs-lookup"><span data-stu-id="eefb5-404">**Apply Windows Settings**: This step gathers information about the Windows installation.</span></span>
      -  <span data-ttu-id="eefb5-405">Proporcione la información de licencias y registro, incluida la clave de producto, la contraseña de la cuenta de administrador local y la zona horaria (según sus necesidades).</span><span class="sxs-lookup"><span data-stu-id="eefb5-405">Provide licensing and registration information including the product key, local administrator account password, and time zone (depending on your needs).</span></span>

   6. <span data-ttu-id="eefb5-406">**Aplicar configuración de red**: este paso le permite especificar un grupo de trabajo o un nombre de dominio de Active Directory y una unidad organizativa.</span><span class="sxs-lookup"><span data-stu-id="eefb5-406">**Apply Network Settings**: This step allows you to specify a workgroup or Active Directory domain name and organizational unit.</span></span>
      > [!NOTE]
      > <span data-ttu-id="eefb5-407">Consulta el [dominio del sistema de la sala de Skype consideraciones](domain-joining-considerations.md) para la Unión de las acciones recomendadas que necesita tomar en la implementación de las unidades de salas de Microsoft Teams como miembros de un dominio de directorio de actve.</span><span class="sxs-lookup"><span data-stu-id="eefb5-407">See [Skype Room System domain joining considerations](domain-joining-considerations.md) for recommended actions you need to take in deploying Microsoft Teams Rooms units as members of an Actve Directory domain.</span></span>
   7. <span data-ttu-id="eefb5-408">**Aplicar drivers:** Este paso y sus subpasos se usan para implementar el firmware y los drivers de dispositivos aplicables según el modelo Surface Pro que tenga.</span><span class="sxs-lookup"><span data-stu-id="eefb5-408">**Apply Drivers:** This step and its sub-steps are used to deploy applicable device drivers and firmware based on the Surface Pro model you have.</span></span> <span data-ttu-id="eefb5-409">Actualice cada paso para especificar el paquete de controladores correspondiente asociado a esta implementación.</span><span class="sxs-lookup"><span data-stu-id="eefb5-409">Update each step to specify the relevant driver package associated with this deployment.</span></span>
      -   <span data-ttu-id="eefb5-410">Cada paquete de controladores está configurado para aprovechar los filtros de instrumental de administración de Windows (WMI) para implementar drivers y firmware relevantes en función de la marca y el modelo de Surface Pro.</span><span class="sxs-lookup"><span data-stu-id="eefb5-410">Each driver package is configured to leverage Windows Management Instrumentation (WMI) filters to deploy relevant drivers and firmware based on the Surface Pro make and model.</span></span>
      -   <span data-ttu-id="eefb5-411">Le recomendamos encarecidamente que no modifique la configuración de estos drivers; de lo contrario, la implementación podría fallar.</span><span class="sxs-lookup"><span data-stu-id="eefb5-411">We highly recommend that you not alter the configuration of these drivers, otherwise deployment might fail.</span></span>

   8. <span data-ttu-id="eefb5-412">**Configurar Windows y el administrador de configuración**: este paso implementa y configura el cliente de Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="eefb5-412">**Set up Windows and Configuration Manager**: This step deploys and configures the Configuration Manager client.</span></span> <span data-ttu-id="eefb5-413">Actualice este paso para especificar el paquete de cliente de Configuration Manager integrado.</span><span class="sxs-lookup"><span data-stu-id="eefb5-413">Update this step to specify the built-in Configuration Manager Client Package.</span></span>

   9. <span data-ttu-id="eefb5-414">**Instalar certificado raíz**: este paso distribuye el certificado raíz para los dispositivos que no están Unidos a un dominio y, por lo tanto, es opcional y está deshabilitado de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="eefb5-414">**Install Root Certificate**: This step distributes the root certificate for non–domain-joined devices, and therefore is optional and disabled by default.</span></span>
      -   <span data-ttu-id="eefb5-415">Habilite este paso si necesita implementar un certificado raíz en las unidades de salas de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="eefb5-415">Enable this step if you need to deploy a root certificate to the Microsoft Teams Rooms units.</span></span>
      -   <span data-ttu-id="eefb5-416">Si necesita realizar este paso, compruebe que esté seleccionada la redirección del sistema de archivos del servicio **raíz SRS V2** y deshabilite el redireccionamiento **del sistema de archivos de 64 bits** .</span><span class="sxs-lookup"><span data-stu-id="eefb5-416">If you do need to perform this step, verify that the **SRS v2 – Root Certificate Package** and **Disable 64-bit file system redirection** are selected.</span></span>

   10. <span data-ttu-id="eefb5-417">**Instalar y configurar el agente de supervisión**: este paso instala la versión de 64 bits del agente de Microsoft Azure monitor y configura el agente para que se conecte al área de trabajo del análisis de registros.</span><span class="sxs-lookup"><span data-stu-id="eefb5-417">**Install and Configure Monitoring Agent**: This step installs the 64-bit version of the Microsoft Azure Monitor agent and configures the agent to connect to your Log Analytics workspace.</span></span>
       -   <span data-ttu-id="eefb5-418">Este paso está deshabilitado de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="eefb5-418">This step is disabled by default.</span></span> <span data-ttu-id="eefb5-419">Habilite este paso solo si va a usar el agente de supervisión para supervisar el estado de las unidades de salas de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="eefb5-419">Enable this step only if you’re going to use the Monitoring Agent to monitor the health of your Microsoft Teams Rooms units.</span></span>
       -   <span data-ttu-id="eefb5-420">Edite este paso y actualice los parámetros de la línea de comandos para especificar el **identificador del área de trabajo** y la **clave del área de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="eefb5-420">Edit this step and update the command-line parameters to specify your **Workspace ID** and **Workspace Key**.</span></span>
       -   <span data-ttu-id="eefb5-421">Vea [configurar dispositivos de prueba para la supervisión de Azure](azure-monitor-deploy.md#configure-test-devices-for-azure-monitoring) para obtener más información sobre cómo obtener el identificador del área de trabajo de Operations Management Suite y la clave principal.</span><span class="sxs-lookup"><span data-stu-id="eefb5-421">See [Configure test devices for Azure Monitoring](azure-monitor-deploy.md#configure-test-devices-for-azure-monitoring) for more information about obtaining the Operations Management Suite Workspace ID and the primary key.</span></span>
       -   <span data-ttu-id="eefb5-422">Compruebe que esté seleccionada la redirección del sistema de archivos de **SRS V2-Microsoft Monitoring Agent** y deshabilitar el redireccionamiento **del sistema de archivos de 64** bits.</span><span class="sxs-lookup"><span data-stu-id="eefb5-422">Verify that the **SRS v2 – Microsoft Monitoring Agent Package** and **Disable 64-bit file system redirection** are selected.</span></span>
       -   <span data-ttu-id="eefb5-423">Para obtener más información sobre cómo supervisar el estado de la implementación de salas de Microsoft Teams, vea [planear la administración de salas de Microsoft Teams con Azure monitor](azure-monitor-plan.md), [implementar la administración de salas de Microsoft Teams con Azure monitor](azure-monitor-deploy.md) y [administrar Microsoft Los dispositivos de salas de equipos con el monitor de Azure](azure-monitor-manage.md).</span><span class="sxs-lookup"><span data-stu-id="eefb5-423">For more information about monitoring the health of your Microsoft Teams Rooms deployment, see [Plan Microsoft Teams Rooms management with Azure Monitor](azure-monitor-plan.md), [Deploy Microsoft Teams Rooms management with Azure Monitor](azure-monitor-deploy.md) and [Manage Microsoft Teams Rooms devices with Azure Monitor](azure-monitor-manage.md).</span></span>

   11. <span data-ttu-id="eefb5-424">**Copie los archivos de configuración de SRS V2**: en este paso, se copian los archivos de configuración y configuración necesarios del kit de implementación de Microsoft Teams Rooms en la unidad de disco duro local.</span><span class="sxs-lookup"><span data-stu-id="eefb5-424">**Copy SRS v2 Configuration Files**: This step copies the required setup and configuration files from the Microsoft Teams Rooms deployment kit to the local hard drive.</span></span> <span data-ttu-id="eefb5-425">No se necesita ninguna personalización para este paso.</span><span class="sxs-lookup"><span data-stu-id="eefb5-425">No customization is required for this step.</span></span>
       -   <span data-ttu-id="eefb5-426">Compruebe que se seleccione el **paquete de aplicación SRS V2-SRS** y deshabilitar el redireccionamiento **del sistema de archivos de 64 bits** .</span><span class="sxs-lookup"><span data-stu-id="eefb5-426">Verify that the **SRS v2 – SRS Application Package** and **Disable 64-bit file system redirection** are selected.</span></span>

   12. <span data-ttu-id="eefb5-427">**Install-SRSv2-os-updates**: este paso implementa todas las actualizaciones de sistema operativo obligatorias necesarias para la implementación de salas de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="eefb5-427">**Install-SRSv2-OS-Updates**: This step deploys any mandatory operating system updates required with the Microsoft Teams Rooms deployment.</span></span> <span data-ttu-id="eefb5-428">Siga este procedimiento:</span><span class="sxs-lookup"><span data-stu-id="eefb5-428">Do the following:</span></span>
       -   <span data-ttu-id="eefb5-429">Marque [configurar una consola de salones de Microsoft Teams](console.md) para ver qué actualizaciones son necesarias.</span><span class="sxs-lookup"><span data-stu-id="eefb5-429">Check [Configure a Microsoft Teams Rooms console](console.md) to see which updates are required.</span></span>
       -   <span data-ttu-id="eefb5-430">Compruebe que el **paquete de actualizaciones para el sistema operativo SRS V2** incluye todas las actualizaciones necesarias.</span><span class="sxs-lookup"><span data-stu-id="eefb5-430">Verify that your **SRS v2 – OS Updates Package** includes all the required updates.</span></span>
       -   <span data-ttu-id="eefb5-431">Compruebe que esté seleccionado el **paquete SRS V2 – os updates** .</span><span class="sxs-lookup"><span data-stu-id="eefb5-431">Verify that the **SRS v2 – OS Updates Package** is selected.</span></span>
       -   <span data-ttu-id="eefb5-432">Compruebe que la Directiva de ejecución de PowerShell esté \*\*\*\* configurada para omitir.</span><span class="sxs-lookup"><span data-stu-id="eefb5-432">Verify that the PowerShell execution policy is set to **Bypass**.</span></span>

   13. <span data-ttu-id="eefb5-433">**Reiniciar equipo**: este paso reinicia el equipo después de instalar las actualizaciones obligatorias del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="eefb5-433">**Restart Computer**: This step reboots the computer after the mandatory operating system updates are installed.</span></span> <span data-ttu-id="eefb5-434">No se necesita ninguna personalización para este paso.</span><span class="sxs-lookup"><span data-stu-id="eefb5-434">No customization is required for this step.</span></span>

   14. <span data-ttu-id="eefb5-435">**Configurar componentes de Windows**: este paso configura las características necesarias de Windows.</span><span class="sxs-lookup"><span data-stu-id="eefb5-435">**Configure Windows Components**: This step configures the required Windows features.</span></span> <span data-ttu-id="eefb5-436">No se necesita ninguna personalización para este paso.</span><span class="sxs-lookup"><span data-stu-id="eefb5-436">No customization is required for this step.</span></span>

   15. <span data-ttu-id="eefb5-437">**Reiniciar equipo**: este paso reinicia el equipo después de configurar las características de Windows.</span><span class="sxs-lookup"><span data-stu-id="eefb5-437">**Restart Computer**: This step reboots the computer after the Windows features are configured.</span></span> <span data-ttu-id="eefb5-438">No se necesita ninguna personalización para este paso.</span><span class="sxs-lookup"><span data-stu-id="eefb5-438">No customization is required for this step.</span></span>

   16. <span data-ttu-id="eefb5-439">**Agregar usuario local de Skype**: este paso crea la cuenta de Skype local que se usa para iniciar sesión automáticamente en Windows e iniciar la aplicación salas de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="eefb5-439">**Add Local Skype User**: This step creates the local Skype account used to automatically sign in to Windows and start the Microsoft Teams Rooms application.</span></span> <span data-ttu-id="eefb5-440">Este paso no tiene ningún paquete de software asociado, y no se necesita ninguna personalización para él.</span><span class="sxs-lookup"><span data-stu-id="eefb5-440">This step doesn’t have any software package associated with it, and no customization is required for it.</span></span>

   17. <span data-ttu-id="eefb5-441">**Instalar y configurar la aplicación SRS**: este paso configura la instalación de la aplicación salas de Microsoft Teams para el siguiente arranque del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="eefb5-441">**Set up and configure SRS application**: This step configures the Microsoft Teams Rooms application installation for the next boot of the operating system.</span></span>
       -   <span data-ttu-id="eefb5-442">Compruebe que esté seleccionada la **configuración de SRS V2-configure SRS Setup Package** and disable **64-bit File System** .</span><span class="sxs-lookup"><span data-stu-id="eefb5-442">Verify that the **SRS v2 – Configure SRS Setup Package** and **Disable 64-bit file system redirection** are selected.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="eefb5-443">Es muy importante que los pasos de la secuencia de tareas estén en el orden indicado.</span><span class="sxs-lookup"><span data-stu-id="eefb5-443">It is very important that the task sequence steps must be in the provided order.</span></span> <span data-ttu-id="eefb5-444">Modificar el orden de los pasos o configurar pasos adicionales puede estropear la implementación.</span><span class="sxs-lookup"><span data-stu-id="eefb5-444">Modifying the order of steps, or configuring additional steps might break the deployment.</span></span>
>
> <span data-ttu-id="eefb5-445">**Configurar y configurar** el paso de la aplicación SRS debe ser el último paso de la secuencia de tareas; de lo contrario, la implementación podría fallar.</span><span class="sxs-lookup"><span data-stu-id="eefb5-445">**Set up and configure SRS application** step must be the last step in the task sequence, otherwise the deployment might fail.</span></span>

### <a name="create-deployment-for-the-task-sequence"></a><span data-ttu-id="eefb5-446">Crear una implementación para la secuencia de tareas</span><span class="sxs-lookup"><span data-stu-id="eefb5-446">Create deployment for the task sequence</span></span>

1. <span data-ttu-id="eefb5-447">Seleccione la secuencia de tareas y, a continuación, seleccione **implementar**.</span><span class="sxs-lookup"><span data-stu-id="eefb5-447">Select the task sequence, and then select **Deploy**.</span></span>

2. <span data-ttu-id="eefb5-448">Seleccione **examinar** para seleccionar recopilación de destino para la implementación.</span><span class="sxs-lookup"><span data-stu-id="eefb5-448">Select **Browse** to select target collection for deployment.</span></span>

3. <span data-ttu-id="eefb5-449">Seleccione **todos los equipos** desconocidos y, después, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="eefb5-449">Select **All Unknown Computers** and then select **OK**.</span></span>

4. <span data-ttu-id="eefb5-450">Seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="eefb5-450">Select **Next**.</span></span>

5. <span data-ttu-id="eefb5-451">Seleccione **disponible** en la lista desplegable **propósito** .</span><span class="sxs-lookup"><span data-stu-id="eefb5-451">Select **Available** on the **Purpose** drop down list.</span></span>

6. <span data-ttu-id="eefb5-452">Seleccione **solo medios y PXE** en la lista **hacer disponible hasta el siguiente** y, a continuación, seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="eefb5-452">Select **Only Media and PXE** in the **Make available to the following** list, and then select **Next**.</span></span>
   > [!WARNING]
   > <span data-ttu-id="eefb5-453">Es muy importante que el **propósito** esté establecido en **disponible**.</span><span class="sxs-lookup"><span data-stu-id="eefb5-453">It is very important that **Purpose** is set to **Available**.</span></span> <span data-ttu-id="eefb5-454">Asegúrese de que el **propósito** **no** esté establecido en **requerido**.</span><span class="sxs-lookup"><span data-stu-id="eefb5-454">Make sure that the **Purpose** is **NOT** set to **Required**.</span></span> <span data-ttu-id="eefb5-455">Además, asegúrese de que selecciona **solo medios y PXE** en la forma **disponible para lo siguiente**.</span><span class="sxs-lookup"><span data-stu-id="eefb5-455">Also make sure that you select **Only Media and PXE** in the **Make available to the following**.</span></span>
   >
   > <span data-ttu-id="eefb5-456">La configuración de estos valores en algo diferente puede hacer que todos los equipos obtengan la imagen de implementación de salas de Microsoft Teams al arrancar.</span><span class="sxs-lookup"><span data-stu-id="eefb5-456">Setting these values to something else might cause all computers to get the Microsoft Teams Rooms deployment image when booted.</span></span>
7. <span data-ttu-id="eefb5-457">No especifique ninguna programación y seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="eefb5-457">Do not specify any schedule and select **Next**.</span></span>

8. <span data-ttu-id="eefb5-458">No cambie nada en la sección **experiencia del usuario** y seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="eefb5-458">Do not change anything within the **User Experience** section and select **Next**.</span></span>

9. <span data-ttu-id="eefb5-459">No cambie nada dentro de la sección **alertas** y seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="eefb5-459">Do not change anything within the **Alerts** section and select **Next**.</span></span>

10. <span data-ttu-id="eefb5-460">No cambie nada en la sección de **puntos de distribución** y seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="eefb5-460">Do not change anything within the **Distribution Points** section and select **Next**.</span></span>

11. <span data-ttu-id="eefb5-461">Confirme la configuración y, a continuación, seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="eefb5-461">Confirm the settings and then select **Next**.</span></span>

12. <span data-ttu-id="eefb5-462">Seleccione **cerrar**.</span><span class="sxs-lookup"><span data-stu-id="eefb5-462">Select **Close**.</span></span>

<a name="validate-and-troubleshoot-the-solution"></a><span data-ttu-id="eefb5-463">Validar y solucionar problemas de la solución</span><span class="sxs-lookup"><span data-stu-id="eefb5-463">Validate and troubleshoot the solution</span></span>
--------------------------------------

<span data-ttu-id="eefb5-464">Una vez completadas las secuencias de tareas de System Center Configuration Manager, tendrá que realizar una ejecución de prueba para validar que la secuencia de tareas puede implementar y configurar las unidades de salas de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="eefb5-464">After you’ve completed the System Center Configuration Manager task sequences, you’ll need to perform a test run to validate that the task sequence can deploy and configure Microsoft Teams Rooms units.</span></span>

1.  <span data-ttu-id="eefb5-465">Conecte el dispositivo de prueba a la red cableada mediante uno de los adaptadores Ethernet compatibles o usando la superficie del Dock.</span><span class="sxs-lookup"><span data-stu-id="eefb5-465">Connect the test device to the wired network by using one of the supported Ethernet adapters or using the Surface dock.</span></span> <span data-ttu-id="eefb5-466">Si la funcionalidad de arranque PXE no se ha configurado para su entorno, puede usar la imagen de arranque de la unidad flash USB [que creó anteriormente](https://docs.microsoft.com/sccm/osd/deploy-use/create-bootable-media) para arrancar desde USB y conectarse a Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="eefb5-466">If PXE boot functionality hasn’t been configured for your environment, you can use the boot image on the USB flash drive [that you created earlier](https://docs.microsoft.com/sccm/osd/deploy-use/create-bootable-media) to boot from USB and connect to Configuration Manager.</span></span>

2.  <span data-ttu-id="eefb5-467">Acceda al firmware e inicie el inicio PXE:</span><span class="sxs-lookup"><span data-stu-id="eefb5-467">Access the firmware and initiate PXE boot:</span></span>

    1.  <span data-ttu-id="eefb5-468">Cerciórese de que el dispositivo Surface esté apagado.</span><span class="sxs-lookup"><span data-stu-id="eefb5-468">Ensure the Surface device is powered off.</span></span>

    2.  <span data-ttu-id="eefb5-469">Mantén pulsado el botón **subir volumen** .</span><span class="sxs-lookup"><span data-stu-id="eefb5-469">Press and hold the **Volume Up** button.</span></span>

    3.  <span data-ttu-id="eefb5-470">Presione y suelte el botón **Power (encendido** ).</span><span class="sxs-lookup"><span data-stu-id="eefb5-470">Press and release the **Power** button.</span></span>

    4.  <span data-ttu-id="eefb5-471">Cuando el dispositivo empiece a arrancar, suelte el botón **subir volumen** .</span><span class="sxs-lookup"><span data-stu-id="eefb5-471">After the device begins to boot, release the **Volume Up** button.</span></span>

    5.  <span data-ttu-id="eefb5-472">Seleccione **configuración de arranque**.</span><span class="sxs-lookup"><span data-stu-id="eefb5-472">Select **Boot configuration**.</span></span>

    6.  <span data-ttu-id="eefb5-473">Siga uno de estos pasos:</span><span class="sxs-lookup"><span data-stu-id="eefb5-473">Do one of the following:</span></span>

        -   <span data-ttu-id="eefb5-474">Seleccione **arranque PXE**y arrástrelo hasta la parte superior de la lista.</span><span class="sxs-lookup"><span data-stu-id="eefb5-474">Select **PXE boot**, and drag it to the top of the list.</span></span> <span data-ttu-id="eefb5-475">Como alternativa, puedes deslizar el dedo hacia la izquierda en el adaptador de red para arrancar el dispositivo inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="eefb5-475">Alternatively, you can swipe left on the network adapter to boot to the device immediately.</span></span> <span data-ttu-id="eefb5-476">Esto no afectará el orden de inicio.</span><span class="sxs-lookup"><span data-stu-id="eefb5-476">This won’t affect the boot order.</span></span>
        -   <span data-ttu-id="eefb5-477">Seleccione la unidad flash USB que contiene el medio de inicio.</span><span class="sxs-lookup"><span data-stu-id="eefb5-477">Select the USB flash drive that holds the boot media.</span></span>

3.  <span data-ttu-id="eefb5-478">Seleccione **salir**y, a continuación, **reiniciar ahora**.</span><span class="sxs-lookup"><span data-stu-id="eefb5-478">Select **Exit**, and then select **Restart Now**.</span></span>

4.  <span data-ttu-id="eefb5-479">Cuando se le solicite, seleccione **entrar** para el servicio de inicio de red.</span><span class="sxs-lookup"><span data-stu-id="eefb5-479">When prompted, select **Enter** for network boot service.</span></span>

5.  <span data-ttu-id="eefb5-480">Windows PE se cargará en la memoria y se iniciará el Asistente para secuencia de tareas.</span><span class="sxs-lookup"><span data-stu-id="eefb5-480">Windows PE will load into memory, and the Task Sequence Wizard will start.</span></span> <span data-ttu-id="eefb5-481">Seleccione **siguiente** para continuar.</span><span class="sxs-lookup"><span data-stu-id="eefb5-481">Select **Next** to continue.</span></span>

6.  <span data-ttu-id="eefb5-482">Seleccione la secuencia de tareas que importó anteriormente y, a continuación, seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="eefb5-482">Select the task sequence that you imported earlier, and then select **Next**.</span></span>

7.  <span data-ttu-id="eefb5-483">Después de aplicar la configuración del disco, se le pedirá que especifique un nombre de equipo para el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="eefb5-483">After the disk configuration is applied, you’ll be prompted to specify a computer name for the device.</span></span> <span data-ttu-id="eefb5-484">La interfaz de usuario mostrará un nombre de equipo recomendado según el número de serie del dispositivo Surface Pro.</span><span class="sxs-lookup"><span data-stu-id="eefb5-484">The user interface will display a recommended computer name based on the serial number of the Surface Pro device.</span></span> <span data-ttu-id="eefb5-485">Puede aceptar el nombre propuesto o especificar uno nuevo.</span><span class="sxs-lookup"><span data-stu-id="eefb5-485">You can either accept the proposed name or specify a new one.</span></span> <span data-ttu-id="eefb5-486">Siga las instrucciones de la pantalla asignación de nombre de equipo.</span><span class="sxs-lookup"><span data-stu-id="eefb5-486">Follow the instructions on the computer name assignment screen.</span></span> <span data-ttu-id="eefb5-487">Al seleccionar **Aceptar**, comienza la implementación.</span><span class="sxs-lookup"><span data-stu-id="eefb5-487">When you select **Accept**, the deployment begins.</span></span>

8.  <span data-ttu-id="eefb5-488">El resto del proceso de implementación es automático y no pide más entradas del usuario.</span><span class="sxs-lookup"><span data-stu-id="eefb5-488">The rest of the deployment process is automatic and doesn’t ask for any more user input.</span></span>

9.  <span data-ttu-id="eefb5-489">Después de que la secuencia de tareas de implementación termine de configurar el dispositivo, verá la siguiente pantalla de configuración que le pedirá que configure las opciones de la aplicación salas de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="eefb5-489">After the deployment task sequence finishes configuring the device, you’ll see the following configuration screen that asks you to configure the Microsoft Teams Rooms application settings.</span></span>

    ![Pantalla inicial de la aplicación salas de Microsoft Teams](../media/room-systems-scale-image2.png)

10.  <span data-ttu-id="eefb5-491">Conecte la Surface Pro a la consola de salas de Microsoft Teams y configure las opciones de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="eefb5-491">Plug the Surface Pro into the Microsoft Teams Rooms console, and configure the application settings.</span></span>

11.  <span data-ttu-id="eefb5-492">Compruebe que las capacidades enumeradas en la [ayuda de Microsoft Teams Rooms](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2) estén funcionando en el dispositivo implementado.</span><span class="sxs-lookup"><span data-stu-id="eefb5-492">Validate that the capabilities listed in [Microsoft Teams Rooms help](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2) are working on the deployed device.</span></span>


<span data-ttu-id="eefb5-493">Para solucionar un error de instalación, consulte el archivo **SMSTS. log** , en el que se registran todos los pasos ejecutados en una secuencia de tareas de Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="eefb5-493">To troubleshoot a failed installation, check the **SMSTS.log** file, which logs all the steps executed in a Configuration Manager task sequence.</span></span>

<span data-ttu-id="eefb5-494">El archivo SMSTS. log se almacena en una de varias rutas, dependiendo de la fase del proceso de compilación.</span><span class="sxs-lookup"><span data-stu-id="eefb5-494">The SMSTS.log file is stored on one of a number of paths, depending on the stage of the build process.</span></span> <span data-ttu-id="eefb5-495">Consulte la tabla siguiente para identificar la ruta de acceso al archivo SMSTS. log.</span><span class="sxs-lookup"><span data-stu-id="eefb5-495">Check the following table to identify the path to the SMSTS.log file.</span></span>


| <span data-ttu-id="eefb5-496">**Fase de implementación**</span><span class="sxs-lookup"><span data-stu-id="eefb5-496">**Deployment phase**</span></span>                                                            | <span data-ttu-id="eefb5-497">**Ruta de registro de secuencia de tareas**</span><span class="sxs-lookup"><span data-stu-id="eefb5-497">**Task sequence log path**</span></span>                         |
|---------------------------------------------------------------------------------|----------------------------------------------------|
| <span data-ttu-id="eefb5-498">WinPE, antes del formato HDD</span><span class="sxs-lookup"><span data-stu-id="eefb5-498">WinPE, before HDD format</span></span>                                                        | <span data-ttu-id="eefb5-499">X:\\Windows\\Temp\\smstslog\\smsts. log</span><span class="sxs-lookup"><span data-stu-id="eefb5-499">X:\\Windows\\Temp\\smstslog\\smsts.log</span></span>             |
| <span data-ttu-id="eefb5-500">WinPE, después de formato HDD</span><span class="sxs-lookup"><span data-stu-id="eefb5-500">WinPE, after HDD format</span></span>                                                         | <span data-ttu-id="eefb5-501">C:\\_SMSTaskSequence\\registra\\Smstslog\\smsts. log</span><span class="sxs-lookup"><span data-stu-id="eefb5-501">C:\\_SMSTaskSequence\\Logs\\Smstslog\\smsts.log</span></span>    |
| <span data-ttu-id="eefb5-502">Sistema operativo implementado antes de instalar el agente de administrador de configuración</span><span class="sxs-lookup"><span data-stu-id="eefb5-502">Operating system deployed, before the Configuration Manager agent was installed</span></span> | <span data-ttu-id="eefb5-503">c:\\_SMSTaskSequence\\registra\\Smstslog\\smsts. log</span><span class="sxs-lookup"><span data-stu-id="eefb5-503">c:\\_SMSTaskSequence\\Logs\\Smstslog\\smsts.log</span></span>    |
| <span data-ttu-id="eefb5-504">Sistema operativo y el agente de Configuration Manager implementado</span><span class="sxs-lookup"><span data-stu-id="eefb5-504">Operating system and the Configuration Manager agent deployed</span></span>                   | <span data-ttu-id="eefb5-505">% WINDIR%\\system32\\CCM\\registra\\Smstslog\\smsts. log</span><span class="sxs-lookup"><span data-stu-id="eefb5-505">%windir%\\System32\\ccm\\logs\\Smstslog\\smsts.log</span></span> |
| <span data-ttu-id="eefb5-506">Ejecución de la secuencia de tareas completada</span><span class="sxs-lookup"><span data-stu-id="eefb5-506">Task sequence execution complete</span></span>                                                | <span data-ttu-id="eefb5-507">% WINDIR%\\system32\\CCM\\registra\\smsts. log</span><span class="sxs-lookup"><span data-stu-id="eefb5-507">%windir%\\System32\\ccm\\logs\\smsts.log</span></span>           |

> [!TIP]
> <span data-ttu-id="eefb5-508">Puede seleccionar **F8** en cualquier momento durante la secuencia de tareas para abrir una consola de comandos y, a continuación, obtener acceso al archivo SMSTS. log.</span><span class="sxs-lookup"><span data-stu-id="eefb5-508">You can select **F8** at any time during the task sequence to open a command console, and then get access to the SMSTS.log file.</span></span>

<span data-ttu-id="eefb5-509">Para solucionar problemas de inicio PXE, consulte los dos archivos de registro en el servidor de Configuration Manager que son específicos de las acciones de PXE:</span><span class="sxs-lookup"><span data-stu-id="eefb5-509">To troubleshoot PXE boot issues, check the two log files on the Configuration Manager server that are specific to PXE actions:</span></span>

-   <span data-ttu-id="eefb5-510">**Pxecontrol. log**, ubicado en el directorio de registros de instalación de Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="eefb5-510">**Pxecontrol.log**, located in the Configuration Manager installation logs directory</span></span>

-   <span data-ttu-id="eefb5-511">**Smspxe. log**, que se encuentra en el directorio de registros del punto de administración de Configuration Manager (MP)</span><span class="sxs-lookup"><span data-stu-id="eefb5-511">**Smspxe.log**, located in Configuration Manager Management Point (MP) logs directory</span></span>

<span data-ttu-id="eefb5-512">Para obtener una lista completa de los archivos de registro que puede usar para solucionar problemas en la instalación de Configuration Manager, consulte [archivos de registro en System Center Configuration Manager](https://docs.microsoft.com/sccm/core/plan-design/hierarchy/log-files).</span><span class="sxs-lookup"><span data-stu-id="eefb5-512">For a complete list of the log files that you can use to further troubleshoot your Configuration Manager installation, see [Log files in System Center Configuration Manager](https://docs.microsoft.com/sccm/core/plan-design/hierarchy/log-files).</span></span>
