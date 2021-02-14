---
title: Configurar Audioconferencia para Skype Empresarial
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
# <a name="set-up-audio-conferencing-for-skype-for-business"></a>Configurar Audioconferencia para Skype Empresarial

A veces, en su organización es necesario usar un teléfono para llamar a una reunión. Skype Empresarial incluye la característica de audioconferencia para este tipo de situaciones. Las personas pueden llamar a las reuniones de Skype Empresarial con un teléfono, en lugar de con la aplicación de Skype Empresarial en un dispositivo móvil o PC. 
  
You only need to set up Audio Conferencing for people who plan to schedule or lead meetings. Meeting attendees who dial in don't need any licenses assigned to them or other setup.
  
Para ver las preguntas más frecuentes acerca de las audioconferencias, consulte [Preguntas frecuentes sobre audioconferencias](/MicrosoftTeams/audio-conferencing-common-questions).

## <a name="step-1-find-out-if-audio-conferencing-is-available-in-your-countryregion"></a>Paso 1: averiguar si Audioconferencia está disponible en su país o región
<a name="__top"> </a>

Vaya a la [Disponibilidad de país y región para Audioconferencia y Planes de llamadas](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans) y seleccione su país o región para obtener información sobre la disponibilidad de Audioconferencia, así como información sobre Sistema telefónico, Planes de llamadas, números gratuitos y de pago, y Créditos de comunicaciones. 
 
## <a name="step-2-get-and-assign-licenses"></a>Paso 2: obtener licencias y asignarlas
 
1. Para Las Audioconferencias, necesita una licencia para cada usuario que configure las reuniones de acceso telefónico local. Para saber qué licencias debe comprar para Audioconferencia y cuánto cuestan, consulte licencias de complementos [de Skype Empresarial.](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)

    >[!NOTE] 
    > Las audioconferencias se incluyen en las licencias de Office 365 Enterprise E5 y como complemento.
        
2. Después de adquirir las licencias de Audioconferencia, tendrá que asignarlas a aquellas personas de la organización que vayan a programar o coordinar reuniones. Vea Asignar o quitar licencias de las aplicaciones de [Microsoft 365](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc) para empresas que compró a las personas de su organización que van a programar o dirigir reuniones.
    
3. También se recomienda que asigne licencias de Créditos de comunicaciones (que no cuesta nada) a los mismos usuarios que asignó licencias en el paso anterior. Para saber si necesita configurar Créditos de comunicaciones, consulte [Configurar Créditos de comunicaciones para su organización](/microsoftteams/set-up-communications-credits-for-your-organization).
    
> [!NOTE]
> También puede establecer una [Audioconferencia de pago por minuto](/microsoftteams/audio-conferencing-pay-per-minute).

## <a name="step-3-get-service-numbers-for-your-conferencing-bridges"></a>Paso 3: obtener los números de servicio para el puente de conferencia
<a name="__top"> </a>

En Audioconferencia, no puede usar números de teléfono para los usuarios; debe obtener números de servicio. Puede obtener números de pago o números gratuitos de servicio para el puente de conferencia. Hay tres formas de obtene números de servicio gratuitos y de pago: 
  
- **Use el Centro de administración de Skype Empresarial.** En algunos países o regiones, puede obtener números de servicio para los puentes de conferencia mediante el Centro de administración de Skype Empresarial. [Obtener números de teléfono de servicio](/microsoftteams/getting-service-phone-numbers)
    
- **Portar los números existentes.** Para transferir o transferir números existentes de su proveedor de servicios u operador telefónico actual a Microsoft 365 u Office 365. Consulte [Transferir números de teléfono a Teams](/microsoftteams/phone-number-calling-plans/transfer-phone-numbers-to-teams) o [Administrar los números de teléfono de su organización](/microsoftteams/manage-phone-numbers-for-your-organization) para obtener más información que le ayude a hacer esto.  
  
- **Usar un formulario de solicitud para números nuevos.** A veces (según su país o región) no podrá obtener los nuevos números de servicio con el Centro de administración de Skype Empresarial o necesitará números de teléfono o códigos de área específicos. Si es así, tendrá que descargar un formulario y enviárselo de nuevo a nosotros. Para obtener más información, vea [Administrar los números de teléfono de su organización](/microsoftteams/manage-phone-numbers-for-your-organization). 
    
## <a name="step-4-assign-a-service-number-to-the-conferencing-bridge"></a>Paso 4: asignar un número de servicio al puente de conferencia
<a name="__top"> </a>

Una vez que obtenga los números de teléfono gratuitos o de pago para el puente de conferencia, debe asignar los números de modo que se pueden usar en invitaciones a reuniones.  

Para asignar un nuevo número de teléfono al puente de audioconferencia:

![Un icono que muestra el logotipo de Skype empresarial](../images/sfb-logo-30x30.png)**con el centro de administración de Skype empresarial:**

 1. Vaya al **Centro de administración de Microsoft 365** > **Centros de administración** > **Teams** > **Portal heredado**.
 2. Seleccione **Voz** > **Números de teléfono**.
 3. Seleccione el número de teléfono y haga clic en **Asignar**.

