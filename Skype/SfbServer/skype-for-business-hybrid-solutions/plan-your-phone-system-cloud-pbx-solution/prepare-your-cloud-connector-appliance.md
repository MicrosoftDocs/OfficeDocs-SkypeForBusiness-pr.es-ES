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
description: Obtenga información sobre cómo preparar el dispositivo de Cloud Connector para su implementación y uso con el sistema telefónico (PBX en la nube).
ms.openlocfilehash: 74c4885a25b4176f4d5eb3ac27926bd9528387c6
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/03/2020
ms.locfileid: "47358946"
---
# <a name="prepare-your-cloud-connector-appliance"></a><span data-ttu-id="d9d84-103">Preparar el dispositivo de Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="d9d84-103">Prepare your Cloud Connector appliance</span></span>

> [!Important]
> <span data-ttu-id="d9d84-104">Cloud Connector Edition se retirará del 31 de julio de 2021 junto con Skype empresarial online.</span><span class="sxs-lookup"><span data-stu-id="d9d84-104">Cloud Connector Edition will retire July 31, 2021 along with Skype for Business Online.</span></span> <span data-ttu-id="d9d84-105">Una vez que la organización haya actualizado a Teams, obtenga información sobre cómo conectar la red de telefonía local a Microsoft Teams mediante el [enrutamiento directo](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page).</span><span class="sxs-lookup"><span data-stu-id="d9d84-105">Once your organization has upgraded to Teams, learn how to connect your on-premises telephony network to Teams using [Direct Routing](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page).</span></span>

<span data-ttu-id="d9d84-106">Obtenga información sobre cómo preparar el dispositivo de Cloud Connector para su implementación y uso con el sistema telefónico (PBX en la nube).</span><span class="sxs-lookup"><span data-stu-id="d9d84-106">Learn about how to prepare your Cloud Connector appliance for deployment and use with Phone System (Cloud PBX).</span></span>

<span data-ttu-id="d9d84-107">En esta sección se describe cómo obtener los archivos de instalación de Skype empresarial Cloud Connector Edition, instalar el software de Cloud Connector y preparar el dispositivo de Cloud Connector para su implementación.</span><span class="sxs-lookup"><span data-stu-id="d9d84-107">This section describes how to get the Skype for Business Cloud Connector Edition installation files, install Cloud Connector software, and prepare your Cloud Connector appliance for deployment.</span></span> <span data-ttu-id="d9d84-108">Una vez que haya completado todos los pasos de esta sección, estará listo para implementar Cloud Connector para un único sitio o varios sitios.</span><span class="sxs-lookup"><span data-stu-id="d9d84-108">After you have completed all steps in this section, you will be ready to deploy Cloud Connector for a single site or multiple sites.</span></span> <span data-ttu-id="d9d84-109">Si tiene una implementación existente de Cloud Connector y aún no ha actualizado a la versión 2,1 de Cloud Connector, consulte [Upgrade to a new version of Cloud Connector](upgrade-to-a-new-version-of-cloud-connector.md).</span><span class="sxs-lookup"><span data-stu-id="d9d84-109">If you have an existing Cloud Connector deployment, and you have not yet upgraded to Cloud Connector version 2.1, see [Upgrade to a new version of Cloud Connector](upgrade-to-a-new-version-of-cloud-connector.md).</span></span>

> [!NOTE]
> <span data-ttu-id="d9d84-110">Microsoft admite la versión actual de Cloud Connector Edition, versión 2,1.</span><span class="sxs-lookup"><span data-stu-id="d9d84-110">Microsoft supports the current version of Cloud Connector Edition, version 2.1.</span></span> <span data-ttu-id="d9d84-111">Si ha configurado la actualización automática, Cloud Connector se actualizará automáticamente.</span><span class="sxs-lookup"><span data-stu-id="d9d84-111">If you configured automatic update, Cloud Connector will update automatically.</span></span> <span data-ttu-id="d9d84-112">Si ha configurado la actualización manual, deberá actualizar a la versión 2,1 en un plazo de 60 días a partir de su publicación.</span><span class="sxs-lookup"><span data-stu-id="d9d84-112">If you configured manual update, you will need to upgrade to version 2.1 within 60 days of its release.</span></span> <span data-ttu-id="d9d84-113">Microsoft admitirá la versión anterior durante 60 días después de la publicación de 2,1 para permitirle el tiempo de actualización.</span><span class="sxs-lookup"><span data-stu-id="d9d84-113">Microsoft will support the previous version for 60 days after the release of 2.1 to allow you time to upgrade.</span></span> 

> [!NOTE]
> <span data-ttu-id="d9d84-114">Para la versión 2,1 de Cloud Connector y versiones posteriores, el dispositivo de host debe tener instalado .NET Framework 4.6.1 o posterior.</span><span class="sxs-lookup"><span data-stu-id="d9d84-114">For Cloud Connector version 2.1 and later, the host appliance must have .NET Framework 4.6.1 or later installed.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="d9d84-115">Para una implementación correcta, al ejecutar los cmdlets para configurar Skype empresarial Cloud Connector Edition, use siempre la misma sesión de consola que la que comenzó en.</span><span class="sxs-lookup"><span data-stu-id="d9d84-115">For successful deployment, when you run the cmdlets to configure Skype for Business Cloud Connector Edition, always use the same console session as the one you started in.</span></span> <span data-ttu-id="d9d84-116">Evite cambiar a sesiones diferentes durante la implementación y la configuración.</span><span class="sxs-lookup"><span data-stu-id="d9d84-116">Avoid switching to different sessions during the deployment and configuration.</span></span> 

> [!NOTE]
> <span data-ttu-id="d9d84-117">Hay algunos pasos que debe realizar para el primer dispositivo de la implementación: crear un recurso compartido para el directorio de sitios, descargar los bits y preparar un archivo de disco duro virtual (VHDX) desde la imagen ISO de Windows Server.</span><span class="sxs-lookup"><span data-stu-id="d9d84-117">There are some steps that you perform only for the first appliance in your deployment: creating a share for the site directory, downloading the bits, and preparing a virtual hard disk (VHDX) file from the Windows Server ISO image.</span></span> 

## <a name="download-the-skype-for-business-cloud-connector-edition-installer"></a><span data-ttu-id="d9d84-118">Descargar el instalador de Skype empresarial Cloud Connector Edition</span><span class="sxs-lookup"><span data-stu-id="d9d84-118">Download the Skype for Business Cloud Connector Edition installer</span></span>

1. <span data-ttu-id="d9d84-119">En el servidor host donde se ejecutarán las máquinas virtuales de Cloud Connector, descargue los archivos de instalación: [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller) .</span><span class="sxs-lookup"><span data-stu-id="d9d84-119">On the host server where the Cloud Connector VMs will run, download the installation files: [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller).</span></span> 

    > [!IMPORTANT]
    > <span data-ttu-id="d9d84-120">El servidor host debe poder acceder a Internet durante la instalación de Cloud Connector, ya que los archivos adicionales se descargan durante la instalación.</span><span class="sxs-lookup"><span data-stu-id="d9d84-120">The host server must be able to access the Internet during the installation of Cloud Connector because additional files are downloaded during the installation.</span></span> 

