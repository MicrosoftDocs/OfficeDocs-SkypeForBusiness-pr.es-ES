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
localization_priority: Normal
f1keywords:
- O365P_DialInConfDesc
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
- LIL_Placement
description: 'Obtenga información acerca de cómo configurar acceso telefónico o audio conferencia para las personas de su empresa que deban unirse a llamadas de conferencia con un teléfono. '
ms.openlocfilehash: f5258ed7f0b056bb9c3381211f5adf3c8ea91715
ms.sourcegitcommit: a0d3e7a177fcd0667ab0d7d0e904f4053b09a92d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2018
---
# <a name="set-up-audio-conferencing-for-skype-for-business-and-microsoft-teams"></a>Configurar conferencias de Audio de Skype para la empresa y Teams de Microsoft

En algunas ocasiones, en su organización se necesitará un teléfono para llamar a una reunión. Skype para empresas y Teams de Microsoft incluyen la característica de conferencia de audio sólo esta situación! La gente puede llamar a Skype para reuniones de negocios o Teams de Microsoft mediante un teléfono, en lugar de utilizar el Skype para negocios o Teams de Microsoft de la aplicación en un dispositivo móvil o PC. 
  
Sólo debe configurar conferencias de Audio para las personas que va a programar o cliente potencial de las reuniones. Asistentes a la reunión que se conectan telefónicamente no necesitan cualquier licencias asignadas a las mismas o a otro programa de instalación.
  
Para las preguntas más frecuentes acerca de las conferencias de Audio, consulte [las preguntas más frecuentes de conferencia de Audio](audio-conferencing-common-questions.md).
  
## <a name="step-1-find-out-if-audio-conferencing-is-available-in-your-countryregion"></a>Paso 1: Averiguar si las conferencias de Audio está disponible en su país o región
<a name="__top"> </a>


Vaya a [disponibilidad de país y región para conferencias de Audio y planes de llamada](../country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md) y seleccione su país o región para obtener la información de disponibilidad acerca de las conferencias de Audio, así como información acerca de llamadas de sistema de teléfono, llamar a los planes y gratis números y créditos de comunicaciones. 
 
## <a name="step-2-get-and-assign-licenses"></a>Paso 2: Obtener y asignar licencias
 
1. Para conferencias de Audio, necesita una licencia para cada usuario que va a configurar reuniones de marcado. Para obtener las licencias que necesita comprar para conferencias de Audio y cuánto de costo, consulte [Skype para negocios y equipos de Microsoft licencias adicionales](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).
        
2. Después de comprar las licencias de las conferencias de Audio, usted podrá ned para asignarlos a aquellas personas de la organización que se van a programar o conducir reuniones. Consulte [asignar o quitar licencias para Office 365 para empresa](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc) adquirió a las personas de la organización que va a las reuniones de programación o cliente potencial.
    
3. También recomendamos que asigne licencias de créditos de comunicaciones (que no cuestan nada) a la misma gente que asignó licencias para en el paso anterior. Para aprender a configurar comunicaciones créditos, consulte [Configurar comunicaciones créditos para su organización](../skype-for-business-and-microsoft-teams-add-on-licensing/set-up-communications-credits-for-your-organization.md).
    
> [!NOTE]
> También puede configurar conferencias de Audio de pago por minuto. Vaya [aquí](../skype-for-business-and-microsoft-teams-add-on-licensing/audio-conferencing-pay-per-minute.md) para obtener más información acerca de cómo utilizarlos.

## <a name="step-3-get-service-numbers-for-your-conferencing-bridges"></a>Paso 3: Obtener números de servicio de los puentes de conferencia
<a name="__top"> </a>

Para conferencias de Audio, no puede utilizar números de teléfono para los usuarios; debe obtener los números de servicio. Puede obtener número o números de servicio gratuito para los puentes de conferencia. Hay tres formas de pago de get y los números de servicio gratuito: 
  
- **Utilice el Skype para el centro de administración de negocios.** Para algunos países o regiones, puede obtener los números de servicio de los puentes de conferencia usando el Skype para el centro de administración de negocios, vea [números de teléfono del servicio de obtención](../what-is-phone-system-in-office-365/getting-service-phone-numbers.md).
    
- **Los números de servicio existente de puerto.** Puerto o transferir números existentes desde su actual proveedor de servicios o la compañía de teléfono para Office 365. Puede ver [transferir números de teléfono a Office 365](../what-are-calling-plans-in-office-365/transfer-phone-numbers-to-office-365.md) o [administrar números de teléfono de la organización](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) para obtener más información para ayudarle a hacerlo.  
  
