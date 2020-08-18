---
title: Configurar audioconferencias en Microsoft Teams
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: d01954f1-4f37-4cf5-a636-20039e5c59e9
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- LIL_Placement
description: 'Obtenga información acerca de cómo configurar las conferencias de acceso telefónico local o de audio para las personas de su empresa que necesitan usar un teléfono para unirse a llamadas de conferencia. '
ms.openlocfilehash: 9c86d83b1a39c5ae3623c2205a09b4e8d604ce5e
ms.sourcegitcommit: d1e4e1105d86745009cf0fdf42d1fc5ad545a952
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/18/2020
ms.locfileid: "46788704"
---
# <a name="set-up-audio-conferencing-for-microsoft-teams"></a>Configurar audioconferencias en Microsoft Teams

En algunas ocasiones, en su organización se necesitará un teléfono para llamar a una reunión. ¡Microsoft Teams incluye la característica de Audioconferencia para este tipo de situaciones! Los usuarios pueden llamar a las reuniones de Teams con un teléfono, en lugar de usar la aplicación Teams en un dispositivo móvil o PC. 
  
Solo debe configurar las audioconferencias para los usuarios que van a programar o dirigir las reuniones. Los asistentes que se conectan por teléfono a la reunión no necesitan tener asignada ninguna licencia ni otra configuración.
  
Para ver las preguntas más frecuentes acerca de las audioconferencias, consulte [Preguntas frecuentes sobre audioconferencias](audio-conferencing-common-questions.md).

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="step-1-find-out-if-audio-conferencing-is-available-in-your-countryregion"></a>Paso 1: averiguar si Audioconferencia está disponible en su país o región
<a name="__top"> </a>

Vaya a la [Disponibilidad de país y región para Audioconferencia y Planes de llamadas](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md) y seleccione su país o región para obtener información sobre la disponibilidad de Audioconferencia, así como información sobre Sistema telefónico, Planes de llamadas, números gratuitos y de pago, y Créditos de comunicaciones. 
 
## <a name="step-2-get-and-assign-licenses"></a>Paso 2: obtener licencias y asignarlas
 
1. Para Audioconferencia, necesita una licencia para cada usuario que vaya a configurar reuniones de acceso telefónico. Para saber qué licencias tiene que comprar para realizar audioconferencias y cuánto cuestan, consulte [Licencias complementarias de Microsoft Teams](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing)

    >[!NOTE] 
    > Las audioconferencias se incluyen en las licencias de Office 365 Enterprise E5 y como complemento.
        
2. Después de adquirir las licencias de Audioconferencia, tendrá que asignarlas a aquellas personas de la organización que vayan a programar o coordinar reuniones. Consulte [asignar licencias a usuarios en Microsoft 365 u Office 365 para empresas](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc) que compró a las personas de su organización que van a programar o coordinar reuniones.
    
3. También se recomienda que asigne licencias de Créditos de comunicaciones (que no cuesta nada) a los mismos usuarios que asignó licencias en el paso anterior. Para saber si necesita configurar Créditos de comunicaciones, consulte [Configurar Créditos de comunicaciones para su organización](set-up-communications-credits-for-your-organization.md).
    
> [!NOTE]
> También puede establecer una [Audioconferencia de pago por minuto](audio-conferencing-pay-per-minute.md).

## <a name="step-3-get-service-numbers-for-your-conferencing-bridges"></a>Paso 3: obtener los números de servicio para el puente de conferencia
<a name="__top"> </a>

En Audioconferencia, no puede usar números de teléfono para los usuarios; debe obtener números de servicio. Puede obtener números de pago o números gratuitos de servicio para el puente de conferencia. Hay tres formas de obtene números de servicio gratuitos y de pago: 
  
- **Usar el centro de administración de Microsoft Teams**. Para algunos países o regiones, puede obtener los números de servicio para el puente de conferencia utilizando el Centro de administración Microsoft Teams. [Obtener números de teléfono de servicio](/microsoftteams/getting-service-phone-numbers)
    
- **Portar los números existentes.** Para migrar o transferir números existentes de su proveedor de servicios actual o de su operador telefónico a Microsoft 365 u Office 365. Consulte [Transferir números de teléfono a Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md) o [Administrar los números de teléfono de su organización](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) para obtener más información que le ayude a hacer esto.  
  
- **Usar un formulario de solicitud para números nuevos.** En ocasiones, también en función de su país o región, no podrá conseguir números nuevos mediante el Centro de administración de Microsoft Teams o necesitará números de teléfono o códigos de área específicos. Si es así, tendrá que descargar un formulario y enviárselo de nuevo a nosotros. Para obtener más información, vea [Administrar los números de teléfono de su organización](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md). 
    
