---
title: Implementación de teléfonos de Skype Empresarial Online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: wasseemh
ms.topic: article
ms.assetid: faa17eb3-7483-4984-87f2-815d981b68ae
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: Aprenda los pasos de implementación para obtener el firmware correcto, actualizarlo si es necesario, asignar licencias y establecer la configuración de los teléfonos de Skype empresarial online.
ms.openlocfilehash: 8d3de52f7c732571b3692ed2b3683673acdb8e60
ms.sourcegitcommit: b92b673e718e34b6ebda6de57ad69eb6651faa98
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/24/2019
ms.locfileid: "34432589"
---
# <a name="deploying-skype-for-business-online-phones"></a><span data-ttu-id="6f002-103">Implementación de teléfonos de Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="6f002-103">Deploying Skype for Business Online phones</span></span>

<span data-ttu-id="6f002-104">[] Esta guía de implementación le ayudará a implementar teléfonos IP para Skype Empresarial Online.</span><span class="sxs-lookup"><span data-stu-id="6f002-104">This is deployment guide will help you deploy Skype for Business Online IP phones.</span></span>
  
<span data-ttu-id="6f002-105">In all types of businesses, having a phone number allows users to make and get voice calls, and it is an important requirement to do business.</span><span class="sxs-lookup"><span data-stu-id="6f002-105">In all types of businesses, having a phone number allows users to make and get voice calls, and it is an important requirement to do business.</span></span> <span data-ttu-id="6f002-106">Users who have phone numbers will be able to make voice calls across all Skype for Business devices including IP phones, PCs, and mobile devices.</span><span class="sxs-lookup"><span data-stu-id="6f002-106">Users who have phone numbers will be able to make voice calls across all Skype for Business devices including IP phones, PCs, and mobile devices.</span></span> <span data-ttu-id="6f002-107">You can learn more about Skype for Business IP phones by reading [Getting phones for Skype for Business Online](getting-phones-for-skype-for-business-online.md).</span><span class="sxs-lookup"><span data-stu-id="6f002-107">You can learn more about Skype for Business IP phones by reading [Getting phones for Skype for Business Online](getting-phones-for-skype-for-business-online.md).</span></span>
  
## <a name="deployment-steps-for-ip-phones"></a><span data-ttu-id="6f002-108">Pasos para la implementación de teléfonos IP</span><span class="sxs-lookup"><span data-stu-id="6f002-108">Deployment steps for IP phones</span></span>

### <a name="step-1---download-the-manufacturers-administrator-guides-and-phone-manuals"></a><span data-ttu-id="6f002-109">Paso 1: descargar las guías para administradores y los manuales de los teléfonos del fabricante</span><span class="sxs-lookup"><span data-stu-id="6f002-109">Step 1 - Download the manufacturer's administrator guides and phone manuals</span></span>

<span data-ttu-id="6f002-110">Antes de comenzar, es recomendable descargar las guías para administradores y los manuales de usuario de los teléfonos que proporciona el fabricante.</span><span class="sxs-lookup"><span data-stu-id="6f002-110">Before you get started, it's a good idea to download the phone manufacturer's administration guides and phone user manuals.</span></span>
  
