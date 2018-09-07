---
title: Configurar conferencias de Audio de Skype for Business y Microsoft Teams
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
- Microsoft Teams
localization_priority: Priority
f1keywords:
- O365P_DialInConfDesc
ms.custom:
- Audio Conferencing
- LIL_Placement
description: 'Obtenga información sobre cómo configurar acceso telefónico o audioconferencias para las personas de su empresa que necesitan unirse a llamadas de conferencia utilizando un teléfono. '
ms.openlocfilehash: 33e499719825a195484c6340bed09afeaa70f5ee
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2018
ms.locfileid: "23850199"
---
# <a name="set-up-audio-conferencing-for-skype-for-business-and-microsoft-teams"></a>Configurar conferencias de Audio de Skype for Business y Microsoft Teams

En algunas ocasiones, en su organización se necesitará un teléfono para llamar a una reunión. ¡Skype for Business y Microsoft Teams incluyen la característica de audioconferencia justo para ese tipo de situaciones! Una persona puede llamar a reuniones de Skype for Business o Microsoft Teams mediante un teléfono, en lugar de usando las aplicaciones de Skype for Business o Microsoft Teams en un dispositivo móvil o un PC. 
  
Solo necesita configurar Audioconferencia para las personas que planeen programar o dirigir las reuniones. Los asistentes que se conectan por teléfono a la reunión no necesitan tener asignada ninguna licencia ni otra configuración.
  
Para ver las preguntas más frecuentes acerca de Audioconferencia, consulte [Preguntas frecuentes sobre Audioconferencia](/MicrosoftTeams/audio-conferencing-common-questions).

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="step-1-find-out-if-audio-conferencing-is-available-in-your-countryregion"></a>Paso 1: averiguar si Audioconferencia está disponible en su país o región
<a name="__top"> </a>


Vaya a la [Disponibilidad de país y región para Audioconferencia y Planes de llamadas](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans) y seleccione su país o región para obtener información sobre la disponibilidad de Audioconferencia, así como información sobre Sistema telefónico, Planes de llamadas, números gratuitos y de pago, y Créditos de comunicaciones. 
 
## <a name="step-2-get-and-assign-licenses"></a>Paso 2: obtener licencias y asignarlas
 
1. Para Audioconferencia, necesita una licencia para cada usuario que vaya a configurar reuniones de acceso telefónico. Para saber qué licencias tiene que comprar para realizar Audioconferencias de acceso telefónico local y cuánto cuestan, consulte [Licencias de complementos de Skype for Business](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).
        
2. Después de adquirir las licencias de Audioconferencia, tendrá que asignarlas a aquellas personas de la organización que vayan a programar o coordinar reuniones. Consulte [Asignar o quitar licencias de Office 365 para empresas](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc) que haya comprado a las personas de su organización que vayan a programar o coordinar reuniones.
    
3. También se recomienda que asigne licencias de Créditos de comunicaciones (que no cuesta nada) a los mismos usuarios que asignó licencias en el paso anterior. Para obtener información sobre cómo configurar Créditos de comunicaciones, vea [Configurar Créditos de comunicaciones para su organización](/microsoftteams/set-up-communications-credits-for-your-organization).
    
> [!NOTE]
> También puede establecer una Audioconferencia de pago por minuto. Vaya [aquí](/microsoftteams/audio-conferencing-pay-per-minute) para obtener más información acerca de cómo usarlas.

## <a name="step-3-get-service-numbers-for-your-conferencing-bridges"></a>Paso 3: obtener los números de servicio para el puente de conferencia
<a name="__top"> </a>

En Audioconferencia, no puede usar números de teléfono para los usuarios; debe obtener números de servicio. Puede obtener números de pago o números gratuitos de servicio para el puente de conferencia. Hay tres formas de obtene números de servicio gratuitos y de pago: 
  
- **Usar el Centro de administración de Skype for Business.** Para algunos países o regiones, puede obtener los números de servicio para el puente de conferencia utilizando el Centro de administración Skype for Business, vea [Obtener números de teléfono de servicio](../what-is-phone-system-in-office-365/getting-service-phone-numbers.md).
    
- **Portar los números existentes.** Para realizar la portabilidad de los números existentes de su proveedor de servicios u operador telefónico actual a Office 365, o transferirlos. Consulte [Transferir números de teléfono a Office 365](/microsoftteams/transfer-phone-numbers-to-office-365) o [Administrar los números de teléfono de su organización](/microsoftteams/manage-phone-numbers-for-your-organization) para obtener más información que le ayude a hacer esto.  
  
- **Usar un formulario de solicitud para números nuevos.** En ocasiones, también en función de su país o región, no podrá conseguir números nuevos mediante el Centro de administración de Skype for Business o necesitará números de teléfono o códigos de área específicos. En ese caso, tendrá que descargar un formulario y enviárnoslo. Para obtener más información, vea [Administrar los números de teléfono de su organización](/microsoftteams/manage-phone-numbers-for-your-organization). 
    
## <a name="step-4-assign-a-service-number-to-the-conferencing-bridge"></a>Paso 4: asignar un número de servicio al puente de conferencia
<a name="__top"> </a>

