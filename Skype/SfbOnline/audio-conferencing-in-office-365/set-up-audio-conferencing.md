---
title: Configurar audioconferencias para Skype empresarial
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
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- LIL_Placement
- O365P_DialInConfDesc
description: 'Obtenga información acerca de cómo configurar las conferencias de acceso telefónico local o de audio para las personas de su empresa que necesitan usar un teléfono para unirse a llamadas de conferencia. '
ms.openlocfilehash: bfd9c9ec31736b0f7fc16f15a907c87406113871
ms.sourcegitcommit: 36f7ec432090683aedb77a5bd7856e1b10af2a81
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/08/2020
ms.locfileid: "44163949"
---
# <a name="set-up-audio-conferencing-for-skype-for-business"></a>Configurar audioconferencias para Skype empresarial

A veces, las personas de su organización deberán usar un teléfono para llamar a una reunión. Skype empresarial incluye la característica de audioconferencia solo en esta situación. Las personas pueden llamar a reuniones de Skype empresarial con un teléfono, en lugar de usar la aplicación de Skype empresarial en un dispositivo móvil o PC. 
  
You only need to set up Audio Conferencing for people who plan to schedule or lead meetings. Meeting attendees who dial in don't need any licenses assigned to them or other setup.
  
Para ver las preguntas más frecuentes acerca de las audioconferencias, consulte [Preguntas frecuentes sobre audioconferencias](/MicrosoftTeams/audio-conferencing-common-questions).

## <a name="step-1-find-out-if-audio-conferencing-is-available-in-your-countryregion"></a>Paso 1: averiguar si Audioconferencia está disponible en su país o región
<a name="__top"> </a>

Vaya a la [Disponibilidad de país y región para Audioconferencia y Planes de llamadas](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans) y seleccione su país o región para obtener información sobre la disponibilidad de Audioconferencia, así como información sobre Sistema telefónico, Planes de llamadas, números gratuitos y de pago, y Créditos de comunicaciones. 
 
## <a name="step-2-get-and-assign-licenses"></a>Paso 2: obtener licencias y asignarlas
 
1. Para las conferencias de audio, necesita una licencia para cada usuario que vaya a configurar las reuniones de acceso telefónico. Para conocer las licencias que necesita comprar para las conferencias de audio y cuánto cuestan, vea [licencias complementarias de Skype empresarial](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).

    >[!NOTE] 
    > Las audioconferencias se incluyen en las licencias de Office 365 Enterprise E5 y como complemento.
        
2. Después de adquirir las licencias de Audioconferencia, tendrá que asignarlas a aquellas personas de la organización que vayan a programar o coordinar reuniones. Consulte [asignar o quitar licencias de las aplicaciones de Microsoft 365 para empresas](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc) que compró a las personas de su organización que van a programar o coordinar reuniones.
    
3. También se recomienda que asigne licencias de Créditos de comunicaciones (que no cuesta nada) a los mismos usuarios que asignó licencias en el paso anterior. Para saber si necesita configurar Créditos de comunicaciones, consulte [Configurar Créditos de comunicaciones para su organización](/microsoftteams/set-up-communications-credits-for-your-organization).
    
> [!NOTE]
> También puede establecer una [Audioconferencia de pago por minuto](/microsoftteams/audio-conferencing-pay-per-minute).

## <a name="step-3-get-service-numbers-for-your-conferencing-bridges"></a>Paso 3: obtener los números de servicio para el puente de conferencia
<a name="__top"> </a>

En Audioconferencia, no puede usar números de teléfono para los usuarios; debe obtener números de servicio. Puede obtener números de pago o números gratuitos de servicio para el puente de conferencia. Hay tres formas de obtene números de servicio gratuitos y de pago: 
  
- **Use el centro de administración de Skype empresarial**. Para algunos países o regiones, puede obtener números de servicio para sus puentes de conferencia con el centro de administración de Skype empresarial. [Obtener números de teléfono de servicio](/microsoftteams/getting-service-phone-numbers)
    
- **Portar los números existentes.** Para migrar o transferir números existentes de su proveedor de servicios actual o de su operador telefónico a Microsoft 365 u Office 365. Consulte [Transferir números de teléfono a Teams](/microsoftteams/phone-number-calling-plans/transfer-phone-numbers-to-teams) o [Administrar los números de teléfono de su organización](/microsoftteams/manage-phone-numbers-for-your-organization) para obtener más información que le ayude a hacer esto.  
  
- **Usar un formulario de solicitud para números nuevos.** A veces, en función de su país o región, no podrá obtener los nuevos números de servicio con el centro de administración de Skype empresarial o necesitará números de teléfono o códigos de área específicos. Si es así, tendrá que descargar un formulario y enviárselo de nuevo a nosotros. Para obtener más información, vea [Administrar los números de teléfono de su organización](/microsoftteams/manage-phone-numbers-for-your-organization). 
    
## <a name="step-4-assign-a-service-number-to-the-conferencing-bridge"></a>Paso 4: asignar un número de servicio al puente de conferencia
<a name="__top"> </a>

Una vez que obtenga los números de teléfono gratuitos o de pago para el puente de conferencia, debe asignar los números de modo que se pueden usar en invitaciones a reuniones.  

Para asignar un nuevo número de teléfono al puente de audioconferencia:

![Un icono que muestra el logotipo de Skype empresarial](../images/sfb-logo-30x30.png)**con el centro de administración de Skype empresarial:**

 1. Vaya al **Centro de administración de Microsoft 365** > **Centros de administración** > **Teams** > **Portal heredado**.
 2. Seleccione **Voz** > **Números de teléfono**.
 3. Seleccione el número de teléfono y haga clic en **Asignar**.

Para obtener más información, consulte [cambiar los números de teléfono en el puente de audioconferencia](/MicrosoftTeams/change-the-phone-numbers-on-your-audio-conferencing-bridge).

## <a name="step-5-set-the-default-and-alternate-languages-for-a-conferencing-bridge"></a>Paso 5: establecer el valor predeterminado e idiomas alternativos para un puente de conferencia
<a name="__top"> </a>

A continuación, deseas [configurar los idiomas del operador automático para las conferencias de audio](../audio-conferencing-in-office-365/set-auto-attendant-languages-for-audio-conferencing.md) que el operador automático de conferencias usa para saludar a las personas que llaman a un número de teléfono para las conferencias de audio. 

![Un icono que muestra el logotipo de Microsoft Teams ](../images/teams-logo-30x30.png) **Mediante el centro de administración de Microsoft Teams**:

1. En el panel, vaya a **Reuniones** > **Puentes de conferencia**.
2. Seleccione el número de teléfono de puente de conferencia, haga clic en **Editar**y, a continuación, elija el idioma predeterminado.

![Un icono que muestra el logotipo](../images/sfb-logo-30x30.png) de Skype empresarial **con el centro de administración de Skype empresarial**:

1. Vaya al centro de administración > **centros** > de administración de**Teams** > **portales heredados**.
2.  > Seleccione **Audio conferencing****Microsoft Bridge**. 
3. Seleccione el número de teléfono del puente de conferencia, seleccione **establecer idiomas**y, a continuación, elija el idioma predeterminado.

## <a name="step-6-set-your-conferencing-bridge-settings"></a>Paso 6: configurar el puente de conferencia
<a name="__top"> </a>
    
Después de configurar el puente de conferencia, compruebe que la configuración predeterminada, como las notificaciones de entrada o salida y la longitud PIN, sea la que va a usar; si no lo es, se puede cambiar. 

![Un icono que muestra el logotipo de Microsoft Teams ](../images/teams-logo-30x30.png) **Mediante el centro de administración de Microsoft Teams**:

1. En el panel, vaya a **Reuniones** > **Puentes de conferencia**.
2. Seleccione **Configuración del puente**. Se abrirá el panel **Configuración de puente**. 

Para obtener más información, consulte [Cambiar la configuración de un puente de Audioconferencia](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge).

![Un icono que muestra el logotipo de Skype empresarial](../images/sfb-logo-30x30.png)**con el centro de administración de Skype empresarial:**

1. Vaya al **Centro de administración de Microsoft 365** > **Centros de administración** > **Teams** > **Portal heredado**.
2. Seleccione **Audio conferencing** > **configuración**de conferencia de audio de Microsoft. Se abrirá la página de **Configuración de puente de Microsoft**. 

Para obtener más información, consulte [Cambiar la configuración de un puente de Audioconferencia](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge).

## <a name="step-7-assign-dial-in-phone-numbers-for-users-who-lead-meetings"></a>Paso 7: asignar los números de teléfono de acceso telefónico a los usuarios que coordinan las reuniones

Después de haber creado un puente de Audioconferencia, debe establecer los números gratuitos y de pago para los usuarios.

Debe hacer esto para todas las personas de su organización que coordinen o programen reuniones. 

![Un icono que muestra el logotipo de Microsoft Teams ](../images/teams-logo-30x30.png) **Mediante el centro de administración de Microsoft Teams**:

1. En el panel, haga clic en **usuarios**, seleccione el usuario de la lista y, a continuación, seleccione**Editar**.
2. Seleccione **Editar** junto a **Audioconferencia** y, a continuación, en el panel de **Audioconferencia**, elija un número en las listas de **Números de pago** y **Números gratuitos**.

![Un icono que muestra el logotipo de Skype empresarial](../images/sfb-logo-30x30.png)**con el centro de administración de Skype empresarial:**

1. Vaya al **Centro** > de administración de Microsoft 365**portal heredado****Teams** > .
2. Seleccione **Audio conferencing** > **usuarios**de la Conferencia de audio y, a continuación, seleccione el usuario de la lista y haga clic en **Editar**. 

Si necesita más detalles, vea [Asignar a Microsoft como proveedor de audioconferencias](../audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider.md).


## <a name="step-8-set-up-meeting-invitations-optional"></a>Paso 8: configurar las invitaciones a reuniones (opcional)
<a name="__top"> </a>
 
Los números de acceso telefónico que se establecen para el usuario se agregan automáticamente a las invitaciones de las reuniones que se envían a los asistentes. Sin embargo, puede agregar sus propios vínculos de ayuda y de avisos legales, un mensaje de texto y un pequeño distintivo gráfico de la empresa. Vea [Personalizar invitaciones a reuniones](../set-up-skype-for-business-online/customize-meeting-invitations.md)
   
## <a name="related-topics"></a>Temas relacionados

[Preguntas frecuentes sobre Audioconferencia](/MicrosoftTeams/audio-conferencing-common-questions)
  
[Configurar Skype Empresarial Online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)
  
[Números de teléfono para Audioconferencia](phone-numbers-for-audio-conferencing.md)
  
[Establecer opciones para reuniones y conferencias telefónicas en línea](https://support.office.com/article/DCD1CA39-0C1F-466C-9573-F04138FEF5E2)
