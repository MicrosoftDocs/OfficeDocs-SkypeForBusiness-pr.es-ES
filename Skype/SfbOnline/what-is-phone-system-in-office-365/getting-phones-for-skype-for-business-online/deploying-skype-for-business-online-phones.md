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
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Priority
f1keywords: None
ms.custom:
- Phone System
description: Obtenga información sobre los pasos de implementación para obtener el firmware correcto, actualizarlo si es necesario, asignar licencias y configurar las opciones de Skype para teléfonos en línea de negocio
ms.openlocfilehash: 9a19367066fac2b74b51659fb6159ba33b68450e
ms.sourcegitcommit: 6207b98e8395f6c640b61cfb3f6c85d96520e33b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/20/2018
ms.locfileid: "22490804"
---
# <a name="deploying-skype-for-business-online-phones"></a><span data-ttu-id="8e06e-103">Implementación de teléfonos de Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="8e06e-103">Deploying Skype for Business Online phones</span></span>

<span data-ttu-id="8e06e-104">[] Esta guía de implementación le ayudará a implementar teléfonos IP para Skype Empresarial Online.</span><span class="sxs-lookup"><span data-stu-id="8e06e-104">This is deployment guide will help you deploy Skype for Business Online IP phones.</span></span>
  
<span data-ttu-id="8e06e-105">En todos los tipos de empresas, tener un número de teléfono permite a los usuarios realizar y recibir llamadas de voz y es un requisito importante para hacer negocios.</span><span class="sxs-lookup"><span data-stu-id="8e06e-105">In all types of businesses, having a phone number allows users to make and get voice calls, and it is an important requirement to do business.</span></span> <span data-ttu-id="8e06e-106">Los usuarios que tienen los números de teléfono podrán realizar llamadas de voz entre todos los Skype para dispositivos de negocio incluidos los teléfonos IP, equipos y dispositivos móviles.</span><span class="sxs-lookup"><span data-stu-id="8e06e-106">Users who have phone numbers will be able to make voice calls across all Skype for Business devices including IP phones, PCs, and mobile devices.</span></span> <span data-ttu-id="8e06e-107">Puede obtener más acerca de Skype para teléfonos IP de negocio mediante la lectura de [teléfonos de introducción de Skype para profesionales en línea](getting-phones-for-skype-for-business-online.md).</span><span class="sxs-lookup"><span data-stu-id="8e06e-107">You can learn more about Skype for Business IP phones by reading [Getting phones for Skype for Business Online](getting-phones-for-skype-for-business-online.md).</span></span>
  
## <a name="deployment-steps-for-ip-phones"></a><span data-ttu-id="8e06e-108">Pasos para la implementación de teléfonos IP</span><span class="sxs-lookup"><span data-stu-id="8e06e-108">Deployment steps for IP phones</span></span>

### <a name="step-1---download-the-manufacturers-administrator-guides-and-phone-manuals"></a><span data-ttu-id="8e06e-109">Paso 1: descargar las guías para administradores y los manuales de los teléfonos del fabricante</span><span class="sxs-lookup"><span data-stu-id="8e06e-109">Step 1 - Download the manufacturer's administrator guides and phone manuals</span></span>

<span data-ttu-id="8e06e-110">Antes de comenzar, es recomendable descargar las guías para administradores y los manuales de usuario de los teléfonos que proporciona el fabricante.</span><span class="sxs-lookup"><span data-stu-id="8e06e-110">Before you get started, it's a good idea to download the phone manufacturer's administration guides and phone user manuals.</span></span>
  
