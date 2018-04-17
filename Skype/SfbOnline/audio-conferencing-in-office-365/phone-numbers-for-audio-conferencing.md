---
title: Números de acceso telefónico local disponibles para conferencias de acceso telefónico local
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 95a08f84-04e5-4f72-88a8-d6472a7c89d7
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
f1keywords: None
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
- LIL_Placement
description: Learn what countries and regions have dial-in conferencing numbers, and how they are automatically assigned.
ms.openlocfilehash: 9b1fca6a576a9de77e74bcab8df740b5106cf5bc
ms.sourcegitcommit: dea27df69d948b7b9cc017b7023c4013cee8e4d1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/16/2018
---
# <a name="phone-numbers-for-audio-conferencing"></a>Números de acceso telefónico local disponibles para conferencias de acceso telefónico local

When you are setting up **Audio Conferencing** for Skype for Business and Microsoft Teams, dial-in phone numbers are automatically assigned to your organization. Para ver los números de teléfono que se han asignado a su puente de conferencia de acceso telefónico local, vaya al **Centro de administración de Skype Empresarial** > **Conferencia de acceso telefónico local** > **Puente de Microsoft**. See [See a list of Audio Conferencing numbers](see-a-list-of-audio-conferencing-numbers.md).
  
> [!NOTE]
> No existe un recurso que incluya un listado con todos los números de acceso telefónico local de Audioconferencia. If you want to see if there are dial-in phone numbers available in your area or country/region, use the **Skype for Business admin center** > **Voice** > **Phone Numbers**, click **Add**, and then click **New Service Numbers**. Use las listas de **País o región**, **Estado o región** y **Ciudad** para filtrar la búsqueda. Also, if you are looking for toll-free service numbers, select **Toll-Free** from the **State/Region** list.
  
## <a name="audio-conferencing-coverage-and-pricing"></a>Audio Conferencing coverage and pricing

For a complete list of all the countries/regions and cities where Audio Conferencing is available, see [Countries and region availability for Audio Conferencing and Calling Plans](../country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md). For pricing information, see 
  
[Precios de Audioconferencia](https://products.office.com/en-us/skype-for-business/audio-conferencing#Requirements)
  
## <a name="dial-in-phone-numbers-in-a-meeting-invite"></a>Números de teléfono de acceso telefónico local en la invitación a la reunión

Cuando un usuario de Skype Empresarial Online programa una reunión en Outlook o en Outlook Web App, en la invitación a la reunión se incluye el número predeterminado de la conferencia de acceso telefónico local que se ha configurado para el usuario. Si quiere seleccionar un número predeterminado distinto para uno o más usuarios, puede cambiarlo en el **Centro de administración de Skype Empresarial** > **Conferencia de acceso telefónico local** > **Usuarios de acceso telefónico local**. See [Set the phone numbers included on invites](set-the-phone-numbers-included-on-invites.md).
  
Para ver otros números de acceso telefónico local, haga clic en el vínculo **Buscar un número local** en la invitación a la reunión.
  
## <a name="dial-in-phone-numbers-set-on-an-audio-conferencing-bridge"></a>Dial-in phone numbers set on an audio conferencing bridge

Existen dos tipos de números de teléfono de conferencias de acceso telefónico local que se pueden asignar a su puente de conferencias: **compartido** y **dedicado**. Ambos tipos los puede usar cualquier persona que llame para unirse a reuniones de acceso telefónico local que se realicen en su organización.
  
 Los **números de teléfono dedicados** son aquellos que solo están disponibles para los usuarios de su organización. Los idiomas que se emplean cuando alguien llama a uno de estos números se pueden cambiar.
  
 Los **números de teléfono compartidos** son aquellos números de teléfono que se pueden compartir con otras organizaciones de Office 365. No es posible cambiar los idiomas que se emplean cuando alguien llama a uno de estos números.
  
Si bien el número de conferencia de acceso telefónico local que se asigna a un organizador es el único que se incluye en la invitación de la reunión, la persona que llama puede usar cualquiera de los números de teléfono que están asignados al puente de conferencia para unirse a una reunión. La lista de estos números de teléfono que se pueden usar para unirse a una reunión está disponible en el vínculo **Buscar un número local** que se incluye en cada invitación a una reunión.
  
## <a name="automatically-assigned-audio-conferencing-phone-numbers"></a>Números de teléfono de conferencias de acceso telefónico local asignados automáticamente

Los números de teléfono de las conferencias de acceso telefónico local compartidos se asignan automáticamente a las organizaciones cuando estas están habilitadas para dicho tipo de conferencias. Cuando se asignan los números de teléfono, uno se asigna como el número de teléfono predeterminado del puente de conferencias. Este número será del país o la región de la organización.
  
> [!NOTE]
> The country or region location of your organization can be found by signing in to the **Office 365 admin center** and looking under **Organization Profile**. 
  
> [!CAUTION]
> Due to limited availability of toll phone numbers in Venezuela, Indonesia, and United Arab Emirates (UAE), organizations from these countries/regions won't have an Audio Conferencing toll number automatically assigned to them. Los números de teléfono gratuitos de estos lugares estarán disponibles según el inventario existente. 
  
Dedicated audio conferencing phone numbers are service numbers that you can get and then assign to your organization. Service numbers can be found by using the **Skype for Business admin center**. For details, see [Getting service phone numbers for Skype for Business and Microsoft Teams](../what-is-phone-system-in-office-365/getting-service-phone-numbers.md).
  
To see a list of those countries/regions that have phone numbers automatically assigned to organizations, see [Country and region availability for Audio Conferencing and Calling Plans](../country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md).
  
## <a name="what-else-should-you-know"></a>¿Qué más tengo que saber?

- To see the list of supported languages for audio conferencing, see [Audio Conferencing supported languages](audio-conferencing-supported-languages.md).
    
- Puede usar el cmdlet [Get-CsOnlineDialInConferencingServiceNumber](https://go.microsoft.com/fwlink/?LinkId=617691) para ver los números de teléfono dedicados para conferencia de acceso telefónico local de su organización.
    
- Puede usar el cmdlet [Get-CsOnlineDialInConferencingLanguagesSupported](https://go.microsoft.com/fwlink/?LinkId=617684) para ver los idiomas que se pueden establecer en un número de teléfono de acceso telefónico local dedicado.
    
- Puede configurar hasta 4 idiomas para cada número de teléfono de conferencia de acceso telefónico local: uno principal y tres secundarios. Además, también puede establecer idiomas en un número de teléfono dedicado para conferencia de acceso telefónico local.
    
- To set the dial-in phone number for a user, see [Set the phone numbers included on invites](set-the-phone-numbers-included-on-invites.md).
    
[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]
   
## <a name="related-topics"></a>See also

[Probar o comprar Audioconferencia en Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
