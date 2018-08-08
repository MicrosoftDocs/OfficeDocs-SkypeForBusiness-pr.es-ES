---
title: Preparar el dispositivo de Cloud Connector
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/15/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 6eacfa99-9759-4c13-aca3-8992c2ff2710
description: Obtenga información sobre cómo preparar su dispositivo conector en la nube para la implementación y usar con el sistema telefónico en Office 365 (en la nube PBX).
ms.openlocfilehash: 54ee8394c9da5b00e6a9c9afa7d4a1f3419c2f41
ms.sourcegitcommit: 8a34b5f0295fc6059852dab6971429fda4d30b67
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/02/2018
ms.locfileid: "20176093"
---
# <a name="prepare-your-cloud-connector-appliance"></a><span data-ttu-id="6622d-103">Preparar el dispositivo de Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="6622d-103">Prepare your Cloud Connector appliance</span></span>
 
<span data-ttu-id="6622d-104">Obtenga información sobre cómo preparar su dispositivo conector en la nube para la implementación y usar con el sistema telefónico en Office 365 (en la nube PBX).</span><span class="sxs-lookup"><span data-stu-id="6622d-104">Learn about how to prepare your Cloud Connector appliance for deployment and use with Phone System in Office 365 (Cloud PBX).</span></span>
  
