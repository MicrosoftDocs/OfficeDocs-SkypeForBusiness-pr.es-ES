---
title: Configurar conferencias de Audio para Skype para la empresa
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: d01954f1-4f37-4cf5-a636-20039e5c59e9
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
f1keywords:
- O365P_DialInConfDesc
ms.custom:
- Audio Conferencing
- LIL_Placement
description: 'Obtenga información sobre cómo configurar acceso telefónico o conferencias de Audio para las personas de su empresa que necesitan utilizar un teléfono para unirse a llamadas de conferencia. '
ms.openlocfilehash: 64ebcb97157d94a5c25ddff38e8e1ca58d3975ec
ms.sourcegitcommit: bc2b227b4ac0a9521993f808a1361b4f9bc7faad
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2019
ms.locfileid: "30633302"
---
# <a name="set-up-audio-conferencing-for-skype-for-business"></a>Configurar conferencias de Audio para Skype para la empresa

En algunas ocasiones, en su organización se necesitará un teléfono para llamar a una reunión. ¡Skype para la empresa incluye la característica de conferencia de audio para justo esta situación! Personas puedan llamar a Skype para reuniones de negocios mediante un teléfono, en lugar de usar el Skype para la aplicación empresarial en un dispositivo móvil o un PC. 
  
You only need to set up Audio Conferencing for people who plan to schedule or lead meetings. Meeting attendees who dial in don't need any licenses assigned to them or other setup.
  
Para ver las preguntas más frecuentes acerca de las audioconferencias, consulte [Preguntas frecuentes sobre audioconferencias](/MicrosoftTeams/audio-conferencing-common-questions).

## <a name="step-1-find-out-if-audio-conferencing-is-available-in-your-countryregion"></a>Paso 1: averiguar si Audioconferencia está disponible en su país o región
<a name="__top"> </a>

Vaya a la [Disponibilidad de país y región para Audioconferencia y Planes de llamadas](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans) y seleccione su país o región para obtener información sobre la disponibilidad de Audioconferencia, así como información sobre Sistema telefónico, Planes de llamadas, números gratuitos y de pago, y Créditos de comunicaciones. 
 
## <a name="step-2-get-and-assign-licenses"></a>Paso 2: obtener licencias y asignarlas
 
1. Para Audioconferencia, necesita una licencia para cada usuario que vaya a configurar reuniones de acceso telefónico. Para obtener información sobre las licencias que necesitará comprar para las conferencias de Audio y cuánto de costo, vea [Skype para Business licensing del complemento](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).

    >[!NOTE] 
    > Conferencias de audio se incluye en las licencias de Office 365 Enterprise E5 y como un complemento.
        
2. Después de adquirir las licencias de Audioconferencia, tendrá que asignarlas a aquellas personas de la organización que vayan a programar o coordinar reuniones. Vea [asignar o quitar licencias de Office 365 para profesionales](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc) ha comprado a las personas de la organización que se van a las reuniones de programación o cliente potencial.
    
3. También se recomienda que asigne licencias de Créditos de comunicaciones (que no cuesta nada) a los mismos usuarios que asignó licencias en el paso anterior. Para obtener información sobre cómo configurar comunicaciones créditos, vea [Configurar Communications créditos para su organización](/microsoftteams/set-up-communications-credits-for-your-organization).
    
> [!NOTE]
> También puede establecer una [Conferencia de Audio de pago por minuto](/microsoftteams/audio-conferencing-pay-per-minute).

## <a name="step-3-get-service-numbers-for-your-conferencing-bridges"></a>Paso 3: obtener los números de servicio para el puente de conferencia
<a name="__top"> </a>

En Audioconferencia, no puede usar números de teléfono para los usuarios; debe obtener números de servicio. Puede obtener números de pago o números gratuitos de servicio para el puente de conferencia. Hay tres formas de obtene números de servicio gratuitos y de pago: 
  
- **Use el Skype para el centro de administración de negocio**. Para algunos países o regiones, puede obtener los números de servicio para el puente de conferencia utilizando el Skype para el centro de administración de negocio. Vea [los números de teléfono del servicio de introducción](../what-is-phone-system-in-office-365/getting-service-phone-numbers.md).
    
- **Puerto sus números de servicio existente**. El puerto o transferir los números existentes desde su proveedor de servicio actual o el operador de teléfono a Office 365. Consulte [Transferir números de teléfono a Office 365](/microsoftteams/transfer-phone-numbers-to-office-365) o [Administrar los números de teléfono de su organización](/microsoftteams/manage-phone-numbers-for-your-organization) para obtener más información que le ayude a hacer esto.  
  
- **Usar un formulario de solicitud para los nuevos números**. A veces (dependiendo de su país o región) no podrá obtener sus números de servicio nueva mediante el Skype para el centro de administración de negocio o necesitará determinados números de teléfono o códigos de área. En ese caso, tendrá que descargar un formulario y enviárnoslo. Para obtener más información, vea [Administrar los números de teléfono de su organización](/microsoftteams/manage-phone-numbers-for-your-organization). 
    
## <a name="step-4-assign-a-service-number-to-the-conferencing-bridge"></a>Paso 4: asignar un número de servicio al puente de conferencia
<a name="__top"> </a>

Una vez que obtenga su teléfono de pago o números de teléfono gratuito para el puente de conferencia, debe asignar los números de modo que se pueden usar en las invitaciones a reuniones.  

Para asignar un nuevo número de teléfono al puente de audioconferencia:

![logotipo-sfb-30x30.png](../images/sfb-logo-30x30.png) **utilizando el Skype para el centro de administración de negocio:**

 1. Vaya al **Centro de administración de Microsoft 365** > **centros de administración** > **equipos** > **portal heredado**.
 2. Seleccione **voz** > **los números de teléfono**.
 3. Seleccione el número de teléfono y haga clic en **asignar**.

Para obtener más información, vea [cambiar los números de teléfono en el puente de conferencia de audio](/MicrosoftTeams/change-the-phone-numbers-on-your-audio-conferencing-bridge).

## <a name="step-5-set-the-default-and-alternate-languages-for-a-conferencing-bridge"></a>Paso 5: establecer el valor predeterminado e idiomas alternativos para un puente de conferencia
<a name="__top"> </a>

A continuación, va a [establecer idiomas de operador automático para conferencias de Audio](../audio-conferencing-in-office-365/set-auto-attendant-languages-for-audio-conferencing.md) que usa el operador automático de conferencia para saludar a los autores de llamadas cuando conectan a un número de teléfono para conferencias de Audio. 

![los equipos-logotipo-30x30.png](../images/teams-logo-30x30.png) **desde el centro de administración de equipos de Microsoft**:

1. En el panel, vaya a **las reuniones** > **puentes de conferencia**.
2. Seleccione el número de teléfono de puente de conferencia, haga clic en **Editar**y, a continuación, elija el idioma predeterminado.

![logotipo-sfb-30x30.png](../images/sfb-logo-30x30.png) **utilizando el Skype para el centro de administración de negocio**:

1. Vaya al **Centro de administración de Office 365** > **centros de administración** > **equipos** > **portal heredado**.
2. Seleccione **conferencias de Audio** > **puente de Microsoft**. 
3. Seleccione el número de teléfono de puente de conferencia, seleccione **conjunto de idiomas**y, a continuación, elija el idioma predeterminado.

## <a name="step-6-set-your-conferencing-bridge-settings"></a>Paso 6: configurar el puente de conferencia
<a name="__top"> </a>
    
Después de configurar el puente de conferencia, compruebe que la configuración predeterminada, como las notificaciones de entrada o salida y la longitud PIN, sea la que va a usar; si no lo es, se puede cambiar. 

![los equipos-logotipo-30x30.png](../images/teams-logo-30x30.png) **desde el centro de administración de equipos de Microsoft**:

1. En el panel, vaya a **las reuniones** > **puentes de conferencia**.
2. Seleccione **configuración de puente**. Se abrirá el panel **Configuración de puente**. 

Para obtener más información, consulte [Cambiar la configuración de un puente de Audioconferencia](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge).

![logotipo-sfb-30x30.png](../images/sfb-logo-30x30.png) **utilizando el Skype para el centro de administración de negocio:**

1. Vaya al **Centro de administración de Microsoft 365** > **centros de administración** > **equipos** > **portal heredado**.
2. Seleccione **conferencias de Audio** > **configuración de puente de Microsoft**. Se abrirá la página de **Configuración de puente de Microsoft**. 

Para obtener más información, consulte [Cambiar la configuración de un puente de Audioconferencia](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge).

## <a name="step-7-assign-dial-in-phone-numbers-for-users-who-lead-meetings"></a>Paso 7: asignar los números de teléfono de acceso telefónico a los usuarios que coordinan las reuniones

Después de haber creado un puente de Audioconferencia, debe establecer los números gratuitos y de pago para los usuarios.

Debe hacer esto para todas las personas de su organización que coordinen o programen reuniones. 

![los equipos-logotipo-30x30.png](../images/teams-logo-30x30.png) **desde el centro de administración de equipos de Microsoft**:

1. En el panel, haga clic en **usuarios**, seleccione el usuario en la lista y seleccione **Editar**.
2. Seleccione **Editar** junto a **Conferencias de Audio**y, a continuación, en el panel de **Conferencia de Audio** , elija un número en las listas números de **número de teléfono de pago** y **gratuito** .

![logotipo-sfb-30x30.png](../images/sfb-logo-30x30.png) **utilizando el Skype para el centro de administración de negocio:**

1. Vaya al **Centro de administración de Microsoft 365** > **equipos** > **portal heredado**.
2. Seleccione **conferencias de Audio** > **a los usuarios**y, a continuación, seleccione el usuario en la lista y haga clic en **Editar**. 

Si necesita más detalles, vea [Asignar a Microsoft como proveedor de audioconferencias](../audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider.md).


## <a name="step-8-set-up-meeting-invitations-optional"></a>Paso 8: configurar las invitaciones a reuniones (opcional)
<a name="__top"> </a>
 
Los números de acceso telefónico que se han establecido para el usuario se agregará automáticamente a las invitaciones a reuniones que se envían a los asistentes de la reunión. Sin embargo, puede agregar su propios ayuda y vínculos legal, un mensaje de texto y gráfico de pequeña empresa si lo desea. Vea [Personalizar las invitaciones a reuniones](../set-up-skype-for-business-online/customize-meeting-invitations.md).
   
## <a name="related-topics"></a>Temas relacionados

[Preguntas comunes sobre Audioconferencia](/MicrosoftTeams/audio-conferencing-common-questions)
  
[Configurar Skype Empresarial Online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)
  
[Números de teléfono para Audioconferencia](phone-numbers-for-audio-conferencing.md)
  
[Establecer opciones para reuniones y conferencias telefónicas en línea](https://support.office.com/article/DCD1CA39-0C1F-466C-9573-F04138FEF5E2)
