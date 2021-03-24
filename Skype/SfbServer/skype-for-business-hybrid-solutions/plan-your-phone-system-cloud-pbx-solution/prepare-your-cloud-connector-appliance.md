---
title: Preparar el dispositivo de Cloud Connector
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 6eacfa99-9759-4c13-aca3-8992c2ff2710
description: Obtenga información sobre cómo preparar el dispositivo de Cloud Connector para su implementación y uso con Phone System (PBX en la nube).
ms.openlocfilehash: 536e9b98520e4274e00d43d57224267f5b824dc9
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51092638"
---
# <a name="prepare-your-cloud-connector-appliance"></a><span data-ttu-id="8dcba-103">Preparar el dispositivo de Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="8dcba-103">Prepare your Cloud Connector appliance</span></span>

> [!Important]
> <span data-ttu-id="8dcba-104">Cloud Connector Edition se retirará el 31 de julio de 2021 junto con Skype Empresarial Online.</span><span class="sxs-lookup"><span data-stu-id="8dcba-104">Cloud Connector Edition will retire July 31, 2021 along with Skype for Business Online.</span></span> <span data-ttu-id="8dcba-105">Una vez que la organización haya actualizado a Teams, obtenga información sobre cómo conectar la red de telefonía local a Teams mediante [enrutamiento directo.](/MicrosoftTeams/direct-routing-landing-page)</span><span class="sxs-lookup"><span data-stu-id="8dcba-105">Once your organization has upgraded to Teams, learn how to connect your on-premises telephony network to Teams using [Direct Routing](/MicrosoftTeams/direct-routing-landing-page).</span></span>

<span data-ttu-id="8dcba-106">Obtenga información sobre cómo preparar el dispositivo de Cloud Connector para su implementación y uso con Phone System (PBX en la nube).</span><span class="sxs-lookup"><span data-stu-id="8dcba-106">Learn about how to prepare your Cloud Connector appliance for deployment and use with Phone System (Cloud PBX).</span></span>

<span data-ttu-id="8dcba-107">En esta sección se describe cómo obtener los archivos de instalación de Skype Empresarial Cloud Connector Edition, instalar el software de Cloud Connector y preparar el dispositivo de Cloud Connector para su implementación.</span><span class="sxs-lookup"><span data-stu-id="8dcba-107">This section describes how to get the Skype for Business Cloud Connector Edition installation files, install Cloud Connector software, and prepare your Cloud Connector appliance for deployment.</span></span> <span data-ttu-id="8dcba-108">Después de completar todos los pasos de esta sección, estará listo para implementar Cloud Connector para un solo sitio o varios sitios.</span><span class="sxs-lookup"><span data-stu-id="8dcba-108">After you have completed all steps in this section, you will be ready to deploy Cloud Connector for a single site or multiple sites.</span></span> <span data-ttu-id="8dcba-109">Si tiene una implementación existente de Cloud Connector y aún no ha actualizado [a](upgrade-to-a-new-version-of-cloud-connector.md)Cloud Connector versión 2.1, consulte Upgrade to a new version of Cloud Connector .</span><span class="sxs-lookup"><span data-stu-id="8dcba-109">If you have an existing Cloud Connector deployment, and you have not yet upgraded to Cloud Connector version 2.1, see [Upgrade to a new version of Cloud Connector](upgrade-to-a-new-version-of-cloud-connector.md).</span></span>

> [!NOTE]
> <span data-ttu-id="8dcba-110">Microsoft admite la versión actual de Cloud Connector Edition, versión 2.1.</span><span class="sxs-lookup"><span data-stu-id="8dcba-110">Microsoft supports the current version of Cloud Connector Edition, version 2.1.</span></span> <span data-ttu-id="8dcba-111">Si configuró la actualización automática, Cloud Connector se actualizará automáticamente.</span><span class="sxs-lookup"><span data-stu-id="8dcba-111">If you configured automatic update, Cloud Connector will update automatically.</span></span> <span data-ttu-id="8dcba-112">Si configuró la actualización manual, tendrá que actualizar a la versión 2.1 en un plazo de 60 días desde su lanzamiento.</span><span class="sxs-lookup"><span data-stu-id="8dcba-112">If you configured manual update, you will need to upgrade to version 2.1 within 60 days of its release.</span></span> <span data-ttu-id="8dcba-113">Microsoft admitirá la versión anterior durante 60 días después de la versión 2.1 para permitirte tiempo para actualizar.</span><span class="sxs-lookup"><span data-stu-id="8dcba-113">Microsoft will support the previous version for 60 days after the release of 2.1 to allow you time to upgrade.</span></span> 

> [!NOTE]
> <span data-ttu-id="8dcba-114">Para Cloud Connector versión 2.1 y versiones posteriores, el dispositivo host debe tener .NET Framework 4.6.1 o posterior instalado.</span><span class="sxs-lookup"><span data-stu-id="8dcba-114">For Cloud Connector version 2.1 and later, the host appliance must have .NET Framework 4.6.1 or later installed.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="8dcba-115">Para una implementación correcta, cuando ejecute los cmdlets para configurar Skype Empresarial Cloud Connector Edition, use siempre la misma sesión de consola que la que inició.</span><span class="sxs-lookup"><span data-stu-id="8dcba-115">For successful deployment, when you run the cmdlets to configure Skype for Business Cloud Connector Edition, always use the same console session as the one you started in.</span></span> <span data-ttu-id="8dcba-116">Evite cambiar a diferentes sesiones durante la implementación y configuración.</span><span class="sxs-lookup"><span data-stu-id="8dcba-116">Avoid switching to different sessions during the deployment and configuration.</span></span> 

> [!NOTE]
> <span data-ttu-id="8dcba-117">Hay algunos pasos que solo se realizan para el primer dispositivo de la implementación: crear un recurso compartido para el directorio del sitio, descargar los bits y preparar un archivo de disco duro virtual (VHDX) desde la imagen ISO de Windows Server.</span><span class="sxs-lookup"><span data-stu-id="8dcba-117">There are some steps that you perform only for the first appliance in your deployment: creating a share for the site directory, downloading the bits, and preparing a virtual hard disk (VHDX) file from the Windows Server ISO image.</span></span> 

## <a name="download-the-skype-for-business-cloud-connector-edition-installer"></a><span data-ttu-id="8dcba-118">Descargar el instalador de Skype Empresarial Cloud Connector Edition</span><span class="sxs-lookup"><span data-stu-id="8dcba-118">Download the Skype for Business Cloud Connector Edition installer</span></span>

1. <span data-ttu-id="8dcba-119">En el servidor host donde se ejecutarán las máquinas virtuales de Cloud Connector, descargue los archivos de instalación: [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller) .</span><span class="sxs-lookup"><span data-stu-id="8dcba-119">On the host server where the Cloud Connector VMs will run, download the installation files: [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller).</span></span> 

    > [!IMPORTANT]
    > <span data-ttu-id="8dcba-120">El servidor host debe poder tener acceso a Internet durante la instalación de Cloud Connector porque se descargan archivos adicionales durante la instalación.</span><span class="sxs-lookup"><span data-stu-id="8dcba-120">The host server must be able to access the Internet during the installation of Cloud Connector because additional files are downloaded during the installation.</span></span> 

