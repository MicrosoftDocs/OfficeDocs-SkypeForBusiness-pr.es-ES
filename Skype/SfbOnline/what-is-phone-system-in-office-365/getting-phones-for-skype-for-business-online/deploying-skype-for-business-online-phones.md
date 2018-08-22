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
# <a name="deploying-skype-for-business-online-phones"></a>Implementación de teléfonos de Skype Empresarial Online

[] Esta guía de implementación le ayudará a implementar teléfonos IP para Skype Empresarial Online.
  
En todos los tipos de empresas, tener un número de teléfono permite a los usuarios realizar y recibir llamadas de voz y es un requisito importante para hacer negocios. Los usuarios que tienen los números de teléfono podrán realizar llamadas de voz entre todos los Skype para dispositivos de negocio incluidos los teléfonos IP, equipos y dispositivos móviles. Puede obtener más acerca de Skype para teléfonos IP de negocio mediante la lectura de [teléfonos de introducción de Skype para profesionales en línea](getting-phones-for-skype-for-business-online.md).
  
## <a name="deployment-steps-for-ip-phones"></a>Pasos para la implementación de teléfonos IP

### <a name="step-1---download-the-manufacturers-administrator-guides-and-phone-manuals"></a>Paso 1: descargar las guías para administradores y los manuales de los teléfonos del fabricante

Antes de comenzar, es recomendable descargar las guías para administradores y los manuales de usuario de los teléfonos que proporciona el fabricante.
  