<span data-ttu-id="6622d-105">En esta sección se describe cómo obtener los archivos de instalación de Skype Empresarial Cloud Connector Edition, instalar el software Cloud Connector y preparar el dispositivo de Cloud Connector para la implementación.</span><span class="sxs-lookup"><span data-stu-id="6622d-105">This section describes how to get the Skype for Business Cloud Connector Edition installation files, install Cloud Connector software, and prepare your Cloud Connector appliance for deployment.</span></span> <span data-ttu-id="6622d-106">Después de completar todos los pasos de esta sección, estará listo para implementar Cloud Connector para un único sitio o para varios sitios.</span><span class="sxs-lookup"><span data-stu-id="6622d-106">After you have completed all steps in this section, you will be ready to deploy Cloud Connector for a single site or multiple sites.</span></span> <span data-ttu-id="6622d-107">Si tiene una implementación existente de conector en la nube, y aún no ha actualizado a la nube conector versión 2.1, consulte [actualizar a una nueva versión del conector en la nube](upgrade-to-a-new-version-of-cloud-connector.md).</span><span class="sxs-lookup"><span data-stu-id="6622d-107">If you have an existing Cloud Connector deployment, and you have not yet upgraded to Cloud Connector version 2.1, see [Upgrade to a new version of Cloud Connector](upgrade-to-a-new-version-of-cloud-connector.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="6622d-108">Microsoft admite la versión actual de la nube conector Edition, versión 2.1.</span><span class="sxs-lookup"><span data-stu-id="6622d-108">Microsoft supports the current version of Cloud Connector Edition, version 2.1.</span></span> <span data-ttu-id="6622d-109">Si ha configurado la actualización automática, Cloud Connector se actualizará automáticamente.</span><span class="sxs-lookup"><span data-stu-id="6622d-109">If you configured automatic update, Cloud Connector will update automatically.</span></span> <span data-ttu-id="6622d-110">Si ha configurado la actualización manual, debe actualizar a la versión 2.1 plazo de 60 días de su publicación.</span><span class="sxs-lookup"><span data-stu-id="6622d-110">If you configured manual update, you will need to upgrade to version 2.1 within 60 days of its release.</span></span> <span data-ttu-id="6622d-111">Microsoft admitirá la versión anterior para 60 días después del lanzamiento de 2.1 para permitir tiempo para actualizar.</span><span class="sxs-lookup"><span data-stu-id="6622d-111">Microsoft will support the previous version for 60 days after the release of 2.1 to allow you time to upgrade.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="6622d-112">Para la nube conector versión 2.1 y versiones posterior, el dispositivo de host debe tener .NET Framework 4.6.1 o posterior instalado.</span><span class="sxs-lookup"><span data-stu-id="6622d-112">For Cloud Connector version 2.1 and later, the host appliance must have .NET Framework 4.6.1 or later installed.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="6622d-113">Para una implementación correcta, al ejecutar los cmdlets para configurar Skype para Business Edition de conector en la nube, use siempre la misma sesión de consola que la inició en.</span><span class="sxs-lookup"><span data-stu-id="6622d-113">For successful deployment, when you run the cmdlets to configure Skype for Business Cloud Connector Edition, always use the same console session as the one you started in.</span></span> <span data-ttu-id="6622d-114">Evite cambiar a diferentes sesiones durante la implementación y la configuración.</span><span class="sxs-lookup"><span data-stu-id="6622d-114">Avoid switching to different sessions during the deployment and configuration.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="6622d-115">Hay algunos pasos que solo se realizan para el primer dispositivo de la implementación: la creación de un recurso compartido del directorio de sitios, la descarga de los bits y la preparación de un archivo de disco duro virtual (VHDX) desde la imagen ISO de Windows Server.</span><span class="sxs-lookup"><span data-stu-id="6622d-115">There are some steps that you perform only for the first appliance in your deployment: creating a share for the site directory, downloading the bits, and preparing a virtual hard disk (VHDX) file from the Windows Server ISO image.</span></span> 
  
## <a name="download-the-skype-for-business-cloud-connector-edition-installer"></a><span data-ttu-id="6622d-116">Descargar el instalador de Skype Empresarial Cloud Connector Edition</span><span class="sxs-lookup"><span data-stu-id="6622d-116">Download the Skype for Business Cloud Connector Edition installer</span></span>

1. <span data-ttu-id="6622d-117">En el servidor host donde se ejecutará el conector en la nube, las máquinas virtuales, descargue los archivos de instalación: [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller).</span><span class="sxs-lookup"><span data-stu-id="6622d-117">On the host server where the Cloud Connector VMs will run, download the installation files: [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller).</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="6622d-118">El servidor host debe poder acceder a Internet durante la instalación de Cloud Connector porque se descargan archivos adicionales durante la instalación.</span><span class="sxs-lookup"><span data-stu-id="6622d-118">The host server must be able to access the Internet during the installation of Cloud Connector because additional files are downloaded during the installation.</span></span> 
  
2. <span data-ttu-id="6622d-119">Ejecute el instalador y acepte los valores predeterminados durante la instalación.</span><span class="sxs-lookup"><span data-stu-id="6622d-119">Run the installer and accept the default values during the installation.</span></span>
    
3. <span data-ttu-id="6622d-120">Confirme que la instalación se ha completado correctamente.</span><span class="sxs-lookup"><span data-stu-id="6622d-120">Confirm that the installation completed successfully.</span></span>
    
## <a name="verify-the-installation-and-configure-the-environment"></a><span data-ttu-id="6622d-121">Comprobar la instalación y configurar el entorno</span><span class="sxs-lookup"><span data-stu-id="6622d-121">Verify the installation and configure the environment</span></span>

1. <span data-ttu-id="6622d-122">Abra una consola de PowerShell como administrador y confirme que la Skype para cmdlets de conector de nube Business Edition están disponibles mediante el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="6622d-122">Open a PowerShell console as administrator and confirm that the Skype for Business Cloud Connector Edition cmdlets are available using the following cmdlet:</span></span>
    
  ```
  Get-Command *-Cc*
  ```

    <span data-ttu-id="6622d-123">El comando debe devolver una lista de cmdlets de Skype para Business Edition de conector en la nube.</span><span class="sxs-lookup"><span data-stu-id="6622d-123">The command should return a list of cmdlets for Skype for Business Cloud Connector Edition.</span></span>
    
2. <span data-ttu-id="6622d-124">Los archivos VHDs, SfBBits y VersionInfo se almacenarán en el **Directorio de sitios**.</span><span class="sxs-lookup"><span data-stu-id="6622d-124">The VHDs, SfBBits, and VersionInfo files will be stored in the **Site Directory**.</span></span>
    
    <span data-ttu-id="6622d-125">Puede encontrar la ubicación del **Directorio de sitios** con el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="6622d-125">You can find the location of the **Site Directory** with the following cmdlet:</span></span>
    
  ```
  Get-CcSiteDirectory
  ```

    <span data-ttu-id="6622d-126">El comando debe devolver una ubicación de su sistema de archivos.</span><span class="sxs-lookup"><span data-stu-id="6622d-126">The command should return a location in your file system.</span></span> <span data-ttu-id="6622d-127">La ubicación puede ser una carpeta local o un recurso compartido de archivos.</span><span class="sxs-lookup"><span data-stu-id="6622d-127">The location can be a local folder or a file share.</span></span> <span data-ttu-id="6622d-128">La ubicación predeterminada del **Directorio de sitios** es: %USERPROFILE%\CloudConnector\SiteRoot.</span><span class="sxs-lookup"><span data-stu-id="6622d-128">The default location for the **Site Directory** is: %USERPROFILE%\CloudConnector\SiteRoot.</span></span> <span data-ttu-id="6622d-129">La ubicación predeterminada se debe cambiar a un recurso compartido de archivos en la primera aplicación que se cree en cada sitio.</span><span class="sxs-lookup"><span data-stu-id="6622d-129">The default location should be changed to a file share on the first appliance created in each site.</span></span>
    
    <span data-ttu-id="6622d-130">La ubicación que seleccione debe:</span><span class="sxs-lookup"><span data-stu-id="6622d-130">The location you select must be:</span></span>
    
  - <span data-ttu-id="6622d-131">Crearse en el primer dispositivo creado en cada sitio.</span><span class="sxs-lookup"><span data-stu-id="6622d-131">Created on the first appliance created in each site.</span></span>
    
  - <span data-ttu-id="6622d-132">Ser una carpeta compartida a la que pueden acceder los servidores host (dispositivos) del mismo sitio.</span><span class="sxs-lookup"><span data-stu-id="6622d-132">A shared folder that is accessible by the other host servers (appliances) in the same site.</span></span>
    
    <span data-ttu-id="6622d-133">Para establecer el **Directorio de sitios** en una ubicación distinta de la predeterminada, ejecute el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="6622d-133">To set the **Site Directory** to a location other than the default, run the following cmdlet:</span></span>
    
  ```
  Set-CcSiteDirectory <UNC File path>
  ```

    <span data-ttu-id="6622d-134">Si va a implementar la alta disponibilidad (HA) para el sitio, asegúrese de ejecutar el cmdlet para establecer el **Directorio de sitios** en la misma ubicación en cada servidor host del sitio.</span><span class="sxs-lookup"><span data-stu-id="6622d-134">If you are deploying High Availability (HA) for the site, make sure you run the cmdlet to set the **Site Directory** to the same location on each host server within the site.</span></span>
    
    <span data-ttu-id="6622d-135">Al inicio de sesión e implementar cada dispositivo en el sitio, asegúrese de que su cuenta de inicio de sesión actual tiene el derecho de acceso al **Directorio de sitios**.</span><span class="sxs-lookup"><span data-stu-id="6622d-135">When you log on and deploy each appliance in the site, make sure your current logon account has the right access to the **Site Directory**.</span></span>
    
3. <span data-ttu-id="6622d-136">El **Directorio del dispositivo** es el directorio raíz de trabajo local para Skype para Business Edition de conector en la nube y la ubicación donde se guardan los certificados externos, instancias y los registros.</span><span class="sxs-lookup"><span data-stu-id="6622d-136">The **Appliance Directory** is the local working root directory for Skype for Business Cloud Connector Edition, and the location where external certificates, instances, and logs are saved.</span></span> <span data-ttu-id="6622d-137">La ubicación predeterminada es: %USERPROFILE%\CloudConnector\ApplianceRoot.</span><span class="sxs-lookup"><span data-stu-id="6622d-137">The default location is: %USERPROFILE%\CloudConnector\ApplianceRoot.</span></span>
    
    <span data-ttu-id="6622d-138">Para encontrar la ubicación del **Directorio de aplicaciones**, ejecute el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="6622d-138">To find the location of the **Appliance Directory**, run the following cmdlet:</span></span>
    
  ```
  Get-CcApplianceDirectory
  ```

    <span data-ttu-id="6622d-139">Para establecer el **Directorio de aplicaciones** en una ubicación distinta de la predeterminada, ejecute el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="6622d-139">To set the **Appliance Directory** to a location other than the default, run the following cmdlet:</span></span>
    
  ```
  Set-CcApplianceDirectory <File path>
  ```

    <span data-ttu-id="6622d-140">El directorio de dispositivos debe establecerse en una carpeta local del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="6622d-140">The Appliance Directory should be set to a local folder on the appliance.</span></span> <span data-ttu-id="6622d-141">Sólo debe establecer el **Directorio de dispositivo** antes de empezar la Skype para la implementación de Business Edition de conector en la nube.</span><span class="sxs-lookup"><span data-stu-id="6622d-141">You should only set the **Appliance Directory** before you start the Skype for Business Cloud Connector Edition deployment.</span></span> <span data-ttu-id="6622d-142">Si lo cambia después, tendrá que volver a implementar el servidor host.</span><span class="sxs-lookup"><span data-stu-id="6622d-142">If you change it after deployment, you'll need to redeploy the host server.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="6622d-143">La ruta de acceso al **Directorio de aplicaciones** no puede contener espacios.</span><span class="sxs-lookup"><span data-stu-id="6622d-143">The path to the **Appliance Directory** must not contain any spaces.</span></span>
  
## <a name="set-the-path-for-the-external-edge-certificate"></a><span data-ttu-id="6622d-144">Establecer la ruta de acceso del certificado perimetral externo</span><span class="sxs-lookup"><span data-stu-id="6622d-144">Set the path for the external Edge certificate</span></span>

- <span data-ttu-id="6622d-p107">Ejecute el siguiente cmdlet para establecer la ruta de acceso, incluido el nombre del archivo, al certificado perimetral externo. Por ejemplo: C:\certs\cce\ap.contoso.com.pfx. El certificado no puede contener claves privadas.</span><span class="sxs-lookup"><span data-stu-id="6622d-p107">Run the following cmdlet to set the path, including the file name, to the external Edge certificate. For example: C:\certs\cce\ap.contoso.com.pfx. The certificate must contain private keys.</span></span>
    
  ```
  Set-CcExternalCertificateFilePath -Path <Full path to External certificate, including file name> -Target EdgeServer
  ```

    > [!NOTE]
    > <span data-ttu-id="6622d-148">Tenga en cuenta que el parámetro -Target es específico de la versión 1.4.2 y las versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="6622d-148">Note that the -Target parameter is specific to versions 1.4.2 and later.</span></span> 
  
    <span data-ttu-id="6622d-149">Especifique la ruta de acceso completa al certificado externo, incluido el nombre del archivo.</span><span class="sxs-lookup"><span data-stu-id="6622d-149">Specify the full path to the external certificate, including the file name.</span></span> <span data-ttu-id="6622d-150">El certificado se puede almacenar localmente o en un recurso compartido de archivos.</span><span class="sxs-lookup"><span data-stu-id="6622d-150">The certificate can be stored locally or on a file share.</span></span> <span data-ttu-id="6622d-151">Si el certificado se almacena en una carpeta compartida, esta deberá crearse en el primer dispositivo de cada sitio y los demás dispositivos que pertenezcan al mismo sitio deben poder acceder a ella.</span><span class="sxs-lookup"><span data-stu-id="6622d-151">If the certificate is stored in a shared folder, the shared folder must be created on the first appliance of each site and must be accessible by other appliances belonging to the same site.</span></span> <span data-ttu-id="6622d-152">Este cmdlet copia el certificado externo en el **directorio de dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="6622d-152">This cmdlet copies the external certificate to the **Appliance Directory**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="6622d-153">**Si ha actualizado a Cloud Connector versión 1.4.2 o posterior**, asegúrese de que el certificado externo preparado contenga claves privadas y la cadena de certificados completa, incluidos el certificado de CA raíz y los certificados de CA intermedios. </span><span class="sxs-lookup"><span data-stu-id="6622d-153">**If you have updated to Cloud Connector version 1.4.2 or later**, make sure your prepared external certificate contains private keys and the full certificate chain including the root CA certificate and the intermediate CA certificates.</span></span> <span data-ttu-id="6622d-154">**Si aún NO ha actualizado a Cloud Connector versión 1.4.2**, asegúrese de que el certificado externo preparado contenga claves privadas.</span><span class="sxs-lookup"><span data-stu-id="6622d-154">**If you have NOT yet updated to Cloud Connector version 1.4.2**, make sure your prepared external certificate contains private keys.</span></span> <span data-ttu-id="6622d-155">Este certificado externo lo debe emitir una entidad de certificación en la que Windows confíe de manera predeterminada.</span><span class="sxs-lookup"><span data-stu-id="6622d-155">This external certificate must be issued by a Certificate Authority that is trusted by Windows by default.</span></span>
  
## <a name="set-the-path-for-the-external-pstn-gatewaysbc-certificate"></a><span data-ttu-id="6622d-156">Establecer la ruta de acceso del certificado de la puerta de enlace RTC/SBC</span><span class="sxs-lookup"><span data-stu-id="6622d-156">Set the path for the external PSTN gateway/SBC certificate</span></span>

<span data-ttu-id="6622d-157">Si va a utilizar TLS entre el servidor de mediación y la puerta de enlace RTC/SBC, ejecute el siguiente cmdlet para establecer la ruta de acceso, incluido el nombre de archivo, al certificado de la puerta de enlace.</span><span class="sxs-lookup"><span data-stu-id="6622d-157">If you are using TLS between the Mediation Server and the PSTN gateway/SBC, run the following cmdlet to set the path, including the file name, to the gateway certificate.</span></span> <span data-ttu-id="6622d-158">Por ejemplo: C:\certs\cce\sbc.contoso.com.cer.</span><span class="sxs-lookup"><span data-stu-id="6622d-158">For example: C:\certs\cce\sbc.contoso.com.cer.</span></span> <span data-ttu-id="6622d-159">El certificado debe contener la CA raíz y la cadena intermedia del certificado asignado a la puerta de enlace:</span><span class="sxs-lookup"><span data-stu-id="6622d-159">The certificate must contain the root CA and the intermediate chain for the certificate assigned to the gateway:</span></span>
  
```
Set-CcExternalCertificateFilePath -Path <Full path to gateway certificate, including file name> -Target MediationServer 

```

> [!NOTE]
> <span data-ttu-id="6622d-160">Tenga en cuenta que el parámetro -Target es específico de la versión 1.4.2 y las versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="6622d-160">Note that the -Target parameter is specific to versions 1.4.2 and later.</span></span> 
  
## <a name="create-virtual-switches-in-hyper-v-manager"></a><span data-ttu-id="6622d-161">Crear conmutadores virtuales en el Administrador de Hyper-V</span><span class="sxs-lookup"><span data-stu-id="6622d-161">Create virtual switches in Hyper-V Manager</span></span>

1. <span data-ttu-id="6622d-162">Abra el **Administrador de Hyper-V** > **Virtual Switch Manager**y seleccione **Nuevo administrador de conmutador Virtual**.</span><span class="sxs-lookup"><span data-stu-id="6622d-162">Open **Hyper-V Manager** > **Virtual Switch Manager**, and select **New Virtual Switch Manager**.</span></span>
    
2. <span data-ttu-id="6622d-163">Cree un conmutador virtual externo y enlácelo al adaptador de red físico que está conectado al dominio de red interno:</span><span class="sxs-lookup"><span data-stu-id="6622d-163">Create an External virtual switch and bind it to the physical network adapter that is connected to your internal network domain:</span></span>
    
    <span data-ttu-id="6622d-164">Seleccione **Permitir que el sistema operativo de administración comparta este adaptador de red** para este conmutador virtual.</span><span class="sxs-lookup"><span data-stu-id="6622d-164">Select **Allow management operating system to share this network adapter** for this virtual switch.</span></span>
    
3. <span data-ttu-id="6622d-165">Cree un conmutador virtual externo y enlazar al adaptador de red físico que se enruta a Internet:</span><span class="sxs-lookup"><span data-stu-id="6622d-165">Create an External virtual switch and bind it to the physical network adapter that is routed to the Internet:</span></span>
    
    <span data-ttu-id="6622d-166">Anule la selección **Permitir que el sistema operativo de administración comparta este adaptador de red** para este conmutador virtual.</span><span class="sxs-lookup"><span data-stu-id="6622d-166">De-select **Allow management operating system to share this network adapter** for this virtual switch.</span></span>
    
4. <span data-ttu-id="6622d-167">Establecer el nombre del conmutador que se conecta a la red perimetral a su dominio de red interna **SfB CCE Corpnet cambiar**.</span><span class="sxs-lookup"><span data-stu-id="6622d-167">Set the name of the switch that connects your perimeter network to your internal network domain **SfB CCE Corpnet Switch**.</span></span>
    
    <span data-ttu-id="6622d-168">Establecer el nombre del conmutador que se conecta a la red perimetral a la Internet **SfB CCE Internet cambiar**.</span><span class="sxs-lookup"><span data-stu-id="6622d-168">Set the name of the switch that connects your perimeter network to the Internet **SfB CCE Internet Switch**.</span></span>
    
## <a name="update-the-cloudconnectorini-configuration-file"></a><span data-ttu-id="6622d-169">Actualizar el archivo de configuración CloudConnector.ini</span><span class="sxs-lookup"><span data-stu-id="6622d-169">Update the CloudConnector.ini configuration file</span></span>

<span data-ttu-id="6622d-170">Preparar el archivo de CloudConnector.ini con la información recopilada en [los parámetros de implementación Determine](plan-skype-for-business-cloud-connector-edition.md#BKMK_SiteParams) en el tema de [planeación de Skype para Business Edition de conector en la nube](plan-skype-for-business-cloud-connector-edition.md) .</span><span class="sxs-lookup"><span data-stu-id="6622d-170">Prepare the CloudConnector.ini file using the information you gathered in [Determine deployment parameters](plan-skype-for-business-cloud-connector-edition.md#BKMK_SiteParams) in the [Plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md) topic.</span></span>
  
<span data-ttu-id="6622d-171">Para actualizar el archivo, ejecute primero el siguiente cmdlet para obtener la plantilla de muestra (CloudConnector.Sample.ini):</span><span class="sxs-lookup"><span data-stu-id="6622d-171">To update the file, first run the following cmdlet to get the sample template (CloudConnector.Sample.ini):</span></span>
  
```
Export-CcConfigurationSampleFile
```

<span data-ttu-id="6622d-172">La plantilla de muestra está almacenada en el **Directorio de aplicaciones**. </span><span class="sxs-lookup"><span data-stu-id="6622d-172">The sample template is stored in the **Appliance Directory**.</span></span>
  
<span data-ttu-id="6622d-p111">Después de actualizarlo con los valores de su entorno, guarde el archivo como CloudConnector.ini en el **Directorio de aplicaciones**. Puede ejecutar **Get-CcApplianceDirectory** para determinar la ruta de acceso al **Directorio de aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="6622d-p111">After you update it with the values for your environment, save the file as CloudConnector.ini in the **Appliance Directory**. You can run **Get-CcApplianceDirectory** to determine the path to the **Appliance Directory**.</span></span>
  
<span data-ttu-id="6622d-175">Al actualizar el archivo .ini, tenga en cuenta lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="6622d-175">When updating the .ini file, consider the following:</span></span>
  
> [!NOTE]
> <span data-ttu-id="6622d-176">No todos los valores del archivo .ini se tratan en esta sección, solo los que tengan una consideración especial.</span><span class="sxs-lookup"><span data-stu-id="6622d-176">Not all values for the .ini file are discussed in this section, only those with a special consideration are covered here.</span></span> <span data-ttu-id="6622d-177">Para obtener una lista completa, vea la sección [parámetros de implementación Determine](plan-skype-for-business-cloud-connector-edition.md#BKMK_SiteParams) del tema de [planeación de Skype para Business Edition de conector en la nube](plan-skype-for-business-cloud-connector-edition.md) .</span><span class="sxs-lookup"><span data-stu-id="6622d-177">For a full list, see the [Determine deployment parameters](plan-skype-for-business-cloud-connector-edition.md#BKMK_SiteParams) section of the [Plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md) topic.</span></span> <span data-ttu-id="6622d-178">Para obtener más información acerca de los valores que se deben cambiar para los dispositivos adicionales o los sitios nuevos, consulte [Sitio único con HA comparado con implementaciones de varios sitios](deploy-multiple-sites-in-cloud-connector.md#BKMK_SingleSitecomparedtomulti-site) en el tema [Deploy multiple sites in Cloud Connector](deploy-multiple-sites-in-cloud-connector.md).</span><span class="sxs-lookup"><span data-stu-id="6622d-178">For more information about what values need to be changed for additional appliances or new sites, see [Single site with High Availability (HA) compared to multi-site deployments](deploy-multiple-sites-in-cloud-connector.md#BKMK_SingleSitecomparedtomulti-site) in the topic [Deploy multiple sites in Cloud Connector](deploy-multiple-sites-in-cloud-connector.md).</span></span> 
  
- <span data-ttu-id="6622d-p113">**SiteName:** El valor predeterminado es **Site1**. Debe actualizarlo antes de implementar Cloud Connector, porque al ejecutar **Register-CcAppliance** para registrar un dispositivo en un sitio nuevo o existente, el cmdlet usará **SiteName** para determinar qué sitio se debe registrar.</span><span class="sxs-lookup"><span data-stu-id="6622d-p113">**SiteName:** The default value is **Site1**. You must update it before you deploy Cloud Connector, because when you run **Register-CcAppliance** to register an appliance to an existing or new site, the cmdlet will use **SiteName** to determine which site to register.</span></span>
    
     <span data-ttu-id="6622d-181">Si desea registrar el dispositivo en un sitio nuevo, el valor de **SiteName** debe ser único y diferente de los sitios existentes.</span><span class="sxs-lookup"><span data-stu-id="6622d-181">If you want to register the appliance to a new site, the value of **SiteName** must be unique and different from existing sites.</span></span> <span data-ttu-id="6622d-182">Si desea registrar el dispositivo a un sitio existente, el valor de **nombre del sitio** en el archivo .ini debe coincidir con el nombre definido en la configuración del inquilino de Office 365.</span><span class="sxs-lookup"><span data-stu-id="6622d-182">If you want to register the appliance to an existing site, the value for **SiteName** in .ini file must match the name defined in your Office 365 tenant configuration.</span></span> <span data-ttu-id="6622d-183">Si va a copiar un archivo de configuración de un sitio a otro, asegúrese de actualizar el valor de **SiteName** para cada sitio tal como corresponda.</span><span class="sxs-lookup"><span data-stu-id="6622d-183">If you are copying a configuration file from one site to another, make sure you update the value for **SiteName** for each site accordingly.</span></span>
    
- <span data-ttu-id="6622d-184">**ServerName:** El nombre del servidor no debe contener el nombre de dominio y debe estar limitado a 15 caracteres. </span><span class="sxs-lookup"><span data-stu-id="6622d-184">**ServerName:** The server name should not contain the domain name and should be limited to 15 characters.</span></span>
    
- <span data-ttu-id="6622d-185">**HardwareType:** Si no establece o deje el valor en null, se usará el valor predeterminado de **Normal** .</span><span class="sxs-lookup"><span data-stu-id="6622d-185">**HardwareType:** If you don't set or leave the value to null, the default value of **Normal** will be used.</span></span> <span data-ttu-id="6622d-186">Utilice **Normal** si tiene previsto implementar la versión mayor del conector en la nube para admitir llamadas simultáneas 500 por máquina del host como se describe en [Plan for Skype para Business Edition de conector en la nube](plan-skype-for-business-cloud-connector-edition.md).</span><span class="sxs-lookup"><span data-stu-id="6622d-186">Use **Normal** if you plan to deploy the larger version of Cloud Connector to support 500 simultaneous calls per host machine as described in [Plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md).</span></span> <span data-ttu-id="6622d-187">Use **Minimum** para una versión más pequeña que admita 50 llamadas simultáneas.</span><span class="sxs-lookup"><span data-stu-id="6622d-187">Use **Minimum** for a smaller deployment that supports 50 simultaneous calls.</span></span>
    
- <span data-ttu-id="6622d-p116">**Conmutadores virtuales de Internet, red corporativa o administración:** Agregue el nombre de los conmutadores virtuales que haya creado. Para el conmutador virtual de administración, deje el valor predeterminado. El script de implementación creará el conmutador virtual de administración al comienzo de la implementación y lo eliminará cuando termine la implementación.
</span><span class="sxs-lookup"><span data-stu-id="6622d-p116">**Internet/Corpnet/Management virtual switches:**: Add the name of the virtual switches you have created. For the management virtual switch, leave the default value. The deployment script will create the management virtual switch at the beginning of deployment and delete it when the deployment finishes.</span></span>
    
- <span data-ttu-id="6622d-p117">**ManagementIPPrefix:** ManagementIPPrefix en la sección de Red debe ser una subred diferente de otras IP internas. Por ejemplo, tal como muestra el valor predeterminado, ManagementIPPrefix es 192.168.213.0, mientras que AD IPAddress es 192.168.0.238.</span><span class="sxs-lookup"><span data-stu-id="6622d-p117">**ManagementIPPrefix:** ManagementIPPrefix in the Network section must be a different subnet from other internal IPs. For example, as the default value shows, ManagementIPPrefix is 192.168.213.0, while AD IPAddress is 192.168.0.238.</span></span>
    
    <span data-ttu-id="6622d-p118">Los scripts de implementación crean un adaptador de red de administración en cada máquina virtual, asignan una IP de administración y lo conectan a un conmutador virtual de administración. Esto permite al servidor host conectarse a cada máquina virtual y administrarlas mediante esta red de administración. El conmutador virtual de administración se elimina cuando finaliza la administración.</span><span class="sxs-lookup"><span data-stu-id="6622d-p118">The deployment scripts create a management network adapter on each virtual machine, assign a management IP, and connect it to a management virtual switch. This enables the host server to connect to and manage each virtual machine via this management network. The management virtual switch is deleted when the deployment is finished.</span></span>
    
- <span data-ttu-id="6622d-196">**Configuraciones específicas de la máquina virtual base:** La configuración de esta sección debe estar configurada para el cmdlet **Convert-CcIsoToVhdx**.</span><span class="sxs-lookup"><span data-stu-id="6622d-196">**Base VM specific configurations:** Settings in this section must be configured for the **Convert-CcIsoToVhdx** cmdlet.</span></span>
    
    <span data-ttu-id="6622d-p119">Durante la preparación de la imagen de la máquina virtual base, esta se conectará al conmutador de red interno. Las siguiente configuración es fundamental para que la máquina virtual pueda acceder a Internet:</span><span class="sxs-lookup"><span data-stu-id="6622d-p119">During base VM image preparation, the base VM will be connected to the internal network switch. The following settings are critical for the VM to be able to access the Internet:</span></span>
    
  - <span data-ttu-id="6622d-199">[Common]BaseVMIP: la dirección IP de la red corporativa que se asignará a la máquina virtual base.</span><span class="sxs-lookup"><span data-stu-id="6622d-199">[Common]BaseVMIP: the corpnet IP address to be assigned to the base VM.</span></span>
    
  - <span data-ttu-id="6622d-200">[Network]CorpnetDefaultGateway: la puerta de enlace predeterminada que se asignará a la máquina virtual base.</span><span class="sxs-lookup"><span data-stu-id="6622d-200">[Network]CorpnetDefaultGateway: the default gateway to be assigned to the base VM.</span></span>
    
  - <span data-ttu-id="6622d-201">[Network]CorpnetDNSIPAddress: la dirección IP de DNS IP que se asignará a la máquina virtual base.</span><span class="sxs-lookup"><span data-stu-id="6622d-201">[Network]CorpnetDNSIPAddress: the DNS IP address to be assigned to the base VM.</span></span>
    
  - <span data-ttu-id="6622d-202">[Network]WSUSServer: la dirección IP de Windows Server Update Service.</span><span class="sxs-lookup"><span data-stu-id="6622d-202">[Network]WSUSServer: the IP address of Windows Server Update Service.</span></span>
    
  - <span data-ttu-id="6622d-203">[Network]WSUSStatusServer: la dirección IP del servidor de estado de Windows Server Update Service.</span><span class="sxs-lookup"><span data-stu-id="6622d-203">[Network]WSUSStatusServer: the IP address of Windows Server Update Service status server.</span></span>
    
  - <span data-ttu-id="6622d-204">[Network]EnableReferSupport: define si se habilita o se deshabilita el soporte de SIP REFER en la configuración de tronco de su IP/PBX.</span><span class="sxs-lookup"><span data-stu-id="6622d-204">[Network]EnableReferSupport: this will define whether SIP REFER support is enabled or disabled on the Trunk Configuration to your IP/PBX.</span></span>
    
- <span data-ttu-id="6622d-205">**IP internas:**</span><span class="sxs-lookup"><span data-stu-id="6622d-205">**Internal IPs:**</span></span>
    
  - <span data-ttu-id="6622d-206">Asegúrese de que la máscara de subred CorpnetIPPrefixLength es correcta.</span><span class="sxs-lookup"><span data-stu-id="6622d-206">Make sure subnet mask CorpnetIPPrefixLength is correct.</span></span>
    
  - <span data-ttu-id="6622d-207">Asegúrese de que no hay ningún conflicto IP para estas direcciones IP interna.</span><span class="sxs-lookup"><span data-stu-id="6622d-207">Make sure there are no IP conflicts for these internal IPs.</span></span>
    
- <span data-ttu-id="6622d-208">**IP externas:**</span><span class="sxs-lookup"><span data-stu-id="6622d-208">**External IPs:**</span></span>
    
  - <span data-ttu-id="6622d-209">Para IP públicas MR: especifique ExternalMRIPs para que no sean de NAT o ExternalMRPublicIPs para NAT.</span><span class="sxs-lookup"><span data-stu-id="6622d-209">For MR public IP: specify either ExternalMRIPs for non-NAT or ExternalMRPublicIPs for NAT.</span></span>
    
  - <span data-ttu-id="6622d-210">ExternalSIPIPs y ExternalMRIPs puede ser la misma.</span><span class="sxs-lookup"><span data-stu-id="6622d-210">ExternalSIPIPs and ExternalMRIPs can be the same.</span></span>
    
  - <span data-ttu-id="6622d-211">Asegúrese de que la máscara de subred InternetIPPrefixLength es correcta.</span><span class="sxs-lookup"><span data-stu-id="6622d-211">Make sure subnet mask InternetIPPrefixLength is correct.</span></span>
    
  - <span data-ttu-id="6622d-212">Asegúrese de que no hay ningún conflicto IP para estas direcciones IP externas.</span><span class="sxs-lookup"><span data-stu-id="6622d-212">Make sure there are no IP conflicts for these external IPs.</span></span>
    
- <span data-ttu-id="6622d-213">**Puertas de enlace:**</span><span class="sxs-lookup"><span data-stu-id="6622d-213">**Gateways:**</span></span>
    
  - <span data-ttu-id="6622d-p120">Si solo tiene una puerta de enlace, quite la sección de la puerta de enlace secundaria. Si tiene más de dos puertas de enlace, cree secciones adicionales copiando y pegando la existente, y después actualizándola.</span><span class="sxs-lookup"><span data-stu-id="6622d-p120">If you have only one gateway, remove the section for the secondary gateway. If you have more than two gateways, create additional sections by copying and pasting the existing one and then updating it.</span></span>
    
  - <span data-ttu-id="6622d-216">Asegúrese de que la dirección IP y los puertos de las puertas de enlace sean correctos.</span><span class="sxs-lookup"><span data-stu-id="6622d-216">Make sure that the IP address and port of the gateway(s) are correct.</span></span>
    
  - <span data-ttu-id="6622d-217">Para que la puerta de enlace RTC de alta disponibilidad sea compatible, deje la puerta de enlace secundaria y agregue las puertas de enlace secundarias que vaya a usar.</span><span class="sxs-lookup"><span data-stu-id="6622d-217">To support PSTN gateway level HA, leave the secondary gateway, and add any additional gateways you will use.</span></span> <span data-ttu-id="6622d-218">Puede copiar y pegar una entrada existente y, a continuación, actualizarlo.</span><span class="sxs-lookup"><span data-stu-id="6622d-218">You can copy and paste an existing entry and then update it.</span></span>
    
- <span data-ttu-id="6622d-219">Opcionalmente, puede actualizar el valor de LocalRoute para restringir los números de llamada salientes.</span><span class="sxs-lookup"><span data-stu-id="6622d-219">Optionally, you can update the LocalRoute value to restrict outbound call numbers.</span></span>
    
## <a name="download-the-bits-to-the-site-directory"></a><span data-ttu-id="6622d-220">Descargar los bits en el Directorio de sitios</span><span class="sxs-lookup"><span data-stu-id="6622d-220">Download the bits to the Site Directory</span></span>

<span data-ttu-id="6622d-221">Ejecute el siguiente cmdlet para descargar los bits y los archivos de información de la versión en el **Directorio de sitios**:</span><span class="sxs-lookup"><span data-stu-id="6622d-221">Run the following cmdlet to download the bits and version information files to the **Site Directory**:</span></span>
  
```
Start-CcDownload
```

> [!NOTE]
> <span data-ttu-id="6622d-222">Deberá realizar este paso solo para el primer dispositivo.</span><span class="sxs-lookup"><span data-stu-id="6622d-222">You need to perform this step for the first appliance only.</span></span> 
  
## <a name="prepare-base-virtual-disk-vhdx-from-the-downloaded-iso-file"></a><span data-ttu-id="6622d-223">Preparar el disco virtual base (VHDX) desde el archivo ISO descargado</span><span class="sxs-lookup"><span data-stu-id="6622d-223">Prepare base virtual disk (VHDX) from the downloaded ISO file</span></span>

<span data-ttu-id="6622d-224">Este paso prepara un archivo de disco duro virtual (VHDX) de la imagen ISO de Windows Server 2012.</span><span class="sxs-lookup"><span data-stu-id="6622d-224">This step prepares a virtual hard disk (VHDX) file from the Windows Server 2012 ISO image.</span></span> <span data-ttu-id="6622d-225">El VHDX se usará para crear máquinas virtuales durante la implementación.</span><span class="sxs-lookup"><span data-stu-id="6622d-225">The VHDX will be used to create virtual machines during deployment.</span></span> <span data-ttu-id="6622d-226">Se creará una máquina virtual temporal (base VM) y Windows Server 2012 se va a instalar desde el archivo ISO.</span><span class="sxs-lookup"><span data-stu-id="6622d-226">A temporary virtual machine (base VM) will be created and Windows Server 2012 will be installed from the ISO file.</span></span> <span data-ttu-id="6622d-227">Una vez creada la máquina virtual, se instalarán algunos componentes necesarios y se aplicará la actualización de Windows más reciente.</span><span class="sxs-lookup"><span data-stu-id="6622d-227">After the VM is created, some necessary components will be installed and the latest Windows update will be applied.</span></span> <span data-ttu-id="6622d-228">Al final, la máquina virtual base se generalizará (Sysprep) y se limpiará, dejando solo el archivo de disco virtual generado.</span><span class="sxs-lookup"><span data-stu-id="6622d-228">At the end, the base VM will be generalized (sysprep) and cleaned up, leaving only the generated virtual disk file.</span></span>
  
> [!NOTE]
> <span data-ttu-id="6622d-229">Deberá realizar este paso solo para el primer dispositivo.</span><span class="sxs-lookup"><span data-stu-id="6622d-229">You need to perform this step for the first appliance only.</span></span> 
  
<span data-ttu-id="6622d-p123">Antes de continuar con este paso, asegúrese de que se haya creado el conmutador de red corporativa. Además, confirme que las siguientes opciones se hayan configurado correctamente en el archivo CloudConnector.ini:</span><span class="sxs-lookup"><span data-stu-id="6622d-p123">Before proceeding with this step, make sure that the corpnet switch is created. Also, confirm that the following settings are correctly configured in the CloudConnector.ini file:</span></span>
  
- <span data-ttu-id="6622d-232">[Network] CorpnetSwitchName</span><span class="sxs-lookup"><span data-stu-id="6622d-232">[Network]CorpnetSwitchName</span></span>
    
- <span data-ttu-id="6622d-233">[Common] BaseVMIP</span><span class="sxs-lookup"><span data-stu-id="6622d-233">[Common]BaseVMIP</span></span>
    
- <span data-ttu-id="6622d-234">[Network] CorpnetIPPrefixLength</span><span class="sxs-lookup"><span data-stu-id="6622d-234">[Network]CorpnetIPPrefixLength</span></span>
    
- <span data-ttu-id="6622d-235">[Network] CorpnetDefaultGateway</span><span class="sxs-lookup"><span data-stu-id="6622d-235">[Network]CorpnetDefaultGateway</span></span>
    
- <span data-ttu-id="6622d-236">[Network] CorpnetDNSIPAddress</span><span class="sxs-lookup"><span data-stu-id="6622d-236">[Network]CorpnetDNSIPAddress</span></span>
    
<span data-ttu-id="6622d-237">Inicie una consola de PowerShell como administrador y ejecute el siguiente cmdlet para convertir la imagen ISO a un disco duro virtual (VHD):</span><span class="sxs-lookup"><span data-stu-id="6622d-237">Start a PowerShell console as administrator and run the following cmdlet to convert the ISO image to a virtual hard disk (VHD):</span></span>
  
```
Convert-CcIsoToVhdx -IsoFilePath <Windows ISO File Path, including file name>
```

<span data-ttu-id="6622d-p124">Especifique la ruta de acceso completa, incluido el nombre del archivo, a la imagen ISO. Por ejemplo: C:\ISO\WindowsServer2012R2.iso.</span><span class="sxs-lookup"><span data-stu-id="6622d-p124">Specify the full path, including file name, to the ISO image. For example: C:\ISO\WindowsServer2012R2.iso.</span></span>
  
<span data-ttu-id="6622d-240">El archivo VHD creado se almacena en la carpeta de \Bits\VHD del **Directorio de sitios** .</span><span class="sxs-lookup"><span data-stu-id="6622d-240">The created VHD file is stored in the **Site Directory** \Bits\VHD folder.</span></span> <span data-ttu-id="6622d-241">Puede obtener la ruta de acceso al **Directorio de sitios** ejecutando **Get-CcSiteDirectory**.</span><span class="sxs-lookup"><span data-stu-id="6622d-241">You can get the path to the **Site Directory** by running the **Get-CcSiteDirectory**.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="6622d-242">De manera predeterminada, la configuración del proxy no se configura en la máquina virtual base.</span><span class="sxs-lookup"><span data-stu-id="6622d-242">By default, proxy settings are not configured on the base VM.</span></span> <span data-ttu-id="6622d-243">Si se requiere un servidor proxy en su entorno de red para actualizar la máquina virtual a través de Windows Update, debe agregar el modificador - PauseBeforeUpdate cuando se ejecuta "Convert-CcIsoToVhdx".</span><span class="sxs-lookup"><span data-stu-id="6622d-243">If a proxy is required in your network environment to update the VM via Windows Update, you should add the -PauseBeforeUpdate switch when you run "Convert-CcIsoToVhdx".</span></span> <span data-ttu-id="6622d-244">La secuencia de comandos hará una pausa antes de la actualización de Windows y tendrá una oportunidad para configurar manualmente el proxy en la máquina virtual.</span><span class="sxs-lookup"><span data-stu-id="6622d-244">The script will pause before Windows Update and you'll have a chance to manually set up proxy on the VM.</span></span> <span data-ttu-id="6622d-245">Después de que se configure el proxy y que la máquina virtual pueda acceder a Internet, podrá reanudar el script para completar los pasos restantes.</span><span class="sxs-lookup"><span data-stu-id="6622d-245">After the proxy is setup and the VM can access Internet, you can resume the script to complete the remaining steps.</span></span> 
  
### <a name="create-vhds-for-a-multi-site-deployment"></a><span data-ttu-id="6622d-246">Crear VHD para una implementación de varios sitios</span><span class="sxs-lookup"><span data-stu-id="6622d-246">Create VHDs for a multi-site deployment</span></span>

<span data-ttu-id="6622d-247">Este es un paso opcional que solo se aplica a las implementaciones de varios sitios.</span><span class="sxs-lookup"><span data-stu-id="6622d-247">This is an optional step that applies only to multi-site deployments.</span></span>
  
<span data-ttu-id="6622d-p127">Si va a realizar una implementación de varios sitios, no necesita convertir el ISO en VHD para cada sitio. Puede copiar el VHDX creado para el primer sitio en el servidor host de un segundo sitio.</span><span class="sxs-lookup"><span data-stu-id="6622d-p127">If you are deploying a multi-site deployment, you do not need to convert the ISO to a VHD for each site. You can copy the VHDX created for the first site to the host server for a second site.</span></span>
  
 <span data-ttu-id="6622d-250">Copie el archivo en la misma ubicación de archivo ( **Directorio de sitios** \Bits\VHD carpeta) y con el mismo nombre de archivo, en el servidor host para un sitio adicional.</span><span class="sxs-lookup"><span data-stu-id="6622d-250">Copy the file to the same file location ( **Site Directory** \Bits\VHD folder), and with the same file name, on the host server for an additional site.</span></span>
  
## <a name="set-the-powershell-execution-policy-to-remotesigned"></a><span data-ttu-id="6622d-251">Establecer la directiva de ejecución de PowerShell en RemoteSigned</span><span class="sxs-lookup"><span data-stu-id="6622d-251">Set the PowerShell Execution policy to RemoteSigned</span></span>

<span data-ttu-id="6622d-p128">Los scripts de PowerShell proporcionados requieren que la directiva de ejecución se establezca en RemoteSigned. Para ver la configuración actual, abra una consola de PowerShell como administrador y después ejecute el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="6622d-p128">The PowerShell scripts provided require that the execution policy be set to RemoteSigned. To see the current setting, open a PowerShell console as administrator and then run the following cmdlet:</span></span>
  
```
Get-ExecutionPolicy
```

<span data-ttu-id="6622d-254">Si no se establece como "RemoteSigned", ejecute el siguiente cmdlet para cambiarlo:</span><span class="sxs-lookup"><span data-stu-id="6622d-254">If it is not set to "RemoteSigned," run the following cmdlet to change it:</span></span>
  
```
Set-ExecutionPolicy RemoteSigned
```

## <a name="change-local-group-policy-on-the-host-machine-versions-141-and-earlier"></a><span data-ttu-id="6622d-255">Cambiar la directiva de grupo local del equipo host (versiones 1.4.1 y anteriores)</span><span class="sxs-lookup"><span data-stu-id="6622d-255">Change local Group Policy on the host machine (versions 1.4.1 and earlier)</span></span>

> [!NOTE]
> <span data-ttu-id="6622d-256">Esta tarea no se requiere para la versión 1.4.2 de Cloud Connector y otras versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="6622d-256">This task is not required for Cloud Connector versions 1.4.2 and later.</span></span> 
  
<span data-ttu-id="6622d-257">La cuenta CceService se crea durante la implementación de Skype Empresarial Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="6622d-257">The CceService account is created during the Skype for Business Cloud Connector Edition deployment.</span></span> <span data-ttu-id="6622d-258">Se ejecuta el servicio de administración del conector de la nube y requiere permiso para desinstalar el cloudconnector.msi.</span><span class="sxs-lookup"><span data-stu-id="6622d-258">It runs the Cloud Connector Management Service and requires permission to uninstall the cloudconnector.msi.</span></span> <span data-ttu-id="6622d-259">Debe cambiar la configuración de la directiva de grupo del equipo host de Cloud Connector para especificar que el registro de usuarios no se descargue cuando el usuario cierre sesión.</span><span class="sxs-lookup"><span data-stu-id="6622d-259">You must change the group policy setting on the Cloud Connector host machine to specify that the user registry should not be unloaded when the user logs off.</span></span> <span data-ttu-id="6622d-260">Siga los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="6622d-260">Follow the steps below:</span></span>
  
### <a name="to-change-the-group-policy-setting"></a><span data-ttu-id="6622d-261">Para cambiar la configuración de la directiva de grupo</span><span class="sxs-lookup"><span data-stu-id="6622d-261">To change the Group Policy setting</span></span>

1. <span data-ttu-id="6622d-262">Abra el **Editor de directiva de grupo** mediante la ejecución de gpedit.msc.</span><span class="sxs-lookup"><span data-stu-id="6622d-262">Open the **Group Policy Editor** by running gpedit.msc.</span></span>
    
2. <span data-ttu-id="6622d-263">En el **Editor de directivas de grupo**, navegue a Plantillas administrativas > Sistema > Perfil de usuario > No descargar forzosamente el Registro de usuarios al cerrar la sesión de usuario. </span><span class="sxs-lookup"><span data-stu-id="6622d-263">In the **Group Policy Editor**, navigate to Administrative Templates > System > UserProfile > Do not forcefully unload the user registry at user logoff.</span></span> 
    
3. <span data-ttu-id="6622d-264">Establezca su valor en **habilitado**.</span><span class="sxs-lookup"><span data-stu-id="6622d-264">Set its value to **Enabled**.</span></span>
    
## <a name="set-up-your-office-365-tenant"></a><span data-ttu-id="6622d-265">Configurar el inquilino de Office 365</span><span class="sxs-lookup"><span data-stu-id="6622d-265">Set up your Office 365 tenant</span></span>

<span data-ttu-id="6622d-266">Se requiere un inquilino de Office 365 con Skype para profesionales en línea y el sistema de teléfono en Office 365.</span><span class="sxs-lookup"><span data-stu-id="6622d-266">An Office 365 tenant with Skype for Business Online and Phone System in Office 365 is required.</span></span> <span data-ttu-id="6622d-267">Asegúrese de que el inquilino es y que esté configurado antes de intentar usar el conector de la nube.</span><span class="sxs-lookup"><span data-stu-id="6622d-267">Make sure your tenant is set up and configured before attempting to use Cloud Connector.</span></span>
  
<span data-ttu-id="6622d-268">Algunos pasos del programa de instalación de Office 365 requieren que se use PowerShell remoto de inquilino (TRPS) para configurar al inquilino de Office 365.</span><span class="sxs-lookup"><span data-stu-id="6622d-268">Some Office 365 setup steps require you to use Tenant Remote PowerShell (TRPS) to configure your Office 365 tenant.</span></span> <span data-ttu-id="6622d-269">**Se debe instalar en el servidor host.**</span><span class="sxs-lookup"><span data-stu-id="6622d-269">**This should be installed on the host server.**</span></span> <span data-ttu-id="6622d-270">Puede descargar el Skype para módulo empresarial en línea para PowerShell desde: [Skype para Online de negocio, módulo de Windows PowerShell](https://www.microsoft.com/en-us/download/details.aspx?id=39366).</span><span class="sxs-lookup"><span data-stu-id="6622d-270">You can download the Skype for Business Online module for PowerShell from: [Skype for Business Online, Windows PowerShell Module](https://www.microsoft.com/en-us/download/details.aspx?id=39366).</span></span>
  
<span data-ttu-id="6622d-271">Crear un Skype dedicada para la cuenta de administrador empresarial para la administración en línea de conector en la nube, por ejemplo CceOnlineManagmentAdministrator.</span><span class="sxs-lookup"><span data-stu-id="6622d-271">Create a dedicated Skype for Business administrator account for Cloud Connector online management, for example CceOnlineManagmentAdministrator.</span></span> <span data-ttu-id="6622d-272">Esta cuenta la usará la aplicación para agregar o quitar aplicaciones, habilitar o deshabilitar actualizaciones automáticas del sistema operativo, habilitar o deshabilitar actualizaciones automáticas de archivos binarios.</span><span class="sxs-lookup"><span data-stu-id="6622d-272">This account will be used by appliance to add or remove appliance, enable or disable automatic OS update, enable or disable automatic binary update.</span></span> <span data-ttu-id="6622d-273">Establezca la contraseña para que esta cuenta no expire nunca y no haya que cambiarla para el servicio cada vez que expire.</span><span class="sxs-lookup"><span data-stu-id="6622d-273">Set the password for this account to never expire so that you do not need to change it for the service each time it expires.</span></span>
  