2. <span data-ttu-id="8dcba-121">Ejecute el instalador y acepte los valores predeterminados durante la instalación.</span><span class="sxs-lookup"><span data-stu-id="8dcba-121">Run the installer and accept the default values during the installation.</span></span>

3. <span data-ttu-id="8dcba-122">Confirme que la instalación se completó correctamente.</span><span class="sxs-lookup"><span data-stu-id="8dcba-122">Confirm that the installation completed successfully.</span></span>

## <a name="verify-the-installation-and-configure-the-environment"></a><span data-ttu-id="8dcba-123">Comprobar la instalación y configurar el entorno</span><span class="sxs-lookup"><span data-stu-id="8dcba-123">Verify the installation and configure the environment</span></span>

1. <span data-ttu-id="8dcba-124">Abra una consola de PowerShell como administrador y confirme que los cmdlets de Skype Empresarial Cloud Connector Edition están disponibles con el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="8dcba-124">Open a PowerShell console as administrator and confirm that the Skype for Business Cloud Connector Edition cmdlets are available using the following cmdlet:</span></span>

   ```powershell
   Get-Command *-Cc*
   ```

    <span data-ttu-id="8dcba-125">El comando debe devolver una lista de cmdlets para Skype Empresarial Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="8dcba-125">The command should return a list of cmdlets for Skype for Business Cloud Connector Edition.</span></span>

2. <span data-ttu-id="8dcba-126">Los archivos VHD, SfBBits y VersionInfo se almacenarán en el **Directorio del sitio**.</span><span class="sxs-lookup"><span data-stu-id="8dcba-126">The VHDs, SfBBits, and VersionInfo files will be stored in the **Site Directory**.</span></span>

    <span data-ttu-id="8dcba-127">Puede encontrar la ubicación del Directorio del **sitio** con el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="8dcba-127">You can find the location of the **Site Directory** with the following cmdlet:</span></span>

   ```powershell
   Get-CcSiteDirectory
   ```

    <span data-ttu-id="8dcba-128">El comando debe devolver una ubicación en el sistema de archivos.</span><span class="sxs-lookup"><span data-stu-id="8dcba-128">The command should return a location in your file system.</span></span> <span data-ttu-id="8dcba-129">La ubicación puede ser una carpeta local o un recurso compartido de archivos.</span><span class="sxs-lookup"><span data-stu-id="8dcba-129">The location can be a local folder or a file share.</span></span> <span data-ttu-id="8dcba-130">La ubicación predeterminada del **Directorio del sitio** es: %USERPROFILE%\CloudConnector\SiteRoot.</span><span class="sxs-lookup"><span data-stu-id="8dcba-130">The default location for the **Site Directory** is: %USERPROFILE%\CloudConnector\SiteRoot.</span></span> <span data-ttu-id="8dcba-131">La ubicación predeterminada debe cambiarse a un recurso compartido de archivos en el primer dispositivo creado en cada sitio.</span><span class="sxs-lookup"><span data-stu-id="8dcba-131">The default location should be changed to a file share on the first appliance created in each site.</span></span>

    <span data-ttu-id="8dcba-132">La ubicación que seleccione debe ser:</span><span class="sxs-lookup"><span data-stu-id="8dcba-132">The location you select must be:</span></span>

   - <span data-ttu-id="8dcba-133">Creado en el primer dispositivo creado en cada sitio.</span><span class="sxs-lookup"><span data-stu-id="8dcba-133">Created on the first appliance created in each site.</span></span>

   - <span data-ttu-id="8dcba-134">Una carpeta compartida a la que los demás servidores host (dispositivos) tienen acceso en el mismo sitio.</span><span class="sxs-lookup"><span data-stu-id="8dcba-134">A shared folder that is accessible by the other host servers (appliances) in the same site.</span></span>

     <span data-ttu-id="8dcba-135">Para establecer **el Directorio del sitio** en una ubicación que no sea la predeterminada, ejecute el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="8dcba-135">To set the **Site Directory** to a location other than the default, run the following cmdlet:</span></span>

   ```powershell
   Set-CcSiteDirectory <UNC File path>
   ```

    <span data-ttu-id="8dcba-136">Si va a implementar alta disponibilidad (HA) para el sitio,  asegúrese de ejecutar el cmdlet para establecer el Directorio del sitio en la misma ubicación en cada servidor host dentro del sitio.</span><span class="sxs-lookup"><span data-stu-id="8dcba-136">If you are deploying High Availability (HA) for the site, make sure you run the cmdlet to set the **Site Directory** to the same location on each host server within the site.</span></span>

    <span data-ttu-id="8dcba-137">Cuando inicie sesión e implemente cada dispositivo en el sitio, asegúrese de que su cuenta de inicio de sesión actual tenga el acceso correcto al **Directorio del sitio**.</span><span class="sxs-lookup"><span data-stu-id="8dcba-137">When you log on and deploy each appliance in the site, make sure your current logon account has the right access to the **Site Directory**.</span></span>

3. <span data-ttu-id="8dcba-138">El **Directorio del dispositivo** es el directorio raíz de trabajo local para Skype Empresarial Cloud Connector Edition y la ubicación donde se guardan certificados, instancias y registros externos.</span><span class="sxs-lookup"><span data-stu-id="8dcba-138">The **Appliance Directory** is the local working root directory for Skype for Business Cloud Connector Edition, and the location where external certificates, instances, and logs are saved.</span></span> <span data-ttu-id="8dcba-139">La ubicación predeterminada es: %USERPROFILE%\CloudConnector\ApplianceRoot.</span><span class="sxs-lookup"><span data-stu-id="8dcba-139">The default location is: %USERPROFILE%\CloudConnector\ApplianceRoot.</span></span>

    <span data-ttu-id="8dcba-140">Para buscar la ubicación del **Directorio de dispositivos,** ejecute el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="8dcba-140">To find the location of the **Appliance Directory**, run the following cmdlet:</span></span>

   ```powershell
   Get-CcApplianceDirectory
   ```

    <span data-ttu-id="8dcba-141">Para establecer **el Directorio del dispositivo** en una ubicación que no sea la predeterminada, ejecute el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="8dcba-141">To set the **Appliance Directory** to a location other than the default, run the following cmdlet:</span></span>

   ```powershell
   Set-CcApplianceDirectory <File path>
   ```

    <span data-ttu-id="8dcba-142">El directorio del dispositivo debe establecerse en una carpeta local del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="8dcba-142">The Appliance Directory should be set to a local folder on the appliance.</span></span> <span data-ttu-id="8dcba-143">Solo debe establecer el directorio **de dispositivos antes** de iniciar la implementación de Skype Empresarial Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="8dcba-143">You should only set the **Appliance Directory** before you start the Skype for Business Cloud Connector Edition deployment.</span></span> <span data-ttu-id="8dcba-144">Si lo cambia después de la implementación, tendrá que volver a implementar el servidor host.</span><span class="sxs-lookup"><span data-stu-id="8dcba-144">If you change it after deployment, you'll need to redeploy the host server.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="8dcba-145">La ruta de acceso al **Directorio de dispositivos** no debe contener espacios.</span><span class="sxs-lookup"><span data-stu-id="8dcba-145">The path to the **Appliance Directory** must not contain any spaces.</span></span>

