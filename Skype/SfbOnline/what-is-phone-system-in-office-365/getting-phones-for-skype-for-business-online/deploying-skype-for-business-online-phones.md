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
f1.keywords:
- NOCSH
ms.custom:
- Phone System
description: Obtenga información sobre los pasos de implementación para obtener el firmware correcto, actualizarlo si es necesario, asignar licencias y configurar la configuración para Skype Empresarial teléfonos en línea
ms.openlocfilehash: 1c607f0dd5c3a82c744f26432fe1c65f31263440
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/06/2021
ms.locfileid: "52237376"
---
# <a name="deploying-skype-for-business-online-phones"></a>Implementación de teléfonos de Skype Empresarial Online

[!INCLUDE [sfbo-retirement](../../../Hub/includes/sfbo-retirement.md)]

[] Esta guía de implementación le ayudará a implementar teléfonos IP para Skype Empresarial Online.
  
En todo tipo de empresas, tener un número de teléfono permite a los usuarios realizar y recibir llamadas de voz, y es un requisito importante para hacer negocios. Los usuarios que tengan números de teléfono podrán realizar llamadas de voz en todos los dispositivos Skype Empresarial, incluidos teléfonos IP, EQUIPOS y dispositivos móviles. Para obtener más información sobre cómo Skype Empresarial teléfonos IP, lea Obtener [teléfonos para Skype Empresarial en línea.](getting-phones-for-skype-for-business-online.md)
  
## <a name="deployment-steps-for-ip-phones"></a>Pasos para la implementación de teléfonos IP

### <a name="step-1---download-the-manufacturers-administrator-guides-and-phone-manuals"></a>Paso 1: descargar las guías para administradores y los manuales de los teléfonos del fabricante

Antes de comenzar, es recomendable descargar las guías para administradores y los manuales de usuario de los teléfonos que proporciona el fabricante.
  