- <span data-ttu-id="6f002-111">Para los teléfonos Polycom, consulte la [Guía de implementación de Polycom](http://www.polycom.com/voice-conferencing-solutions/desktop-ip-phones.html).</span><span class="sxs-lookup"><span data-stu-id="6f002-111">For Polycom phones, see the [Polycom Deployment Guide](http://www.polycom.com/voice-conferencing-solutions/desktop-ip-phones.html).</span></span>
    
- <span data-ttu-id="6f002-112">Para teléfonos Yealink, consulte [Yealink solución de teléfonos SIP HD de Skype empresarial](http://www.yealink.com/products_top_2.html).</span><span class="sxs-lookup"><span data-stu-id="6f002-112">For Yealink phones, see [Yealink Skype for Business HD SIP Phones Solution](http://www.yealink.com/products_top_2.html).</span></span>
    
- <span data-ttu-id="6f002-113">Para teléfonos AudioCodes, consulte la [Guía de administración del aprovisionamiento de AudioCodes](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/ip-phones-room-solutions).</span><span class="sxs-lookup"><span data-stu-id="6f002-113">For AudioCodes phones, see the [Audiocodes Provisioning Management Guide](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/ip-phones-room-solutions).</span></span>
    
### <a name="step-2---make-sure-youre-purchasing-or-migrating-a-skype-for-business-supported-ip-phone-and-firmware"></a><span data-ttu-id="6f002-114">Paso 2: asegurarse de que los teléfonos que va a comprar o a los que va a realizar la migración son teléfonos IP compatibles con Skype Empresarial y tienen el firmware adecuado</span><span class="sxs-lookup"><span data-stu-id="6f002-114">Step 2 - Make sure you're purchasing or migrating a Skype for Business Supported IP phone and firmware</span></span>

<span data-ttu-id="6f002-115">A Skype for Business Online supported phone and firmware is compatible for Skype for Business Server as well, but the opposite isn't always true.</span><span class="sxs-lookup"><span data-stu-id="6f002-115">A Skype for Business Online supported phone and firmware is compatible for Skype for Business Server as well, but the opposite isn't always true.</span></span> <span data-ttu-id="6f002-116">To make sure you are buying or provisioning a supported phone and firmware, see [Getting phones for Skype for Business Online](getting-phones-for-skype-for-business-online.md).</span><span class="sxs-lookup"><span data-stu-id="6f002-116">To make sure you are buying or provisioning a supported phone and firmware, see [Getting phones for Skype for Business Online](getting-phones-for-skype-for-business-online.md).</span></span>
  
### <a name="step-3---checking-that-the-right-firmware-is-installed-and-update-the-firmware-if-required"></a><span data-ttu-id="6f002-117">Paso 3: comprobar que está instalado el firmware correcto y actualizarlo si es necesario</span><span class="sxs-lookup"><span data-stu-id="6f002-117">Step 3 - Checking that the right firmware is installed and update the firmware if required</span></span>

<span data-ttu-id="6f002-118">Check the firmware version on your phones.</span><span class="sxs-lookup"><span data-stu-id="6f002-118">Check the firmware version on your phones.</span></span> <span data-ttu-id="6f002-119">For:</span><span class="sxs-lookup"><span data-stu-id="6f002-119">For:</span></span>
  
- <span data-ttu-id="6f002-120">**Teléfonos Polycom VVX:** vaya a **Ajustes** > **Estado** > **Plataforma** > **Aplicación** > **Principal**.</span><span class="sxs-lookup"><span data-stu-id="6f002-120">**Polycom VVX phones**, go to **Settings** > **Status** > **Platform** > **Application** > **Main**.</span></span>
    
- <span data-ttu-id="6f002-121">**Teléfonos Yealink:** vaya a **Estado** en la pantalla principal del teléfono.</span><span class="sxs-lookup"><span data-stu-id="6f002-121">**Yealink phones**, go to **Status** on the main phone screen.</span></span>
    
- <span data-ttu-id="6f002-122">**Teléfonos AudioCodes:** desde la pantalla de inicio, vaya a **Menú** > **Estado del dispositivo** > **Versión de firmware**.</span><span class="sxs-lookup"><span data-stu-id="6f002-122">**AudioCodes phones**, go to **Menu** > **Device Status** > **Firmware version** from the start screen.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="6f002-123">For remote access to phone details, refer to manufacturer administration guides.</span><span class="sxs-lookup"><span data-stu-id="6f002-123">For remote access to phone details, refer to manufacturer administration guides.</span></span> <span data-ttu-id="6f002-124">See the links above for the user guides and phone manuals.</span><span class="sxs-lookup"><span data-stu-id="6f002-124">See the links above for the user guides and phone manuals.</span></span> 
  
- <span data-ttu-id="6f002-125">**Teléfonos Lync Phone Edition (LPE):** desde la pantalla de inicio, vaya a **Menú** > **Información del sistema**.</span><span class="sxs-lookup"><span data-stu-id="6f002-125">**Lync Phone Edition (LPE) phones**, go to **Menu** > **System Information** from the start screen.</span></span>
    
### <a name="step-4---device-update-considerations"></a><span data-ttu-id="6f002-126">Paso 4: consideraciones con respecto a la actualización de los dispositivos</span><span class="sxs-lookup"><span data-stu-id="6f002-126">Step 4 - Device Update Considerations</span></span>

> [!NOTE]
> <span data-ttu-id="6f002-127">Polycom firmware prior to 5.5.1.X had a manufacturer-specific device-lock mechanism that is replaced with a Skype for Business implementation "Phone-Lock."</span><span class="sxs-lookup"><span data-stu-id="6f002-127">Polycom firmware prior to 5.5.1.X had a manufacturer-specific device-lock mechanism that is replaced with a Skype for Business implementation "Phone-Lock."</span></span> <span data-ttu-id="6f002-128">Upgrading a phone from 5.4.X.X that was secured with "Device-Lock" to 5.5.1.X with "Phone-Lock" won't inherit the PIN code from "Device-Lock," which can leave the phone unsecured.</span><span class="sxs-lookup"><span data-stu-id="6f002-128">Upgrading a phone from 5.4.X.X that was secured with "Device-Lock" to 5.5.1.X with "Phone-Lock" won't inherit the PIN code from "Device-Lock," which can leave the phone unsecured.</span></span> <span data-ttu-id="6f002-129">Users who have activated "Device-Lock" need to enable the following Polycom Device Profile parameter to give users control of time of upgrade (lync.deviceUpdate.popUpSK.enabled=1).</span><span class="sxs-lookup"><span data-stu-id="6f002-129">Users who have activated "Device-Lock" need to enable the following Polycom Device Profile parameter to give users control of time of upgrade (lync.deviceUpdate.popUpSK.enabled=1).</span></span> 
  
<span data-ttu-id="6f002-130">Firmware updates are managed by the Skype for Business Service.</span><span class="sxs-lookup"><span data-stu-id="6f002-130">Firmware updates are managed by the Skype for Business Service.</span></span> <span data-ttu-id="6f002-131">Every Skype for Business certified phone's firmware is uploaded to the Skype for Business Update server, and device update is enabled on all phones by default.</span><span class="sxs-lookup"><span data-stu-id="6f002-131">Every Skype for Business certified phone's firmware is uploaded to the Skype for Business Update server, and device update is enabled on all phones by default.</span></span> <span data-ttu-id="6f002-132">Depending on the inactivity time on the phone and polling intervals, phones will automatically download and install the latest certified builds.</span><span class="sxs-lookup"><span data-stu-id="6f002-132">Depending on the inactivity time on the phone and polling intervals, phones will automatically download and install the latest certified builds.</span></span> <span data-ttu-id="6f002-133">You can disable the device update settings by using the [Set-CsIPPhonePolicy](https://technet.microsoft.com/en-us/library/mt629497.aspx) cmdlet and setting the _EnableDeviceUpdate_ parameter to `false`.</span><span class="sxs-lookup"><span data-stu-id="6f002-133">You can disable the device update settings by using the [Set-CsIPPhonePolicy](https://technet.microsoft.com/en-us/library/mt629497.aspx) cmdlet and setting the _EnableDeviceUpdate_ parameter to `false`.</span></span>
  
![Captura de pantalla que muestra la implementación de teléfonos](../../images/be727622-1924-439f-96ca-89230739db9e.png)
  
<span data-ttu-id="6f002-135">When a new firmware is available and ready for download and install, the phone will notify the user.</span><span class="sxs-lookup"><span data-stu-id="6f002-135">When a new firmware is available and ready for download and install, the phone will notify the user.</span></span> <span data-ttu-id="6f002-136">Polycom phones will notify the user and provide them with an option to **Update** or **Postpone**.</span><span class="sxs-lookup"><span data-stu-id="6f002-136">Polycom phones will notify the user and provide them with an option to **Update** or **Postpone**.</span></span>
  
![Captura de pantalla que muestra las opciones de actualización y posponer.](../../images/50956fa0-da0c-4085-9bb5-4a2e99aecebb.png)
  
<span data-ttu-id="6f002-138">En un teléfono Polycom, puede actualizar el firmware desde el teléfono seleccionando **ActualizaciónSw**.</span><span class="sxs-lookup"><span data-stu-id="6f002-138">For a Polycom phone, you can update the firmware on the phone by selecting **SwUpdate**.</span></span>
  
![Captura de pantalla que muestra la opción Actualizaciónsw](../../images/376c1998-6ce6-44b6-a84d-ae7d96b1c307.png)
  
<span data-ttu-id="6f002-p108">También puede optar por administrar las actualizaciones de firmware usando un sistema de aprovisionamiento de nuestros socios. Para obtener información sobre la administración de los sistemas de aprovisionamiento de nuestros socios y la personalización avanzada de teléfonos, consulte las guías de administración del fabricante.</span><span class="sxs-lookup"><span data-stu-id="6f002-p108">You can also choose to manage firmware updates using a partner provisioning system. For partner provisioning system management including advanced phone customization, refer to manufacturer administration guides.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="6f002-142">Asegúrese de que solo tiene una autoridad de actualización de dispositivos (actualización de dispositivos en banda o un servidor de aprovisionamiento de terceros) para evitar los bucles de actualizaciones.</span><span class="sxs-lookup"><span data-stu-id="6f002-142">Make sure to have a single device update authority (In-band device update or a third-party provisioning server) to avoid update loops.</span></span> 
  
### <a name="step-5---configuration-and-infrastructure-phone-settings"></a><span data-ttu-id="6f002-143">Paso 5: configuración del teléfono de configuración e infraestructura</span><span class="sxs-lookup"><span data-stu-id="6f002-143">Step 5 - Configuration and infrastructure phone settings</span></span>

<span data-ttu-id="6f002-p109">Puede configurar las opciones y políticas más utilizadas de los teléfonos usando los cmdlets de Windows PowerShell para la administración en banda de Skype Empresarial. Consulte [Set-CsIPPhonePolicy](https://technet.microsoft.com/en-us/library/mt629497.aspx) para obtener más información sobre estos parámetros y ajustes.</span><span class="sxs-lookup"><span data-stu-id="6f002-p109">You can set up the most commonly used phone options and policies using Skype for Business In-band management Windows PowerShell cmdlets. See [Set-CsIPPhonePolicy](https://technet.microsoft.com/en-us/library/mt629497.aspx) for details of those parameters and settings.</span></span>
  
<span data-ttu-id="6f002-146">Para planear la infraestructura de red, consulte [Skype Operations Framework](https://www.skypeoperationsframework.com/).</span><span class="sxs-lookup"><span data-stu-id="6f002-146">For network infrastructure planning, see [Skype Operations Framework](https://www.skypeoperationsframework.com/).</span></span>
  
### <a name="step-6---preparing-for-users-to-sign-in"></a><span data-ttu-id="6f002-147">Paso 6: prepararse para que los usuarios inicien sesión</span><span class="sxs-lookup"><span data-stu-id="6f002-147">Step 6 - Preparing for users to sign in</span></span>

<span data-ttu-id="6f002-148">To enable users to successfully sign in to a Skype for Business Online phone and make calls, you need to make sure users are assigned the correct licenses.</span><span class="sxs-lookup"><span data-stu-id="6f002-148">To enable users to successfully sign in to a Skype for Business Online phone and make calls, you need to make sure users are assigned the correct licenses.</span></span> <span data-ttu-id="6f002-149">At a minimum, you will need to assign a Phone System license and a Calling Plan.</span><span class="sxs-lookup"><span data-stu-id="6f002-149">At a minimum, you will need to assign a Phone System license and a Calling Plan.</span></span> <span data-ttu-id="6f002-150">For additional information, you can see [Skype for Business and Microsoft Teams add-on licensing](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md) and [Assign Skype for Business and Microsoft Teams licenses](../../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span><span class="sxs-lookup"><span data-stu-id="6f002-150">For additional information, you can see [Skype for Business and Microsoft Teams add-on licensing](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md) and [Assign Skype for Business and Microsoft Teams licenses](../../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span></span>
  
<span data-ttu-id="6f002-151">Para obtener más información sobre cómo llamar a planes, lea el [sistema telefónico y los planes de llamadas](/microsoftteams/calling-plan-landing-page)</span><span class="sxs-lookup"><span data-stu-id="6f002-151">You can find out more about Calling Plans by reading [Phone System and Calling Plans](/microsoftteams/calling-plan-landing-page)</span></span>
  
- <span data-ttu-id="6f002-152">**Sign-in options** that are available for Online users are:</span><span class="sxs-lookup"><span data-stu-id="6f002-152">**Sign-in options** that are available for Online users are:</span></span>
    
  - <span data-ttu-id="6f002-153">Los usuarios con teléfonos **Polycom VVX 5xx/6xx** verán:</span><span class="sxs-lookup"><span data-stu-id="6f002-153">Users with **Polycom VVX 5XX/6XX** phones will see:</span></span>
    
     ![Captura de pantalla que muestra el inicio de sesión de los teléfonos Polycom](../../images/8a1ffb33-8a63-4242-bb76-d5fafb6a6472.png)
  
  - <span data-ttu-id="6f002-155">Los usuarios con teléfonos **YEALINK T48G/t46g verán** verán:</span><span class="sxs-lookup"><span data-stu-id="6f002-155">Users with **Yealink T48G/T46G** phones will see:</span></span>
    
     ![Captura de pantalla que muestra el inicio de sesión de los teléfonos Yealink.](../../images/2a2892ae-850d-4781-8be0-4ffb8af068c9.png)
  
    <span data-ttu-id="6f002-157">Para más información sobre las opciones de inicio de sesión que admite el fabricante, vea [obtener teléfonos con Skype empresarial online](getting-phones-for-skype-for-business-online.md).</span><span class="sxs-lookup"><span data-stu-id="6f002-157">For details on sign-in options supported by the manufacturer, see [Getting phones for Skype for Business Online](getting-phones-for-skype-for-business-online.md).</span></span>
    
- <span data-ttu-id="6f002-p111">**Id. de usuario**: usando el teclado del teléfono o el teclado en pantalla (si está disponible), los usuarios pueden usar el nombre de usuario y la contraseña de su organización para iniciar sesión en el teléfono. Por ejemplo, deben usar el formato UPN, como <em>amosm@contoso.com</em>  , en el nombre de usuario.</span><span class="sxs-lookup"><span data-stu-id="6f002-p111">**User ID** Using the phone's keypad or on-screen keyboard (if available), users can use their organization's user name and password to sign in to the phone. For example, they should use the UPN format like <em>amosm@contoso.com</em>  for their user name.</span></span>
    
     ![Captura de pantalla que muestra la pantalla de inicio de sesión](../../images/f67fa8f4-66a5-451d-bdf2-a12daac15cb5.png)
  
    > [!NOTE]
    > <span data-ttu-id="6f002-161">La autenticación con PIN no se admite en Skype Empresarial Online con teléfonos LPE y teléfonos IP de socios.</span><span class="sxs-lookup"><span data-stu-id="6f002-161">PIN authentication isn't supported for Skype for Business Online for LPE and Partner IP phones.</span></span> 
  
- <span data-ttu-id="6f002-162">**Using a PC** When Better Together over Ethernet (BToE) software is installed on user's PC and enabled, users can log in to their phones using the authentication window on their Windows Skype for Business App.</span><span class="sxs-lookup"><span data-stu-id="6f002-162">**Using a PC** When Better Together over Ethernet (BToE) software is installed on user's PC and enabled, users can log in to their phones using the authentication window on their Windows Skype for Business App.</span></span> <span data-ttu-id="6f002-163">See [Step 7 (optional) - If you have device pairing and Better Together over Ethernet (BToE)](deploying-skype-for-business-online-phones.md#BK_BTOE) for other information.</span><span class="sxs-lookup"><span data-stu-id="6f002-163">See [Step 7 (optional) - If you have device pairing and Better Together over Ethernet (BToE)](deploying-skype-for-business-online-phones.md#BK_BTOE) for other information.</span></span>
    
  > [!NOTE]
  > <span data-ttu-id="6f002-p113">Los usuarios deben usar el nombre de usuario y la contraseña de su organización para iniciar sesión en el teléfono. Por ejemplo, deben usar el formato UPN, como  <em>amosm@contoso.com</em>  , en el nombre de usuario.</span><span class="sxs-lookup"><span data-stu-id="6f002-p113">Users are required to use their organization's user name and password to sign in to the phone. For example, they should use the UPN format like  <em>amosm@contoso.com</em>  for their user name.</span></span>
  
     ![Captura de pantalla que muestra la pantalla de inicio de sesión](../../images/f67fa8f4-66a5-451d-bdf2-a12daac15cb5.png)
  
- <span data-ttu-id="6f002-167">**Using a Web Sign-in**: This is a new way for Online users to authenticate using a standard web browser.</span><span class="sxs-lookup"><span data-stu-id="6f002-167">**Using a Web Sign-in**: This is a new way for Online users to authenticate using a standard web browser.</span></span> <span data-ttu-id="6f002-168">Users will be provided with a set of instructions to follow when they use a browser to sign in.</span><span class="sxs-lookup"><span data-stu-id="6f002-168">Users will be provided with a set of instructions to follow when they use a browser to sign in.</span></span>
    
  - <span data-ttu-id="6f002-169">Los usuarios con teléfonos **Polycom VVX 5xx/6xx** verán:</span><span class="sxs-lookup"><span data-stu-id="6f002-169">Users with **Polycom VVX 5XX/6XX** phones will see:</span></span>
    
     ![Captura de pantalla que muestra las instrucciones de Polycom](../../images/ba0df923-a6e5-4a9b-b40b-b03ca188e814.png)
  
  - <span data-ttu-id="6f002-171">Los usuarios con teléfonos **YEALINK T48G/t46g verán** verán:</span><span class="sxs-lookup"><span data-stu-id="6f002-171">Users with **Yealink T48G/T46G** phones will see:</span></span>
    
     ![Captura de pantalla que muestra instrucciones Yealink](../../images/86551cc3-533a-4694-9683-bad907c9ad5a.png)
  
    <span data-ttu-id="6f002-173">The code that is generated will expire in 15 minutes.</span><span class="sxs-lookup"><span data-stu-id="6f002-173">The code that is generated will expire in 15 minutes.</span></span> <span data-ttu-id="6f002-174">When it expires, the user will have to click **Retry** or **OK** to generate a new code, depending on the phone.</span><span class="sxs-lookup"><span data-stu-id="6f002-174">When it expires, the user will have to click **Retry** or **OK** to generate a new code, depending on the phone.</span></span>
    
  - <span data-ttu-id="6f002-175">Los usuarios con teléfonos **Polycom VVX 5xx/6xx** verán:</span><span class="sxs-lookup"><span data-stu-id="6f002-175">Users with **Polycom VVX 5XX/6XX** phones will see:</span></span>
    
     ![Captura de pantalla que muestra el código de Polycom vencido](../../images/b5d27037-aa26-4054-be95-d5a6c293d08c.png)
  
  - <span data-ttu-id="6f002-177">Los usuarios con teléfonos **YEALINK T48G/t46g verán** verán:</span><span class="sxs-lookup"><span data-stu-id="6f002-177">Users with **Yealink T48G/T46G** phones will see:</span></span>
    
     ![Captura de pantalla que muestra el código de Yealink caducado](../../images/3a4462ac-0c59-409e-a3bb-1451cdcc8676.png)
  
    <span data-ttu-id="6f002-179">Usando un explorador, vaya a la dirección que se muestra en el teléfono e introduzca su nombre de usuario de Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="6f002-179">Using a browser, navigate to the address displayed on the phone and enter your Skype for Business username.</span></span>
    
     ![Captura de pantalla que muestra la comprobación de correo electrónico](../../images/7c540b85-dc37-4ce7-a077-9e3454a0efd0.png)
  
    <span data-ttu-id="6f002-181">Introduzca el código que se muestra en el teléfono.</span><span class="sxs-lookup"><span data-stu-id="6f002-181">Enter the code shown on the phone.</span></span>
    
     ![Captura de pantalla que muestra cómo escribir el código en la pantalla de inicio de sesión](../../images/d6b88016-35d2-41d1-a0da-81fef34521d4.png)
  
    <span data-ttu-id="6f002-183">Compruebe que el sitio muestra " **teléfono certificado por Skype para empresas de**[nombre del fabricante del teléfono]" y haga clic en **continuar**.</span><span class="sxs-lookup"><span data-stu-id="6f002-183">Verify that the site shows "[Phone Manufacturer name] **Skype for Business Certified Phone**," and click **Continue**.</span></span>
    
     ![Captura de pantalla que muestra la verificación de nombre](../../images/a8252b37-4ff5-4ece-9e2a-3e05bf928299.png)
  
    <span data-ttu-id="6f002-185">Haga clic en las credenciales de usuario o en **Usar otra cuenta**:</span><span class="sxs-lookup"><span data-stu-id="6f002-185">Click the user's credentials or click **Use another account**:</span></span>
    
     ![Captura de pantalla que muestra las opciones de credenciales](../../images/8415028b-7924-4747-b639-052d9b0b961e.png)
  
    <span data-ttu-id="6f002-187">Cuando se muestre la página siguiente, es seguro cerrar el explorador.</span><span class="sxs-lookup"><span data-stu-id="6f002-187">When the following page is displayed, it is safe to close the browser.</span></span>
    
     ![Captura de pantalla que muestra el mensaje de confirmación](../../images/1a873201-52fc-4a63-b7b5-e82bbd031fd2.png)
  
    > [!NOTE]
    > <span data-ttu-id="6f002-189">Los teléfonos LPE para Skype Empresarial Online solo admiten el inicio de sesión mediante tethering USB.</span><span class="sxs-lookup"><span data-stu-id="6f002-189">LPE phones for Skype for Business Online support sign-in through USB tethering only.</span></span> 
  
- <span data-ttu-id="6f002-190">**Implementaciones admitidas**: la siguiente tabla muestra los tipos de autenticación compatibles con los modelos de implementación que se admiten actualmente, incluidos la integración de Exchange, la autenticación moderna con Multi-factor Authentication (MFA) y Skype Empresarial Online y local.</span><span class="sxs-lookup"><span data-stu-id="6f002-190">**Supported deployments** The table below shows the supported authentication types for the currently supported deployment models including Exchange Integration, Modern authentication with Multi-factor Authentication (MFA), and Skype for Business Online and on-premises.</span></span>
    
|||||||
|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="6f002-191">**Skype Empresarial**</span><span class="sxs-lookup"><span data-stu-id="6f002-191">**Skype for Business**</span></span> <br/> |<span data-ttu-id="6f002-192">**Exchange**</span><span class="sxs-lookup"><span data-stu-id="6f002-192">**Exchange**</span></span> <br/> |<span data-ttu-id="6f002-193">**Método de inicio de sesión en el teléfono**</span><span class="sxs-lookup"><span data-stu-id="6f002-193">**Phone Sign-In method**</span></span> <br/> |<span data-ttu-id="6f002-194">**Acceso a Skype empresarial**</span><span class="sxs-lookup"><span data-stu-id="6f002-194">**Skype for Business access**</span></span> <br/> |<span data-ttu-id="6f002-195">**Acceso a Exchange con autenticación moderna y MFA desactivados**</span><span class="sxs-lookup"><span data-stu-id="6f002-195">**Exchange Access with Modern Auth and MFA disabled**</span></span> <br/> |<span data-ttu-id="6f002-196">**Acceso a Exchange con autenticación moderna y MFA activados**</span><span class="sxs-lookup"><span data-stu-id="6f002-196">**Exchange Access with Modern Auth and MFA enabled**</span></span> <br/> |
|<span data-ttu-id="6f002-197">En línea</span><span class="sxs-lookup"><span data-stu-id="6f002-197">Online</span></span>  <br/> |<span data-ttu-id="6f002-198">En línea</span><span class="sxs-lookup"><span data-stu-id="6f002-198">Online</span></span>  <br/> |<span data-ttu-id="6f002-199">Inicio de sesión web</span><span class="sxs-lookup"><span data-stu-id="6f002-199">Web Sign-in</span></span>  <br/> |<span data-ttu-id="6f002-200">Sí</span><span class="sxs-lookup"><span data-stu-id="6f002-200">Yes</span></span>  <br/> |<span data-ttu-id="6f002-201">Sí</span><span class="sxs-lookup"><span data-stu-id="6f002-201">Yes</span></span>  <br/> |<span data-ttu-id="6f002-202">Sí</span><span class="sxs-lookup"><span data-stu-id="6f002-202">Yes</span></span>  <br/> |
|<span data-ttu-id="6f002-203">En línea</span><span class="sxs-lookup"><span data-stu-id="6f002-203">Online</span></span>  <br/> |<span data-ttu-id="6f002-204">En línea</span><span class="sxs-lookup"><span data-stu-id="6f002-204">Online</span></span>  <br/> |<span data-ttu-id="6f002-205">Nombre de usuario y contraseña</span><span class="sxs-lookup"><span data-stu-id="6f002-205">Username/Password</span></span>  <br/> |<span data-ttu-id="6f002-206">Sí</span><span class="sxs-lookup"><span data-stu-id="6f002-206">Yes</span></span>  <br/> |<span data-ttu-id="6f002-207">Sí</span><span class="sxs-lookup"><span data-stu-id="6f002-207">Yes</span></span>  <br/> |<span data-ttu-id="6f002-208">No</span><span class="sxs-lookup"><span data-stu-id="6f002-208">No</span></span>  <br/> |
|<span data-ttu-id="6f002-209">En línea</span><span class="sxs-lookup"><span data-stu-id="6f002-209">Online</span></span>  <br/> |<span data-ttu-id="6f002-210">Local</span><span class="sxs-lookup"><span data-stu-id="6f002-210">On-premises</span></span>  <br/> |<span data-ttu-id="6f002-211">Inicio de sesión web</span><span class="sxs-lookup"><span data-stu-id="6f002-211">Web Sign-in</span></span>  <br/> |<span data-ttu-id="6f002-212">Sí</span><span class="sxs-lookup"><span data-stu-id="6f002-212">Yes</span></span>  <br/> |<span data-ttu-id="6f002-213">No</span><span class="sxs-lookup"><span data-stu-id="6f002-213">No</span></span>  <br/> |<span data-ttu-id="6f002-214">No</span><span class="sxs-lookup"><span data-stu-id="6f002-214">No</span></span>  <br/> |
|<span data-ttu-id="6f002-215">En línea</span><span class="sxs-lookup"><span data-stu-id="6f002-215">Online</span></span>  <br/> |<span data-ttu-id="6f002-216">Local</span><span class="sxs-lookup"><span data-stu-id="6f002-216">On-Premises</span></span>  <br/> |<span data-ttu-id="6f002-217">Nombre de usuario y contraseña</span><span class="sxs-lookup"><span data-stu-id="6f002-217">Username/Password</span></span>  <br/> |<span data-ttu-id="6f002-218">Sí</span><span class="sxs-lookup"><span data-stu-id="6f002-218">Yes</span></span>  <br/> |<span data-ttu-id="6f002-219">Sí</span><span class="sxs-lookup"><span data-stu-id="6f002-219">Yes</span></span>  <br/> |<span data-ttu-id="6f002-220">No</span><span class="sxs-lookup"><span data-stu-id="6f002-220">No</span></span>  <br/> |
|<span data-ttu-id="6f002-221">Local</span><span class="sxs-lookup"><span data-stu-id="6f002-221">On-premises</span></span>  <br/> |<span data-ttu-id="6f002-222">En línea/local</span><span class="sxs-lookup"><span data-stu-id="6f002-222">Online/On-Premises</span></span>  <br/> |<span data-ttu-id="6f002-223">Autenticación de PIN</span><span class="sxs-lookup"><span data-stu-id="6f002-223">PIN Authentication</span></span>  <br/> |<span data-ttu-id="6f002-224">Sí</span><span class="sxs-lookup"><span data-stu-id="6f002-224">Yes</span></span>  <br/> |<span data-ttu-id="6f002-225">No</span><span class="sxs-lookup"><span data-stu-id="6f002-225">No</span></span>  <br/> |<span data-ttu-id="6f002-226">No</span><span class="sxs-lookup"><span data-stu-id="6f002-226">No</span></span>  <br/> |
|<span data-ttu-id="6f002-227">Local</span><span class="sxs-lookup"><span data-stu-id="6f002-227">On-premises</span></span>  <br/> |<span data-ttu-id="6f002-228">En línea/local</span><span class="sxs-lookup"><span data-stu-id="6f002-228">Online/On-Premises</span></span>  <br/> |<span data-ttu-id="6f002-229">Nombre de usuario y contraseña</span><span class="sxs-lookup"><span data-stu-id="6f002-229">Username/Password</span></span>  <br/> |<span data-ttu-id="6f002-230">Sí</span><span class="sxs-lookup"><span data-stu-id="6f002-230">Yes</span></span>  <br/> |<span data-ttu-id="6f002-231">Sí</span><span class="sxs-lookup"><span data-stu-id="6f002-231">Yes</span></span>  <br/> |<span data-ttu-id="6f002-232">N/D</span><span class="sxs-lookup"><span data-stu-id="6f002-232">N/A</span></span>  <br/> |
|<span data-ttu-id="6f002-233">Local</span><span class="sxs-lookup"><span data-stu-id="6f002-233">On-premises</span></span>  <br/> |<span data-ttu-id="6f002-234">En línea/local</span><span class="sxs-lookup"><span data-stu-id="6f002-234">Online/On-Premises</span></span>  <br/> |<span data-ttu-id="6f002-235">Inicio de sesión vía equipo (BTOE)</span><span class="sxs-lookup"><span data-stu-id="6f002-235">Sign-in via PC (BTOE)</span></span>  <br/> |<span data-ttu-id="6f002-236">Sí</span><span class="sxs-lookup"><span data-stu-id="6f002-236">Yes</span></span>  <br/> |<span data-ttu-id="6f002-237">Sí</span><span class="sxs-lookup"><span data-stu-id="6f002-237">Yes</span></span>  <br/> |<span data-ttu-id="6f002-238">N/D</span><span class="sxs-lookup"><span data-stu-id="6f002-238">N/A</span></span>  <br/> |
   
- <span data-ttu-id="6f002-239">**Phone features** The feature set may vary slightly based on the IP phone partner.</span><span class="sxs-lookup"><span data-stu-id="6f002-239">**Phone features** The feature set may vary slightly based on the IP phone partner.</span></span> <span data-ttu-id="6f002-240">For the complete feature set and for more information on the features for each phone manufacturer, see [Getting phones for Skype for Business Online](getting-phones-for-skype-for-business-online.md).</span><span class="sxs-lookup"><span data-stu-id="6f002-240">For the complete feature set and for more information on the features for each phone manufacturer, see [Getting phones for Skype for Business Online](getting-phones-for-skype-for-business-online.md).</span></span>
    
- <span data-ttu-id="6f002-241">**Phone-Lock** is a recently introduced feature in Skype for Business certified phones that is used to secure a phone.</span><span class="sxs-lookup"><span data-stu-id="6f002-241">**Phone-Lock** is a recently introduced feature in Skype for Business certified phones that is used to secure a phone.</span></span> <span data-ttu-id="6f002-242">If enabled, users will be asked to create a PIN upon successful authentication.</span><span class="sxs-lookup"><span data-stu-id="6f002-242">If enabled, users will be asked to create a PIN upon successful authentication.</span></span> <span data-ttu-id="6f002-243">Once created, phones will lock when the idle-timeout that you define expires, a user manually locks their phone, or they sync their phone-lock with their PC lock using Phone Pairing.</span><span class="sxs-lookup"><span data-stu-id="6f002-243">Once created, phones will lock when the idle-timeout that you define expires, a user manually locks their phone, or they sync their phone-lock with their PC lock using Phone Pairing.</span></span> <span data-ttu-id="6f002-244">If the phone-lock PIN is entered wrong several times, the phone will either sign the user out or require an administrator's code to unlock the phone, but this will vary depending on the phone partner.</span><span class="sxs-lookup"><span data-stu-id="6f002-244">If the phone-lock PIN is entered wrong several times, the phone will either sign the user out or require an administrator's code to unlock the phone, but this will vary depending on the phone partner.</span></span> <span data-ttu-id="6f002-245">The user's PIN should be between 6 and 15 digits.</span><span class="sxs-lookup"><span data-stu-id="6f002-245">The user's PIN should be between 6 and 15 digits.</span></span>
    
    <span data-ttu-id="6f002-246">You can disable Phone-Lock for your organization (which is enabled by default), change the idle-timeout, and choose whether users can make phone calls while they are locked or not using inband-settings.</span><span class="sxs-lookup"><span data-stu-id="6f002-246">You can disable Phone-Lock for your organization (which is enabled by default), change the idle-timeout, and choose whether users can make phone calls while they are locked or not using inband-settings.</span></span> <span data-ttu-id="6f002-247">Para obtener más información sobre esta configuración [, consulta Set-CsUCPhoneConfiguration](https://technet.microsoft.com/en-us/library/mt629497.aspx) .</span><span class="sxs-lookup"><span data-stu-id="6f002-247">See [Set-CsUCPhoneConfiguration](https://technet.microsoft.com/en-us/library/mt629497.aspx) for more details on those settings.</span></span>
    
## <a name="step-7-optional---if-you-have-device-pairing-and-better-together-over-ethernet-btoe"></a><span data-ttu-id="6f002-248">Paso 7 (opcional): si se dispone de emparejamiento de dispositivos y Better Together over Ethernet (BToE)</span><span class="sxs-lookup"><span data-stu-id="6f002-248">Step 7 (optional) - If you have device pairing and Better Together over Ethernet (BToE)</span></span>
<span data-ttu-id="6f002-249"><a name="BK_BTOE"> </a></span><span class="sxs-lookup"><span data-stu-id="6f002-249"><a name="BK_BTOE"> </a></span></span>

<span data-ttu-id="6f002-250">BToE is a phone paining mechanism for Partner IP phones that pairs a user's phone with their Windows Skype for Business app.</span><span class="sxs-lookup"><span data-stu-id="6f002-250">BToE is a phone paining mechanism for Partner IP phones that pairs a user's phone with their Windows Skype for Business app.</span></span> <span data-ttu-id="6f002-251">BToE enables users to:</span><span class="sxs-lookup"><span data-stu-id="6f002-251">BToE enables users to:</span></span>
  
- <span data-ttu-id="6f002-252">Iniciar sesión en su teléfono IP usando su aplicación de escritorio de Skype empresarial (con un equipo de PC)</span><span class="sxs-lookup"><span data-stu-id="6f002-252">Sign in to their IP phone using their Skype for Business desktop app (using a PC)</span></span>
    
- <span data-ttu-id="6f002-253">Sincronizar el bloqueo de teléfono con el bloqueo de PC</span><span class="sxs-lookup"><span data-stu-id="6f002-253">Synchronize Phone-Lock with PC lock</span></span>
    
- <span data-ttu-id="6f002-254">Haz clic para llamar</span><span class="sxs-lookup"><span data-stu-id="6f002-254">Click to call</span></span>
    
<span data-ttu-id="6f002-255">BToE can be configured to operate in two modes:  *Auto*  (default) and *Manual*  .</span><span class="sxs-lookup"><span data-stu-id="6f002-255">BToE can be configured to operate in two modes:  *Auto*  (default) and *Manual*  .</span></span> <span data-ttu-id="6f002-256">It can also be enabled (default)/disabled for users using Skype for Business in-band settings.</span><span class="sxs-lookup"><span data-stu-id="6f002-256">It can also be enabled (default)/disabled for users using Skype for Business in-band settings.</span></span> <span data-ttu-id="6f002-257">When operating in *Manual*  mode, users will have to take an additional step to pair their phone with their Windows app.</span><span class="sxs-lookup"><span data-stu-id="6f002-257">When operating in *Manual*  mode, users will have to take an additional step to pair their phone with their Windows app.</span></span>
  
 <span data-ttu-id="6f002-258">**Para implementar BToE a los usuarios**</span><span class="sxs-lookup"><span data-stu-id="6f002-258">**To deploy BToE to users**</span></span>
  
1. <span data-ttu-id="6f002-259">Conecte los equipos con los teléfonos usando el puerto de los equipos.</span><span class="sxs-lookup"><span data-stu-id="6f002-259">Connect their PC to their phone using the PC port.</span></span>
    
     ![Captura de pantalla que muestra la conexión a un PC](../../images/e21d76c7-867c-4fe6-95c6-fc40c608ed0c.png)
  
2. <span data-ttu-id="6f002-p121">Descargue el software BToE más reciente desde el sitio web del fabricante utilizando los vínculos que se ofrecen a continuación e instálelo. Para obtener una mejor experiencia de usuario, puede distribuir e instalar el software BToE usando una solución de distribución para administradores, como System Center Configuration Manager (SCCM). Para obtener ayuda sobre el uso de SCCM, consulte [Paquetes y programas en System Center Configuration Manager](https://docs.microsoft.com/sccm/apps/deploy-use/packages-and-programs).</span><span class="sxs-lookup"><span data-stu-id="6f002-p121">Download and install the latest BToE software from the manufacturer website from the links below. For a better user experience, you can distribute and install the BToE software using an admin distribution solution such as System Center Configuration Manager (SCCM). For help using SCCM, See [Packages and programs in System Center Configuration Manager](https://docs.microsoft.com/sccm/apps/deploy-use/packages-and-programs).</span></span>
    
   - [<span data-ttu-id="6f002-264">Sitio de descarga del software BToE de Polycom</span><span class="sxs-lookup"><span data-stu-id="6f002-264">Polycom BToE Software Download site</span></span>](http://www.polycom.com/voice-conferencing-solutions/microsoft-phones.html)
    
   - [<span data-ttu-id="6f002-265">Descarga del software BToE de Yealink</span><span class="sxs-lookup"><span data-stu-id="6f002-265">Yealink BToE Software Download</span></span>](http://www.yealink.com/products_list_10.html)
    
   - [<span data-ttu-id="6f002-266">Descarga del software BToE de AudioCodes</span><span class="sxs-lookup"><span data-stu-id="6f002-266">AudioCodes BToE Software Downloads</span></span>](https://www.audiocodes.com/solutions-products/solutions/skype-for-business-microsoft-teams/skype-for-business-online)
    
3. <span data-ttu-id="6f002-p122">The server setting for BToE is set to **Enabled** and **Auto mode** by default. To change those settings, see [Set-CsIPPhonePolicy](https://technet.microsoft.com/en-us/library/mt629497.aspx).</span><span class="sxs-lookup"><span data-stu-id="6f002-p122">The server setting for BToE is set to **Enabled** and **Auto mode** by default. To change those settings, see [Set-CsIPPhonePolicy](https://technet.microsoft.com/en-us/library/mt629497.aspx).</span></span>
    
> [!NOTE]
> <span data-ttu-id="6f002-269">Actualmente BToE no es compatible con Mac ni plataformas VDI.</span><span class="sxs-lookup"><span data-stu-id="6f002-269">BToE isn't currently supported on Mac and VDI platforms.</span></span> 
  
## <a name="related-topics"></a><span data-ttu-id="6f002-270">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="6f002-270">Related topics</span></span>
[<span data-ttu-id="6f002-271">Obtener números de teléfono de servicio para Skype Empresarial y Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="6f002-271">Getting service phone numbers for Skype for Business and Microsoft Teams</span></span>](../../what-is-phone-system-in-office-365/getting-service-phone-numbers.md)

[<span data-ttu-id="6f002-272">Esto es lo obtiene con el Sistema telefónico de Office 365</span><span class="sxs-lookup"><span data-stu-id="6f002-272">Here's what you get with Phone System in Office 365</span></span>](/MicrosoftTeams/here-s-what-you-get-with-phone-system)

[<span data-ttu-id="6f002-273">Países y regiones donde Audioconferencia y Planes de llamada están disponibles</span><span class="sxs-lookup"><span data-stu-id="6f002-273">Country and region availability for Audio Conferencing and Calling Plans</span></span>](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)

  
 