- Para los teléfonos Polycom, vea la [Guía de implementación de Polycom] ((http://www.polycom.com/voice-conferencing-solutions/desktop-ip-phones.html).
    
- Para los teléfonos Yealink, vea [Skype Yealink for Business HD SIP teléfonos Solution](http://www.yealink.com/products_top_2.html).
    
- Para teléfonos AudioCodes, consulte la [Guía de administración del aprovisionamiento de AudioCodes](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/ip-phones-room-solutions).
    
### <a name="step-2---make-sure-youre-purchasing-or-migrating-a-skype-for-business-supported-ip-phone-and-firmware"></a>Paso 2: asegurarse de que los teléfonos que va a comprar o a los que va a realizar la migración son teléfonos IP compatibles con Skype Empresarial y tienen el firmware adecuado

Los teléfonos y el firmware compatibles con Skype Empresarial Online también lo son con Skype Empresarial Server, pero no siempre sucede lo mismo a la inversa. Para asegurarse de que se compra o un teléfono admitido y el firmware de aprovisionamiento, vea [Introducción teléfonos de Skype para profesionales en línea](getting-phones-for-skype-for-business-online.md).
  
### <a name="step-3---checking-that-the-right-firmware-is-installed-and-update-the-firmware-if-required"></a>Paso 3: comprobar que está instalado el firmware correcto y actualizarlo si es necesario

Comprobar la versión de firmware en los teléfonos. Para:
  
- **Teléfonos Polycom VVX:** vaya a **Ajustes** > **Estado** > **Plataforma** > **Aplicación** > **Principal**.
    
- **Teléfonos Yealink:** vaya a **Estado** en la pantalla principal del teléfono.
    
- **Teléfonos AudioCodes:** desde la pantalla de inicio, vaya a **Menú** > **Estado del dispositivo** > **Versión de firmware**.
    
    > [!NOTE]
    > Para el acceso remoto a los detalles de teléfono, hacer referencia a las guías de administración del fabricante. Vea los vínculos por encima de las guías de usuario y manuales de teléfono. 
  
- **Teléfonos Lync Phone Edition (LPE):** desde la pantalla de inicio, vaya a **Menú** > **Información del sistema**.
    
### <a name="step-4---device-update-considerations"></a>Paso 4: consideraciones con respecto a la actualización de los dispositivos

> [!NOTE]
> Firmware Polycom antes de 5.5.1.X tenía un mecanismo de bloqueo de dispositivos específicos del fabricante que se ha reemplazado con un Skype para la implementación empresarial "-bloqueo del teléfono." Actualización de un teléfono de 5.4.X.X que estaba protegida con "Bloqueo de dispositivo" a 5.5.1.X con "Bloqueo del teléfono" no hereda el código PIN de "Dispositivo de bloqueo," que puede dejar el teléfono no seguro. Los usuarios que se han activado "Bloqueo de dispositivo" necesitan habilitar el siguiente parámetro Polycom Device Profile ofrecer a los usuarios de control de tiempo de actualización (lync.deviceUpdate.popUpSK.enabled=1). 
  
Las actualizaciones de firmware las administra el servicio de Skype for Business. Todos los firmware de teléfono certificados para Skype for Business se cargan en el servidor de actualización de Skype for Business, y la actualización del dispositivo está habilitada en todos los teléfonos de forma predeterminada. En función del tiempo de inactividad del teléfono y de los intervalos de sondeo, los teléfonos descargarán e instalarán automáticamente las últimas compilaciones certificadas. Puede deshabilitar la configuración de actualización de dispositivo mediante el cmdlet [Set-CsIPPhonePolicy](https://technet.microsoft.com/en-us/library/mt629497.aspx) y establecer el parámetro _EnableDeviceUpdate_ en `false`.
  
![Deploying phones.](../../images/be727622-1924-439f-96ca-89230739db9e.png)
  
Cuando un nuevo firmware está disponible y listo para descargar e instalar, el teléfono notificará al usuario. Los teléfonos Polycom va a notificar al usuario y proporcionar con una opción para **Actualizar** o **Posponer**.
  
![Deploying phones.](../../images/50956fa0-da0c-4085-9bb5-4a2e99aecebb.png)
  
En un teléfono Polycom, puede actualizar el firmware desde el teléfono seleccionando **ActualizaciónSw**.
  
![Deploying phones.](../../images/376c1998-6ce6-44b6-a84d-ae7d96b1c307.png)
  
También puede optar por administrar las actualizaciones de firmware usando un sistema de aprovisionamiento de nuestros socios. Para obtener información sobre la administración de los sistemas de aprovisionamiento de nuestros socios y la personalización avanzada de teléfonos, consulte las guías de administración del fabricante.
  
> [!CAUTION]
> Asegúrese de que solo tiene una autoridad de actualización de dispositivos (actualización de dispositivos en banda o un servidor de aprovisionamiento de terceros) para evitar los bucles de actualizaciones. 
  
### <a name="step-5---configuration-and-infrastructure-phone-settings"></a>Paso 5: configuración y la configuración del teléfono de infraestructura

Puede configurar las opciones y políticas más utilizadas de los teléfonos usando los cmdlets de Windows PowerShell para la administración en banda de Skype Empresarial. Consulte [Set-CsIPPhonePolicy](https://technet.microsoft.com/en-us/library/mt629497.aspx) para obtener más información sobre estos parámetros y ajustes.
  
Para la planificación de la infraestructura de red, vea [Skype Operations Framework](https://www.skypeoperationsframework.com/).
  
### <a name="step-6---preparing-for-users-to-sign-in"></a>Paso 6: preparación para que los usuarios inicien sesión

Para habilitar a los usuarios iniciar sesión en un Skype para teléfono empresarial en línea correctamente y realizar llamadas, necesitará para asegurarse de que los usuarios se asignan las licencias correctas. Como mínimo, debe asignar una licencia de sistema telefónico y un Plan de llamada. Para obtener información adicional, puede ver [Skype para profesionales y los equipos de Microsoft complemento licencias](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md) y [Asignar Skype para licencias de negocio y equipos de Microsoft](../../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).
  
Puede encontrar más información acerca de los planes de llamada mediante la lectura de [¿Cuáles son los planes de llamada en Office 365?](../../what-are-calling-plans-in-office-365/what-are-calling-plans-in-office-365.md)
  
- Las ** opciones de inicio de sesión** disponibles para los usuarios en línea son:
    
  - Los usuarios con los teléfonos **Polycom VVX 5XX y 6XX** verán:
    
     ![Deploying phones.](../../images/8a1ffb33-8a63-4242-bb76-d5fafb6a6472.png)
  
  - Los usuarios con los teléfonos **Yealink T48G/T46G** verán:
    
     ![Yealink phones logon.](../../images/2a2892ae-850d-4781-8be0-4ffb8af068c9.png)
  
    Para obtener información detallada sobre las opciones de inicio de sesión admitidas por el fabricante, vea [Introducción teléfonos de Skype para profesionales en línea](getting-phones-for-skype-for-business-online.md).
    
- **Id. de usuario**: usando el teclado del teléfono o el teclado en pantalla (si está disponible), los usuarios pueden usar el nombre de usuario y la contraseña de su organización para iniciar sesión en el teléfono. Por ejemplo, deben usar el formato UPN, como *amosm@contoso.com*  , en el nombre de usuario.
    
     ![Deploying phones.](../../images/f67fa8f4-66a5-451d-bdf2-a12daac15cb5.png)
  
    > [!NOTE]
    > La autenticación con PIN no se admite en Skype Empresarial Online con teléfonos LPE y teléfonos IP de socios. 
  
- **Uso de un PC** Cuando se Better Together a través de software de Ethernet (BToE) está instalado en el PC del usuario y habilitado, los usuarios pueden iniciar sesión a sus teléfonos mediante la ventana de autenticación en sus Skype de Windows para la aplicación empresarial de. Para obtener más información, vea [paso 7 (opcional) - si tiene el apareamiento de dispositivo y mejor juntos a través de Ethernet (BToE)](deploying-skype-for-business-online-phones.md#BK_BTOE) .
    
    > [!NOTE]
    > Los usuarios deben usar el nombre de usuario y la contraseña de su organización para iniciar sesión en el teléfono. Por ejemplo, deben usar el formato UPN, como  *amosm@contoso.com*  , en el nombre de usuario.
  
     ![Deploying phones.](../../images/f67fa8f4-66a5-451d-bdf2-a12daac15cb5.png)
  
- **Uso de un inicio de sesión en Web**: Esto es una forma nueva para los usuarios en línea que se autentiquen mediante un explorador web estándar. Se proporcionará a los usuarios con un conjunto de instrucciones que se deben seguir al usar un explorador para iniciar sesión.
    
  - Los usuarios con los teléfonos **Polycom VVX 5XX y 6XX** verán:
    
     ![Deploying phones.](../../images/ba0df923-a6e5-4a9b-b40b-b03ca188e814.png)
  
  - Los usuarios con los teléfonos **Yealink T48G/T46G** verán:
    
     ![Yealink phone logon.](../../images/86551cc3-533a-4694-9683-bad907c9ad5a.png)
  
    El código que se genera caducará en 15 minutos. Cuando expira, el usuario tendrá que hacer clic en **Reintentar** o en **Aceptar** para generar un nuevo código, en función del teléfono.
    
  - Los usuarios con los teléfonos **Polycom VVX 5XX y 6XX** verán:
    
     ![PIN code expired.](../../images/b5d27037-aa26-4054-be95-d5a6c293d08c.png)
  
  - Los usuarios con los teléfonos **Yealink T48G/T46G** verán:
    
     ![Yealink phones logon.](../../images/3a4462ac-0c59-409e-a3bb-1451cdcc8676.png)
  
    Usando un explorador, vaya a la dirección que se muestra en el teléfono e introduzca su nombre de usuario de Skype Empresarial.
    
     ![Deploying phones.](../../images/7c540b85-dc37-4ce7-a077-9e3454a0efd0.png)
  
    Introduzca el código que se muestra en el teléfono.
    
     ![Deploying phones.](../../images/d6b88016-35d2-41d1-a0da-81fef34521d4.png)
  
    Compruebe que el sitio muestra "[nombre del fabricante del teléfono] **Skype para teléfono del trabajo certificada**," y haga clic en **continuar**.
    
     ![Deploying phones.](../../images/a8252b37-4ff5-4ece-9e2a-3e05bf928299.png)
  
    Haga clic en las credenciales de usuario o en **Usar otra cuenta**:
    
     ![Deploying phones.](../../images/8415028b-7924-4747-b639-052d9b0b961e.png)
  
    Cuando se muestra la página siguiente, es segura cerrar el explorador.
    
     ![Deploying phones.](../../images/1a873201-52fc-4a63-b7b5-e82bbd031fd2.png)
  
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
   
- **Características de teléfono** El conjunto de características puede variar ligeramente en función de los socios de teléfono IP. Para la característica completa establece y para obtener más información sobre las características para cada fabricante del teléfono, vea [Introducción teléfonos de Skype para profesionales en línea](getting-phones-for-skype-for-business-online.md).
    
- **Bloqueo del teléfono**: esta es una característica que se ha incorporado a los teléfonos certificados para Skype Empresarial recientemente como medida de protección del teléfono. Si se habilita, los usuarios le pedirá que cree un PIN tras la autenticación. Una vez creado, el teléfono se bloqueará cuando transcurra el tiempo de inactividad definido, o si el usuario bloquea manualmente el teléfono o sincroniza el bloqueo del teléfono con el de su equipo mediante la característica de emparejamiento del teléfono. Si el PIN de bloqueo del teléfono se escribe mal varias veces, el teléfono se cierre la sesión del usuario o requieren código de un administrador para desbloquear el teléfono, pero esto variará en función del socio de teléfono. El PIN del usuario debe estar comprendido entre 6 y 15 dígitos.
    
    Puede deshabilitar el bloqueo del teléfono para la organización (que está habilitada de forma predeterminada), cambiar el tiempo de espera de inactividad y elija si los usuarios pueden realizar llamadas telefónicas mientras están bloqueados o no utiliza configuración de banda. Consulte [Set-CsIPPhonePolicy](https://technet.microsoft.com/en-us/library/mt629497.aspx) para obtener más detalles sobre esta configuración.
    
## <a name="step-7-optional---if-you-have-device-pairing-and-better-together-over-ethernet-btoe"></a>Paso 7 (opcional): si se dispone de emparejamiento de dispositivos y Better Together over Ethernet (BToE)
<a name="BK_BTOE"> </a>

BToE es un teléfono paining mecanismo para teléfonos IP de socio que pares de teléfono de un usuario con sus Skype de Windows para la aplicación empresarial. BToE permite a los usuarios:
  
- Inicie sesión en su teléfono IP con su Skype para la aplicación de escritorio empresarial (mediante un PC)
    
- Sincronizar el bloqueo del teléfono con bloqueo de PC
    
- Hacer clic para llamar
    
BToE puede configurarse para funcionar en dos modos: *Manual* y *automático* (valor predeterminado). También se puede activar (opción predeterminada) y desactivar para los usuarios con configuración en banda de Skype Empresarial. En el modo *Manual*  , los usuarios tendrán que realizar un paso adicional para emparejar sus teléfonos con la aplicación para Windows.
  
 **Para implementar BToE a los usuarios**
  
1. Conecte los equipos con los teléfonos usando el puerto de los equipos.
    
     ![Deploying phones.](../../images/e21d76c7-867c-4fe6-95c6-fc40c608ed0c.png)
  
2. Descargue el software BToE más reciente desde el sitio web del fabricante utilizando los vínculos que se ofrecen a continuación e instálelo. Para obtener una mejor experiencia de usuario, puede distribuir e instalar el software BToE usando una solución de distribución para administradores, como System Center Configuration Manager (SCCM). Para obtener ayuda sobre el uso de SCCM, consulte [Paquetes y programas en System Center Configuration Manager](https://docs.microsoft.com/en-us/sccm/apps/deploy-use/packages-and-programs).
    
  - [Sitio de descarga de Software de Polycom BToE](http://www.polycom.com/voice-conferencing-solutions/microsoft-phones.html)
    
  - [Descarga del software BToE de Yealink](http://www.yealink.com/products_list_10.html)
    
  - [Descarga del software BToE de AudioCodes](https://www.audiocodes.com/solutions-products/solutions/skype-for-business-microsoft-teams/skype-for-business-online)
    
3. La configuración del servidor para BToE se establece en **habilitado** y **el modo automático** de forma predeterminada. Para cambiar esa configuración, vea [Set-CsIPPhonePolicy](https://technet.microsoft.com/en-us/library/mt629497.aspx).
    
> [!NOTE]
> Actualmente BToE no es compatible con Mac ni plataformas VDI. 
  
## <a name="related-topics"></a>Temas relacionados
[Obtener números de teléfono de servicio para Skype Empresarial y Microsoft Teams](../../what-is-phone-system-in-office-365/getting-service-phone-numbers.md)

[Esto es lo que conseguirá con Sistema telefónico en Office 365](../../what-is-phone-system-in-office-365/here-s-what-you-get-with-phone-system.md)

[Países y regiones donde Audioconferencia y Planes de llamada están disponibles](../../country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

  
 