## <a name="step-4-assign-a-service-number-to-the-conferencing-bridge"></a>Paso 4: asignar un número de servicio al puente de conferencia
<a name="__top"> </a>

Una vez que obtenga los números de teléfono gratuitos o de pago para el puente de conferencia, debe asignar los números de modo que se pueden usar en invitaciones a reuniones.  

Para asignar un nuevo número de teléfono al puente de audioconferencia.

![Un icono que muestra el logotipo de Skype empresarial](media/sfb-logo-30x30.png)**con el centro de administración de Skype empresarial:**

 1. Vaya al **Centro de administración de Microsoft 365** > **Centros de administración** > **Teams** > **Portal heredado**.
 2. Seleccione **Voz** > **Números de teléfono**.
 3. Seleccione el número de teléfono y haga clic en **Asignar**.

Para obtener más detalles, vea[Cambiar los números de teléfono de su puente de Audioconferencia](change-the-phone-numbers-on-your-audio-conferencing-bridge.md)

## <a name="step-5-set-the-default-and-alternate-languages-for-a-conferencing-bridge"></a>Paso 5: establecer los idiomas alternativos y predeterminados para un puente de conferencia
<a name="__top"> </a> A continuación, le recomendamos que [establecer un operador automático para las conferencias de audio en Microsoft Teams](set-auto-attendant-languages-for-audio-conferencing-in-teams.md) que el operador automático de conferencias use para saludar a los usuarios que llaman a un número de teléfono para las audioconferencia. 

![Un icono que muestra el logotipo de Microsoft Teams ](media/teams-logo-30x30.png) **Mediante el centro de administración de Microsoft Teams**:

1. En el panel, vaya a **Reuniones** > **Puentes de conferencia**.
2. Seleccione el número de teléfono de puente de conferencia, haga clic en **Editar**y, a continuación, elija el idioma predeterminado.

## <a name="step-6-set-your-conferencing-bridge-settings"></a>Paso 6: configurar el puente de conferencia
<a name="__top"> </a>
    
Después de configurar el puente de conferencia, compruebe que la configuración predeterminada, como las notificaciones de entrada o salida y la longitud PIN, sea la que va a usar; si no lo es, se puede cambiar. 

![Un icono que muestra el logotipo de Microsoft Teams ](media/teams-logo-30x30.png) **Mediante el centro de administración de Microsoft Teams**:

1. En el panel, vaya a **Reuniones** > **Puentes de conferencia**.
2. Seleccione **Configuración del puente**. Se abrirá el panel **Configuración de puente**. 

Para obtener más información, consulte [Cambiar la configuración de un puente de Audioconferencia](change-the-settings-for-an-audio-conferencing-bridge.md).

## <a name="step-7-assign-dial-in-phone-numbers-for-users-who-lead-meetings"></a>Paso 7: asignar los números de teléfono de acceso telefónico a los usuarios que coordinan las reuniones

Después de haber creado un puente de Audioconferencia, debe establecer los números gratuitos y de pago para los usuarios.

Debe hacer esto para todas las personas de su organización que coordinen o programen reuniones. 

![Un icono que muestra el logotipo de Microsoft Teams ](media/teams-logo-30x30.png) **Mediante el centro de administración de Microsoft Teams**:

1. En el panel, haga clic en **usuarios**, seleccione el usuario de la lista y, a continuación, seleccione**Editar**.
2. Seleccione **Editar** junto a **Audioconferencia** y, a continuación, en el panel de **Audioconferencia**, elija un número en las listas de **Números de pago** y **Números gratuitos**.

Si necesita más detalles, vea [Asignar a Microsoft como proveedor de audioconferencias](/skypeforbusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider).


## <a name="step-8-set-up-meeting-invitations-optional"></a>Paso 8: configurar las invitaciones a reuniones (opcional)
<a name="__top"> </a>
 
Los números de acceso telefónico que se establecen para el usuario se agregan automáticamente a las invitaciones de las reuniones que se envían a los asistentes. Sin embargo, puede agregar sus propios vínculos de ayuda y de avisos legales, un mensaje de texto y un pequeño distintivo gráfico de la empresa. Vea [Personalizar invitaciones a reuniones](meeting-settings-in-teams.md#customize-meeting-invitations)
   
## <a name="related-topics"></a>Temas relacionados

[Preguntas frecuentes sobre Audioconferencia](audio-conferencing-common-questions.md)
  
[Números de teléfono para Audioconferencia en Microsoft Teams](phone-numbers-for-audio-conferencing-in-teams.md)
  
[Establecer opciones para reuniones y conferencias telefónicas en línea](https://support.office.com/article/DCD1CA39-0C1F-466C-9573-F04138FEF5E2)
