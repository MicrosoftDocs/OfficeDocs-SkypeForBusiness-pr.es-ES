---
title: Implementación de sistemas de salón de Skype con System Center Configuration Manager
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 5/10/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.custom: Strat_SB_Admin
ms.assetid: 678689e4-d547-499b-be64-7d8f16dd8668
description: Lea este tema para obtener más información sobre la implementación de sistemas de salón de Skype v2 en las implementaciones de gran escala.
ms.openlocfilehash: 33ac42e42695a7881d6348aee32046223f97b418
ms.sourcegitcommit: febd51fd7988602a8c9839e4e9872ae8f5d77c63
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2018
---
# <a name="deploy-skype-room-systems-v2-by-using-system-center-configuration-manager"></a><span data-ttu-id="f40d4-103">Implementación de sistemas de salón de Skype v2 mediante System Center Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="f40d4-103">Deploy Skype Room Systems v2 by using System Center Configuration Manager</span></span>

<span data-ttu-id="f40d4-104">En este artículo se proporciona toda la información necesaria para crear las implementaciones de sistemas de salón de Skype v2 mediante System Center Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="f40d4-104">This article gives you all the necessary information to create your Skype Room Systems v2 deployments by using System Center Configuration Manager.</span></span>

<span data-ttu-id="f40d4-105">Con la fáciles de usar los métodos proporcionados por System Center Configuration Manager, puede implementar el sistema operativo y otras aplicaciones en varios dispositivos de destino.</span><span class="sxs-lookup"><span data-stu-id="f40d4-105">With the easy-to-use methods provided by System Center Configuration Manager, you can deploy the operating system and other applications to multiple target devices.</span></span>

<span data-ttu-id="f40d4-106">Use el enfoque se ilustra a continuación le guiarán a través de la configuración del Administrador de configuración y personalizar los paquetes de ejemplo y secuencias de comandos proporcionadas a lo largo de esta guía, según sea necesario para la organización.</span><span class="sxs-lookup"><span data-stu-id="f40d4-106">Use the approach illustrated below to guide you through your Configuration Manager configuration, and customize the sample packages and scripts provided throughout this guidance as needed for your organization.</span></span>

![Proceso de implementación de sistemas de salón de Skype v2 mediante el Administrador de configuración](../../media/room-systems-scale-image1.png)

> [!IMPORTANT]
> <span data-ttu-id="f40d4-108">Esta solución sólo se ha probado con implementaciones basado en Surface Pro.</span><span class="sxs-lookup"><span data-stu-id="f40d4-108">This solution has only been tested with Surface Pro–based deployments.</span></span> <span data-ttu-id="f40d4-109">Siga las instrucciones del fabricante para las configuraciones que no están basadas en Surface Pro.</span><span class="sxs-lookup"><span data-stu-id="f40d4-109">Follow the manufacturer’s guidelines for configurations that aren’t based on Surface Pro.</span></span>

## <a name="validate-prerequisites"></a><span data-ttu-id="f40d4-110">Validar los requisitos previos</span><span class="sxs-lookup"><span data-stu-id="f40d4-110">Validate prerequisites</span></span>

<span data-ttu-id="f40d4-111">Para implementar sistemas de salón de Skype v2 con el Administrador de configuración, asegúrese de que cumple los siguientes requisitos previos y requisitos.</span><span class="sxs-lookup"><span data-stu-id="f40d4-111">To deploy Skype Room Systems v2 with Configuration Manager, ensure that you meet the following prerequisites and requirements.</span></span>

### <a name="system-center-configuration-manager-requirements"></a><span data-ttu-id="f40d4-112">Requisitos de System Center Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="f40d4-112">System Center Configuration Manager requirements</span></span>

