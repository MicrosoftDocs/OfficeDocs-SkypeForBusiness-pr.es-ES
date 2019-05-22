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
- Teams_ITAdmin_Help
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
- LIL_Placement
description: 'Obtenga información sobre cómo configurar las conferencias de acceso telefónico local o de audio para las personas de su empresa que necesitan usar un teléfono para unirse a llamadas en conferencia. '
ms.openlocfilehash: 41a2d4288185d75bfed4d9882775ba054e2b3ccd
ms.sourcegitcommit: 2f8b9c7c8d20f2605d09cae4bbaeb10667f2ddea
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/21/2019
ms.locfileid: "34329735"
---
# <a name="set-up-audio-conferencing-for-microsoft-teams"></a>Configurar audioconferencias en Microsoft Teams

En algunas ocasiones, en su organización se necesitará un teléfono para llamar a una reunión. Microsoft Teams incluye la característica de audioconferencia solo para esta situación. Los usuarios pueden llamar a las reuniones de Teams mediante un teléfono, en lugar de usar la aplicación de Teams en un dispositivo móvil o PC. 
  
Solo debe configurar las audioconferencias para los usuarios que van a programar o dirigir las reuniones. Los asistentes que se conectan por teléfono a la reunión no necesitan tener asignada ninguna licencia ni otra configuración.
  
Para ver las preguntas más frecuentes acerca de las audioconferencias, consulte [Preguntas frecuentes sobre audioconferencias](audio-conferencing-common-questions.md).

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="step-1-find-out-if-audio-conferencing-is-available-in-your-countryregion"></a>Paso 1: averiguar si Audioconferencia está disponible en su país o región
<a name="__top"> </a>

Vaya a la [Disponibilidad de país y región para Audioconferencia y Planes de llamadas](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md) y seleccione su país o región para obtener información sobre la disponibilidad de Audioconferencia, así como información sobre Sistema telefónico, Planes de llamadas, números gratuitos y de pago, y Créditos de comunicaciones. 
 
## <a name="step-2-get-and-assign-licenses"></a>Paso 2: obtener licencias y asignarlas
 
1. Para Audioconferencia, necesita una licencia para cada usuario que vaya a configurar reuniones de acceso telefónico. Para conocer las licencias que necesita comprar para la audioconferencia y cuánto cuestan, vea [licencias complementarias de Microsoft Teams](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).

    >[!NOTE] 
    > Las conferencias de audio se incluyen en las licencias de Office 365 Enterprise E5 y como complemento.
        
2. Después de comprar las licencias de audioconferencia, tendrá que asignarlas a las personas de su organización que vayan a programar o coordinar reuniones. Consulte [asignar licencias a usuarios en Office 365 para empresas](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc) que compró a las personas de su organización que van a programar o coordinar reuniones.
    
3. También se recomienda que asigne licencias de Créditos de comunicaciones (que no cuesta nada) a los mismos usuarios que asignó licencias en el paso anterior. Para obtener información sobre cómo configurar créditos de comunicaciones, consulte [configurar créditos de comunicaciones para su organización](set-up-communications-credits-for-your-organization.md).
    
> [!NOTE]
> También puedes configurar las [conferencias de audio por minuto](audio-conferencing-pay-per-minute.md).

## <a name="step-3-get-service-numbers-for-your-conferencing-bridges"></a>Paso 3: obtener los números de servicio para el puente de conferencia
<a name="__top"> </a>

En Audioconferencia, no puede usar números de teléfono para los usuarios; debe obtener números de servicio. Puede obtener números de pago o números gratuitos de servicio para el puente de conferencia. Hay tres formas de obtene números de servicio gratuitos y de pago: 
  
- **Use el centro de administración de Microsoft Teams**. Para algunos países o regiones, puede obtener números de servicio para sus puentes de conferencia con el centro de administración de Microsoft Teams. Consulta [obtener números de teléfono de servicio](/microsoftteams/getting-service-phone-numbers).
    
- **Porte los números de servicio existentes**. Para migrar o transferir números existentes de su proveedor de servicios actual u operador telefónico a Office 365. Consulte [Transferir números de teléfono a Office 365](transfer-phone-numbers-to-office-365.md) o [Administrar los números de teléfono de su organización](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) para obtener más información que le ayude a hacer esto.  
  
- **Usar un formulario de solicitud para números nuevos**. A veces, en función de su país o región, no podrá obtener los números de servicio nuevos mediante el centro de administración de Microsoft Teams o necesitará números de teléfono o códigos de área específicos. En ese caso, tendrá que descargar un formulario y enviárnoslo. Para obtener más información, vea [Administrar los números de teléfono de su organización](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md). 
    