## <a name="set-the-path-for-the-external-edge-certificate"></a><span data-ttu-id="8dcba-146">Establecer la ruta de acceso para el certificado perimetral externo</span><span class="sxs-lookup"><span data-stu-id="8dcba-146">Set the path for the external Edge certificate</span></span>

- <span data-ttu-id="8dcba-147">Ejecute el siguiente cmdlet para establecer la ruta de acceso, incluido el nombre de archivo, en el certificado perimetral externo.</span><span class="sxs-lookup"><span data-stu-id="8dcba-147">Run the following cmdlet to set the path, including the file name, to the external Edge certificate.</span></span> <span data-ttu-id="8dcba-148">Por ejemplo: C:\certs\cce\ap.contoso.com.pfx.</span><span class="sxs-lookup"><span data-stu-id="8dcba-148">For example: C:\certs\cce\ap.contoso.com.pfx.</span></span> <span data-ttu-id="8dcba-149">El certificado debe contener claves privadas.</span><span class="sxs-lookup"><span data-stu-id="8dcba-149">The certificate must contain private keys.</span></span>

  ```powershell
  Set-CcExternalCertificateFilePath -Path <Full path to External certificate, including file name> -Target EdgeServer
  ```

    > [!NOTE]
    > <span data-ttu-id="8dcba-150">Tenga en cuenta que el parámetro -Target es específico de las versiones 1.4.2 y posteriores.</span><span class="sxs-lookup"><span data-stu-id="8dcba-150">Note that the -Target parameter is specific to versions 1.4.2 and later.</span></span> 

    <span data-ttu-id="8dcba-151">Especifique la ruta de acceso completa al certificado externo, incluido el nombre del archivo.</span><span class="sxs-lookup"><span data-stu-id="8dcba-151">Specify the full path to the external certificate, including the file name.</span></span> <span data-ttu-id="8dcba-152">El certificado se puede almacenar localmente o en un recurso compartido de archivos.</span><span class="sxs-lookup"><span data-stu-id="8dcba-152">The certificate can be stored locally or on a file share.</span></span> <span data-ttu-id="8dcba-153">Si el certificado se almacena en una carpeta compartida, la carpeta compartida debe crearse en el primer dispositivo de cada sitio y debe ser accesible por otros dispositivos pertenecientes al mismo sitio.</span><span class="sxs-lookup"><span data-stu-id="8dcba-153">If the certificate is stored in a shared folder, the shared folder must be created on the first appliance of each site and must be accessible by other appliances belonging to the same site.</span></span> <span data-ttu-id="8dcba-154">Este cmdlet copia el certificado externo en **el Directorio del dispositivo**.</span><span class="sxs-lookup"><span data-stu-id="8dcba-154">This cmdlet copies the external certificate to the **Appliance Directory**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="8dcba-155">Si se ha actualizado a Cloud Connector versión **1.4.2** o posterior, asegúrese de que el certificado externo preparado contiene claves privadas y la cadena de certificados completa, incluidos el certificado de CA raíz y los certificados de CA intermedios.</span><span class="sxs-lookup"><span data-stu-id="8dcba-155">**If you have updated to Cloud Connector version 1.4.2 or later**, make sure your prepared external certificate contains private keys and the full certificate chain including the root CA certificate and the intermediate CA certificates.</span></span> <span data-ttu-id="8dcba-156">Si aún no se ha actualizado a **Cloud Connector versión 1.4.2,** asegúrese de que el certificado externo preparado contiene claves privadas.</span><span class="sxs-lookup"><span data-stu-id="8dcba-156">**If you have NOT yet updated to Cloud Connector version 1.4.2**, make sure your prepared external certificate contains private keys.</span></span> <span data-ttu-id="8dcba-157">Este certificado externo debe ser emitido por una entidad de certificación de confianza de Windows de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="8dcba-157">This external certificate must be issued by a Certificate Authority that is trusted by Windows by default.</span></span>

## <a name="set-the-path-for-the-external-pstn-gatewaysbc-certificate"></a><span data-ttu-id="8dcba-158">Establecer la ruta de acceso para la puerta de enlace RTC externa/certificado SBC</span><span class="sxs-lookup"><span data-stu-id="8dcba-158">Set the path for the external PSTN gateway/SBC certificate</span></span>

<span data-ttu-id="8dcba-159">Si usa TLS entre el servidor de mediación y la puerta de enlace RTC/SBC, ejecute el siguiente cmdlet para establecer la ruta de acceso, incluido el nombre del archivo, en el certificado de puerta de enlace.</span><span class="sxs-lookup"><span data-stu-id="8dcba-159">If you are using TLS between the Mediation Server and the PSTN gateway/SBC, run the following cmdlet to set the path, including the file name, to the gateway certificate.</span></span> <span data-ttu-id="8dcba-160">Por ejemplo: C:\certs\cce\sbc.contoso.com.cer.</span><span class="sxs-lookup"><span data-stu-id="8dcba-160">For example: C:\certs\cce\sbc.contoso.com.cer.</span></span> <span data-ttu-id="8dcba-161">El certificado debe contener la CA raíz y la cadena intermedia del certificado asignado a la puerta de enlace:</span><span class="sxs-lookup"><span data-stu-id="8dcba-161">The certificate must contain the root CA and the intermediate chain for the certificate assigned to the gateway:</span></span>

```powershell
Set-CcExternalCertificateFilePath -Path <Full path to gateway certificate, including file name> -Target MediationServer 
```

> [!NOTE]
> <span data-ttu-id="8dcba-162">Tenga en cuenta que el parámetro -Target es específico de las versiones 1.4.2 y posteriores.</span><span class="sxs-lookup"><span data-stu-id="8dcba-162">Note that the -Target parameter is specific to versions 1.4.2 and later.</span></span> 

## <a name="create-virtual-switches-in-hyper-v-manager"></a><span data-ttu-id="8dcba-163">Crear conmutadores virtuales en el Administrador de Hyper-V</span><span class="sxs-lookup"><span data-stu-id="8dcba-163">Create virtual switches in Hyper-V Manager</span></span>

1. <span data-ttu-id="8dcba-164">Abra el Administrador de conmutador virtual de **Hyper-V Manager**  >  y seleccione Nuevo Administrador **de modificadores virtuales**.</span><span class="sxs-lookup"><span data-stu-id="8dcba-164">Open **Hyper-V Manager** > **Virtual Switch Manager**, and select **New Virtual Switch Manager**.</span></span>

