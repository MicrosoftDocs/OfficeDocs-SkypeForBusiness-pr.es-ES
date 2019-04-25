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
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: Obtenga información sobre los pasos de implementación para obtener el firmware correcto, actualizarlo si es necesario, asignar licencias y configurar las opciones de Skype para teléfonos en línea de negocio
ms.openlocfilehash: 9bc2a4754560b6d6caaed349377039c0b257936e
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32230439"
---
# <a name="deploying-skype-for-business-online-phones"></a>Implementación de teléfonos de Skype Empresarial Online

[] Esta guía de implementación le ayudará a implementar teléfonos IP para Skype Empresarial Online.
  
In all types of businesses, having a phone number allows users to make and get voice calls, and it is an important requirement to do business. Users who have phone numbers will be able to make voice calls across all Skype for Business devices including IP phones, PCs, and mobile devices. You can learn more about Skype for Business IP phones by reading [Getting phones for Skype for Business Online](getting-phones-for-skype-for-business-online.md).
  
## <a name="deployment-steps-for-ip-phones"></a>Pasos para la implementación de teléfonos IP

### <a name="step-1---download-the-manufacturers-administrator-guides-and-phone-manuals"></a>Paso 1: descargar las guías para administradores y los manuales de los teléfonos del fabricante

Antes de comenzar, es recomendable descargar las guías para administradores y los manuales de usuario de los teléfonos que proporciona el fabricante.
  