- Para teléfonos Polycom, vea la [Biblioteca de documentación poly.](https://documents.polycom.com/category/voice)
    
- Para teléfonos Yealink, vea [Yealink Skype Empresarial solución de teléfonos SIP HD.](http://www.yealink.com/products_top_2.html)
    
- Para teléfonos AudioCodes, consulte la [Guía de administración del aprovisionamiento de AudioCodes](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/ip-phones-room-solutions).
    
### <a name="step-2---make-sure-youre-purchasing-or-migrating-a-skype-for-business-supported-ip-phone-and-firmware"></a>Paso 2: asegurarse de que los teléfonos que va a comprar o a los que va a realizar la migración son teléfonos IP compatibles con Skype Empresarial y tienen el firmware adecuado

Los teléfonos y el firmware compatibles con Skype Empresarial Online también lo son con Skype Empresarial Server, pero no siempre sucede lo mismo a la inversa. Para asegurarse de que está comprando o aprovisionando un teléfono y un firmware compatibles, vea Obtener [teléfonos para Skype Empresarial En línea.](getting-phones-for-skype-for-business-online.md)
  
### <a name="step-3---checking-that-the-right-firmware-is-installed-and-update-the-firmware-if-required"></a>Paso 3: comprobar que está instalado el firmware correcto y actualizarlo si es necesario

Comprueba la versión de firmware de tus teléfonos. Para:
  
- **Teléfonos Polycom VVX:** vaya a **Ajustes** > **Estado** > **Plataforma** > **Aplicación** > **Principal**.
    
- **Teléfonos Yealink:** vaya a **Estado** en la pantalla principal del teléfono.
    
- **Teléfonos AudioCodes:** desde la pantalla de inicio, vaya a **Menú** > **Estado del dispositivo** > **Versión de firmware**.
    
    > [!NOTE]
    > Para obtener acceso remoto a los detalles del teléfono, consulte guías de administración del fabricante. Consulte los enlaces anteriores para acceder a las guías de usuario y los manuales de los teléfonos. 
  
- **Teléfonos Lync Phone Edition (LPE):** desde la pantalla de inicio, vaya a **Menú** > **Información del sistema**.
    
### <a name="step-4---device-update-considerations"></a>Paso 4: consideraciones con respecto a la actualización de los dispositivos

> [!NOTE]
> El firmware polycom anterior a la 5.5.1.X tenía un mecanismo de bloqueo de dispositivo específico del fabricante que se reemplaza por una implementación Skype Empresarial "Teléfono-Lock". Actualizar un teléfono de 5.4.X.X que estaba protegido con "Bloqueo de dispositivo" a 5.5.1.X con "Teléfono-Lock" no heredará el código PIN de "Bloqueo de dispositivo", lo que puede dejar el teléfono sin seguridad. Los usuarios que han activado "Bloqueo de dispositivo" necesitan habilitar el siguiente parámetro de perfil de dispositivo Polycom para proporcionar a los usuarios el control del tiempo de actualización (lync.deviceUpdate.popUpSK.enabled=1). 
  
Las actualizaciones de firmware las administra el servicio de Skype for Business. Todos los firmware de teléfono certificados para Skype for Business se cargan en el servidor de actualización de Skype for Business, y la actualización del dispositivo está habilitada en todos los teléfonos de forma predeterminada. En función del tiempo de inactividad del teléfono y de los intervalos de sondeo, los teléfonos descargarán e instalarán automáticamente las últimas compilaciones certificadas. Puede deshabilitar la configuración de actualización del dispositivo mediante el cmdlet [Set-CsIPPhonePolicy](/powershell/module/skype/Set-CsIPPhonePolicy) y estableciendo el _parámetro EnableDeviceUpdate_ en `false` .
  
![Captura de pantalla que muestra la implementación de teléfonos](../../images/be727622-1924-439f-96ca-89230739db9e.png)
  
Cuando haya un nuevo firmware disponible y preparado para la descarga y la instalación, el teléfono notificará al usuario. Los teléfonos Polycom notificarán al usuario y les proporcionarán una opción para **Actualizar** o **Posponer.**
  
![Captura de pantalla que muestra las opciones Actualizar y Posponer.](../../images/50956fa0-da0c-4085-9bb5-4a2e99aecebb.png)
  
En un teléfono Polycom, puede actualizar el firmware desde el teléfono seleccionando **ActualizaciónSw**.
  
![Captura de pantalla que muestra la opción SwUpdate](../../images/376c1998-6ce6-44b6-a84d-ae7d96b1c307.png)
  
También puede optar por administrar las actualizaciones de firmware usando un sistema de aprovisionamiento de nuestros socios. Para obtener información sobre la administración de los sistemas de aprovisionamiento de nuestros socios y la personalización avanzada de teléfonos, consulte las guías de administración del fabricante.
  
> [!CAUTION]
> Asegúrese de que solo tiene una autoridad de actualización de dispositivos (actualización de dispositivos en banda o un servidor de aprovisionamiento de terceros) para evitar los bucles de actualizaciones. 
  
### <a name="step-5---configuration-and-infrastructure-phone-settings"></a>Paso 5: configuración e infraestructura del teléfono

Puede configurar las opciones y políticas más utilizadas de los teléfonos usando los cmdlets de Windows PowerShell para la administración en banda de Skype Empresarial. Consulte [Set-CsIPPhonePolicy](/powershell/module/skype/Set-CsIPPhonePolicy) para obtener más información sobre estos parámetros y ajustes.
  
Para obtener información sobre la planificación de infraestructura [de red, vea Skype Operations Framework](https://www.skypeoperationsframework.com/).
  
### <a name="step-6---preparing-for-users-to-sign-in"></a>Paso 6: Preparación para que los usuarios inicien sesión

Para permitir que los usuarios inicien sesión correctamente en un teléfono Skype Empresarial Online y realicen llamadas, debe asegurarse de que los usuarios tienen asignadas las licencias correctas. Como mínimo, tendrá que asignar una licencia de Sistema telefónico y un plan de llamadas. Para obtener más información, puede ver Skype Empresarial y [Microsoft Teams](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md) de complementos y Asignar Skype Empresarial y [Microsoft Teams licencias.](../../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)
  
Para obtener más información sobre planes de llamadas, lea [Sistema telefónico planes de llamadas](/microsoftteams/calling-plan-landing-page)
  
- **Sign-in options** that are available for Online users are:
    
  - Los usuarios **con teléfonos Polycom VVX 5XX/6XX** verán:
    
     ![Captura de pantalla que muestra el inicio de sesión de teléfonos Polycom](../../images/8a1ffb33-8a63-4242-bb76-d5fafb6a6472.png)
  
  - Los usuarios **con teléfonos Yealink T48G/T46G** verán:
    
     ![Captura de pantalla que muestra el inicio de sesión de los teléfonos Yealink.](../../images/2a2892ae-850d-4781-8be0-4ffb8af068c9.png)
  
    Para obtener información detallada sobre las opciones de inicio de sesión admitidas por el fabricante, vea Obtener [teléfonos para Skype Empresarial en línea.](getting-phones-for-skype-for-business-online.md)
    
- **Id. de usuario**: usando el teclado del teléfono o el teclado en pantalla (si está disponible), los usuarios pueden usar el nombre de usuario y la contraseña de su organización para iniciar sesión en el teléfono. Por ejemplo, deben usar el formato UPN, como <em>amosm@contoso.com</em>  , en el nombre de usuario.
    
     ![Captura de pantalla que muestra la pantalla de inicio de sesión](../../images/f67fa8f4-66a5-451d-bdf2-a12daac15cb5.png)
  
    > [!NOTE]
    > La autenticación con PIN no se admite en Skype Empresarial Online con teléfonos LPE y teléfonos IP de socios. 
  
- **Usar un EQUIPO** Cuando el software Better Together over Ethernet (BToE) está instalado en el equipo del usuario y está habilitado, los usuarios pueden iniciar sesión en sus teléfonos con la ventana de autenticación en su Windows Skype Empresarial aplicación. Vea Paso 7 (opcional): si tiene emparejamiento de dispositivos y [Better Together over Ethernet (BToE)](deploying-skype-for-business-online-phones.md#BK_BTOE) para obtener más información.
    
  > [!NOTE]
  > Los usuarios deben usar el nombre de usuario y la contraseña de su organización para iniciar sesión en el teléfono. Por ejemplo, deben usar el formato UPN, como  <em>amosm@contoso.com</em>  , en el nombre de usuario.
  
     ![Captura de pantalla que muestra la pantalla de inicio de sesión](../../images/f67fa8f4-66a5-451d-bdf2-a12daac15cb5.png)
  
- **Usar un inicio de sesión web:** esta es una nueva forma de que los usuarios en línea se autentiquen con un explorador web estándar. Los usuarios recibirán un conjunto de instrucciones para seguir cuando usen un explorador para iniciar sesión.
    
  - Los usuarios **con teléfonos Polycom VVX 5XX/6XX** verán:
    
     ![Captura de pantalla que muestra las instrucciones de Polycom](../../images/ba0df923-a6e5-4a9b-b40b-b03ca188e814.png)
  
  - Los usuarios **con teléfonos Yealink T48G/T46G** verán:
    
     ![Captura de pantalla que muestra instrucciones de Yealink](../../images/86551cc3-533a-4694-9683-bad907c9ad5a.png)
  
    El código que se genera expira en 15 minutos. Cuando expire, el usuario tendrá que hacer clic en **Reintentar** o **Aceptar** para generar un código nuevo, según el teléfono.
    
  - Los usuarios **con teléfonos Polycom VVX 5XX/6XX** verán:
    
     ![Captura de pantalla que muestra el código Polycom expirado](../../images/b5d27037-aa26-4054-be95-d5a6c293d08c.png)
  
  - Los usuarios **con teléfonos Yealink T48G/T46G** verán:
    
     ![Captura de pantalla que muestra el código Yealink expirado](../../images/3a4462ac-0c59-409e-a3bb-1451cdcc8676.png)
  
    Usando un explorador, vaya a la dirección que se muestra en el teléfono e introduzca su nombre de usuario de Skype Empresarial.
    
     ![Captura de pantalla que muestra la verificación por correo electrónico](../../images/7c540b85-dc37-4ce7-a077-9e3454a0efd0.png)
  
    Introduzca el código que se muestra en el teléfono.
    
     ![Captura de pantalla que muestra la introducción de código en la pantalla de inicio de sesión](../../images/d6b88016-35d2-41d1-a0da-81fef34521d4.png)
  
    Compruebe que el sitio muestra "[Teléfono nombre del fabricante] Skype Empresarial **certificado Teléfono**" y haga clic en **Continuar**.
    
     ![Captura de pantalla que muestra la verificación del nombre](../../images/a8252b37-4ff5-4ece-9e2a-3e05bf928299.png)
  
    Haga clic en las credenciales de usuario o en **Usar otra cuenta**:
    
     ![Captura de pantalla que muestra las opciones de credenciales](../../images/8415028b-7924-4747-b639-052d9b0b961e.png)
  
    Cuando se muestra la página siguiente, es seguro cerrar el explorador.
    
     ![Captura de pantalla que muestra un mensaje de confirmación](../../images/1a873201-52fc-4a63-b7b5-e82bbd031fd2.png)
  
    > [!NOTE]
    > Los teléfonos LPE para Skype Empresarial Online solo admiten el inicio de sesión mediante tethering USB. 
  
- **Implementaciones admitidas**: la siguiente tabla muestra los tipos de autenticación compatibles con los modelos de implementación que se admiten actualmente, incluidos la integración de Exchange, la autenticación moderna con Multi-factor Authentication (MFA) y Skype Empresarial Online y local.
    
|||||||
|:-----|:-----|:-----|:-----|:-----|:-----|
|**Skype Empresarial** <br/> |**Exchange** <br/> |**Método de inicio de sesión en el teléfono** <br/> |**Skype Empresarial acceso** <br/> |**Acceso a Exchange con autenticación moderna y MFA desactivados** <br/> |**Acceso a Exchange con autenticación moderna y MFA activados** <br/> |
|En línea  <br/> |En línea  <br/> |Inicio de sesión web  <br/> |Sí  <br/> |Sí  <br/> |Sí  <br/> |
|En línea  <br/> |En línea  <br/> |Nombre de usuario y contraseña  <br/> |Sí  <br/> |Sí  <br/> |No  <br/> |
|En línea  <br/> |Local  <br/> |Inicio de sesión web  <br/> |Sí  <br/> |No  <br/> |No  <br/> |
|En línea  <br/> |Local  <br/> |Nombre de usuario y contraseña  <br/> |Sí  <br/> |Sí  <br/> |No  <br/> |
|Local  <br/> |En línea/local  <br/> |Autenticación de PIN  <br/> |Sí  <br/> |No  <br/> |No  <br/> |
|Local  <br/> |En línea/local  <br/> |Nombre de usuario y contraseña  <br/> |Sí  <br/> |Sí  <br/> |N/D  <br/> |
|Local  <br/> |En línea/local  <br/> |Inicio de sesión vía equipo (BTOE)  <br/> |Sí  <br/> |Sí  <br/> |N/D  <br/> |
   
- **Teléfono características** El conjunto de características puede variar ligeramente en función del partner del teléfono IP. Para obtener el conjunto de características completo y para obtener más información sobre las características de cada fabricante de teléfonos, vea Obtener [teléfonos para Skype Empresarial en línea.](getting-phones-for-skype-for-business-online.md)
    
- **Bloqueo del teléfono**: esta es una característica que se ha incorporado a los teléfonos certificados para Skype Empresarial recientemente como medida de protección del teléfono. Si está habilitado, se le pedirá a los usuarios que creen un PIN tras la autenticación correcta. Una vez creado, el teléfono se bloqueará cuando transcurra el tiempo de inactividad definido, o si el usuario bloquea manualmente el teléfono o sincroniza el bloqueo del teléfono con el de su equipo mediante la característica de emparejamiento del teléfono. Si el PIN de bloqueo de teléfono se introduce incorrectamente varias veces, el teléfono cerrará la sesión del usuario o requerirá el código de un administrador para desbloquear el teléfono, pero esto variará dependiendo del partner telefónico. El PIN del usuario debe tener entre 6 y 15 dígitos.
    
    Puede deshabilitar Phone-Lock para su organización (que está habilitada de forma predeterminada), cambiar el tiempo de inactividad y elegir si los usuarios pueden realizar llamadas telefónicas mientras están bloqueados o no usando la configuración de la banda. Vea [Set-CsUCPhoneConfiguration](/powershell/module/skype/set-csucphoneconfiguration?view=skype-ps) para obtener más información sobre esa configuración.
    
## <a name="step-7-optional---if-you-have-device-pairing-and-better-together-over-ethernet-btoe"></a>Paso 7 (opcional): si se dispone de emparejamiento de dispositivos y Better Together over Ethernet (BToE)
<a name="BK_BTOE"> </a>

BToE es un mecanismo de dolor de teléfono para teléfonos IP asociados que empareja el teléfono de un usuario con su Windows Skype Empresarial aplicación. BToE permite a los usuarios:
  
- Iniciar sesión en su teléfono IP con su Skype Empresarial de escritorio (con un equipo PC)
    
- Sincronizar Phone-Lock con el bloqueo de PC
    
- Haga clic para llamar
    
BToE se puede configurar para que funcione en dos modos: *Automático* (predeterminado) y *Manual.* También se puede activar (opción predeterminada) y desactivar para los usuarios con configuración en banda de Skype Empresarial. En el modo *Manual*  , los usuarios tendrán que realizar un paso adicional para emparejar sus teléfonos con la aplicación para Windows.
  
 **Para implementar BToE a los usuarios**
  
1. Conecte los equipos con los teléfonos usando el puerto de los equipos.
    
     ![Captura de pantalla que muestra la conexión a un equipo PC](../../images/e21d76c7-867c-4fe6-95c6-fc40c608ed0c.png)
  
2. Descargue el software BToE más reciente desde el sitio web del fabricante utilizando los vínculos que se ofrecen a continuación e instálelo. Para una mejor experiencia de usuario, puede distribuir e instalar el software BToE con una solución de distribución de administración como Microsoft Endpoint Configuration Manager. Para obtener ayuda con Configuration Manager, vea [Paquetes y programas en Configuration Manager.](/configmgr/apps/deploy-use/packages-and-programs)
    
   - [Sitio de descarga de software de Polycom BToE](https://www.polycom.com/voice-conferencing-solutions/microsoft-phones.html)
    
   - [Descarga del software BToE de Yealink](http://www.yealink.com/products_list_10.html)
    
   - [Descarga del software BToE de AudioCodes](https://www.audiocodes.com/solutions-products/solutions/skype-for-business-microsoft-teams/skype-for-business-online)
    
3. La configuración del servidor para BToE está establecida en **Habilitado** y **modo automático** de forma predeterminada. Para cambiar esa configuración, consulte [Set-CsIPPhonePolicy](/powershell/module/skype/Set-CsIPPhonePolicy).
    
> [!NOTE]
> Actualmente BToE no es compatible con Mac ni plataformas VDI. 
  
## <a name="related-topics"></a>Temas relacionados
[Obtener números de teléfono de servicio para Skype Empresarial y Microsoft Teams](/microsoftteams/getting-service-phone-numbers)

[Esto es lo obtiene con el Sistema telefónico](/MicrosoftTeams/here-s-what-you-get-with-phone-system)

[Países y regiones donde Audioconferencia y Planes de llamada están disponibles](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)

  