Una vez que obtenga los números de teléfono gratuitos o de pago para el puente de conferencia, debe asignar los números de modo que se pueden usar en invitaciones a reuniones.  

Para asignar un nuevo número de teléfono al puente de audioconferencia:

![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Mediante el Centro de administración de Skype for Business:**

 Vaya al **Centro de administración de Office 365** > **Centros de administración** > **Skype for Business** > **Voz** > **Números de teléfono**, seleccione el número de teléfono y haga clic en **Asignar**.

Para obtener más información, vea [Cambiar los números de teléfono en el puente de audioconferencia](/MicrosoftTeams/change-the-phone-numbers-on-your-audio-conferencing-bridge).

## <a name="step-5-set-the-default-and-alternate-languages-for-a-conferencing-bridge"></a>Paso 5: establecer el valor predeterminado e idiomas alternativos para un puente de conferencia
<a name="__top"> </a>

A continuación, [Establezca los idiomas de operador automático para Audioconferencia](../audio-conferencing-in-office-365/set-auto-attendant-languages-for-audio-conferencing.md), los cuales usa el operador automático de conferencia para saludar a los autores de las llamadas cuando llaman a un número de teléfono para Audioconferencia. 

![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Mediante el Centro de administración de Skype for Business y Microsoft Teams:**

En el panel, vaya a **Reuniones** > **Puentes de conferencia**, seleccione el número de teléfono de puente de conferencia, haga clic en **Editar**y, a continuación, elija el idioma predeterminado.

![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Mediante el Centro de administración de Skype for Business:**

Vaya al **Centro de administración de Office 365** > **Centros de administración** > **Skype for Business** > **Audioconferencia** > **Configuración de puente de Microsoft**, seleccione el número de teléfono de puente de conferencia y, a continuación, haga clic en **Establecer idiomas**.

## <a name="step-6-set-your-conferencing-bridge-settings"></a>Paso 6: configurar el puente de conferencia
<a name="__top"> </a>
    
Después de configurar el puente de conferencia, compruebe que la configuración predeterminada, como las notificaciones de entrada o salida y la longitud PIN, sea la que va a usar; si no lo es, se puede cambiar. 

![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Mediante el Centro de administración de Skype for Business y Microsoft Teams:**

En el panel, vaya a **Reuniones** > **Puentes de conferencia** > **Configuración de puente**. Se abrirá el panel **Configuración de puente**. Para obtener más información, consulte [Cambiar la configuración de un puente de Audioconferencia](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge).

![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Mediante el Centro de administración de Skype for Business:**

Vaya al **Centro de administración de Office 365** > **Centros de administración** > **Skype for Business** > **Audioconferencia** > **Configuración de puente de Microsoft**. Se abrirá la página de **Configuración de puente de Microsoft**. Para obtener más información, consulte [Cambiar la configuración de un puente de Audioconferencia](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge).

## <a name="step-7-assign-dial-in-phone-numbers-for-users-who-lead-meetings"></a>Paso 7: asignar los números de teléfono de acceso telefónico a los usuarios que coordinan las reuniones

Después de haber creado un puente de Audioconferencia, debe establecer los números gratuitos y de pago para los usuarios.

Debe hacer esto para todas las personas de su organización que coordinen o programen reuniones. Para ello:

![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Mediante el Centro de administración de Skype for Business y Microsoft Teams:**

En el panel, haga clic en **Usuarios**, seleccione el usuario en la lista, haga clic en **Editar**, haga clic en **Editar** junto a **Audioconferencia** y, a continuación, en el panel de **Audioconferencia**, elija un número en las listas de **Números de pago** y **Números gratuitos**.

![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Mediante el Centro de administración de Skype for Business:**

Vaya al **Centro de administración de Office 365** > **Skype for Business** > **Audioconferencia** > **Usuarios** y, a continuación, seleccione el usuario en la lista y haga clic en **Editar**. Si necesita más detalles, vea [Asignar a Microsoft como proveedor de audioconferencias](../audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider.md).


## <a name="step-8-set-up-meeting-invitations-optional"></a>Paso 8: configurar las invitaciones a reuniones (opcional)
<a name="__top"> </a>
 
Los números de acceso telefónico que se establecen para el usuario se agregarán automáticamente a las invitaciones de las reuniones que se envían a los asistentes de la reunión. Sin embargo, puede agregar sus propios vínculos de ayuda y de avisos legales, un mensaje de texto y un pequeño distintivo gráfico de la empresa, si así lo desea. Consulte [Personalizar las invitaciones a las reuniones](../set-up-skype-for-business-online/customize-meeting-invitations.md).
   
## <a name="related-topics"></a>Temas relacionados

[Preguntas comunes sobre Audioconferencia](/MicrosoftTeams/audio-conferencing-common-questions)
  
[Configurar Skype for Business Online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)
  
[Números de teléfono para Audioconferencia](phone-numbers-for-audio-conferencing.md)
  
[Establecer opciones para reuniones y conferencias telefónicas en línea](https://support.office.com/article/DCD1CA39-0C1F-466C-9573-F04138FEF5E2)
