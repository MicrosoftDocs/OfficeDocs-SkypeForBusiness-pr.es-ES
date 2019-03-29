---
title: Establecer una conferencia de Audio para Microsoft Teams
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
- Teams_ITAdmin_Help
- M365-collaboration
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
- LIL_Placement
description: 'Obtenga información sobre cómo configurar acceso telefónico o conferencias de Audio para las personas de su empresa que necesitan utilizar un teléfono para unirse a llamadas de conferencia. '
ms.openlocfilehash: 30e79282f04c2d1b4dc7ff01673461b7a18254fd
ms.sourcegitcommit: 188c57e6b6c707edb694bb922556dea1c4724846
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/29/2019
ms.locfileid: "30955033"
---
# <a name="set-up-audio-conferencing-for-microsoft-teams"></a>Establecer una conferencia de Audio para Microsoft Teams

En algunas ocasiones, en su organización se necesitará un teléfono para llamar a una reunión. ¡Microsoft Teams incluye la característica de conferencia de audio para justo esta situación! Personas puedan llamar a las reuniones, los equipos con un teléfono, en lugar de usar la aplicación de los equipos en un dispositivo móvil o un PC. 
  
Solo debe configurar las audioconferencias para los usuarios que van a programar o dirigir las reuniones. Los asistentes que se conectan por teléfono a la reunión no necesitan tener asignada ninguna licencia ni otra configuración.
  
Para ver las preguntas más frecuentes acerca de las audioconferencias, consulte [Preguntas frecuentes sobre audioconferencias](audio-conferencing-common-questions.md).

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="step-1-find-out-if-audio-conferencing-is-available-in-your-countryregion"></a>Paso 1: averiguar si Audioconferencia está disponible en su país o región
<a name="__top"> </a>

Vaya a la [Disponibilidad de país y región para Audioconferencia y Planes de llamadas](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md) y seleccione su país o región para obtener información sobre la disponibilidad de Audioconferencia, así como información sobre Sistema telefónico, Planes de llamadas, números gratuitos y de pago, y Créditos de comunicaciones. 
 
## <a name="step-2-get-and-assign-licenses"></a>Paso 2: obtener licencias y asignarlas
 
1. Para Audioconferencia, necesita una licencia para cada usuario que vaya a configurar reuniones de acceso telefónico. Para obtener información sobre las licencias que necesitará comprar para las conferencias de Audio y cuánto de costo, vea [licencias de complemento de equipos de Microsoft](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).

    >[!NOTE] 
    > Conferencias de audio se incluye en las licencias de Office 365 Enterprise E5 y como un complemento.
        
2. Después de adquirir las licencias de conferencias de Audio, necesita asignarlas a aquellas personas de la organización que se van a programar o potenciales de las reuniones. Vea [asignar licencias a los usuarios de Office 365 para la empresa](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc) ha comprado a las personas de la organización que se van a las reuniones de programación o cliente potencial.
    
3. También se recomienda que asigne licencias de Créditos de comunicaciones (que no cuesta nada) a los mismos usuarios que asignó licencias en el paso anterior. Para obtener información sobre cómo configurar comunicaciones créditos, vea [Configurar Communications créditos para su organización](set-up-communications-credits-for-your-organization.md).
    
> [!NOTE]
> También puede establecer una [Conferencia de Audio de pago por minuto](audio-conferencing-pay-per-minute.md).

## <a name="step-3-get-service-numbers-for-your-conferencing-bridges"></a>Paso 3: obtener los números de servicio para el puente de conferencia
<a name="__top"> </a>

En Audioconferencia, no puede usar números de teléfono para los usuarios; debe obtener números de servicio. Puede obtener números de pago o números gratuitos de servicio para el puente de conferencia. Hay tres formas de obtene números de servicio gratuitos y de pago: 
  