Para obtener más información, [vea Cambiar los números de teléfono del puente de audioconferencia.](/MicrosoftTeams/change-the-phone-numbers-on-your-audio-conferencing-bridge)

## <a name="step-5-set-the-default-and-alternate-languages-for-a-conferencing-bridge"></a>Paso 5: establecer el valor predeterminado e idiomas alternativos para un puente de conferencia
<a name="__top"> </a>

A continuación, desea establecer los idiomas del operador automático para las [audioconferencias](../audio-conferencing-in-office-365/set-auto-attendant-languages-for-audio-conferencing.md) que el operador automático de las conferencias usa para saludar a los autores de las llamadas cuando llaman a un número de teléfono para Audioconferencia. 

![Un icono que muestra el logotipo de Microsoft Teams ](../images/teams-logo-30x30.png) **Mediante el centro de administración de Microsoft Teams**:

1. En el panel, vaya a **Reuniones** > **Puentes de conferencia**.
2. Seleccione el número de teléfono de puente de conferencia, haga clic en **Editar** y, a continuación, elija el idioma predeterminado.

![Un icono que muestra el logotipo de Skype Empresarial ](../images/sfb-logo-30x30.png) **mediante el Centro de administración de Skype Empresarial:**

1. Vaya al Centro de administración > **Centro de administración** del portal heredado de  >    >  **Teams.**
2. Seleccione **Puente de Microsoft de Audioconferencia.**  >   
3. Seleccione el número de teléfono del puente de conferencia, seleccione **Establecer idiomas** y, a continuación, elija el idioma predeterminado.

## <a name="step-6-set-your-conferencing-bridge-settings"></a>Paso 6: configurar el puente de conferencia
<a name="__top"> </a>
    
Después de configurar el puente de conferencia, compruebe que la configuración predeterminada, como las notificaciones de entrada o salida y la longitud PIN, sea la que va a usar; si no lo es, se puede cambiar. 

![Un icono que muestra el logotipo de Microsoft Teams ](../images/teams-logo-30x30.png) **Mediante el centro de administración de Microsoft Teams**:

1. En el panel, vaya a **Reuniones** > **Puentes de conferencia**.
2. Seleccione **Configuración del puente**. Se abrirá el panel **Configuración de puente**. 

Para obtener más información, consulte [Cambiar la configuración de un puente de Audioconferencia](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge).

![Un icono que muestra el logotipo de Skype empresarial](../images/sfb-logo-30x30.png)**con el centro de administración de Skype empresarial:**

1. Vaya al **Centro de administración de Microsoft 365** > **Centros de administración** > **Teams** > **Portal heredado**.
2. Seleccione Configuración del puente de Microsoft **de Audioconferencia.**  >   Se abrirá la página de **Configuración de puente de Microsoft**. 

Para obtener más información, consulte [Cambiar la configuración de un puente de Audioconferencia](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge).

## <a name="step-7-assign-dial-in-phone-numbers-for-users-who-lead-meetings"></a>Paso 7: asignar los números de teléfono de acceso telefónico a los usuarios que coordinan las reuniones

Después de haber creado un puente de Audioconferencia, debe establecer los números gratuitos y de pago para los usuarios.

Debe hacer esto para todas las personas de su organización que coordinen o programen reuniones. 

![Un icono que muestra el logotipo de Microsoft Teams ](../images/teams-logo-30x30.png) **Mediante el centro de administración de Microsoft Teams**:

1. En el panel, haga clic en **usuarios**, seleccione el usuario de la lista y, a continuación, seleccione **Editar**.
2. Seleccione **Editar** junto a **Audioconferencia** y, a continuación, en el panel de **Audioconferencia**, elija un número en las listas de **Números de pago** y **Números gratuitos**.

![Un icono que muestra el logotipo de Skype empresarial](../images/sfb-logo-30x30.png)**con el centro de administración de Skype empresarial:**

1. Vaya al portal heredado de Teams del Centro de administración de **Microsoft 365.**  >    >  
2. Seleccione **Usuarios de audioconferencia** y, a continuación,  >  seleccione el usuario de la lista y haga clic en **Editar.** 

Si necesita más detalles, vea [Asignar a Microsoft como proveedor de audioconferencias](../audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider.md).


## <a name="step-8-set-up-meeting-invitations-optional"></a>Paso 8: configurar las invitaciones a reuniones (opcional)
<a name="__top"> </a>
 
Los números de acceso telefónico que se establecen para el usuario se agregan automáticamente a las invitaciones de las reuniones que se envían a los asistentes. Sin embargo, puede agregar sus propios vínculos de ayuda y de avisos legales, un mensaje de texto y un pequeño distintivo gráfico de la empresa. Vea [Personalizar invitaciones a reuniones](../set-up-skype-for-business-online/customize-meeting-invitations.md)
   
## <a name="related-topics"></a>Temas relacionados

[Preguntas frecuentes sobre Audioconferencia](/MicrosoftTeams/audio-conferencing-common-questions)
  
[Configurar Skype Empresarial Online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)
  
[Números de teléfono para Audioconferencia](phone-numbers-for-audio-conferencing.md)
  
[Establecer opciones para reuniones y conferencias telefónicas en línea](https://support.office.com/article/DCD1CA39-0C1F-466C-9573-F04138FEF5E2)