2. <span data-ttu-id="d9d84-121">Ejecute el instalador y acepte los valores predeterminados durante la instalación.</span><span class="sxs-lookup"><span data-stu-id="d9d84-121">Run the installer and accept the default values during the installation.</span></span>

3. <span data-ttu-id="d9d84-122">Confirme que la instalación se completó correctamente.</span><span class="sxs-lookup"><span data-stu-id="d9d84-122">Confirm that the installation completed successfully.</span></span>

## <a name="verify-the-installation-and-configure-the-environment"></a><span data-ttu-id="d9d84-123">Comprobación de la instalación y configuración del entorno</span><span class="sxs-lookup"><span data-stu-id="d9d84-123">Verify the installation and configure the environment</span></span>

1. <span data-ttu-id="d9d84-124">Abra una consola de PowerShell como administrador y confirme que los cmdlets de Skype empresarial Cloud Connector Edition están disponibles mediante el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="d9d84-124">Open a PowerShell console as administrator and confirm that the Skype for Business Cloud Connector Edition cmdlets are available using the following cmdlet:</span></span>

   ```powershell
   Get-Command *-Cc*
   ```

    <span data-ttu-id="d9d84-125">El comando debe devolver una lista de cmdlets para Skype empresarial Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="d9d84-125">The command should return a list of cmdlets for Skype for Business Cloud Connector Edition.</span></span>

2. <span data-ttu-id="d9d84-126">Los archivos VHD, SfBBits y VersionInfo se almacenarán en el **Directorio de sitios**.</span><span class="sxs-lookup"><span data-stu-id="d9d84-126">The VHDs, SfBBits, and VersionInfo files will be stored in the **Site Directory**.</span></span>

    <span data-ttu-id="d9d84-127">Puede encontrar la ubicación del directorio de **sitios** con el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="d9d84-127">You can find the location of the **Site Directory** with the following cmdlet:</span></span>

   ```powershell
   Get-CcSiteDirectory
   ```

    <span data-ttu-id="d9d84-128">El comando debe devolver una ubicación en el sistema de archivos.</span><span class="sxs-lookup"><span data-stu-id="d9d84-128">The command should return a location in your file system.</span></span> <span data-ttu-id="d9d84-129">La ubicación puede ser una carpeta local o un recurso compartido de archivos.</span><span class="sxs-lookup"><span data-stu-id="d9d84-129">The location can be a local folder or a file share.</span></span> <span data-ttu-id="d9d84-130">La ubicación predeterminada del **Directorio de sitios** es:%userprofile%\CloudConnector\SiteRoot.</span><span class="sxs-lookup"><span data-stu-id="d9d84-130">The default location for the **Site Directory** is: %USERPROFILE%\CloudConnector\SiteRoot.</span></span> <span data-ttu-id="d9d84-131">La ubicación predeterminada debe cambiarse a un recurso compartido de archivos en el primer dispositivo creado en cada sitio.</span><span class="sxs-lookup"><span data-stu-id="d9d84-131">The default location should be changed to a file share on the first appliance created in each site.</span></span>

    <span data-ttu-id="d9d84-132">La ubicación que seleccione debe ser:</span><span class="sxs-lookup"><span data-stu-id="d9d84-132">The location you select must be:</span></span>

   - <span data-ttu-id="d9d84-133">Se crea en el primer dispositivo creado en cada sitio.</span><span class="sxs-lookup"><span data-stu-id="d9d84-133">Created on the first appliance created in each site.</span></span>

   - <span data-ttu-id="d9d84-134">Una carpeta compartida a la que tengan acceso los otros servidores host (equipos) en el mismo sitio.</span><span class="sxs-lookup"><span data-stu-id="d9d84-134">A shared folder that is accessible by the other host servers (appliances) in the same site.</span></span>

     <span data-ttu-id="d9d84-135">Para establecer el **Directorio de sitios** en una ubicación distinta de la predeterminada, ejecute el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="d9d84-135">To set the **Site Directory** to a location other than the default, run the following cmdlet:</span></span>

   ```powershell
   Set-CcSiteDirectory <UNC File path>
   ```

    <span data-ttu-id="d9d84-136">Si va a implementar la alta disponibilidad (HA) para el sitio, asegúrese de ejecutar el cmdlet para establecer el **Directorio de sitios** en la misma ubicación en cada servidor host dentro del sitio.</span><span class="sxs-lookup"><span data-stu-id="d9d84-136">If you are deploying High Availability (HA) for the site, make sure you run the cmdlet to set the **Site Directory** to the same location on each host server within the site.</span></span>

    <span data-ttu-id="d9d84-137">Cuando inicie sesión e implemente cada dispositivo en el sitio, asegúrese de que su cuenta de inicio de sesión actual tiene el acceso adecuado al **Directorio de sitios**.</span><span class="sxs-lookup"><span data-stu-id="d9d84-137">When you log on and deploy each appliance in the site, make sure your current logon account has the right access to the **Site Directory**.</span></span>

3. <span data-ttu-id="d9d84-138">El **directorio** de la aplicación es el directorio raíz de trabajo local de Skype empresarial Cloud Connector Edition y la ubicación donde se guardan los certificados, las instancias y los registros externos.</span><span class="sxs-lookup"><span data-stu-id="d9d84-138">The **Appliance Directory** is the local working root directory for Skype for Business Cloud Connector Edition, and the location where external certificates, instances, and logs are saved.</span></span> <span data-ttu-id="d9d84-139">La ubicación predeterminada es:%USERPROFILE%\CloudConnector\ApplianceRoot.</span><span class="sxs-lookup"><span data-stu-id="d9d84-139">The default location is: %USERPROFILE%\CloudConnector\ApplianceRoot.</span></span>

    <span data-ttu-id="d9d84-140">Para encontrar la ubicación del **Directorio de dispositivos**, ejecute el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="d9d84-140">To find the location of the **Appliance Directory**, run the following cmdlet:</span></span>

   ```powershell
   Get-CcApplianceDirectory
   ```

    <span data-ttu-id="d9d84-141">Para establecer el **directorio del dispositivo** en una ubicación distinta de la predeterminada, ejecute el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="d9d84-141">To set the **Appliance Directory** to a location other than the default, run the following cmdlet:</span></span>

   ```powershell
   Set-CcApplianceDirectory <File path>
   ```

    <span data-ttu-id="d9d84-142">El directorio de la aplicación debe establecerse en una carpeta local del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="d9d84-142">The Appliance Directory should be set to a local folder on the appliance.</span></span> <span data-ttu-id="d9d84-143">Solo debe establecer el **Directorio de dispositivos** antes de iniciar la implementación de Skype empresarial Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="d9d84-143">You should only set the **Appliance Directory** before you start the Skype for Business Cloud Connector Edition deployment.</span></span> <span data-ttu-id="d9d84-144">Si lo cambia después de la implementación, tendrá que volver a implementar el servidor host.</span><span class="sxs-lookup"><span data-stu-id="d9d84-144">If you change it after deployment, you'll need to redeploy the host server.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="d9d84-145">La ruta de acceso al directorio de la **aplicación** no debe contener espacios.</span><span class="sxs-lookup"><span data-stu-id="d9d84-145">The path to the **Appliance Directory** must not contain any spaces.</span></span>

