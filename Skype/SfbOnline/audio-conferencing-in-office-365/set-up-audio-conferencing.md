---
title: Configurar conferencias de Audio de Skype para la empresa y Teams de Microsoft
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: d01954f1-4f37-4cf5-a636-20039e5c59e9
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
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
description: 'Obtenga información sobre cómo configurar conferencia de acceso telefónico o de audio para las personas de su empresa que necesitan para unirse a llamadas de conferencia utilizando un teléfono. '
ms.openlocfilehash: 52872b9995d5973ee872e3105c870ccf7bb07abc
ms.sourcegitcommit: 527c7dd4c5edc70503ba31e7c689a71d7356b17e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2018
ms.locfileid: "19703488"
---
# <a name="set-up-audio-conferencing-for-skype-for-business-and-microsoft-teams"></a>Configurar conferencias de Audio de Skype para la empresa y Teams de Microsoft

En algunas ocasiones, en su organización se necesitará un teléfono para llamar a una reunión. Skype para empresas y Microsoft Teams incluye la característica de conferencia de audio para justo esta situación! Personas puedan llamar a Skype para reuniones profesionales o Teams de Microsoft mediante un teléfono, en lugar de usar el Skype para una aplicación empresarial o Teams de Microsoft en un dispositivo móvil o un PC. 
  
Sólo necesita configurar conferencias de Audio para las personas que va a programar o potenciales de las reuniones. Asistentes a la reunión que se conectan no necesitan ninguna licencia asignada a ellos u otro programa de instalación.
  
Para las preguntas más frecuentes acerca de las conferencias de Audio, consulte [las preguntas más frecuentes de conferencias de Audio](audio-conferencing-common-questions.md).

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="step-1-find-out-if-audio-conferencing-is-available-in-your-countryregion"></a>Paso 1: Averiguar si la conferencia de Audio está disponible en su país o región
<a name="__top"> </a>


Vaya a la [disponibilidad de país y región para las conferencias de Audio y llamar a los planes](../country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md) y seleccione su país o región para obtener información sobre la disponibilidad acerca de las conferencias de Audio, así como información sobre el pago de sistema de teléfono, planes de llamada y gratuito los números y créditos Communications. 
 
## <a name="step-2-get-and-assign-licenses"></a>Paso 2: Obtener y asignar licencias
 
1. Para conferencias de Audio, necesita una licencia para cada usuario que va a configurar acceso telefónico en las reuniones. Para obtener información sobre las licencias que necesitará comprar para las conferencias de Audio y cuánto de costo, vea [Skype para profesionales y los equipos de Microsoft complemento licencias](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).
        
2. Después de adquirir las licencias de conferencias de Audio, usted podrá ned para asignarlas a aquellas personas de la organización que se van a programar o potenciales de las reuniones. Vea [asignar o quitar licencias de Office 365 para profesionales](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc) ha comprado a las personas de la organización que se van a las reuniones de programación o cliente potencial.
    
3. También se recomienda que asigne licencias de créditos Communications (que no cuesta nada) a los mismos usuarios que asignó licencias a en el paso anterior. Para obtener información sobre cómo configurar comunicaciones créditos, vea [Configurar Communications créditos para su organización](../skype-for-business-and-microsoft-teams-add-on-licensing/set-up-communications-credits-for-your-organization.md).
    
> [!NOTE]
> También puede establecer una conferencia de Audio de pago por minuto. Vaya [aquí](../skype-for-business-and-microsoft-teams-add-on-licensing/audio-conferencing-pay-per-minute.md) para obtener más información acerca de cómo usarlas.

## <a name="step-3-get-service-numbers-for-your-conferencing-bridges"></a>Paso 3: Obtener los números de servicio para el puente de conferencia
<a name="__top"> </a>

Para conferencias de Audio, no se puede usar los números de teléfono para los usuarios; debe obtener los números de servicio. Puede obtener números de pago o números de teléfono gratuito de servicio para el puente de conferencia. Hay tres formas de pago de get y los números de teléfono gratuito de servicio: 
  
- **Use el Skype para el centro de administración de negocio.** Para algunos países o regiones, puede obtener los números de servicio para el puente de conferencia utilizando el Skype para el centro de administración de negocio, vea [números de teléfono del servicio de introducción](../what-is-phone-system-in-office-365/getting-service-phone-numbers.md).
    
- **Puertos de sus números de servicio existente.** El puerto o transferir los números existentes desde su proveedor de servicio actual o el operador de teléfono a Office 365. Puede ver la [transferencia de números de teléfono para Office 365](../what-are-calling-plans-in-office-365/transfer-phone-numbers-to-office-365.md) o [administrar los números de teléfono para su organización](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) para obtener más información que le ayudarán a hacer esto.  
  
- **Usar un formulario de solicitud para los nuevos números.** A veces (dependiendo de su país o región) no podrá obtener sus números de servicio nueva mediante el Skype para el centro de administración de negocio o necesitará determinados números de teléfono o códigos de área. En ese caso, tendrá que descargar un formulario y enviárnoslo. Para obtener más información, vea [administrar los números de teléfono para su organización](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) . 
    
## <a name="step-4-assign-a-service-number-to-the-conferencing-bridge"></a>Paso 4: Asignar a un número de servicio para el puente de conferencia
<a name="__top"> </a>

Una vez que obtenga su teléfono de pago o números de teléfono gratuito para el puente de conferencia, debe asignar los números de modo que se pueden usar en invitaciones a reuniones.  

Para asignar a un nuevo número de teléfono para el puente de conferencia de audio:

![logotipo-sfb-30x30.png](../images/sfb-logo-30x30.png) **utilizando el Skype para el centro de administración de negocio:**

 Vaya al **Centro de administración de Office 365** > **centros de administración** > **Skype para la empresa** > **voz** > **los números de teléfono**, seleccione el número de teléfono y haga clic en **asignar**.

Para obtener más información, vea [asignar a un nuevo número de teléfono para el puente de conferencia de audio](../audio-conferencing-in-office-365/change-the-phone-numbers-on-your-audio-conferencing-bridge.md).

## <a name="step-5-set-the-default-and-alternate-languages-for-a-conferencing-bridge"></a>Paso 5: Establecer el valor predeterminado e idiomas alternativos para un puente de conferencia
<a name="__top"> </a>

A continuación, va a [establecer idiomas de operador automático para conferencias de Audio](../audio-conferencing-in-office-365/set-auto-attendant-languages-for-audio-conferencing.md) que usa el operador automático de conferencia para saludar a un autor de la llamada cuando conectan a un número de teléfono para conferencias de Audio. 

![los equipos-logotipo-30x30.png](../images/teams-logo-30x30.png) **mediante el Microsoft Teams y Skype para centro de administración de negocio:**

En el panel, vaya a **las reuniones** > **puentes de conferencia**, seleccione el número de teléfono de puente de conferencia, haga clic en **Editar**y, a continuación, elija el idioma predeterminado.

![logotipo-sfb-30x30.png](../images/sfb-logo-30x30.png) **utilizando el Skype para el centro de administración de negocio:**

Vaya al **Centro de administración de Office 365** > **centros de administración** > **Skype para la empresa** > **conferencias de Audio** > **configuración de puente de Microsoft**, seleccione el número de teléfono de puente de conferencia y, a continuación, Haga clic en **conjunto de idiomas**.

## <a name="step-6-set-your-conferencing-bridge-settings"></a>Paso 6: Configurar la conferencia puente
<a name="__top"> </a>
    
Después de configurar el puente de conferencia, compruebe que la configuración predeterminada, como las notificaciones de entrada o salida y longitud PIN es las que va a usar; Si no lo está, se puede cambiar. 

![los equipos-logotipo-30x30.png](../images/teams-logo-30x30.png) **mediante el Microsoft Teams y Skype para centro de administración de negocio:**

En el panel, vaya a **las reuniones** > **puentes de conferencia** > **configuración de puente**. Se abrirá el panel **configuración de puente** . Para obtener más información, vea [cambiar la configuración de un puente de conferencia de Audio](../audio-conferencing-in-office-365/change-the-settings-for-an-audio-conferencing-bridge.md).

![logotipo-sfb-30x30.png](../images/sfb-logo-30x30.png) **utilizando el Skype para el centro de administración de negocio:**

Vaya al **Centro de administración de Office 365** > **centros de administración** > **Skype para la empresa** > **conferencias de Audio** > **configuración de puente de Microsoft**. Se abrirá la página de **configuración de puente de Microsoft** . Para obtener más información, vea [cambiar la configuración de un puente de conferencia de Audio](../audio-conferencing-in-office-365/change-the-settings-for-an-audio-conferencing-bridge.md).

## <a name="step-7-assign-dial-in-phone-numbers-for-users-who-lead-meetings"></a>Paso 7: Asignar marcado de teléfono para números para los usuarios potenciales de las reuniones

Después de haber creado un puente de conferencia de Audio, debe establecer el teléfono de pago y los números gratuitos para los usuarios.

Debe hacer esto para todas las personas de su organización que potenciales o programar reuniones. Para hacer esto:

![los equipos-logotipo-30x30.png](../images/teams-logo-30x30.png) **mediante el Microsoft Teams y Skype para centro de administración de negocio:**

En el panel, haga clic en **usuarios**, seleccione el usuario en la lista, haga clic en **Editar**, haga clic en **Editar** junto a **Conferencias de Audio**y, a continuación, en el panel de **Conferencia de Audio** , elija un número en el **número de teléfono de pago** y ** Gratuito** listas de número.

![logotipo-sfb-30x30.png](../images/sfb-logo-30x30.png) **utilizando el Skype para el centro de administración de negocio:**

Vaya al **Centro de administración de Office 365** > **Skype para la empresa** > **conferencias de Audio** > **a los usuarios**y, a continuación, seleccione el usuario en la lista y haga clic en **Editar**. Si necesita más detalles, vea [Asignar Microsoft como proveedor de conferencias de audio](../audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider.md).


## <a name="step-8-set-up-meeting-invitations-optional"></a>Paso 8: Configurar las invitaciones a reuniones (opcional)
<a name="__top"> </a>
 
Los números de acceso telefónico que se han establecido para el usuario se agregará automáticamente a las invitaciones a reuniones que se envían a los asistentes de la reunión. Sin embargo, puede agregar su propios ayuda y vínculos legal, un mensaje de texto y gráfico de pequeña empresa si lo desea. Vea [Personalizar las invitaciones a reuniones](../set-up-skype-for-business-online/customize-meeting-invitations.md).
   
## <a name="related-topics"></a>See also

[Preguntas comunes sobre Audioconferencia](audio-conferencing-common-questions.md)
  
[Configurar Skype Empresarial Online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)
  
[Números de teléfono para Audioconferencia](phone-numbers-for-audio-conferencing.md)
  
[Establecer las opciones para llamadas de conferencia y reuniones en línea](https://support.office.com/article/DCD1CA39-0C1F-466C-9573-F04138FEF5E2)