2. <span data-ttu-id="8dcba-165">Crear un conmutador virtual externo y enlazarlo al adaptador de red físico que está conectado al dominio de red interno:</span><span class="sxs-lookup"><span data-stu-id="8dcba-165">Create an External virtual switch and bind it to the physical network adapter that is connected to your internal network domain:</span></span>

    <span data-ttu-id="8dcba-166">Seleccione **Permitir que el sistema operativo de administración comparta este adaptador de red** para este conmutador virtual.</span><span class="sxs-lookup"><span data-stu-id="8dcba-166">Select **Allow management operating system to share this network adapter** for this virtual switch.</span></span>

3. <span data-ttu-id="8dcba-167">Crear un conmutador virtual externo y enlazarlo al adaptador de red físico que se enruta a Internet:</span><span class="sxs-lookup"><span data-stu-id="8dcba-167">Create an External virtual switch and bind it to the physical network adapter that is routed to the Internet:</span></span>

    <span data-ttu-id="8dcba-168">Des seleccione **Permitir que el sistema operativo de administración comparta este adaptador de red** para este conmutador virtual.</span><span class="sxs-lookup"><span data-stu-id="8dcba-168">De-select **Allow management operating system to share this network adapter** for this virtual switch.</span></span>

4. <span data-ttu-id="8dcba-169">Establezca el nombre del conmutador que conecta la red perimetral con el dominio de red interno **SfB CCE Corpnet Switch**.</span><span class="sxs-lookup"><span data-stu-id="8dcba-169">Set the name of the switch that connects your perimeter network to your internal network domain **SfB CCE Corpnet Switch**.</span></span>

    <span data-ttu-id="8dcba-170">Establezca el nombre del conmutador que conecta la red perimetral al conmutador de **Internet Internet SfB CCE .**</span><span class="sxs-lookup"><span data-stu-id="8dcba-170">Set the name of the switch that connects your perimeter network to the Internet **SfB CCE Internet Switch**.</span></span>

## <a name="update-the-cloudconnectorini-configuration-file"></a><span data-ttu-id="8dcba-171">Actualizar el archivo CloudConnector.ini de configuración</span><span class="sxs-lookup"><span data-stu-id="8dcba-171">Update the CloudConnector.ini configuration file</span></span>