## <a name="step-4-assign-a-service-number-to-the-conferencing-bridge"></a>Paso 4: asignar un número de servicio al puente de conferencia
<a name="__top"> </a>

Una vez que haya obtenido sus números de teléfono gratuitos o de pago para su puente de conferencia, tendrá que asignar los números para que puedan usarse en las invitaciones a reuniones.  

Siga estos pasos para asignar un nuevo número de teléfono a su puente de audioconferencia.

![SFB-logo-30x30. png](media/sfb-logo-30x30.png) **con el centro de administración de Skype empresarial:**

 1. Vaya al portal de > **Administración** > de **centro de administración de Microsoft 365****Teams** > **Legacy**.
 2. Seleccione **** > **números de teléfono**de voz.
 3. Seleccione el número de teléfono y haga clic en **asignar**.

Para obtener más información, consulte [cambiar los números de teléfono en el puente de audioconferencia](change-the-phone-numbers-on-your-audio-conferencing-bridge.md).

## <a name="step-5-set-the-default-and-alternate-languages-for-a-conferencing-bridge"></a>Paso 5: establecer el valor predeterminado e idiomas alternativos para un puente de conferencia
<a name="__top"></a> A continuación, desea [configurar los idiomas del operador automático para audioconferencia en Microsoft Teams](set-auto-attendant-languages-for-audio-conferencing-in-teams.md) que el operador automático de conferencias usa para saludar a las personas que llaman a un número de teléfono para las conferencias de audio. 

![Teams-logo-30x30. png](media/teams-logo-30x30.png) **con el centro de administración de Microsoft Teams**:

1. Desde el panel, vaya a conferencias de**Conferencia**de **reuniones** > .
2. Seleccione el número de teléfono del puente de conferencia, haga clic en **Editar**y, a continuación, elija el idioma predeterminado.

## <a name="step-6-set-your-conferencing-bridge-settings"></a>Paso 6: configurar el puente de conferencia
<a name="__top"> </a>
    
Después de configurar el puente de conferencia, compruebe que la configuración predeterminada, como las notificaciones de entrada o salida y la longitud PIN, sea la que va a usar; si no lo es, se puede cambiar. 

![Teams-logo-30x30. png](media/teams-logo-30x30.png) **con el centro de administración de Microsoft Teams**:

1. Desde el panel, vaya a conferencias de**Conferencia**de **reuniones** > .
2. Seleccione **configuración de puente**. Se abrirá el panel **Configuración de puente**. 

Para obtener más información, consulte [Cambiar la configuración de un puente de Audioconferencia](change-the-settings-for-an-audio-conferencing-bridge.md).

## <a name="step-7-assign-dial-in-phone-numbers-for-users-who-lead-meetings"></a>Paso 7: asignar los números de teléfono de acceso telefónico a los usuarios que coordinan las reuniones

Después de haber creado un puente de Audioconferencia, debe establecer los números gratuitos y de pago para los usuarios.

Debe hacer esto para todas las personas de su organización que coordinen o programen reuniones. 

![Teams-logo-30x30. png](media/teams-logo-30x30.png) **con el centro de administración de Microsoft Teams**:

1. En el panel, haga clic en **usuarios**, seleccione el usuario de la lista y seleccione **Editar**.
2. Seleccione **Editar** junto a **audioconferencia**y, en el panel **audioconferencia** , elija un número en las listas número de **teléfono de pago** y número **gratuito** .

Si necesita más detalles, vea [Asignar a Microsoft como proveedor de audioconferencias](/skypeforbusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider).


## <a name="step-8-set-up-meeting-invitations-optional"></a>Paso 8: configurar las invitaciones a reuniones (opcional)
<a name="__top"> </a>
 
Los números de acceso telefónico local establecidos para el usuario se agregarán automáticamente a las invitaciones a reuniones que se envíen a los asistentes de la reunión. Sin embargo, si lo desea, puede agregar su propia ayuda y vínculos legales, un mensaje de texto y un gráfico de pequeña empresa. Consulte [personalizar invitaciones a reuniones](customize-meeting-invitations.md).
   
## <a name="related-topics"></a>Temas relacionados

[Preguntas comunes sobre Audioconferencia](audio-conferencing-common-questions.md)
  
[Números de teléfono para Audioconferencia en Microsoft Teams](phone-numbers-for-audio-conferencing-in-teams.md)
  
[Establecer opciones para reuniones y conferencias telefónicas en línea](https://support.office.com/article/DCD1CA39-0C1F-466C-9573-F04138FEF5E2)