## <a name="set-the-path-for-the-external-edge-certificate"></a><span data-ttu-id="d9d84-146">Establecer la ruta de acceso para el certificado perimetral externo</span><span class="sxs-lookup"><span data-stu-id="d9d84-146">Set the path for the external Edge certificate</span></span>

- <span data-ttu-id="d9d84-147">Ejecute el siguiente cmdlet para establecer la ruta de acceso, incluido el nombre de archivo, en el certificado perimetral externo.</span><span class="sxs-lookup"><span data-stu-id="d9d84-147">Run the following cmdlet to set the path, including the file name, to the external Edge certificate.</span></span> <span data-ttu-id="d9d84-148">Por ejemplo: C:\certs\cce\ap.contoso.com.pfx.</span><span class="sxs-lookup"><span data-stu-id="d9d84-148">For example: C:\certs\cce\ap.contoso.com.pfx.</span></span> <span data-ttu-id="d9d84-149">El certificado debe contener claves privadas.</span><span class="sxs-lookup"><span data-stu-id="d9d84-149">The certificate must contain private keys.</span></span>

  ```powershell
  Set-CcExternalCertificateFilePath -Path <Full path to External certificate, including file name> -Target EdgeServer
  ```

    > [!NOTE]
    > <span data-ttu-id="d9d84-150">Tenga en cuenta que el parámetro-Target es específico de las versiones 1.4.2 y posteriores.</span><span class="sxs-lookup"><span data-stu-id="d9d84-150">Note that the -Target parameter is specific to versions 1.4.2 and later.</span></span> 

    <span data-ttu-id="d9d84-151">Especifique la ruta de acceso completa al certificado externo, incluido el nombre de archivo.</span><span class="sxs-lookup"><span data-stu-id="d9d84-151">Specify the full path to the external certificate, including the file name.</span></span> <span data-ttu-id="d9d84-152">El certificado se puede almacenar localmente o en un recurso compartido de archivos.</span><span class="sxs-lookup"><span data-stu-id="d9d84-152">The certificate can be stored locally or on a file share.</span></span> <span data-ttu-id="d9d84-153">Si el certificado se almacena en una carpeta compartida, la carpeta compartida debe crearse en el primer dispositivo de cada sitio y debe ser accesible para otros dispositivos que pertenezcan al mismo sitio.</span><span class="sxs-lookup"><span data-stu-id="d9d84-153">If the certificate is stored in a shared folder, the shared folder must be created on the first appliance of each site and must be accessible by other appliances belonging to the same site.</span></span> <span data-ttu-id="d9d84-154">Este cmdlet copia el certificado externo en el **Directorio de dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="d9d84-154">This cmdlet copies the external certificate to the **Appliance Directory**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="d9d84-155">**Si ha actualizado a Cloud Connector versión 1.4.2 o posterior**, asegúrese de que el certificado externo preparado contenga claves privadas y la cadena de certificados completa, incluidos el certificado de CA raíz y los certificados de CA intermedios.</span><span class="sxs-lookup"><span data-stu-id="d9d84-155">**If you have updated to Cloud Connector version 1.4.2 or later**, make sure your prepared external certificate contains private keys and the full certificate chain including the root CA certificate and the intermediate CA certificates.</span></span> <span data-ttu-id="d9d84-156">**Si aún no ha actualizado a Cloud Connector versión 1.4.2**, asegúrese de que el certificado externo preparado contenga claves privadas.</span><span class="sxs-lookup"><span data-stu-id="d9d84-156">**If you have NOT yet updated to Cloud Connector version 1.4.2**, make sure your prepared external certificate contains private keys.</span></span> <span data-ttu-id="d9d84-157">Este certificado externo debe ser emitido por una entidad de certificación que sea de confianza para Windows de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="d9d84-157">This external certificate must be issued by a Certificate Authority that is trusted by Windows by default.</span></span>

## <a name="set-the-path-for-the-external-pstn-gatewaysbc-certificate"></a><span data-ttu-id="d9d84-158">Establecer la ruta de acceso para el certificado de la puerta de enlace RTC/SBC externo</span><span class="sxs-lookup"><span data-stu-id="d9d84-158">Set the path for the external PSTN gateway/SBC certificate</span></span>

<span data-ttu-id="d9d84-159">Si está usando TLS entre el servidor de mediación y la puerta de enlace o el SBC RTC, ejecute el siguiente cmdlet para establecer la ruta de acceso, incluido el nombre de archivo, en el certificado de puerta de enlace.</span><span class="sxs-lookup"><span data-stu-id="d9d84-159">If you are using TLS between the Mediation Server and the PSTN gateway/SBC, run the following cmdlet to set the path, including the file name, to the gateway certificate.</span></span> <span data-ttu-id="d9d84-160">Por ejemplo: C:\certs\cce\sbc.contoso.com.cer.</span><span class="sxs-lookup"><span data-stu-id="d9d84-160">For example: C:\certs\cce\sbc.contoso.com.cer.</span></span> <span data-ttu-id="d9d84-161">El certificado debe contener la entidad de certificación raíz y la cadena intermedia para el certificado asignado a la puerta de enlace:</span><span class="sxs-lookup"><span data-stu-id="d9d84-161">The certificate must contain the root CA and the intermediate chain for the certificate assigned to the gateway:</span></span>

```powershell
Set-CcExternalCertificateFilePath -Path <Full path to gateway certificate, including file name> -Target MediationServer 
```

> [!NOTE]
> <span data-ttu-id="d9d84-162">Tenga en cuenta que el parámetro-Target es específico de las versiones 1.4.2 y posteriores.</span><span class="sxs-lookup"><span data-stu-id="d9d84-162">Note that the -Target parameter is specific to versions 1.4.2 and later.</span></span> 

## <a name="create-virtual-switches-in-hyper-v-manager"></a><span data-ttu-id="d9d84-163">Crear conmutadores virtuales en el administrador de Hyper-V</span><span class="sxs-lookup"><span data-stu-id="d9d84-163">Create virtual switches in Hyper-V Manager</span></span>

1. <span data-ttu-id="d9d84-164">Abra el administrador de conmutadores virtuales de **Administrador de Hyper-V**  >  **Virtual Switch Manager**y seleccione **nuevo administrador de conmutadores virtuales**.</span><span class="sxs-lookup"><span data-stu-id="d9d84-164">Open **Hyper-V Manager** > **Virtual Switch Manager**, and select **New Virtual Switch Manager**.</span></span>

