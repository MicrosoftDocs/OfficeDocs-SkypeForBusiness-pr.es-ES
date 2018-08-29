---
title: Configuración de autenticación de dos factores en Skype para Business Server
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: c24e0891-e108-4cb6-9902-c6a4c8e68455
description: 'Resumen: Configurar la autenticación de dos factores en Skype para Business Server.'
ms.openlocfilehash: 4fc8791cd7459ecea89bb8101b2c1a488b6eace2
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/28/2018
ms.locfileid: "23250804"
---
# <a name="configure-two-factor-authentication-in-skype-for-business-server"></a><span data-ttu-id="e550d-103">Configuración de autenticación de dos factores en Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="e550d-103">Configure two-factor authentication in Skype for Business Server</span></span>

<span data-ttu-id="e550d-104">**Resumen:** Configuración de autenticación de dos factores en Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="e550d-104">**Summary:** Configure two-factor authentication in Skype for Business Server.</span></span>

<span data-ttu-id="e550d-105">En las siguientes secciones se describen los pasos necesarios para configurar la autenticación en dos fases para la implementación.</span><span class="sxs-lookup"><span data-stu-id="e550d-105">The following sections describe the steps necessary to configure two-factor authentication for your deployment.</span></span> <span data-ttu-id="e550d-106">Para obtener más información acerca de la autenticación en dos fases, vea [autenticación multifactor de habilitación de Office 365 para administradores online - Post del usuario de cuadrícula](https://go.microsoft.com/fwlink/p/?LinkId=313332).</span><span class="sxs-lookup"><span data-stu-id="e550d-106">For more information about Two-factor authentication, see [Enabling Office 365 multi-factor authentication for online administrators - Grid User Post](https://go.microsoft.com/fwlink/p/?LinkId=313332).</span></span>

## <a name="configure-an-enterprise-root-certificate-authority-to-support-smart-card-authentication"></a><span data-ttu-id="e550d-107">Configurar una entidad de certificación raíz empresarial para admitir la autenticación de tarjeta inteligente</span><span class="sxs-lookup"><span data-stu-id="e550d-107">Configure an Enterprise Root Certificate Authority to Support Smart Card Authentication</span></span>

<span data-ttu-id="e550d-108">En los siguientes pasos, se describe cómo configurar una CA raíz empresarial para admitir la autenticación de tarjeta inteligente:</span><span class="sxs-lookup"><span data-stu-id="e550d-108">The following steps describe how to configure an Enterprise Root CA to support Smart Card Authentication:</span></span>

<span data-ttu-id="e550d-109">Para obtener información sobre cómo instalar una entidad de certificación raíz de empresa, vea [instalar una entidad de certificación raíz de empresa](https://go.microsoft.com/fwlink/p/?LinkID=313364).</span><span class="sxs-lookup"><span data-stu-id="e550d-109">For information on how to install an Enterprise Root CA, see [Install an Enterprise Root Certification Authority](https://go.microsoft.com/fwlink/p/?LinkID=313364).</span></span>

1. <span data-ttu-id="e550d-110">Inicie sesión en el equipo de la CA empresarial usando una cuenta de administrador de dominio.</span><span class="sxs-lookup"><span data-stu-id="e550d-110">Log in to the Enterprise CA computer using a Domain Admin account.</span></span>

2. <span data-ttu-id="e550d-111">Inicie el Administrador del sistema y compruebe que está instalado el rol Inscripción web de entidad de certificación.</span><span class="sxs-lookup"><span data-stu-id="e550d-111">Launch System Manager, and verify that the Certificate Authority Web Enrollment role is installed.</span></span>

3. <span data-ttu-id="e550d-112">En el menú **Herramientas administrativas**, abra la consola de administración de **Entidad de certificación**.</span><span class="sxs-lookup"><span data-stu-id="e550d-112">From the **Administrative Tools** menu, open the **Certification Authority** management console.</span></span>

4. <span data-ttu-id="e550d-113">En el panel de navegación, expanda **Entidad de certificación**.</span><span class="sxs-lookup"><span data-stu-id="e550d-113">In the Navigation pane, expand **Certification Authority**.</span></span>

5. <span data-ttu-id="e550d-114">Haga clic con el botón derecho en **Plantillas de certificado**, elija **Nueva** y, luego, elija **Plantilla de certificado que se va a emitir**.</span><span class="sxs-lookup"><span data-stu-id="e550d-114">Right click on **Certificate Templates**, select **New**, then select **Certificate Template to Issue**.</span></span>

6. <span data-ttu-id="e550d-115">Elija **Enrollment Agent**, **Usuario de tarjeta inteligente** e **Inicio de sesión de Tarjeta inteligente**.</span><span class="sxs-lookup"><span data-stu-id="e550d-115">Select **Enrollment Agent**, **Smartcard User**, and **Smartcard Logon**.</span></span>

7. <span data-ttu-id="e550d-116">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="e550d-116">Click **OK**.</span></span>

8. <span data-ttu-id="e550d-117">Haga clic con el botón derecho en **Plantillas de certificado**.</span><span class="sxs-lookup"><span data-stu-id="e550d-117">Right click on **Certificate Templates**.</span></span>

9. <span data-ttu-id="e550d-118">Elija **Administrar**.</span><span class="sxs-lookup"><span data-stu-id="e550d-118">Select **Manage**.</span></span>

10. <span data-ttu-id="e550d-119">Abra las propiedades de la plantilla Usuario de tarjeta inteligente.</span><span class="sxs-lookup"><span data-stu-id="e550d-119">Open the properties of the Smartcard User template.</span></span>

11. <span data-ttu-id="e550d-120">Haga clic en la pestaña **Seguridad**.</span><span class="sxs-lookup"><span data-stu-id="e550d-120">Click on the **Security** tab.</span></span>

12. <span data-ttu-id="e550d-121">Cambie los permisos como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="e550d-121">Change the permissions as follows:</span></span>

    - <span data-ttu-id="e550d-122">Agregue cuentas de usuario individuales de AD con los permisos Leer/Inscribir (permitir), o</span><span class="sxs-lookup"><span data-stu-id="e550d-122">Add individual user AD accounts with Read/Enroll (Allow) permissions, or</span></span>

    - <span data-ttu-id="e550d-123">Agregue un grupo de seguridad que contenga los usuarios de tarjeta inteligente con permisos Leer/Inscribir (permitir), o</span><span class="sxs-lookup"><span data-stu-id="e550d-123">Add a security group containing smart card users with Read/Enroll (Allow) permissions, or</span></span>

    - <span data-ttu-id="e550d-124">Agregue el grupo Usuarios del dominio con los permisos Leer/Inscribir (permitir)</span><span class="sxs-lookup"><span data-stu-id="e550d-124">Add the Domain Users group with Read/Enroll (Allow) permissions</span></span>

## <a name="configure-windows-8-for-virtual-smart-cards"></a><span data-ttu-id="e550d-125">Configurar Windows 8 para las tarjetas inteligentes virtuales</span><span class="sxs-lookup"><span data-stu-id="e550d-125">Configure Windows 8 for Virtual Smart Cards</span></span>

<span data-ttu-id="e550d-126">Un factor que se necesita considerar al implementar la autenticación en dos fases y la tecnología de tarjetas inteligentes es el costo de la implementación.</span><span class="sxs-lookup"><span data-stu-id="e550d-126">One factor to consider when deploying two-factor authentication and smart card technology is the cost of implementation.</span></span> <span data-ttu-id="e550d-127">Windows 8 proporciona un número de nuevas capacidades de seguridad y una de las nuevas características más interesantes es la compatibilidad para tarjetas inteligentes virtuales.</span><span class="sxs-lookup"><span data-stu-id="e550d-127">Windows 8 provides a number of new security capabilities, and one of the most interesting new features is support for virtual smart cards.</span></span>

<span data-ttu-id="e550d-128">Para los equipos que vienen con el chip del Módulo de plataforma segura (TPM) que cumple la especificación versión 1.2, las organizaciones ahora pueden obtener beneficios del inicio de sesión con tarjeta inteligente sin hacer inversiones adicionales en hardware.</span><span class="sxs-lookup"><span data-stu-id="e550d-128">For computers equipped with a Trusted Platform Module (TPM) chip that meets specification version 1.2, organizations can now get the benefits of smart card logon without making any additional investments in hardware.</span></span> <span data-ttu-id="e550d-129">Para obtener más información, vea [uso de Virtual las tarjetas inteligentes con Windows 8](https://go.microsoft.com/fwlink/p/?LinkId=313365).</span><span class="sxs-lookup"><span data-stu-id="e550d-129">For more information, see [Using Virtual Smart Cards with Windows 8](https://go.microsoft.com/fwlink/p/?LinkId=313365).</span></span>

### <a name="to-configure-windows-8-for-virtual-smart-cards"></a><span data-ttu-id="e550d-130">Para configurar Windows 8 para las tarjetas inteligentes virtuales</span><span class="sxs-lookup"><span data-stu-id="e550d-130">To Configure Windows 8 for Virtual Smart Cards</span></span>

1. <span data-ttu-id="e550d-131">Inicie sesión el equipo de Windows 8 con las credenciales de un Skype para usuario habilitado para el negocio.</span><span class="sxs-lookup"><span data-stu-id="e550d-131">Log in to the Windows 8 computer using the credentials of a Skype for Business-enabled user.</span></span>

2. <span data-ttu-id="e550d-132">En la pantalla de inicio de Windows 8, mueva el cursor a la esquina inferior derecha de la pantalla.</span><span class="sxs-lookup"><span data-stu-id="e550d-132">At the Windows 8 Start screen, move your cursor to the bottom right corner of the screen.</span></span>

3. <span data-ttu-id="e550d-133">Seleccione la opción de **búsqueda** y, a continuación, busque forCommand símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="e550d-133">Select the **Search** option, and then search forCommand Prompt.</span></span>

4. <span data-ttu-id="e550d-134">Haga clic con el botón derecho en **Símbolo del sistema** y, luego, seleccione **Ejecutar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="e550d-134">Right click on **Command Prompt**, and then select **Run as Administrator**.</span></span>

5. <span data-ttu-id="e550d-135">Abra la consola de administración del Módulo de plataforma segura (TPM) ejecutando el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="e550d-135">Open the Trusted Platform Module (TPM) Management console by running the following command:</span></span>

  ```
  Tpm.msc
  ```

6. <span data-ttu-id="e550d-136">Desde la consola de administración de TPM, compruebe que la versión de la especificación de TPM sea al menos 1.2</span><span class="sxs-lookup"><span data-stu-id="e550d-136">From the TPM management console, verify that your TPM specification version is at least 1.2</span></span>

    > [!NOTE]
    > <span data-ttu-id="e550d-137">Si recibe un diálogo que indique que no se encuentra un Módulo de plataforma segura (TPM) compatible, compruebe que el equipo tenga un módulo TPM compatible y que esté habilitado en el sistema BIOS.</span><span class="sxs-lookup"><span data-stu-id="e550d-137">If you receive a dialog stating that a Compatible Trust Platform Module (TPM) cannot be found, verify that the computer has a compatible TPM module and that it is enabled in the system BIOS.</span></span>

7. <span data-ttu-id="e550d-138">Cierre la consola de administración de TPM</span><span class="sxs-lookup"><span data-stu-id="e550d-138">Close the TPM management console</span></span>

8. <span data-ttu-id="e550d-139">Desde el símbolo del sistema, cree una tarjeta inteligente virtual por medio del siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="e550d-139">From the command prompt, create a new virtual smart card using the following command:</span></span>

  ```
  TpmVscMgr create /name MyVSC /pin default /adminkey random /generate
  ```

    > [!NOTE]
    > <span data-ttu-id="e550d-140">Para proporcionar un valor PIN personalizado al crear la tarjeta inteligente virtual, use en su lugar la solicitud de PIN.</span><span class="sxs-lookup"><span data-stu-id="e550d-140">To provide a custom PIN value when creating the virtual smart card, use /pin prompt instead.</span></span>

9. <span data-ttu-id="e550d-141">Desde el símbolo del sistema, abra la consola de administración del equipo ejecutando el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="e550d-141">From the command prompt, open the Computer Management console by running the following command:</span></span>

  ```
  CompMgmt.msc
  ```

10. <span data-ttu-id="e550d-142">En la consola de administración del equipo, seleccione **Administración de dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="e550d-142">In the Computer Management console, select **Device Management**.</span></span>

11. <span data-ttu-id="e550d-143">Expanda **Lectores de tarjetas inteligentes**.</span><span class="sxs-lookup"><span data-stu-id="e550d-143">Expand **Smart card readers**.</span></span>

12. <span data-ttu-id="e550d-144">Compruebe que el nuevo lector de tarjetas inteligentes virtuales se haya creado correctamente.</span><span class="sxs-lookup"><span data-stu-id="e550d-144">Verify that the new virtual smart card reader has been created successfully.</span></span>

## <a name="enroll-users-for-smart-card-authentication"></a><span data-ttu-id="e550d-145">Inscribir a usuarios en la autenticación de tarjeta inteligente</span><span class="sxs-lookup"><span data-stu-id="e550d-145">Enroll users for smart card authentication</span></span>

<span data-ttu-id="e550d-p104">En general, existen dos métodos para inscribir a los usuarios en la autenticación de tarjeta inteligente. El método más sencillo consiste en que los usuarios se inscriban directamente en la autenticación de tarjeta inteligente a través de la inscripción web; el más complejo consiste en usar un Enrollment Agent. Este tema se centra en la autoinscripción para usar certificados de tarjeta inteligente.</span><span class="sxs-lookup"><span data-stu-id="e550d-p104">There are generally two methods for enrolling users for smart card authentication. The easier method involves having users enroll directly for smart card authentication using web enrollment, while the more complex method involves using an enrollment agent. This topic focuses on self-enrollment for smartcard certificates.</span></span>

<span data-ttu-id="e550d-149">Para obtener más información sobre inscribirse en nombre de los usuarios como un agente de inscripción, vea [inscripción de certificados en nombre de otros usuarios](https://go.microsoft.com/fwlink/p/?LinkID=313367).</span><span class="sxs-lookup"><span data-stu-id="e550d-149">For more information on enrolling on behalf of users as an enrollment agent, see [Enroll for Certificates on Behalf of Other Users](https://go.microsoft.com/fwlink/p/?LinkID=313367).</span></span>

### <a name="to-enroll-users-for-smart-card-authentication"></a><span data-ttu-id="e550d-150">Para inscribir a usuarios en la autenticación de tarjeta inteligente</span><span class="sxs-lookup"><span data-stu-id="e550d-150">To Enroll Users for Smart Card Authentication</span></span>

1. <span data-ttu-id="e550d-151">Inicie sesión en la estación de trabajo de Windows 8 con las credenciales de un Skype para usuario habilitado para el negocio.</span><span class="sxs-lookup"><span data-stu-id="e550d-151">Log in to the Windows 8 workstation using the credentials of a Skype for Business-enabled user.</span></span>

2. <span data-ttu-id="e550d-152">Inicie Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="e550d-152">Launch Internet Explorer.</span></span>

3. <span data-ttu-id="e550d-153">Vaya a la página de **Inscripción de certificado de entidad de certificación Web** (por ejemplo, https://MyCA.contoso.com/certsrv).</span><span class="sxs-lookup"><span data-stu-id="e550d-153">Browse to the **Certificate Authority Web Enrollment** page (e.g. https://MyCA.contoso.com/certsrv).</span></span>

    > [!NOTE]
    > <span data-ttu-id="e550d-154">Si usa Internet Explorer 10, puede que tenga que ver este sitio web en modo de compatibilidad.</span><span class="sxs-lookup"><span data-stu-id="e550d-154">If you are using Internet Explorer 10, you may need to view this website in Compatibility Mode.</span></span>

4. <span data-ttu-id="e550d-155">En la página **principal**, elija **Solicitar un certificado**.</span><span class="sxs-lookup"><span data-stu-id="e550d-155">On the **Welcome** Page, select **Request a certificate**.</span></span>

5. <span data-ttu-id="e550d-156">Luego elija **Solicitud avanzada**.</span><span class="sxs-lookup"><span data-stu-id="e550d-156">Next, select **Advanced Request**.</span></span>

6. <span data-ttu-id="e550d-157">Elija **Crear y enviar una solicitud a esta CA**.</span><span class="sxs-lookup"><span data-stu-id="e550d-157">Select **Create and submit a request to this CA**.</span></span>

7. <span data-ttu-id="e550d-158">Seleccione **Usuario de tarjeta inteligente** en la sección **Plantilla de certificado** y complete la solicitud de certificado avanzada con los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="e550d-158">Select **Smartcard User** under the **Certificate Template** section and complete the advanced certificate request with the following values:</span></span>

  - <span data-ttu-id="e550d-159">En **Opciones de clave**, confirme la siguiente configuración:</span><span class="sxs-lookup"><span data-stu-id="e550d-159">**Key Options** confirm he following settings:</span></span>

    - <span data-ttu-id="e550d-160">Active el botón de radio **Crear conjunto de claves nuevo**.</span><span class="sxs-lookup"><span data-stu-id="e550d-160">Select the **Create new key set** radio button</span></span>

    - <span data-ttu-id="e550d-161">En **CSP**, seleccione **Proveedor base de cifrado para tarjetas inteligentes de Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="e550d-161">For **CSP**, select **Microsoft Base Smart Card Crypto Provider**</span></span>

    - <span data-ttu-id="e550d-162">En **Uso de la clave**, seleccione **Exchange** (es la única opción disponible).</span><span class="sxs-lookup"><span data-stu-id="e550d-162">For **Key Usage**, select **Exchange** (this is the only option available).</span></span>

    - <span data-ttu-id="e550d-163">En **Tamaño de la clave**, escriba 2048.</span><span class="sxs-lookup"><span data-stu-id="e550d-163">For **Key Size**, enter 2048</span></span>

    - <span data-ttu-id="e550d-164">Confirme que está activado **Nombre automático de contenedor de claves**.</span><span class="sxs-lookup"><span data-stu-id="e550d-164">Confirm that **Automatic key container name** is selected</span></span>

    - <span data-ttu-id="e550d-165">Deje las demás casillas desactivadas.</span><span class="sxs-lookup"><span data-stu-id="e550d-165">Leave the other boxes unchecked.</span></span>

  - <span data-ttu-id="e550d-166">En **Opciones adicionales**, confirme los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="e550d-166">Under **Additional Options** confirm the following values:</span></span>

    - <span data-ttu-id="e550d-167">En **Formato de la solicitud**, seleccione **CMC**.</span><span class="sxs-lookup"><span data-stu-id="e550d-167">For **Request Format** select **CMC**.</span></span>

    - <span data-ttu-id="e550d-168">En **Algoritmo hash**, seleccione **sha1**.</span><span class="sxs-lookup"><span data-stu-id="e550d-168">For **Hash Algorithm** select **sha1**.</span></span>

    - <span data-ttu-id="e550d-169">Para **Nombre descriptivo** enterSmardcard certificado.</span><span class="sxs-lookup"><span data-stu-id="e550d-169">For **Friendly Name** enterSmardcard Certificate.</span></span>

8. <span data-ttu-id="e550d-170">Si utiliza un lector de tarjetas inteligentes físico, inserte la tarjeta inteligente en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="e550d-170">If you are using a physical smartcard reader, insert the smart card into the device.</span></span>

9. <span data-ttu-id="e550d-171">Haga clic en **Enviar** para enviar la solicitud de certificado.</span><span class="sxs-lookup"><span data-stu-id="e550d-171">Click **Submit** to submit the certificate request.</span></span>

10. <span data-ttu-id="e550d-172">Cuando se le pida, escriba el PIN que se usó para crear la tarjeta inteligente virtual.</span><span class="sxs-lookup"><span data-stu-id="e550d-172">When prompted, enter the PIN that was used to create the virtual smart card.</span></span>

    > [!NOTE]
    > <span data-ttu-id="e550d-173">El valor PIN de tarjeta inteligente virtual predeterminado es '12345678'.</span><span class="sxs-lookup"><span data-stu-id="e550d-173">The default virtual smart card PIN value is '12345678'.</span></span>

11. <span data-ttu-id="e550d-174">Una vez emitido el certificado, haga clic en **Instalar este certificado** para completar el proceso de inscripción.</span><span class="sxs-lookup"><span data-stu-id="e550d-174">Once the certificate has been issued, click **Install this certificate** to complete the enrollment process.</span></span>

    > [!NOTE]
    >  <span data-ttu-id="e550d-175">Si la solicitud de certificado produce el error "este explorador Web no admite la generación de las solicitudes de certificados", hay tres maneras posibles para resolver el problema:</span><span class="sxs-lookup"><span data-stu-id="e550d-175">If your certificate request fails with the error "This Web browser does not support the generation of certificate requests," there are three possible ways to resolve the issue:</span></span>

        a. Enable Compatibility View in Internet Explorer
        b. Enable the Turn on Intranet settings option in Internet Explorer
        c. Select the Reset all zones to default level setting under the Security tab in the Internet Explorer options menu.

## <a name="configure-active-directory-federation-services-ad-fs-20"></a><span data-ttu-id="e550d-176">Configurar los Servicios de federación de Active Directory (AD FS 2.0)</span><span class="sxs-lookup"><span data-stu-id="e550d-176">Configure Active Directory Federation Services (AD FS 2.0)</span></span>

<span data-ttu-id="e550d-177">En la siguiente sección se describe cómo configurar los servicios de federación de Active Directory (AD FS 2.0) para admitir autenticación multifactor.</span><span class="sxs-lookup"><span data-stu-id="e550d-177">The following section describes how to configure Active Directory Federation Services (AD FS 2.0) to support multi-factor authentication.</span></span> <span data-ttu-id="e550d-178">Para obtener información acerca de cómo instalar AD FS 2.0, vea [AD FS 2.0 Step y cómo a las guías](https://go.microsoft.com/fwlink/p/?LinkId=313374).</span><span class="sxs-lookup"><span data-stu-id="e550d-178">For information on how to install AD FS 2.0, see [AD FS 2.0 Step-by-Step and How To Guides](https://go.microsoft.com/fwlink/p/?LinkId=313374).</span></span>

> [!NOTE]
> <span data-ttu-id="e550d-179">Al instalar AD FS 2.0, no use Windows Server Manager para agregar el rol de los servicios de federación de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="e550d-179">When installing AD FS 2.0, do not use the Windows Server Manager to add the Active Directory Federation Services role.</span></span> <span data-ttu-id="e550d-180">En su lugar, descargue e instale el [paquete de Active Directory Federation Services 2.0 RTW](https://go.microsoft.com/fwlink/p/?LinkId=313375).</span><span class="sxs-lookup"><span data-stu-id="e550d-180">Instead, download and install the [Active Directory Federation Services 2.0 RTW package](https://go.microsoft.com/fwlink/p/?LinkId=313375).</span></span>

### <a name="to-configure-ad-fs-for-two-factor-authentication"></a><span data-ttu-id="e550d-181">Para configurar AD FS para la autenticación en dos fases</span><span class="sxs-lookup"><span data-stu-id="e550d-181">To configure AD FS for two-factor Authentication</span></span>

1. <span data-ttu-id="e550d-182">Inicie sesión en el equipo con AD FS 2.0 por medio de una cuenta de administrador de dominio.</span><span class="sxs-lookup"><span data-stu-id="e550d-182">Log in to the AD FS 2.0 computer using a Domain Admin account.</span></span>

2. <span data-ttu-id="e550d-183">Inicie Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e550d-183">Start Windows PowerShell.</span></span>

3. <span data-ttu-id="e550d-184">Desde la línea de comandos de Windows PowerShell, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="e550d-184">From the Windows PowerShell command-line, run the following command:</span></span>

  ```
  add-pssnapin Microsoft.Adfs.PowerShell
  ```

4. <span data-ttu-id="e550d-185">Establezca una asociación con cada uno de los servidores que estarán habilitados para la autenticación pasiva ejecutando el siguiente comando, sustituyendo el nombre del servidor específico para su implementación:</span><span class="sxs-lookup"><span data-stu-id="e550d-185">Establish a partnership with each server that will be enabled for passive authentication by running the following command, replacing the server name specific to your deployment:</span></span>

  ```
  Add-ADFSRelyingPartyTrust -Name SfBPool01-PassiveAuth -MetadataURL https://SfBpool01.contoso.com/passiveauth/federationmetadata/2007-06/federationmetadata.xml
  ```

5. <span data-ttu-id="e550d-186">Desde el menú Herramientas administrativas, inicie la consola de administración de AD FS 2.0.</span><span class="sxs-lookup"><span data-stu-id="e550d-186">From the Administrative Tools menu, launch the AD FS 2.0 Management console.</span></span>

6. <span data-ttu-id="e550d-187">Expanda **las relaciones de confianza** > **confía en el usuario de confianza**.</span><span class="sxs-lookup"><span data-stu-id="e550d-187">Expand **Trust Relationships** > **Relying Party Trusts**.</span></span>

7. <span data-ttu-id="e550d-188">Compruebe que se ha creado una nueva relación de confianza para su Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="e550d-188">Verify that a new trust has been created for your Skype for Business Server.</span></span>

8. <span data-ttu-id="e550d-189">Cree y asigne una regla de autorización de emisión para la relación de confianza para usuario autenticado por medio de Windows PowerShell ejecutando los siguientes comandos:</span><span class="sxs-lookup"><span data-stu-id="e550d-189">Create and assign an Issuance Authorization Rule for your relying party trust using Windows PowerShell by running the following commands:</span></span>

  ```
  $IssuanceAuthorizationRules = '@RuleTemplate = "AllowAllAuthzRule" => issue(Type = "https://schemas.microsoft.com/authorization/claims/permit", Value = "true");'
  ```

  ```
  Set-ADFSRelyingPartyTrust -TargetName SfBPool01-PassiveAuth
-IssuanceAuthorizationRules $IssuanceAuthorizationRules
  ```

9. <span data-ttu-id="e550d-190">Cree y asigne una regla de transformación de emisión para la relación de confianza para usuario autenticado por medio de Windows PowerShell ejecutando los siguientes comandos:</span><span class="sxs-lookup"><span data-stu-id="e550d-190">Create and assign an Issuance Transform Rule for your relying party trust using Windows PowerShell by running the following commands:</span></span>

  ```
  $IssuanceTransformRules = '@RuleTemplate = "PassThroughClaims" @RuleName = "Sid" c:[Type == "https://schemas.microsoft.com/ws/2008/06/identity/claims/primarysid"]=> issue(claim = c);'
  ```

  ```
  Set-ADFSRelyingPartyTrust -TargetName SfBPool01-PassiveAuth -IssuanceTransformRules $IssuanceTransformRules
  ```

10. <span data-ttu-id="e550d-191">Desde la consola de administración de AD FS 2.0, haga clic con el botón secundario en la relación de confianza para el usuario autenticado y seleccione **Editar reglas de notificaciones**.</span><span class="sxs-lookup"><span data-stu-id="e550d-191">From the AD FS 2.0 Management console, right click on your relying party trust and select **Edit Claim Rules**.</span></span>

11. <span data-ttu-id="e550d-192">Seleccione la pestaña **Reglas de autorización de emisión** y compruebe que la nueva regla de autorización se haya creado correctamente.</span><span class="sxs-lookup"><span data-stu-id="e550d-192">Select the **Issuance Authorization Rules** tab and verify that the new authorization rule was created successfully.</span></span>

12. <span data-ttu-id="e550d-193">Seleccione la pestaña **Reglas de transformación de emisión** y compruebe que la nueva regla de transformación se haya creado correctamente.</span><span class="sxs-lookup"><span data-stu-id="e550d-193">Select the **Issuance Transform Rules** tab and verify that the new transform rule was created successfully.</span></span>

## <a name="configuring-ad-fs-20-to-support-client-authentication"></a><span data-ttu-id="e550d-194">Configurar AD FS 2.0 para que sea compatible con la autenticación de clientes</span><span class="sxs-lookup"><span data-stu-id="e550d-194">Configuring AD FS 2.0 to support client authentication</span></span>

<span data-ttu-id="e550d-195">Hay dos tipos de autenticación posibles que se pueden configurar para permitir que AD FS 2.0 admita autenticación con tarjetas inteligentes:</span><span class="sxs-lookup"><span data-stu-id="e550d-195">There are two possible authentication types that can be configured to allow AD FS 2.0 to support authentication using smart cards:</span></span>

- <span data-ttu-id="e550d-196">Autenticación basada en formularios (FBA)</span><span class="sxs-lookup"><span data-stu-id="e550d-196">Forms-based authentication (FBA)</span></span>

- <span data-ttu-id="e550d-197">Autenticación de cliente de seguridad de capa de transporte</span><span class="sxs-lookup"><span data-stu-id="e550d-197">Transport Layer Security Client Authentication</span></span>

<span data-ttu-id="e550d-198">Al usar la autenticación basada en formularios, puede desarrollar una página web que permita a los usuarios autenticarse ya sea por medio de su nombre de usuario/contraseña o por medio de su tarjeta inteligente y PIN.</span><span class="sxs-lookup"><span data-stu-id="e550d-198">Using forms-based authentication, you can develop a web page that allows users to authenticate either by using their username/password or by using their smart card and PIN.</span></span> <span data-ttu-id="e550d-199">Este tema se enfoca en cómo implementar la autenticación de cliente de seguridad de capa de transporte con AD FS 2.0.</span><span class="sxs-lookup"><span data-stu-id="e550d-199">This topic focuses on how to implement Transport Layer Security Client Authentication with AD FS 2.0.</span></span> <span data-ttu-id="e550d-200">Para obtener más información acerca de los tipos de autenticación 2.0 de AD FS, vea [AD FS 2.0: cómo cambiar el tipo de autenticación Local](https://go.microsoft.com/fwlink/p/?LinkId=313384).</span><span class="sxs-lookup"><span data-stu-id="e550d-200">For more information about AD FS 2.0 authentication types, see [AD FS 2.0: How to Change the Local Authentication Type](https://go.microsoft.com/fwlink/p/?LinkId=313384).</span></span>

### <a name="to-configure-ad-fs-20-to-support-client-authentication"></a><span data-ttu-id="e550d-201">Para configurar AD FS 2.0 para admitir la autenticación de cliente</span><span class="sxs-lookup"><span data-stu-id="e550d-201">To Configure AD FS 2.0 to Support Client Authentication</span></span>

1. <span data-ttu-id="e550d-202">Inicie sesión en el equipo con AD FS 2.0 por medio de una cuenta de administrador de dominio.</span><span class="sxs-lookup"><span data-stu-id="e550d-202">Log in to the AD FS 2.0 computer using a Domain Admin account.</span></span>

2. <span data-ttu-id="e550d-203">Inicie Windows Explorer.</span><span class="sxs-lookup"><span data-stu-id="e550d-203">Launch Windows Explorer.</span></span>

3. <span data-ttu-id="e550d-204">Vaya a C:\inetpub\adfs\ls.</span><span class="sxs-lookup"><span data-stu-id="e550d-204">Browse to C:\inetpub\adfs\ls</span></span>

4. <span data-ttu-id="e550d-205">Haga una copia de seguridad del archivo web.config existente.</span><span class="sxs-lookup"><span data-stu-id="e550d-205">Make a backup copy of the existing web.config file.</span></span>

5. <span data-ttu-id="e550d-206">Abra el archivo web.config existente con el Bloc de notas.</span><span class="sxs-lookup"><span data-stu-id="e550d-206">Open the existing web.config file using Notepad.</span></span>

6. <span data-ttu-id="e550d-207">Desde la barra de menús, seleccione **Editar** y, luego, seleccione **Buscar**.</span><span class="sxs-lookup"><span data-stu-id="e550d-207">From the Menu bar, select **Edit** and then select **Find**.</span></span>

7. <span data-ttu-id="e550d-208">Buscar \<localAuthenticationTypes\>.</span><span class="sxs-lookup"><span data-stu-id="e550d-208">Search for \<localAuthenticationTypes\>.</span></span>

    <span data-ttu-id="e550d-209">Tenga en cuenta que hay cuatro tipos de autenticación enumerados, uno por línea.</span><span class="sxs-lookup"><span data-stu-id="e550d-209">Note that there are four authentication types listed, one per line.</span></span>

8. <span data-ttu-id="e550d-210">Mueva la línea que contiene el tipo de autenticación TLSClient hacia la parte superior de la lista en la sección.</span><span class="sxs-lookup"><span data-stu-id="e550d-210">Move the line containing the TLSClient authentication type to the top of the list in the section.</span></span>

9. <span data-ttu-id="e550d-211">Guarde y cierre el archivo web.config.</span><span class="sxs-lookup"><span data-stu-id="e550d-211">Save and Close the web.config file.</span></span>

10. <span data-ttu-id="e550d-212">Inicie un símbolo del sistema con privilegios elevados.</span><span class="sxs-lookup"><span data-stu-id="e550d-212">Launch a Command Prompt with elevated privileges.</span></span>

11. <span data-ttu-id="e550d-213">Reinicie IIS ejecutando el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="e550d-213">Restart IIS by running the following command:</span></span>

  ```
  IISReset /Restart /NoForce
  ```

## <a name="configuring-skype-for-business-server-passive-authentication"></a><span data-ttu-id="e550d-214">Configurar la autenticación pasiva de Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="e550d-214">Configuring Skype for Business Server passive authentication</span></span>

<span data-ttu-id="e550d-215">En la siguiente sección se describe cómo configurar Skype para Business Server admitir la autenticación pasiva.</span><span class="sxs-lookup"><span data-stu-id="e550d-215">The following section describes how to configure Skype for Business Server to support passive authentication.</span></span> <span data-ttu-id="e550d-216">Una vez habilitado, los usuarios que están habilitados para la autenticación en dos fases se necesitarán para usar una tarjeta inteligente física o virtual y un PIN válido para iniciar sesión mediante el Skype para clientes empresariales.</span><span class="sxs-lookup"><span data-stu-id="e550d-216">Once enabled, users who are enabled for two-factor authentication will be required to use a physical or virtual smart card and a valid PIN to sign in using the Skype for Business client.</span></span>

> [!NOTE]
> <span data-ttu-id="e550d-p109">Se recomienda encarecidamente a los clientes que habiliten la autenticación pasiva del registrador y los servicios web en el nivel de servicios. Si se habilita la autenticación pasiva del registrador y los servicios web en el nivel global, lo más probable es que se produzcan errores de autenticación en toda la organización cuando los usuarios no inicien sesión con el cliente de escritorio compatible.</span><span class="sxs-lookup"><span data-stu-id="e550d-p109">It is strongly recommended that customers enable passive authentication for Registrar and Web Services at the service level. If passive authentication is enabled for Registrar and Web Services at the global level, it will likely result in organization-wide authentication failures for users who are not signing in with the supported desktop client.</span></span>

### <a name="web-service-configuration"></a><span data-ttu-id="e550d-219">Configuración de servicios web</span><span class="sxs-lookup"><span data-stu-id="e550d-219">Web Service Configuration</span></span>

<span data-ttu-id="e550d-220">En los siguientes pasos, se describe cómo crear una configuración de servicios web personalizada para los Directores, grupos de servidores Enterprise y servidores Standard Edition que estarán habilitados para la autenticación pasiva.</span><span class="sxs-lookup"><span data-stu-id="e550d-220">The following steps describe how to create a custom web service configuration for Directors, Enterprise Pools, and Standard Edition servers that will be enabled for passive authentication.</span></span>

### <a name="to-create-a-custom-web-service-configuration"></a><span data-ttu-id="e550d-221">Para crear una configuración de servicios web personalizada</span><span class="sxs-lookup"><span data-stu-id="e550d-221">To create a custom web service configuration</span></span>

1. <span data-ttu-id="e550d-222">Inicie sesión en su Skype para servidor de negocio de servidor Front-End mediante un Skype para la cuenta de administrador de empresa.</span><span class="sxs-lookup"><span data-stu-id="e550d-222">Log in to your Skype for Business Server Front End server using a Skype for Business administrator account.</span></span>

2. <span data-ttu-id="e550d-223">Inicie el Skype para Shell de administración de servidor empresarial.</span><span class="sxs-lookup"><span data-stu-id="e550d-223">Launch the Skype for Business Server Management Shell.</span></span>

3. <span data-ttu-id="e550d-224">Desde Skype para Business Server Management Shell de línea de comandos, cree una nueva configuración de servicio Web para cada Director, grupo de servidores Enterprise y servidores Standard Edition que va a estar habilitada para autenticación pasiva, ejecute el comando siguiente:</span><span class="sxs-lookup"><span data-stu-id="e550d-224">From the Skype for Business Server Management Shell command-line, create a new Web Service configuration for each Director, Enterprise Pool, and Standard Edition server that will be enabled for passive authentication by running the following command:</span></span>

  ```
  New-CsWebServiceConfiguration -Identity "Service:WebServer:SfBPool01.contoso.com" -UseWsFedPassiveAuth $true -WsFedPassiveMetadataUri https://dc.contoso.com/federationmetadata/2007-06/federationmetadata.xml
  ```

    > [!CAUTION]
    > <span data-ttu-id="e550d-p110">El valor del FQDN WsFedPassiveMetadataUri es el Nombre del servicio de federación de su servidor AD FS 2.0. El valor de Nombre del servicio de federación se puede consultar en la consola de administración de AD FS 2.0 al hacer clic en **Servicio** en el panel de navegación y, luego, elegir **Editar propiedades del servicio de federación**.</span><span class="sxs-lookup"><span data-stu-id="e550d-p110">The value for the WsFedPassiveMetadataUri FQDN is the Federation Service Name of your AD FS 2.0 server. The Federation Service Name value can be found in the AD FS 2.0 Management Console by right-clicking on **Service** from the navigation pane and then selecting **Edit Federation Service Properties**.</span></span>

4. <span data-ttu-id="e550d-227">Para comprobar que los valores de UseWsFedPassiveAuth y WsFedPassiveMetadataUri se configuraron correctamente, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="e550d-227">Verify that the UseWsFedPassiveAuth and WsFedPassiveMetadataUri values were set correctly by running the following command:</span></span>

  ```
  Get-CsWebServiceConfiguration -identity "Service:WebServer:SfBPool01.contoso.com" | format-list UseWsFedPassiveAuth, WsFedPassiveMetadataUri
  ```

5. <span data-ttu-id="e550d-228">En los clientes, la autenticación pasiva es el método de autenticación menos preferido para la autenticación de WebTicket.</span><span class="sxs-lookup"><span data-stu-id="e550d-228">For clients, Passive Authentication is the least preferred authentication method for webticket authentication.</span></span> <span data-ttu-id="e550d-229">Para todos los directores, grupos de servidores Enterprise y servidores Standard Edition que va a estar habilitados para la autenticación de pasivo, todos los demás tipos de autenticación deben estar deshabilitados en Skype para los servicios Web empresarial ejecutando el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="e550d-229">For all Directors, Enterprise Pools, and Standard Edition servers that will be enabled for passive authentication, all other authentication types must be disabled in Skype for Business Web Services by running the following cmdlet:</span></span>

  ```
  Set-CsWebServiceConfiguration -Identity "Service:WebServer:SfBPool01.contoso.com" -UseCertificateAuth $false -UsePinAuth $false -UseWindowsAuth NONE
  ```

6. <span data-ttu-id="e550d-230">Para comprobar que se han deshabilitado correctamente todos los demás tipos de autenticación, ejecute el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="e550d-230">Verify that all other authentication types have been successfully disabled by running the following cmdlet:</span></span>

  ```
  Get-CsWebServiceConfiguration -Identity "Service:WebServer:SfBPool01.contoso.com" | format-list UseCertificateAuth, UsePinAuth, UseWindowsAuth
  ```

### <a name="proxy-configuration"></a><span data-ttu-id="e550d-231">Configuración de proxy</span><span class="sxs-lookup"><span data-stu-id="e550d-231">Proxy Configuration</span></span>

<span data-ttu-id="e550d-232">Cuando está deshabilitada la autenticación de certificados de Skype para los servicios Web empresarial, la Skype para clientes empresariales usará un tipo de autenticación menos preferido, como Kerberos o NTLM, para autenticarse en el servicio de registrador.</span><span class="sxs-lookup"><span data-stu-id="e550d-232">When certificate authentication is disabled for Skype for Business Web Services, the Skype for Business client will use a less preferred authentication type, such as Kerberos or NTLM, to authenticate to the Registrar service.</span></span> <span data-ttu-id="e550d-233">La autenticación de certificado se sigue necesitando para permitir al cliente que recupere un WebTicket, pero Kerberos y NTLM tienen que estar deshabilitados en el servicio registrador.</span><span class="sxs-lookup"><span data-stu-id="e550d-233">Certificate authentication is still needed to allow the client to retrieve a webticket, however, Kerberos and NTLM must be disabled for the Registrar service.</span></span>

<span data-ttu-id="e550d-234">En los siguientes pasos, se describe cómo crear una configuración de proxy personalizada para los grupos de servidores perimetrales, grupos de servidores Enterprise y servidores Standard Edition que estarán habilitados para la autenticación pasiva.</span><span class="sxs-lookup"><span data-stu-id="e550d-234">The following steps describe how to create a custom proxy configuration for Edge Pools, Enterprise Pools, and Standard Edition servers that will be enabled for passive authentication.</span></span>

### <a name="to-create-a-custom-proxy-configuration"></a><span data-ttu-id="e550d-235">Para crear una configuración de proxy personalizada</span><span class="sxs-lookup"><span data-stu-id="e550d-235">To create a custom proxy configuration</span></span>

1. <span data-ttu-id="e550d-236">Desde Skype para Business Server Management Shell de línea de comandos, cree una nueva configuración de proxy para cada Skype para servidor perimetral de servidores de negocio, grupo de servidores Enterprise y Standard Edition que va a estar habilitado para autenticación pasiva mediante la ejecución de la siguiente comandos:</span><span class="sxs-lookup"><span data-stu-id="e550d-236">From the Skype for Business Server Management Shell command-line, create a new proxy configuration for each Skype for Business Server Edge Pool, Enterprise Pool, and Standard Edition server that will be enabled for passive authentication by running the following commands:</span></span>

  ```
  New-CsProxyConfiguration -Identity "Service:EdgeServer:EdgePool01.contoso.com" -UseKerberosForClientToProxyAuth $False -UseNtlmForClientToProxyAuth $False
  ```

  ```
  New-CsProxyConfiguration -Identity "Service:Registrar:SfBPool01.contoso.com" -UseKerberosForClientToProxyAuth $False -UseNtlmForClientToProxyAuth $False
  ```

2. <span data-ttu-id="e550d-237">Para comprobar que se han deshabilitado correctamente todos los demás tipos de autenticación de proxy, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="e550d-237">Verify that all other proxy authentication types have been successfully disabled by running the following command:</span></span>

  ```
  Get-CsProxyConfiguration -Identity "Service:Registrar:SfBPool01.contoso.com" | format-list UseKerberosForClientToProxyAuth, UseNtlmForClientToProxyAuth, UseCertifcateForClientToProxyAuth
  ```

## <a name="see-also"></a><span data-ttu-id="e550d-238">Vea también</span><span class="sxs-lookup"><span data-stu-id="e550d-238">See also</span></span>

[<span data-ttu-id="e550d-239">Administrar la autenticación de dos factores en Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="e550d-239">Manage two-factor authentication in Skype for Business Server</span></span>](two-factor-authentication.md)

[<span data-ttu-id="e550d-240">Usar autenticación de dos factores con Skype para clientes empresariales y Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="e550d-240">Use two-factor authentication with Skype for Business client and Skype for Business Server</span></span>](use.md)