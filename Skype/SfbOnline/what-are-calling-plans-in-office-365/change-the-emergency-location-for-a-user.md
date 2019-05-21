---
title: Asignar o cambiar la ubicación de emergencia de un usuario
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.assetid: 2d5d3c87-af1e-487e-b86c-261f2e5a0661
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Calling Plans
description: 'Obtenga información sobre cómo cambiar la ubicación de emergencia para los usuarios. Con un número ilimitado de ubicaciones, puede cambiar las ubicaciones de emergencia cuando los empleados cambien de plantas o edificios. '
ms.openlocfilehash: 49410b0ba98e6d193749b558e479d98de1f4ef29
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34303838"
---
# <a name="assign-or-change-the-emergency-location-for-a-user"></a>Asignar o cambiar la ubicación de emergencia de un usuario

Cada número de teléfono activo debe tener una dirección de emergencia asociada al asignar el número de teléfono a un usuario. (La dirección se asocia al obtener un número de teléfono en Office 365 o al transferir un número de teléfono). Cuando asocias el número con una dirección de emergencia, también puedes añadir una ubicación de emergencia para proporcionar una ubicación más exacta dentro de una ubicación física. Una ubicación de emergencia puede ser una planta, el ala de un edificio o un número de oficina donde se encuentra el usuario. Puede tener un número ilimitado de ubicaciones para una determinada dirección de emergencia, y puede cambiar la ubicación de emergencia si el usuario se desplaza a una oficina o edificio diferente: por ejemplo, si el usuario se mueve desde la planta 34 a la planta 35.
  
Para obtener información sobre cómo obtener planes de llamada en Office 365 y su coste, vea [Licencias de complementos de Skype for Business y Microsoft Teams](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).
  
## <a name="assign-or-change-the-emergency-location"></a>Asignar o cambiar la ubicación de emergencia

1. Inicie sesión en Office 365 con su cuenta profesional o educativa.
    
2. Vaya al > **portal heredado**del **centro de administración de Microsoft Teams**.
    
3. En el navegación de la izquierda **** > , vaya a**usuarios de voz**.
    
    > [!IMPORTANT]
    > Para ver la opción de **voz** en el navegación izquierdo en el centro de administración de Skype empresarial, primero debe comprar al menos una **licencia de Enterprise E5**, una licencia de complemento de **sistema de teléfono** o una licencia de complemento de **audioconferencia** .
    
4. En la página **usuarios de voz** , busque y seleccione el usuario para el que desea cambiar la ubicación de emergencia.
    
5. En el panel de acciones, en **Ubicación de emergencia**, haga clic en **Cambiar**.
    
6. En la página **Asignar un número**, haga clic en **Cambiar ubicación**. 
    
7. En **cambiar dirección de emergencia a**, escriba el nombre de la ciudad en el cuadro y haga clic en **Buscar**.

8. Seleccione **Buscar por ubicación** en la lista desplegable, escriba un nombre parcial para la ubicación (por ejemplo, escriba **piso**) y, a continuación, haga clic en **Buscar**. 
    
8. Seleccione la ubicación de emergencia de la lista y, a continuación, haga clic en **Guardar**.
    
    Si quiere agregar una nueva ubicación de emergencia que aparecerá en la lista, vea [Agregar, cambiar o quitar una ubicación de emergencia para su organización](add-change-or-remove-an-emergency-location-for-your-organization.md).
    
## <a name="related-topics"></a>Temas relacionados

[Asignar una ubicación de respuesta de emergencia a través de PowerShell](https://github.com/MicrosoftDocs/office-docs-powershell/blob/master/skype/skype-ps/skype/Set-CsOnlineVoiceUser.md)

[Agregar o quitar una dirección de emergencia para su organización](add-or-remove-an-emergency-address-for-your-organization.md)

[Agregar, cambiar o quitar una ubicación de emergencia para su organización](add-change-or-remove-an-emergency-location-for-your-organization.md)

[¿Qué es la validación de direcciones?](what-is-address-validation.md)

[Administrar los números de teléfono para su organización](/microsoftteams/manage-phone-numbers-for-your-organization)

[Términos y condiciones de las llamadas de emergencia](/microsoftteams/emergency-calling-terms-and-conditions)

[Skype Empresarial Online: Etiqueta de aviso de declinación de responsabilidades de las llamadas de emergencia](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

[Cmdlet Set-CsOnlineVoiceUser](https://docs.microsoft.com/en-us/powershell/module/skype/set-csonlinevoiceuser?view=skype-ps)

  
 