-   <span data-ttu-id="f40d4-113">System Center Configuration Manager versión debe ser al menos 1706 o anterior.</span><span class="sxs-lookup"><span data-stu-id="f40d4-113">System Center Configuration Manager version must be at least 1706 or above.</span></span> <span data-ttu-id="f40d4-114">Se recomienda usar 1710 o posterior.</span><span class="sxs-lookup"><span data-stu-id="f40d4-114">We recommend using 1710 or later.</span></span> <span data-ttu-id="f40d4-115">Desproteger el [soporte técnico para Windows 10 en System Center Configuration Manager](https://docs.microsoft.com/sccm/core/plan-design/configs/support-for-windows-10#windows-10-as-a-client) para obtener más información acerca de las versiones de Windows 10 que admite el Administrador de configuración.</span><span class="sxs-lookup"><span data-stu-id="f40d4-115">Check out [Support for Windows 10 in System Center Configuration Manager](https://docs.microsoft.com/sccm/core/plan-design/configs/support-for-windows-10#windows-10-as-a-client) to learn about the Windows 10 versions that Configuration Manager supports.</span></span>

-   <span data-ttu-id="f40d4-116">Debe estar instalada una versión compatible de evaluación de Windows y el Kit de implementación (ADK) para Windows 10.</span><span class="sxs-lookup"><span data-stu-id="f40d4-116">A supported version of Windows Assessment and Deployment Kit (ADK) for Windows 10 must be installed.</span></span> <span data-ttu-id="f40d4-117">Vea las versiones de [Windows 10 ADK](https://docs.microsoft.com/sccm/core/plan-design/configs/support-for-windows-10#windows-10-adk) que puede usar con distintas versiones de Configuration Manager y asegúrese de que la implementación incluye la versión correcta.</span><span class="sxs-lookup"><span data-stu-id="f40d4-117">See the versions of the [Windows 10 ADK](https://docs.microsoft.com/sccm/core/plan-design/configs/support-for-windows-10#windows-10-adk) that you can use with different versions of Configuration Manager, and ensure that your deployment includes the correct version.</span></span>

-   <span data-ttu-id="f40d4-118">Los servidores del sistema de sitio deben tener el rol de punto de distribución, y las imágenes de arranque deberían estar habilitadas para que [previo al arranque de soporte técnico de entorno (PXE) de ejecución](https://docs.microsoft.com/sccm/osd/deploy-use/use-pxe-to-deploy-windows-over-the-network) habilitar las implementaciones iniciadas por la red.</span><span class="sxs-lookup"><span data-stu-id="f40d4-118">The site system servers must have been assigned the distribution point role, and the boot images should be enabled for [preboot execution environment (PXE) support](https://docs.microsoft.com/sccm/osd/deploy-use/use-pxe-to-deploy-windows-over-the-network) to enable network-initiated deployments.</span></span> <span data-ttu-id="f40d4-119">Si no está habilitada la compatibilidad PXE, puede usar el [medio de arranque](https://docs.microsoft.com/sccm/osd/deploy-use/use-bootable-media-to-deploy-windows-over-the-network) para las implementaciones de.</span><span class="sxs-lookup"><span data-stu-id="f40d4-119">If PXE support isn’t enabled, you can use [bootable media](https://docs.microsoft.com/sccm/osd/deploy-use/use-bootable-media-to-deploy-windows-over-the-network) for your deployments.</span></span>

-   <span data-ttu-id="f40d4-120">Una cuenta de acceso de red debe configurarse para admitir escenarios de implementación de nuevo equipo (más bajos del hardware).</span><span class="sxs-lookup"><span data-stu-id="f40d4-120">A network access account must be configured to support new computer (bare metal) deployment scenarios.</span></span> <span data-ttu-id="f40d4-121">Para obtener más información acerca de la configuración de una cuenta de acceso de red, consulte [Administrar cuentas para tener acceso al contenido en System Center Configuration Manager](https://docs.microsoft.com/sccm/core/plan-design/hierarchy/manage-accounts-to-access-content#bkmk_NAA).</span><span class="sxs-lookup"><span data-stu-id="f40d4-121">To learn more about the configuration of a network access account, see [Manage accounts to access content in System Center Configuration Manager](https://docs.microsoft.com/sccm/core/plan-design/hierarchy/manage-accounts-to-access-content#bkmk_NAA).</span></span>

-   <span data-ttu-id="f40d4-122">Se recomienda que habilite [la compatibilidad con multidifusión](https://docs.microsoft.com/sccm/osd/deploy-use/use-multicast-to-deploy-windows-over-the-network), si es probable que implementar la misma imagen v2 de sistemas de salón de Skype en varias unidades al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="f40d4-122">We recommend that you enable [multicast support](https://docs.microsoft.com/sccm/osd/deploy-use/use-multicast-to-deploy-windows-over-the-network), if you’re likely to deploy the same Skype Room Systems v2 image to multiple units at the same time.</span></span>

### <a name="networking-requirements"></a><span data-ttu-id="f40d4-123">Requisitos de red</span><span class="sxs-lookup"><span data-stu-id="f40d4-123">Networking requirements</span></span>

-   <span data-ttu-id="f40d4-124">La red debe tener un servidor de protocolo de configuración dinámica de Host (DHCP), configurado para la distribución automática de direcciones IP a las subredes donde se implementará unidades de sistemas de salón de Skype v2.</span><span class="sxs-lookup"><span data-stu-id="f40d4-124">Your network should have a Dynamic Host Configuration Protocol (DHCP) server, configured for automatic IP address distribution to the subnets where Skype Room Systems v2 units will be deployed.</span></span>

    > [!NOTE]
    > <span data-ttu-id="f40d4-125">Duración de concesión DHCP debe establecerse en un valor mayor que la duración de la implementación de imagen.</span><span class="sxs-lookup"><span data-stu-id="f40d4-125">DHCP lease duration must be set to a value longer than the image deployment duration.</span></span> <span data-ttu-id="f40d4-126">De lo contrario, puede producirse un error en la implementación.</span><span class="sxs-lookup"><span data-stu-id="f40d4-126">Otherwise, the deployment might fail.</span></span>

-   <span data-ttu-id="f40d4-127">La red, incluidos los modificadores y LAN virtuales (VLAN), debe configurarse para que admita PXE.</span><span class="sxs-lookup"><span data-stu-id="f40d4-127">Your network, including switches and virtual LANs (VLANs), should be configured to support PXE.</span></span> <span data-ttu-id="f40d4-128">Consulte a su proveedor de red para obtener más información acerca de la configuración de IP auxiliares y PXE.</span><span class="sxs-lookup"><span data-stu-id="f40d4-128">Refer to your network vendor for more information about IP Helper and PXE configuration.</span></span> <span data-ttu-id="f40d4-129">Como alternativa, puede usar [un medio de arranque](https://docs.microsoft.com/sccm/osd/deploy-use/use-bootable-media-to-deploy-windows-over-the-network) para las implementaciones, si no está habilitado el soporte de PXE.</span><span class="sxs-lookup"><span data-stu-id="f40d4-129">Alternatively, you can use [bootable media](https://docs.microsoft.com/sccm/osd/deploy-use/use-bootable-media-to-deploy-windows-over-the-network) for your deployments, if PXE support isn’t enabled.</span></span>

    > [!NOTE]
    > <span data-ttu-id="f40d4-130">Para Surface Pro dispositivos, arranque desde la red (inicio PXE) sólo se admiten cuando se usa un adaptador Ethernet o estación de acoplamiento de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="f40d4-130">For Surface Pro devices, booting from the network (PXE boot) is only supported when you use an Ethernet adapter or docking station from Microsoft.</span></span> <span data-ttu-id="f40d4-131">Adaptadores de Ethernet de terceros no admiten el arranque PXE con Surface Pro.</span><span class="sxs-lookup"><span data-stu-id="f40d4-131">Third-party Ethernet adapters don’t support PXE boot with Surface Pro.</span></span> <span data-ttu-id="f40d4-132">Para obtener más información, vea [adaptadores Ethernet e implementación de superficie](https://docs.microsoft.com/surface/ethernet-adapters-and-surface-device-deployment) .</span><span class="sxs-lookup"><span data-stu-id="f40d4-132">See [Ethernet adapters and Surface deployment](https://docs.microsoft.com/surface/ethernet-adapters-and-surface-device-deployment) for more information.</span></span>

## <a name="configure-system-center-configuration-manager-for-operating-system-deployment"></a><span data-ttu-id="f40d4-133">Configuración de System Center Configuration Manager para la implementación de sistema operativo</span><span class="sxs-lookup"><span data-stu-id="f40d4-133">Configure System Center Configuration Manager for operating system deployment</span></span>

<span data-ttu-id="f40d4-134">En este artículo se da por supuesto que ya tiene una buen implementación de System Center Configuration Manager y no todos los detalles de todos los pasos necesarios para implementar y configurar el Administrador de configuración desde el principio.</span><span class="sxs-lookup"><span data-stu-id="f40d4-134">This article assumes you already have a healthy System Center Configuration Manager deployment, and doesn’t detail all the steps required to deploy and configure Configuration Manager from scratch.</span></span> <span data-ttu-id="f40d4-135">La [documentación y las instrucciones de configuración](https://docs.microsoft.com/sccm/) de System Center Configuration Manager es un gran recurso; se recomienda que empezar con estos recursos si aún no ha implementado el Administrador de configuración.</span><span class="sxs-lookup"><span data-stu-id="f40d4-135">The [documentation and the configuration guidance](https://docs.microsoft.com/sccm/) on the System Center Configuration Manager is a great resource; we recommend you start with these resources if you haven’t yet deployed Configuration Manager.</span></span>

<span data-ttu-id="f40d4-136">Use las siguientes instrucciones para comprobar que se han configurado correctamente las características de implementación (OSD) del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="f40d4-136">Use the following instructions to verify that the operating system deployment (OSD) features are configured properly.</span></span>

### <a name="validate-and-upgrade-configuration-manager"></a><span data-ttu-id="f40d4-137">Validar y actualizar el Administrador de configuración</span><span class="sxs-lookup"><span data-stu-id="f40d4-137">Validate and upgrade Configuration Manager</span></span>

1.  <span data-ttu-id="f40d4-138">En la consola de Configuration Manager, vaya a **administración** \> **actualizaciones y modelo de servicio**.</span><span class="sxs-lookup"><span data-stu-id="f40d4-138">In the Configuration Manager console, go to **Administration** \> **Updates and Servicing**.</span></span>

2.  <span data-ttu-id="f40d4-139">Compruebe la compilación instalada y actualizaciones aplicables que aún no se han instalado todavía.</span><span class="sxs-lookup"><span data-stu-id="f40d4-139">Check the installed build and applicable updates that haven’t been installed yet.</span></span>

3.  <span data-ttu-id="f40d4-140">Revisión de [compatibilidad con Windows 10 en System Center Configuration Manager](https://docs.microsoft.com/sccm/core/plan-design/configs/support-for-windows-10#windows-10-as-a-client); Si necesita actualizar su implementación, seleccione la actualización que desea instalar y, a continuación, seleccione **Descargar**.</span><span class="sxs-lookup"><span data-stu-id="f40d4-140">Review [Support for Windows 10 in System Center Configuration Manager](https://docs.microsoft.com/sccm/core/plan-design/configs/support-for-windows-10#windows-10-as-a-client); if you need to upgrade your deployment, select the update you want to install, and then select **Download**.</span></span>

4.  <span data-ttu-id="f40d4-141">Una vez finalizada la descarga, seleccione la actualización y, a continuación, seleccione **Instalar el paquete de actualización**.</span><span class="sxs-lookup"><span data-stu-id="f40d4-141">After the download is complete, select the update, and then select **Install Update Pack**.</span></span>

### <a name="configure-distribution-points-to-support-pxe-and-multicast"></a><span data-ttu-id="f40d4-142">Configuración de los puntos de distribución para admitir PXE y multidifusión</span><span class="sxs-lookup"><span data-stu-id="f40d4-142">Configure distribution points to support PXE and multicast</span></span>

1.  <span data-ttu-id="f40d4-143">En la consola de Configuration Manager, vaya a **administración** \> **Puntos de distribución**.</span><span class="sxs-lookup"><span data-stu-id="f40d4-143">In the Configuration Manager console, go to **Administration** \> **Distribution Points**.</span></span>

2.  <span data-ttu-id="f40d4-144">Seleccione el servidor de punto de distribución que va a servir la implementación de sistemas de salón de Skype v2 y, a continuación, seleccione **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="f40d4-144">Select the distribution point server that will serve the Skype Room Systems v2 deployment, and then select **Properties**.</span></span>

3.  <span data-ttu-id="f40d4-145">Seleccione la ficha **PXE** y asegúrese de que estén habilitadas las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="f40d4-145">Select the **PXE** tab, and ensure that the following settings are enabled:</span></span> 
    -   <span data-ttu-id="f40d4-146">Habilitar la compatibilidad con PXE para los clientes</span><span class="sxs-lookup"><span data-stu-id="f40d4-146">Enable PXE support for clients</span></span>
    -   <span data-ttu-id="f40d4-147">Permitir que este punto de distribución responder a las solicitudes de PXE entrantes</span><span class="sxs-lookup"><span data-stu-id="f40d4-147">Allow this distribution point to respond to incoming PXE requests</span></span>
    -   <span data-ttu-id="f40d4-148">Habilitar la compatibilidad con equipo desconocido</span><span class="sxs-lookup"><span data-stu-id="f40d4-148">Enable unknown computer support</span></span>

4.  <span data-ttu-id="f40d4-149">*Opcional:* Para habilitar la compatibilidad con multidifusión, seleccione la ficha **multidifusión** y asegúrese de que estén habilitadas las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="f40d4-149">*Optional:* To enable multicast support, select the **Multicast** tab, and ensure that the following settings are enabled:</span></span>
    -   <span data-ttu-id="f40d4-150">Habilitar la multidifusión enviar datos simultáneamente a varios clientes</span><span class="sxs-lookup"><span data-stu-id="f40d4-150">Enable multicast to simultaneously send data to multiple clients</span></span>
    -   <span data-ttu-id="f40d4-151">Configurar el intervalo de puertos UDP según la recomendación del equipo de su red</span><span class="sxs-lookup"><span data-stu-id="f40d4-151">Configure the UDP port range as per your network team’s recommendation</span></span>

### <a name="configure-the-network-access-account"></a><span data-ttu-id="f40d4-152">Configuración de la cuenta de acceso de red</span><span class="sxs-lookup"><span data-stu-id="f40d4-152">Configure the Network Access Account</span></span>

1.  <span data-ttu-id="f40d4-153">En la consola de Configuration Manager, vaya a **administración** \> **Configuración de sitio** \> **sitios**y, a continuación, seleccione el sitio.</span><span class="sxs-lookup"><span data-stu-id="f40d4-153">In the Configuration Manager console, go to **Administration** \> **Site Configuration** \> **Sites**, and then select the site.</span></span>

2.  <span data-ttu-id="f40d4-154">En el grupo **configuración** , seleccione **Configurar componentes de sitio** \> **La distribución de Software**.</span><span class="sxs-lookup"><span data-stu-id="f40d4-154">In the **Settings** group, select **Configure Site Components** \> **Software Distribution**.</span></span>

3.  <span data-ttu-id="f40d4-155">Seleccione la ficha de la **Cuenta de acceso de red** conjunto de copia de seguridad una o más cuentas y, a continuación, seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="f40d4-155">Select the **Network Access Account** tab. Set up one or more accounts, and then select **OK**.</span></span>

> [!NOTE]
> <span data-ttu-id="f40d4-156">Las cuentas no necesitan ningún derecho en particular, excepto el derecho de **tener acceso a este equipo desde la red** en el servidor de punto de distribución.</span><span class="sxs-lookup"><span data-stu-id="f40d4-156">The accounts don’t need any special rights, except for the **Access this computer from the network** right on the distribution point server.</span></span> <span data-ttu-id="f40d4-157">Una cuenta de usuario de dominio genérico será adecuada.</span><span class="sxs-lookup"><span data-stu-id="f40d4-157">A generic domain user account will be appropriate.</span></span> <span data-ttu-id="f40d4-158">Para obtener más información, consulte [Administrar cuentas para tener acceso al contenido en System Center Configuration Manager](https://docs.microsoft.com/sccm/core/plan-design/hierarchy/manage-accounts-to-access-content#bkmk_NAA).</span><span class="sxs-lookup"><span data-stu-id="f40d4-158">For more information, see [Manage accounts to access content in System Center Configuration Manager](https://docs.microsoft.com/sccm/core/plan-design/hierarchy/manage-accounts-to-access-content#bkmk_NAA).</span></span>

### <a name="configure-a-boot-image"></a><span data-ttu-id="f40d4-159">Configurar una imagen de arranque</span><span class="sxs-lookup"><span data-stu-id="f40d4-159">Configure a boot image</span></span>

1.  <span data-ttu-id="f40d4-160">En la consola de Configuration Manager, vaya a la **Biblioteca de Software** \> **del sistema operativo** \> **Imágenes de arranque**.</span><span class="sxs-lookup"><span data-stu-id="f40d4-160">In the Configuration Manager console, go to **Software Library** \> **Operating System** \> **Boot Images**.</span></span>

2.  <span data-ttu-id="f40d4-161">Seleccione la **imagen de arranque (x64)** y, a continuación, seleccione **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="f40d4-161">Select **Boot image (x64)**, and then select **Properties**.</span></span>

3.  <span data-ttu-id="f40d4-162">Seleccione la ficha **Origen de datos** y permiten **implementar esta imagen de arranque desde el punto de distribución habilitado para PXE**.</span><span class="sxs-lookup"><span data-stu-id="f40d4-162">Select the **Data Source** tab, and enable **Deploy this boot image from the PXE-enabled distribution point**.</span></span>

4.  <span data-ttu-id="f40d4-163">Seleccione la ficha **Componentes opcionales** para instalar los componentes requeridos:</span><span class="sxs-lookup"><span data-stu-id="f40d4-163">Select the **Optional Components** tab to install required components:</span></span>

    1.  <span data-ttu-id="f40d4-164">Seleccione el icono de estrella y buscar **HTML (WinPE-HTA)**</span><span class="sxs-lookup"><span data-stu-id="f40d4-164">Select the star icon, and search for **HTML (WinPE-HTA)**</span></span>

    2.  <span data-ttu-id="f40d4-165">Seleccione **Aceptar** para agregar compatibilidad con la aplicación de HTML en la imagen de arranque.</span><span class="sxs-lookup"><span data-stu-id="f40d4-165">Select **OK** to add HTML application support in to the boot image.</span></span>

5.  <span data-ttu-id="f40d4-166">*Opcional:* Para personalizar la experiencia de implementación, seleccione la ficha **personalización** .</span><span class="sxs-lookup"><span data-stu-id="f40d4-166">*Optional:* To customize the deployment experience, select the **Customization** tab.</span></span>
    -   <span data-ttu-id="f40d4-167">Habilitar **comando admitir (sólo para pruebas)** si desea que tengan acceso a un símbolo del sistema durante la implementación.</span><span class="sxs-lookup"><span data-stu-id="f40d4-167">Enable **command support (testing only)** if you want to have access to a command prompt during the deployment.</span></span> <span data-ttu-id="f40d4-168">Cuando está habilitado, puede iniciar un símbolo del sistema mediante la selección F8 en cualquier momento durante la implementación.</span><span class="sxs-lookup"><span data-stu-id="f40d4-168">When this is enabled, you can         start a command prompt by selecting F8 at any time during the deployment.</span></span>
    -   <span data-ttu-id="f40d4-169">También puede especificar una imagen de fondo personalizada que se mostrará durante la implementación.</span><span class="sxs-lookup"><span data-stu-id="f40d4-169">You can also specify a custom background image to be displayed during the deployment.</span></span> <span data-ttu-id="f40d4-170">Para establecer una imagen, habilite **especificar el archivo de imagen de fondo personalizado (ruta de acceso UNC** y seleccione el fondo.</span><span class="sxs-lookup"><span data-stu-id="f40d4-170">To set an image, enable **Specify the custom background image file (UNC path** and select your background.</span></span>

6.  <span data-ttu-id="f40d4-171">Cuando se le pida, seleccione **Sí** y distribuir la imagen de arranque actualizada a los puntos de distribución.</span><span class="sxs-lookup"><span data-stu-id="f40d4-171">When asked, select **Yes** and distribute the updated boot image to your distribution points.</span></span>

<span data-ttu-id="f40d4-172">Para obtener más información, vea [Administrar imágenes de arranque con System Center Configuration Manager](https://docs.microsoft.com/sccm/osd/get-started/manage-boot-images).</span><span class="sxs-lookup"><span data-stu-id="f40d4-172">For more information, see [Manage boot images with System Center Configuration Manager](https://docs.microsoft.com/sccm/osd/get-started/manage-boot-images).</span></span>

> [!NOTE]
> <span data-ttu-id="f40d4-173">Puede crear un medio de arranque USB para iniciar implementaciones de basado en secuencia de tareas de Configuration Manager para entornos que tienen el soporte PXE.</span><span class="sxs-lookup"><span data-stu-id="f40d4-173">You can create a bootable USB media to initiate Configuration Manager task sequence–based deployments for environments that have no PXE support.</span></span> <span data-ttu-id="f40d4-174">El medio de arranque contiene sólo la imagen de arranque, opcionales prestart comandos y sus archivos necesarios y los archivos binarios de Configuration Manager para admitir el arranque en Windows PE y la conexión para el Administrador de configuración para el resto del proceso de implementación.</span><span class="sxs-lookup"><span data-stu-id="f40d4-174">The bootable media contains only the boot image, optional prestart commands and their required files, and Configuration Manager binaries to support booting into Windows PE and connecting to Configuration Manager for the rest of the deployment process.</span></span> <span data-ttu-id="f40d4-175">Para obtener más información, vea [cómo crear un medio de arranque](https://docs.microsoft.com/sccm/osd/deploy-use/create-bootable-media#BKMK_CreateBootableMedia).</span><span class="sxs-lookup"><span data-stu-id="f40d4-175">For more information, see [How to Create Bootable Media](https://docs.microsoft.com/sccm/osd/deploy-use/create-bootable-media#BKMK_CreateBootableMedia).</span></span>

## <a name="create-configuration-manager-packages"></a><span data-ttu-id="f40d4-176">Crear paquetes de Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="f40d4-176">Create Configuration Manager packages</span></span>

<span data-ttu-id="f40d4-177">Administrador de configuración requiere un número de paquetes para implementar y configurar las unidades de sistema de salas de Skype v2.</span><span class="sxs-lookup"><span data-stu-id="f40d4-177">Configuration Manager requires a number of packages to deploy and configure the Skype Room System v2 units.</span></span>

<span data-ttu-id="f40d4-178">Necesario crear y configurar los siguientes paquetes y, a continuación, distribuirlas a los sistemas de sitio de Configuration Manager que se han asignado el rol de servidor del punto de distribución.</span><span class="sxs-lookup"><span data-stu-id="f40d4-178">You need to create and configure the following packages, and then distribute them to the Configuration Manager site systems that have been assigned the distribution point server role.</span></span>

| <span data-ttu-id="f40d4-179">**Nombre del paquete**</span><span class="sxs-lookup"><span data-stu-id="f40d4-179">**Package name**</span></span>                     | <span data-ttu-id="f40d4-180">**Tipo de**</span><span class="sxs-lookup"><span data-stu-id="f40d4-180">**Type**</span></span>               | <span data-ttu-id="f40d4-181">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="f40d4-181">**Description**</span></span>                                                                        |
|--------------------------------------|------------------------|----------------------------------------------------------------------------------------|
| <span data-ttu-id="f40d4-182">SRS v2 - SRS paquete de la aplicación</span><span class="sxs-lookup"><span data-stu-id="f40d4-182">SRS v2 - SRS Application Package</span></span>     | <span data-ttu-id="f40d4-183">Paquete de software</span><span class="sxs-lookup"><span data-stu-id="f40d4-183">Software package</span></span>       | <span data-ttu-id="f40d4-184">Paquete para el kit de implementación de sistemas de salón de Skype v2</span><span class="sxs-lookup"><span data-stu-id="f40d4-184">Package for the Skype Room Systems v2 deployment kit</span></span>                                   |
| <span data-ttu-id="f40d4-185">SRS v2 - paquete de Sysprep</span><span class="sxs-lookup"><span data-stu-id="f40d4-185">SRS v2 - Sysprep Package</span></span>             | <span data-ttu-id="f40d4-186">Paquete de software</span><span class="sxs-lookup"><span data-stu-id="f40d4-186">Software package</span></span>       | <span data-ttu-id="f40d4-187">Paquete para el Unattended.xml personalizado configurar unidades de v2 de sistemas de salón de Skype</span><span class="sxs-lookup"><span data-stu-id="f40d4-187">Package for the custom Unattended.xml to configure Skype Room Systems v2 units</span></span>         |
| <span data-ttu-id="f40d4-188">SRS v2 - Set-SRSComputerName paquete</span><span class="sxs-lookup"><span data-stu-id="f40d4-188">SRS v2 - Set-SRSComputerName Package</span></span> | <span data-ttu-id="f40d4-189">Paquete de software</span><span class="sxs-lookup"><span data-stu-id="f40d4-189">Software package</span></span>       | <span data-ttu-id="f40d4-190">Paquete de la aplicación HTML (HTA) asignar un nombre de equipo durante la implementación</span><span class="sxs-lookup"><span data-stu-id="f40d4-190">Package for the HTML application (HTA) to assign a computer name during the deployment</span></span> |
| <span data-ttu-id="f40d4-191">Las actualizaciones de SO SRS v2 - paquete</span><span class="sxs-lookup"><span data-stu-id="f40d4-191">SRS v2 - OS Updates Package</span></span>          | <span data-ttu-id="f40d4-192">Paquete de software</span><span class="sxs-lookup"><span data-stu-id="f40d4-192">Software package</span></span>       | <span data-ttu-id="f40d4-193">Paquete de implementación de actualizaciones de sistema operativo obligatorio</span><span class="sxs-lookup"><span data-stu-id="f40d4-193">Package to deploy mandatory operating system updates</span></span>                                   |
| <span data-ttu-id="f40d4-194">SRS v2 - paquete de certificado raíz</span><span class="sxs-lookup"><span data-stu-id="f40d4-194">SRS v2 - Root Certificate Package</span></span>    | <span data-ttu-id="f40d4-195">Paquete de software</span><span class="sxs-lookup"><span data-stu-id="f40d4-195">Software package</span></span>       | <span data-ttu-id="f40d4-196">Paquete para implementar el certificado raíz (no es necesario para las unidades unido a un dominio)</span><span class="sxs-lookup"><span data-stu-id="f40d4-196">Package to deploy the root certificate (not required for domain-joined units)</span></span>          |
| <span data-ttu-id="f40d4-197">SRS v2 - paquete de agente de OMS de Microsoft</span><span class="sxs-lookup"><span data-stu-id="f40d4-197">SRS v2 - Microsoft OMS Agent Package</span></span> | <span data-ttu-id="f40d4-198">Paquete de software</span><span class="sxs-lookup"><span data-stu-id="f40d4-198">Software package</span></span>       | <span data-ttu-id="f40d4-199">Paquete para implementar y configurar al agente de conjunto de aplicaciones de administración de operaciones de Microsoft</span><span class="sxs-lookup"><span data-stu-id="f40d4-199">Package to deploy and configure the Microsoft Operations Management Suite agent</span></span>        |
| <span data-ttu-id="f40d4-200">SRS v2 - WinPE fondo paquete</span><span class="sxs-lookup"><span data-stu-id="f40d4-200">SRS v2 - WinPE Background Package</span></span>    | <span data-ttu-id="f40d4-201">Paquete de software</span><span class="sxs-lookup"><span data-stu-id="f40d4-201">Software package</span></span>       | <span data-ttu-id="f40d4-202">Paquete de la imagen de fondo personalizado usar con imágenes de arranque</span><span class="sxs-lookup"><span data-stu-id="f40d4-202">Package for the custom background image to use with boot images</span></span>                        |
| <span data-ttu-id="f40d4-203">Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="f40d4-203">Windows 10 Enterprise</span></span>                | <span data-ttu-id="f40d4-204">Imagen de sistema operativo</span><span class="sxs-lookup"><span data-stu-id="f40d4-204">Operating system image</span></span> | <span data-ttu-id="f40d4-205">Paquete para el archivo de instalación del sistema operativo (install.wim)</span><span class="sxs-lookup"><span data-stu-id="f40d4-205">Package for the operating system installation file (install.wim)</span></span>                       |
| <span data-ttu-id="f40d4-206">Surface Pro</span><span class="sxs-lookup"><span data-stu-id="f40d4-206">Surface Pro</span></span>                          | <span data-ttu-id="f40d4-207">Paquete de controladores</span><span class="sxs-lookup"><span data-stu-id="f40d4-207">Driver package</span></span>         | <span data-ttu-id="f40d4-208">Paquete para los controladores de dispositivos y el firmware para Microsoft Surface Pro</span><span class="sxs-lookup"><span data-stu-id="f40d4-208">Package for the device drivers and firmware for Microsoft Surface Pro</span></span>                  |
| <span data-ttu-id="f40d4-209">Surface Pro 4</span><span class="sxs-lookup"><span data-stu-id="f40d4-209">Surface Pro 4</span></span>                        | <span data-ttu-id="f40d4-210">Paquete de controladores</span><span class="sxs-lookup"><span data-stu-id="f40d4-210">Driver package</span></span>         | <span data-ttu-id="f40d4-211">Paquete para los controladores de dispositivos y el firmware de Microsoft Surface Pro 4</span><span class="sxs-lookup"><span data-stu-id="f40d4-211">Package for the device drivers and firmware for Microsoft Surface Pro 4</span></span>                |

<span data-ttu-id="f40d4-212">Para obtener más información, vea [paquetes y programas en System Center Configuration Manager](https://docs.microsoft.com/sccm/apps/deploy-use/packages-and-programs).</span><span class="sxs-lookup"><span data-stu-id="f40d4-212">For more information, see [Packages and programs in System Center Configuration Manager](https://docs.microsoft.com/sccm/apps/deploy-use/packages-and-programs).</span></span>

### <a name="create-folders-for-the-package-source-files"></a><span data-ttu-id="f40d4-213">Crear carpetas para el paquete de archivos de origen</span><span class="sxs-lookup"><span data-stu-id="f40d4-213">Create folders for the package source files</span></span>

<span data-ttu-id="f40d4-214">Administrador de configuración requiere que los archivos de origen del paquete a se organizan en una estructura de carpetas específicas cuando se crean en primer lugar y cuando se actualicen.</span><span class="sxs-lookup"><span data-stu-id="f40d4-214">Configuration Manager requires package source files to be organized in a specific folder structure when they’re first created and when they’re updated.</span></span>

<span data-ttu-id="f40d4-215">Cree la siguiente estructura de carpetas en el sitio de administración central de System Center Configuration Manager o el sitio primario, o en un recurso compartido del servidor que está utilizando para los archivos de origen del paquete de host:</span><span class="sxs-lookup"><span data-stu-id="f40d4-215">Create the following folder structure on the System Center Configuration Manager central administration site or primary site, or on a server share you’re using to host package source files:</span></span>

-   <span data-ttu-id="f40d4-216">SRS v2 - paquete de agente de OMS de Microsoft</span><span class="sxs-lookup"><span data-stu-id="f40d4-216">SRS v2 - Microsoft OMS Agent Package</span></span>
-   <span data-ttu-id="f40d4-217">Las actualizaciones de SO SRS v2 - paquete</span><span class="sxs-lookup"><span data-stu-id="f40d4-217">SRS v2 - OS Updates Package</span></span>
-   <span data-ttu-id="f40d4-218">SRS v2 - paquete de certificado raíz</span><span class="sxs-lookup"><span data-stu-id="f40d4-218">SRS v2 - Root Certificate Package</span></span>
-   <span data-ttu-id="f40d4-219">SRS v2 - Set-SRSComputerName paquete</span><span class="sxs-lookup"><span data-stu-id="f40d4-219">SRS v2 - Set-SRSComputerName Package</span></span>
-   <span data-ttu-id="f40d4-220">SRS v2 - SRS paquete de la aplicación</span><span class="sxs-lookup"><span data-stu-id="f40d4-220">SRS v2 - SRS Application Package</span></span>
-   <span data-ttu-id="f40d4-221">SRS v2 - paquete de Sysprep</span><span class="sxs-lookup"><span data-stu-id="f40d4-221">SRS v2 - Sysprep Package</span></span>
-   <span data-ttu-id="f40d4-222">Controladores</span><span class="sxs-lookup"><span data-stu-id="f40d4-222">Drivers</span></span>
    -   <span data-ttu-id="f40d4-223">Surface Pro</span><span class="sxs-lookup"><span data-stu-id="f40d4-223">Surface Pro</span></span>
    -   <span data-ttu-id="f40d4-224">Surface Pro 4</span><span class="sxs-lookup"><span data-stu-id="f40d4-224">Surface Pro 4</span></span>
-   <span data-ttu-id="f40d4-225">Sistemas operativos</span><span class="sxs-lookup"><span data-stu-id="f40d4-225">Operating Systems</span></span>
    -   <span data-ttu-id="f40d4-226">Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="f40d4-226">Windows 10 Enterprise</span></span>

> [!TIP]
> <span data-ttu-id="f40d4-227">También puede [Descargar](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true) y usar el archivo zip que incluye la estructura de carpetas para los paquetes, las secuencias de comandos que se debe usar y la plantilla de secuencia de tareas, que necesita para importar.</span><span class="sxs-lookup"><span data-stu-id="f40d4-227">You may also [download](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true) and use the zip file that includes the folder structure for the packages, the scripts that you need to use, and the task sequence template, that you need to import.</span></span>

### <a name="create-the-microsoft-operations-management-suite-agent-package"></a><span data-ttu-id="f40d4-228">Crear el paquete de agente de conjunto de aplicaciones de administración de operaciones de Microsoft</span><span class="sxs-lookup"><span data-stu-id="f40d4-228">Create the Microsoft Operations Management Suite agent package</span></span>

1.  <span data-ttu-id="f40d4-229">Descargue el agente de X-64 del conjunto de aplicaciones de administración de operaciones de <https://go.microsoft.com/fwlink/?LinkId=828603>.</span><span class="sxs-lookup"><span data-stu-id="f40d4-229">Download the Operations Management Suite X-64 agent from <https://go.microsoft.com/fwlink/?LinkId=828603>.</span></span>

2.  <span data-ttu-id="f40d4-230">Extraer el paquete en la carpeta **SRS v2 - paquete del agente Microsoft OMS** abrir una ventana del símbolo del sistema y **escribir/C: MMASetup-AMD64.exe** en el símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="f40d4-230">Extract the package into the **SRS v2 - Microsoft OMS Agent Package** folder by opening a Command Prompt window and entering **MMASetup-AMD64.exe /C:**     at the command prompt.</span></span>

3.  <span data-ttu-id="f40d4-231">En la consola de Configuration Manager, vaya a la **Biblioteca de Software** \> **Administración de aplicaciones** \> **paquetes**y, a continuación, seleccione **Crear paquete**.</span><span class="sxs-lookup"><span data-stu-id="f40d4-231">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**, and then select **Create Package**.</span></span>

4.  <span data-ttu-id="f40d4-232">Escriba la información siguiente para crear el paquete:</span><span class="sxs-lookup"><span data-stu-id="f40d4-232">Enter the following information to create the package:</span></span>

    -   <span data-ttu-id="f40d4-233">Nombre de **: SRS v2 - paquete del agente de Microsoft OMS**</span><span class="sxs-lookup"><span data-stu-id="f40d4-233">Name **: SRS v2 - Microsoft OMS Agent Package**</span></span>

    -   <span data-ttu-id="f40d4-234">Fabricante **: Microsoft Corporation**</span><span class="sxs-lookup"><span data-stu-id="f40d4-234">Manufacturer **: Microsoft Corporation**</span></span>

    -   <span data-ttu-id="f40d4-235">Versión **: 8.1.11081.0** (especifique la versión del archivo de instalación descargado)</span><span class="sxs-lookup"><span data-stu-id="f40d4-235">Version **: 8.1.11081.0** (enter the version of the downloaded installation file)</span></span>

    -   <span data-ttu-id="f40d4-236">Active la casilla de verificación **este paquete contiene archivos de origen** , escriba la ruta de acceso a la carpeta **SRS v2 - paquete de agente de OMS de Microsoft** y, a continuación, seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="f40d4-236">Select the **This package contains source files** check box, enter the path to the **SRS v2 - Microsoft OMS Agent Package** folder, and then select **Next**.</span></span>

5.  <span data-ttu-id="f40d4-237">Seleccione **no crear un programa**y, a continuación, seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="f40d4-237">Select **Do not create a program**, and then select **Next**.</span></span>

6.  <span data-ttu-id="f40d4-238">Revise la página **Confirmar la configuración** y, a continuación, seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="f40d4-238">Review the **Confirm the settings** page, and then select **Next**.</span></span>

7.  <span data-ttu-id="f40d4-239">Seleccione **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="f40d4-239">Select **Close**.</span></span>

### <a name="create-the-operating-system-updates-package"></a><span data-ttu-id="f40d4-240">Crear el paquete de actualizaciones del sistema operativo</span><span class="sxs-lookup"><span data-stu-id="f40d4-240">Create the operating system updates package</span></span>

1.  <span data-ttu-id="f40d4-241">En la carpeta **SRS v2 - paquete de actualizaciones del sistema operativo** , cree una nueva secuencia de comandos de PowerShell denominado **Install-SRSv2-OS-Updates.ps1**.</span><span class="sxs-lookup"><span data-stu-id="f40d4-241">In the **SRS v2 - OS Updates Package** folder, create a new PowerShell script named **Install-SRSv2-OS-Updates.ps1**.</span></span>

2.  <span data-ttu-id="f40d4-242">Copie la siguiente secuencia de comandos en la secuencia de comandos **Install-SRSv2-OS-Updates.ps1** .</span><span class="sxs-lookup"><span data-stu-id="f40d4-242">Copy the script below into the **Install-SRSv2-OS-Updates.ps1** script.</span></span> <span data-ttu-id="f40d4-243">Como alternativa, puede descargar la secuencia de comandos Install-SRSv2-OS-Updates.ps1 desde [aquí](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true).</span><span class="sxs-lookup"><span data-stu-id="f40d4-243">Alternatively, you can download the Install-SRSv2-OS-Updates.ps1 script from [here](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true).</span></span>
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
3.  <span data-ttu-id="f40d4-244">Descargue los paquetes de actualización de Windows obligatorio en la misma carpeta.</span><span class="sxs-lookup"><span data-stu-id="f40d4-244">Download the mandatory Windows Update packages into the same folder.</span></span>  
    > [!NOTE]
    > <span data-ttu-id="f40d4-245">En el momento en que se publicó este artículo, sólo [KB4056892](http://download.windowsupdate.com/c/msdownload/update/software/secu/2018/01/windows10.0-kb4056892-x64_a41a378cf9ae609152b505c40e691ca1228e28ea.msu) era necesaria.</span><span class="sxs-lookup"><span data-stu-id="f40d4-245">At the time this article was published, only [KB4056892](http://download.windowsupdate.com/c/msdownload/update/software/secu/2018/01/windows10.0-kb4056892-x64_a41a378cf9ae609152b505c40e691ca1228e28ea.msu) was required.</span></span> <span data-ttu-id="f40d4-246">Comprobar [Configure una consola de v2 de Skype salón de sistemas](console.md), para ver si se requiere cualquier otra actualización.</span><span class="sxs-lookup"><span data-stu-id="f40d4-246">Check [Configure a Skype Room Systems v2 console](console.md), to see whether any other updates are required.</span></span>

4.  <span data-ttu-id="f40d4-247">En la consola de Configuration Manager, vaya a la **Biblioteca de Software** \> **Administración de aplicaciones** \> **paquetes**y, a continuación, seleccione **Crear paquete**.</span><span class="sxs-lookup"><span data-stu-id="f40d4-247">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**, and then select **Create Package**.</span></span>

5.  <span data-ttu-id="f40d4-248">Escriba la información siguiente para crear el paquete:</span><span class="sxs-lookup"><span data-stu-id="f40d4-248">Enter the following information to create the package:</span></span>
    -   <span data-ttu-id="f40d4-249">Nombre: **SRS v2 – OS actualiza paquete**</span><span class="sxs-lookup"><span data-stu-id="f40d4-249">Name: **SRS v2 – OS Updates Package**</span></span>
    -   <span data-ttu-id="f40d4-250">Fabricante: **Microsoft Corporation**</span><span class="sxs-lookup"><span data-stu-id="f40d4-250">Manufacturer: **Microsoft Corporation**</span></span>
    -   <span data-ttu-id="f40d4-251">Versión: **versión 1.0.0**</span><span class="sxs-lookup"><span data-stu-id="f40d4-251">Version: **1.0.0**</span></span>
    -   <span data-ttu-id="f40d4-252">Active la casilla de verificación **este paquete contiene archivos de origen** , escriba la ruta de acceso a la carpeta **SRS v2 - paquete de actualizaciones del sistema operativo** y, a continuación, seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="f40d4-252">Select the **This package contains source files** check box, enter the path to the **SRS v2 - OS Updates Package** folder, and then select **Next**.</span></span>

6.  <span data-ttu-id="f40d4-253">Seleccione **no crear un programa**y, a continuación, seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="f40d4-253">Select **Do not create a program**, and then select **Next**.</span></span>

7.  <span data-ttu-id="f40d4-254">Revise la página **Confirmar la configuración** y, a continuación, seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="f40d4-254">Review the **Confirm the settings** page, and then select **Next**.</span></span>

8.  <span data-ttu-id="f40d4-255">Seleccione **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="f40d4-255">Select **Close**.</span></span>

### <a name="create-the-root-certificate-package-optional"></a><span data-ttu-id="f40d4-256">Crear el paquete de certificado raíz (opcional)</span><span class="sxs-lookup"><span data-stu-id="f40d4-256">Create the root certificate package (optional)</span></span>

<span data-ttu-id="f40d4-257">Crear este paquete para distribuir el certificado raíz para dispositivos que no se ha unido a un dominio de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="f40d4-257">You create this package to distribute the root certificate for devices that won’t be joined to an Active Directory domain.</span></span> <span data-ttu-id="f40d4-258">Crear este paquete sólo si se aplican las siguientes condiciones:</span><span class="sxs-lookup"><span data-stu-id="f40d4-258">Create this package only if both the following conditions apply:</span></span>
-   <span data-ttu-id="f40d4-259">La implementación incluye local Lync o Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="f40d4-259">Your deployment includes on-premises Lync or Skype for Business Server.</span></span>
-   <span data-ttu-id="f40d4-260">Unidades de sistemas de salón de Skype v2 se configuran para que funcione en un grupo de trabajo en lugar de un miembro de dominio.</span><span class="sxs-lookup"><span data-stu-id="f40d4-260">Skype Room Systems v2 units are configured to work in a workgroup instead of a domain member.</span></span>

1.  <span data-ttu-id="f40d4-261">Copie el certificado raíz en la carpeta **SRS v2: paquete de certificado raíz** .</span><span class="sxs-lookup"><span data-stu-id="f40d4-261">Copy the root certificate into the **SRS v2 – Root Certificate Package** folder.</span></span>

2.  <span data-ttu-id="f40d4-262">En la consola de Configuration Manager, vaya a la **Biblioteca de Software** \> **Administración de aplicaciones** \> **paquetes**y, a continuación, seleccione **Crear paquete**.</span><span class="sxs-lookup"><span data-stu-id="f40d4-262">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**, and then select **Create Package**.</span></span>

3.  <span data-ttu-id="f40d4-263">Escriba la información siguiente para crear el paquete:</span><span class="sxs-lookup"><span data-stu-id="f40d4-263">Enter the following information to create the package:</span></span>
    -   <span data-ttu-id="f40d4-264">Nombre: **SRS v2: paquete de certificado raíz**</span><span class="sxs-lookup"><span data-stu-id="f40d4-264">Name: **SRS v2 – Root Certificate Package**</span></span>
    -   <span data-ttu-id="f40d4-265">Fabricante: *nombre de la organización*</span><span class="sxs-lookup"><span data-stu-id="f40d4-265">Manufacturer: *Your organization’s name*</span></span>
    -   <span data-ttu-id="f40d4-266">Versión: **versión 1.0.0**</span><span class="sxs-lookup"><span data-stu-id="f40d4-266">Version: **1.0.0**</span></span>
    -   <span data-ttu-id="f40d4-267">Active la casilla de verificación **este paquete contiene archivos de origen** , escriba la ruta de acceso a la carpeta **SRS v2: paquete de certificado raíz** y, a continuación, seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="f40d4-267">Select the **This package contains source files** check box, enter the path to the **SRS v2 – Root Certificate Package** folder, and then select **Next**.</span></span>

4.  <span data-ttu-id="f40d4-268">Seleccione **no crear un programa**y, a continuación, seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="f40d4-268">Select **Do not create a program**, and then select **Next**.</span></span>

5.  <span data-ttu-id="f40d4-269">Revise la página **Confirmar la configuración** y, a continuación, seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="f40d4-269">Review the **Confirm the settings** page, and then select **Next**.</span></span>

6.  <span data-ttu-id="f40d4-270">Seleccione **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="f40d4-270">Select **Close**.</span></span>

### <a name="create-the-skype-room-systems-v2-deployment-kit-package"></a><span data-ttu-id="f40d4-271">Crear el paquete de kit de implementación de sistemas de salón de Skype v2</span><span class="sxs-lookup"><span data-stu-id="f40d4-271">Create the Skype Room Systems v2 deployment kit package</span></span>

1.  <span data-ttu-id="f40d4-272">Descargar la versión más reciente del **kit de implementación de sistemas de salón de Skype v2** de <https://go.microsoft.com/fwlink/?linkid=851168>e instalar una estación de trabajo.</span><span class="sxs-lookup"><span data-stu-id="f40d4-272">Download the latest version of the **Skype Room Systems v2 deployment kit** from <https://go.microsoft.com/fwlink/?linkid=851168>, and install it to a workstation.</span></span>

2.  <span data-ttu-id="f40d4-273">Copie el contenido de **C:\\archivos de programa (x86)\\Kit de implementación de sistema de sala de Skype** a la carpeta **SRS v2 - SRS paquete de la aplicación** .</span><span class="sxs-lookup"><span data-stu-id="f40d4-273">Copy the content from **C:\\Program Files (x86)\\Skype Room System Deployment Kit** to the **SRS v2 - SRS Application Package** folder.</span></span>

3.  <span data-ttu-id="f40d4-274">En la consola de Configuration Manager, vaya a la **Biblioteca de Software** \> **Administración de aplicaciones** \> **paquetes**y, a continuación, seleccione **Crear paquete**.</span><span class="sxs-lookup"><span data-stu-id="f40d4-274">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**, and then select **Create Package**.</span></span>

4.  <span data-ttu-id="f40d4-275">Escriba la información siguiente para crear el paquete:</span><span class="sxs-lookup"><span data-stu-id="f40d4-275">Enter the following information to create the package:</span></span>
    -   <span data-ttu-id="f40d4-276">Nombre: **SRS v2 – paquete de aplicación de SRS**</span><span class="sxs-lookup"><span data-stu-id="f40d4-276">Name: **SRS v2 – SRS Application Package**</span></span>
    -   <span data-ttu-id="f40d4-277">Fabricante: **Microsoft Corporation**</span><span class="sxs-lookup"><span data-stu-id="f40d4-277">Manufacturer: **Microsoft Corporation**</span></span>
    -   <span data-ttu-id="f40d4-278">Versión: **3.1.104.0** (especifique la versión del archivo de instalación descargado)</span><span class="sxs-lookup"><span data-stu-id="f40d4-278">Version: **3.1.104.0** (enter the version of the downloaded installation file)</span></span>
    -   <span data-ttu-id="f40d4-279">Active la casilla de verificación **este paquete contiene archivos de origen** , escriba la ruta de acceso a la carpeta **SRS v2 – SRS paquete de la aplicación** y, a continuación, seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="f40d4-279">Select the **This package contains source files** check box, enter the path to the **SRS v2 – SRS Application Package** folder, and then select **Next**.</span></span>
5.  <span data-ttu-id="f40d4-280">Seleccione **no crear un programa**y, a continuación, seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="f40d4-280">Select **Do not create a program**, and then select **Next**.</span></span>

6.  <span data-ttu-id="f40d4-281">Revise la página **Confirmar la configuración** y, a continuación, seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="f40d4-281">Review the **Confirm the settings** page, and then select **Next**.</span></span>

7.  <span data-ttu-id="f40d4-282">Seleccione **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="f40d4-282">Select **Close**.</span></span>

### <a name="create-the-computer-name-assignment-package"></a><span data-ttu-id="f40d4-283">Crear el paquete de asignación de nombre de equipo</span><span class="sxs-lookup"><span data-stu-id="f40d4-283">Create the computer name assignment package</span></span>

1.  <span data-ttu-id="f40d4-284">En la carpeta **SRS v2 - Set-SRSComputerName paquete** , cree una nueva aplicación de HTML denominada **Set-SRSComputerName.hta** .</span><span class="sxs-lookup"><span data-stu-id="f40d4-284">In the **SRS v2 - Set-SRSComputerName Package** folder, create a new HTML application named **Set-SRSComputerName.hta** .</span></span>

2.  <span data-ttu-id="f40d4-285">Copie la siguiente secuencia de comandos en el archivo **SRSComputerName.hta del conjunto** .</span><span class="sxs-lookup"><span data-stu-id="f40d4-285">Copy the following script into the **Set-SRSComputerName.hta** file.</span></span> <span data-ttu-id="f40d4-286">Como alternativa, puede descargar el archivo de conjunto de SRSComputerName.hta desde [aquí](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true).</span><span class="sxs-lookup"><span data-stu-id="f40d4-286">Alternatively, you can download the Set-SRSComputerName.hta file from [here](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true).</span></span>
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
3.  <span data-ttu-id="f40d4-287">En la consola de Configuration Manager, vaya a la **Biblioteca de Software** \> **Administración de aplicaciones** \> **paquetes**y, a continuación, seleccione **Crear paquete**.</span><span class="sxs-lookup"><span data-stu-id="f40d4-287">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**, and then select **Create Package**.</span></span>

4.  <span data-ttu-id="f40d4-288">Escriba la información siguiente para crear el paquete:</span><span class="sxs-lookup"><span data-stu-id="f40d4-288">Enter the following information to create the package:</span></span>

    -   <span data-ttu-id="f40d4-289">Nombre: **SRS v2 - Set-SRSComputerName paquete**</span><span class="sxs-lookup"><span data-stu-id="f40d4-289">Name: **SRS v2 - Set-SRSComputerName Package**</span></span>

    -   <span data-ttu-id="f40d4-290">Fabricante: **Microsoft Corporation**</span><span class="sxs-lookup"><span data-stu-id="f40d4-290">Manufacturer: **Microsoft Corporation**</span></span>

    -   <span data-ttu-id="f40d4-291">Versión: **versión 1.0.0**</span><span class="sxs-lookup"><span data-stu-id="f40d4-291">Version: **1.0.0**</span></span>

    -   <span data-ttu-id="f40d4-292">Active la casilla de verificación **este paquete contiene archivos de origen** , escriba la ruta de acceso a la carpeta **SRS v2 - Set-SRSComputerName paquete** y, a continuación, seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="f40d4-292">Select the **This package contains source files** check box, enter the path to the **SRS v2 - Set-SRSComputerName Package** folder, and then select **Next**.</span></span>

5.  <span data-ttu-id="f40d4-293">Seleccione **no crear un programa**y, a continuación, seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="f40d4-293">Select **Do not create a program**, and then select **Next**.</span></span>

6.  <span data-ttu-id="f40d4-294">Revise la página **Confirmar la configuración** y, a continuación, seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="f40d4-294">Review the **Confirm the settings** page, and then select **Next**.</span></span>

7.  <span data-ttu-id="f40d4-295">Seleccione **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="f40d4-295">Select **Close**.</span></span>

### <a name="create-the-sysprep-package"></a><span data-ttu-id="f40d4-296">Crear el paquete de Sysprep</span><span class="sxs-lookup"><span data-stu-id="f40d4-296">Create the Sysprep package</span></span>

1.  <span data-ttu-id="f40d4-297">En la carpeta **SRS v2 – paquete de Sysprep** , cree un nuevo archivo XML denominado **Unattend.xml** .</span><span class="sxs-lookup"><span data-stu-id="f40d4-297">In the **SRS v2 – Sysprep Package** folder, create a new XML file named **Unattend.xml** .</span></span>

2.  <span data-ttu-id="f40d4-298">Copie el texto siguiente en el archivo **Unattend.xml** .</span><span class="sxs-lookup"><span data-stu-id="f40d4-298">Copy the following text into the **Unattend.xml** file.</span></span> <span data-ttu-id="f40d4-299">Como alternativa, puede descargar el archivo Unattend.xml desde [aquí](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true).</span><span class="sxs-lookup"><span data-stu-id="f40d4-299">Alternatively, you can download the Unattend.xml file from [here](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true).</span></span>
```
<?xml version="1.0" encoding="utf-8"?>
<unattend xmlns="urn:schemas-microsoft-com:unattend">
    <servicing>
        <package action="configure">
            <assemblyIdentity name="Microsoft-Windows-Foundation-Package" version="10.0.15063.0" processorArchitecture="amd64" publicKeyToken="31bf3856ad364e35" language="" />
            <selection name="Client-DeviceLockdown" state="true" />
            <selection name="Client-EmbeddedLogon" state="true" />
            <selection name="Client-EmbeddedBootExp" state="true" />
            <selection name="Client-EmbeddedShellLauncher" state="true" />
            <selection name="Client-KeyboardFilter" state="true" />
            <selection name="Internet-Explorer-Optional-amd64" state="false" />
            <selection name="MediaPlayback" state="false" />
            <selection name="WindowsMediaPlayer" state="false" />
            <selection name="Xps-Foundation-Xps-Viewer" state="false" />
            <selection name="WorkFolders-Client" state="false" />
            <selection name="SMB1Protocol" state="false" />
            <selection name="SearchEngine-Client-Package" state="false" />
            <selection name="Printing-Foundation-Features" state="false" />
            <selection name="FaxServicesClientPackage" state="false" />
            <selection name="Printing-Foundation-InternetPrinting-Client" state="false" />
            <selection name="Printing-XPSServices-Features" state="false" />
            <selection name="Printing-PrintToPDFServices-Features" state="false" />
            <selection name="Microsoft-Hyper-V-Hypervisor" state="true" />
            <selection name="Microsoft-Hyper-V-All" state="true" />
            <selection name="Microsoft-Hyper-V" state="true" />
        </package>
    </servicing>
    <settings pass="auditSystem">
        <component name="Microsoft-Windows-Shell-Setup" processorArchitecture="amd64" publicKeyToken="31bf3856ad364e35" language="neutral" versionScope="nonSxS" xmlns:wcm="http://schemas.microsoft.com/WMIConfig/2002/State" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
            <AutoLogon>
                <Enabled>true</Enabled>
                <Username>Admin</Username>
                <Password>
                    <Value>cwBmAGIAUABhAHMAcwB3AG8AcgBkAA==</Value>
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
    <settings pass="oobeSystem">
        <component name="Microsoft-Windows-Shell-Setup" processorArchitecture="amd64" publicKeyToken="31bf3856ad364e35" language="neutral" versionScope="nonSxS" xmlns:wcm="http://schemas.microsoft.com/WMIConfig/2002/State" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
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
        </component>
    </settings>
    <cpi:offlineImage cpi:source="wim://com-sccm01/_sources/capture/srscaptured.wim#SRSImage" xmlns:cpi="urn:schemas-microsoft-com:cpi" />
</unattend>
```
3.  <span data-ttu-id="f40d4-300">En la consola de Configuration Manager, vaya a la **Biblioteca de Software** \> **Administración de aplicaciones** \> **paquetes**y, a continuación, seleccione **Crear paquete**.</span><span class="sxs-lookup"><span data-stu-id="f40d4-300">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**, and then select **Create Package**.</span></span>

4.  <span data-ttu-id="f40d4-301">Escriba la información siguiente para crear el paquete:</span><span class="sxs-lookup"><span data-stu-id="f40d4-301">Enter the following information to create the package:</span></span>
    -   <span data-ttu-id="f40d4-302">Nombre: **SRS v2 - paquete de Sysprep**</span><span class="sxs-lookup"><span data-stu-id="f40d4-302">Name: **SRS v2 - Sysprep Package**</span></span>
    -   <span data-ttu-id="f40d4-303">Fabricante: **Microsoft Corporation**</span><span class="sxs-lookup"><span data-stu-id="f40d4-303">Manufacturer: **Microsoft Corporation**</span></span>
    -   <span data-ttu-id="f40d4-304">Versión: **versión 1.0.0**</span><span class="sxs-lookup"><span data-stu-id="f40d4-304">Version: **1.0.0**</span></span>
    -   <span data-ttu-id="f40d4-305">Active la casilla de verificación **este paquete contiene archivos de origen** , escriba la ruta de acceso a la carpeta **SRS v2 – paquete de Sysprep** y, a continuación, seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="f40d4-305">Select the **This package contains source files** check box, enter the path to the **SRS v2 – Sysprep Package** folder, and then select **Next**.</span></span>
5.  <span data-ttu-id="f40d4-306">Seleccione **no crear un programa**y, a continuación, seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="f40d4-306">Select **Do not create a program**, and then select **Next**.</span></span>

6.  <span data-ttu-id="f40d4-307">Revise la página **Confirmar la configuración** y, a continuación, seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="f40d4-307">Review the **Confirm the settings** page, and then select **Next**.</span></span>

7.  <span data-ttu-id="f40d4-308">Seleccione **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="f40d4-308">Select **Close**.</span></span>

### <a name="create-the-windows-10-enterprise-package"></a><span data-ttu-id="f40d4-309">Crear el paquete de Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="f40d4-309">Create the Windows 10 Enterprise package</span></span>

1.  <span data-ttu-id="f40d4-310">Obtener una media de Windows 10 Enterprise x64 y copie el archivo **install.wim** para el **sistemas operativos\\Windows 10 Enterprise** carpeta.</span><span class="sxs-lookup"><span data-stu-id="f40d4-310">Obtain a Windows 10 Enterprise x64 media, and copy the **install.wim** file to the **Operating Systems\\Windows 10 Enterprise** folder.</span></span>

2.  <span data-ttu-id="f40d4-311">En la consola de Configuration Manager, vaya a la **Biblioteca de Software** \> **sistemas operativos** \> **Imágenes del sistema operativo**y, a continuación, seleccione **Agregar imagen de sistema operativo**.</span><span class="sxs-lookup"><span data-stu-id="f40d4-311">In the Configuration Manager console, go to **Software Library** \> **Operating Systems** \> **Operating System Images**, and then select **Add Operating System Image**.</span></span>

3.  <span data-ttu-id="f40d4-312">Especifique la ruta de acceso al archivo **install.wim** que acaba de copiar y, a continuación, seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="f40d4-312">Specify the path to the **install.wim** file you just copied, and then select **Next**.</span></span>

4.  <span data-ttu-id="f40d4-313">Actualice el campo de **versión** para que coincida con el número de compilación de la imagen de Windows 10 Enterprise y, a continuación, seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="f40d4-313">Update the **Version** field to match the build number of the Windows 10 Enterprise image, and then select **Next**.</span></span>

5.  <span data-ttu-id="f40d4-314">Revise la página de **Detalles** y, a continuación, seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="f40d4-314">Review the **Details** page, and then select **Next**.</span></span>

6.  <span data-ttu-id="f40d4-315">Seleccione **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="f40d4-315">Select **Close**.</span></span>

<span data-ttu-id="f40d4-316">Para obtener más información, vea [Administrar imágenes del sistema operativo con System Center Configuration Manager](https://docs.microsoft.com/sccm/osd/get-started/manage-operating-system-images).</span><span class="sxs-lookup"><span data-stu-id="f40d4-316">For more information, see [Manage operating system images with System Center Configuration Manager](https://docs.microsoft.com/sccm/osd/get-started/manage-operating-system-images).</span></span>

### <a name="create-surface-pro-device-driver-packages"></a><span data-ttu-id="f40d4-317">Crear paquetes de controladores de dispositivo Surface Pro</span><span class="sxs-lookup"><span data-stu-id="f40d4-317">Create Surface Pro device driver packages</span></span>

<span data-ttu-id="f40d4-318">Es compatible con sistemas de salas de Skype v2 Surface Pro y Surface Pro 4.</span><span class="sxs-lookup"><span data-stu-id="f40d4-318">Skype Room Systems v2 is supported for both Surface Pro and Surface Pro 4.</span></span> <span data-ttu-id="f40d4-319">Debe crear un paquete de controlador para cada modelo Surface Pro que tiene en su entorno.</span><span class="sxs-lookup"><span data-stu-id="f40d4-319">You need to create a driver package for each Surface Pro model you have in your environment.</span></span>

1.  <span data-ttu-id="f40d4-320">Descargue los controladores y el firmware más reciente.</span><span class="sxs-lookup"><span data-stu-id="f40d4-320">Download the latest drivers and firmware.</span></span>
    -   <span data-ttu-id="f40d4-321">Para Surface Pro:<https://www.microsoft.com/download/details.aspx?id=55484></span><span class="sxs-lookup"><span data-stu-id="f40d4-321">For Surface Pro: <https://www.microsoft.com/download/details.aspx?id=55484></span></span>
    -   <span data-ttu-id="f40d4-322">Para Surface Pro 4:<https://www.microsoft.com/download/details.aspx?id=49498></span><span class="sxs-lookup"><span data-stu-id="f40d4-322">For Surface Pro 4: <https://www.microsoft.com/download/details.aspx?id=49498></span></span>
> [!IMPORTANT]
> <span data-ttu-id="f40d4-323">Los controladores deben ser compatibles con la compilación de Windows 10 Enterprise y la versión de kit de implementación de sistemas de salón de Skype v2.</span><span class="sxs-lookup"><span data-stu-id="f40d4-323">The drivers must be compatible with the Windows 10 Enterprise build and the Skype Room Systems v2 deployment kit version.</span></span> <span data-ttu-id="f40d4-324">Para obtener más información, vea [descargar el firmware más reciente y los controladores para dispositivos superficiales](https://docs.microsoft.com/surface/deploy-the-latest-firmware-and-drivers-for-surface-devices).</span><span class="sxs-lookup"><span data-stu-id="f40d4-324">For more information, see [Download the latest firmware and drivers for Surface devices](https://docs.microsoft.com/surface/deploy-the-latest-firmware-and-drivers-for-surface-devices).</span></span>
2.  <span data-ttu-id="f40d4-325">Extraiga el controlador descargado y firmware.</span><span class="sxs-lookup"><span data-stu-id="f40d4-325">Extract the downloaded driver and firmware.</span></span> <span data-ttu-id="f40d4-326">Abra una ventana del símbolo del sistema y en el símbolo del sistema, escriba uno de los siguientes comandos:</span><span class="sxs-lookup"><span data-stu-id="f40d4-326">Open a Command Prompt window and at the command prompt, enter one of the following commands:</span></span>
    -   `msiexec /a C:\SurfacePro_Win10.msi /passive TARGETDIR="C:\_Sources\\Drivers\Surface Pro"`
    -   `msiexec /a C:\SurfacePro4_Win10.msi /passive TARGETDIR="C:\_Sources\\Drivers\Surface Pro 4"`

3.  <span data-ttu-id="f40d4-327">En la consola de Configuration Manager, vaya a la **Biblioteca de Software** \> **sistemas operativos** \> **controladores**y, a continuación, seleccione **El controlador de importación**.</span><span class="sxs-lookup"><span data-stu-id="f40d4-327">In the Configuration Manager console, go to **Software Library** \> **Operating Systems** \> **Drivers**, and then select **Import Driver**.</span></span>

4.  <span data-ttu-id="f40d4-328">Seleccione **importar todos los controladores en la siguiente ruta de acceso de red (UNC)**, seleccione la carpeta de origen (por ejemplo, C:\\_Sources\\controladores\\Surface Pro) y, a continuación, seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="f40d4-328">Select **Import all drivers in the following network path (UNC)**, select the source folder (for example, C:\\_Sources\\Drivers\\Surface Pro), and then select **Next**.</span></span>

5.  <span data-ttu-id="f40d4-329">En la página **especificar los detalles de los controladores importados** , seleccione todos los controladores enumerados y, a continuación, seleccione **Habilitar a estos controladores y permitir que los equipos de instalarlas**.</span><span class="sxs-lookup"><span data-stu-id="f40d4-329">On the **Specify the details for the imported drivers** page, select all the listed drivers, and then select **Enable these drivers and allow computers to install them**.</span></span>

6.  <span data-ttu-id="f40d4-330">Seleccionar **las categorías**, crear una nueva categoría que coincide con el modelo de superficie, haga **clic en Aceptar**y, a continuación, seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="f40d4-330">Select **Categories**, create a new category that matches the Surface model, select **OK**, and then select **Next**.</span></span>

7.  <span data-ttu-id="f40d4-331">Seleccione **nuevo paquete**.</span><span class="sxs-lookup"><span data-stu-id="f40d4-331">Select **New Package**.</span></span>

8.  <span data-ttu-id="f40d4-332">Especificar el nombre del paquete que coincide con el modelo Surface Pro, escriba una ruta de acceso de carpeta para almacenar los archivos de paquete del controlador en, seleccione **Aceptar**y, a continuación, seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="f40d4-332">Specify the package name that matches the Surface Pro model, enter a folder path to store the driver package files in, select **OK**, and then select **Next**.</span></span>

9.  <span data-ttu-id="f40d4-333">En la página de **imágenes de arranque** , asegúrese de que ninguna imagen de arranque está seleccionada y, a continuación, seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="f40d4-333">On the **boot images** page, ensure that no boot images are selected, and then select **Next**.</span></span>

10. <span data-ttu-id="f40d4-334">Seleccione **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="f40d4-334">Select **Close**.</span></span>

11. <span data-ttu-id="f40d4-335">Vaya a la **Biblioteca de Software** \> **sistemas operativos** \> **controladores**, seleccione **carpeta \> crear carpeta**y especifique un nombre de carpeta que coincide con el modelo Surface Pro que acaba de importar los controladores para.</span><span class="sxs-lookup"><span data-stu-id="f40d4-335">Go to **Software Library** \> **Operating Systems** \> **Drivers**, select **Folder \> Create Folder**, and enter a folder name that matches the Surface Pro model that you just imported the drivers for.</span></span>

12. <span data-ttu-id="f40d4-336">Mover todos los controladores importados a la carpeta recién creada para que sea más fácil navegación y operación.</span><span class="sxs-lookup"><span data-stu-id="f40d4-336">Move all the imported drivers to the newly created folder for easier navigation and operation.</span></span>

> [!NOTE]
> <span data-ttu-id="f40d4-337">Repita los mismos pasos para otros modelos Surface Pro, es posible que deba.</span><span class="sxs-lookup"><span data-stu-id="f40d4-337">Repeat the same steps for other Surface Pro models you might have.</span></span> <span data-ttu-id="f40d4-338">Para obtener más información, vea [Administrar controladores en System Center Configuration Manager](https://docs.microsoft.com/sccm/osd/get-started/manage-drivers).</span><span class="sxs-lookup"><span data-stu-id="f40d4-338">For more information, see [Manage drivers in System Center Configuration Manager](https://docs.microsoft.com/sccm/osd/get-started/manage-drivers).</span></span>

## <a name="distribute-configuration-manager-packages"></a><span data-ttu-id="f40d4-339">Distribuir los paquetes de Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="f40d4-339">Distribute Configuration Manager packages</span></span>

<span data-ttu-id="f40d4-340">Todos los paquetes se deben distribuir a los servidores que se han asignado la función de punto de distribución en la jerarquía de Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="f40d4-340">All the packages must be distributed to the servers that have been assigned the distribution point role in the Configuration Manager hierarchy.</span></span> <span data-ttu-id="f40d4-341">Siga las instrucciones siguientes para iniciar la distribución de paquetes.</span><span class="sxs-lookup"><span data-stu-id="f40d4-341">Follow the instructions below to initiate package distribution.</span></span>

1.  <span data-ttu-id="f40d4-342">Distribuir paquetes de software.</span><span class="sxs-lookup"><span data-stu-id="f40d4-342">Distribute software packages.</span></span>

    1.  <span data-ttu-id="f40d4-343">En la consola de Configuration Manager, vaya a la **Biblioteca de Software** \> **Administración de aplicaciones** \> **paquetes**.</span><span class="sxs-lookup"><span data-stu-id="f40d4-343">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**.</span></span> <span data-ttu-id="f40d4-344">Seleccione todos los paquetes de software que desea distribuir y, a continuación, seleccione **Distribuir contenido**.</span><span class="sxs-lookup"><span data-stu-id="f40d4-344">Select all the software packages you want to distribute, and then select **Distribute Content**.</span></span>

    2.  <span data-ttu-id="f40d4-345">Revise la lista de paquetes y, a continuación, seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="f40d4-345">Review the list of packages, and then select **Next**.</span></span>

    3.  <span data-ttu-id="f40d4-346">Agregar todos los servidores de punto de distribución (o grupos de puntos de distribución, dependiendo de la jerarquía de Configuration Manager) a la lista y, a continuación, seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="f40d4-346">Add all the distribution point servers (or distribution point groups, depending on your Configuration Manager hierarchy) to the list, and then select **Next**.</span></span>

    4.  <span data-ttu-id="f40d4-347">Seleccione **siguiente**y, a continuación, seleccione **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="f40d4-347">Select **Next**, and then select **Close**.</span></span>

2.  <span data-ttu-id="f40d4-348">Distribuir paquetes de controladores.</span><span class="sxs-lookup"><span data-stu-id="f40d4-348">Distribute driver packages.</span></span>

    1.  <span data-ttu-id="f40d4-349">En la consola de Configuration Manager, vaya a la **Biblioteca de Software** \> **sistemas operativos** \> **Paquetes de controladores**.</span><span class="sxs-lookup"><span data-stu-id="f40d4-349">In the Configuration Manager console, go to **Software Library** \> **Operating Systems** \> **Driver Packages**.</span></span> <span data-ttu-id="f40d4-350">Seleccione todos los paquetes de controlador que desea distribuir y, a continuación, seleccione **Distribuir contenido**.</span><span class="sxs-lookup"><span data-stu-id="f40d4-350">Select all the driver packages you want to distribute, and then select **Distribute Content**.</span></span>

    2.  <span data-ttu-id="f40d4-351">Revise la lista de paquetes y, a continuación, seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="f40d4-351">Review the list of packages, and then select **Next**.</span></span>

    3.  <span data-ttu-id="f40d4-352">Agregar todos los servidores de punto de distribución (o grupos de puntos de distribución, dependiendo de la jerarquía de Configuration Manager) a la lista y, a continuación, seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="f40d4-352">Add all the distribution point servers (or distribution point groups, depending on your Configuration Manager hierarchy) to the list, and then select **Next**.</span></span>

    4.  <span data-ttu-id="f40d4-353">Seleccione **siguiente**y, a continuación, seleccione **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="f40d4-353">Select **Next**, and then select **Close**.</span></span>

3.  <span data-ttu-id="f40d4-354">Distribuir los paquetes de sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="f40d4-354">Distribute operating system packages.</span></span>

    1.  <span data-ttu-id="f40d4-355">En la consola de Configuration Manager, vaya a la **Biblioteca de Software** \> **sistemas operativos** \> **Imágenes del sistema operativo**.</span><span class="sxs-lookup"><span data-stu-id="f40d4-355">In the Configuration Manager console, go to **Software Library** \> **Operating Systems** \> **Operating System Images**.</span></span> <span data-ttu-id="f40d4-356">Seleccione todas las imágenes de sistema operativo que desea distribuir y, a continuación, seleccione **Distribuir contenido**.</span><span class="sxs-lookup"><span data-stu-id="f40d4-356">Select all the operating system images you want to distribute, and then select **Distribute Content**.</span></span>

    2.  <span data-ttu-id="f40d4-357">Revise la lista de paquetes y, a continuación, seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="f40d4-357">Review the list of packages, and then select **Next**.</span></span>

    3.  <span data-ttu-id="f40d4-358">Agregar todos los servidores de punto de distribución (o grupos de puntos de distribución, dependiendo de la jerarquía de Configuration Manager) a la lista y, a continuación, seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="f40d4-358">Add all the distribution point servers (or distribution point groups, depending on your Configuration Manager hierarchy) to the list, and then select **Next**.</span></span>

    4.  <span data-ttu-id="f40d4-359">Seleccione **siguiente**y, a continuación, seleccione **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="f40d4-359">Select **Next**, and then select **Close**.</span></span>

> [!NOTE]
> <span data-ttu-id="f40d4-360">Paquete de distribución puede tardar algún tiempo, según el tamaño del paquete, jerarquía de Configuration Manager, número de servidores de punto de distribución y el ancho de banda disponible en la red.</span><span class="sxs-lookup"><span data-stu-id="f40d4-360">Package distribution might take some time, depending on the package size, Configuration Manager hierarchy, number of distribution point servers, and the bandwidth available in your network.</span></span>

> <span data-ttu-id="f40d4-361">Todos los paquetes deben distribuirse antes de empezar a implementar una unidad de v2 de sistemas de salón de Skype.</span><span class="sxs-lookup"><span data-stu-id="f40d4-361">All the packages must be distributed before you can start deploying a Skype Room Systems v2 unit.</span></span>

> <span data-ttu-id="f40d4-362">Puede revisar el estado de la distribución de paquetes en la consola de Configuration Manager, vaya a **supervisión** \> **Estado de distribución** \> **Estado del contenido**.</span><span class="sxs-lookup"><span data-stu-id="f40d4-362">You can review the status of your package distribution in the Configuration Manager console by going to **Monitoring** \> **Distribution Status** \> **Content Status**.</span></span>

## <a name="configuration-manager-task-sequences"></a><span data-ttu-id="f40d4-363">Secuencias de tareas de Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="f40d4-363">Configuration Manager task sequences</span></span>

<span data-ttu-id="f40d4-364">Utilice las secuencias de tareas con System Center Configuration Manager para automatizar los pasos para implementar una imagen de sistema operativo en un equipo de destino.</span><span class="sxs-lookup"><span data-stu-id="f40d4-364">You use task sequences with System Center Configuration Manager to automate the steps for deploying an operating system image to a destination computer.</span></span> <span data-ttu-id="f40d4-365">Para implementar una unidad de v2 de sistemas de salón de Skype en forma automática, se crea una secuencia de tareas que hace referencia a la imagen de arranque se usa para iniciar el equipo de destino v2 de sistemas de salón de Skype, la imagen del sistema operativo Windows 10 Enterprise que desea instalar y cualquiera otro contenido adicional, como otras aplicaciones o actualizaciones de software.</span><span class="sxs-lookup"><span data-stu-id="f40d4-365">To deploy a Skype Room Systems v2 unit in an automated fashion, you create a task sequence that references the boot image used to start the destination Skype Room Systems v2 computer, the Windows 10 Enterprise operating system image that you want to install, and any other additional content, such as other applications or software updates.</span></span>

### <a name="import-the-sample-task-sequence"></a><span data-ttu-id="f40d4-366">Importación de la secuencia de tareas de ejemplo</span><span class="sxs-lookup"><span data-stu-id="f40d4-366">Import the sample task sequence</span></span>

<span data-ttu-id="f40d4-367">Puede descargar y fácilmente importar una secuencia de tareas de ejemplo y personalícelo para satisfacer sus necesidades.</span><span class="sxs-lookup"><span data-stu-id="f40d4-367">You can download and easily import a sample task sequence and customize it to meet your needs.</span></span>

1.  <span data-ttu-id="f40d4-368">[**Descargue**]() el ejemplo de secuencia de tareas y copie el archivo zip descargado en una ubicación compartida.</span><span class="sxs-lookup"><span data-stu-id="f40d4-368">[**Download**]() the sample task sequence, and copy the downloaded zip file to a shared location.</span></span>
2.  <span data-ttu-id="f40d4-369">En la consola de Configuration Manager, vaya a la **Biblioteca de Software** \> **sistemas operativos** \> **Secuencias de tareas**y, a continuación, seleccione **Importar secuencia de tareas**.</span><span class="sxs-lookup"><span data-stu-id="f40d4-369">In the Configuration Manager console, go to **Software Library** \> **Operating Systems** \> **Task Sequences**, and then select **Import Task Sequence**.</span></span>

3.  <span data-ttu-id="f40d4-370">Seleccione **Examinar**, vaya a la ubicación de la carpeta compartida que utilizó en el paso 1, seleccione el archivo **.zip de implementación (EN-US) v2 de Skype salón de sistemas** y, a continuación, seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="f40d4-370">Select **Browse**, go to the shared folder location you used in step 1, select the **Skype Room Systems v2 Deployment (EN-US).zip** file, and then select **Next**.</span></span>

4.  <span data-ttu-id="f40d4-371">Establecer la **acción** para **Crear nuevo**y, a continuación, seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="f40d4-371">Set **Action** to **Create New**, and then select **Next**.</span></span>

5.  <span data-ttu-id="f40d4-372">Confirmar la configuración y, a continuación, seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="f40d4-372">Confirm the settings, and then select **Next**.</span></span>

6.  <span data-ttu-id="f40d4-373">Seleccione **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="f40d4-373">Select **Close**.</span></span>

### <a name="validate-that-the-reference-packages-are-correctly-linked-to-each-task-sequence-step"></a><span data-ttu-id="f40d4-374">Validar que los paquetes de referencia correctamente están vinculados a cada paso de la secuencia de tareas.</span><span class="sxs-lookup"><span data-stu-id="f40d4-374">Validate that the reference packages are correctly linked to each task sequence step.</span></span>

1.  <span data-ttu-id="f40d4-375">Seleccione la secuencia de tareas importadas y, a continuación, seleccione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="f40d4-375">Select the imported task sequence, and then select **Edit**.</span></span>

     <span data-ttu-id="f40d4-376">El Editor de secuencia de tareas se abre y muestra cada paso secuencial que necesita para implementar y configurar una unidad de v2 de sistemas de salón de Skype.</span><span class="sxs-lookup"><span data-stu-id="f40d4-376">The Task Sequence Editor opens and displays each sequential step that you need to deploy and configure a Skype Room Systems v2 unit.</span></span>

1.  <span data-ttu-id="f40d4-377">Recorra cada paso y completar las actualizaciones recomendadas:</span><span class="sxs-lookup"><span data-stu-id="f40d4-377">Walk through each step and complete the recommended updates:</span></span>

    1.  <span data-ttu-id="f40d4-378">**Reiniciar en Windows PE**: en este paso se reinicia y, a continuación, se inicia el equipo en PXE de Windows.</span><span class="sxs-lookup"><span data-stu-id="f40d4-378">**Restart in Windows PE**: This step restarts and then boots the computer into Windows PXE.</span></span> <span data-ttu-id="f40d4-379">No hay cambios son necesarios para este paso.</span><span class="sxs-lookup"><span data-stu-id="f40d4-379">No changes are required for this step.</span></span>

    2.  <span data-ttu-id="f40d4-380">**Partición disco 0 – UEFI**: este paso elimina la configuración de disco y crea particiones en función de la configuración establecida.</span><span class="sxs-lookup"><span data-stu-id="f40d4-380">**Partition Disk 0 – UEFI**: This step wipes the disk configuration and creates partitions based on the configured settings.</span></span> <span data-ttu-id="f40d4-381">Se recomienda que no realice ningún cambio para este paso.</span><span class="sxs-lookup"><span data-stu-id="f40d4-381">We recommend that you not make any changes to this step.</span></span>

    3.  <span data-ttu-id="f40d4-382">**Establecer el nombre de equipo de SRS**: este paso incluye una aplicación HTML para proporcionar una interfaz de usuario para establecer un nombre de equipo para la unidad de v2 de sistemas de salón de Skype durante la implementación.</span><span class="sxs-lookup"><span data-stu-id="f40d4-382">**Set SRS Computer Name**: This step includes an HTML application to provide a UI to set a computer name for the Skype Room Systems v2 unit during the deployment.</span></span>
        -  <span data-ttu-id="f40d4-383">Éste es un paso opcional, pero solo puede deshabilitarse si desea administrar a través de un proceso alternativo de nombre del equipo.</span><span class="sxs-lookup"><span data-stu-id="f40d4-383">This is an optional step, but it can only be disabled if you want to manage computer naming through an alternate process.</span></span>
        -  <span data-ttu-id="f40d4-384">Compruebe que esté seleccionado el paquete **SRS v2 - Set-SRSComputerName** .</span><span class="sxs-lookup"><span data-stu-id="f40d4-384">Verify that the **SRS v2 - Set-SRSComputerName** package is selected.</span></span> <span data-ttu-id="f40d4-385">Si no es así, vaya al paquete y selecciónelo.</span><span class="sxs-lookup"><span data-stu-id="f40d4-385">If it isn’t, browse to the package and select it.</span></span>

    4.  <span data-ttu-id="f40d4-386">**Aplicar sistema operativo**: este paso especifica la imagen de sistema operativo que se va a implementar y el archivo de respuesta Sysprep desatendido para usar.</span><span class="sxs-lookup"><span data-stu-id="f40d4-386">**Apply Operating System**: This step specifies the operating system image to be deployed and the unattended Sysprep answer file to use.</span></span>
        -  <span data-ttu-id="f40d4-387">Compruebe que el archivo de imagen de sistema operativo Windows 10 Enterprise correcto está seleccionado.</span><span class="sxs-lookup"><span data-stu-id="f40d4-387">Verify that the correct Windows 10 Enterprise operating system image file is selected.</span></span>
        -  <span data-ttu-id="f40d4-388">Compruebe que está habilitado el **archivo de respuesta de Sysprep para una instalación personalizada o utilice una instalación desatendida** y se selecciona el **SRS v2 - paquete de Sysprep** .</span><span class="sxs-lookup"><span data-stu-id="f40d4-388">Verify that **Use an unattended or Sysprep answer file for a custom installation** is enabled, and the **SRS v2 - Sysprep Package** is selected.</span></span> <span data-ttu-id="f40d4-389">Asegúrese también de que el **Nombre de archivo** está establecido en **unattend.xml**.</span><span class="sxs-lookup"><span data-stu-id="f40d4-389">Also ensure that **File Name** is set to **unattend.xml**.</span></span>

    5.  <span data-ttu-id="f40d4-390">**Aplicar la configuración de Windows**: este paso recopila información acerca de la instalación de Windows.</span><span class="sxs-lookup"><span data-stu-id="f40d4-390">**Apply Windows Settings**: This step gathers information about the Windows installation.</span></span>
        -  <span data-ttu-id="f40d4-391">Proporcionar información de licencias y el registro incluida la clave de producto, contraseña de la cuenta de administrador local y la zona horaria (según sus necesidades).</span><span class="sxs-lookup"><span data-stu-id="f40d4-391">Provide licensing and registration information including the product key, local administrator account password, and time zone (depending on your needs).</span></span>

    6.  <span data-ttu-id="f40d4-392">**Aplicar la configuración de red**: este paso permite especificar un grupo de trabajo o el nombre de dominio de Active Directory y la unidad organizativa.</span><span class="sxs-lookup"><span data-stu-id="f40d4-392">**Apply Network Settings**: This step allows you to specify a workgroup or Active Directory domain name and organizational unit.</span></span>

    7.  <span data-ttu-id="f40d4-393">**Aplicar controladores:** Este paso y sus subpasos se usan para implementar controladores de dispositivo aplicables y firmware basada en el modelo Surface Pro que tiene.</span><span class="sxs-lookup"><span data-stu-id="f40d4-393">**Apply Drivers:** This step and its sub-steps are used to deploy applicable device drivers and firmware based on the Surface Pro model you have.</span></span> <span data-ttu-id="f40d4-394">Actualizar cada paso para especificar el paquete de controladores relevantes asociado con esta implementación.</span><span class="sxs-lookup"><span data-stu-id="f40d4-394">Update each step to specify the relevant driver package associated with this deployment.</span></span>
        -   <span data-ttu-id="f40d4-395">Cada paquete de controlador está configurado para sacar provecho de los filtros de Instrumental de administración de Windows (WMI) para implementar los controladores relevantes y marca y modelo de firmware según la Surface Pro.</span><span class="sxs-lookup"><span data-stu-id="f40d4-395">Each driver package is configured to leverage Windows Management Instrumentation (WMI) filters to deploy relevant drivers and firmware based on the Surface Pro make and model.</span></span>
        -   <span data-ttu-id="f40d4-396">Se recomienda encarecidamente que no se modifique la configuración de estos controladores, en caso contrario, puede producirse un error de implementación.</span><span class="sxs-lookup"><span data-stu-id="f40d4-396">We highly recommend that you not alter the configuration of these drivers, otherwise deployment might fail.</span></span>

    8.  <span data-ttu-id="f40d4-397">**Configurar Windows y el Administrador de configuración**: este paso se implementa y se configura el cliente del Administrador de configuración.</span><span class="sxs-lookup"><span data-stu-id="f40d4-397">**Set up Windows and Configuration Manager**: This step deploys and configures the Configuration Manager client.</span></span> <span data-ttu-id="f40d4-398">Actualizar este paso para especificar el paquete de cliente de Configuration Manager integradas.</span><span class="sxs-lookup"><span data-stu-id="f40d4-398">Update this step to specify the built-in Configuration Manager Client Package.</span></span>

    9.  <span data-ttu-id="f40d4-399">**Instalar el certificado de raíz**: en este paso se distribuye el certificado raíz para dispositivos que no pertenecen a un dominio y, por lo tanto, es opcional.</span><span class="sxs-lookup"><span data-stu-id="f40d4-399">**Install Root Certificate**: This step distributes the root certificate for non–domain-joined devices, and therefore is optional.</span></span>
        -   <span data-ttu-id="f40d4-400">Quitar o deshabilitar este paso si no es necesario implementar un certificado raíz para las unidades de v2 de sistemas de salón de Skype.</span><span class="sxs-lookup"><span data-stu-id="f40d4-400">Remove or disable this step if you don’t need to deploy a root certificate to the Skype Room Systems v2 units.</span></span>
        -   <span data-ttu-id="f40d4-401">Si es necesario realizar este paso, compruebe que esté seleccionado el **SRS v2: paquete de certificado raíz** .</span><span class="sxs-lookup"><span data-stu-id="f40d4-401">If you do need to perform this step, verify that the **SRS v2 – Root Certificate Package** is selected.</span></span>

    10. <span data-ttu-id="f40d4-402">**Instalar y configurar el agente de OMS**: este paso instala la versión de 64 bits del agente de conjunto de aplicaciones de administración de operaciones de Microsoft y configura el agente para conectarse a su área de trabajo de análisis de registro.</span><span class="sxs-lookup"><span data-stu-id="f40d4-402">**Install and Configure OMS Agent**: This step installs the 64-bit version of the Microsoft Operations Management Suite agent and configures the agent to connect to your Log Analytics workspace.</span></span>
        -   <span data-ttu-id="f40d4-403">Deshabilitar este paso únicamente si va a utilizar algunas otras plataformas para supervisar el estado de las unidades de sistemas de salón de Skype v2.</span><span class="sxs-lookup"><span data-stu-id="f40d4-403">Disable this step only if you’re going to use some other platforms to monitor the health of your Skype Room Systems v2 units.</span></span>
        -   <span data-ttu-id="f40d4-404">Editar este paso y actualizar los parámetros de línea de comandos para especificar el **Identificador del área de trabajo** y la **Clave de área de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="f40d4-404">Edit this step and update the command-line parameters to specify your **Workspace ID** and **Workspace Key**.</span></span>
        -   <span data-ttu-id="f40d4-405">Para obtener más información acerca de cómo obtener el identificador de las operaciones de administración de conjunto de aplicaciones de área de trabajo y la clave principal, vea [equipos Windows conectarse al servicio de registro de análisis de Azure](with-oms.md#configure-test-devices-for-operations-management-suite-setup) .</span><span class="sxs-lookup"><span data-stu-id="f40d4-405">See [Connect Windows computers to the Log Analytics service in Azure](with-oms.md#configure-test-devices-for-operations-management-suite-setup) for more information about obtaining the Operations Management Suite Workspace ID and the primary key.</span></span>
        -   <span data-ttu-id="f40d4-406">Compruebe que esté seleccionado el **SRS v2 – paquete de agente de OMS de Microsoft** .</span><span class="sxs-lookup"><span data-stu-id="f40d4-406">Verify that the **SRS v2 – Microsoft OMS Agent Package** is selected.</span></span>
        -   <span data-ttu-id="f40d4-407">Para obtener más información acerca de cómo supervisar el estado de la implementación de sistemas de salón de Skype v2, vea [administración de sistemas de planeación de las salas Skype v2 con OMS](../../plan-your-deployment/clients-and-devices/oms-management.md) y [administración de v2 de implementar sistemas de salón de Skype con OMS](with-oms.md#configure-test-devices-for-operations-management-suite-setup).</span><span class="sxs-lookup"><span data-stu-id="f40d4-407">For more information about monitoring the health of your Skype Room Systems v2 deployment, see [Plan Skype Room Systems v2 management with OMS](../../plan-your-deployment/clients-and-devices/oms-management.md) and [Deploy Skype Room Systems v2 management with OMS](with-oms.md#configure-test-devices-for-operations-management-suite-setup).</span></span>

    11. <span data-ttu-id="f40d4-408">**Los archivos de configuración de copia SRS v2**: este paso copia los archivos del programa de instalación y configuración necesarios desde el kit de implementación de sistemas de salón de Skype v2 a la unidad de disco duro local.</span><span class="sxs-lookup"><span data-stu-id="f40d4-408">**Copy SRS v2 Configuration Files**: This step copies the required setup and configuration files from the Skype Room Systems v2 deployment kit to the local hard drive.</span></span> <span data-ttu-id="f40d4-409">Personalización no es necesaria para este paso.</span><span class="sxs-lookup"><span data-stu-id="f40d4-409">No customization is required for this step.</span></span>

    12. <span data-ttu-id="f40d4-410">**Install-SRSv2--actualizaciones del sistema operativo**: este paso implementa las actualizaciones de sistema operativo obligatorio necesarias con la implementación de sistemas de salón de Skype v2.</span><span class="sxs-lookup"><span data-stu-id="f40d4-410">**Install-SRSv2-OS-Updates**: This step deploys any mandatory operating system updates required with the Skype Room Systems v2 deployment.</span></span> <span data-ttu-id="f40d4-411">Siga este procedimiento:</span><span class="sxs-lookup"><span data-stu-id="f40d4-411">Do the following:</span></span>
        -   <span data-ttu-id="f40d4-412">Compruebe la [consola de configurar un v2 de sistemas de salón de Skype](console.md) para ver qué actualizaciones son necesarias.</span><span class="sxs-lookup"><span data-stu-id="f40d4-412">Check [Configure a Skype Room Systems v2 console](console.md) to see which updates are required.</span></span>
        -   <span data-ttu-id="f40d4-413">Compruebe que su **SRS v2 – paquete de actualizaciones del sistema operativo** incluye todas las actualizaciones necesarias.</span><span class="sxs-lookup"><span data-stu-id="f40d4-413">Verify that your **SRS v2 – OS Updates Package** includes all the required updates.</span></span>
        -   <span data-ttu-id="f40d4-414">Compruebe que esté seleccionado el **SRS v2 – paquete de actualizaciones del sistema operativo** .</span><span class="sxs-lookup"><span data-stu-id="f40d4-414">Verify that the **SRS v2 – OS Updates Package** is selected.</span></span>
        -   <span data-ttu-id="f40d4-415">Compruebe que la directiva de ejecución de PowerShell esté establecida en **el desvío**.</span><span class="sxs-lookup"><span data-stu-id="f40d4-415">Verify that the PowerShell execution policy is set to **Bypass**.</span></span>

    13. <span data-ttu-id="f40d4-416">**Reiniciar el equipo**: en este paso se reinicia el equipo después de instalaron las actualizaciones del sistema operativo obligatorio.</span><span class="sxs-lookup"><span data-stu-id="f40d4-416">**Restart Computer**: This step reboots the computer after the mandatory operating system updates are installed.</span></span> <span data-ttu-id="f40d4-417">Personalización no es necesaria para este paso.</span><span class="sxs-lookup"><span data-stu-id="f40d4-417">No customization is required for this step.</span></span>

    14. <span data-ttu-id="f40d4-418">**Agregar usuario de Skype Local**: este paso crea la cuenta de Skype local se usa para iniciar sesión en Windows y para iniciar la aplicación de sistemas de salón de Skype v2 de automáticamente.</span><span class="sxs-lookup"><span data-stu-id="f40d4-418">**Add Local Skype User**: This step creates the local Skype account used to automatically sign in to Windows and start the Skype Room Systems v2 application.</span></span> <span data-ttu-id="f40d4-419">Este paso no tiene ningún paquete de software asociado con él y, personalización no se requiere para él.</span><span class="sxs-lookup"><span data-stu-id="f40d4-419">This step doesn’t have any software package associated with it, and no customization is required for it.</span></span>

    15. <span data-ttu-id="f40d4-420">**Establecer de seguridad y configuración de aplicación de SRS**: este paso instala y configura la aplicación de sistemas de salón de Skype v2.</span><span class="sxs-lookup"><span data-stu-id="f40d4-420">**Set up and configure SRS application**: This step installs and configures the Skype Room Systems v2 application.</span></span> <span data-ttu-id="f40d4-421">Este paso utiliza los bits copiados localmente para instalar la aplicación y, por tanto, no tienen los paquetes de software asociados con él.</span><span class="sxs-lookup"><span data-stu-id="f40d4-421">This step uses the locally copied bits to install the application and therefore doesn’t have any software packages associated with it.</span></span> <span data-ttu-id="f40d4-422">Personalización no es necesaria para este paso.</span><span class="sxs-lookup"><span data-stu-id="f40d4-422">No customization is required for this step.</span></span>

### <a name="create-deployment-for-the-task-sequence"></a><span data-ttu-id="f40d4-423">Creación de implementación para la secuencia de tareas</span><span class="sxs-lookup"><span data-stu-id="f40d4-423">Create deployment for the task sequence</span></span>

1.  <span data-ttu-id="f40d4-424">Seleccione la secuencia de tareas y, a continuación, seleccione **implementar**.</span><span class="sxs-lookup"><span data-stu-id="f40d4-424">Select the task sequence, and then select **Deploy**.</span></span>

2.  <span data-ttu-id="f40d4-425">Seleccione **Examinar** para seleccionar la colección de destino para la implementación.</span><span class="sxs-lookup"><span data-stu-id="f40d4-425">Select **Browse** to select target collection for deployment.</span></span>

3.  <span data-ttu-id="f40d4-426">Seleccione **Todos los equipos desconocidos** y, a continuación, seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="f40d4-426">Select **All Unknown Computers** and then select **OK**.</span></span>

4.  <span data-ttu-id="f40d4-427">Seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="f40d4-427">Select **Next**.</span></span>

5.  <span data-ttu-id="f40d4-428">Seleccione **disponible** en la lista desplegable **propósito** .</span><span class="sxs-lookup"><span data-stu-id="f40d4-428">Select **Available** on the **Purpose** drop down list.</span></span>

6.  <span data-ttu-id="f40d4-429">Seleccione **sólo medios y PXE** en la lista **que esté disponible para los siguientes** y, a continuación, seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="f40d4-429">Select **Only Media and PXE** in the **Make available to the following** list, and then select **Next**.</span></span>
> [!WARNING]
> <span data-ttu-id="f40d4-430">Es muy importante que **propósito** se establece en **disponible**.</span><span class="sxs-lookup"><span data-stu-id="f40d4-430">It is very important that **Purpose** is set to **Available**.</span></span> <span data-ttu-id="f40d4-431">Asegúrese de que el **propósito** es **no** **requerido**.</span><span class="sxs-lookup"><span data-stu-id="f40d4-431">Make sure that the **Purpose** is **NOT** set to **Required**.</span></span> <span data-ttu-id="f40d4-432">También asegúrese de que seleccione **sólo medios y PXE** en la **que esté disponible al siguiente**.</span><span class="sxs-lookup"><span data-stu-id="f40d4-432">Also make sure that you select **Only Media and PXE** in the **Make available to the following**.</span></span> <span data-ttu-id="f40d4-433">Configuración de estos valores a otra cosa puede causar todos los equipos obtener la imagen de implementación de sistemas de salón de Skype al arrancar.</span><span class="sxs-lookup"><span data-stu-id="f40d4-433">Setting these values to something else might cause all computers to get the Skype Room Systems deployment image when booted.</span></span>
7.  <span data-ttu-id="f40d4-434">No especifique cualquier programación y seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="f40d4-434">Do not specify any schedule and select **Next**.</span></span>

8.  <span data-ttu-id="f40d4-435">No cambiar nada dentro de la sección de la **Experiencia del usuario** y seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="f40d4-435">Do not change anything within the **User Experience** section and select **Next**.</span></span>

9.  <span data-ttu-id="f40d4-436">No cambiar nada dentro de la sección de **alertas** y seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="f40d4-436">Do not change anything within the **Alerts** section and select **Next**.</span></span>

10.  <span data-ttu-id="f40d4-437">No cambiar nada dentro de la sección de **Puntos de distribución** y seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="f40d4-437">Do not change anything within the **Distribution Points** section and select **Next**.</span></span>

11.  <span data-ttu-id="f40d4-438">Confirmar la configuración y, a continuación, seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="f40d4-438">Confirm the settings and then select **Next**.</span></span>

12.  <span data-ttu-id="f40d4-439">Seleccione **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="f40d4-439">Select **Close**.</span></span>

<a name="validate-and-troubleshoot-the-solution"></a><span data-ttu-id="f40d4-440">Validar y solucionar problemas de la solución</span><span class="sxs-lookup"><span data-stu-id="f40d4-440">Validate and troubleshoot the solution</span></span>
--------------------------------------

<span data-ttu-id="f40d4-441">Una vez completada la secuencias de tareas de System Center Configuration Manager, debe realizar una ejecución de prueba para validar que la secuencia de tareas puede implementar y configurar unidades de sistemas de salón de Skype v2.</span><span class="sxs-lookup"><span data-stu-id="f40d4-441">After you’ve completed the System Center Configuration Manager task sequences, you’ll need to perform a test run to validate that the task sequence can deploy and configure Skype Room Systems v2 units.</span></span>

1.  <span data-ttu-id="f40d4-442">Conecte el dispositivo de prueba a la red por cable mediante uno de los adaptadores admitidos de Ethernet o utilizando el muelle de superficie.</span><span class="sxs-lookup"><span data-stu-id="f40d4-442">Connect the test device to the wired network by using one of the supported Ethernet adapters or using the Surface dock.</span></span> <span data-ttu-id="f40d4-443">Si no se ha configurado la funcionalidad de arranque PXE para su entorno, puede usar la imagen de arranque en el USB unidad flash [creó anteriormente](https://docs.microsoft.com/sccm/osd/deploy-use/create-bootable-media) para iniciar desde USB y conectar con el Administrador de configuración.</span><span class="sxs-lookup"><span data-stu-id="f40d4-443">If PXE boot functionality hasn’t been configured for your environment, you can use the boot image on the USB flash drive [that you created earlier](https://docs.microsoft.com/sccm/osd/deploy-use/create-bootable-media) to boot from USB and connect to Configuration Manager.</span></span>

2.  <span data-ttu-id="f40d4-444">Obtener acceso el firmware e iniciar inicio PXE:</span><span class="sxs-lookup"><span data-stu-id="f40d4-444">Access the firmware and initiate PXE boot:</span></span>

    1.  <span data-ttu-id="f40d4-445">Asegúrese de que el dispositivo de superficie está apagado.</span><span class="sxs-lookup"><span data-stu-id="f40d4-445">Ensure the Surface device is powered off.</span></span>

    2.  <span data-ttu-id="f40d4-446">Presione y mantenga presionado el botón **Subir volumen** .</span><span class="sxs-lookup"><span data-stu-id="f40d4-446">Press and hold the **Volume Up** button.</span></span>

    3.  <span data-ttu-id="f40d4-447">Presione y suelte el botón de **encendido** .</span><span class="sxs-lookup"><span data-stu-id="f40d4-447">Press and release the **Power** button.</span></span>

    4.  <span data-ttu-id="f40d4-448">Tras el dispositivo comienza a arrancar, suelte el botón **Subir volumen** .</span><span class="sxs-lookup"><span data-stu-id="f40d4-448">After the device begins to boot, release the **Volume Up** button.</span></span>

    5.  <span data-ttu-id="f40d4-449">Seleccione **configuración de inicio**.</span><span class="sxs-lookup"><span data-stu-id="f40d4-449">Select **Boot configuration**.</span></span>

    6.  <span data-ttu-id="f40d4-450">Realice una de las acciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="f40d4-450">Do one of the following:</span></span>

        -   <span data-ttu-id="f40d4-451">Seleccione **inicio PXE**y arrástrelo a la parte superior de la lista.</span><span class="sxs-lookup"><span data-stu-id="f40d4-451">Select **PXE boot**, and drag it to the top of the list.</span></span> <span data-ttu-id="f40d4-452">Como alternativa, puede pasar izquierda en el adaptador de red para iniciar inmediatamente el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="f40d4-452">Alternatively, you can swipe left on the network adapter to boot to the device immediately.</span></span> <span data-ttu-id="f40d4-453">Esto no afecta al orden de arranque.</span><span class="sxs-lookup"><span data-stu-id="f40d4-453">This won’t affect the boot order.</span></span>
        -   <span data-ttu-id="f40d4-454">Seleccione la unidad flash USB que contiene el medio de arranque.</span><span class="sxs-lookup"><span data-stu-id="f40d4-454">Select the USB flash drive that holds the boot media.</span></span>

3.  <span data-ttu-id="f40d4-455">Seleccione **Salir**y, a continuación, seleccione **Reiniciar ahora**.</span><span class="sxs-lookup"><span data-stu-id="f40d4-455">Select **Exit**, and then select **Restart Now**.</span></span>

4.  <span data-ttu-id="f40d4-456">Cuando se le solicite, seleccione **ENTRAR** para el servicio de inicio de red.</span><span class="sxs-lookup"><span data-stu-id="f40d4-456">When prompted, select **Enter** for network boot service.</span></span>

5.  <span data-ttu-id="f40d4-457">Windows PE se cargará en la memoria y se iniciará el Asistente para la secuencia de tareas.</span><span class="sxs-lookup"><span data-stu-id="f40d4-457">Windows PE will load into memory, and the Task Sequence Wizard will start.</span></span> <span data-ttu-id="f40d4-458">Seleccione **siguiente** para continuar.</span><span class="sxs-lookup"><span data-stu-id="f40d4-458">Select **Next** to continue.</span></span>

6.  <span data-ttu-id="f40d4-459">Seleccione la secuencia de tareas que importó anteriormente y, a continuación, seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="f40d4-459">Select the task sequence that you imported earlier, and then select **Next**.</span></span>

7.  <span data-ttu-id="f40d4-460">Después de aplica la configuración del disco, se le pedirá que especifique un nombre de equipo para el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="f40d4-460">After the disk configuration is applied, you’ll be prompted to specify a computer name for the device.</span></span> <span data-ttu-id="f40d4-461">Un nombre de equipo recomendada en función del número de serie del dispositivo Surface Pro, mostrará la interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="f40d4-461">The user interface will display a recommended computer name based on the serial number of the Surface Pro device.</span></span> <span data-ttu-id="f40d4-462">Puede aceptar el nombre propuesto o especifique uno nuevo.</span><span class="sxs-lookup"><span data-stu-id="f40d4-462">You can either accept the proposed name or specify a new one.</span></span> <span data-ttu-id="f40d4-463">Siga las instrucciones que aparecen en la pantalla de asignación de nombre de equipo.</span><span class="sxs-lookup"><span data-stu-id="f40d4-463">Follow the instructions on the computer name assignment screen.</span></span> <span data-ttu-id="f40d4-464">Cuando se selecciona **Aceptar**, comienza la implementación.</span><span class="sxs-lookup"><span data-stu-id="f40d4-464">When you select **Accept**, the deployment begins.</span></span>

8.  <span data-ttu-id="f40d4-465">El resto del proceso de implementación es automático y no solicitar ninguna entrada del usuario más.</span><span class="sxs-lookup"><span data-stu-id="f40d4-465">The rest of the deployment process is automatic and doesn’t ask for any more user input.</span></span>

9.  <span data-ttu-id="f40d4-466">Después de la secuencia de tareas de implementación termina de configurar el dispositivo, verá la siguiente pantalla de configuración que le pide que configure la configuración de la aplicación de sistemas de salón de Skype v2.</span><span class="sxs-lookup"><span data-stu-id="f40d4-466">After the deployment task sequence finishes configuring the device, you’ll see the following configuration screen that asks you to configure the Skype Room Systems v2 application settings.</span></span>

    ![Pantalla inicial del programa de instalación para aplicación v2 de sistemas de salón de Skype](../../media/room-systems-scale-image2.png)

10.  <span data-ttu-id="f40d4-468">Conecte el Surface Pro en la consola de v2 de sistemas de salón de Skype y configurar la configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="f40d4-468">Plug the Surface Pro into the Skype Room Systems v2 console, and configure the application settings.</span></span>

11.  <span data-ttu-id="f40d4-469">Validar que las funciones que aparecen en la [Ayuda de sistemas de salón de Skype v2](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2) están trabajando en el dispositivo implementado.</span><span class="sxs-lookup"><span data-stu-id="f40d4-469">Validate that the capabilities listed in [Skype Room Systems v2 help](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2) are working on the deployed device.</span></span>


<span data-ttu-id="f40d4-470">Para solucionar problemas de una instalación con errores, compruebe el archivo **SMSTS.log** , que registra todos los pasos que se ejecutan en una secuencia de tareas de administrador de configuración.</span><span class="sxs-lookup"><span data-stu-id="f40d4-470">To troubleshoot a failed installation, check the **SMSTS.log** file, which logs all the steps executed in a Configuration Manager task sequence.</span></span>

<span data-ttu-id="f40d4-471">El archivo SMSTS.log se almacena en uno de un número de rutas de acceso, según la fase del proceso de generación.</span><span class="sxs-lookup"><span data-stu-id="f40d4-471">The SMSTS.log file is stored on one of a number of paths, depending on the stage of the build process.</span></span> <span data-ttu-id="f40d4-472">Compruebe la tabla siguiente para identificar la ruta de acceso al archivo SMSTS.log.</span><span class="sxs-lookup"><span data-stu-id="f40d4-472">Check the following table to identify the path to the SMSTS.log file.</span></span>


| <span data-ttu-id="f40d4-473">**Fase de implementación**</span><span class="sxs-lookup"><span data-stu-id="f40d4-473">**Deployment phase**</span></span>                                                            | <span data-ttu-id="f40d4-474">**Ruta de acceso del registro de secuencia de tareas**</span><span class="sxs-lookup"><span data-stu-id="f40d4-474">**Task sequence log path**</span></span>                         |
|---------------------------------------------------------------------------------|----------------------------------------------------|
| <span data-ttu-id="f40d4-475">WinPE, antes de formato de la unidad de disco duro</span><span class="sxs-lookup"><span data-stu-id="f40d4-475">WinPE, before HDD format</span></span>                                                        | <span data-ttu-id="f40d4-476">X:\\Windows\\Temp\\smstslog\\smsts.log</span><span class="sxs-lookup"><span data-stu-id="f40d4-476">X:\\Windows\\Temp\\smstslog\\smsts.log</span></span>             |
| <span data-ttu-id="f40d4-477">WinPE, después de formato de la unidad de disco duro</span><span class="sxs-lookup"><span data-stu-id="f40d4-477">WinPE, after HDD format</span></span>                                                         | <span data-ttu-id="f40d4-478">C:\\_SMSTaskSequence\\registros\\Smstslog\\smsts.log</span><span class="sxs-lookup"><span data-stu-id="f40d4-478">C:\\_SMSTaskSequence\\Logs\\Smstslog\\smsts.log</span></span>    |
| <span data-ttu-id="f40d4-479">Sistema operativo implementado, antes de que se ha instalado el agente de Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="f40d4-479">Operating system deployed, before the Configuration Manager agent was installed</span></span> | <span data-ttu-id="f40d4-480">c:\\_SMSTaskSequence\\registros\\Smstslog\\smsts.log</span><span class="sxs-lookup"><span data-stu-id="f40d4-480">c:\\_SMSTaskSequence\\Logs\\Smstslog\\smsts.log</span></span>    |
| <span data-ttu-id="f40d4-481">Sistema operativo y el agente de Configuration Manager implementado</span><span class="sxs-lookup"><span data-stu-id="f40d4-481">Operating system and the Configuration Manager agent deployed</span></span>                   | <span data-ttu-id="f40d4-482">% windir %\\System32\\MCC\\registros\\Smstslog\\smsts.log</span><span class="sxs-lookup"><span data-stu-id="f40d4-482">%windir%\\System32\\ccm\\logs\\Smstslog\\smsts.log</span></span> |
| <span data-ttu-id="f40d4-483">Ejecución de secuencia de tareas completa</span><span class="sxs-lookup"><span data-stu-id="f40d4-483">Task sequence execution complete</span></span>                                                | <span data-ttu-id="f40d4-484">% windir %\\System32\\MCC\\registros\\smsts.log</span><span class="sxs-lookup"><span data-stu-id="f40d4-484">%windir%\\System32\\ccm\\logs\\smsts.log</span></span>           |

> [!TIP]
> <span data-ttu-id="f40d4-485">Puede seleccionar F8 en cualquier momento durante la secuencia de tareas para abrir una consola de comandos y obtener acceso al archivo SMSTS.log.</span><span class="sxs-lookup"><span data-stu-id="f40d4-485">You can select F8 at any time during the task sequence to open a command console and get access to the SMSTS.log file.</span></span>

<span data-ttu-id="f40d4-486">Para resolver problemas de inicio PXE, compruebe los dos archivos de registro en el servidor del Administrador de configuración que son específicos de acciones de PXE:</span><span class="sxs-lookup"><span data-stu-id="f40d4-486">To resolve PXE boot issues, check the two log files on the Configuration Manager server that are specific to PXE actions:</span></span>

-   <span data-ttu-id="f40d4-487">**Pxecontrol.log**, que se encuentra en el directorio de los registros de instalación de administrador de configuración</span><span class="sxs-lookup"><span data-stu-id="f40d4-487">**Pxecontrol.log**, located in the Configuration Manager installation logs directory</span></span>

-   <span data-ttu-id="f40d4-488">**Smspxe.log**, que se encuentra en el directorio de registros del punto de administración de administrador de configuración (MP)</span><span class="sxs-lookup"><span data-stu-id="f40d4-488">**Smspxe.log**, located in Configuration Manager Management Point (MP) logs directory</span></span>

<span data-ttu-id="f40d4-489">Para obtener una lista completa de los archivos de registro que se pueden utilizar para solucionar aún más la instalación de administrador de configuración, vea [archivos de registro en System Center Configuration Manager](https://docs.microsoft.com/sccm/core/plan-design/hierarchy/log-files).</span><span class="sxs-lookup"><span data-stu-id="f40d4-489">For a complete list of the log files that you can use to further troubleshoot your Configuration Manager installation, see [Log files in System Center Configuration Manager](https://docs.microsoft.com/sccm/core/plan-design/hierarchy/log-files).</span></span>