2. <span data-ttu-id="d9d84-165">Cree un conmutador virtual externo y enlácelo al adaptador de red físico que está conectado al dominio de red interna:</span><span class="sxs-lookup"><span data-stu-id="d9d84-165">Create an External virtual switch and bind it to the physical network adapter that is connected to your internal network domain:</span></span>

    <span data-ttu-id="d9d84-166">Seleccione **permitir que el sistema operativo de administración comparta este adaptador de red** para este conmutador virtual.</span><span class="sxs-lookup"><span data-stu-id="d9d84-166">Select **Allow management operating system to share this network adapter** for this virtual switch.</span></span>

3. <span data-ttu-id="d9d84-167">Cree un conmutador virtual externo y enlácelo al adaptador de red físico que se redirige a Internet:</span><span class="sxs-lookup"><span data-stu-id="d9d84-167">Create an External virtual switch and bind it to the physical network adapter that is routed to the Internet:</span></span>

    <span data-ttu-id="d9d84-168">Anule la selección de permitir que el **sistema operativo de administración comparta este adaptador de red** para este conmutador virtual.</span><span class="sxs-lookup"><span data-stu-id="d9d84-168">De-select **Allow management operating system to share this network adapter** for this virtual switch.</span></span>

4. <span data-ttu-id="d9d84-169">Establezca el nombre del conmutador que conecta la red perimetral al dominio de red interno **SfB de CorpNet CorpNet**.</span><span class="sxs-lookup"><span data-stu-id="d9d84-169">Set the name of the switch that connects your perimeter network to your internal network domain **SfB CCE Corpnet Switch**.</span></span>

    <span data-ttu-id="d9d84-170">Establezca el nombre del conmutador que conecta la red perimetral a Internet **SFB CCE Internet switch**.</span><span class="sxs-lookup"><span data-stu-id="d9d84-170">Set the name of the switch that connects your perimeter network to the Internet **SfB CCE Internet Switch**.</span></span>

## <a name="update-the-cloudconnectorini-configuration-file"></a><span data-ttu-id="d9d84-171">Actualizar el archivo de configuración de CloudConnector.ini</span><span class="sxs-lookup"><span data-stu-id="d9d84-171">Update the CloudConnector.ini configuration file</span></span>