- **Utilizar un formulario de solicitud para nuevos números.** A veces (dependiendo de su país o región) no podrá obtener los nuevos números de servicio utilizando el Skype para el centro de administración de negocios o necesita determinados números de teléfono o códigos de área. En ese caso, tendrá que descargar un formulario y enviárnoslo. Para obtener más información, vea [administrar números de teléfono para su organización](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) . 
    
## <a name="step-4-assign-a-service-number-to-the-conferencing-bridge"></a>Paso 4: Asignar a un número de servicio para el puente de conferencia
<a name="__top"> </a>

Una vez que obtenga el cobro de peajes y números de teléfono gratuitos para el puente de conferencia, debe asignar a los números para que se puedan utilizar en invitaciones a reuniones.  

Para asignar un nuevo número de teléfono para el puente de conferencia de audio, vaya al **Centro de administración de Office 365** > **centra Admin** > **Skype for Business** > **voz** > **números de teléfono**, seleccione el teléfono número y haga clic en **asignar**.

Para obtener más información, vea [asignar a un nuevo número de teléfono para el puente de conferencia de audio](../audio-conferencing-in-office-365/change-the-phone-numbers-on-your-audio-conferencing-bridge.md).

## <a name="step-5-set-the-default-and-alternate-languages-for-a-conferencing-bridge"></a>Paso 5: Establecer los predeterminados y los idiomas alternativos para un puente de conferencia
<a name="__top"> </a>

A continuación, desea [establecer idiomas de operador automático para conferencias de Audio](../audio-conferencing-in-office-365/set-auto-attendant-languages-for-audio-conferencing.md) que utiliza el operador automático de conferencia para saludar a un llamador cuando se conectan a un número de teléfono para las conferencias de Audio. 

Ir al **Centro de administración de Office 365** > **centra Admin** > **Skype para empresas** > **conferencias de Audio** > **configuración de puente de Microsoft**, seleccione el número de teléfono de puente de conferencia y, a continuación, Haga clic en **idiomas**.

## <a name="step-6-set-your-conferencing-bridge-settings"></a>Paso 6: Configurar la conferencia puente
<a name="__top"> </a>
    
Después de configurar el puente de conferencia, compruebe que la configuración predeterminada, como las notificaciones de entrada y salida y PIN es las que desea utilizar; Si no lo está, puede cambiarlos. 

Puede ir al **Centro de administración de Office 365** > **centra Admin** > **Skype for Business** > **conferencias de Audio** > **configuración de puente de Microsoft**. Se abrirá la página de **configuración de puente de Microsoft** . Para obtener más información, vea [cambiar la configuración de un puente de conferencia de Audio](../audio-conferencing-in-office-365/change-the-settings-for-an-audio-conferencing-bridge.md).

## <a name="step-7-assign-the-audio-conferencing-provider-and-dial-in-phone-numbers"></a>Paso 7: Asignar a los números de teléfono de proveedor y de acceso telefónico de conferencia de audio

Ahora debe asegurarse de que Microsoft está asignado como el proveedor y establecer el pago y números de teléfono gratuitos para ellos al mismo tiempo.

Asignar Microsoft como proveedor a las personas de la organización que conducen o programar reuniones, yendo al **Centro de administración de Office 365** > **Skype for Business** > **conferencias de Audio** > **usuarios**y, a continuación, seleccione el usuario de la lista y haga clic en **Editar**. Si necesita más detalles, vea [Asignar Microsoft como proveedor de conferencia de audio](../audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider.md).

Al establecer el proveedor, también puede establecer el número de víctimas e invita los números de teléfono gratuitos que se agregará a la reunión para ese usuario. Simplemente seleccione los números de teléfono de las listas desplegables. Para obtener más detalles, vea [establecer el teléfono invita números incluidos en](../audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites.md). 


## <a name="step-8-set-up-meeting-invitations-optional"></a>Paso 8: Configurar las invitaciones a reuniones (opcional)
<a name="__top"> </a>
 
Los números de acceso telefónico que se establecen para que el usuario se agregará automáticamente las invitaciones a reuniones que se envían a los asistentes. Sin embargo, puede agregar su propia ayuda y vínculos jurídicos, un mensaje de texto y gráfico de pequeña empresa si desea. Consulte [personalizar invitaciones a reuniones](../set-up-skype-for-business-online/customize-meeting-invitations.md).
   
## <a name="related-topics"></a>See also

[Preguntas comunes sobre Audioconferencia](audio-conferencing-common-questions.md)
  
[Configurar Skype Empresarial Online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)
  
[Números de teléfono para Audioconferencia](phone-numbers-for-audio-conferencing.md)
  
[Establecer opciones de reuniones en línea y llamadas de conferencia](https://support.office.com/article/DCD1CA39-0C1F-466C-9573-F04138FEF5E2)
