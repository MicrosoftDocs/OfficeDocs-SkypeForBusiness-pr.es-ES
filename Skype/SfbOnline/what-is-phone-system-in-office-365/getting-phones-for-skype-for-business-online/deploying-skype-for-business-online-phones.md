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
description: Descubra los pasos de implementación para obtener el firmware correcto, actualizarlo si es necesario, asignar licencias y ajustar la configuración para teléfonos de Skype Empresarial Online
ms.openlocfilehash: 4237e1cb32204a3d87d639710a2829c1111cc354
ms.sourcegitcommit: cbb4738e119cf366c3aad9aad7f7b369bcd86c19
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/30/2018
ms.locfileid: "23780066"
---
# <a name="deploying-skype-for-business-online-phones"></a><span data-ttu-id="c1a47-103">Implementación de teléfonos en Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="c1a47-103">Deploying Skype for Business Online phones</span></span>

<span data-ttu-id="c1a47-104">[] Esta guía de implementación le ayudará a implementar teléfonos IP para Skype Empresarial Online.</span><span class="sxs-lookup"><span data-stu-id="c1a47-104">This is deployment guide will help you deploy Skype for Business Online IP phones.</span></span>
  
<span data-ttu-id="c1a47-p101">En todo tipo de negocios, tener un número de teléfono permite a los usuarios hacer y recibir llamadas de voz, lo cual es un requisito importante para lograr los objetivos empresariales. Los usuarios con números de teléfono pueden hacer llamadas de voz con cualquier dispositivo con Skype Empresarial, como teléfonos IP, equipos y dispositivos móviles. Para obtener más información sobre los teléfonos IP de Skype Empresarial, consulte [Obtener teléfonos para Skype Empresarial Online](getting-phones-for-skype-for-business-online.md).</span><span class="sxs-lookup"><span data-stu-id="c1a47-p101">In all types of businesses, having a phone number allows users to make and get voice calls and it is an important requirement to do business. Users that have phone numbers will be able to make voice calls across all Skype for Business devices including IP phones, PCs, and mobile devices. You can learn more about Skype for Business IP phones by seeing, [Getting phones for Skype for Business Online](getting-phones-for-skype-for-business-online.md).</span></span>
  
## <a name="deployment-steps-for-ip-phones"></a><span data-ttu-id="c1a47-108">Pasos para la implementación de teléfonos IP</span><span class="sxs-lookup"><span data-stu-id="c1a47-108">Deployment steps for IP phones</span></span>

### <a name="step-1---download-the-manufacturers-administrator-guides-and-phone-manuals"></a><span data-ttu-id="c1a47-109">Paso 1: descargar las guías para administradores y los manuales de los teléfonos del fabricante</span><span class="sxs-lookup"><span data-stu-id="c1a47-109">Step 1 - Download the manufacturer's administrator guides and phone manuals</span></span>

<span data-ttu-id="c1a47-110">Antes de comenzar, es recomendable descargar las guías para administradores y los manuales de usuario de los teléfonos que proporciona el fabricante.</span><span class="sxs-lookup"><span data-stu-id="c1a47-110">Before you get started, it's a good idea to download the phone manufacturer's administration guides and phone user manuals.</span></span>
  