- **Usar el centro de administración de equipos de Microsoft**. Para algunos países o regiones, puede obtener los números de servicio para el puente de conferencia mediante el centro de administración de Microsoft Teams. Vea [los números de teléfono del servicio de introducción](https://docs.microsoft.com/SkypeForBusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json).
    
- **Puerto sus números de servicio existente**. El puerto o transferir los números existentes desde su proveedor de servicio actual o el operador de teléfono a Office 365. Consulte [Transferir números de teléfono a Office 365](transfer-phone-numbers-to-office-365.md) o [Administrar los números de teléfono de su organización](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) para obtener más información que le ayude a hacer esto.  
  
- **Usar un formulario de solicitud para los nuevos números**. A veces (dependiendo de su país o región) no podrá obtener los nuevos números de servicio mediante el centro de administración de Microsoft Teams o necesitará determinados números de teléfono o códigos de área. En ese caso, tendrá que descargar un formulario y enviárnoslo. Para obtener más información, vea [Administrar los números de teléfono de su organización](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md). 
    
## <a name="step-4-assign-a-service-number-to-the-conferencing-bridge"></a>Paso 4: asignar un número de servicio al puente de conferencia
<a name="__top"> </a>

Una vez que obtenga su teléfono de pago o números de teléfono gratuito para el puente de conferencia, debe asignar los números de modo que se pueden usar en las invitaciones a reuniones.  

Siga estos stesps para asignar a un nuevo número de teléfono para el puente de conferencia de audio.

![logotipo-sfb-30x30.png](media/sfb-logo-30x30.png) **utilizando el Skype para el centro de administración de negocio:**

 1. Vaya al **Centro de administración de Microsoft 365** > **centros de administración** > **equipos** > **portal heredado**.
 2. Seleccione **voz** > **los números de teléfono**.
 3. Seleccione el número de teléfono y haga clic en **asignar**.

Para obtener más información, vea [cambiar los números de teléfono en el puente de conferencia de Audio](change-the-phone-numbers-on-your-audio-conferencing-bridge.md).

## <a name="step-5-set-the-default-and-alternate-languages-for-a-conferencing-bridge"></a>Paso 5: establecer el valor predeterminado e idiomas alternativos para un puente de conferencia
<a name="__top"></a> a continuación, en el que desea [establecer auto attendant idiomas para conferencias de Audio en los equipos de Microsoft](set-auto-attendant-languages-for-audio-conferencing-in-teams.md) que usa el operador automático de conferencia para saludar a los autores de llamadas cuando conectan a un número de teléfono para conferencias de Audio. 

![los equipos-logotipo-30x30.png](media/teams-logo-30x30.png) **desde el centro de administración de equipos de Microsoft**:

1. En el panel, vaya a **las reuniones** > **puentes de conferencia**.
2. Seleccione el número de teléfono de puente de conferencia, haga clic en **Editar**y, a continuación, elija el idioma predeterminado.

## <a name="step-6-set-your-conferencing-bridge-settings"></a>Paso 6: configurar el puente de conferencia
<a name="__top"> </a>
    
Después de configurar el puente de conferencia, compruebe que la configuración predeterminada, como las notificaciones de entrada o salida y la longitud PIN, sea la que va a usar; si no lo es, se puede cambiar. 

![los equipos-logotipo-30x30.png](media/teams-logo-30x30.png) **desde el centro de administración de equipos de Microsoft**:

1. En el panel, vaya a **las reuniones** > **puentes de conferencia**.
2. Seleccione **configuración de puente**. Se abrirá el panel **Configuración de puente**. 

Para obtener más información, consulte [Cambiar la configuración de un puente de Audioconferencia](change-the-settings-for-an-audio-conferencing-bridge.md).

## <a name="step-7-assign-dial-in-phone-numbers-for-users-who-lead-meetings"></a>Paso 7: asignar los números de teléfono de acceso telefónico a los usuarios que coordinan las reuniones

Después de haber creado un puente de Audioconferencia, debe establecer los números gratuitos y de pago para los usuarios.

Debe hacer esto para todas las personas de su organización que coordinen o programen reuniones. 

![los equipos-logotipo-30x30.png](media/teams-logo-30x30.png) **desde el centro de administración de equipos de Microsoft**:

1. En el panel, haga clic en **usuarios**, seleccione el usuario en la lista y seleccione **Editar**.
2. Seleccione **Editar** junto a **Conferencias de Audio**y, a continuación, en el panel de **Conferencia de Audio** , elija un número en las listas números de **número de teléfono de pago** y **gratuito** .

Si necesita más detalles, vea [Asignar a Microsoft como proveedor de audioconferencias](/skypeforbusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider).


## <a name="step-8-set-up-meeting-invitations-optional"></a>Paso 8: configurar las invitaciones a reuniones (opcional)
<a name="__top"> </a>
 
Los números de acceso telefónico que se han establecido para el usuario se agregará automáticamente a las invitaciones a reuniones que se envían a los asistentes de la reunión. Sin embargo, puede agregar su propios ayuda y vínculos legal, un mensaje de texto y gráfico de pequeña empresa si lo desea. Vea [Personalizar las invitaciones a reuniones](customize-meeting-invitations.md).
   
## <a name="related-topics"></a>Temas relacionados

[Preguntas comunes sobre Audioconferencia](audio-conferencing-common-questions.md)
  
[Números de teléfono para Audioconferencia en Microsoft Teams](phone-numbers-for-audio-conferencing-in-teams.md)
  
[Establecer opciones para reuniones y conferencias telefónicas en línea](https://support.office.com/article/DCD1CA39-0C1F-466C-9573-F04138FEF5E2)
