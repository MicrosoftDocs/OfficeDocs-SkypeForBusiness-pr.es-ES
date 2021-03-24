---
title: Configurar la autenticación en dos fases en Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: c24e0891-e108-4cb6-9902-c6a4c8e68455
description: 'Resumen: configure la autenticación en dos fases en Skype Empresarial Server.'
ms.openlocfilehash: 8651be3fbc07bb890637bc8d1c7c99a827d1ea1e
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51096826"
---
# <a name="configure-two-factor-authentication-in-skype-for-business-server"></a><span data-ttu-id="0f959-103">Configurar la autenticación en dos fases en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="0f959-103">Configure two-factor authentication in Skype for Business Server</span></span>

<span data-ttu-id="0f959-104">**Resumen:** Configure la autenticación en dos fases en Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="0f959-104">**Summary:** Configure two-factor authentication in Skype for Business Server.</span></span>

<span data-ttu-id="0f959-105">En las secciones siguientes se describen los pasos necesarios para configurar la autenticación en dos fases para la implementación.</span><span class="sxs-lookup"><span data-stu-id="0f959-105">The following sections describe the steps necessary to configure two-factor authentication for your deployment.</span></span> <span data-ttu-id="0f959-106">Para obtener más información acerca de la autenticación en dos [fases, vea Enabling Office 365 multi-factor authentication for online administrators - Grid User Post](https://go.microsoft.com/fwlink/p/?LinkId=313332).</span><span class="sxs-lookup"><span data-stu-id="0f959-106">For more information about Two-factor authentication, see [Enabling Office 365 multi-factor authentication for online administrators - Grid User Post](https://go.microsoft.com/fwlink/p/?LinkId=313332).</span></span>

## <a name="configure-an-enterprise-root-certificate-authority-to-support-smart-card-authentication"></a><span data-ttu-id="0f959-107">Configurar una entidad de certificación raíz de empresa para admitir la autenticación de tarjeta inteligente</span><span class="sxs-lookup"><span data-stu-id="0f959-107">Configure an Enterprise Root Certificate Authority to Support Smart Card Authentication</span></span>

<span data-ttu-id="0f959-108">Los siguientes pasos describen cómo configurar una CA raíz de empresa para admitir la autenticación de tarjeta inteligente:</span><span class="sxs-lookup"><span data-stu-id="0f959-108">The following steps describe how to configure an Enterprise Root CA to support Smart Card Authentication:</span></span>

<span data-ttu-id="0f959-109">Para obtener información sobre cómo instalar una ENTIDAD de certificación raíz de empresa, vea [Install an Enterprise Root Certification Authority](/previous-versions/windows/it-pro/windows-server-2003/cc776709(v=ws.10)).</span><span class="sxs-lookup"><span data-stu-id="0f959-109">For information on how to install an Enterprise Root CA, see [Install an Enterprise Root Certification Authority](/previous-versions/windows/it-pro/windows-server-2003/cc776709(v=ws.10)).</span></span>

1. <span data-ttu-id="0f959-110">Inicie sesión en el equipo de ca de empresa con una cuenta de administrador de dominio.</span><span class="sxs-lookup"><span data-stu-id="0f959-110">Log in to the Enterprise CA computer using a Domain Admin account.</span></span>

2. <span data-ttu-id="0f959-111">Inicie el Administrador del sistema y compruebe que el rol de inscripción web de entidad de certificación está instalado.</span><span class="sxs-lookup"><span data-stu-id="0f959-111">Launch System Manager, and verify that the Certificate Authority Web Enrollment role is installed.</span></span>

3. <span data-ttu-id="0f959-112">En el **menú Herramientas administrativas,** abra la consola **de administración de entidad de** certificación.</span><span class="sxs-lookup"><span data-stu-id="0f959-112">From the **Administrative Tools** menu, open the **Certification Authority** management console.</span></span>

4. <span data-ttu-id="0f959-113">En el panel navegación, expanda **Entidad de certificación**.</span><span class="sxs-lookup"><span data-stu-id="0f959-113">In the Navigation pane, expand **Certification Authority**.</span></span>

5. <span data-ttu-id="0f959-114">Haga clic con el botón **secundario en Plantillas de** certificado , seleccione **Nuevo** y, a continuación, seleccione Plantilla de certificado **para emitir**.</span><span class="sxs-lookup"><span data-stu-id="0f959-114">Right click on **Certificate Templates**, select **New**, then select **Certificate Template to Issue**.</span></span>

6. <span data-ttu-id="0f959-115">Seleccione **Agente de inscripción,** **Usuario de tarjeta inteligente** e Inicio de sesión de **tarjeta inteligente.**</span><span class="sxs-lookup"><span data-stu-id="0f959-115">Select **Enrollment Agent**, **Smartcard User**, and **Smartcard Logon**.</span></span>

7. <span data-ttu-id="0f959-116">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="0f959-116">Click **OK**.</span></span>

8. <span data-ttu-id="0f959-117">Haga clic con el botón secundario **en Plantillas de certificado**.</span><span class="sxs-lookup"><span data-stu-id="0f959-117">Right click on **Certificate Templates**.</span></span>

9. <span data-ttu-id="0f959-118">Seleccione **Administrar**.</span><span class="sxs-lookup"><span data-stu-id="0f959-118">Select **Manage**.</span></span>

10. <span data-ttu-id="0f959-119">Abra las propiedades de la plantilla Usuario de tarjeta inteligente.</span><span class="sxs-lookup"><span data-stu-id="0f959-119">Open the properties of the Smartcard User template.</span></span>

11. <span data-ttu-id="0f959-120">Haga clic en la **pestaña** Seguridad.</span><span class="sxs-lookup"><span data-stu-id="0f959-120">Click on the **Security** tab.</span></span>

12. <span data-ttu-id="0f959-121">Cambie los permisos de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="0f959-121">Change the permissions as follows:</span></span>

    - <span data-ttu-id="0f959-122">Agregar cuentas de AD de usuario individuales con permisos de lectura/inscripción (permitir) o</span><span class="sxs-lookup"><span data-stu-id="0f959-122">Add individual user AD accounts with Read/Enroll (Allow) permissions, or</span></span>

    - <span data-ttu-id="0f959-123">Agregar un grupo de seguridad que contenga usuarios de tarjetas inteligentes con permisos de lectura/inscripción (permitir) o</span><span class="sxs-lookup"><span data-stu-id="0f959-123">Add a security group containing smart card users with Read/Enroll (Allow) permissions, or</span></span>

    - <span data-ttu-id="0f959-124">Agregar el grupo Usuarios de dominio con permisos de lectura/inscripción (permitir)</span><span class="sxs-lookup"><span data-stu-id="0f959-124">Add the Domain Users group with Read/Enroll (Allow) permissions</span></span>

## <a name="configure-windows-8-for-virtual-smart-cards"></a><span data-ttu-id="0f959-125">Configurar Windows 8 para tarjetas inteligentes virtuales</span><span class="sxs-lookup"><span data-stu-id="0f959-125">Configure Windows 8 for Virtual Smart Cards</span></span>

<span data-ttu-id="0f959-126">Un factor a tener en cuenta al implementar la autenticación en dos fases y la tecnología de tarjetas inteligentes es el costo de implementación.</span><span class="sxs-lookup"><span data-stu-id="0f959-126">One factor to consider when deploying two-factor authentication and smart card technology is the cost of implementation.</span></span> <span data-ttu-id="0f959-127">Windows 8 proporciona una serie de nuevas funcionalidades de seguridad y una de las nuevas características más interesantes es la compatibilidad con tarjetas inteligentes virtuales.</span><span class="sxs-lookup"><span data-stu-id="0f959-127">Windows 8 provides a number of new security capabilities, and one of the most interesting new features is support for virtual smart cards.</span></span>

<span data-ttu-id="0f959-128">Para los equipos equipados con un chip de módulo de plataforma segura (TPM) que cumple con la versión 1.2 de la especificación, las organizaciones ahora pueden obtener las ventajas del inicio de sesión con tarjeta inteligente sin realizar ninguna inversión adicional en hardware.</span><span class="sxs-lookup"><span data-stu-id="0f959-128">For computers equipped with a Trusted Platform Module (TPM) chip that meets specification version 1.2, organizations can now get the benefits of smart card logon without making any additional investments in hardware.</span></span> <span data-ttu-id="0f959-129">Para obtener más información, consulta [Usar tarjetas inteligentes virtuales con Windows 8](https://go.microsoft.com/fwlink/p/?LinkId=313365).</span><span class="sxs-lookup"><span data-stu-id="0f959-129">For more information, see [Using Virtual Smart Cards with Windows 8](https://go.microsoft.com/fwlink/p/?LinkId=313365).</span></span>

### <a name="to-configure-windows-8-for-virtual-smart-cards"></a><span data-ttu-id="0f959-130">Para configurar Windows 8 para tarjetas inteligentes virtuales</span><span class="sxs-lookup"><span data-stu-id="0f959-130">To Configure Windows 8 for Virtual Smart Cards</span></span>

1. <span data-ttu-id="0f959-131">Inicie sesión en el equipo con Windows 8 con las credenciales de un usuario habilitado para Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="0f959-131">Log in to the Windows 8 computer using the credentials of a Skype for Business-enabled user.</span></span>

2. <span data-ttu-id="0f959-132">En la pantalla Inicio de Windows 8, mueve el cursor a la esquina inferior derecha de la pantalla.</span><span class="sxs-lookup"><span data-stu-id="0f959-132">At the Windows 8 Start screen, move your cursor to the bottom right corner of the screen.</span></span>

3. <span data-ttu-id="0f959-133">Seleccione la **opción Buscar** y, a continuación, busque Símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="0f959-133">Select the **Search** option, and then search forCommand Prompt.</span></span>

4. <span data-ttu-id="0f959-134">Haga clic con el **botón secundario en símbolo del** sistema y, a continuación, seleccione Ejecutar como **administrador**.</span><span class="sxs-lookup"><span data-stu-id="0f959-134">Right click on **Command Prompt**, and then select **Run as Administrator**.</span></span>

5. <span data-ttu-id="0f959-135">Abra la consola de administración del módulo de plataforma segura (TPM) ejecutando el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="0f959-135">Open the Trusted Platform Module (TPM) Management console by running the following command:</span></span>

  ```console
  Tpm.msc
  ```

6. <span data-ttu-id="0f959-136">Desde la consola de administración de TPM, compruebe que la versión de especificación del TPM es al menos 1.2</span><span class="sxs-lookup"><span data-stu-id="0f959-136">From the TPM management console, verify that your TPM specification version is at least 1.2</span></span>

    > [!NOTE]
    > <span data-ttu-id="0f959-137">Si recibe un cuadro de diálogo que indica que no se puede encontrar un módulo de plataforma de confianza compatible (TPM), compruebe que el equipo tiene un módulo TPM compatible y que está habilitado en el BIOS del sistema.</span><span class="sxs-lookup"><span data-stu-id="0f959-137">If you receive a dialog stating that a Compatible Trust Platform Module (TPM) cannot be found, verify that the computer has a compatible TPM module and that it is enabled in the system BIOS.</span></span>

7. <span data-ttu-id="0f959-138">Cerrar la consola de administración de TPM</span><span class="sxs-lookup"><span data-stu-id="0f959-138">Close the TPM management console</span></span>

8. <span data-ttu-id="0f959-139">Desde el símbolo del sistema, cree una nueva tarjeta inteligente virtual con el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="0f959-139">From the command prompt, create a new virtual smart card using the following command:</span></span>

  ```console
  TpmVscMgr create /name MyVSC /pin default /adminkey random /generate
  ```

    > [!NOTE]
    > <span data-ttu-id="0f959-140">Para proporcionar un valor de PIN personalizado al crear la tarjeta inteligente virtual, use /pin prompt en su lugar.</span><span class="sxs-lookup"><span data-stu-id="0f959-140">To provide a custom PIN value when creating the virtual smart card, use /pin prompt instead.</span></span>

9. <span data-ttu-id="0f959-141">En el símbolo del sistema, abra la consola de administración de equipos ejecutando el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="0f959-141">From the command prompt, open the Computer Management console by running the following command:</span></span>

  ```console
  CompMgmt.msc
  ```

10. <span data-ttu-id="0f959-142">En la consola administración del equipo, seleccione **Administración de dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="0f959-142">In the Computer Management console, select **Device Management**.</span></span>

11. <span data-ttu-id="0f959-143">Expanda **Lectores de tarjetas inteligentes**.</span><span class="sxs-lookup"><span data-stu-id="0f959-143">Expand **Smart card readers**.</span></span>

12. <span data-ttu-id="0f959-144">Compruebe que el nuevo lector de tarjetas inteligentes virtuales se haya creado correctamente.</span><span class="sxs-lookup"><span data-stu-id="0f959-144">Verify that the new virtual smart card reader has been created successfully.</span></span>

## <a name="enroll-users-for-smart-card-authentication"></a><span data-ttu-id="0f959-145">Inscribir usuarios para la autenticación con tarjeta inteligente</span><span class="sxs-lookup"><span data-stu-id="0f959-145">Enroll users for smart card authentication</span></span>

<span data-ttu-id="0f959-146">Por lo general, hay dos métodos para inscribir usuarios para la autenticación de tarjetas inteligentes.</span><span class="sxs-lookup"><span data-stu-id="0f959-146">There are generally two methods for enrolling users for smart card authentication.</span></span> <span data-ttu-id="0f959-147">El método más sencillo implica que los usuarios se inscriban directamente para la autenticación de tarjetas inteligentes mediante la inscripción web, mientras que el método más complejo implica el uso de un agente de inscripción.</span><span class="sxs-lookup"><span data-stu-id="0f959-147">The easier method involves having users enroll directly for smart card authentication using web enrollment, while the more complex method involves using an enrollment agent.</span></span> <span data-ttu-id="0f959-148">Este tema se centra en la inscripción automática para certificados de tarjeta inteligente.</span><span class="sxs-lookup"><span data-stu-id="0f959-148">This topic focuses on self-enrollment for smartcard certificates.</span></span>

<span data-ttu-id="0f959-149">Para obtener más información sobre la inscripción en nombre de los usuarios como agente de inscripción, vea Inscribir para certificados [en nombre de otros usuarios](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc770802(v=ws.11)).</span><span class="sxs-lookup"><span data-stu-id="0f959-149">For more information on enrolling on behalf of users as an enrollment agent, see [Enroll for Certificates on Behalf of Other Users](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc770802(v=ws.11)).</span></span>

### <a name="to-enroll-users-for-smart-card-authentication"></a><span data-ttu-id="0f959-150">Para inscribir usuarios para autenticación con tarjeta inteligente</span><span class="sxs-lookup"><span data-stu-id="0f959-150">To Enroll Users for Smart Card Authentication</span></span>

1. <span data-ttu-id="0f959-151">Inicie sesión en la estación de trabajo de Windows 8 con las credenciales de un usuario habilitado para Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="0f959-151">Log in to the Windows 8 workstation using the credentials of a Skype for Business-enabled user.</span></span>

2. <span data-ttu-id="0f959-152">Inicie Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="0f959-152">Launch Internet Explorer.</span></span>

3. <span data-ttu-id="0f959-153">Vaya a la **página Inscripción web de entidad de** certificación (por ejemplo, https://MyCA.contoso.com/certsrv) .</span><span class="sxs-lookup"><span data-stu-id="0f959-153">Browse to the **Certificate Authority Web Enrollment** page (e.g. https://MyCA.contoso.com/certsrv).</span></span>

    > [!NOTE]
    > <span data-ttu-id="0f959-154">Si usa Internet Explorer 10, es posible que deba ver este sitio web en modo de compatibilidad.</span><span class="sxs-lookup"><span data-stu-id="0f959-154">If you are using Internet Explorer 10, you may need to view this website in Compatibility Mode.</span></span>

4. <span data-ttu-id="0f959-155">En la **página de** bienvenida, seleccione Solicitar **un certificado**.</span><span class="sxs-lookup"><span data-stu-id="0f959-155">On the **Welcome** Page, select **Request a certificate**.</span></span>

5. <span data-ttu-id="0f959-156">A continuación, **seleccione Solicitud avanzada**.</span><span class="sxs-lookup"><span data-stu-id="0f959-156">Next, select **Advanced Request**.</span></span>

6. <span data-ttu-id="0f959-157">Seleccione **Crear y enviar una solicitud a esta CA**.</span><span class="sxs-lookup"><span data-stu-id="0f959-157">Select **Create and submit a request to this CA**.</span></span>

7. <span data-ttu-id="0f959-158">Seleccione **Usuario de tarjeta inteligente en** la sección Plantilla **de** certificado y complete la solicitud de certificado avanzada con los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="0f959-158">Select **Smartcard User** under the **Certificate Template** section and complete the advanced certificate request with the following values:</span></span>

  - <span data-ttu-id="0f959-159">**Las opciones clave** confirman que sigue la configuración:</span><span class="sxs-lookup"><span data-stu-id="0f959-159">**Key Options** confirm he following settings:</span></span>

    - <span data-ttu-id="0f959-160">Seleccione el **botón de opción Crear nuevo conjunto de** teclas</span><span class="sxs-lookup"><span data-stu-id="0f959-160">Select the **Create new key set** radio button</span></span>

    - <span data-ttu-id="0f959-161">Para **CSP,** seleccione Proveedor criptográfico **de tarjeta inteligente de Microsoft Base**</span><span class="sxs-lookup"><span data-stu-id="0f959-161">For **CSP**, select **Microsoft Base Smart Card Crypto Provider**</span></span>

    - <span data-ttu-id="0f959-162">Para **Uso de clave,** **seleccione Exchange** (esta es la única opción disponible).</span><span class="sxs-lookup"><span data-stu-id="0f959-162">For **Key Usage**, select **Exchange** (this is the only option available).</span></span>

    - <span data-ttu-id="0f959-163">Para **Tamaño de clave**, escriba 2048</span><span class="sxs-lookup"><span data-stu-id="0f959-163">For **Key Size**, enter 2048</span></span>

    - <span data-ttu-id="0f959-164">Confirmar que **el nombre del contenedor de claves automático** está seleccionado</span><span class="sxs-lookup"><span data-stu-id="0f959-164">Confirm that **Automatic key container name** is selected</span></span>

    - <span data-ttu-id="0f959-165">Deje las otras casillas desactivadas.</span><span class="sxs-lookup"><span data-stu-id="0f959-165">Leave the other boxes unchecked.</span></span>

  - <span data-ttu-id="0f959-166">En **Opciones adicionales,** confirme los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="0f959-166">Under **Additional Options** confirm the following values:</span></span>

    - <span data-ttu-id="0f959-167">Para **Formato de solicitud,** **seleccione CMC**.</span><span class="sxs-lookup"><span data-stu-id="0f959-167">For **Request Format** select **CMC**.</span></span>

    - <span data-ttu-id="0f959-168">Para **Algoritmo hash,** seleccione **sha1**.</span><span class="sxs-lookup"><span data-stu-id="0f959-168">For **Hash Algorithm** select **sha1**.</span></span>

    - <span data-ttu-id="0f959-169">Para **Nombre descriptivo,** escribaSmardcard Certificate.</span><span class="sxs-lookup"><span data-stu-id="0f959-169">For **Friendly Name** enterSmardcard Certificate.</span></span>

8. <span data-ttu-id="0f959-170">Si usas un lector de tarjeta inteligente física, inserta la tarjeta inteligente en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="0f959-170">If you are using a physical smartcard reader, insert the smart card into the device.</span></span>

9. <span data-ttu-id="0f959-171">Haga **clic en Enviar** para enviar la solicitud de certificado.</span><span class="sxs-lookup"><span data-stu-id="0f959-171">Click **Submit** to submit the certificate request.</span></span>

10. <span data-ttu-id="0f959-172">Cuando se le pida, escriba el PIN que se usó para crear la tarjeta inteligente virtual.</span><span class="sxs-lookup"><span data-stu-id="0f959-172">When prompted, enter the PIN that was used to create the virtual smart card.</span></span>

    > [!NOTE]
    > <span data-ttu-id="0f959-173">El valor predeterminado del PIN de tarjeta inteligente virtual es "12345678".</span><span class="sxs-lookup"><span data-stu-id="0f959-173">The default virtual smart card PIN value is '12345678'.</span></span>

11. <span data-ttu-id="0f959-174">Una vez emitido el certificado, haga clic **en Instalar este certificado** para completar el proceso de inscripción.</span><span class="sxs-lookup"><span data-stu-id="0f959-174">Once the certificate has been issued, click **Install this certificate** to complete the enrollment process.</span></span>

    > [!NOTE]
    >  <span data-ttu-id="0f959-175">Si se produce un error en la solicitud de certificado con el error "Este explorador web no admite la generación de solicitudes de certificado", hay tres maneras posibles de resolver el problema:</span><span class="sxs-lookup"><span data-stu-id="0f959-175">If your certificate request fails with the error "This Web browser does not support the generation of certificate requests," there are three possible ways to resolve the issue:</span></span>

        a. Enable Compatibility View in Internet Explorer
        b. Enable the Turn on Intranet settings option in Internet Explorer
        c. Select the Reset all zones to default level setting under the Security tab in the Internet Explorer options menu.

## <a name="configure-active-directory-federation-services-ad-fs-20"></a><span data-ttu-id="0f959-176">Configurar servicios de federación de Active Directory (AD FS 2.0)</span><span class="sxs-lookup"><span data-stu-id="0f959-176">Configure Active Directory Federation Services (AD FS 2.0)</span></span>

<span data-ttu-id="0f959-177">En la siguiente sección se describe cómo configurar los Servicios de federación de Active Directory (AD FS 2.0) para admitir la autenticación multifactor.</span><span class="sxs-lookup"><span data-stu-id="0f959-177">The following section describes how to configure Active Directory Federation Services (AD FS 2.0) to support multi-factor authentication.</span></span> <span data-ttu-id="0f959-178">Para obtener información sobre cómo instalar AD FS 2.0, vea [AD FS 2.0 Step-by-Step y How To Guides](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/dd727938(v=ws.10)).</span><span class="sxs-lookup"><span data-stu-id="0f959-178">For information on how to install AD FS 2.0, see [AD FS 2.0 Step-by-Step and How To Guides](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/dd727938(v=ws.10)).</span></span>

> [!NOTE]
> <span data-ttu-id="0f959-179">Al instalar AD FS 2.0, no use el Administrador de Windows Server para agregar el rol Servicios de federación de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="0f959-179">When installing AD FS 2.0, do not use the Windows Server Manager to add the Active Directory Federation Services role.</span></span> <span data-ttu-id="0f959-180">En su lugar, descargue e instale el paquete de Servicios de federación [de Active Directory 2.0 RTW](https://go.microsoft.com/fwlink/p/?LinkId=313375).</span><span class="sxs-lookup"><span data-stu-id="0f959-180">Instead, download and install the [Active Directory Federation Services 2.0 RTW package](https://go.microsoft.com/fwlink/p/?LinkId=313375).</span></span>

### <a name="to-configure-ad-fs-for-two-factor-authentication"></a><span data-ttu-id="0f959-181">Para configurar AD FS para la autenticación en dos fases</span><span class="sxs-lookup"><span data-stu-id="0f959-181">To configure AD FS for two-factor Authentication</span></span>

1. <span data-ttu-id="0f959-182">Inicie sesión en el equipo de AD FS 2.0 con una cuenta de administrador de dominio.</span><span class="sxs-lookup"><span data-stu-id="0f959-182">Log in to the AD FS 2.0 computer using a Domain Admin account.</span></span>

2. <span data-ttu-id="0f959-183">Iniciar Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="0f959-183">Start Windows PowerShell.</span></span>

3. <span data-ttu-id="0f959-184">Desde la Windows PowerShell de comandos, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="0f959-184">From the Windows PowerShell command-line, run the following command:</span></span>

  ```PowerShell
  add-pssnapin Microsoft.Adfs.PowerShell
  ```

4. <span data-ttu-id="0f959-185">Establezca una asociación con cada servidor que se habilitará para la autenticación pasiva ejecutando el siguiente comando, reemplazando el nombre del servidor específico de la implementación:</span><span class="sxs-lookup"><span data-stu-id="0f959-185">Establish a partnership with each server that will be enabled for passive authentication by running the following command, replacing the server name specific to your deployment:</span></span>

  ```PowerShell
  Add-ADFSRelyingPartyTrust -Name SfBPool01-PassiveAuth -MetadataURL https://SfBpool01.contoso.com/passiveauth/federationmetadata/2007-06/federationmetadata.xml
  ```

5. <span data-ttu-id="0f959-186">En el menú Herramientas administrativas, inicie la consola de administración de AD FS 2.0.</span><span class="sxs-lookup"><span data-stu-id="0f959-186">From the Administrative Tools menu, launch the AD FS 2.0 Management console.</span></span>

6. <span data-ttu-id="0f959-187">Expande **Relaciones de confianza**  >  **Confianzas de usuario de confianza**.</span><span class="sxs-lookup"><span data-stu-id="0f959-187">Expand **Trust Relationships** > **Relying Party Trusts**.</span></span>

7. <span data-ttu-id="0f959-188">Compruebe que se ha creado una nueva confianza para su Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="0f959-188">Verify that a new trust has been created for your Skype for Business Server.</span></span>

8. <span data-ttu-id="0f959-189">Cree y asigne una regla de autorización de emisión para su confianza de usuario de confianza Windows PowerShell mediante la ejecución de los siguientes comandos:</span><span class="sxs-lookup"><span data-stu-id="0f959-189">Create and assign an Issuance Authorization Rule for your relying party trust using Windows PowerShell by running the following commands:</span></span>

  ```PowerShell
  $IssuanceAuthorizationRules = '@RuleTemplate = "AllowAllAuthzRule" => issue(Type = "https://schemas.microsoft.com/authorization/claims/permit", Value = "true");'
  ```

  ```PowerShell
  Set-ADFSRelyingPartyTrust -TargetName SfBPool01-PassiveAuth
-IssuanceAuthorizationRules $IssuanceAuthorizationRules
  ```

9. <span data-ttu-id="0f959-190">Cree y asigne una regla de transformación de emisión para su confianza de usuario de confianza mediante Windows PowerShell mediante la ejecución de los siguientes comandos:</span><span class="sxs-lookup"><span data-stu-id="0f959-190">Create and assign an Issuance Transform Rule for your relying party trust using Windows PowerShell by running the following commands:</span></span>

  ```PowerShell
  $IssuanceTransformRules = '@RuleTemplate = "PassThroughClaims" @RuleName = "Sid" c:[Type == "https://schemas.microsoft.com/ws/2008/06/identity/claims/primarysid"]=> issue(claim = c);'
  ```

  ```PowerShell
  Set-ADFSRelyingPartyTrust -TargetName SfBPool01-PassiveAuth -IssuanceTransformRules $IssuanceTransformRules
  ```

10. <span data-ttu-id="0f959-191">En la consola de administración de AD FS 2.0, haga clic con el botón secundario en su confianza de usuario de confianza y seleccione **Editar reglas de notificación.**</span><span class="sxs-lookup"><span data-stu-id="0f959-191">From the AD FS 2.0 Management console, right click on your relying party trust and select **Edit Claim Rules**.</span></span>

11. <span data-ttu-id="0f959-192">Seleccione la **pestaña Reglas de autorización de** emisión y compruebe que la nueva regla de autorización se creó correctamente.</span><span class="sxs-lookup"><span data-stu-id="0f959-192">Select the **Issuance Authorization Rules** tab and verify that the new authorization rule was created successfully.</span></span>

12. <span data-ttu-id="0f959-193">Seleccione la **pestaña Reglas de transformación de** emisión y compruebe que la nueva regla de transformación se creó correctamente.</span><span class="sxs-lookup"><span data-stu-id="0f959-193">Select the **Issuance Transform Rules** tab and verify that the new transform rule was created successfully.</span></span>

## <a name="configuring-ad-fs-20-to-support-client-authentication"></a><span data-ttu-id="0f959-194">Configuración de AD FS 2.0 para admitir la autenticación de cliente</span><span class="sxs-lookup"><span data-stu-id="0f959-194">Configuring AD FS 2.0 to support client authentication</span></span>

<span data-ttu-id="0f959-195">Hay dos tipos de autenticación posibles que se pueden configurar para permitir que AD FS 2.0 admita la autenticación con tarjetas inteligentes:</span><span class="sxs-lookup"><span data-stu-id="0f959-195">There are two possible authentication types that can be configured to allow AD FS 2.0 to support authentication using smart cards:</span></span>

- <span data-ttu-id="0f959-196">Autenticación basada en formularios (FBA)</span><span class="sxs-lookup"><span data-stu-id="0f959-196">Forms-based authentication (FBA)</span></span>

- <span data-ttu-id="0f959-197">Autenticación de cliente de seguridad de la capa de transporte</span><span class="sxs-lookup"><span data-stu-id="0f959-197">Transport Layer Security Client Authentication</span></span>

<span data-ttu-id="0f959-198">Con la autenticación basada en formularios, puede desarrollar una página web que permita a los usuarios autenticarse con su nombre de usuario o contraseña o con su tarjeta inteligente y PIN.</span><span class="sxs-lookup"><span data-stu-id="0f959-198">Using forms-based authentication, you can develop a web page that allows users to authenticate either by using their username/password or by using their smart card and PIN.</span></span> <span data-ttu-id="0f959-199">Este tema se centra en cómo implementar la autenticación de cliente de seguridad de la capa de transporte con AD FS 2.0.</span><span class="sxs-lookup"><span data-stu-id="0f959-199">This topic focuses on how to implement Transport Layer Security Client Authentication with AD FS 2.0.</span></span> <span data-ttu-id="0f959-200">Para obtener más información acerca de los tipos de autenticación de AD FS 2.0, vea [AD FS 2.0: How to Change the Local Authentication Type](https://go.microsoft.com/fwlink/p/?LinkId=313384).</span><span class="sxs-lookup"><span data-stu-id="0f959-200">For more information about AD FS 2.0 authentication types, see [AD FS 2.0: How to Change the Local Authentication Type](https://go.microsoft.com/fwlink/p/?LinkId=313384).</span></span>

### <a name="to-configure-ad-fs-20-to-support-client-authentication"></a><span data-ttu-id="0f959-201">Para configurar AD FS 2.0 para admitir la autenticación de cliente</span><span class="sxs-lookup"><span data-stu-id="0f959-201">To Configure AD FS 2.0 to Support Client Authentication</span></span>

1. <span data-ttu-id="0f959-202">Inicie sesión en el equipo de AD FS 2.0 con una cuenta de administrador de dominio.</span><span class="sxs-lookup"><span data-stu-id="0f959-202">Log in to the AD FS 2.0 computer using a Domain Admin account.</span></span>

2. <span data-ttu-id="0f959-203">Inicie Windows Explorer.</span><span class="sxs-lookup"><span data-stu-id="0f959-203">Launch Windows Explorer.</span></span>

3. <span data-ttu-id="0f959-204">Vaya a C:\inetpub\adfs\ls</span><span class="sxs-lookup"><span data-stu-id="0f959-204">Browse to C:\inetpub\adfs\ls</span></span>

4. <span data-ttu-id="0f959-205">Realice una copia de seguridad del archivo web.config existente.</span><span class="sxs-lookup"><span data-stu-id="0f959-205">Make a backup copy of the existing web.config file.</span></span>

5. <span data-ttu-id="0f959-206">Abra el archivo web.config con el Bloc de notas.</span><span class="sxs-lookup"><span data-stu-id="0f959-206">Open the existing web.config file using Notepad.</span></span>

6. <span data-ttu-id="0f959-207">En la barra de menús, **seleccione Editar** y, a continuación, **seleccione Buscar**.</span><span class="sxs-lookup"><span data-stu-id="0f959-207">From the Menu bar, select **Edit** and then select **Find**.</span></span>

7. <span data-ttu-id="0f959-208">Buscar \<localAuthenticationTypes\> .</span><span class="sxs-lookup"><span data-stu-id="0f959-208">Search for \<localAuthenticationTypes\>.</span></span>

    <span data-ttu-id="0f959-209">Tenga en cuenta que hay cuatro tipos de autenticación enumerados, uno por línea.</span><span class="sxs-lookup"><span data-stu-id="0f959-209">Note that there are four authentication types listed, one per line.</span></span>

8. <span data-ttu-id="0f959-210">Mueva la línea que contiene el tipo de autenticación TLSClient a la parte superior de la lista de la sección.</span><span class="sxs-lookup"><span data-stu-id="0f959-210">Move the line containing the TLSClient authentication type to the top of the list in the section.</span></span>

9. <span data-ttu-id="0f959-211">Guarde y cierre el web.config archivo.</span><span class="sxs-lookup"><span data-stu-id="0f959-211">Save and Close the web.config file.</span></span>

10. <span data-ttu-id="0f959-212">Inicie un símbolo del sistema con privilegios elevados.</span><span class="sxs-lookup"><span data-stu-id="0f959-212">Launch a Command Prompt with elevated privileges.</span></span>

11. <span data-ttu-id="0f959-213">Reinicie IIS ejecutando el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="0f959-213">Restart IIS by running the following command:</span></span>

  ```console
  IISReset /Restart /NoForce
  ```

## <a name="configuring-skype-for-business-server-passive-authentication"></a><span data-ttu-id="0f959-214">Configuración de la autenticación pasiva de Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="0f959-214">Configuring Skype for Business Server passive authentication</span></span>

<span data-ttu-id="0f959-215">En la siguiente sección se describe cómo configurar Skype Empresarial Server para admitir la autenticación pasiva.</span><span class="sxs-lookup"><span data-stu-id="0f959-215">The following section describes how to configure Skype for Business Server to support passive authentication.</span></span> <span data-ttu-id="0f959-216">Una vez habilitado, los usuarios habilitados para la autenticación en dos fases tendrán que usar una tarjeta inteligente física o virtual y un PIN válido para iniciar sesión con el cliente de Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="0f959-216">Once enabled, users who are enabled for two-factor authentication will be required to use a physical or virtual smart card and a valid PIN to sign in using the Skype for Business client.</span></span>

> [!NOTE]
> <span data-ttu-id="0f959-217">Se recomienda encarecidamente que los clientes habiliten la autenticación pasiva para registrar y los servicios web en el nivel de servicio.</span><span class="sxs-lookup"><span data-stu-id="0f959-217">It is strongly recommended that customers enable passive authentication for Registrar and Web Services at the service level.</span></span> <span data-ttu-id="0f959-218">Si la autenticación pasiva está habilitada para registrador y servicios web en el nivel global, probablemente provocará errores de autenticación en toda la organización para los usuarios que no inicien sesión con el cliente de escritorio compatible.</span><span class="sxs-lookup"><span data-stu-id="0f959-218">If passive authentication is enabled for Registrar and Web Services at the global level, it will likely result in organization-wide authentication failures for users who are not signing in with the supported desktop client.</span></span>

### <a name="web-service-configuration"></a><span data-ttu-id="0f959-219">Configuración del servicio web</span><span class="sxs-lookup"><span data-stu-id="0f959-219">Web Service Configuration</span></span>

<span data-ttu-id="0f959-220">En los pasos siguientes se describe cómo crear una configuración de servicio web personalizada para directores, grupos de servidores de empresa y servidores Standard Edition que se habilitarán para la autenticación pasiva.</span><span class="sxs-lookup"><span data-stu-id="0f959-220">The following steps describe how to create a custom web service configuration for Directors, Enterprise Pools, and Standard Edition servers that will be enabled for passive authentication.</span></span>

### <a name="to-create-a-custom-web-service-configuration"></a><span data-ttu-id="0f959-221">Para crear una configuración de servicio web personalizada</span><span class="sxs-lookup"><span data-stu-id="0f959-221">To create a custom web service configuration</span></span>

1. <span data-ttu-id="0f959-222">Inicie sesión en el servidor front-end de Skype Empresarial Server con una cuenta de administrador de Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="0f959-222">Log in to your Skype for Business Server Front End server using a Skype for Business administrator account.</span></span>

2. <span data-ttu-id="0f959-223">Inicie el Shell de administración de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="0f959-223">Launch the Skype for Business Server Management Shell.</span></span>

3. <span data-ttu-id="0f959-224">Desde la línea de comandos del Shell de administración de Skype Empresarial Server, cree una nueva configuración de servicio web para cada servidor director, grupo de empresas y Standard Edition que se habilitará para la autenticación pasiva ejecutando el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="0f959-224">From the Skype for Business Server Management Shell command-line, create a new Web Service configuration for each Director, Enterprise Pool, and Standard Edition server that will be enabled for passive authentication by running the following command:</span></span>

  ```PowerShell
  New-CsWebServiceConfiguration -Identity "Service:WebServer:SfBPool01.contoso.com" -UseWsFedPassiveAuth $true -WsFedPassiveMetadataUri https://dc.contoso.com/federationmetadata/2007-06/federationmetadata.xml
  ```

    > [!CAUTION]
    > <span data-ttu-id="0f959-225">El valor del FQDN WsFedPassiveMetadataUri es el nombre del servicio de federación del servidor de AD FS 2.0.</span><span class="sxs-lookup"><span data-stu-id="0f959-225">The value for the WsFedPassiveMetadataUri FQDN is the Federation Service Name of your AD FS 2.0 server.</span></span> <span data-ttu-id="0f959-226">El valor nombre del servicio de federación se puede encontrar en la Consola de administración de AD FS 2.0 haciendo clic con el botón secundario en **Servicio** en el panel de navegación y, a continuación, seleccionando Editar propiedades del servicio **de federación**.</span><span class="sxs-lookup"><span data-stu-id="0f959-226">The Federation Service Name value can be found in the AD FS 2.0 Management Console by right-clicking on **Service** from the navigation pane and then selecting **Edit Federation Service Properties**.</span></span>

4. <span data-ttu-id="0f959-227">Compruebe que los valores UseWsFedPassiveAuth y WsFedPassiveMetadataUri se han establecido correctamente ejecutando el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="0f959-227">Verify that the UseWsFedPassiveAuth and WsFedPassiveMetadataUri values were set correctly by running the following command:</span></span>

  ```PowerShell
  Get-CsWebServiceConfiguration -identity "Service:WebServer:SfBPool01.contoso.com" | format-list UseWsFedPassiveAuth, WsFedPassiveMetadataUri
  ```

5. <span data-ttu-id="0f959-228">Para los clientes, la autenticación pasiva es el método de autenticación menos preferido para la autenticación de webticket.</span><span class="sxs-lookup"><span data-stu-id="0f959-228">For clients, Passive Authentication is the least preferred authentication method for webticket authentication.</span></span> <span data-ttu-id="0f959-229">Para todos los servidores directores, grupos de servidores de empresa y Standard Edition que se habilitarán para la autenticación pasiva, todos los demás tipos de autenticación deben deshabilitarse en Skype Empresarial Web Services ejecutando el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="0f959-229">For all Directors, Enterprise Pools, and Standard Edition servers that will be enabled for passive authentication, all other authentication types must be disabled in Skype for Business Web Services by running the following cmdlet:</span></span>

  ```PowerShell
  Set-CsWebServiceConfiguration -Identity "Service:WebServer:SfBPool01.contoso.com" -UseCertificateAuth $false -UsePinAuth $false -UseWindowsAuth NONE
  ```

6. <span data-ttu-id="0f959-230">Compruebe que todos los demás tipos de autenticación se han deshabilitado correctamente ejecutando el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="0f959-230">Verify that all other authentication types have been successfully disabled by running the following cmdlet:</span></span>

  ```PowerShell
  Get-CsWebServiceConfiguration -Identity "Service:WebServer:SfBPool01.contoso.com" | format-list UseCertificateAuth, UsePinAuth, UseWindowsAuth
  ```

### <a name="proxy-configuration"></a><span data-ttu-id="0f959-231">Configuración de proxy</span><span class="sxs-lookup"><span data-stu-id="0f959-231">Proxy Configuration</span></span>

<span data-ttu-id="0f959-232">Cuando la autenticación de certificados está deshabilitada para Skype Empresarial Web Services, el cliente de Skype Empresarial usará un tipo de autenticación menos preferido, como Kerberos o NTLM, para autenticarse en el servicio de registrador.</span><span class="sxs-lookup"><span data-stu-id="0f959-232">When certificate authentication is disabled for Skype for Business Web Services, the Skype for Business client will use a less preferred authentication type, such as Kerberos or NTLM, to authenticate to the Registrar service.</span></span> <span data-ttu-id="0f959-233">La autenticación de certificados sigue siendo necesaria para permitir que el cliente recupere un webticket, sin embargo, Kerberos y NTLM deben deshabilitarse para el servicio de registrador.</span><span class="sxs-lookup"><span data-stu-id="0f959-233">Certificate authentication is still needed to allow the client to retrieve a webticket, however, Kerberos and NTLM must be disabled for the Registrar service.</span></span>

<span data-ttu-id="0f959-234">En los pasos siguientes se describe cómo crear una configuración de proxy personalizada para grupos de servidores perimetrales, grupos de servidores empresariales y servidores Standard Edition que se habilitarán para la autenticación pasiva.</span><span class="sxs-lookup"><span data-stu-id="0f959-234">The following steps describe how to create a custom proxy configuration for Edge Pools, Enterprise Pools, and Standard Edition servers that will be enabled for passive authentication.</span></span>

### <a name="to-create-a-custom-proxy-configuration"></a><span data-ttu-id="0f959-235">Para crear una configuración de proxy personalizada</span><span class="sxs-lookup"><span data-stu-id="0f959-235">To create a custom proxy configuration</span></span>

1. <span data-ttu-id="0f959-236">Desde la línea de comandos del Shell de administración de Skype Empresarial Server, cree una nueva configuración de proxy para cada grupo perimetral de Skype Empresarial Server, grupo de servidores empresarial y servidor Standard Edition que se habilitará para la autenticación pasiva ejecutando los siguientes comandos:</span><span class="sxs-lookup"><span data-stu-id="0f959-236">From the Skype for Business Server Management Shell command-line, create a new proxy configuration for each Skype for Business Server Edge Pool, Enterprise Pool, and Standard Edition server that will be enabled for passive authentication by running the following commands:</span></span>

  ```PowerShell
  New-CsProxyConfiguration -Identity "Service:EdgeServer:EdgePool01.contoso.com" -UseKerberosForClientToProxyAuth $False -UseNtlmForClientToProxyAuth $False
  ```

  ```PowerShell
  New-CsProxyConfiguration -Identity "Service:Registrar:SfBPool01.contoso.com" -UseKerberosForClientToProxyAuth $False -UseNtlmForClientToProxyAuth $False
  ```

2. <span data-ttu-id="0f959-237">Compruebe que todos los demás tipos de autenticación de proxy se han deshabilitado correctamente ejecutando el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="0f959-237">Verify that all other proxy authentication types have been successfully disabled by running the following command:</span></span>

  ```PowerShell
  Get-CsProxyConfiguration -Identity "Service:Registrar:SfBPool01.contoso.com" | format-list UseKerberosForClientToProxyAuth, UseNtlmForClientToProxyAuth, UseCertifcateForClientToProxyAuth
  ```

## <a name="see-also"></a><span data-ttu-id="0f959-238">Ver también</span><span class="sxs-lookup"><span data-stu-id="0f959-238">See also</span></span>

[<span data-ttu-id="0f959-239">Administrar la autenticación en dos fases en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="0f959-239">Manage two-factor authentication in Skype for Business Server</span></span>](two-factor-authentication.md)

[<span data-ttu-id="0f959-240">Usar la autenticación en dos fases con el cliente de Skype Empresarial y Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="0f959-240">Use two-factor authentication with Skype for Business client and Skype for Business Server</span></span>](use-two-factor.md)