- <span data-ttu-id="c1a47-111">Para los teléfonos Polycom, vea la [Guía de implementación de Polycom] ((http://www.polycom.com/voice-conferencing-solutions/desktop-ip-phones.html).</span><span class="sxs-lookup"><span data-stu-id="c1a47-111">For Polycom phones, see the http://www.polycom.com/voice-conferencing-solutions/desktop-ip-phones.html).</span></span>
    
- <span data-ttu-id="c1a47-112">Para los teléfonos Yealink, consulte la [Solución de teléfonos SIP HD para Skype Empresarial de Yealink](http://www.yealink.com/products_top_2.html).</span><span class="sxs-lookup"><span data-stu-id="c1a47-112">For Yealink phones, see [Yealink Skype for Business® HD IP Phones Solution](http://www.yealink.com/products_top_2.html).</span></span>
    
- <span data-ttu-id="c1a47-113">Para teléfonos AudioCodes, consulte la [Guía de administración del aprovisionamiento de AudioCodes](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/ip-phones-room-solutions).</span><span class="sxs-lookup"><span data-stu-id="c1a47-113">For AudioCodes phones, see the [Audiocodes Provisioning Management Guide](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/ip-phones-room-solutions).</span></span>
    
### <a name="step-2---make-sure-youre-purchasing-or-migrating-a-skype-for-business-supported-ip-phone-and-firmware"></a><span data-ttu-id="c1a47-114">Paso 2: asegurarse de que los teléfonos IP y el firmware que va a comprar o a los que va a realizar la migración son compatibles con Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="c1a47-114">Step 2 - Make sure you're purchasing or migrating a Skype for Business Supported IP phone and firmware</span></span>

<span data-ttu-id="c1a47-p102">El firmware y los teléfonos compatibles con Skype Empresarial Online también lo son con Skype Empresarial Server, pero no siempre sucede lo mismo a la inversa. Para asegurarse de que los teléfonos y el firmware que va a comprar o aprovisionar son compatibles, consulte la guía [Obtener teléfonos para Skype Empresarial Online](getting-phones-for-skype-for-business-online.md).</span><span class="sxs-lookup"><span data-stu-id="c1a47-p102">A Skype for Business Online supported phone and firmware is compatible for Skype for Business Server as well, but the opposite isn't always true. To make sure you are buying or provisioning a supported phone and firmware, see [Getting phones for Skype for Business Online](getting-phones-for-skype-for-business-online.md) guide.</span></span>
  
### <a name="step-3---checking-that-the-right-firmware-is-installed-and-update-the-firmware-if-required"></a><span data-ttu-id="c1a47-117">Paso 3: comprobar que está instalado el firmware correcto y actualizarlo si es necesario</span><span class="sxs-lookup"><span data-stu-id="c1a47-117">Step 3 - Checking that the right firmware is installed and update the firmware if required</span></span>

<span data-ttu-id="c1a47-p103">Compruebe la versión del firmware de sus teléfonos. Para:</span><span class="sxs-lookup"><span data-stu-id="c1a47-p103">To check the firmware version on your phones. For:</span></span>
  
- <span data-ttu-id="c1a47-120">**Teléfonos Polycom VVX:** vaya a **Ajustes** > **Estado** > **Plataforma** > **Aplicación** > **Principal**.</span><span class="sxs-lookup"><span data-stu-id="c1a47-120">**Polycom VVX phones**, go to **Settings** > **Status** > **Platform** > **Application** > **Main**.</span></span>
    
- <span data-ttu-id="c1a47-121">**Teléfonos Yealink:** vaya a **Estado** en la pantalla principal del teléfono.</span><span class="sxs-lookup"><span data-stu-id="c1a47-121">**Yealink phones**, go to **Status** on the main phone screen.</span></span>
    
- <span data-ttu-id="c1a47-122">**Teléfonos AudioCodes:** desde la pantalla de inicio, vaya a **Menú** > **Estado del dispositivo** > **Versión de firmware**.</span><span class="sxs-lookup"><span data-stu-id="c1a47-122">**AudioCodes phones**, go to **Menu** > **Device Status** > **Firmware version** from the start screen.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="c1a47-p104">Para obtener más información sobre el acceso remoto a los teléfonos, consulte las guías de administración de los fabricantes. Vea los enlaces anteriores para acceder a las guías de usuario y a los manuales de los teléfonos.</span><span class="sxs-lookup"><span data-stu-id="c1a47-p104">For remote access to phone details refer to manufacturer administration guides. See the links above for the user guides and phone manuals.</span></span> 
  
- <span data-ttu-id="c1a47-125">**Teléfonos Lync Phone Edition (LPE):** desde la pantalla de inicio, vaya a **Menú** > **Información del sistema**.</span><span class="sxs-lookup"><span data-stu-id="c1a47-125">**Lync Phone Edition (LPE) phones**, go to **Menu** > **System Information** from the start screen.</span></span>
    
### <a name="step-4---device-update-considerations"></a><span data-ttu-id="c1a47-126">Paso 4: consideraciones con respecto a la actualización de los dispositivos</span><span class="sxs-lookup"><span data-stu-id="c1a47-126">Step 4 - Device Update Considerations</span></span>

> [!NOTE]
> <span data-ttu-id="c1a47-p105">El firmware de Polycom anterior a 5.5.1.X tenía un mecanismo de bloqueo del dispositivo específico del fabricante que se ha reemplazado con una implementación del "bloqueo del teléfono" de Skype Empresarial. Al actualizar un teléfono con la versión 5.4.X.X que tuviera activado el "bloqueo del dispositivo" a la versión 5.5.1.X con "bloqueo del teléfono" no se conservará el código PIN de la característica de "bloqueo del dispositivo", lo que puede provocar que el teléfono quede desprotegido. Los usuarios que tengan activado el "bloqueo del dispositivo", deberán activar el siguiente parámetro del perfil del dispositivo Polycom para permitir que los usuarios controlen cuándo realizar la actualización (lync.deviceUpdate.popUpSK.enabled=1).</span><span class="sxs-lookup"><span data-stu-id="c1a47-p105">Polycom firmware prior to 5.5.1.X had a manufacturer specific device-lock mechanism that is replaced with a Skype for Business implementation "Phone-Lock". Upgrading a phone from 5.4.X.X that was secured with "Device-Lock" to 5.5.1.X with "Phone-Lock" won't inherit the PIN code from "Device-Lock", which can leave the phone unsecured. For users who have activated "Device-Lock", you need to enable the following Polycom Device Profile parameter to give users control of time of upgrade (lync.deviceUpdate.popUpSK.enabled=1).</span></span> 
  
<span data-ttu-id="c1a47-p106">El servicio de Skype Empresarial administra las actualizaciones de firmware. El firmware de los teléfonos certificados para Skype Empresarial se carga en el servidor del servicio de actualización de Skype Empresarial. La actualización del dispositivo está activada de forma predeterminada en todos los teléfonos. Los teléfonos descargarán e instalarán automáticamente las compilaciones más recientes certificadas, dependiendo del tiempo de inactividad de cada teléfono y los intervalos de sondeo. Puede desactivar la opción de actualización del dispositivo usando el cmdlet [Set-CsIPPhonePolicy](https://technet.microsoft.com/en-us/library/mt629497.aspx) y estableciendo el parámetro _EnableDeviceUpdate_ en `false`.</span><span class="sxs-lookup"><span data-stu-id="c1a47-p106">Firmware updates are managed by the Skype for Business Service. Every Skype for Business certified phone's firmware is uploaded to the Skype for Business Update server, and device update is enabled on all phones by default. Depending on the inactivity time on the phone and polling intervals, phones will automatically download and install the latest certified builds. You can disable the device update settings using the [Set-CsIPPhonePolicy](https://technet.microsoft.com/en-us/library/mt629497.aspx) cmdlet and setting the _EnableDeviceUpdate_ parameter to `false`.</span></span>
  
![Implementación de teléfonos.](../../images/be727622-1924-439f-96ca-89230739db9e.png)
  
<span data-ttu-id="c1a47-p107">Cuando haya un nuevo firmware disponible y preparado para descargarse e instalarse, el teléfono se lo notificará al usuario. Los teléfonos Polycom informarán al usuario y le permitirán elegir entre las opciones **Actualizar** y **Posponer**.</span><span class="sxs-lookup"><span data-stu-id="c1a47-p107">When a new firmware is available and ready for download and install, the phone will notify the user. Polycom phones will notify the user and provide them with an option to **Update**, or **Postpone**.</span></span>
  
![Implementación de teléfonos.](../../images/50956fa0-da0c-4085-9bb5-4a2e99aecebb.png)
  
<span data-ttu-id="c1a47-138">En un teléfono Polycom, puede actualizar el firmware desde el teléfono seleccionando **ActualizaciónSw**.</span><span class="sxs-lookup"><span data-stu-id="c1a47-138">For a Polycom phone, you can update the firmware on the phone by selecting **SwUpdate**.</span></span>
  
![Implementación de teléfonos.](../../images/376c1998-6ce6-44b6-a84d-ae7d96b1c307.png)
  
<span data-ttu-id="c1a47-p108">También puede optar por administrar las actualizaciones de firmware usando un sistema de aprovisionamiento de nuestros socios. Para obtener información sobre la administración de los sistemas de aprovisionamiento de nuestros socios y la personalización avanzada de teléfonos, consulte las guías de administración del fabricante.</span><span class="sxs-lookup"><span data-stu-id="c1a47-p108">You can also choose to manage firmware updates using a partner provisioning system. For partner provisioning system management including advanced phone customization, refer to manufacturer administration guides.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="c1a47-142">Asegúrese de que solo tiene una autoridad de actualización de dispositivos (actualización de dispositivos en banda o un servidor de aprovisionamiento de terceros) para evitar los bucles de actualizaciones.</span><span class="sxs-lookup"><span data-stu-id="c1a47-142">Make sure to have a single device update authority (In-band device update or a third-party provisioning server) to avoid update loops.</span></span> 
  
### <a name="step-5---configuration-and-infrastructure-phone-settings"></a><span data-ttu-id="c1a47-143">Paso 5: establecer los ajustes de configuración e infraestructura de los teléfonos</span><span class="sxs-lookup"><span data-stu-id="c1a47-143">Step 5 - Configure and infrastructure phone settings</span></span>

<span data-ttu-id="c1a47-p109">Puede configurar las opciones y políticas más utilizadas de los teléfonos usando los cmdlets de Windows PowerShell para la administración en banda de Skype Empresarial. Consulte [Set-CsIPPhonePolicy](https://technet.microsoft.com/en-us/library/mt629497.aspx) para obtener más información sobre estos parámetros y ajustes.</span><span class="sxs-lookup"><span data-stu-id="c1a47-p109">You can set up the most commonly used phone options and policies using Skype for Business In-band management Windows PowerShell cmdlets. See [Set-CsIPPhonePolicy](https://technet.microsoft.com/en-us/library/mt629497.aspx) for details of those parameters and settings.</span></span>
  
<span data-ttu-id="c1a47-146">Para la planificación de la infraestructura de red, vea [Marco de operaciones de Skype](https://www.skypeoperationsframework.com/).</span><span class="sxs-lookup"><span data-stu-id="c1a47-146">For network infrastructure planning, see [Skype Operations Framework](https://www.skypeoperationsframework.com/) andDeploy, Migrate, and Roll Out.</span></span>
  
### <a name="step-6---preparing-for-users-to-sign-in"></a><span data-ttu-id="c1a47-147">Paso 6: prepararse para el inicio de sesión de los usuarios</span><span class="sxs-lookup"><span data-stu-id="c1a47-147">Step 6 - Preparing for users to sign-in</span></span>

<span data-ttu-id="c1a47-p110">Para que los usuarios puedan iniciar sesión correctamente en un teléfono de Skype Empresarial Online y realizar llamadas, debe asegurarse de que se les han asignado las licencias correctamente. Como mínimo, tendrá que asignar una licencia de Sistema telefónico y un Plan de llamadas. Para obtener más información, puede consultar [Licencias de complementos de Skype Empresarial y Microsoft Teams](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md) y [Asignar licencias de Skype Empresarial y Microsoft Teams](../../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span><span class="sxs-lookup"><span data-stu-id="c1a47-p110">To enable users to successfully sign-on to a Skype for Business Online phone and make calls, you need to make sure users are assigned the correct licenses. At a minimum you will need to assign a Skype for Business Cloud PBX license and a PSTN Calling plan. For additional information you can see [Skype for Business add-on licensing](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md) and[Assign Skype for Business licenses](../../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md) .</span></span>
  
<span data-ttu-id="c1a47-151">Puede encontrar más información acerca de los Planes de llamada mediante la lectura de [¿Cuáles son los Planes de llamada en Office 365?](/microsoftteams/what-are-calling-plans-in-office-365)</span><span class="sxs-lookup"><span data-stu-id="c1a47-151">You can find out more about Calling Plans by reading [What are Calling Plans in Office 365?](/microsoftteams/what-are-calling-plans-in-office-365)</span></span>
  
- <span data-ttu-id="c1a47-152">Las **opciones de inicio de sesión** disponibles para los usuarios online son:</span><span class="sxs-lookup"><span data-stu-id="c1a47-152">**Sign-in options** that are available for Online users are:</span></span>
    
  - <span data-ttu-id="c1a47-153">Los usuarios con teléfonos **Polycom VVX 5XX/6XX** verán:</span><span class="sxs-lookup"><span data-stu-id="c1a47-153">For those users with **Polycom VVX 5XX/6XX** phones, they will see:</span></span>
    
     ![Implementación de teléfonos.](../../images/8a1ffb33-8a63-4242-bb76-d5fafb6a6472.png)
  
  - <span data-ttu-id="c1a47-155">Los usuarios con teléfonos **Yealink T48G/T46G** verán:</span><span class="sxs-lookup"><span data-stu-id="c1a47-155">For those users with **Yealink T48G/T46G** phones, they will see:</span></span>
    
     ![Inicio de sesión de teléfonos Yealink.](../../images/2a2892ae-850d-4781-8be0-4ffb8af068c9.png)
  
    <span data-ttu-id="c1a47-157">Para obtener información sobre las opciones de inicio de sesión que admite cada fabricante, consulte [Obtener teléfonos para Skype Empresarial Online](getting-phones-for-skype-for-business-online.md).</span><span class="sxs-lookup"><span data-stu-id="c1a47-157">For details on sign-in options supported by manufacturer, see [Getting phones for Skype for Business Online](getting-phones-for-skype-for-business-online.md).</span></span>
    
- <span data-ttu-id="c1a47-p111">**Id. de usuario**: usando el teclado del teléfono o el teclado en pantalla (si está disponible), los usuarios pueden usar el nombre de usuario y la contraseña de su organización para iniciar sesión en el teléfono. Por ejemplo, deben usar el formato UPN, como *amosm@contoso.com*  , en el nombre de usuario.</span><span class="sxs-lookup"><span data-stu-id="c1a47-p111">**User ID** Using the phone's keypad or on-screen keyboard (if available), users can use their organization's user name and password to sign in to the phone. For example, they should use the UPN format like *amosm@contoso.com*  for their user name.</span></span>
    
     ![Implementación de teléfonos.](../../images/f67fa8f4-66a5-451d-bdf2-a12daac15cb5.png)
  
    > [!NOTE]
    > <span data-ttu-id="c1a47-161">La autenticación con PIN no se admite en Skype Empresarial Online con teléfonos LPE y teléfonos IP de socios.</span><span class="sxs-lookup"><span data-stu-id="c1a47-161">PIN authentication isn't supported for Skype for Business Online for LPE and Partner IP phones.</span></span> 
  
- <span data-ttu-id="c1a47-p112">**Con un equipo**: si en el equipo del usuario está instalado y habilitado el software Better Together over Ethernet (BToE), este puede iniciar sesión en el teléfono usando la ventana de autenticación de su aplicación de Skype Empresarial para Windows. Consulte [Paso 7 (opcional): si se dispone de emparejamiento de dispositivos y Better Together over Ethernet (BToE)](deploying-skype-for-business-online-phones.md#BK_BTOE) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="c1a47-p112">**Using a PC** When Better Together over Ethernet (BToE) software is installed on user's PC and enabled, users can log into their phone using the authentication window on their Windows Skype for Business App. See[Step 7 (optional) - If you have device pairing and Better Together over Ethernet (BToE)](deploying-skype-for-business-online-phones.md#BK_BTOE) for other information.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="c1a47-p113">Los usuarios deben usar el nombre de usuario y la contraseña de su organización para iniciar sesión en el teléfono. Por ejemplo, deben usar el formato UPN, como  *amosm@contoso.com*  , en el nombre de usuario.</span><span class="sxs-lookup"><span data-stu-id="c1a47-p113">Users are required to use their organization's user name and password to sign in to the phone. For example, they should use the UPN format like  *amosm@contoso.com*  for their user name.</span></span>
  
     ![Implementación de teléfonos.](../../images/f67fa8f4-66a5-451d-bdf2-a12daac15cb5.png)
  
- <span data-ttu-id="c1a47-p114">**Con inicio de sesión web**: esta es una nueva forma de autenticación que permite a los usuarios online realizar el proceso a través de un navegador web estándar. Los usuarios recibirán una serie de instrucciones que deben seguir para iniciar sesión a través del navegador.</span><span class="sxs-lookup"><span data-stu-id="c1a47-p114">**Using a** Web Sign-in: This is a new way for Online users to authenticate using a standard web browser. Users will be provided with a set of instructions to follow when they use a browser to sign-in.</span></span>
    
  - <span data-ttu-id="c1a47-169">Los usuarios con teléfonos **Polycom VVX 5XX/6XX** verán:</span><span class="sxs-lookup"><span data-stu-id="c1a47-169">For users with **Polycom VVX 5XX/6XX** phones, they will see:</span></span>
    
     ![Implementación de teléfonos.](../../images/ba0df923-a6e5-4a9b-b40b-b03ca188e814.png)
  
  - <span data-ttu-id="c1a47-171">Los usuarios con teléfonos **Yealink T48G/T46G** verán:</span><span class="sxs-lookup"><span data-stu-id="c1a47-171">For users with **Yealink T48G/T46G** phones, they will see:</span></span>
    
     ![Inicio de sesión de teléfonos Yealink.](../../images/86551cc3-533a-4694-9683-bad907c9ad5a.png)
  
    <span data-ttu-id="c1a47-p115">El código que se genera expira en 15 minutos. Una vez expirado, en función del teléfono, el usuario tendrá que hacer clic en **Reintentar** o en **Aceptar** para generar un código nuevo.</span><span class="sxs-lookup"><span data-stu-id="c1a47-p115">The code that is generated will expire in 15 minutes. When it expires, the user will have to click **Retry** or **OK** to generate a new code depending on the phone.</span></span>
    
  - <span data-ttu-id="c1a47-175">Los usuarios con teléfonos **Polycom VVX 5XX/6XX** verán:</span><span class="sxs-lookup"><span data-stu-id="c1a47-175">For users with **Polycom VVX 5XX/6XX** phones, they will see:</span></span>
    
     ![El código PIN ha caducado.](../../images/b5d27037-aa26-4054-be95-d5a6c293d08c.png)
  
  - <span data-ttu-id="c1a47-177">Los usuarios con teléfonos **Yealink T48G/T46G** verán:</span><span class="sxs-lookup"><span data-stu-id="c1a47-177">For users with **Yealink T48G/T46G** phones, they will see:</span></span>
    
     ![Inicio de sesión de teléfonos Yealink.](../../images/3a4462ac-0c59-409e-a3bb-1451cdcc8676.png)
  
    <span data-ttu-id="c1a47-179">Usando un explorador, vaya a la dirección que se muestra en el teléfono e introduzca su nombre de usuario de Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="c1a47-179">Using a browser, navigate to the address displayed on the phone and enter your Skype for Business username.</span></span>
    
     ![Implementación de teléfonos.](../../images/7c540b85-dc37-4ce7-a077-9e3454a0efd0.png)
  
    <span data-ttu-id="c1a47-181">Introduzca el código que se muestra en el teléfono.</span><span class="sxs-lookup"><span data-stu-id="c1a47-181">Enter the code shown on the phone.</span></span>
    
     ![Implementación de teléfonos.](../../images/d6b88016-35d2-41d1-a0da-81fef34521d4.png)
  
    <span data-ttu-id="c1a47-183">Compruebe que en el sitio se muestra "**Teléfono certificado para Skype Empresarial** de [nombre del fabricante del teléfono]" y haga clic en **Continuar**.</span><span class="sxs-lookup"><span data-stu-id="c1a47-183">Verify that the site shows "[Phone Manufacturer name] **Skype for Business Certified Phone**", and click **Continue**.</span></span>
    
     ![Implementación de teléfonos.](../../images/a8252b37-4ff5-4ece-9e2a-3e05bf928299.png)
  
    <span data-ttu-id="c1a47-185">Haga clic en las credenciales de usuario o en **Usar otra cuenta**:</span><span class="sxs-lookup"><span data-stu-id="c1a47-185">Click the user's credentials or click **Use another account**:</span></span>
    
     ![Implementación de teléfonos.](../../images/8415028b-7924-4747-b639-052d9b0b961e.png)
  
    <span data-ttu-id="c1a47-187">Cuando se muestra la página siguiente, es seguro cerrar el navegador.</span><span class="sxs-lookup"><span data-stu-id="c1a47-187">Once below page is displayed, it is safe to close the browser.</span></span>
    
     ![Implementación de teléfonos.](../../images/1a873201-52fc-4a63-b7b5-e82bbd031fd2.png)
  
    > [!NOTE]
    > <span data-ttu-id="c1a47-189">Los teléfonos LPE para Skype Empresarial Online solo admiten el inicio de sesión mediante tethering USB.</span><span class="sxs-lookup"><span data-stu-id="c1a47-189">LPE phones for Skype for Business Online support sign-in through USB tethering only.</span></span> 
  
- <span data-ttu-id="c1a47-190">**Implementaciones admitidas**: la siguiente tabla muestra los tipos de autenticación compatibles con los modelos de implementación que se admiten actualmente, incluidos la integración de Exchange, la autenticación moderna con Multi-factor Authentication (MFA) y Skype Empresarial Online y local.</span><span class="sxs-lookup"><span data-stu-id="c1a47-190">**Supported deployments** The table below shows the supported authentication types for the currently supported deployment models including Exchange Integration, Modern authentication with Multi-factor Authentication (MFA), and Skype for Business Online and on-premises.</span></span>
    
|||||||
|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="c1a47-191">**Skype Empresarial**</span><span class="sxs-lookup"><span data-stu-id="c1a47-191">**Skype for Business**</span></span> <br/> |<span data-ttu-id="c1a47-192">**Exchange**</span><span class="sxs-lookup"><span data-stu-id="c1a47-192">**Exchange**</span></span> <br/> |<span data-ttu-id="c1a47-193">**Método de inicio de sesión en el teléfono**</span><span class="sxs-lookup"><span data-stu-id="c1a47-193">**Phone Sign-In method**</span></span> <br/> |<span data-ttu-id="c1a47-194">**Acceso a Skype Empresarial**</span><span class="sxs-lookup"><span data-stu-id="c1a47-194">**Skype For Business Access**</span></span> <br/> |<span data-ttu-id="c1a47-195">**Acceso a Exchange con autenticación moderna y MFA desactivados**</span><span class="sxs-lookup"><span data-stu-id="c1a47-195">**Exchange Access with Modern Auth and MFA disabled**</span></span> <br/> |<span data-ttu-id="c1a47-196">**Acceso a Exchange con autenticación moderna y MFA activados**</span><span class="sxs-lookup"><span data-stu-id="c1a47-196">**Exchange Access with Modern Auth and MFA enabled**</span></span> <br/> |
|<span data-ttu-id="c1a47-197">En línea</span><span class="sxs-lookup"><span data-stu-id="c1a47-197">Online</span></span>  <br/> |<span data-ttu-id="c1a47-198">En línea</span><span class="sxs-lookup"><span data-stu-id="c1a47-198">Online</span></span>  <br/> |<span data-ttu-id="c1a47-199">Inicio de sesión web</span><span class="sxs-lookup"><span data-stu-id="c1a47-199">Web Sign-in</span></span>  <br/> |<span data-ttu-id="c1a47-200">Sí</span><span class="sxs-lookup"><span data-stu-id="c1a47-200">Yes</span></span>  <br/> |<span data-ttu-id="c1a47-201">Sí</span><span class="sxs-lookup"><span data-stu-id="c1a47-201">Yes</span></span>  <br/> |<span data-ttu-id="c1a47-202">Sí</span><span class="sxs-lookup"><span data-stu-id="c1a47-202">Yes</span></span>  <br/> |
|<span data-ttu-id="c1a47-203">En línea</span><span class="sxs-lookup"><span data-stu-id="c1a47-203">Online</span></span>  <br/> |<span data-ttu-id="c1a47-204">En línea</span><span class="sxs-lookup"><span data-stu-id="c1a47-204">Online</span></span>  <br/> |<span data-ttu-id="c1a47-205">Nombre de usuario y contraseña</span><span class="sxs-lookup"><span data-stu-id="c1a47-205">Username/Password</span></span>  <br/> |<span data-ttu-id="c1a47-206">Sí</span><span class="sxs-lookup"><span data-stu-id="c1a47-206">Yes</span></span>  <br/> |<span data-ttu-id="c1a47-207">Sí</span><span class="sxs-lookup"><span data-stu-id="c1a47-207">Yes</span></span>  <br/> |<span data-ttu-id="c1a47-208">No</span><span class="sxs-lookup"><span data-stu-id="c1a47-208">No</span></span>  <br/> |
|<span data-ttu-id="c1a47-209">En línea</span><span class="sxs-lookup"><span data-stu-id="c1a47-209">Online</span></span>  <br/> |<span data-ttu-id="c1a47-210">Local</span><span class="sxs-lookup"><span data-stu-id="c1a47-210">On-premises</span></span>  <br/> |<span data-ttu-id="c1a47-211">Inicio de sesión web</span><span class="sxs-lookup"><span data-stu-id="c1a47-211">Web Sign-in</span></span>  <br/> |<span data-ttu-id="c1a47-212">Sí</span><span class="sxs-lookup"><span data-stu-id="c1a47-212">Yes</span></span>  <br/> |<span data-ttu-id="c1a47-213">No</span><span class="sxs-lookup"><span data-stu-id="c1a47-213">No</span></span>  <br/> |<span data-ttu-id="c1a47-214">No</span><span class="sxs-lookup"><span data-stu-id="c1a47-214">No</span></span>  <br/> |
|<span data-ttu-id="c1a47-215">En línea</span><span class="sxs-lookup"><span data-stu-id="c1a47-215">Online</span></span>  <br/> |<span data-ttu-id="c1a47-216">Local</span><span class="sxs-lookup"><span data-stu-id="c1a47-216">On-Premises</span></span>  <br/> |<span data-ttu-id="c1a47-217">Nombre de usuario y contraseña</span><span class="sxs-lookup"><span data-stu-id="c1a47-217">Username/Password</span></span>  <br/> |<span data-ttu-id="c1a47-218">Sí</span><span class="sxs-lookup"><span data-stu-id="c1a47-218">Yes</span></span>  <br/> |<span data-ttu-id="c1a47-219">Sí</span><span class="sxs-lookup"><span data-stu-id="c1a47-219">Yes</span></span>  <br/> |<span data-ttu-id="c1a47-220">No</span><span class="sxs-lookup"><span data-stu-id="c1a47-220">No</span></span>  <br/> |
|<span data-ttu-id="c1a47-221">Local</span><span class="sxs-lookup"><span data-stu-id="c1a47-221">On-premises</span></span>  <br/> |<span data-ttu-id="c1a47-222">En línea/local</span><span class="sxs-lookup"><span data-stu-id="c1a47-222">Online/On-Premises</span></span>  <br/> |<span data-ttu-id="c1a47-223">Autenticación con PIN</span><span class="sxs-lookup"><span data-stu-id="c1a47-223">Pin Authentication</span></span>  <br/> |<span data-ttu-id="c1a47-224">Sí</span><span class="sxs-lookup"><span data-stu-id="c1a47-224">Yes</span></span>  <br/> |<span data-ttu-id="c1a47-225">No</span><span class="sxs-lookup"><span data-stu-id="c1a47-225">No</span></span>  <br/> |<span data-ttu-id="c1a47-226">No</span><span class="sxs-lookup"><span data-stu-id="c1a47-226">No</span></span>  <br/> |
|<span data-ttu-id="c1a47-227">Local</span><span class="sxs-lookup"><span data-stu-id="c1a47-227">On-premises</span></span>  <br/> |<span data-ttu-id="c1a47-228">En línea/local</span><span class="sxs-lookup"><span data-stu-id="c1a47-228">Online/On-Premises</span></span>  <br/> |<span data-ttu-id="c1a47-229">Nombre de usuario y contraseña</span><span class="sxs-lookup"><span data-stu-id="c1a47-229">Username/Password</span></span>  <br/> |<span data-ttu-id="c1a47-230">Sí</span><span class="sxs-lookup"><span data-stu-id="c1a47-230">Yes</span></span>  <br/> |<span data-ttu-id="c1a47-231">Sí</span><span class="sxs-lookup"><span data-stu-id="c1a47-231">Yes</span></span>  <br/> |<span data-ttu-id="c1a47-232">N/D</span><span class="sxs-lookup"><span data-stu-id="c1a47-232">N/A</span></span>  <br/> |
|<span data-ttu-id="c1a47-233">Local</span><span class="sxs-lookup"><span data-stu-id="c1a47-233">On-premises</span></span>  <br/> |<span data-ttu-id="c1a47-234">En línea/local</span><span class="sxs-lookup"><span data-stu-id="c1a47-234">Online/On-Premises</span></span>  <br/> |<span data-ttu-id="c1a47-235">Inicio de sesión vía equipo (BTOE)</span><span class="sxs-lookup"><span data-stu-id="c1a47-235">Sign-in via PC (BTOE)</span></span>  <br/> |<span data-ttu-id="c1a47-236">Sí</span><span class="sxs-lookup"><span data-stu-id="c1a47-236">Yes</span></span>  <br/> |<span data-ttu-id="c1a47-237">Sí</span><span class="sxs-lookup"><span data-stu-id="c1a47-237">Yes</span></span>  <br/> |<span data-ttu-id="c1a47-238">N/D</span><span class="sxs-lookup"><span data-stu-id="c1a47-238">N/A</span></span>  <br/> |
   
- <span data-ttu-id="c1a47-p116">**Características de teléfono** El conjunto de características puede variar ligeramente en función de los socios del teléfono IP. Para la característica completa de configuración y para obtener más información sobre las características de cada fabricante de teléfonos, consulte [Obtener teléfonos para Skype Empresarial Online](getting-phones-for-skype-for-business-online.md).</span><span class="sxs-lookup"><span data-stu-id="c1a47-p116">**Phone features** The feature-set may slightly vary based on the IP phone partner. For complete feature set, see[Getting phones for Skype for Business Online](getting-phones-for-skype-for-business-online.md) for more information on the features for each phone manufacturer.</span></span>
    
- <span data-ttu-id="c1a47-p117">**Bloqueo del teléfono**: esta es una característica que se ha incorporado recientemente a los teléfonos certificados para Skype Empresarial como medida de protección del teléfono. Si está activada, se pedirá a los usuarios que creen un PIN después de autenticarse correctamente. Una vez creado, el teléfono se bloqueará cuando transcurra el tiempo de inactividad definido, o si el usuario bloquea manualmente el teléfono o sincroniza el bloqueo del teléfono con el de su equipo mediante la característica de emparejamiento del teléfono. Si se introduce un PIN de desbloqueo del teléfono incorrecto varias veces, el teléfono cerrará la sesión del usuario o le pedirá un código de administrador para desbloquearlo, pero esto varía en función del socio del teléfono. El PIN del usuario debe tener entre 6 y 15 dígitos.</span><span class="sxs-lookup"><span data-stu-id="c1a47-p117">**Phone-Lock** is a recently introduced feature in Skype for Business certified phones that is used to secure a phone. If enabled, users will be asked to create a PIN upon successfully authentication. Once created, phones will lock when the idle-timeout that you define expires, a user manually locks their phone, or they sync their phone-lock with their PC lock using Phone Pairing. If the phone-lock PIN is entered wrong several times, the phone will either sign the user out or require a administrator's code to unlock the phone, but this will vary from depending on the phone Partner. The user's PIN should be between 6-15 digits.</span></span>
    
    <span data-ttu-id="c1a47-p118">Puede desactivar la característica de bloqueo del teléfono para su organización (que está activada por defecto), cambiar el tiempo de espera de inactividad y elegir si los usuarios pueden hacer o no llamadas durante el bloqueo usando la configuración en banda. Consulte [Set-CsIPPhonePolicy](https://technet.microsoft.com/en-us/library/mt629497.aspx) para obtener más detalles sobre esta configuración.</span><span class="sxs-lookup"><span data-stu-id="c1a47-p118">You can disable Phone-Lock for your organization that is enabled by default, change the idle-timeout and choose if users can make phone calls while they are locked or not using inband-settings. See [Set-CsIPPhonePolicy](https://technet.microsoft.com/en-us/library/mt629497.aspx) for more details on those settings.</span></span>
    
## <a name="step-7-optional---if-you-have-device-pairing-and-better-together-over-ethernet-btoe"></a><span data-ttu-id="c1a47-248">Paso 7 (opcional): si se dispone de emparejamiento de dispositivos y Better Together over Ethernet (BToE)</span><span class="sxs-lookup"><span data-stu-id="c1a47-248">Step 7 (optional) - If you have device pairing and Better Together over Ethernet (BToE)</span></span>
<span data-ttu-id="c1a47-249"><a name="BK_BTOE"> </a></span><span class="sxs-lookup"><span data-stu-id="c1a47-249"><a name="BK_BTOE"> </a></span></span>

<span data-ttu-id="c1a47-p119">BToE es un mecanismo de emparejamiento de teléfonos para teléfonos IP de socios que empareja el teléfono del usuario con su aplicación de Skype Empresarial para Windows. BToE permite a los usuarios:</span><span class="sxs-lookup"><span data-stu-id="c1a47-p119">BToE is a phone paining mechanism for Partner IP phones that pairs user's phone with their Windows Skype for Business app. BToE enables users to:</span></span>
  
- <span data-ttu-id="c1a47-252">Iniciar sesión en el teléfono IP usando la aplicación de escritorio de Skype Empresarial (con un equipo)</span><span class="sxs-lookup"><span data-stu-id="c1a47-252">Sign-into their IP phone using their Skype for Business desktop app (using a PC).</span></span>
    
- <span data-ttu-id="c1a47-253">Sincronizar el bloqueo del teléfono con el del equipo</span><span class="sxs-lookup"><span data-stu-id="c1a47-253">Synchronize phone-lock with PC lock.</span></span>
    
- <span data-ttu-id="c1a47-254">Hacer clic para llamar</span><span class="sxs-lookup"><span data-stu-id="c1a47-254">Click to call.</span></span>
    
<span data-ttu-id="c1a47-p120">BToE se puede configurar en dos modos de funcionamiento:  *Automático*  (predeterminado) y *Manual*. También se puede habilitar (opción predeterminada) y deshabilitar para los usuarios que usen la configuración en banda de Skype Empresarial. En el modo *Manual*, los usuarios tendrán que realizar un paso adicional para emparejar sus teléfonos con la aplicación para Windows.</span><span class="sxs-lookup"><span data-stu-id="c1a47-p120">BToE can be configured to operate in 2 modes;  *Auto*  (default) and *Manual*  . It can also be enabled (default)/disabled for users using Skype for Business in-band settings. When operating in *Manual*  mode, users will have to take an additional step to pair their phone with their Windows app.</span></span>
  
 <span data-ttu-id="c1a47-258">**Para implementar BToE para los usuarios**</span><span class="sxs-lookup"><span data-stu-id="c1a47-258">**** To deploy BToE to users</span></span>
  
1. <span data-ttu-id="c1a47-259">Conecte los equipos con los teléfonos usando el puerto de los equipos.</span><span class="sxs-lookup"><span data-stu-id="c1a47-259">Connect their PC to their phone using the PC port.</span></span>
    
     ![Implementación de teléfonos.](../../images/e21d76c7-867c-4fe6-95c6-fc40c608ed0c.png)
  
2. <span data-ttu-id="c1a47-p121">Descargue el software BToE más reciente desde el sitio web del fabricante utilizando los vínculos que se ofrecen a continuación e instálelo. Para obtener una mejor experiencia de usuario, puede distribuir e instalar el software BToE usando una solución de distribución para administradores, como System Center Configuration Manager (SCCM). Para obtener ayuda sobre el uso de SCCM, consulte [Paquetes y programas en System Center Configuration Manager](https://docs.microsoft.com/en-us/sccm/apps/deploy-use/packages-and-programs).</span><span class="sxs-lookup"><span data-stu-id="c1a47-p121">Download and install the latest BToE software from the manufacturer website from the links below. For a better user experience, you can distribute and install the BToE software using an admin distribution solution such as System Center Configuration Manager (SCCM). For help using SCCM, See [Packages and programs in System Center Configuration Manager](https://docs.microsoft.com/en-us/sccm/apps/deploy-use/packages-and-programs).</span></span>
    
  - [<span data-ttu-id="c1a47-264">Sitio de descarga del software BToE de Polycom</span><span class="sxs-lookup"><span data-stu-id="c1a47-264">Polycom BToE Software Download site:</span></span>](http://www.polycom.com/voice-conferencing-solutions/microsoft-phones.html)
    
  - [<span data-ttu-id="c1a47-265">Descarga del software BToE de Yealink</span><span class="sxs-lookup"><span data-stu-id="c1a47-265">Yealink BToE Software Download</span></span>](http://www.yealink.com/products_list_10.html)
    
  - [<span data-ttu-id="c1a47-266">Descarga del software BToE de AudioCodes</span><span class="sxs-lookup"><span data-stu-id="c1a47-266">AudioCodes BToE Software Downloads</span></span>](https://www.audiocodes.com/solutions-products/solutions/skype-for-business-microsoft-teams/skype-for-business-online)
    
3. <span data-ttu-id="c1a47-267">La configuración del servidor para BToE se establece en **habilitado** y **modo automático** de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="c1a47-267">The server setting for BToE is set to Enabled and Auto mode by default, to change those settings, seeSet-CsIPPhonePolicy.</span></span> <span data-ttu-id="c1a47-268">Para cambiar esa configuración, consulte [Set-CsIPPhonePolicy](https://technet.microsoft.com/en-us/library/mt629497.aspx).</span><span class="sxs-lookup"><span data-stu-id="c1a47-268">To change those settings, see [Set-CsIPPhonePolicy](https://technet.microsoft.com/en-us/library/mt629497.aspx).</span></span>
    
> [!NOTE]
> <span data-ttu-id="c1a47-269">Actualmente BToE no es compatible con Mac ni plataformas VDI.</span><span class="sxs-lookup"><span data-stu-id="c1a47-269">BToE isn't currently supported on Mac and VDI platforms.</span></span> 
  
## <a name="related-topics"></a><span data-ttu-id="c1a47-270">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="c1a47-270">Related topics</span></span>
[<span data-ttu-id="c1a47-271">Obtener números de teléfono de servicio para Skype Empresarial y Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c1a47-271">Getting service phone numbers for Skype for Business and Microsoft Teams</span></span>](../../what-is-phone-system-in-office-365/getting-service-phone-numbers.md)

[<span data-ttu-id="c1a47-272">Esto es lo que conseguirá con el Sistema telefónico en Office 365</span><span class="sxs-lookup"><span data-stu-id="c1a47-272">Here's what you get with Phone System in Office 365</span></span>](/MicrosoftTeams/here-s-what-you-get-with-phone-system)

[<span data-ttu-id="c1a47-273">Países y regiones donde la Audioconferencia y los Planes de llamada están disponibles</span><span class="sxs-lookup"><span data-stu-id="c1a47-273">Country and region availability for Audio Conferencing and Calling Plans</span></span>](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)

  
 