<span data-ttu-id="d9d84-172">Prepare el archivo de CloudConnector.ini con la información que ha recopilado en [determinar parámetros de implementación](plan-skype-for-business-cloud-connector-edition.md#BKMK_SiteParams) en el tema [Plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md) .</span><span class="sxs-lookup"><span data-stu-id="d9d84-172">Prepare the CloudConnector.ini file using the information you gathered in [Determine deployment parameters](plan-skype-for-business-cloud-connector-edition.md#BKMK_SiteParams) in the [Plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md) topic.</span></span>

<span data-ttu-id="d9d84-173">Para actualizar el archivo, primero ejecute el siguiente cmdlet para obtener la plantilla de ejemplo (CloudConnector.Sample.ini):</span><span class="sxs-lookup"><span data-stu-id="d9d84-173">To update the file, first run the following cmdlet to get the sample template (CloudConnector.Sample.ini):</span></span>

```powershell
Export-CcConfigurationSampleFile
```

<span data-ttu-id="d9d84-174">La plantilla de muestra se almacena en el **Directorio de dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="d9d84-174">The sample template is stored in the **Appliance Directory**.</span></span>

<span data-ttu-id="d9d84-175">Después de actualizarlo con los valores de su entorno, guarde el archivo como CloudConnector.ini en el **directorio**de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="d9d84-175">After you update it with the values for your environment, save the file as CloudConnector.ini in the **Appliance Directory**.</span></span> <span data-ttu-id="d9d84-176">Puede ejecutar **Get-CcApplianceDirectory** para determinar la ruta de acceso al **Directorio de dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="d9d84-176">You can run **Get-CcApplianceDirectory** to determine the path to the **Appliance Directory**.</span></span>

<span data-ttu-id="d9d84-177">Al actualizar el archivo. ini, tenga en cuenta lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="d9d84-177">When updating the .ini file, consider the following:</span></span>

> [!NOTE]
> <span data-ttu-id="d9d84-178">No todos los valores del archivo. ini se describen en esta sección, solo se tratan los que tienen una consideración especial.</span><span class="sxs-lookup"><span data-stu-id="d9d84-178">Not all values for the .ini file are discussed in this section, only those with a special consideration are covered here.</span></span> <span data-ttu-id="d9d84-179">Para obtener una lista completa, consulte la sección [determinar los parámetros de implementación](plan-skype-for-business-cloud-connector-edition.md#BKMK_SiteParams) del tema [Plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md) .</span><span class="sxs-lookup"><span data-stu-id="d9d84-179">For a full list, see the [Determine deployment parameters](plan-skype-for-business-cloud-connector-edition.md#BKMK_SiteParams) section of the [Plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md) topic.</span></span> <span data-ttu-id="d9d84-180">Para obtener más información sobre los valores que deben cambiarse para dispositivos adicionales o para nuevos sitios, vea [un único sitio con alta disponibilidad (ha) comparado con implementaciones de varios sitios](deploy-multiple-sites-in-cloud-connector.md#BKMK_SingleSitecomparedtomulti-site) en el tema [deploy Multiple sites in Cloud Connector](deploy-multiple-sites-in-cloud-connector.md).</span><span class="sxs-lookup"><span data-stu-id="d9d84-180">For more information about what values need to be changed for additional appliances or new sites, see [Single site with High Availability (HA) compared to multi-site deployments](deploy-multiple-sites-in-cloud-connector.md#BKMK_SingleSitecomparedtomulti-site) in the topic [Deploy multiple sites in Cloud Connector](deploy-multiple-sites-in-cloud-connector.md).</span></span> 

- <span data-ttu-id="d9d84-181">**SiteName:** El valor predeterminado es **sitio1**.</span><span class="sxs-lookup"><span data-stu-id="d9d84-181">**SiteName:** The default value is **Site1**.</span></span> <span data-ttu-id="d9d84-182">Debe actualizarlo antes de implementar Cloud Connector, ya que al ejecutar **Register-CcAppliance** para registrar un dispositivo en un sitio nuevo o existente, el cmdlet usará **siteName** para determinar qué sitio registrar.</span><span class="sxs-lookup"><span data-stu-id="d9d84-182">You must update it before you deploy Cloud Connector, because when you run **Register-CcAppliance** to register an appliance to an existing or new site, the cmdlet will use **SiteName** to determine which site to register.</span></span>

     <span data-ttu-id="d9d84-183">Si desea registrar el dispositivo en un sitio nuevo, el valor de **siteName** debe ser único y diferente de los sitios existentes.</span><span class="sxs-lookup"><span data-stu-id="d9d84-183">If you want to register the appliance to a new site, the value of **SiteName** must be unique and different from existing sites.</span></span> <span data-ttu-id="d9d84-184">Si desea registrar el dispositivo en un sitio existente, el valor de **siteName** en el archivo. ini debe coincidir con el nombre definido en la configuración de la organización de Microsoft 365 u Office 365.</span><span class="sxs-lookup"><span data-stu-id="d9d84-184">If you want to register the appliance to an existing site, the value for **SiteName** in .ini file must match the name defined in your Microsoft 365 or Office 365 organization configuration.</span></span> <span data-ttu-id="d9d84-185">Si va a copiar un archivo de configuración de un sitio a otro, asegúrese de actualizar el valor de **siteName** para cada sitio en consecuencia.</span><span class="sxs-lookup"><span data-stu-id="d9d84-185">If you are copying a configuration file from one site to another, make sure you update the value for **SiteName** for each site accordingly.</span></span>

- <span data-ttu-id="d9d84-186">**ServerName:** El nombre del servidor no debe contener el nombre de dominio y debe estar limitado a 15 caracteres.</span><span class="sxs-lookup"><span data-stu-id="d9d84-186">**ServerName:** The server name should not contain the domain name and should be limited to 15 characters.</span></span>

- <span data-ttu-id="d9d84-187">**HardwareType:** Si no establece o deja el valor en null, se usará el valor predeterminado de **normal** .</span><span class="sxs-lookup"><span data-stu-id="d9d84-187">**HardwareType:** If you don't set or leave the value to null, the default value of **Normal** will be used.</span></span> <span data-ttu-id="d9d84-188">Use **normal** si tiene previsto implementar la versión más grande de Cloud Connector para admitir 500 llamadas simultáneas por equipo host, como se describe en [Plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md).</span><span class="sxs-lookup"><span data-stu-id="d9d84-188">Use **Normal** if you plan to deploy the larger version of Cloud Connector to support 500 simultaneous calls per host machine as described in [Plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md).</span></span> <span data-ttu-id="d9d84-189">Use **Minimum** para una implementación más pequeña que admita 50 llamadas simultáneas.</span><span class="sxs-lookup"><span data-stu-id="d9d84-189">Use **Minimum** for a smaller deployment that supports 50 simultaneous calls.</span></span>

- <span data-ttu-id="d9d84-190">**Conmutadores virtuales de Internet/red corporativa/administración:** agregue el nombre de los conmutadores virtuales que ha creado.</span><span class="sxs-lookup"><span data-stu-id="d9d84-190">**Internet/Corpnet/Management virtual switches:**: Add the name of the virtual switches you have created.</span></span> <span data-ttu-id="d9d84-191">Para el conmutador virtual de administración, deje el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="d9d84-191">For the management virtual switch, leave the default value.</span></span> <span data-ttu-id="d9d84-192">El script de implementación creará el conmutador virtual de administración al principio de la implementación y lo eliminará cuando finalice la implementación.</span><span class="sxs-lookup"><span data-stu-id="d9d84-192">The deployment script will create the management virtual switch at the beginning of deployment and delete it when the deployment finishes.</span></span>

- <span data-ttu-id="d9d84-193">**ManagementIPPrefix:** ManagementIPPrefix en la sección red debe ser una subred diferente de otras IP internas.</span><span class="sxs-lookup"><span data-stu-id="d9d84-193">**ManagementIPPrefix:** ManagementIPPrefix in the Network section must be a different subnet from other internal IPs.</span></span> <span data-ttu-id="d9d84-194">Por ejemplo, como se muestra el valor predeterminado, ManagementIPPrefix es 192.168.213.0, mientras que AD IPAddress es 192.168.0.238.</span><span class="sxs-lookup"><span data-stu-id="d9d84-194">For example, as the default value shows, ManagementIPPrefix is 192.168.213.0, while AD IPAddress is 192.168.0.238.</span></span>

    <span data-ttu-id="d9d84-195">Los scripts de implementación crean un adaptador de red de administración en cada máquina virtual, asignan una IP de administración y la conectan a un conmutador virtual de administración.</span><span class="sxs-lookup"><span data-stu-id="d9d84-195">The deployment scripts create a management network adapter on each virtual machine, assign a management IP, and connect it to a management virtual switch.</span></span> <span data-ttu-id="d9d84-196">Esto permite que el servidor host se conecte a cada máquina virtual y la administre a través de esta red de administración.</span><span class="sxs-lookup"><span data-stu-id="d9d84-196">This enables the host server to connect to and manage each virtual machine via this management network.</span></span> <span data-ttu-id="d9d84-197">El conmutador virtual de administración se elimina al finalizar la implementación.</span><span class="sxs-lookup"><span data-stu-id="d9d84-197">The management virtual switch is deleted when the deployment is finished.</span></span>

- <span data-ttu-id="d9d84-198">**Configuraciones específicas de la máquina virtual base:** La configuración de esta sección debe estar configurada para el cmdlet **Convert-CcIsoToVhdx** .</span><span class="sxs-lookup"><span data-stu-id="d9d84-198">**Base VM specific configurations:** Settings in this section must be configured for the **Convert-CcIsoToVhdx** cmdlet.</span></span>

    <span data-ttu-id="d9d84-199">Durante la preparación de la imagen de la máquina virtual base, la máquina virtual base se conectará al conmutador de red interna.</span><span class="sxs-lookup"><span data-stu-id="d9d84-199">During base VM image preparation, the base VM will be connected to the internal network switch.</span></span> <span data-ttu-id="d9d84-200">La siguiente configuración es fundamental para que la máquina virtual pueda acceder a Internet:</span><span class="sxs-lookup"><span data-stu-id="d9d84-200">The following settings are critical for the VM to be able to access the Internet:</span></span>

  - <span data-ttu-id="d9d84-201">Comunes BaseVMIP: la dirección IP de CorpNet que se asignará a la máquina virtual base.</span><span class="sxs-lookup"><span data-stu-id="d9d84-201">[Common]BaseVMIP: the corpnet IP address to be assigned to the base VM.</span></span>

  - <span data-ttu-id="d9d84-202">Red CorpnetDefaultGateway: la puerta de enlace predeterminada que se asignará a la máquina virtual base.</span><span class="sxs-lookup"><span data-stu-id="d9d84-202">[Network]CorpnetDefaultGateway: the default gateway to be assigned to the base VM.</span></span>

  - <span data-ttu-id="d9d84-203">Red Cropnetdnsipaddress: la dirección IP de DNS que se asignará a la máquina virtual base.</span><span class="sxs-lookup"><span data-stu-id="d9d84-203">[Network]CorpnetDNSIPAddress: the DNS IP address to be assigned to the base VM.</span></span>

  - <span data-ttu-id="d9d84-204">Red WSUSServer: la dirección IP del servicio de actualización de Windows Server.</span><span class="sxs-lookup"><span data-stu-id="d9d84-204">[Network]WSUSServer: the IP address of Windows Server Update Service.</span></span>

  - <span data-ttu-id="d9d84-205">Red WSUSStatusServer: la dirección IP del servidor de estado del servicio de actualización de Windows Server.</span><span class="sxs-lookup"><span data-stu-id="d9d84-205">[Network]WSUSStatusServer: the IP address of Windows Server Update Service status server.</span></span>

  - <span data-ttu-id="d9d84-206">Red EnableReferSupport: define si la compatibilidad con SIP REFER está habilitada o deshabilitada en la configuración del tronco de su IP/PBX.</span><span class="sxs-lookup"><span data-stu-id="d9d84-206">[Network]EnableReferSupport: this will define whether SIP REFER support is enabled or disabled on the Trunk Configuration to your IP/PBX.</span></span>

- <span data-ttu-id="d9d84-207">**IP internas:**</span><span class="sxs-lookup"><span data-stu-id="d9d84-207">**Internal IPs:**</span></span>

  - <span data-ttu-id="d9d84-208">Asegúrese de que la máscara de subred Corpnetlpprefixlength es correcta.</span><span class="sxs-lookup"><span data-stu-id="d9d84-208">Make sure subnet mask CorpnetIPPrefixLength is correct.</span></span>

  - <span data-ttu-id="d9d84-209">Asegúrese de que no haya conflictos de IP en estas IP internas.</span><span class="sxs-lookup"><span data-stu-id="d9d84-209">Make sure there are no IP conflicts for these internal IPs.</span></span>

- <span data-ttu-id="d9d84-210">**IP externas:**</span><span class="sxs-lookup"><span data-stu-id="d9d84-210">**External IPs:**</span></span>

  - <span data-ttu-id="d9d84-211">Para la IP pública del MR: especifique ExternalMRIPs para NAT no NAT o ExternalMRPublicIPs para NAT.</span><span class="sxs-lookup"><span data-stu-id="d9d84-211">For MR public IP: specify either ExternalMRIPs for non-NAT or ExternalMRPublicIPs for NAT.</span></span>

  - <span data-ttu-id="d9d84-212">ExternalSIPIPs y ExternalMRIPs pueden ser iguales.</span><span class="sxs-lookup"><span data-stu-id="d9d84-212">ExternalSIPIPs and ExternalMRIPs can be the same.</span></span>

  - <span data-ttu-id="d9d84-213">Asegúrese de que la máscara de subred InternetIPPrefixLength es correcta.</span><span class="sxs-lookup"><span data-stu-id="d9d84-213">Make sure subnet mask InternetIPPrefixLength is correct.</span></span>

  - <span data-ttu-id="d9d84-214">Asegúrese de que no haya conflictos de IP en estas IP externas.</span><span class="sxs-lookup"><span data-stu-id="d9d84-214">Make sure there are no IP conflicts for these external IPs.</span></span>

- <span data-ttu-id="d9d84-215">**Puertas**</span><span class="sxs-lookup"><span data-stu-id="d9d84-215">**Gateways:**</span></span>

  - <span data-ttu-id="d9d84-216">Si solo tiene una puerta de enlace, quite la sección de la puerta de enlace secundaria.</span><span class="sxs-lookup"><span data-stu-id="d9d84-216">If you have only one gateway, remove the section for the secondary gateway.</span></span> <span data-ttu-id="d9d84-217">Si tiene más de dos puertas de enlace, cree secciones adicionales copiando y pegando la existente y, a continuación, actualizándolos.</span><span class="sxs-lookup"><span data-stu-id="d9d84-217">If you have more than two gateways, create additional sections by copying and pasting the existing one and then updating it.</span></span>

  - <span data-ttu-id="d9d84-218">Asegúrese de que la dirección IP y el puerto de las puertas de enlace sean correctos.</span><span class="sxs-lookup"><span data-stu-id="d9d84-218">Make sure that the IP address and port of the gateway(s) are correct.</span></span>

  - <span data-ttu-id="d9d84-219">Para admitir el nivel de puerta de enlace RTC, deje la puerta de enlace secundaria y agregue las puertas de enlace adicionales que vaya a usar.</span><span class="sxs-lookup"><span data-stu-id="d9d84-219">To support PSTN gateway level HA, leave the secondary gateway, and add any additional gateways you will use.</span></span> <span data-ttu-id="d9d84-220">Puede copiar y pegar una entrada existente y, a continuación, actualizarla.</span><span class="sxs-lookup"><span data-stu-id="d9d84-220">You can copy and paste an existing entry and then update it.</span></span>

- <span data-ttu-id="d9d84-221">Si lo desea, puede actualizar el valor de LocalRoute para restringir los números de llamadas salientes.</span><span class="sxs-lookup"><span data-stu-id="d9d84-221">Optionally, you can update the LocalRoute value to restrict outbound call numbers.</span></span>

## <a name="download-the-bits-to-the-site-directory"></a><span data-ttu-id="d9d84-222">Descargar los bits en el directorio de sitios</span><span class="sxs-lookup"><span data-stu-id="d9d84-222">Download the bits to the Site Directory</span></span>

<span data-ttu-id="d9d84-223">Ejecute el siguiente cmdlet para descargar los bits y los archivos de información de la versión en el **Directorio de sitios**:</span><span class="sxs-lookup"><span data-stu-id="d9d84-223">Run the following cmdlet to download the bits and version information files to the **Site Directory**:</span></span>

```powershell
Start-CcDownload
```

> [!NOTE]
> <span data-ttu-id="d9d84-224">Debe realizar este paso solo para el primer dispositivo.</span><span class="sxs-lookup"><span data-stu-id="d9d84-224">You need to perform this step for the first appliance only.</span></span> 

## <a name="prepare-base-virtual-disk-vhdx-from-the-downloaded-iso-file"></a><span data-ttu-id="d9d84-225">Preparar el disco virtual base (VHDX) desde el archivo ISO descargado</span><span class="sxs-lookup"><span data-stu-id="d9d84-225">Prepare base virtual disk (VHDX) from the downloaded ISO file</span></span>

<span data-ttu-id="d9d84-226">Este paso prepara un archivo de disco duro virtual (VHDX) a partir de la imagen ISO de Windows Server 2012.</span><span class="sxs-lookup"><span data-stu-id="d9d84-226">This step prepares a virtual hard disk (VHDX) file from the Windows Server 2012 ISO image.</span></span> <span data-ttu-id="d9d84-227">El VHDX se usará para crear máquinas virtuales durante la implementación.</span><span class="sxs-lookup"><span data-stu-id="d9d84-227">The VHDX will be used to create virtual machines during deployment.</span></span> <span data-ttu-id="d9d84-228">Se creará una máquina virtual temporal (VM base) y se instalará Windows Server 2012 desde el archivo ISO.</span><span class="sxs-lookup"><span data-stu-id="d9d84-228">A temporary virtual machine (base VM) will be created and Windows Server 2012 will be installed from the ISO file.</span></span> <span data-ttu-id="d9d84-229">Una vez creada la máquina virtual, se instalarán algunos de los componentes necesarios y se aplicará la última actualización de Windows.</span><span class="sxs-lookup"><span data-stu-id="d9d84-229">After the VM is created, some necessary components will be installed and the latest Windows update will be applied.</span></span> <span data-ttu-id="d9d84-230">Al final, la máquina virtual base se generalizará (Sysprep) y se limpiará, dejando solo el archivo de disco virtual generado.</span><span class="sxs-lookup"><span data-stu-id="d9d84-230">At the end, the base VM will be generalized (sysprep) and cleaned up, leaving only the generated virtual disk file.</span></span>

> [!NOTE]
> <span data-ttu-id="d9d84-231">Debe realizar este paso solo para el primer dispositivo.</span><span class="sxs-lookup"><span data-stu-id="d9d84-231">You need to perform this step for the first appliance only.</span></span> 

<span data-ttu-id="d9d84-232">Antes de continuar con este paso, asegúrese de que se haya creado el conmutador de red corporativa.</span><span class="sxs-lookup"><span data-stu-id="d9d84-232">Before proceeding with this step, make sure that the corpnet switch is created.</span></span> <span data-ttu-id="d9d84-233">Además, confirme que las siguientes opciones de configuración están correctamente configuradas en el archivo CloudConnector.ini:</span><span class="sxs-lookup"><span data-stu-id="d9d84-233">Also, confirm that the following settings are correctly configured in the CloudConnector.ini file:</span></span>

- <span data-ttu-id="d9d84-234">Red CorpnetSwitchName</span><span class="sxs-lookup"><span data-stu-id="d9d84-234">[Network]CorpnetSwitchName</span></span>

- <span data-ttu-id="d9d84-235">Comunes BaseVMIP</span><span class="sxs-lookup"><span data-stu-id="d9d84-235">[Common]BaseVMIP</span></span>

- <span data-ttu-id="d9d84-236">Red Corpnetlpprefixlength</span><span class="sxs-lookup"><span data-stu-id="d9d84-236">[Network]CorpnetIPPrefixLength</span></span>

- <span data-ttu-id="d9d84-237">Red CorpnetDefaultGateway</span><span class="sxs-lookup"><span data-stu-id="d9d84-237">[Network]CorpnetDefaultGateway</span></span>

- <span data-ttu-id="d9d84-238">Red Cropnetdnsipaddress</span><span class="sxs-lookup"><span data-stu-id="d9d84-238">[Network]CorpnetDNSIPAddress</span></span>

<span data-ttu-id="d9d84-239">Inicie una consola de PowerShell como administrador y ejecute el siguiente cmdlet para convertir la imagen ISO en un disco duro virtual (VHD):</span><span class="sxs-lookup"><span data-stu-id="d9d84-239">Start a PowerShell console as administrator and run the following cmdlet to convert the ISO image to a virtual hard disk (VHD):</span></span>

```powershell
Convert-CcIsoToVhdx -IsoFilePath <Windows ISO File Path, including file name>
```

<span data-ttu-id="d9d84-240">Especifique la ruta de acceso completa, incluido el nombre de archivo, en la imagen ISO.</span><span class="sxs-lookup"><span data-stu-id="d9d84-240">Specify the full path, including file name, to the ISO image.</span></span> <span data-ttu-id="d9d84-241">Por ejemplo: C:\ISO\WindowsServer2012R2.iso.</span><span class="sxs-lookup"><span data-stu-id="d9d84-241">For example: C:\ISO\WindowsServer2012R2.iso.</span></span>

<span data-ttu-id="d9d84-242">El archivo VHD creado se almacena en la carpeta **Directorio de sitios** \Bits\VHD.</span><span class="sxs-lookup"><span data-stu-id="d9d84-242">The created VHD file is stored in the **Site Directory** \Bits\VHD folder.</span></span> <span data-ttu-id="d9d84-243">Puede obtener la ruta de acceso al **Directorio de sitios** ejecutando el **Get-CcSiteDirectory**.</span><span class="sxs-lookup"><span data-stu-id="d9d84-243">You can get the path to the **Site Directory** by running the **Get-CcSiteDirectory**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d9d84-244">De forma predeterminada, la configuración de proxy no está configurada en la máquina virtual base.</span><span class="sxs-lookup"><span data-stu-id="d9d84-244">By default, proxy settings are not configured on the base VM.</span></span> <span data-ttu-id="d9d84-245">Si se requiere un proxy en el entorno de red para actualizar la máquina virtual a través de Windows Update, debe agregar el conmutador-PauseBeforeUpdate al ejecutar "Convert-CcIsoToVhdx".</span><span class="sxs-lookup"><span data-stu-id="d9d84-245">If a proxy is required in your network environment to update the VM via Windows Update, you should add the -PauseBeforeUpdate switch when you run "Convert-CcIsoToVhdx".</span></span> <span data-ttu-id="d9d84-246">El script se hará una pausa antes de Windows Update y tendrá la posibilidad de configurar manualmente el proxy en la máquina virtual.</span><span class="sxs-lookup"><span data-stu-id="d9d84-246">The script will pause before Windows Update and you'll have a chance to manually set up proxy on the VM.</span></span> <span data-ttu-id="d9d84-247">Después de configurar el proxy y de que la máquina virtual pueda acceder a Internet, puede reanudar el script para completar los pasos restantes.</span><span class="sxs-lookup"><span data-stu-id="d9d84-247">After the proxy is setup and the VM can access Internet, you can resume the script to complete the remaining steps.</span></span> 

### <a name="create-vhds-for-a-multi-site-deployment"></a><span data-ttu-id="d9d84-248">Crear VHD para una implementación de varios sitios</span><span class="sxs-lookup"><span data-stu-id="d9d84-248">Create VHDs for a multi-site deployment</span></span>

<span data-ttu-id="d9d84-249">Este es un paso opcional que solo se aplica a las implementaciones de varios sitios.</span><span class="sxs-lookup"><span data-stu-id="d9d84-249">This is an optional step that applies only to multi-site deployments.</span></span>

<span data-ttu-id="d9d84-250">Si va a implementar una implementación de varios sitios, no es necesario convertir la ISO en un VHD para cada sitio.</span><span class="sxs-lookup"><span data-stu-id="d9d84-250">If you are deploying a multi-site deployment, you do not need to convert the ISO to a VHD for each site.</span></span> <span data-ttu-id="d9d84-251">Puede copiar el VHDX creado para el primer sitio en el servidor host de un segundo sitio.</span><span class="sxs-lookup"><span data-stu-id="d9d84-251">You can copy the VHDX created for the first site to the host server for a second site.</span></span>

 <span data-ttu-id="d9d84-252">Copie el archivo en la misma ubicación del archivo ( **Directorio de sitios** \Bits\VHD) y con el mismo nombre de archivo, en el servidor host para un sitio adicional.</span><span class="sxs-lookup"><span data-stu-id="d9d84-252">Copy the file to the same file location ( **Site Directory** \Bits\VHD folder), and with the same file name, on the host server for an additional site.</span></span>

## <a name="set-the-powershell-execution-policy-to-remotesigned"></a><span data-ttu-id="d9d84-253">Establecer la Directiva de ejecución de PowerShell en RemoteSigned</span><span class="sxs-lookup"><span data-stu-id="d9d84-253">Set the PowerShell Execution policy to RemoteSigned</span></span>

<span data-ttu-id="d9d84-254">Los scripts de PowerShell proporcionados requieren que la Directiva de ejecución se establezca como RemoteSigned.</span><span class="sxs-lookup"><span data-stu-id="d9d84-254">The PowerShell scripts provided require that the execution policy be set to RemoteSigned.</span></span> <span data-ttu-id="d9d84-255">Para ver la configuración actual, abra una consola de PowerShell como administrador y, a continuación, ejecute el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="d9d84-255">To see the current setting, open a PowerShell console as administrator and then run the following cmdlet:</span></span>

```powershell
Get-ExecutionPolicy
```

<span data-ttu-id="d9d84-256">Si no se establece en "RemoteSigned", ejecute el siguiente cmdlet para cambiarlo:</span><span class="sxs-lookup"><span data-stu-id="d9d84-256">If it is not set to "RemoteSigned," run the following cmdlet to change it:</span></span>

```powershell
Set-ExecutionPolicy RemoteSigned
```

## <a name="change-local-group-policy-on-the-host-machine-versions-141-and-earlier"></a><span data-ttu-id="d9d84-257">Cambiar la Directiva de grupo local en el equipo host (versiones 1.4.1 y anteriores)</span><span class="sxs-lookup"><span data-stu-id="d9d84-257">Change local Group Policy on the host machine (versions 1.4.1 and earlier)</span></span>

> [!NOTE]
> <span data-ttu-id="d9d84-258">Esta tarea no es necesaria para las versiones de Cloud Connector 1.4.2 y posterior.</span><span class="sxs-lookup"><span data-stu-id="d9d84-258">This task is not required for Cloud Connector versions 1.4.2 and later.</span></span> 

<span data-ttu-id="d9d84-259">La cuenta CceService se crea durante la implementación de Skype empresarial Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="d9d84-259">The CceService account is created during the Skype for Business Cloud Connector Edition deployment.</span></span> <span data-ttu-id="d9d84-260">Ejecuta el servicio de administración de Cloud Connector y requiere permiso para desinstalar el cloudconnector.msi.</span><span class="sxs-lookup"><span data-stu-id="d9d84-260">It runs the Cloud Connector Management Service and requires permission to uninstall the cloudconnector.msi.</span></span> <span data-ttu-id="d9d84-261">Debe cambiar la configuración de la Directiva de grupo en la máquina host de Cloud Connector para especificar que el registro de usuarios no se debe descargar cuando el usuario cierra la sesión.</span><span class="sxs-lookup"><span data-stu-id="d9d84-261">You must change the group policy setting on the Cloud Connector host machine to specify that the user registry should not be unloaded when the user logs off.</span></span> <span data-ttu-id="d9d84-262">Siga los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="d9d84-262">Follow the steps below:</span></span>

### <a name="to-change-the-group-policy-setting"></a><span data-ttu-id="d9d84-263">Para cambiar la configuración de la Directiva de grupo</span><span class="sxs-lookup"><span data-stu-id="d9d84-263">To change the Group Policy setting</span></span>

1. <span data-ttu-id="d9d84-264">Abra el **Editor de directivas de grupo** ejecutando gpedit. msc.</span><span class="sxs-lookup"><span data-stu-id="d9d84-264">Open the **Group Policy Editor** by running gpedit.msc.</span></span>

2. <span data-ttu-id="d9d84-265">En el **Editor de directivas de grupo**, vaya a plantillas administrativas > System > userprofile > no descargar forzosamente el registro de usuarios al cerrar la sesión de usuario.</span><span class="sxs-lookup"><span data-stu-id="d9d84-265">In the **Group Policy Editor**, navigate to Administrative Templates > System > UserProfile > Do not forcefully unload the user registry at user logoff.</span></span> 

3. <span data-ttu-id="d9d84-266">Establezca su valor en **habilitado**.</span><span class="sxs-lookup"><span data-stu-id="d9d84-266">Set its value to **Enabled**.</span></span>

## <a name="set-up-your-microsoft-365-or-office-365-organization"></a><span data-ttu-id="d9d84-267">Configurar la organización de Microsoft 365 u Office 365</span><span class="sxs-lookup"><span data-stu-id="d9d84-267">Set up your Microsoft 365 or Office 365 organization</span></span>

<span data-ttu-id="d9d84-268">Se necesita una organización de Microsoft 365 u Office 365 con Skype empresarial online y el sistema telefónico.</span><span class="sxs-lookup"><span data-stu-id="d9d84-268">A Microsoft 365 or Office 365 organization with Skype for Business Online and Phone System is required.</span></span> <span data-ttu-id="d9d84-269">Asegúrese de que el inquilino esté configurado y configurado antes de intentar usar Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="d9d84-269">Make sure your tenant is set up and configured before attempting to use Cloud Connector.</span></span>

<span data-ttu-id="d9d84-270">Algunos pasos de configuración de Microsoft 365 y Office 365 requieren que use el PowerShell remoto del inquilino (TRPS) para configurar su organización de Microsoft 365 u Office 365.</span><span class="sxs-lookup"><span data-stu-id="d9d84-270">Some Microsoft 365 and Office 365 setup steps require you to use Tenant Remote PowerShell (TRPS) to configure your Microsoft 365 or Office 365 organization.</span></span> <span data-ttu-id="d9d84-271">**Debe estar instalado en el servidor host.**</span><span class="sxs-lookup"><span data-stu-id="d9d84-271">**This should be installed on the host server.**</span></span> <span data-ttu-id="d9d84-272">Puede descargar el módulo de Skype empresarial online para PowerShell desde: [Skype empresarial online, módulo de Windows PowerShell](https://www.microsoft.com/download/details.aspx?id=39366).</span><span class="sxs-lookup"><span data-stu-id="d9d84-272">You can download the Skype for Business Online module for PowerShell from: [Skype for Business Online, Windows PowerShell Module](https://www.microsoft.com/download/details.aspx?id=39366).</span></span>

<span data-ttu-id="d9d84-273">Cree una cuenta de administrador de Skype empresarial dedicado para la administración en línea de Cloud Connector, por ejemplo, Cceonlinemanagmentadministrator.</span><span class="sxs-lookup"><span data-stu-id="d9d84-273">Create a dedicated Skype for Business administrator account for Cloud Connector online management, for example CceOnlineManagmentAdministrator.</span></span> <span data-ttu-id="d9d84-274">Esta cuenta se usará en el dispositivo para agregar o eliminar el dispositivo, habilitar o deshabilitar la actualización automática del sistema operativo, habilitar o deshabilitar la actualización binaria automática.</span><span class="sxs-lookup"><span data-stu-id="d9d84-274">This account will be used by appliance to add or remove appliance, enable or disable automatic OS update, enable or disable automatic binary update.</span></span> <span data-ttu-id="d9d84-275">Establezca la contraseña de esta cuenta para que no expire nunca, de modo que no tenga que cambiarla para el servicio cada vez que expire.</span><span class="sxs-lookup"><span data-stu-id="d9d84-275">Set the password for this account to never expire so that you do not need to change it for the service each time it expires.</span></span>


