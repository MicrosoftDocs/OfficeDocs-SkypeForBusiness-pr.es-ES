---
title: Preparar el dispositivo de Cloud Connector
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/15/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.custom: Strat_SB_Hybrid
ms.assetid: 6eacfa99-9759-4c13-aca3-8992c2ff2710
description: Obtenga información sobre cómo preparar su dispositivo conector de nube para la implementación y uso con sistema de teléfono en Office 365 (nube PBX).
ms.openlocfilehash: 8dcc15d2feb12516025afb5e60d916f94a81fa57
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="prepare-your-cloud-connector-appliance"></a><span data-ttu-id="a5a3b-103">Preparar el dispositivo de Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="a5a3b-103">Prepare your Cloud Connector appliance</span></span>
 
<span data-ttu-id="a5a3b-104">Obtenga información sobre cómo preparar su dispositivo conector de nube para la implementación y uso con sistema de teléfono en Office 365 (nube PBX).</span><span class="sxs-lookup"><span data-stu-id="a5a3b-104">Learn about how to prepare your Cloud Connector appliance for deployment and use with Phone System in Office 365 (Cloud PBX).</span></span>
  
<span data-ttu-id="a5a3b-105">En esta sección se describe cómo obtener los archivos de instalación de Skype Empresarial Cloud Connector Edition, instalar el software Cloud Connector y preparar el dispositivo de Cloud Connector para la implementación.</span><span class="sxs-lookup"><span data-stu-id="a5a3b-105">This section describes how to get the Skype for Business Cloud Connector Edition installation files, install Cloud Connector software, and prepare your Cloud Connector appliance for deployment.</span></span> <span data-ttu-id="a5a3b-106">Después de completar todos los pasos de esta sección, estará listo para implementar Cloud Connector para un único sitio o para varios sitios.</span><span class="sxs-lookup"><span data-stu-id="a5a3b-106">After you have completed all steps in this section, you will be ready to deploy Cloud Connector for a single site or multiple sites.</span></span> <span data-ttu-id="a5a3b-107">Si tiene una implementación de nube conector existente y aún no ha actualizado a la nube conector versión 2.1, consulte [actualizar a una nueva versión del conector de la nube](upgrade-to-a-new-version-of-cloud-connector.md).</span><span class="sxs-lookup"><span data-stu-id="a5a3b-107">If you have an existing Cloud Connector deployment, and you have not yet upgraded to Cloud Connector version 2.1, see [Upgrade to a new version of Cloud Connector](upgrade-to-a-new-version-of-cloud-connector.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="a5a3b-108">Microsoft es compatible con la versión actual de nube conector Edition, versión 2.1.</span><span class="sxs-lookup"><span data-stu-id="a5a3b-108">Microsoft supports the current version of Cloud Connector Edition, version 2.1.</span></span> <span data-ttu-id="a5a3b-109">Si ha configurado la actualización automática, Cloud Connector se actualizará automáticamente.</span><span class="sxs-lookup"><span data-stu-id="a5a3b-109">If you configured automatic update, Cloud Connector will update automatically.</span></span> <span data-ttu-id="a5a3b-110">Si ha configurado la actualización manual, debe actualizar a la versión 2.1 dentro de 60 días de su publicación.</span><span class="sxs-lookup"><span data-stu-id="a5a3b-110">If you configured manual update, you will need to upgrade to version 2.1 within 60 days of its release.</span></span> <span data-ttu-id="a5a3b-111">Microsoft soportará la versión anterior de 60 días después del lanzamiento de 2.1 para permitir tiempo para actualizar.</span><span class="sxs-lookup"><span data-stu-id="a5a3b-111">Microsoft will support the previous version for 60 days after the release of 2.1 to allow you time to upgrade.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="a5a3b-112">Conector de nube versión 2.1 y posteriores, el dispositivo host debe tener.NET Framework 4.6.1 o posterior instalado.</span><span class="sxs-lookup"><span data-stu-id="a5a3b-112">For Cloud Connector version 2.1 and later, the host appliance must have .NET Framework 4.6.1 or later installed.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="a5a3b-113">Para una implementación correcta, al ejecutar los cmdlets para configurar Skype para conector de nube Business Edition, utilice siempre la misma sesión de consola como aquella que inició en el.</span><span class="sxs-lookup"><span data-stu-id="a5a3b-113">For successful deployment, when you run the cmdlets to configure Skype for Business Cloud Connector Edition, always use the same console session as the one you started in.</span></span> <span data-ttu-id="a5a3b-114">Evite cambiar a diferentes sesiones durante la implementación y la configuración.</span><span class="sxs-lookup"><span data-stu-id="a5a3b-114">Avoid switching to different sessions during the deployment and configuration.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="a5a3b-115">Hay algunos pasos que solo se realizan para el primer dispositivo de la implementación: la creación de un recurso compartido del directorio de sitios, la descarga de los bits y la preparación de un archivo de disco duro virtual (VHDX) desde la imagen ISO de Windows Server.</span><span class="sxs-lookup"><span data-stu-id="a5a3b-115">There are some steps that you perform only for the first appliance in your deployment: creating a share for the site directory, downloading the bits, and preparing a virtual hard disk (VHDX) file from the Windows Server ISO image.</span></span> 
  
## <a name="download-the-skype-for-business-cloud-connector-edition-installer"></a><span data-ttu-id="a5a3b-116">Descargar el instalador de Skype Empresarial Cloud Connector Edition</span><span class="sxs-lookup"><span data-stu-id="a5a3b-116">Download the Skype for Business Cloud Connector Edition installer</span></span>

1. <span data-ttu-id="a5a3b-117">En el servidor host donde se ejecutará las VMs de conector de nube, descargar los archivos de instalación: [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller).</span><span class="sxs-lookup"><span data-stu-id="a5a3b-117">On the host server where the Cloud Connector VMs will run, download the installation files: [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller).</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="a5a3b-118">El servidor host debe poder acceder a Internet durante la instalación de Cloud Connector porque se descargan archivos adicionales durante la instalación.</span><span class="sxs-lookup"><span data-stu-id="a5a3b-118">The host server must be able to access the Internet during the installation of Cloud Connector because additional files are downloaded during the installation.</span></span> 
  
2. <span data-ttu-id="a5a3b-119">Ejecute el instalador y acepte los valores predeterminados durante la instalación.</span><span class="sxs-lookup"><span data-stu-id="a5a3b-119">Run the installer and accept the default values during the installation.</span></span>
    
3. <span data-ttu-id="a5a3b-120">Confirme que la instalación se ha completado correctamente.</span><span class="sxs-lookup"><span data-stu-id="a5a3b-120">Confirm that the installation completed successfully.</span></span>
    
## <a name="verify-the-installation-and-configure-the-environment"></a><span data-ttu-id="a5a3b-121">Comprobar la instalación y configurar el entorno</span><span class="sxs-lookup"><span data-stu-id="a5a3b-121">Verify the installation and configure the environment</span></span>

1. <span data-ttu-id="a5a3b-122">Abrir una consola de PowerShell como administrador y confirme que el Skype para conector de nube Business Edition cmdlets están disponibles mediante el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="a5a3b-122">Open a PowerShell console as administrator and confirm that the Skype for Business Cloud Connector Edition cmdlets are available using the following cmdlet:</span></span>
    
  ```
  Get-Command *-Cc*
  ```

    <span data-ttu-id="a5a3b-123">El comando debe devolver una lista de cmdlets de Skype para conector de nube Business Edition.</span><span class="sxs-lookup"><span data-stu-id="a5a3b-123">The command should return a list of cmdlets for Skype for Business Cloud Connector Edition.</span></span>
    
2. <span data-ttu-id="a5a3b-124">Los archivos VHDs, SfBBits y VersionInfo se almacenarán en el **Directorio de sitios**.</span><span class="sxs-lookup"><span data-stu-id="a5a3b-124">The VHDs, SfBBits, and VersionInfo files will be stored in the **Site Directory**.</span></span>
    
    <span data-ttu-id="a5a3b-125">Puede encontrar la ubicación del **Directorio de sitios** con el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="a5a3b-125">You can find the location of the **Site Directory** with the following cmdlet:</span></span>
    
  ```
  Get-CcSiteDirectory
  ```

    <span data-ttu-id="a5a3b-126">El comando debe devolver una ubicación de su sistema de archivos.</span><span class="sxs-lookup"><span data-stu-id="a5a3b-126">The command should return a location in your file system.</span></span> <span data-ttu-id="a5a3b-127">La ubicación puede ser una carpeta local o un recurso compartido de archivos.</span><span class="sxs-lookup"><span data-stu-id="a5a3b-127">The location can be a local folder or a file share.</span></span> <span data-ttu-id="a5a3b-128">La ubicación predeterminada del **Directorio de sitios** es: %USERPROFILE%\CloudConnector\SiteRoot.</span><span class="sxs-lookup"><span data-stu-id="a5a3b-128">The default location for the **Site Directory** is: %USERPROFILE%\CloudConnector\SiteRoot.</span></span> <span data-ttu-id="a5a3b-129">La ubicación predeterminada se debe cambiar a un recurso compartido de archivos en la primera aplicación que se cree en cada sitio.</span><span class="sxs-lookup"><span data-stu-id="a5a3b-129">The default location should be changed to a file share on the first appliance created in each site.</span></span>
    
    <span data-ttu-id="a5a3b-130">La ubicación que seleccione debe:</span><span class="sxs-lookup"><span data-stu-id="a5a3b-130">The location you select must be:</span></span>
    
  - <span data-ttu-id="a5a3b-131">Crearse en el primer dispositivo creado en cada sitio.</span><span class="sxs-lookup"><span data-stu-id="a5a3b-131">Created on the first appliance created in each site.</span></span>
    
  - <span data-ttu-id="a5a3b-132">Ser una carpeta compartida a la que pueden acceder los servidores host (dispositivos) del mismo sitio.</span><span class="sxs-lookup"><span data-stu-id="a5a3b-132">A shared folder that is accessible by the other host servers (appliances) in the same site.</span></span>
    
    <span data-ttu-id="a5a3b-133">Para establecer el **Directorio de sitios** en una ubicación distinta de la predeterminada, ejecute el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="a5a3b-133">To set the **Site Directory** to a location other than the default, run the following cmdlet:</span></span>
    
  ```
  Set-CcSiteDirectory <UNC File path>
  ```

    <span data-ttu-id="a5a3b-134">Si va a implementar la alta disponibilidad (HA) para el sitio, asegúrese de ejecutar el cmdlet para establecer el **Directorio de sitios** en la misma ubicación en cada servidor host del sitio.</span><span class="sxs-lookup"><span data-stu-id="a5a3b-134">If you are deploying High Availability (HA) for the site, make sure you run the cmdlet to set the **Site Directory** to the same location on each host server within the site.</span></span>
    
    <span data-ttu-id="a5a3b-135">Al iniciar sesión e implementar cada dispositivo en el sitio, asegúrese de que su cuenta de inicio de sesión actual tiene el derecho de acceso al **Directorio de sitios**.</span><span class="sxs-lookup"><span data-stu-id="a5a3b-135">When you log on and deploy each appliance in the site, make sure your current logon account has the right access to the **Site Directory**.</span></span>
    
3. <span data-ttu-id="a5a3b-136">El **Directorio del dispositivo** es el directorio raíz de trabajo local de Skype para conector de nube Business Edition y la ubicación donde se guardan los certificados externos, instancias y registros.</span><span class="sxs-lookup"><span data-stu-id="a5a3b-136">The **Appliance Directory** is the local working root directory for Skype for Business Cloud Connector Edition, and the location where external certificates, instances, and logs are saved.</span></span> <span data-ttu-id="a5a3b-137">La ubicación predeterminada es: %USERPROFILE%\CloudConnector\ApplianceRoot.</span><span class="sxs-lookup"><span data-stu-id="a5a3b-137">The default location is: %USERPROFILE%\CloudConnector\ApplianceRoot.</span></span>
    
    <span data-ttu-id="a5a3b-138">Para encontrar la ubicación del **Directorio de aplicaciones**, ejecute el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="a5a3b-138">To find the location of the **Appliance Directory**, run the following cmdlet:</span></span>
    
  ```
  Get-CcApplianceDirectory
  ```

    <span data-ttu-id="a5a3b-139">Para establecer el **Directorio de aplicaciones** en una ubicación distinta de la predeterminada, ejecute el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="a5a3b-139">To set the **Appliance Directory** to a location other than the default, run the following cmdlet:</span></span>
    
  ```
  Set-CcApplianceDirectory <File path>
  ```

    <span data-ttu-id="a5a3b-140">El directorio de dispositivos debe establecerse en una carpeta local del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="a5a3b-140">The Appliance Directory should be set to a local folder on the appliance.</span></span> <span data-ttu-id="a5a3b-141">Sólo debe configurar el **Directorio del dispositivo** antes de iniciar el Skype para la implementación del conector de nube Business Edition.</span><span class="sxs-lookup"><span data-stu-id="a5a3b-141">You should only set the **Appliance Directory** before you start the Skype for Business Cloud Connector Edition deployment.</span></span> <span data-ttu-id="a5a3b-142">Si lo cambia después, tendrá que volver a implementar el servidor host.</span><span class="sxs-lookup"><span data-stu-id="a5a3b-142">If you change it after deployment, you'll need to redeploy the host server.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="a5a3b-143">La ruta de acceso al **Directorio de aplicaciones** no puede contener espacios.</span><span class="sxs-lookup"><span data-stu-id="a5a3b-143">The path to the **Appliance Directory** must not contain any spaces.</span></span>
  
## <a name="set-the-path-for-the-external-edge-certificate"></a><span data-ttu-id="a5a3b-144">Establecer la ruta de acceso del certificado perimetral externo</span><span class="sxs-lookup"><span data-stu-id="a5a3b-144">Set the path for the external Edge certificate</span></span>

- <span data-ttu-id="a5a3b-p107">Ejecute el siguiente cmdlet para establecer la ruta de acceso, incluido el nombre del archivo, al certificado perimetral externo. Por ejemplo: C:\certs\cce\ap.contoso.com.pfx. El certificado no puede contener claves privadas.</span><span class="sxs-lookup"><span data-stu-id="a5a3b-p107">Run the following cmdlet to set the path, including the file name, to the external Edge certificate. For example: C:\certs\cce\ap.contoso.com.pfx. The certificate must contain private keys.</span></span>
    
  ```
  Set-CcExternalCertificateFilePath -Path <Full path to External certificate, including file name> -Target EdgeServer
  ```

    > [!NOTE]
    > <span data-ttu-id="a5a3b-148">Tenga en cuenta que el parámetro -Target es específico de la versión 1.4.2 y las versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="a5a3b-148">Note that the -Target parameter is specific to versions 1.4.2 and later.</span></span> 
  
    <span data-ttu-id="a5a3b-149">Especifique la ruta de acceso completa al certificado externo, incluido el nombre del archivo.</span><span class="sxs-lookup"><span data-stu-id="a5a3b-149">Specify the full path to the external certificate, including the file name.</span></span> <span data-ttu-id="a5a3b-150">El certificado se puede almacenar localmente o en un recurso compartido de archivos.</span><span class="sxs-lookup"><span data-stu-id="a5a3b-150">The certificate can be stored locally or on a file share.</span></span> <span data-ttu-id="a5a3b-151">Si el certificado se almacena en una carpeta compartida, esta deberá crearse en el primer dispositivo de cada sitio y los demás dispositivos que pertenezcan al mismo sitio deben poder acceder a ella.</span><span class="sxs-lookup"><span data-stu-id="a5a3b-151">If the certificate is stored in a shared folder, the shared folder must be created on the first appliance of each site and must be accessible by other appliances belonging to the same site.</span></span> <span data-ttu-id="a5a3b-152">Este cmdlet copia el certificado externo en el **directorio de dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="a5a3b-152">This cmdlet copies the external certificate to the **Appliance Directory**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="a5a3b-153">**Si se ha actualizado al conector de nube versión 1.4.2 o posterior**, asegúrese de que el certificado externo preparado contiene claves privadas y la cadena de certificados completa incluyendo el certificado de entidad emisora raíz y los certificados de CA intermedios. > **Si tiene Aún no se ha actualizado a la nube conector versión 1.4.2**, asegúrese de que el certificado externo preparado contiene claves privadas.</span><span class="sxs-lookup"><span data-stu-id="a5a3b-153">**If you have updated to Cloud Connector version 1.4.2 or later**, make sure your prepared external certificate contains private keys and the full certificate chain including the root CA certificate and the intermediate CA certificates.> **If you have NOT yet updated to Cloud Connector version 1.4.2**, make sure your prepared external certificate contains private keys.</span></span> <span data-ttu-id="a5a3b-154">Este certificado externo lo debe emitir una entidad de certificación en la que Windows confíe de manera predeterminada.</span><span class="sxs-lookup"><span data-stu-id="a5a3b-154">This external certificate must be issued by a Certificate Authority that is trusted by Windows by default.</span></span>
  
## <a name="set-the-path-for-the-external-pstn-gatewaysbc-certificate"></a><span data-ttu-id="a5a3b-155">Establecer la ruta para el certificado externo de SBC/puerta de enlace PSTN</span><span class="sxs-lookup"><span data-stu-id="a5a3b-155">Set the path for the external PSTN gateway/SBC certificate</span></span>

<span data-ttu-id="a5a3b-156">Si va a utilizar TLS entre el servidor de mediación y la puerta de enlace RTC/SBC, ejecute el siguiente cmdlet para establecer la ruta de acceso, incluido el nombre de archivo, al certificado de la puerta de enlace.</span><span class="sxs-lookup"><span data-stu-id="a5a3b-156">If you are using TLS between the Mediation Server and the PSTN gateway/SBC, run the following cmdlet to set the path, including the file name, to the gateway certificate.</span></span> <span data-ttu-id="a5a3b-157">Por ejemplo: C:\certs\cce\sbc.contoso.com.cer.</span><span class="sxs-lookup"><span data-stu-id="a5a3b-157">For example: C:\certs\cce\sbc.contoso.com.cer.</span></span> <span data-ttu-id="a5a3b-158">El certificado debe contener la CA raíz y la cadena intermedia del certificado asignado a la puerta de enlace:</span><span class="sxs-lookup"><span data-stu-id="a5a3b-158">The certificate must contain the root CA and the intermediate chain for the certificate assigned to the gateway:</span></span>
  
```
Set-CcExternalCertificateFilePath -Path <Full path to gateway certificate, including file name> -Target MediationServer 

```

> [!NOTE]
> <span data-ttu-id="a5a3b-159">Tenga en cuenta que el parámetro -Target es específico de la versión 1.4.2 y las versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="a5a3b-159">Note that the -Target parameter is specific to versions 1.4.2 and later.</span></span> 
  
## <a name="create-virtual-switches-in-hyper-v-manager"></a><span data-ttu-id="a5a3b-160">Crear conmutadores virtuales en el Administrador de Hyper-V</span><span class="sxs-lookup"><span data-stu-id="a5a3b-160">Create virtual switches in Hyper-V Manager</span></span>

1. <span data-ttu-id="a5a3b-161">Abra el **Administrador de Hyper-V** > **Virtual Switch Manager**y seleccione el **Nuevo administrador de modificador Virtual**.</span><span class="sxs-lookup"><span data-stu-id="a5a3b-161">Open **Hyper-V Manager** > **Virtual Switch Manager**, and select **New Virtual Switch Manager**.</span></span>
    
2. <span data-ttu-id="a5a3b-162">Cree un conmutador virtual externo y enlácelo al adaptador de red físico que está conectado al dominio de red interno:</span><span class="sxs-lookup"><span data-stu-id="a5a3b-162">Create an External virtual switch and bind it to the physical network adapter that is connected to your internal network domain:</span></span>
    
    <span data-ttu-id="a5a3b-163">Seleccione **Permitir que el sistema operativo de administración comparta este adaptador de red** para este conmutador virtual.</span><span class="sxs-lookup"><span data-stu-id="a5a3b-163">Select **Allow management operating system to share this network adapter** for this virtual switch.</span></span>
    
3. <span data-ttu-id="a5a3b-164">Crear un switch virtual externo y enlazarlo al adaptador de red físico que se enruta a Internet:</span><span class="sxs-lookup"><span data-stu-id="a5a3b-164">Create an External virtual switch and bind it to the physical network adapter that is routed to the Internet:</span></span>
    
    <span data-ttu-id="a5a3b-165">Desactive **Permitir sistema de operativo de administración comparta este adaptador de red** para este switch virtual.</span><span class="sxs-lookup"><span data-stu-id="a5a3b-165">De-select **Allow management operating system to share this network adapter** for this virtual switch.</span></span>
    
4. <span data-ttu-id="a5a3b-166">Establezca el nombre del conmutador que conecta la red perimetral a su dominio de red interna **SfB CCE Corpnet cambie**.</span><span class="sxs-lookup"><span data-stu-id="a5a3b-166">Set the name of the switch that connects your perimeter network to your internal network domain **SfB CCE Corpnet Switch**.</span></span>
    
    <span data-ttu-id="a5a3b-167">Establezca el nombre del conmutador que conecta la red perimetral al Internet **SfB CCE Internet cambie**.</span><span class="sxs-lookup"><span data-stu-id="a5a3b-167">Set the name of the switch that connects your perimeter network to the Internet **SfB CCE Internet Switch**.</span></span>
    
## <a name="update-the-cloudconnectorini-configuration-file"></a><span data-ttu-id="a5a3b-168">Actualizar el archivo de configuración CloudConnector.ini</span><span class="sxs-lookup"><span data-stu-id="a5a3b-168">Update the CloudConnector.ini configuration file</span></span>

<span data-ttu-id="a5a3b-169">Prepare el archivo CloudConnector.ini utilizando la información recopilada en [determinar los parámetros de implementación](plan-skype-for-business-cloud-connector-edition.md#BKMK_SiteParams) en el tema [planificar Skype para conector de nube Business Edition](plan-skype-for-business-cloud-connector-edition.md) .</span><span class="sxs-lookup"><span data-stu-id="a5a3b-169">Prepare the CloudConnector.ini file using the information you gathered in [Determine deployment parameters](plan-skype-for-business-cloud-connector-edition.md#BKMK_SiteParams) in the [Plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md) topic.</span></span>
  
<span data-ttu-id="a5a3b-170">Para actualizar el archivo, ejecute primero el siguiente cmdlet para obtener la plantilla de muestra (CloudConnector.Sample.ini):</span><span class="sxs-lookup"><span data-stu-id="a5a3b-170">To update the file, first run the following cmdlet to get the sample template (CloudConnector.Sample.ini):</span></span>
  
```
Export-CcConfigurationSampleFile
```

<span data-ttu-id="a5a3b-171">La plantilla de muestra está almacenada en el **Directorio de aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="a5a3b-171">The sample template is stored in the **Appliance Directory**.</span></span>
  
<span data-ttu-id="a5a3b-172">Después de actualizarlo con los valores de su entorno, guarde el archivo como CloudConnector.ini en el **Directorio de aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="a5a3b-172">After you update it with the values for your environment, save the file as CloudConnector.ini in the **Appliance Directory**.</span></span> <span data-ttu-id="a5a3b-173">Puede ejecutar **Get-CcApplianceDirectory** para determinar la ruta de acceso al **Directorio del dispositivo**.</span><span class="sxs-lookup"><span data-stu-id="a5a3b-173">You can run **Get-CcApplianceDirectory** to determine the path to the **Appliance Directory**.</span></span>
  
<span data-ttu-id="a5a3b-174">Al actualizar el archivo .ini, tenga en cuenta lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="a5a3b-174">When updating the .ini file, consider the following:</span></span>
  
> [!NOTE]
> <span data-ttu-id="a5a3b-175">No todos los valores del archivo .ini se tratan en esta sección, solo los que tengan una consideración especial.</span><span class="sxs-lookup"><span data-stu-id="a5a3b-175">Not all values for the .ini file are discussed in this section, only those with a special consideration are covered here.</span></span> <span data-ttu-id="a5a3b-176">Para obtener una lista completa, consulte la sección [determinar los parámetros de implementación](plan-skype-for-business-cloud-connector-edition.md#BKMK_SiteParams) del [Plan de Skype para conector de nube Business Edition](plan-skype-for-business-cloud-connector-edition.md) tema. > para obtener más información acerca de qué valores deben cambiarse para dispositivos adicionales o nuevos sitios, consulte [ Único sitio con alta disponibilidad (HA) en comparación con las implementaciones multisitio](deploy-multiple-sites-in-cloud-connector.md#BKMK_SingleSitecomparedtomulti-site) en el tema[implementar varios sitios en el conector de la nube](deploy-multiple-sites-in-cloud-connector.md).</span><span class="sxs-lookup"><span data-stu-id="a5a3b-176">For a full list, see the [Determine deployment parameters](plan-skype-for-business-cloud-connector-edition.md#BKMK_SiteParams) section of the [Plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md) topic.> For more information about what values need to be changed for additional appliances or new sites, see [Single site with High Availability (HA) compared to multi-site deployments](deploy-multiple-sites-in-cloud-connector.md#BKMK_SingleSitecomparedtomulti-site) in the topic[Deploy multiple sites in Cloud Connector](deploy-multiple-sites-in-cloud-connector.md).</span></span> 
  
- <span data-ttu-id="a5a3b-p113">**SiteName:** El valor predeterminado es **Site1**. Debe actualizarlo antes de implementar Cloud Connector, porque al ejecutar **Register-CcAppliance** para registrar un dispositivo en un sitio nuevo o existente, el cmdlet usará **SiteName** para determinar qué sitio se debe registrar.</span><span class="sxs-lookup"><span data-stu-id="a5a3b-p113">**SiteName:** The default value is **Site1**. You must update it before you deploy Cloud Connector, because when you run **Register-CcAppliance** to register an appliance to an existing or new site, the cmdlet will use **SiteName** to determine which site to register.</span></span>
    
     <span data-ttu-id="a5a3b-179">Si desea registrar el dispositivo en un sitio nuevo, el valor de **SiteName** debe ser único y diferente de los sitios existentes.</span><span class="sxs-lookup"><span data-stu-id="a5a3b-179">If you want to register the appliance to a new site, the value of **SiteName** must be unique and different from existing sites.</span></span> <span data-ttu-id="a5a3b-180">Si desea registrar el dispositivo a un sitio existente, el valor de **nombre del sitio** en el archivo .ini debe coincidir con el nombre definido en la configuración de clientes de Office 365.</span><span class="sxs-lookup"><span data-stu-id="a5a3b-180">If you want to register the appliance to an existing site, the value for **SiteName** in .ini file must match the name defined in your Office 365 tenant configuration.</span></span> <span data-ttu-id="a5a3b-181">Si va a copiar un archivo de configuración de un sitio a otro, asegúrese de actualizar el valor de **SiteName** para cada sitio tal como corresponda.</span><span class="sxs-lookup"><span data-stu-id="a5a3b-181">If you are copying a configuration file from one site to another, make sure you update the value for **SiteName** for each site accordingly.</span></span>
    
- <span data-ttu-id="a5a3b-182">**ServerName:** El nombre del servidor no debe contener el nombre de dominio y debe estar limitado a 15 caracteres. </span><span class="sxs-lookup"><span data-stu-id="a5a3b-182">**ServerName:** The server name should not contain the domain name and should be limited to 15 characters.</span></span>
    
- <span data-ttu-id="a5a3b-183">**HardwareType:** Si no establece o deje el valor en null, se utilizará el valor predeterminado **normal** .</span><span class="sxs-lookup"><span data-stu-id="a5a3b-183">**HardwareType:** If you don't set or leave the value to null, the default value of **Normal** will be used.</span></span> <span data-ttu-id="a5a3b-184">Utilice **Normal** si planea implementar la mayor versión de conector de nube para admitir 500 llamadas simultáneas por máquina del host como se describe en el [Plan de Skype para conector de nube Business Edition](plan-skype-for-business-cloud-connector-edition.md).</span><span class="sxs-lookup"><span data-stu-id="a5a3b-184">Use **Normal** if you plan to deploy the larger version of Cloud Connector to support 500 simultaneous calls per host machine as described in [Plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md).</span></span> <span data-ttu-id="a5a3b-185">Use **Minimum** para una versión más pequeña que admita 50 llamadas simultáneas.</span><span class="sxs-lookup"><span data-stu-id="a5a3b-185">Use **Minimum** for a smaller deployment that supports 50 simultaneous calls.</span></span>
    
- <span data-ttu-id="a5a3b-186">**Switches virtuales de Internet y red corporativa/administración:**: agregar el nombre de los switches virtuales que haya creado.</span><span class="sxs-lookup"><span data-stu-id="a5a3b-186">**Internet/Corpnet/Management virtual switches:**: Add the name of the virtual switches you have created.</span></span> <span data-ttu-id="a5a3b-187">Para la administración del switch virtual, deje el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="a5a3b-187">For the management virtual switch, leave the default value.</span></span> <span data-ttu-id="a5a3b-188">El script de implementación creará el switch virtual de administración al principio de la implementación y eliminarlo cuando finalice la implementación.</span><span class="sxs-lookup"><span data-stu-id="a5a3b-188">The deployment script will create the management virtual switch at the beginning of deployment and delete it when the deployment finishes.</span></span>
    
- <span data-ttu-id="a5a3b-p117">**ManagementIPPrefix:** ManagementIPPrefix en la sección de Red debe ser una subred diferente de otras IP internas. Por ejemplo, tal como muestra el valor predeterminado, ManagementIPPrefix es 192.168.213.0, mientras que AD IPAddress es 192.168.0.238.</span><span class="sxs-lookup"><span data-stu-id="a5a3b-p117">**ManagementIPPrefix:** ManagementIPPrefix in the Network section must be a different subnet from other internal IPs. For example, as the default value shows, ManagementIPPrefix is 192.168.213.0, while AD IPAddress is 192.168.0.238.</span></span>
    
    <span data-ttu-id="a5a3b-p118">Los scripts de implementación crean un adaptador de red de administración en cada máquina virtual, asignan una IP de administración y lo conectan a un conmutador virtual de administración. Esto permite al servidor host conectarse a cada máquina virtual y administrarlas mediante esta red de administración. El conmutador virtual de administración se elimina cuando finaliza la administración.</span><span class="sxs-lookup"><span data-stu-id="a5a3b-p118">The deployment scripts create a management network adapter on each virtual machine, assign a management IP, and connect it to a management virtual switch. This enables the host server to connect to and manage each virtual machine via this management network. The management virtual switch is deleted when the deployment is finished.</span></span>
    
- <span data-ttu-id="a5a3b-194">**Configuraciones específicas de VM de base:** Opciones en esta sección se deben configurar para el cmdlet **Convertir CcIsoToVhdx** .</span><span class="sxs-lookup"><span data-stu-id="a5a3b-194">**Base VM specific configurations:** Settings in this section must be configured for the **Convert-CcIsoToVhdx** cmdlet.</span></span>
    
    <span data-ttu-id="a5a3b-p119">Durante la preparación de la imagen de la máquina virtual base, esta se conectará al conmutador de red interno. Las siguiente configuración es fundamental para que la máquina virtual pueda acceder a Internet:</span><span class="sxs-lookup"><span data-stu-id="a5a3b-p119">During base VM image preparation, the base VM will be connected to the internal network switch. The following settings are critical for the VM to be able to access the Internet:</span></span>
    
  - <span data-ttu-id="a5a3b-197">[Common]BaseVMIP: la dirección IP de la red corporativa que se asignará a la máquina virtual base.</span><span class="sxs-lookup"><span data-stu-id="a5a3b-197">[Common]BaseVMIP: the corpnet IP address to be assigned to the base VM.</span></span>
    
  - <span data-ttu-id="a5a3b-198">[Network]CorpnetDefaultGateway: la puerta de enlace predeterminada que se asignará a la máquina virtual base.</span><span class="sxs-lookup"><span data-stu-id="a5a3b-198">[Network]CorpnetDefaultGateway: the default gateway to be assigned to the base VM.</span></span>
    
  - <span data-ttu-id="a5a3b-199">[Network]CorpnetDNSIPAddress: la dirección IP de DNS IP que se asignará a la máquina virtual base.</span><span class="sxs-lookup"><span data-stu-id="a5a3b-199">[Network]CorpnetDNSIPAddress: the DNS IP address to be assigned to the base VM.</span></span>
    
  - <span data-ttu-id="a5a3b-200">[Network]WSUSServer: la dirección IP de Windows Server Update Service.</span><span class="sxs-lookup"><span data-stu-id="a5a3b-200">[Network]WSUSServer: the IP address of Windows Server Update Service.</span></span>
    
  - <span data-ttu-id="a5a3b-201">[Network]WSUSStatusServer: la dirección IP del servidor de estado de Windows Server Update Service.</span><span class="sxs-lookup"><span data-stu-id="a5a3b-201">[Network]WSUSStatusServer: the IP address of Windows Server Update Service status server.</span></span>
    
  - <span data-ttu-id="a5a3b-202">[Network]EnableReferSupport: define si se habilita o se deshabilita el soporte de SIP REFER en la configuración de tronco de su IP/PBX.</span><span class="sxs-lookup"><span data-stu-id="a5a3b-202">[Network]EnableReferSupport: this will define whether SIP REFER support is enabled or disabled on the Trunk Configuration to your IP/PBX.</span></span>
    
- <span data-ttu-id="a5a3b-203">**IP internas:**</span><span class="sxs-lookup"><span data-stu-id="a5a3b-203">**Internal IPs:**</span></span>
    
  - <span data-ttu-id="a5a3b-204">Asegúrese de que la máscara de subred CorpnetIPPrefixLength es correcta.</span><span class="sxs-lookup"><span data-stu-id="a5a3b-204">Make sure subnet mask CorpnetIPPrefixLength is correct.</span></span>
    
  - <span data-ttu-id="a5a3b-205">Asegúrese de que no existen conflictos IP para estas direcciones IP internas.</span><span class="sxs-lookup"><span data-stu-id="a5a3b-205">Make sure there are no IP conflicts for these internal IPs.</span></span>
    
- <span data-ttu-id="a5a3b-206">**IP externas:**</span><span class="sxs-lookup"><span data-stu-id="a5a3b-206">**External IPs:**</span></span>
    
  - <span data-ttu-id="a5a3b-207">Para IP pública MR: especifique ExternalMRIPs para NAT no o ExternalMRPublicIPs para NAT.</span><span class="sxs-lookup"><span data-stu-id="a5a3b-207">For MR public IP: specify either ExternalMRIPs for non-NAT or ExternalMRPublicIPs for NAT.</span></span>
    
  - <span data-ttu-id="a5a3b-208">ExternalSIPIPs y ExternalMRIPs pueden ser el mismo.</span><span class="sxs-lookup"><span data-stu-id="a5a3b-208">ExternalSIPIPs and ExternalMRIPs can be the same.</span></span>
    
  - <span data-ttu-id="a5a3b-209">Asegúrese de que la máscara de subred InternetIPPrefixLength es correcta.</span><span class="sxs-lookup"><span data-stu-id="a5a3b-209">Make sure subnet mask InternetIPPrefixLength is correct.</span></span>
    
  - <span data-ttu-id="a5a3b-210">Asegúrese de que no existen conflictos IP para estas direcciones IP externas.</span><span class="sxs-lookup"><span data-stu-id="a5a3b-210">Make sure there are no IP conflicts for these external IPs.</span></span>
    
- <span data-ttu-id="a5a3b-211">**Puertas de enlace:**</span><span class="sxs-lookup"><span data-stu-id="a5a3b-211">**Gateways:**</span></span>
    
  - <span data-ttu-id="a5a3b-p120">Si solo tiene una puerta de enlace, quite la sección de la puerta de enlace secundaria. Si tiene más de dos puertas de enlace, cree secciones adicionales copiando y pegando la existente, y después actualizándola.</span><span class="sxs-lookup"><span data-stu-id="a5a3b-p120">If you have only one gateway, remove the section for the secondary gateway. If you have more than two gateways, create additional sections by copying and pasting the existing one and then updating it.</span></span>
    
  - <span data-ttu-id="a5a3b-214">Asegúrese de que la dirección IP y los puertos de las puertas de enlace sean correctos.</span><span class="sxs-lookup"><span data-stu-id="a5a3b-214">Make sure that the IP address and port of the gateway(s) are correct.</span></span>
    
  - <span data-ttu-id="a5a3b-215">Para que la puerta de enlace RTC de alta disponibilidad sea compatible, deje la puerta de enlace secundaria y agregue las puertas de enlace secundarias que vaya a usar.</span><span class="sxs-lookup"><span data-stu-id="a5a3b-215">To support PSTN gateway level HA, leave the secondary gateway, and add any additional gateways you will use.</span></span> <span data-ttu-id="a5a3b-216">Puede copiar y pegar una entrada existente y, a continuación, actualizarlo.</span><span class="sxs-lookup"><span data-stu-id="a5a3b-216">You can copy and paste an existing entry and then update it.</span></span>
    
- <span data-ttu-id="a5a3b-217">Opcionalmente, puede actualizar el valor de LocalRoute para restringir los números de llamadas salientes.</span><span class="sxs-lookup"><span data-stu-id="a5a3b-217">Optionally, you can update the LocalRoute value to restrict outbound call numbers.</span></span>
    
## <a name="download-the-bits-to-the-site-directory"></a><span data-ttu-id="a5a3b-218">Descargar los bits en el Directorio de sitios</span><span class="sxs-lookup"><span data-stu-id="a5a3b-218">Download the bits to the Site Directory</span></span>

<span data-ttu-id="a5a3b-219">Ejecute el siguiente cmdlet para descargar los bits y los archivos de información de la versión en el **Directorio de sitios**:</span><span class="sxs-lookup"><span data-stu-id="a5a3b-219">Run the following cmdlet to download the bits and version information files to the **Site Directory**:</span></span>
  
```
Start-CcDownload
```

> [!NOTE]
> <span data-ttu-id="a5a3b-220">Deberá realizar este paso solo para el primer dispositivo.</span><span class="sxs-lookup"><span data-stu-id="a5a3b-220">You need to perform this step for the first appliance only.</span></span> 
  
## <a name="prepare-base-virtual-disk-vhdx-from-the-downloaded-iso-file"></a><span data-ttu-id="a5a3b-221">Preparar el disco virtual base (VHDX) desde el archivo ISO descargado</span><span class="sxs-lookup"><span data-stu-id="a5a3b-221">Prepare base virtual disk (VHDX) from the downloaded ISO file</span></span>

<span data-ttu-id="a5a3b-222">Este paso prepara un archivo de disco duro virtual (VHDX) de la imagen ISO de Windows Server 2012.</span><span class="sxs-lookup"><span data-stu-id="a5a3b-222">This step prepares a virtual hard disk (VHDX) file from the Windows Server 2012 ISO image.</span></span> <span data-ttu-id="a5a3b-223">El VHDX se usará para crear máquinas virtuales durante la implementación.</span><span class="sxs-lookup"><span data-stu-id="a5a3b-223">The VHDX will be used to create virtual machines during deployment.</span></span> <span data-ttu-id="a5a3b-224">Se creará una máquina virtual temporal (base VM) y Windows Server 2012 se instalará desde el archivo ISO.</span><span class="sxs-lookup"><span data-stu-id="a5a3b-224">A temporary virtual machine (base VM) will be created and Windows Server 2012 will be installed from the ISO file.</span></span> <span data-ttu-id="a5a3b-225">Una vez creada la máquina virtual, se instalarán algunos componentes necesarios y se aplicará la actualización de Windows más reciente.</span><span class="sxs-lookup"><span data-stu-id="a5a3b-225">After the VM is created, some necessary components will be installed and the latest Windows update will be applied.</span></span> <span data-ttu-id="a5a3b-226">Al final, la máquina virtual base se generalizará (Sysprep) y se limpiará, dejando solo el archivo de disco virtual generado.</span><span class="sxs-lookup"><span data-stu-id="a5a3b-226">At the end, the base VM will be generalized (sysprep) and cleaned up, leaving only the generated virtual disk file.</span></span>
  
> [!NOTE]
> <span data-ttu-id="a5a3b-227">Deberá realizar este paso solo para el primer dispositivo.</span><span class="sxs-lookup"><span data-stu-id="a5a3b-227">You need to perform this step for the first appliance only.</span></span> 
  
<span data-ttu-id="a5a3b-p123">Antes de continuar con este paso, asegúrese de que se haya creado el conmutador de red corporativa. Además, confirme que las siguientes opciones se hayan configurado correctamente en el archivo CloudConnector.ini:</span><span class="sxs-lookup"><span data-stu-id="a5a3b-p123">Before proceeding with this step, make sure that the corpnet switch is created. Also, confirm that the following settings are correctly configured in the CloudConnector.ini file:</span></span>
  
- <span data-ttu-id="a5a3b-230">[Red] CorpnetSwitchName</span><span class="sxs-lookup"><span data-stu-id="a5a3b-230">[Network]CorpnetSwitchName</span></span>
    
- <span data-ttu-id="a5a3b-231">[Common] BaseVMIP</span><span class="sxs-lookup"><span data-stu-id="a5a3b-231">[Common]BaseVMIP</span></span>
    
- <span data-ttu-id="a5a3b-232">[Red] CorpnetIPPrefixLength</span><span class="sxs-lookup"><span data-stu-id="a5a3b-232">[Network]CorpnetIPPrefixLength</span></span>
    
- <span data-ttu-id="a5a3b-233">[Red] CorpnetDefaultGateway</span><span class="sxs-lookup"><span data-stu-id="a5a3b-233">[Network]CorpnetDefaultGateway</span></span>
    
- <span data-ttu-id="a5a3b-234">[Red] CorpnetDNSIPAddress</span><span class="sxs-lookup"><span data-stu-id="a5a3b-234">[Network]CorpnetDNSIPAddress</span></span>
    
<span data-ttu-id="a5a3b-235">Inicie una consola de PowerShell como administrador y ejecute el siguiente cmdlet para convertir la imagen ISO a un disco duro virtual (VHD):</span><span class="sxs-lookup"><span data-stu-id="a5a3b-235">Start a PowerShell console as administrator and run the following cmdlet to convert the ISO image to a virtual hard disk (VHD):</span></span>
  
```
Convert-CcIsoToVhdx -IsoFilePath <Windows ISO File Path, including file name>
```

<span data-ttu-id="a5a3b-p124">Especifique la ruta de acceso completa, incluido el nombre del archivo, a la imagen ISO. Por ejemplo: C:\ISO\WindowsServer2012R2.iso.</span><span class="sxs-lookup"><span data-stu-id="a5a3b-p124">Specify the full path, including file name, to the ISO image. For example: C:\ISO\WindowsServer2012R2.iso.</span></span>
  
<span data-ttu-id="a5a3b-238">El archivo VHD creado se almacena en la carpeta de \Bits\VHD del **Directorio de sitios** .</span><span class="sxs-lookup"><span data-stu-id="a5a3b-238">The created VHD file is stored in the **Site Directory** \Bits\VHD folder.</span></span> <span data-ttu-id="a5a3b-239">Puede obtener la ruta de acceso al **Directorio de sitios** ejecutando **Get-CcSiteDirectory**.</span><span class="sxs-lookup"><span data-stu-id="a5a3b-239">You can get the path to the **Site Directory** by running the **Get-CcSiteDirectory**.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="a5a3b-240">De manera predeterminada, la configuración del proxy no se configura en la máquina virtual base.</span><span class="sxs-lookup"><span data-stu-id="a5a3b-240">By default, proxy settings are not configured on the base VM.</span></span> <span data-ttu-id="a5a3b-241">Si un servidor proxy es necesaria en el entorno de red para actualizar la máquina virtual a través de Windows Update, debe agregar el modificador - PauseBeforeUpdate al ejecutar "Convert-CcIsoToVhdx".</span><span class="sxs-lookup"><span data-stu-id="a5a3b-241">If a proxy is required in your network environment to update the VM via Windows Update, you should add the -PauseBeforeUpdate switch when you run "Convert-CcIsoToVhdx".</span></span> <span data-ttu-id="a5a3b-242">La ejecución se detendrá antes de la actualización de Windows y tendrá la oportunidad de configurar manualmente el proxy en la máquina virtual.</span><span class="sxs-lookup"><span data-stu-id="a5a3b-242">The script will pause before Windows Update and you'll have a chance to manually set up proxy on the VM.</span></span> <span data-ttu-id="a5a3b-243">Después de que se configure el proxy y que la máquina virtual pueda acceder a Internet, podrá reanudar el script para completar los pasos restantes.</span><span class="sxs-lookup"><span data-stu-id="a5a3b-243">After the proxy is setup and the VM can access Internet, you can resume the script to complete the remaining steps.</span></span> 
  
### <a name="create-vhds-for-a-multi-site-deployment"></a><span data-ttu-id="a5a3b-244">Crear VHD para una implementación de varios sitios</span><span class="sxs-lookup"><span data-stu-id="a5a3b-244">Create VHDs for a multi-site deployment</span></span>

<span data-ttu-id="a5a3b-245">Este es un paso opcional que solo se aplica a las implementaciones de varios sitios.</span><span class="sxs-lookup"><span data-stu-id="a5a3b-245">This is an optional step that applies only to multi-site deployments.</span></span>
  
<span data-ttu-id="a5a3b-p127">Si va a realizar una implementación de varios sitios, no necesita convertir el ISO en VHD para cada sitio. Puede copiar el VHDX creado para el primer sitio en el servidor host de un segundo sitio.</span><span class="sxs-lookup"><span data-stu-id="a5a3b-p127">If you are deploying a multi-site deployment, you do not need to convert the ISO to a VHD for each site. You can copy the VHDX created for the first site to the host server for a second site.</span></span>
  
 <span data-ttu-id="a5a3b-248">Copie el archivo en la misma ubicación de archivo ( **Directorio de sitios** \Bits\VHD carpeta) y con el mismo nombre de archivo en el servidor host para un sitio adicional.</span><span class="sxs-lookup"><span data-stu-id="a5a3b-248">Copy the file to the same file location ( **Site Directory** \Bits\VHD folder), and with the same file name, on the host server for an additional site.</span></span>
  
## <a name="set-the-powershell-execution-policy-to-remotesigned"></a><span data-ttu-id="a5a3b-249">Establecer la directiva de ejecución de PowerShell en RemoteSigned</span><span class="sxs-lookup"><span data-stu-id="a5a3b-249">Set the PowerShell Execution policy to RemoteSigned</span></span>

<span data-ttu-id="a5a3b-p128">Los scripts de PowerShell proporcionados requieren que la directiva de ejecución se establezca en RemoteSigned. Para ver la configuración actual, abra una consola de PowerShell como administrador y después ejecute el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="a5a3b-p128">The PowerShell scripts provided require that the execution policy be set to RemoteSigned. To see the current setting, open a PowerShell console as administrator and then run the following cmdlet:</span></span>
  
```
Get-ExecutionPolicy
```

<span data-ttu-id="a5a3b-252">Si no se establece como "RemoteSigned", ejecute el siguiente cmdlet para cambiarlo:</span><span class="sxs-lookup"><span data-stu-id="a5a3b-252">If it is not set to "RemoteSigned," run the following cmdlet to change it:</span></span>
  
```
Set-ExecutionPolicy RemoteSigned
```

## <a name="change-local-group-policy-on-the-host-machine-versions-141-and-earlier"></a><span data-ttu-id="a5a3b-253">Cambiar la directiva de grupo local del equipo host (versiones 1.4.1 y anteriores)</span><span class="sxs-lookup"><span data-stu-id="a5a3b-253">Change local Group Policy on the host machine (versions 1.4.1 and earlier)</span></span>

> [!NOTE]
> <span data-ttu-id="a5a3b-254">Esta tarea no se requiere para la versión 1.4.2 de Cloud Connector y otras versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="a5a3b-254">This task is not required for Cloud Connector versions 1.4.2 and later.</span></span> 
  
<span data-ttu-id="a5a3b-255">La cuenta CceService se crea durante la implementación de Skype Empresarial Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="a5a3b-255">The CceService account is created during the Skype for Business Cloud Connector Edition deployment.</span></span> <span data-ttu-id="a5a3b-256">Se ejecuta el servicio de administración del conector de nube y requiere permiso para desinstalar el cloudconnector.msi.</span><span class="sxs-lookup"><span data-stu-id="a5a3b-256">It runs the Cloud Connector Management Service and requires permission to uninstall the cloudconnector.msi.</span></span> <span data-ttu-id="a5a3b-257">Debe cambiar la configuración de la directiva de grupo del equipo host de Cloud Connector para especificar que el registro de usuarios no se descargue cuando el usuario cierre sesión.</span><span class="sxs-lookup"><span data-stu-id="a5a3b-257">You must change the group policy setting on the Cloud Connector host machine to specify that the user registry should not be unloaded when the user logs off.</span></span> <span data-ttu-id="a5a3b-258">Siga los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="a5a3b-258">Follow the steps below:</span></span>
  
### <a name="to-change-the-group-policy-setting"></a><span data-ttu-id="a5a3b-259">Para cambiar la configuración de la directiva de grupo</span><span class="sxs-lookup"><span data-stu-id="a5a3b-259">To change the Group Policy setting</span></span>

1. <span data-ttu-id="a5a3b-260">Abra el **Editor de directiva de grupo** al ejecutar gpedit.msc.</span><span class="sxs-lookup"><span data-stu-id="a5a3b-260">Open the **Group Policy Editor** by running gpedit.msc.</span></span>
    
2. <span data-ttu-id="a5a3b-261">En el **Editor de directivas de grupo**, navegue a Plantillas administrativas > Sistema > Perfil de usuario > No descargar forzosamente el Registro de usuarios al cerrar la sesión de usuario. </span><span class="sxs-lookup"><span data-stu-id="a5a3b-261">In the **Group Policy Editor**, navigate to Administrative Templates > System > UserProfile > Do not forcefully unload the user registry at user logoff.</span></span> 
    
3. <span data-ttu-id="a5a3b-262">Su valor se establece en **habilitado**.</span><span class="sxs-lookup"><span data-stu-id="a5a3b-262">Set its value to **Enabled**.</span></span>
    
## <a name="set-up-your-office-365-tenant"></a><span data-ttu-id="a5a3b-263">Configurar el inquilino de Office 365</span><span class="sxs-lookup"><span data-stu-id="a5a3b-263">Set up your Office 365 tenant</span></span>

<span data-ttu-id="a5a3b-264">Se requiere un arrendatario Office 365 con Skype para los negocios en línea y el sistema de teléfono en Office 365.</span><span class="sxs-lookup"><span data-stu-id="a5a3b-264">An Office 365 tenant with Skype for Business Online and Phone System in Office 365 is required.</span></span> <span data-ttu-id="a5a3b-265">Asegúrese de que el arrendatario está instalado y configurado antes de intentar utilizar el conector de la nube.</span><span class="sxs-lookup"><span data-stu-id="a5a3b-265">Make sure your tenant is set up and configured before attempting to use Cloud Connector.</span></span>
  
<span data-ttu-id="a5a3b-266">Algunos pasos de configuración de Office 365 requieren que se use PowerShell remoto de inquilinos (TRPS) para configurar a los clientes de Office 365.</span><span class="sxs-lookup"><span data-stu-id="a5a3b-266">Some Office 365 setup steps require you to use Tenant Remote PowerShell (TRPS) to configure your Office 365 tenant.</span></span> <span data-ttu-id="a5a3b-267">**Se debe instalar en el servidor host.**</span><span class="sxs-lookup"><span data-stu-id="a5a3b-267">**This should be installed on the host server.**</span></span> <span data-ttu-id="a5a3b-268">Puede descargar el Skype para módulo empresarial en línea para PowerShell desde:[Skype para los negocios en línea, módulo de Windows PowerShell](https://www.microsoft.com/en-us/download/details.aspx?id=39366).</span><span class="sxs-lookup"><span data-stu-id="a5a3b-268">You can download the Skype for Business Online module for PowerShell from:[Skype for Business Online, Windows PowerShell Module](https://www.microsoft.com/en-us/download/details.aspx?id=39366).</span></span>
  
<span data-ttu-id="a5a3b-269">Crear un Skype dedicado de cuenta de administrador de empresa administración de nube conector en línea, por ejemplo CceOnlineManagmentAdministrator.</span><span class="sxs-lookup"><span data-stu-id="a5a3b-269">Create a dedicated Skype for Business administrator account for Cloud Connector online management, for example CceOnlineManagmentAdministrator.</span></span> <span data-ttu-id="a5a3b-270">Esta cuenta la usará la aplicación para agregar o quitar aplicaciones, habilitar o deshabilitar actualizaciones automáticas del sistema operativo, habilitar o deshabilitar actualizaciones automáticas de archivos binarios.</span><span class="sxs-lookup"><span data-stu-id="a5a3b-270">This account will be used by appliance to add or remove appliance, enable or disable automatic OS update, enable or disable automatic binary update.</span></span> <span data-ttu-id="a5a3b-271">Establezca la contraseña para que esta cuenta no expire nunca y no haya que cambiarla para el servicio cada vez que expire.</span><span class="sxs-lookup"><span data-stu-id="a5a3b-271">Set the password for this account to never expire so that you do not need to change it for the service each time it expires.</span></span>
  