<span data-ttu-id="8dcba-172">Prepare el CloudConnector.ini con la información que recopiló en [Determine deployment parameters](plan-skype-for-business-cloud-connector-edition.md#BKMK_SiteParams) en el tema Plan for Skype for Business Cloud Connector [Edition.](plan-skype-for-business-cloud-connector-edition.md)</span><span class="sxs-lookup"><span data-stu-id="8dcba-172">Prepare the CloudConnector.ini file using the information you gathered in [Determine deployment parameters](plan-skype-for-business-cloud-connector-edition.md#BKMK_SiteParams) in the [Plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md) topic.</span></span>

<span data-ttu-id="8dcba-173">Para actualizar el archivo, ejecute primero el siguiente cmdlet para obtener la plantilla de ejemplo (CloudConnector.Sample.ini):</span><span class="sxs-lookup"><span data-stu-id="8dcba-173">To update the file, first run the following cmdlet to get the sample template (CloudConnector.Sample.ini):</span></span>

```powershell
Export-CcConfigurationSampleFile
```

<span data-ttu-id="8dcba-174">La plantilla de ejemplo se almacena en el **Directorio de dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="8dcba-174">The sample template is stored in the **Appliance Directory**.</span></span>

<span data-ttu-id="8dcba-175">Después de actualizarlo con los valores de su entorno, guarde el archivo como CloudConnector.ini en el **Directorio del dispositivo**.</span><span class="sxs-lookup"><span data-stu-id="8dcba-175">After you update it with the values for your environment, save the file as CloudConnector.ini in the **Appliance Directory**.</span></span> <span data-ttu-id="8dcba-176">Puede ejecutar **Get-CcApplianceDirectory para** determinar la ruta de acceso al **directorio del dispositivo**.</span><span class="sxs-lookup"><span data-stu-id="8dcba-176">You can run **Get-CcApplianceDirectory** to determine the path to the **Appliance Directory**.</span></span>

<span data-ttu-id="8dcba-177">Al actualizar el archivo .ini, tenga en cuenta lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="8dcba-177">When updating the .ini file, consider the following:</span></span>

> [!NOTE]
> <span data-ttu-id="8dcba-178">No todos los valores del archivo .ini se tratan en esta sección, solo los que tienen una consideración especial se tratan aquí.</span><span class="sxs-lookup"><span data-stu-id="8dcba-178">Not all values for the .ini file are discussed in this section, only those with a special consideration are covered here.</span></span> <span data-ttu-id="8dcba-179">Para obtener una lista completa, vea la [sección Determine deployment parameters](plan-skype-for-business-cloud-connector-edition.md#BKMK_SiteParams) del tema Plan for Skype for Business Cloud Connector [Edition.](plan-skype-for-business-cloud-connector-edition.md)</span><span class="sxs-lookup"><span data-stu-id="8dcba-179">For a full list, see the [Determine deployment parameters](plan-skype-for-business-cloud-connector-edition.md#BKMK_SiteParams) section of the [Plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md) topic.</span></span> <span data-ttu-id="8dcba-180">Para obtener más información acerca de los valores que deben cambiarse para dispositivos adicionales o sitios nuevos, vea [Single site with High Availability (HA) compared to multi-site deployments](deploy-multiple-sites-in-cloud-connector.md#BKMK_SingleSitecomparedtomulti-site) en el tema Deploy multiple sites in Cloud [Connector](deploy-multiple-sites-in-cloud-connector.md).</span><span class="sxs-lookup"><span data-stu-id="8dcba-180">For more information about what values need to be changed for additional appliances or new sites, see [Single site with High Availability (HA) compared to multi-site deployments](deploy-multiple-sites-in-cloud-connector.md#BKMK_SingleSitecomparedtomulti-site) in the topic [Deploy multiple sites in Cloud Connector](deploy-multiple-sites-in-cloud-connector.md).</span></span> 

- <span data-ttu-id="8dcba-181">**SiteName:** El valor predeterminado es **Site1**.</span><span class="sxs-lookup"><span data-stu-id="8dcba-181">**SiteName:** The default value is **Site1**.</span></span> <span data-ttu-id="8dcba-182">Debe actualizarlo antes de implementar Cloud Connector, ya que al ejecutar **Register-CcAppliance** para registrar un dispositivo en un sitio existente o nuevo, el cmdlet usará **SiteName** para determinar qué sitio registrar.</span><span class="sxs-lookup"><span data-stu-id="8dcba-182">You must update it before you deploy Cloud Connector, because when you run **Register-CcAppliance** to register an appliance to an existing or new site, the cmdlet will use **SiteName** to determine which site to register.</span></span>

     <span data-ttu-id="8dcba-183">Si desea registrar el dispositivo en un nuevo sitio, el valor de **SiteName** debe ser único y diferente de los sitios existentes.</span><span class="sxs-lookup"><span data-stu-id="8dcba-183">If you want to register the appliance to a new site, the value of **SiteName** must be unique and different from existing sites.</span></span> <span data-ttu-id="8dcba-184">Si desea registrar el dispositivo en un sitio existente, el valor de **SiteName** en el archivo .ini debe coincidir con el nombre definido en la configuración de la organización de Microsoft 365 u Office 365.</span><span class="sxs-lookup"><span data-stu-id="8dcba-184">If you want to register the appliance to an existing site, the value for **SiteName** in .ini file must match the name defined in your Microsoft 365 or Office 365 organization configuration.</span></span> <span data-ttu-id="8dcba-185">Si va a copiar un archivo de configuración de un sitio a otro, asegúrese de actualizar el valor de **SiteName** para cada sitio en consecuencia.</span><span class="sxs-lookup"><span data-stu-id="8dcba-185">If you are copying a configuration file from one site to another, make sure you update the value for **SiteName** for each site accordingly.</span></span>

- <span data-ttu-id="8dcba-186">**ServerName:** El nombre del servidor no debe contener el nombre de dominio y debe limitarse a 15 caracteres.</span><span class="sxs-lookup"><span data-stu-id="8dcba-186">**ServerName:** The server name should not contain the domain name and should be limited to 15 characters.</span></span>

- <span data-ttu-id="8dcba-187">**HardwareType:** Si no establece o deja el valor en null, se usará el valor predeterminado de **Normal.**</span><span class="sxs-lookup"><span data-stu-id="8dcba-187">**HardwareType:** If you don't set or leave the value to null, the default value of **Normal** will be used.</span></span> <span data-ttu-id="8dcba-188">Use **Normal** si tiene previsto implementar la versión más grande de Cloud Connector para admitir 500 llamadas simultáneas por equipo host, tal como se describe en [Plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md).</span><span class="sxs-lookup"><span data-stu-id="8dcba-188">Use **Normal** if you plan to deploy the larger version of Cloud Connector to support 500 simultaneous calls per host machine as described in [Plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md).</span></span> <span data-ttu-id="8dcba-189">Use **Minimum** para una implementación más pequeña que admita 50 llamadas simultáneas.</span><span class="sxs-lookup"><span data-stu-id="8dcba-189">Use **Minimum** for a smaller deployment that supports 50 simultaneous calls.</span></span>

- <span data-ttu-id="8dcba-190">**Conmutadores virtuales de Internet/Corpnet/Management:**: Agregue el nombre de los conmutadores virtuales que haya creado.</span><span class="sxs-lookup"><span data-stu-id="8dcba-190">**Internet/Corpnet/Management virtual switches:**: Add the name of the virtual switches you have created.</span></span> <span data-ttu-id="8dcba-191">Para el conmutador virtual de administración, deje el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="8dcba-191">For the management virtual switch, leave the default value.</span></span> <span data-ttu-id="8dcba-192">El script de implementación creará el conmutador virtual de administración al principio de la implementación y lo eliminará cuando finalice la implementación.</span><span class="sxs-lookup"><span data-stu-id="8dcba-192">The deployment script will create the management virtual switch at the beginning of deployment and delete it when the deployment finishes.</span></span>

- <span data-ttu-id="8dcba-193">**ManagementIPPrefix:** ManagementIPPrefix en la sección Red debe ser una subred diferente de otras direcciones IP internas.</span><span class="sxs-lookup"><span data-stu-id="8dcba-193">**ManagementIPPrefix:** ManagementIPPrefix in the Network section must be a different subnet from other internal IPs.</span></span> <span data-ttu-id="8dcba-194">Por ejemplo, como muestra el valor predeterminado, ManagementIPPrefix es 192.168.213.0, mientras que AD IPAddress es 192.168.0.238.</span><span class="sxs-lookup"><span data-stu-id="8dcba-194">For example, as the default value shows, ManagementIPPrefix is 192.168.213.0, while AD IPAddress is 192.168.0.238.</span></span>

    <span data-ttu-id="8dcba-195">Los scripts de implementación crean un adaptador de red de administración en cada máquina virtual, asignan una IP de administración y la conectan a un conmutador virtual de administración.</span><span class="sxs-lookup"><span data-stu-id="8dcba-195">The deployment scripts create a management network adapter on each virtual machine, assign a management IP, and connect it to a management virtual switch.</span></span> <span data-ttu-id="8dcba-196">Esto permite al servidor host conectarse y administrar cada máquina virtual a través de esta red de administración.</span><span class="sxs-lookup"><span data-stu-id="8dcba-196">This enables the host server to connect to and manage each virtual machine via this management network.</span></span> <span data-ttu-id="8dcba-197">El conmutador virtual de administración se elimina cuando finaliza la implementación.</span><span class="sxs-lookup"><span data-stu-id="8dcba-197">The management virtual switch is deleted when the deployment is finished.</span></span>

- <span data-ttu-id="8dcba-198">**Configuraciones específicas de vm base:** La configuración de esta sección debe configurarse para el cmdlet **Convert-CcIsoToVhdx.**</span><span class="sxs-lookup"><span data-stu-id="8dcba-198">**Base VM specific configurations:** Settings in this section must be configured for the **Convert-CcIsoToVhdx** cmdlet.</span></span>

    <span data-ttu-id="8dcba-199">Durante la preparación de la imagen de vm base, la máquina virtual base se conectará al conmutador de red interno.</span><span class="sxs-lookup"><span data-stu-id="8dcba-199">During base VM image preparation, the base VM will be connected to the internal network switch.</span></span> <span data-ttu-id="8dcba-200">La siguiente configuración es fundamental para que la máquina virtual pueda tener acceso a Internet:</span><span class="sxs-lookup"><span data-stu-id="8dcba-200">The following settings are critical for the VM to be able to access the Internet:</span></span>

  - <span data-ttu-id="8dcba-201">[Common] BaseVMIP: la dirección IP corpnet que se asignará a la máquina virtual base.</span><span class="sxs-lookup"><span data-stu-id="8dcba-201">[Common]BaseVMIP: the corpnet IP address to be assigned to the base VM.</span></span>

  - <span data-ttu-id="8dcba-202">[Red] CorpnetDefaultGateway: la puerta de enlace predeterminada que se asignará a la máquina virtual base.</span><span class="sxs-lookup"><span data-stu-id="8dcba-202">[Network]CorpnetDefaultGateway: the default gateway to be assigned to the base VM.</span></span>

  - <span data-ttu-id="8dcba-203">[Red] CorpnetDNSIPAddress: la dirección IP DNS que se asignará a la máquina virtual base.</span><span class="sxs-lookup"><span data-stu-id="8dcba-203">[Network]CorpnetDNSIPAddress: the DNS IP address to be assigned to the base VM.</span></span>

  - <span data-ttu-id="8dcba-204">[Red] WSUSServer: la dirección IP del servicio Windows Server Update.</span><span class="sxs-lookup"><span data-stu-id="8dcba-204">[Network]WSUSServer: the IP address of Windows Server Update Service.</span></span>

  - <span data-ttu-id="8dcba-205">[Red] WSUSStatusServer: la dirección IP del servidor de estado de Windows Server Update Service.</span><span class="sxs-lookup"><span data-stu-id="8dcba-205">[Network]WSUSStatusServer: the IP address of Windows Server Update Service status server.</span></span>

  - <span data-ttu-id="8dcba-206">[Red] EnableReferSupport: esto definirá si la compatibilidad con SIP REFER está habilitada o deshabilitada en la configuración de tronco a su IP/PBX.</span><span class="sxs-lookup"><span data-stu-id="8dcba-206">[Network]EnableReferSupport: this will define whether SIP REFER support is enabled or disabled on the Trunk Configuration to your IP/PBX.</span></span>

- <span data-ttu-id="8dcba-207">**IP internas:**</span><span class="sxs-lookup"><span data-stu-id="8dcba-207">**Internal IPs:**</span></span>

  - <span data-ttu-id="8dcba-208">Asegúrese de que la máscara de subred CorpnetIPPrefixLength es correcta.</span><span class="sxs-lookup"><span data-stu-id="8dcba-208">Make sure subnet mask CorpnetIPPrefixLength is correct.</span></span>

  - <span data-ttu-id="8dcba-209">Asegúrese de que no hay conflictos de IP para estas direcciones IP internas.</span><span class="sxs-lookup"><span data-stu-id="8dcba-209">Make sure there are no IP conflicts for these internal IPs.</span></span>

- <span data-ttu-id="8dcba-210">**IP externas:**</span><span class="sxs-lookup"><span data-stu-id="8dcba-210">**External IPs:**</span></span>

  - <span data-ttu-id="8dcba-211">Para IP pública de MR: especifique ExternalMRIPs para NAT o ExternalMRPublicIPs para NAT.</span><span class="sxs-lookup"><span data-stu-id="8dcba-211">For MR public IP: specify either ExternalMRIPs for non-NAT or ExternalMRPublicIPs for NAT.</span></span>

  - <span data-ttu-id="8dcba-212">ExternalSIPIPs y ExternalMRIPs pueden ser los mismos.</span><span class="sxs-lookup"><span data-stu-id="8dcba-212">ExternalSIPIPs and ExternalMRIPs can be the same.</span></span>

  - <span data-ttu-id="8dcba-213">Asegúrese de que la máscara de subred InternetIPPrefixLength es correcta.</span><span class="sxs-lookup"><span data-stu-id="8dcba-213">Make sure subnet mask InternetIPPrefixLength is correct.</span></span>

  - <span data-ttu-id="8dcba-214">Asegúrese de que no hay conflictos de IP para estas direcciones IP externas.</span><span class="sxs-lookup"><span data-stu-id="8dcba-214">Make sure there are no IP conflicts for these external IPs.</span></span>

- <span data-ttu-id="8dcba-215">**Puertas de enlace:**</span><span class="sxs-lookup"><span data-stu-id="8dcba-215">**Gateways:**</span></span>

  - <span data-ttu-id="8dcba-216">Si solo tiene una puerta de enlace, quite la sección de la puerta de enlace secundaria.</span><span class="sxs-lookup"><span data-stu-id="8dcba-216">If you have only one gateway, remove the section for the secondary gateway.</span></span> <span data-ttu-id="8dcba-217">Si tiene más de dos puertas de enlace, cree secciones adicionales copiando y pegando la existente y actualizándola.</span><span class="sxs-lookup"><span data-stu-id="8dcba-217">If you have more than two gateways, create additional sections by copying and pasting the existing one and then updating it.</span></span>

  - <span data-ttu-id="8dcba-218">Asegúrese de que la dirección IP y el puerto de las puertas de enlace son correctos.</span><span class="sxs-lookup"><span data-stu-id="8dcba-218">Make sure that the IP address and port of the gateway(s) are correct.</span></span>

  - <span data-ttu-id="8dcba-219">Para admitir ha de nivel de puerta de enlace RTC, deje la puerta de enlace secundaria y agregue las puertas de enlace adicionales que vaya a usar.</span><span class="sxs-lookup"><span data-stu-id="8dcba-219">To support PSTN gateway level HA, leave the secondary gateway, and add any additional gateways you will use.</span></span> <span data-ttu-id="8dcba-220">Puede copiar y pegar una entrada existente y, a continuación, actualizarla.</span><span class="sxs-lookup"><span data-stu-id="8dcba-220">You can copy and paste an existing entry and then update it.</span></span>

- <span data-ttu-id="8dcba-221">Opcionalmente, puede actualizar el valor de LocalRoute para restringir los números de llamadas salientes.</span><span class="sxs-lookup"><span data-stu-id="8dcba-221">Optionally, you can update the LocalRoute value to restrict outbound call numbers.</span></span>

## <a name="download-the-bits-to-the-site-directory"></a><span data-ttu-id="8dcba-222">Descargar los bits en el Directorio del sitio</span><span class="sxs-lookup"><span data-stu-id="8dcba-222">Download the bits to the Site Directory</span></span>

<span data-ttu-id="8dcba-223">Ejecute el siguiente cmdlet para descargar los bits y los archivos de información de versión en el **Directorio del sitio:**</span><span class="sxs-lookup"><span data-stu-id="8dcba-223">Run the following cmdlet to download the bits and version information files to the **Site Directory**:</span></span>

```powershell
Start-CcDownload
```

> [!NOTE]
> <span data-ttu-id="8dcba-224">Debe realizar este paso solo para el primer dispositivo.</span><span class="sxs-lookup"><span data-stu-id="8dcba-224">You need to perform this step for the first appliance only.</span></span> 

## <a name="prepare-base-virtual-disk-vhdx-from-the-downloaded-iso-file"></a><span data-ttu-id="8dcba-225">Preparar el disco virtual base (VHDX) desde el archivo ISO descargado</span><span class="sxs-lookup"><span data-stu-id="8dcba-225">Prepare base virtual disk (VHDX) from the downloaded ISO file</span></span>

<span data-ttu-id="8dcba-226">Este paso prepara un archivo de disco duro virtual (VHDX) a partir de la imagen ISO de Windows Server 2012.</span><span class="sxs-lookup"><span data-stu-id="8dcba-226">This step prepares a virtual hard disk (VHDX) file from the Windows Server 2012 ISO image.</span></span> <span data-ttu-id="8dcba-227">El VHDX se usará para crear máquinas virtuales durante la implementación.</span><span class="sxs-lookup"><span data-stu-id="8dcba-227">The VHDX will be used to create virtual machines during deployment.</span></span> <span data-ttu-id="8dcba-228">Se creará una máquina virtual temporal (VM base) y Windows Server 2012 se instalará desde el archivo ISO.</span><span class="sxs-lookup"><span data-stu-id="8dcba-228">A temporary virtual machine (base VM) will be created and Windows Server 2012 will be installed from the ISO file.</span></span> <span data-ttu-id="8dcba-229">Después de crear la máquina virtual, se instalarán algunos componentes necesarios y se aplicará la actualización más reciente de Windows.</span><span class="sxs-lookup"><span data-stu-id="8dcba-229">After the VM is created, some necessary components will be installed and the latest Windows update will be applied.</span></span> <span data-ttu-id="8dcba-230">Al final, la máquina virtual base se generalizará (sysprep) y se limpiará, dejando solo el archivo de disco virtual generado.</span><span class="sxs-lookup"><span data-stu-id="8dcba-230">At the end, the base VM will be generalized (sysprep) and cleaned up, leaving only the generated virtual disk file.</span></span>

> [!NOTE]
> <span data-ttu-id="8dcba-231">Debe realizar este paso solo para el primer dispositivo.</span><span class="sxs-lookup"><span data-stu-id="8dcba-231">You need to perform this step for the first appliance only.</span></span> 

<span data-ttu-id="8dcba-232">Antes de continuar con este paso, asegúrese de que se crea el modificador corpnet.</span><span class="sxs-lookup"><span data-stu-id="8dcba-232">Before proceeding with this step, make sure that the corpnet switch is created.</span></span> <span data-ttu-id="8dcba-233">Asimismo, confirme que las siguientes opciones de configuración están configuradas correctamente en el CloudConnector.ini archivo:</span><span class="sxs-lookup"><span data-stu-id="8dcba-233">Also, confirm that the following settings are correctly configured in the CloudConnector.ini file:</span></span>

- <span data-ttu-id="8dcba-234">[Red] CorpnetSwitchName</span><span class="sxs-lookup"><span data-stu-id="8dcba-234">[Network]CorpnetSwitchName</span></span>

- <span data-ttu-id="8dcba-235">[Common] BaseVMIP</span><span class="sxs-lookup"><span data-stu-id="8dcba-235">[Common]BaseVMIP</span></span>

- <span data-ttu-id="8dcba-236">[Red] CorpnetIPPrefixLength</span><span class="sxs-lookup"><span data-stu-id="8dcba-236">[Network]CorpnetIPPrefixLength</span></span>

- <span data-ttu-id="8dcba-237">[Red] CorpnetDefaultGateway</span><span class="sxs-lookup"><span data-stu-id="8dcba-237">[Network]CorpnetDefaultGateway</span></span>

- <span data-ttu-id="8dcba-238">[Red] CorpnetDNSIPAddress</span><span class="sxs-lookup"><span data-stu-id="8dcba-238">[Network]CorpnetDNSIPAddress</span></span>

<span data-ttu-id="8dcba-239">Inicie una consola de PowerShell como administrador y ejecute el siguiente cmdlet para convertir la imagen ISO en un disco duro virtual (VHD):</span><span class="sxs-lookup"><span data-stu-id="8dcba-239">Start a PowerShell console as administrator and run the following cmdlet to convert the ISO image to a virtual hard disk (VHD):</span></span>

```powershell
Convert-CcIsoToVhdx -IsoFilePath <Windows ISO File Path, including file name>
```

<span data-ttu-id="8dcba-240">Especifique la ruta de acceso completa, incluido el nombre de archivo, a la imagen ISO.</span><span class="sxs-lookup"><span data-stu-id="8dcba-240">Specify the full path, including file name, to the ISO image.</span></span> <span data-ttu-id="8dcba-241">Por ejemplo: C:\ISO\WindowsServer2012R2.iso.</span><span class="sxs-lookup"><span data-stu-id="8dcba-241">For example: C:\ISO\WindowsServer2012R2.iso.</span></span>

<span data-ttu-id="8dcba-242">El archivo VHD creado se almacena en la carpeta Directorio **del sitio** \Bits\VHD.</span><span class="sxs-lookup"><span data-stu-id="8dcba-242">The created VHD file is stored in the **Site Directory** \Bits\VHD folder.</span></span> <span data-ttu-id="8dcba-243">Puede obtener la ruta de acceso al **Directorio del sitio** ejecutando **Get-CcSiteDirectory**.</span><span class="sxs-lookup"><span data-stu-id="8dcba-243">You can get the path to the **Site Directory** by running the **Get-CcSiteDirectory**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8dcba-244">De forma predeterminada, la configuración de proxy no está configurada en la máquina virtual base.</span><span class="sxs-lookup"><span data-stu-id="8dcba-244">By default, proxy settings are not configured on the base VM.</span></span> <span data-ttu-id="8dcba-245">Si se necesita un proxy en el entorno de red para actualizar la máquina virtual a través de Windows Update, debes agregar el modificador -PauseBeforeUpdate al ejecutar "Convert-CcIsoToVhdx".</span><span class="sxs-lookup"><span data-stu-id="8dcba-245">If a proxy is required in your network environment to update the VM via Windows Update, you should add the -PauseBeforeUpdate switch when you run "Convert-CcIsoToVhdx".</span></span> <span data-ttu-id="8dcba-246">El script se pausará antes de Windows Update y tendrás la oportunidad de configurar manualmente el proxy en la máquina virtual.</span><span class="sxs-lookup"><span data-stu-id="8dcba-246">The script will pause before Windows Update and you'll have a chance to manually set up proxy on the VM.</span></span> <span data-ttu-id="8dcba-247">Después de configurar el proxy y de que la máquina virtual pueda tener acceso a Internet, puede reanudar el script para completar los pasos restantes.</span><span class="sxs-lookup"><span data-stu-id="8dcba-247">After the proxy is setup and the VM can access Internet, you can resume the script to complete the remaining steps.</span></span> 

### <a name="create-vhds-for-a-multi-site-deployment"></a><span data-ttu-id="8dcba-248">Crear VHD para una implementación de varios sitios</span><span class="sxs-lookup"><span data-stu-id="8dcba-248">Create VHDs for a multi-site deployment</span></span>

<span data-ttu-id="8dcba-249">Este es un paso opcional que solo se aplica a las implementaciones de varios sitios.</span><span class="sxs-lookup"><span data-stu-id="8dcba-249">This is an optional step that applies only to multi-site deployments.</span></span>

<span data-ttu-id="8dcba-250">Si va a implementar una implementación de varios sitios, no es necesario convertir la ISO en un VHD para cada sitio.</span><span class="sxs-lookup"><span data-stu-id="8dcba-250">If you are deploying a multi-site deployment, you do not need to convert the ISO to a VHD for each site.</span></span> <span data-ttu-id="8dcba-251">Puede copiar el VHDX creado para el primer sitio en el servidor host de un segundo sitio.</span><span class="sxs-lookup"><span data-stu-id="8dcba-251">You can copy the VHDX created for the first site to the host server for a second site.</span></span>

 <span data-ttu-id="8dcba-252">Copie el archivo en la misma ubicación de archivo **(** Directorio del sitio \Bits\CARPETA VHD) y con el mismo nombre de archivo, en el servidor host de un sitio adicional.</span><span class="sxs-lookup"><span data-stu-id="8dcba-252">Copy the file to the same file location ( **Site Directory** \Bits\VHD folder), and with the same file name, on the host server for an additional site.</span></span>

## <a name="set-the-powershell-execution-policy-to-remotesigned"></a><span data-ttu-id="8dcba-253">Establecer la directiva de ejecución de PowerShell en RemoteSigned</span><span class="sxs-lookup"><span data-stu-id="8dcba-253">Set the PowerShell Execution policy to RemoteSigned</span></span>

<span data-ttu-id="8dcba-254">Los scripts de PowerShell proporcionados requieren que la directiva de ejecución se establezca en RemoteSigned.</span><span class="sxs-lookup"><span data-stu-id="8dcba-254">The PowerShell scripts provided require that the execution policy be set to RemoteSigned.</span></span> <span data-ttu-id="8dcba-255">Para ver la configuración actual, abra una consola de PowerShell como administrador y, a continuación, ejecute el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="8dcba-255">To see the current setting, open a PowerShell console as administrator and then run the following cmdlet:</span></span>

```powershell
Get-ExecutionPolicy
```

<span data-ttu-id="8dcba-256">Si no está establecido en "RemoteSigned", ejecute el siguiente cmdlet para cambiarlo:</span><span class="sxs-lookup"><span data-stu-id="8dcba-256">If it is not set to "RemoteSigned," run the following cmdlet to change it:</span></span>

```powershell
Set-ExecutionPolicy RemoteSigned
```

## <a name="change-local-group-policy-on-the-host-machine-versions-141-and-earlier"></a><span data-ttu-id="8dcba-257">Cambiar la directiva de grupo local en el equipo host (versiones 1.4.1 y versiones anteriores)</span><span class="sxs-lookup"><span data-stu-id="8dcba-257">Change local Group Policy on the host machine (versions 1.4.1 and earlier)</span></span>

> [!NOTE]
> <span data-ttu-id="8dcba-258">Esta tarea no es necesaria para las versiones 1.4.2 y posteriores de Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="8dcba-258">This task is not required for Cloud Connector versions 1.4.2 and later.</span></span> 

<span data-ttu-id="8dcba-259">La cuenta CceService se crea durante la implementación de Skype Empresarial Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="8dcba-259">The CceService account is created during the Skype for Business Cloud Connector Edition deployment.</span></span> <span data-ttu-id="8dcba-260">Ejecuta el servicio de administración de Cloud Connector y requiere permiso para desinstalar el cloudconnector.msi.</span><span class="sxs-lookup"><span data-stu-id="8dcba-260">It runs the Cloud Connector Management Service and requires permission to uninstall the cloudconnector.msi.</span></span> <span data-ttu-id="8dcba-261">Debe cambiar la configuración de directiva de grupo en el equipo host de Cloud Connector para especificar que el registro de usuarios no se debe descargar cuando el usuario cierra sesión.</span><span class="sxs-lookup"><span data-stu-id="8dcba-261">You must change the group policy setting on the Cloud Connector host machine to specify that the user registry should not be unloaded when the user logs off.</span></span> <span data-ttu-id="8dcba-262">Siga los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="8dcba-262">Follow the steps below:</span></span>

### <a name="to-change-the-group-policy-setting"></a><span data-ttu-id="8dcba-263">Para cambiar la configuración de directiva de grupo</span><span class="sxs-lookup"><span data-stu-id="8dcba-263">To change the Group Policy setting</span></span>

1. <span data-ttu-id="8dcba-264">Abra el **Editor de directivas de grupo** ejecutando gpedit.msc.</span><span class="sxs-lookup"><span data-stu-id="8dcba-264">Open the **Group Policy Editor** by running gpedit.msc.</span></span>

2. <span data-ttu-id="8dcba-265">En el **Editor de directivas** de grupo, vaya a Plantillas administrativas > System > UserProfile > No descargar el registro de usuarios de forma forzar al cerrar sesión de usuario.</span><span class="sxs-lookup"><span data-stu-id="8dcba-265">In the **Group Policy Editor**, navigate to Administrative Templates > System > UserProfile > Do not forcefully unload the user registry at user logoff.</span></span> 

3. <span data-ttu-id="8dcba-266">Establezca su valor en **Enabled**.</span><span class="sxs-lookup"><span data-stu-id="8dcba-266">Set its value to **Enabled**.</span></span>

## <a name="set-up-your-microsoft-365-or-office-365-organization"></a><span data-ttu-id="8dcba-267">Configurar la organización de Microsoft 365 u Office 365</span><span class="sxs-lookup"><span data-stu-id="8dcba-267">Set up your Microsoft 365 or Office 365 organization</span></span>

<span data-ttu-id="8dcba-268">Se requiere una organización de Microsoft 365 u Office 365 con Skype Empresarial Online y sistema telefónico.</span><span class="sxs-lookup"><span data-stu-id="8dcba-268">A Microsoft 365 or Office 365 organization with Skype for Business Online and Phone System is required.</span></span> <span data-ttu-id="8dcba-269">Asegúrese de que el espacio empresarial está configurado y configurado antes de intentar usar Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="8dcba-269">Make sure your tenant is set up and configured before attempting to use Cloud Connector.</span></span>

<span data-ttu-id="8dcba-270">Algunos pasos de configuración de Microsoft 365 y Office 365 requieren que use PowerShell remoto de inquilino (TRPS) para configurar su organización de Microsoft 365 u Office 365.</span><span class="sxs-lookup"><span data-stu-id="8dcba-270">Some Microsoft 365 and Office 365 setup steps require you to use Tenant Remote PowerShell (TRPS) to configure your Microsoft 365 or Office 365 organization.</span></span> <span data-ttu-id="8dcba-271">**Esto debe instalarse en el servidor host.**</span><span class="sxs-lookup"><span data-stu-id="8dcba-271">**This should be installed on the host server.**</span></span> <span data-ttu-id="8dcba-272">Puede descargar el módulo de Skype Empresarial Online para PowerShell desde: [Skype Empresarial Online, Windows PowerShell Module](https://www.microsoft.com/download/details.aspx?id=39366).</span><span class="sxs-lookup"><span data-stu-id="8dcba-272">You can download the Skype for Business Online module for PowerShell from: [Skype for Business Online, Windows PowerShell Module](https://www.microsoft.com/download/details.aspx?id=39366).</span></span>

<span data-ttu-id="8dcba-273">Cree una cuenta de administrador de Skype Empresarial dedicada para la administración en línea de Cloud Connector, por ejemplo, CceOnlineManagmentAdministrator.</span><span class="sxs-lookup"><span data-stu-id="8dcba-273">Create a dedicated Skype for Business administrator account for Cloud Connector online management, for example CceOnlineManagmentAdministrator.</span></span> <span data-ttu-id="8dcba-274">El dispositivo usará esta cuenta para agregar o quitar el dispositivo, habilitar o deshabilitar la actualización automática del sistema operativo, habilitar o deshabilitar la actualización binaria automática.</span><span class="sxs-lookup"><span data-stu-id="8dcba-274">This account will be used by appliance to add or remove appliance, enable or disable automatic OS update, enable or disable automatic binary update.</span></span> <span data-ttu-id="8dcba-275">Establezca la contraseña de esta cuenta para que nunca expire para que no tenga que cambiarla para el servicio cada vez que expire.</span><span class="sxs-lookup"><span data-stu-id="8dcba-275">Set the password for this account to never expire so that you do not need to change it for the service each time it expires.</span></span>