- Para los teléfonos Polycom, consulte la [Guía de implementación de Polycom](http://www.polycom.com/voice-conferencing-solutions/desktop-ip-phones.html).
    
- Para los teléfonos Yealink, vea [Skype Yealink for Business HD SIP teléfonos Solution](http://www.yealink.com/products_top_2.html).
    
- Para teléfonos AudioCodes, consulte la [Guía de administración del aprovisionamiento de AudioCodes](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/ip-phones-room-solutions).
    
### <a name="step-2---make-sure-youre-purchasing-or-migrating-a-skype-for-business-supported-ip-phone-and-firmware"></a>Paso 2: asegurarse de que los teléfonos que va a comprar o a los que va a realizar la migración son teléfonos IP compatibles con Skype Empresarial y tienen el firmware adecuado

A Skype for Business Online supported phone and firmware is compatible for Skype for Business Server as well, but the opposite isn't always true. To make sure you are buying or provisioning a supported phone and firmware, see [Getting phones for Skype for Business Online](getting-phones-for-skype-for-business-online.md).
  
### <a name="step-3---checking-that-the-right-firmware-is-installed-and-update-the-firmware-if-required"></a>Paso 3: comprobar que está instalado el firmware correcto y actualizarlo si es necesario

Check the firmware version on your phones. For:
  
- **Teléfonos Polycom VVX:** vaya a **Ajustes** > **Estado** > **Plataforma** > **Aplicación** > **Principal**.
    
- **Teléfonos Yealink:** vaya a **Estado** en la pantalla principal del teléfono.
    
- **Teléfonos AudioCodes:** desde la pantalla de inicio, vaya a **Menú** > **Estado del dispositivo** > **Versión de firmware**.
    
    > [!NOTE]
    > For remote access to phone details, refer to manufacturer administration guides. See the links above for the user guides and phone manuals. 
  
- **Teléfonos Lync Phone Edition (LPE):** desde la pantalla de inicio, vaya a **Menú** > **Información del sistema**.
    
### <a name="step-4---device-update-considerations"></a>Paso 4: consideraciones con respecto a la actualización de los dispositivos

> [!NOTE]
> Polycom firmware prior to 5.5.1.X had a manufacturer-specific device-lock mechanism that is replaced with a Skype for Business implementation "Phone-Lock." Upgrading a phone from 5.4.X.X that was secured with "Device-Lock" to 5.5.1.X with "Phone-Lock" won't inherit the PIN code from "Device-Lock," which can leave the phone unsecured. Users who have activated "Device-Lock" need to enable the following Polycom Device Profile parameter to give users control of time of upgrade (lync.deviceUpdate.popUpSK.enabled=1). 
  
Firmware updates are managed by the Skype for Business Service. Every Skype for Business certified phone's firmware is uploaded to the Skype for Business Update server, and device update is enabled on all phones by default. Depending on the inactivity time on the phone and polling intervals, phones will automatically download and install the latest certified builds. You can disable the device update settings by using the [Set-CsIPPhonePolicy](https://technet.microsoft.com/en-us/library/mt629497.aspx) cmdlet and setting the _EnableDeviceUpdate_ parameter to `false`.
  
![Implementación de teléfonos.](../../images/be727622-1924-439f-96ca-89230739db9e.png)
  
When a new firmware is available and ready for download and install, the phone will notify the user. Polycom phones will notify the user and provide them with an option to **Update** or **Postpone**.
  
![Implementación de teléfonos.](../../images/50956fa0-da0c-4085-9bb5-4a2e99aecebb.png)
  
En un teléfono Polycom, puede actualizar el firmware desde el teléfono seleccionando **ActualizaciónSw**.
  
![Implementación de teléfonos.](../../images/376c1998-6ce6-44b6-a84d-ae7d96b1c307.png)
  
También puede optar por administrar las actualizaciones de firmware usando un sistema de aprovisionamiento de nuestros socios. Para obtener información sobre la administración de los sistemas de aprovisionamiento de nuestros socios y la personalización avanzada de teléfonos, consulte las guías de administración del fabricante.
  
> [!CAUTION]
> Asegúrese de que solo tiene una autoridad de actualización de dispositivos (actualización de dispositivos en banda o un servidor de aprovisionamiento de terceros) para evitar los bucles de actualizaciones. 
  
### <a name="step-5---configuration-and-infrastructure-phone-settings"></a>Paso 5: configuración y la configuración del teléfono de infraestructura

Puede configurar las opciones y políticas más utilizadas de los teléfonos usando los cmdlets de Windows PowerShell para la administración en banda de Skype Empresarial. Consulte [Set-CsIPPhonePolicy](https://technet.microsoft.com/en-us/library/mt629497.aspx) para obtener más información sobre estos parámetros y ajustes.
  
Para la planificación de la infraestructura de red, vea [Skype Operations Framework](https://www.skypeoperationsframework.com/).
  
### <a name="step-6---preparing-for-users-to-sign-in"></a>Paso 6: preparación para que los usuarios inicien sesión

To enable users to successfully sign in to a Skype for Business Online phone and make calls, you need to make sure users are assigned the correct licenses. At a minimum, you will need to assign a Phone System license and a Calling Plan. For additional information, you can see [Skype for Business and Microsoft Teams add-on licensing](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md) and [Assign Skype for Business and Microsoft Teams licenses](../../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).
  
Puede encontrar más información acerca de los planes de llamada leyendo el [sistema telefónico y planes de llamada](/microsoftteams/calling-plan-landing-page)
  
- **Sign-in options** that are available for Online users are:
    
  - Los usuarios con los teléfonos **Polycom VVX 5XX y 6XX** verán:
    
     ![Implementación de teléfonos.](../../images/8a1ffb33-8a63-4242-bb76-d5fafb6a6472.png)
  
  - Los usuarios con los teléfonos **Yealink T48G/T46G** verán:
    
     ![Inicio de sesión de teléfonos Yealink.](../../images/2a2892ae-850d-4781-8be0-4ffb8af068c9.png)
  
    Para obtener información detallada sobre las opciones de inicio de sesión admitidas por el fabricante, vea [Introducción teléfonos de Skype para profesionales en línea](getting-phones-for-skype-for-business-online.md).
    
- **Id. de usuario**: usando el teclado del teléfono o el teclado en pantalla (si está disponible), los usuarios pueden usar el nombre de usuario y la contraseña de su organización para iniciar sesión en el teléfono. Por ejemplo, deben usar el formato UPN, como <em>amosm@contoso.com</em>  , en el nombre de usuario.
    
     ![Implementación de teléfonos.](../../images/f67fa8f4-66a5-451d-bdf2-a12daac15cb5.png)
  
    > [!NOTE]
    > La autenticación con PIN no se admite en Skype Empresarial Online con teléfonos LPE y teléfonos IP de socios. 
  
- **Using a PC** When Better Together over Ethernet (BToE) software is installed on user's PC and enabled, users can log in to their phones using the authentication window on their Windows Skype for Business App. See [Step 7 (optional) - If you have device pairing and Better Together over Ethernet (BToE)](deploying-skype-for-business-online-phones.md#BK_BTOE) for other information.
    
  > [!NOTE]
  > Los usuarios deben usar el nombre de usuario y la contraseña de su organización para iniciar sesión en el teléfono. Por ejemplo, deben usar el formato UPN, como  <em>amosm@contoso.com</em>  , en el nombre de usuario.
  
     ![Implementación de teléfonos.](../../images/f67fa8f4-66a5-451d-bdf2-a12daac15cb5.png)
  
- **Using a Web Sign-in**: This is a new way for Online users to authenticate using a standard web browser. Users will be provided with a set of instructions to follow when they use a browser to sign in.
    
  - Los usuarios con los teléfonos **Polycom VVX 5XX y 6XX** verán:
    
     ![Implementación de teléfonos.](../../images/ba0df923-a6e5-4a9b-b40b-b03ca188e814.png)
  
  - Los usuarios con los teléfonos **Yealink T48G/T46G** verán:
    
     ![Inicio de sesión de teléfonos Yealink.](../../images/86551cc3-533a-4694-9683-bad907c9ad5a.png)
  
    The code that is generated will expire in 15 minutes. When it expires, the user will have to click **Retry** or **OK** to generate a new code, depending on the phone.
    
  - Los usuarios con los teléfonos **Polycom VVX 5XX y 6XX** verán:
    
     ![El código PIN ha caducado.](../../images/b5d27037-aa26-4054-be95-d5a6c293d08c.png)
  
  - Los usuarios con los teléfonos **Yealink T48G/T46G** verán:
    
     ![Inicio de sesión de teléfonos Yealink.](../../images/3a4462ac-0c59-409e-a3bb-1451cdcc8676.png)
  
    Usando un explorador, vaya a la dirección que se muestra en el teléfono e introduzca su nombre de usuario de Skype Empresarial.
    
     ![Implementación de teléfonos.](../../images/7c540b85-dc37-4ce7-a077-9e3454a0efd0.png)
  
    Introduzca el código que se muestra en el teléfono.
    
     ![Implementación de teléfonos.](../../images/d6b88016-35d2-41d1-a0da-81fef34521d4.png)
  
    Compruebe que el sitio muestra "[nombre del fabricante del teléfono] **Skype para teléfono del trabajo certificada**," y haga clic en **continuar**.
    
     ![Implementación de teléfonos.](../../images/a8252b37-4ff5-4ece-9e2a-3e05bf928299.png)
  
    Haga clic en las credenciales de usuario o en **Usar otra cuenta**:
    
     ![Implementación de teléfonos.](../../images/8415028b-7924-4747-b639-052d9b0b961e.png)
  
    Cuando se muestra la página siguiente, es segura cerrar el explorador.
    
     ![Implementación de teléfonos.](../../images/1a873201-52fc-4a63-b7b5-e82bbd031fd2.png)
  
    > [!NOTE]
    > Los teléfonos LPE para Skype Empresarial Online solo admiten el inicio de sesión mediante tethering USB. 
  
- **Implementaciones admitidas**: la siguiente tabla muestra los tipos de autenticación compatibles con los modelos de implementación que se admiten actualmente, incluidos la integración de Exchange, la autenticación moderna con Multi-factor Authentication (MFA) y Skype Empresarial Online y local.
    
|||||||
|:-----|:-----|:-----|:-----|:-----|:-----|
|**Skype Empresarial** <br/> |**Exchange** <br/> |**Método de inicio de sesión en el teléfono** <br/> |**Skype para el acceso de negocio** <br/> |**Acceso a Exchange con autenticación moderna y MFA desactivados** <br/> |**Acceso a Exchange con autenticación moderna y MFA activados** <br/> |
|En línea  <br/> |En línea  <br/> |Inicio de sesión web  <br/> |Sí  <br/> |Sí  <br/> |Sí  <br/> |
|En línea  <br/> |En línea  <br/> |Nombre de usuario y contraseña  <br/> |Sí  <br/> |Sí  <br/> |No  <br/> |
|En línea  <br/> |Local  <br/> |Inicio de sesión web  <br/> |Sí  <br/> |No  <br/> |No  <br/> |
|En línea  <br/> |Local  <br/> |Nombre de usuario y contraseña  <br/> |Sí  <br/> |Sí  <br/> |No  <br/> |
|Local  <br/> |En línea/local  <br/> |Autenticación de PIN  <br/> |Sí  <br/> |No  <br/> |No  <br/> |
|Local  <br/> |En línea/local  <br/> |Nombre de usuario y contraseña  <br/> |Sí  <br/> |Sí  <br/> |N/D  <br/> |
|Local  <br/> |En línea/local  <br/> |Inicio de sesión vía equipo (BTOE)  <br/> |Sí  <br/> |Sí  <br/> |N/D  <br/> |
   
- **Phone features** The feature set may vary slightly based on the IP phone partner. For the complete feature set and for more information on the features for each phone manufacturer, see [Getting phones for Skype for Business Online](getting-phones-for-skype-for-business-online.md).
    
- **Phone-Lock** is a recently introduced feature in Skype for Business certified phones that is used to secure a phone. If enabled, users will be asked to create a PIN upon successful authentication. Once created, phones will lock when the idle-timeout that you define expires, a user manually locks their phone, or they sync their phone-lock with their PC lock using Phone Pairing. If the phone-lock PIN is entered wrong several times, the phone will either sign the user out or require an administrator's code to unlock the phone, but this will vary depending on the phone partner. The user's PIN should be between 6 and 15 digits.
    
    You can disable Phone-Lock for your organization (which is enabled by default), change the idle-timeout, and choose whether users can make phone calls while they are locked or not using inband-settings. Para obtener más información acerca de la configuración, consulte [Set-CsUCPhoneConfiguration](https://technet.microsoft.com/en-us/library/mt629497.aspx) .
    
## <a name="step-7-optional---if-you-have-device-pairing-and-better-together-over-ethernet-btoe"></a>Paso 7 (opcional): si se dispone de emparejamiento de dispositivos y Better Together over Ethernet (BToE)
<a name="BK_BTOE"> </a>

BToE is a phone paining mechanism for Partner IP phones that pairs a user's phone with their Windows Skype for Business app. BToE enables users to:
  
- Inicie sesión en su teléfono IP con su Skype para la aplicación de escritorio empresarial (mediante un PC)
    
- Sincronizar el bloqueo del teléfono con bloqueo de PC
    
- Hacer clic para llamar
    
BToE can be configured to operate in two modes:  *Auto*  (default) and *Manual*  . It can also be enabled (default)/disabled for users using Skype for Business in-band settings. When operating in *Manual*  mode, users will have to take an additional step to pair their phone with their Windows app.
  
 **Para implementar BToE a los usuarios**
  
1. Conecte los equipos con los teléfonos usando el puerto de los equipos.
    
     ![Implementación de teléfonos.](../../images/e21d76c7-867c-4fe6-95c6-fc40c608ed0c.png)
  
2. Descargue el software BToE más reciente desde el sitio web del fabricante utilizando los vínculos que se ofrecen a continuación e instálelo. Para obtener una mejor experiencia de usuario, puede distribuir e instalar el software BToE usando una solución de distribución para administradores, como System Center Configuration Manager (SCCM). Para obtener ayuda sobre el uso de SCCM, consulte [Paquetes y programas en System Center Configuration Manager](https://docs.microsoft.com/sccm/apps/deploy-use/packages-and-programs).
    
   - [Sitio de descarga de Software de Polycom BToE](http://www.polycom.com/voice-conferencing-solutions/microsoft-phones.html)
    
   - [Descarga del software BToE de Yealink](http://www.yealink.com/products_list_10.html)
    
   - [Descarga del software BToE de AudioCodes](https://www.audiocodes.com/solutions-products/solutions/skype-for-business-microsoft-teams/skype-for-business-online)
    
3. The server setting for BToE is set to **Enabled** and **Auto mode** by default. To change those settings, see [Set-CsIPPhonePolicy](https://technet.microsoft.com/en-us/library/mt629497.aspx).
    
> [!NOTE]
> Actualmente BToE no es compatible con Mac ni plataformas VDI. 
  
## <a name="related-topics"></a>Temas relacionados
[Obtener números de teléfono de servicio para Skype Empresarial y Microsoft Teams](../../what-is-phone-system-in-office-365/getting-service-phone-numbers.md)

[Esto es lo obtiene con el Sistema telefónico de Office 365](/MicrosoftTeams/here-s-what-you-get-with-phone-system)

[Países y regiones donde Audioconferencia y Planes de llamada están disponibles](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)

  
 