- <span data-ttu-id="8e06e-111">Para los teléfonos Polycom, vea la [Guía de implementación de Polycom] ((http://www.polycom.com/voice-conferencing-solutions/desktop-ip-phones.html).</span><span class="sxs-lookup"><span data-stu-id="8e06e-111">For Polycom phones, see the [Polycom Deployment Guide]((http://www.polycom.com/voice-conferencing-solutions/desktop-ip-phones.html).</span></span>
    
- <span data-ttu-id="8e06e-112">Para los teléfonos Yealink, vea [Skype Yealink for Business HD SIP teléfonos Solution](http://www.yealink.com/products_top_2.html).</span><span class="sxs-lookup"><span data-stu-id="8e06e-112">For Yealink phones, see [Yealink Skype for Business HD SIP Phones Solution](http://www.yealink.com/products_top_2.html).</span></span>
    
- <span data-ttu-id="8e06e-113">Para teléfonos AudioCodes, consulte la [Guía de administración del aprovisionamiento de AudioCodes](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/ip-phones-room-solutions).</span><span class="sxs-lookup"><span data-stu-id="8e06e-113">For AudioCodes phones, see the [Audiocodes Provisioning Management Guide](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/ip-phones-room-solutions).</span></span>
    
### <a name="step-2---make-sure-youre-purchasing-or-migrating-a-skype-for-business-supported-ip-phone-and-firmware"></a><span data-ttu-id="8e06e-114">Paso 2: asegurarse de que los teléfonos que va a comprar o a los que va a realizar la migración son teléfonos IP compatibles con Skype Empresarial y tienen el firmware adecuado</span><span class="sxs-lookup"><span data-stu-id="8e06e-114">Step 2 - Make sure you're purchasing or migrating a Skype for Business Supported IP phone and firmware</span></span>

<span data-ttu-id="8e06e-115">Los teléfonos y el firmware compatibles con Skype Empresarial Online también lo son con Skype Empresarial Server, pero no siempre sucede lo mismo a la inversa.</span><span class="sxs-lookup"><span data-stu-id="8e06e-115">A Skype for Business Online supported phone and firmware is compatible for Skype for Business Server as well, but the opposite isn't always true.</span></span> <span data-ttu-id="8e06e-116">Para asegurarse de que se compra o un teléfono admitido y el firmware de aprovisionamiento, vea [Introducción teléfonos de Skype para profesionales en línea](getting-phones-for-skype-for-business-online.md).</span><span class="sxs-lookup"><span data-stu-id="8e06e-116">To make sure you are buying or provisioning a supported phone and firmware, see [Getting phones for Skype for Business Online](getting-phones-for-skype-for-business-online.md).</span></span>
  
### <a name="step-3---checking-that-the-right-firmware-is-installed-and-update-the-firmware-if-required"></a><span data-ttu-id="8e06e-117">Paso 3: comprobar que está instalado el firmware correcto y actualizarlo si es necesario</span><span class="sxs-lookup"><span data-stu-id="8e06e-117">Step 3 - Checking that the right firmware is installed and update the firmware if required</span></span>

<span data-ttu-id="8e06e-118">Comprobar la versión de firmware en los teléfonos.</span><span class="sxs-lookup"><span data-stu-id="8e06e-118">Check the firmware version on your phones.</span></span> <span data-ttu-id="8e06e-119">Para:</span><span class="sxs-lookup"><span data-stu-id="8e06e-119">For:</span></span>
  
- <span data-ttu-id="8e06e-120">**Teléfonos Polycom VVX:** vaya a **Ajustes** > **Estado** > **Plataforma** > **Aplicación** > **Principal**.</span><span class="sxs-lookup"><span data-stu-id="8e06e-120">**Polycom VVX phones**, go to **Settings** > **Status** > **Platform** > **Application** > **Main**.</span></span>
    
- <span data-ttu-id="8e06e-121">**Teléfonos Yealink:** vaya a **Estado** en la pantalla principal del teléfono.</span><span class="sxs-lookup"><span data-stu-id="8e06e-121">**Yealink phones**, go to **Status** on the main phone screen.</span></span>
    
- <span data-ttu-id="8e06e-122">**Teléfonos AudioCodes:** desde la pantalla de inicio, vaya a **Menú** > **Estado del dispositivo** > **Versión de firmware**.</span><span class="sxs-lookup"><span data-stu-id="8e06e-122">**AudioCodes phones**, go to **Menu** > **Device Status** > **Firmware version** from the start screen.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="8e06e-p104">Para el acceso remoto a los detalles de teléfono, hacer referencia a las guías de administración del fabricante. Vea los vínculos por encima de las guías de usuario y manuales de teléfono.</span><span class="sxs-lookup"><span data-stu-id="8e06e-p104">For remote access to phone details, refer to manufacturer administration guides. See the links above for the user guides and phone manuals.</span></span> 
  
- <span data-ttu-id="8e06e-125">**Teléfonos Lync Phone Edition (LPE):** desde la pantalla de inicio, vaya a **Menú** > **Información del sistema**.</span><span class="sxs-lookup"><span data-stu-id="8e06e-125">**Lync Phone Edition (LPE) phones**, go to **Menu** > **System Information** from the start screen.</span></span>
    
### <a name="step-4---device-update-considerations"></a><span data-ttu-id="8e06e-126">Paso 4: consideraciones con respecto a la actualización de los dispositivos</span><span class="sxs-lookup"><span data-stu-id="8e06e-126">Step 4 - Device Update Considerations</span></span>

> [!NOTE]
> <span data-ttu-id="8e06e-127">Firmware Polycom antes de 5.5.1.X tenía un mecanismo de bloqueo de dispositivos específicos del fabricante que se ha reemplazado con un Skype para la implementación empresarial "-bloqueo del teléfono."</span><span class="sxs-lookup"><span data-stu-id="8e06e-127">Polycom firmware prior to 5.5.1.X had a manufacturer-specific device-lock mechanism that is replaced with a Skype for Business implementation "Phone-Lock."</span></span> <span data-ttu-id="8e06e-128">Actualización de un teléfono de 5.4.X.X que estaba protegida con "Bloqueo de dispositivo" a 5.5.1.X con "Bloqueo del teléfono" no hereda el código PIN de "Dispositivo de bloqueo," que puede dejar el teléfono no seguro.</span><span class="sxs-lookup"><span data-stu-id="8e06e-128">Upgrading a phone from 5.4.X.X that was secured with "Device-Lock" to 5.5.1.X with "Phone-Lock" won't inherit the PIN code from "Device-Lock," which can leave the phone unsecured.</span></span> <span data-ttu-id="8e06e-129">Los usuarios que se han activado "Bloqueo de dispositivo" necesitan habilitar el siguiente parámetro Polycom Device Profile ofrecer a los usuarios de control de tiempo de actualización (lync.deviceUpdate.popUpSK.enabled=1).</span><span class="sxs-lookup"><span data-stu-id="8e06e-129">Users who have activated "Device-Lock" need to enable the following Polycom Device Profile parameter to give users control of time of upgrade (lync.deviceUpdate.popUpSK.enabled=1).</span></span> 
  
<span data-ttu-id="8e06e-130">Las actualizaciones de firmware las administra el servicio de Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="8e06e-130">Firmware updates are managed by the Skype for Business Service.</span></span> <span data-ttu-id="8e06e-131">Todos los firmware de teléfono certificados para Skype for Business se cargan en el servidor de actualización de Skype for Business, y la actualización del dispositivo está habilitada en todos los teléfonos de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="8e06e-131">Every Skype for Business certified phone's firmware is uploaded to the Skype for Business Update server, and device update is enabled on all phones by default.</span></span> <span data-ttu-id="8e06e-132">En función del tiempo de inactividad del teléfono y de los intervalos de sondeo, los teléfonos descargarán e instalarán automáticamente las últimas compilaciones certificadas.</span><span class="sxs-lookup"><span data-stu-id="8e06e-132">Depending on the inactivity time on the phone and polling intervals, phones will automatically download and install the latest certified builds.</span></span> <span data-ttu-id="8e06e-133">Puede deshabilitar la configuración de actualización de dispositivo mediante el cmdlet [Set-CsIPPhonePolicy](https://technet.microsoft.com/en-us/library/mt629497.aspx) y establecer el parámetro _EnableDeviceUpdate_ en `false`.</span><span class="sxs-lookup"><span data-stu-id="8e06e-133">You can disable the device update settings by using the [Set-CsIPPhonePolicy](https://technet.microsoft.com/en-us/library/mt629497.aspx) cmdlet and setting the _EnableDeviceUpdate_ parameter to `false`.</span></span>
  
![Deploying phones.](../../images/be727622-1924-439f-96ca-89230739db9e.png)
  
<span data-ttu-id="8e06e-p107">Cuando un nuevo firmware está disponible y listo para descargar e instalar, el teléfono notificará al usuario. Los teléfonos Polycom va a notificar al usuario y proporcionar con una opción para **Actualizar** o **Posponer**.</span><span class="sxs-lookup"><span data-stu-id="8e06e-p107">When a new firmware is available and ready for download and install, the phone will notify the user. Polycom phones will notify the user and provide them with an option to **Update** or **Postpone**.</span></span>
  
![Deploying phones.](../../images/50956fa0-da0c-4085-9bb5-4a2e99aecebb.png)
  
<span data-ttu-id="8e06e-138">En un teléfono Polycom, puede actualizar el firmware desde el teléfono seleccionando **ActualizaciónSw**.</span><span class="sxs-lookup"><span data-stu-id="8e06e-138">For a Polycom phone, you can update the firmware on the phone by selecting **SwUpdate**.</span></span>
  
![Deploying phones.](../../images/376c1998-6ce6-44b6-a84d-ae7d96b1c307.png)
  
<span data-ttu-id="8e06e-p108">También puede optar por administrar las actualizaciones de firmware usando un sistema de aprovisionamiento de nuestros socios. Para obtener información sobre la administración de los sistemas de aprovisionamiento de nuestros socios y la personalización avanzada de teléfonos, consulte las guías de administración del fabricante.</span><span class="sxs-lookup"><span data-stu-id="8e06e-p108">You can also choose to manage firmware updates using a partner provisioning system. For partner provisioning system management including advanced phone customization, refer to manufacturer administration guides.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="8e06e-142">Asegúrese de que solo tiene una autoridad de actualización de dispositivos (actualización de dispositivos en banda o un servidor de aprovisionamiento de terceros) para evitar los bucles de actualizaciones.</span><span class="sxs-lookup"><span data-stu-id="8e06e-142">Make sure to have a single device update authority (In-band device update or a third-party provisioning server) to avoid update loops.</span></span> 
  
### <a name="step-5---configuration-and-infrastructure-phone-settings"></a><span data-ttu-id="8e06e-143">Paso 5: configuración y la configuración del teléfono de infraestructura</span><span class="sxs-lookup"><span data-stu-id="8e06e-143">Step 5 - Configuration and infrastructure phone settings</span></span>

<span data-ttu-id="8e06e-p109">Puede configurar las opciones y políticas más utilizadas de los teléfonos usando los cmdlets de Windows PowerShell para la administración en banda de Skype Empresarial. Consulte [Set-CsIPPhonePolicy](https://technet.microsoft.com/en-us/library/mt629497.aspx) para obtener más información sobre estos parámetros y ajustes.</span><span class="sxs-lookup"><span data-stu-id="8e06e-p109">You can set up the most commonly used phone options and policies using Skype for Business In-band management Windows PowerShell cmdlets. See [Set-CsIPPhonePolicy](https://technet.microsoft.com/en-us/library/mt629497.aspx) for details of those parameters and settings.</span></span>
  
<span data-ttu-id="8e06e-146">Para la planificación de la infraestructura de red, vea [Skype Operations Framework](https://www.skypeoperationsframework.com/).</span><span class="sxs-lookup"><span data-stu-id="8e06e-146">For network infrastructure planning, see [Skype Operations Framework](https://www.skypeoperationsframework.com/).</span></span>
  
### <a name="step-6---preparing-for-users-to-sign-in"></a><span data-ttu-id="8e06e-147">Paso 6: preparación para que los usuarios inicien sesión</span><span class="sxs-lookup"><span data-stu-id="8e06e-147">Step 6 - Preparing for users to sign in</span></span>

<span data-ttu-id="8e06e-148">Para habilitar a los usuarios iniciar sesión en un Skype para teléfono empresarial en línea correctamente y realizar llamadas, necesitará para asegurarse de que los usuarios se asignan las licencias correctas.</span><span class="sxs-lookup"><span data-stu-id="8e06e-148">To enable users to successfully sign in to a Skype for Business Online phone and make calls, you need to make sure users are assigned the correct licenses.</span></span> <span data-ttu-id="8e06e-149">Como mínimo, debe asignar una licencia de sistema telefónico y un Plan de llamada.</span><span class="sxs-lookup"><span data-stu-id="8e06e-149">At a minimum, you will need to assign a Phone System license and a Calling Plan.</span></span> <span data-ttu-id="8e06e-150">Para obtener información adicional, puede ver [Skype para profesionales y los equipos de Microsoft complemento licencias](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md) y [Asignar Skype para licencias de negocio y equipos de Microsoft](../../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span><span class="sxs-lookup"><span data-stu-id="8e06e-150">For additional information, you can see [Skype for Business and Microsoft Teams add-on licensing](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md) and [Assign Skype for Business and Microsoft Teams licenses](../../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span></span>
  
<span data-ttu-id="8e06e-151">Puede encontrar más información acerca de los planes de llamada mediante la lectura de [¿Cuáles son los planes de llamada en Office 365?](../../what-are-calling-plans-in-office-365/what-are-calling-plans-in-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="8e06e-151">You can find out more about Calling Plans by reading [What are Calling Plans in Office 365?](../../what-are-calling-plans-in-office-365/what-are-calling-plans-in-office-365.md)</span></span>
  
- <span data-ttu-id="8e06e-152">Las ** opciones de inicio de sesión** disponibles para los usuarios en línea son:</span><span class="sxs-lookup"><span data-stu-id="8e06e-152">**Sign-in options** that are available for Online users are:</span></span>
    
  - <span data-ttu-id="8e06e-153">Los usuarios con los teléfonos **Polycom VVX 5XX y 6XX** verán:</span><span class="sxs-lookup"><span data-stu-id="8e06e-153">Users with **Polycom VVX 5XX/6XX** phones will see:</span></span>
    
     ![Deploying phones.](../../images/8a1ffb33-8a63-4242-bb76-d5fafb6a6472.png)
  
  - <span data-ttu-id="8e06e-155">Los usuarios con los teléfonos **Yealink T48G/T46G** verán:</span><span class="sxs-lookup"><span data-stu-id="8e06e-155">Users with **Yealink T48G/T46G** phones will see:</span></span>
    
     ![Yealink phones logon.](../../images/2a2892ae-850d-4781-8be0-4ffb8af068c9.png)
  
    <span data-ttu-id="8e06e-157">Para obtener información detallada sobre las opciones de inicio de sesión admitidas por el fabricante, vea [Introducción teléfonos de Skype para profesionales en línea](getting-phones-for-skype-for-business-online.md).</span><span class="sxs-lookup"><span data-stu-id="8e06e-157">For details on sign-in options supported by the manufacturer, see [Getting phones for Skype for Business Online](getting-phones-for-skype-for-business-online.md).</span></span>
    
- <span data-ttu-id="8e06e-p111">**Id. de usuario**: usando el teclado del teléfono o el teclado en pantalla (si está disponible), los usuarios pueden usar el nombre de usuario y la contraseña de su organización para iniciar sesión en el teléfono. Por ejemplo, deben usar el formato UPN, como *amosm@contoso.com*  , en el nombre de usuario.</span><span class="sxs-lookup"><span data-stu-id="8e06e-p111">**User ID** Using the phone's keypad or on-screen keyboard (if available), users can use their organization's user name and password to sign in to the phone. For example, they should use the UPN format like *amosm@contoso.com*  for their user name.</span></span>
    
     ![Deploying phones.](../../images/f67fa8f4-66a5-451d-bdf2-a12daac15cb5.png)
  
    > [!NOTE]
    > <span data-ttu-id="8e06e-161">La autenticación con PIN no se admite en Skype Empresarial Online con teléfonos LPE y teléfonos IP de socios.</span><span class="sxs-lookup"><span data-stu-id="8e06e-161">PIN authentication isn't supported for Skype for Business Online for LPE and Partner IP phones.</span></span> 
  
- <span data-ttu-id="8e06e-162">**Uso de un PC** Cuando se Better Together a través de software de Ethernet (BToE) está instalado en el PC del usuario y habilitado, los usuarios pueden iniciar sesión a sus teléfonos mediante la ventana de autenticación en sus Skype de Windows para la aplicación empresarial de.</span><span class="sxs-lookup"><span data-stu-id="8e06e-162">**Using a PC** When Better Together over Ethernet (BToE) software is installed on user's PC and enabled, users can log in to their phones using the authentication window on their Windows Skype for Business App.</span></span> <span data-ttu-id="8e06e-163">Para obtener más información, vea [paso 7 (opcional) - si tiene el apareamiento de dispositivo y mejor juntos a través de Ethernet (BToE)](deploying-skype-for-business-online-phones.md#BK_BTOE) .</span><span class="sxs-lookup"><span data-stu-id="8e06e-163">See [Step 7 (optional) - If you have device pairing and Better Together over Ethernet (BToE)](deploying-skype-for-business-online-phones.md#BK_BTOE) for other information.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="8e06e-p113">Los usuarios deben usar el nombre de usuario y la contraseña de su organización para iniciar sesión en el teléfono. Por ejemplo, deben usar el formato UPN, como  *amosm@contoso.com*  , en el nombre de usuario.</span><span class="sxs-lookup"><span data-stu-id="8e06e-p113">Users are required to use their organization's user name and password to sign in to the phone. For example, they should use the UPN format like  *amosm@contoso.com*  for their user name.</span></span>
  
     ![Deploying phones.](../../images/f67fa8f4-66a5-451d-bdf2-a12daac15cb5.png)
  
- <span data-ttu-id="8e06e-167">**Uso de un inicio de sesión en Web**: Esto es una forma nueva para los usuarios en línea que se autentiquen mediante un explorador web estándar.</span><span class="sxs-lookup"><span data-stu-id="8e06e-167">**Using a Web Sign-in**: This is a new way for Online users to authenticate using a standard web browser.</span></span> <span data-ttu-id="8e06e-168">Se proporcionará a los usuarios con un conjunto de instrucciones que se deben seguir al usar un explorador para iniciar sesión.</span><span class="sxs-lookup"><span data-stu-id="8e06e-168">Users will be provided with a set of instructions to follow when they use a browser to sign in.</span></span>
    
  - <span data-ttu-id="8e06e-169">Los usuarios con los teléfonos **Polycom VVX 5XX y 6XX** verán:</span><span class="sxs-lookup"><span data-stu-id="8e06e-169">Users with **Polycom VVX 5XX/6XX** phones will see:</span></span>
    
     ![Deploying phones.](../../images/ba0df923-a6e5-4a9b-b40b-b03ca188e814.png)
  
  - <span data-ttu-id="8e06e-171">Los usuarios con los teléfonos **Yealink T48G/T46G** verán:</span><span class="sxs-lookup"><span data-stu-id="8e06e-171">Users with **Yealink T48G/T46G** phones will see:</span></span>
    
     ![Yealink phone logon.](../../images/86551cc3-533a-4694-9683-bad907c9ad5a.png)
  
    <span data-ttu-id="8e06e-p115">El código que se genera caducará en 15 minutos. Cuando expira, el usuario tendrá que hacer clic en **Reintentar** o en **Aceptar** para generar un nuevo código, en función del teléfono.</span><span class="sxs-lookup"><span data-stu-id="8e06e-p115">The code that is generated will expire in 15 minutes. When it expires, the user will have to click **Retry** or **OK** to generate a new code, depending on the phone.</span></span>
    
  - <span data-ttu-id="8e06e-175">Los usuarios con los teléfonos **Polycom VVX 5XX y 6XX** verán:</span><span class="sxs-lookup"><span data-stu-id="8e06e-175">Users with **Polycom VVX 5XX/6XX** phones will see:</span></span>
    
     ![PIN code expired.](../../images/b5d27037-aa26-4054-be95-d5a6c293d08c.png)
  
  - <span data-ttu-id="8e06e-177">Los usuarios con los teléfonos **Yealink T48G/T46G** verán:</span><span class="sxs-lookup"><span data-stu-id="8e06e-177">Users with **Yealink T48G/T46G** phones will see:</span></span>
    
     ![Yealink phones logon.](../../images/3a4462ac-0c59-409e-a3bb-1451cdcc8676.png)
  
    <span data-ttu-id="8e06e-179">Usando un explorador, vaya a la dirección que se muestra en el teléfono e introduzca su nombre de usuario de Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="8e06e-179">Using a browser, navigate to the address displayed on the phone and enter your Skype for Business username.</span></span>
    
     ![Deploying phones.](../../images/7c540b85-dc37-4ce7-a077-9e3454a0efd0.png)
  
    <span data-ttu-id="8e06e-181">Introduzca el código que se muestra en el teléfono.</span><span class="sxs-lookup"><span data-stu-id="8e06e-181">Enter the code shown on the phone.</span></span>
    
     ![Deploying phones.](../../images/d6b88016-35d2-41d1-a0da-81fef34521d4.png)
  
    <span data-ttu-id="8e06e-183">Compruebe que el sitio muestra "[nombre del fabricante del teléfono] **Skype para teléfono del trabajo certificada**," y haga clic en **continuar**.</span><span class="sxs-lookup"><span data-stu-id="8e06e-183">Verify that the site shows "[Phone Manufacturer name] **Skype for Business Certified Phone**," and click **Continue**.</span></span>
    
     ![Deploying phones.](../../images/a8252b37-4ff5-4ece-9e2a-3e05bf928299.png)
  
    <span data-ttu-id="8e06e-185">Haga clic en las credenciales de usuario o en **Usar otra cuenta**:</span><span class="sxs-lookup"><span data-stu-id="8e06e-185">Click the user's credentials or click **Use another account**:</span></span>
    
     ![Deploying phones.](../../images/8415028b-7924-4747-b639-052d9b0b961e.png)
  
    <span data-ttu-id="8e06e-187">Cuando se muestra la página siguiente, es segura cerrar el explorador.</span><span class="sxs-lookup"><span data-stu-id="8e06e-187">When the following page is displayed, it is safe to close the browser.</span></span>
    
     ![Deploying phones.](../../images/1a873201-52fc-4a63-b7b5-e82bbd031fd2.png)
  
    > [!NOTE]
    > <span data-ttu-id="8e06e-189">Los teléfonos LPE para Skype Empresarial Online solo admiten el inicio de sesión mediante tethering USB.</span><span class="sxs-lookup"><span data-stu-id="8e06e-189">LPE phones for Skype for Business Online support sign-in through USB tethering only.</span></span> 
  
- <span data-ttu-id="8e06e-190">**Implementaciones admitidas**: la siguiente tabla muestra los tipos de autenticación compatibles con los modelos de implementación que se admiten actualmente, incluidos la integración de Exchange, la autenticación moderna con Multi-factor Authentication (MFA) y Skype Empresarial Online y local.</span><span class="sxs-lookup"><span data-stu-id="8e06e-190">**Supported deployments** The table below shows the supported authentication types for the currently supported deployment models including Exchange Integration, Modern authentication with Multi-factor Authentication (MFA), and Skype for Business Online and on-premises.</span></span>
    
|||||||
|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="8e06e-191">**Skype Empresarial**</span><span class="sxs-lookup"><span data-stu-id="8e06e-191">**Skype for Business**</span></span> <br/> |<span data-ttu-id="8e06e-192">**Exchange**</span><span class="sxs-lookup"><span data-stu-id="8e06e-192">**Exchange**</span></span> <br/> |<span data-ttu-id="8e06e-193">**Método de inicio de sesión en el teléfono**</span><span class="sxs-lookup"><span data-stu-id="8e06e-193">**Phone Sign-In method**</span></span> <br/> |<span data-ttu-id="8e06e-194">**Skype para el acceso de negocio**</span><span class="sxs-lookup"><span data-stu-id="8e06e-194">**Skype for Business access**</span></span> <br/> |<span data-ttu-id="8e06e-195">**Acceso a Exchange con autenticación moderna y MFA desactivados**</span><span class="sxs-lookup"><span data-stu-id="8e06e-195">**Exchange Access with Modern Auth and MFA disabled**</span></span> <br/> |<span data-ttu-id="8e06e-196">**Acceso a Exchange con autenticación moderna y MFA activados**</span><span class="sxs-lookup"><span data-stu-id="8e06e-196">**Exchange Access with Modern Auth and MFA enabled**</span></span> <br/> |
|<span data-ttu-id="8e06e-197">En línea</span><span class="sxs-lookup"><span data-stu-id="8e06e-197">Online</span></span>  <br/> |<span data-ttu-id="8e06e-198">En línea</span><span class="sxs-lookup"><span data-stu-id="8e06e-198">Online</span></span>  <br/> |<span data-ttu-id="8e06e-199">Inicio de sesión web</span><span class="sxs-lookup"><span data-stu-id="8e06e-199">Web Sign-in</span></span>  <br/> |<span data-ttu-id="8e06e-200">Sí</span><span class="sxs-lookup"><span data-stu-id="8e06e-200">Yes</span></span>  <br/> |<span data-ttu-id="8e06e-201">Sí</span><span class="sxs-lookup"><span data-stu-id="8e06e-201">Yes</span></span>  <br/> |<span data-ttu-id="8e06e-202">Sí</span><span class="sxs-lookup"><span data-stu-id="8e06e-202">Yes</span></span>  <br/> |
|<span data-ttu-id="8e06e-203">En línea</span><span class="sxs-lookup"><span data-stu-id="8e06e-203">Online</span></span>  <br/> |<span data-ttu-id="8e06e-204">En línea</span><span class="sxs-lookup"><span data-stu-id="8e06e-204">Online</span></span>  <br/> |<span data-ttu-id="8e06e-205">Nombre de usuario y contraseña</span><span class="sxs-lookup"><span data-stu-id="8e06e-205">Username/Password</span></span>  <br/> |<span data-ttu-id="8e06e-206">Sí</span><span class="sxs-lookup"><span data-stu-id="8e06e-206">Yes</span></span>  <br/> |<span data-ttu-id="8e06e-207">Sí</span><span class="sxs-lookup"><span data-stu-id="8e06e-207">Yes</span></span>  <br/> |<span data-ttu-id="8e06e-208">No</span><span class="sxs-lookup"><span data-stu-id="8e06e-208">No</span></span>  <br/> |
|<span data-ttu-id="8e06e-209">En línea</span><span class="sxs-lookup"><span data-stu-id="8e06e-209">Online</span></span>  <br/> |<span data-ttu-id="8e06e-210">Local</span><span class="sxs-lookup"><span data-stu-id="8e06e-210">On-premises</span></span>  <br/> |<span data-ttu-id="8e06e-211">Inicio de sesión web</span><span class="sxs-lookup"><span data-stu-id="8e06e-211">Web Sign-in</span></span>  <br/> |<span data-ttu-id="8e06e-212">Sí</span><span class="sxs-lookup"><span data-stu-id="8e06e-212">Yes</span></span>  <br/> |<span data-ttu-id="8e06e-213">No</span><span class="sxs-lookup"><span data-stu-id="8e06e-213">No</span></span>  <br/> |<span data-ttu-id="8e06e-214">No</span><span class="sxs-lookup"><span data-stu-id="8e06e-214">No</span></span>  <br/> |
|<span data-ttu-id="8e06e-215">En línea</span><span class="sxs-lookup"><span data-stu-id="8e06e-215">Online</span></span>  <br/> |<span data-ttu-id="8e06e-216">Local</span><span class="sxs-lookup"><span data-stu-id="8e06e-216">On-Premises</span></span>  <br/> |<span data-ttu-id="8e06e-217">Nombre de usuario y contraseña</span><span class="sxs-lookup"><span data-stu-id="8e06e-217">Username/Password</span></span>  <br/> |<span data-ttu-id="8e06e-218">Sí</span><span class="sxs-lookup"><span data-stu-id="8e06e-218">Yes</span></span>  <br/> |<span data-ttu-id="8e06e-219">Sí</span><span class="sxs-lookup"><span data-stu-id="8e06e-219">Yes</span></span>  <br/> |<span data-ttu-id="8e06e-220">No</span><span class="sxs-lookup"><span data-stu-id="8e06e-220">No</span></span>  <br/> |
|<span data-ttu-id="8e06e-221">Local</span><span class="sxs-lookup"><span data-stu-id="8e06e-221">On-premises</span></span>  <br/> |<span data-ttu-id="8e06e-222">En línea/local</span><span class="sxs-lookup"><span data-stu-id="8e06e-222">Online/On-Premises</span></span>  <br/> |<span data-ttu-id="8e06e-223">Autenticación de PIN</span><span class="sxs-lookup"><span data-stu-id="8e06e-223">PIN Authentication</span></span>  <br/> |<span data-ttu-id="8e06e-224">Sí</span><span class="sxs-lookup"><span data-stu-id="8e06e-224">Yes</span></span>  <br/> |<span data-ttu-id="8e06e-225">No</span><span class="sxs-lookup"><span data-stu-id="8e06e-225">No</span></span>  <br/> |<span data-ttu-id="8e06e-226">No</span><span class="sxs-lookup"><span data-stu-id="8e06e-226">No</span></span>  <br/> |
|<span data-ttu-id="8e06e-227">Local</span><span class="sxs-lookup"><span data-stu-id="8e06e-227">On-premises</span></span>  <br/> |<span data-ttu-id="8e06e-228">En línea/local</span><span class="sxs-lookup"><span data-stu-id="8e06e-228">Online/On-Premises</span></span>  <br/> |<span data-ttu-id="8e06e-229">Nombre de usuario y contraseña</span><span class="sxs-lookup"><span data-stu-id="8e06e-229">Username/Password</span></span>  <br/> |<span data-ttu-id="8e06e-230">Sí</span><span class="sxs-lookup"><span data-stu-id="8e06e-230">Yes</span></span>  <br/> |<span data-ttu-id="8e06e-231">Sí</span><span class="sxs-lookup"><span data-stu-id="8e06e-231">Yes</span></span>  <br/> |<span data-ttu-id="8e06e-232">N/D</span><span class="sxs-lookup"><span data-stu-id="8e06e-232">N/A</span></span>  <br/> |
|<span data-ttu-id="8e06e-233">Local</span><span class="sxs-lookup"><span data-stu-id="8e06e-233">On-premises</span></span>  <br/> |<span data-ttu-id="8e06e-234">En línea/local</span><span class="sxs-lookup"><span data-stu-id="8e06e-234">Online/On-Premises</span></span>  <br/> |<span data-ttu-id="8e06e-235">Inicio de sesión vía equipo (BTOE)</span><span class="sxs-lookup"><span data-stu-id="8e06e-235">Sign-in via PC (BTOE)</span></span>  <br/> |<span data-ttu-id="8e06e-236">Sí</span><span class="sxs-lookup"><span data-stu-id="8e06e-236">Yes</span></span>  <br/> |<span data-ttu-id="8e06e-237">Sí</span><span class="sxs-lookup"><span data-stu-id="8e06e-237">Yes</span></span>  <br/> |<span data-ttu-id="8e06e-238">N/D</span><span class="sxs-lookup"><span data-stu-id="8e06e-238">N/A</span></span>  <br/> |
   
- <span data-ttu-id="8e06e-239">**Características de teléfono** El conjunto de características puede variar ligeramente en función de los socios de teléfono IP.</span><span class="sxs-lookup"><span data-stu-id="8e06e-239">**Phone features** The feature set may vary slightly based on the IP phone partner.</span></span> <span data-ttu-id="8e06e-240">Para la característica completa establece y para obtener más información sobre las características para cada fabricante del teléfono, vea [Introducción teléfonos de Skype para profesionales en línea](getting-phones-for-skype-for-business-online.md).</span><span class="sxs-lookup"><span data-stu-id="8e06e-240">For the complete feature set and for more information on the features for each phone manufacturer, see [Getting phones for Skype for Business Online](getting-phones-for-skype-for-business-online.md).</span></span>
    
- <span data-ttu-id="8e06e-241">**Bloqueo del teléfono**: esta es una característica que se ha incorporado a los teléfonos certificados para Skype Empresarial recientemente como medida de protección del teléfono.</span><span class="sxs-lookup"><span data-stu-id="8e06e-241">**Phone-Lock** is a recently introduced feature in Skype for Business certified phones that is used to secure a phone.</span></span> <span data-ttu-id="8e06e-242">Si se habilita, los usuarios le pedirá que cree un PIN tras la autenticación.</span><span class="sxs-lookup"><span data-stu-id="8e06e-242">If enabled, users will be asked to create a PIN upon successful authentication.</span></span> <span data-ttu-id="8e06e-243">Una vez creado, el teléfono se bloqueará cuando transcurra el tiempo de inactividad definido, o si el usuario bloquea manualmente el teléfono o sincroniza el bloqueo del teléfono con el de su equipo mediante la característica de emparejamiento del teléfono.</span><span class="sxs-lookup"><span data-stu-id="8e06e-243">Once created, phones will lock when the idle-timeout that you define expires, a user manually locks their phone, or they sync their phone-lock with their PC lock using Phone Pairing.</span></span> <span data-ttu-id="8e06e-244">Si el PIN de bloqueo del teléfono se escribe mal varias veces, el teléfono se cierre la sesión del usuario o requieren código de un administrador para desbloquear el teléfono, pero esto variará en función del socio de teléfono.</span><span class="sxs-lookup"><span data-stu-id="8e06e-244">If the phone-lock PIN is entered wrong several times, the phone will either sign the user out or require an administrator's code to unlock the phone, but this will vary depending on the phone partner.</span></span> <span data-ttu-id="8e06e-245">El PIN del usuario debe estar comprendido entre 6 y 15 dígitos.</span><span class="sxs-lookup"><span data-stu-id="8e06e-245">The user's PIN should be between 6 and 15 digits.</span></span>
    
    <span data-ttu-id="8e06e-246">Puede deshabilitar el bloqueo del teléfono para la organización (que está habilitada de forma predeterminada), cambiar el tiempo de espera de inactividad y elija si los usuarios pueden realizar llamadas telefónicas mientras están bloqueados o no utiliza configuración de banda.</span><span class="sxs-lookup"><span data-stu-id="8e06e-246">You can disable Phone-Lock for your organization (which is enabled by default), change the idle-timeout, and choose whether users can make phone calls while they are locked or not using inband-settings.</span></span> <span data-ttu-id="8e06e-247">Consulte [Set-CsIPPhonePolicy](https://technet.microsoft.com/en-us/library/mt629497.aspx) para obtener más detalles sobre esta configuración.</span><span class="sxs-lookup"><span data-stu-id="8e06e-247">See [Set-CsIPPhonePolicy](https://technet.microsoft.com/en-us/library/mt629497.aspx) for more details on those settings.</span></span>
    
## <a name="step-7-optional---if-you-have-device-pairing-and-better-together-over-ethernet-btoe"></a><span data-ttu-id="8e06e-248">Paso 7 (opcional): si se dispone de emparejamiento de dispositivos y Better Together over Ethernet (BToE)</span><span class="sxs-lookup"><span data-stu-id="8e06e-248">Step 7 (optional) - If you have device pairing and Better Together over Ethernet (BToE)</span></span>
<span data-ttu-id="8e06e-249"><a name="BK_BTOE"> </a></span><span class="sxs-lookup"><span data-stu-id="8e06e-249"><a name="BK_BTOE"> </a></span></span>

<span data-ttu-id="8e06e-250">BToE es un teléfono paining mecanismo para teléfonos IP de socio que pares de teléfono de un usuario con sus Skype de Windows para la aplicación empresarial.</span><span class="sxs-lookup"><span data-stu-id="8e06e-250">BToE is a phone paining mechanism for Partner IP phones that pairs a user's phone with their Windows Skype for Business app.</span></span> <span data-ttu-id="8e06e-251">BToE permite a los usuarios:</span><span class="sxs-lookup"><span data-stu-id="8e06e-251">BToE enables users to:</span></span>
  
- <span data-ttu-id="8e06e-252">Inicie sesión en su teléfono IP con su Skype para la aplicación de escritorio empresarial (mediante un PC)</span><span class="sxs-lookup"><span data-stu-id="8e06e-252">Sign in to their IP phone using their Skype for Business desktop app (using a PC)</span></span>
    
- <span data-ttu-id="8e06e-253">Sincronizar el bloqueo del teléfono con bloqueo de PC</span><span class="sxs-lookup"><span data-stu-id="8e06e-253">Synchronize Phone-Lock with PC lock</span></span>
    
- <span data-ttu-id="8e06e-254">Hacer clic para llamar</span><span class="sxs-lookup"><span data-stu-id="8e06e-254">Click to call</span></span>
    
<span data-ttu-id="8e06e-255">BToE puede configurarse para funcionar en dos modos: *Manual* y *automático* (valor predeterminado).</span><span class="sxs-lookup"><span data-stu-id="8e06e-255">BToE can be configured to operate in two modes:  *Auto*  (default) and *Manual*  .</span></span> <span data-ttu-id="8e06e-256">También se puede activar (opción predeterminada) y desactivar para los usuarios con configuración en banda de Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="8e06e-256">It can also be enabled (default)/disabled for users using Skype for Business in-band settings.</span></span> <span data-ttu-id="8e06e-257">En el modo *Manual*  , los usuarios tendrán que realizar un paso adicional para emparejar sus teléfonos con la aplicación para Windows.</span><span class="sxs-lookup"><span data-stu-id="8e06e-257">When operating in *Manual*  mode, users will have to take an additional step to pair their phone with their Windows app.</span></span>
  
 <span data-ttu-id="8e06e-258">**Para implementar BToE a los usuarios**</span><span class="sxs-lookup"><span data-stu-id="8e06e-258">**To deploy BToE to users**</span></span>
  
1. <span data-ttu-id="8e06e-259">Conecte los equipos con los teléfonos usando el puerto de los equipos.</span><span class="sxs-lookup"><span data-stu-id="8e06e-259">Connect their PC to their phone using the PC port.</span></span>
    
     ![Deploying phones.](../../images/e21d76c7-867c-4fe6-95c6-fc40c608ed0c.png)
  
2. <span data-ttu-id="8e06e-p121">Descargue el software BToE más reciente desde el sitio web del fabricante utilizando los vínculos que se ofrecen a continuación e instálelo. Para obtener una mejor experiencia de usuario, puede distribuir e instalar el software BToE usando una solución de distribución para administradores, como System Center Configuration Manager (SCCM). Para obtener ayuda sobre el uso de SCCM, consulte [Paquetes y programas en System Center Configuration Manager](https://docs.microsoft.com/en-us/sccm/apps/deploy-use/packages-and-programs).</span><span class="sxs-lookup"><span data-stu-id="8e06e-p121">Download and install the latest BToE software from the manufacturer website from the links below. For a better user experience, you can distribute and install the BToE software using an admin distribution solution such as System Center Configuration Manager (SCCM). For help using SCCM, See [Packages and programs in System Center Configuration Manager](https://docs.microsoft.com/en-us/sccm/apps/deploy-use/packages-and-programs).</span></span>
    
  - [<span data-ttu-id="8e06e-264">Sitio de descarga de Software de Polycom BToE</span><span class="sxs-lookup"><span data-stu-id="8e06e-264">Polycom BToE Software Download site</span></span>](http://www.polycom.com/voice-conferencing-solutions/microsoft-phones.html)
    
  - [<span data-ttu-id="8e06e-265">Descarga del software BToE de Yealink</span><span class="sxs-lookup"><span data-stu-id="8e06e-265">Yealink BToE Software Download</span></span>](http://www.yealink.com/products_list_10.html)
    
  - [<span data-ttu-id="8e06e-266">Descarga del software BToE de AudioCodes</span><span class="sxs-lookup"><span data-stu-id="8e06e-266">AudioCodes BToE Software Downloads</span></span>](https://www.audiocodes.com/solutions-products/solutions/skype-for-business-microsoft-teams/skype-for-business-online)
    
3. <span data-ttu-id="8e06e-267">La configuración del servidor para BToE se establece en **habilitado** y **el modo automático** de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="8e06e-267">The server setting for BToE is set to **Enabled** and **Auto mode** by default.</span></span> <span data-ttu-id="8e06e-268">Para cambiar esa configuración, vea [Set-CsIPPhonePolicy](https://technet.microsoft.com/en-us/library/mt629497.aspx).</span><span class="sxs-lookup"><span data-stu-id="8e06e-268">To change those settings, see [Set-CsIPPhonePolicy](https://technet.microsoft.com/en-us/library/mt629497.aspx).</span></span>
    
> [!NOTE]
> <span data-ttu-id="8e06e-269">Actualmente BToE no es compatible con Mac ni plataformas VDI.</span><span class="sxs-lookup"><span data-stu-id="8e06e-269">BToE isn't currently supported on Mac and VDI platforms.</span></span> 
  
## <a name="related-topics"></a><span data-ttu-id="8e06e-270">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="8e06e-270">Related topics</span></span>
[<span data-ttu-id="8e06e-271">Obtener números de teléfono de servicio para Skype Empresarial y Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="8e06e-271">Getting service phone numbers for Skype for Business and Microsoft Teams</span></span>](../../what-is-phone-system-in-office-365/getting-service-phone-numbers.md)

[<span data-ttu-id="8e06e-272">Esto es lo que conseguirá con Sistema telefónico en Office 365</span><span class="sxs-lookup"><span data-stu-id="8e06e-272">Here's what you get with Phone System in Office 365</span></span>](../../what-is-phone-system-in-office-365/here-s-what-you-get-with-phone-system.md)

[<span data-ttu-id="8e06e-273">Países y regiones donde Audioconferencia y Planes de llamada están disponibles</span><span class="sxs-lookup"><span data-stu-id="8e06e-273">Country and region availability for Audio Conferencing and Calling Plans</span></span>](../../country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

  
 
