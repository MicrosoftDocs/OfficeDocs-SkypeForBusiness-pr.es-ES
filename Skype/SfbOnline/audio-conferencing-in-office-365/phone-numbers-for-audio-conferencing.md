---
title: Números de teléfono para Audioconferencia en Skype for Business Online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 95a08f84-04e5-4f72-88a8-d6472a7c89d7
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
f1keywords: None
ms.custom:
- Audio Conferencing
- LIL_Placement
description: Obtenga información sobre qué países y regiones tienen números de conferencia de marcado, y cómo asignarlos automáticamente.
ms.openlocfilehash: feaa7972766ffeb21517080e97ee67dcd597edb4
ms.sourcegitcommit: 7d85a6784a21aec20dcaddd8940ffe95d532c2f4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/22/2019
ms.locfileid: "35134256"
---
# <a name="phone-numbers-for-audio-conferencing-in-skype-for-business-online"></a>Números de teléfono para Audioconferencia en Skype for Business Online

> [!NOTE]
> Para obtener información acerca de los números de teléfono en Microsoft Teams, vea [Números de teléfono para Audioconferencia en Microsoft Teams](/MicrosoftTeams/phone-numbers-for-audio-conferencing-in-teams).

When you are setting up **Audio Conferencing** for Skype for Business, dial-in phone numbers are automatically assigned to your organization. You can see the phone numbers that are assigned to your audio conferencing bridge by going to the **Skype for Business admin center** > **Audio conferencing** > **Microsoft bridge**. See [See a list of Audio Conferencing numbers](see-a-list-of-audio-conferencing-numbers.md).
  
> [!NOTE]
> There isn't a resource that contains a listing of all of the dial-in numbers for Audio Conferencing. If you want to see if there are dial-in phone numbers available in your area or country/region, use the **Skype for Business admin center** > **Voice** > **Phone Numbers**, click **Add**, and then click **New Service Numbers**. Use the lists for **Country/Region**, **State/Region**, and **City** to filter your search. Also, if you are looking for toll-free service numbers, select **Toll-Free** from the **State/Region** list.
  
## <a name="audio-conferencing-coverage-and-pricing"></a>Cobertura y precios de Audioconferencia

For a complete list of all the countries/regions and cities where Audio Conferencing is available, see [Countries and region availability for Audio Conferencing and Calling Plans](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans). For pricing information, see [Pricing for Audio Conferencing](https://products.office.com/en-us/skype-for-business/audio-conferencing#Requirements).
  
## <a name="dial-in-phone-numbers-in-a-meeting-invite"></a>Números de teléfono de acceso telefónico local en la invitación a la reunión

When a Skype for Business Online user schedules a meeting in Outlook or Outlook Web App, the default audio conferencing number that is set for the user is included in the meeting invite. If you want to select a different default number for one or more users, you can change that by going to the **Skype for Business admin center** > **Audio conferencing** > **Users**. See [Set the phone numbers included on invites](set-the-phone-numbers-included-on-invites.md).
  
Para ver otros números de acceso telefónico local, haga clic en el vínculo **Buscar un número local** en la invitación a la reunión.
  
## <a name="dial-in-phone-numbers-set-on-an-audio-conferencing-bridge"></a>Números de teléfono de acceso telefónico local establecidos en un puente de audioconferencia

Existen dos tipos de números de teléfono de conferencias de acceso telefónico local que se pueden asignar a su puente de conferencias: **compartido** y **dedicado**. Ambos tipos los puede usar cualquier persona que llame para unirse a reuniones de acceso telefónico local que se realicen en su organización.
  
 Los **números de teléfono dedicados** son aquellos que solo están disponibles para los usuarios de su organización. Los idiomas que se emplean cuando alguien llama a uno de estos números se pueden cambiar.
  
 Los **números de teléfono compartidos** son aquellos números de teléfono que se pueden compartir con otras organizaciones de Office 365. No es posible cambiar los idiomas que se emplean cuando alguien llama a uno de estos números.
  
Si bien el número de conferencia de acceso telefónico local que se asigna a un organizador es el único que se incluye en la invitación de la reunión, la persona que llama puede usar cualquiera de los números de teléfono que están asignados al puente de conferencia para unirse a una reunión. La lista de estos números de teléfono que se pueden usar para unirse a una reunión está disponible en el vínculo **Buscar un número local** que se incluye en cada invitación a una reunión.
  
## <a name="automatically-assigned-audio-conferencing-phone-numbers"></a>Números de teléfono de conferencias de acceso telefónico local asignados automáticamente

Los números de teléfono de las conferencias de acceso telefónico local compartidos se asignan automáticamente a las organizaciones cuando estas están habilitadas para dicho tipo de conferencias. Cuando se asignan los números de teléfono, uno se asigna como el número de teléfono predeterminado del puente de conferencias. Este número será del país o la región de la organización.
  
> [!NOTE]
> La ubicación del país o la región de su organización se puede encontrar iniciando sesión en el **centro de administración de Office 365** y buscando en Perfil de la **organización**. 
  
> [!CAUTION]
> Debido a la disponibilidad limitada de números de teléfono de pago en Venezuela, Indonesia, Vietnam, y los Emiratos Árabes Unidos (EAU), las organizaciones de estos países o regiones no tienen asignado automáticamente un número de teléfono de audioconferencia. Los números de teléfono gratuitos de estos lugares estarán disponibles según el inventario existente. 
  
Dedicated audio conferencing phone numbers are service numbers that you can get and then assign to your organization. Service numbers can be found by using the **Skype for Business admin center**. For details, see [Getting service phone numbers](/microsoftteams/getting-service-phone-numbers).
  
Para ver una lista de los países o regiones en los que se asignan automáticamente números de teléfono a las organizaciones, vea [Disponibilidad de país y región para Audioconferencia y Planes de llamada](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans).
  
## <a name="what-else-should-you-know"></a>¿Qué más debe saber?

- Para ver la lista de los idiomas admitidos para audioconferencia, consulte [idiomas compatibles con audioconferencia](/MicrosoftTeams/audio-conferencing-supported-languages).
    
- Puede usar el cmdlet [Get-CsOnlineDialInConferencingServiceNumber](https://go.microsoft.com/fwlink/?LinkId=617691) para ver los números de teléfono dedicados para conferencia de acceso telefónico local de su organización.
    
- Puede usar el cmdlet [Get-CsOnlineDialInConferencingLanguagesSupported](https://go.microsoft.com/fwlink/?LinkId=617684) para ver los idiomas que se pueden establecer en un número de teléfono de acceso telefónico local dedicado.
    
- You can set up to four languages for each audio conferencing phone number - one primary and three secondary. And you can also set languages on a dedicated audio conferencing phone number.
    
- Para establecer el número de teléfono de acceso telefónico local de un usuario, vea [establecer los números de teléfono incluidos en los invitados](set-the-phone-numbers-included-on-invites.md).
    
[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]
   
## <a name="related-topics"></a>Temas relacionados

[Probar o comprar Audioconferencia en Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
