---
title: Agregar, cambiar o quitar una dirección de emergencia para su organización
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.assetid: f954c67c-b73c-4473-b6cd-a0fbcd0fd4c9
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
description: 'Aprenda cómo agregar una dirección de emergencia a su cuenta de Skype for Business. '
ms.openlocfilehash: 5c22875873d2164c14d690523404481a514ef388
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34293739"
---
# <a name="add-change-or-remove-an-emergency-address-for-your-organization"></a>Agregar, cambiar o quitar una dirección de emergencia para su organización

Una dirección de emergencia debe estar asociada a un número de teléfono, pero cuando esto sucede puede variar entre el país o las regiones. Por ejemplo, en los Estados Unidos, debe asociar una dirección de emergencia al asignar el número de teléfono al usuario. En el Reino Unido, debe asociar una dirección de emergencia al número de teléfono al obtener los números de teléfono de Office 365 o transferir los números de teléfono de su proveedor de servicio actual.
  
No matter which country/region you are in, it's possible to add a location or locations to an emergency address or remove an emergency address. Depending on the number of physical locations in your organization, you can create them for buildings, floors, and offices. See [What are emergency locations, addresses, and call routing?](/microsoftteams/what-are-emergency-locations-addresses-and-call-routing) for some details.
  
Para obtener información sobre cómo obtener planes de llamadas y su coste, vea [Licencias de complementos de Skype for Business y Microsoft Teams](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).
  
## <a name="add-an-emergency-address"></a>Agregar una dirección de emergencia

1. Inicie sesión en Office 365 con su cuenta profesional o educativa.
    
2. Vaya al > **portal heredado**del **centro de administración de Microsoft Teams**.
    
3. En el panel de navegación izquierdo, vaya a VozUbicaciones de emergenciay, a continuación, haga clic en el botón Agregar nueva dirección.** **  >  ** ** ** **
    
    > [!Important]
    > Para ver la opción de **voz** en el navegación izquierdo en el centro de administración de Skype empresarial, primero debe comprar al menos una **licencia de Enterprise E5**, una licencia de complemento de **sistema de teléfono** o una licencia de complemento de **audioconferencia** .
    
4. En el Panel de acciones, en **Nueva dirección**, escriba la información necesaria en las casillas.
    
5. Después de escribir toda la información de la dirección, haga clic en **validar**.
    
    > [!IMPORTANT]
    > Validar una dirección civil o postal implica asegurarse de que sea legítima y tenga el formato correcto. Es posible que una dirección de emergencia parcialmente correcta, por ejemplo con el nombre de la ciudad mal escrito, pueda seguir pasando como válida. Incluso si está mal escrita, pero pasó la validación, la combinación del nombre de la ciudad mal escrito junto con las demás partes correctas de la dirección constituye información suficiente para dirigir la llamada al centro de distribución emergencia correspondiente. 
    
    > Nota: en Bélgica, Francia, Alemania, Irlanda, Países Bajos y España es importante comprender que, para poder activar correctamente un número de teléfono en Office 365, la configuración de dirección en la ubicación de emergencia, que se utilizará para obtener el número, debe coincidir con la código de área del número de teléfono.
  
    Si no se puede validar la dirección, puede enviar una solicitud de validación manual haciendo clic en **Enviar una solicitud de validación** si está intentando validar una dirección de Estados Unidos, o haga clic en **Abrir una solicitud de servicio para obtener ayuda con la validación de direcciones** si está fuera de la Estados Unidos.
    
6. Después de validar la dirección, haga clic en **Guardar**.
    
## <a name="change-an-emergency-address"></a>Cambiar una dirección de emergencia

1. Inicie sesión en Office 365 con su cuenta profesional o educativa.
    
2. Vaya al > **portal heredado**del **centro de administración de Microsoft Teams**.
    
3. En el panel de navegación izquierdo, vaya a**ubicaciones de emergencia**de **voz** > , seleccione la dirección que desee cambiar y, en el panel de acciones, haga clic en **Editar**.
    
    > [!IMPORTANT]
    > Para ver la opción de **voz** en el navegación izquierdo en el centro de administración de Skype empresarial, primero debe comprar al menos una **licencia de Enterprise E5**, una licencia de complemento de **sistema de teléfono** o una licencia de complemento de **audioconferencia** .

4. Realice los cambios y, a continuación, haga clic en **validar**.

5. Haga clic en **Guardar **.

## <a name="remove-an-emergency-address"></a>Quitar una dirección de emergencia

1. Inicie sesión en Office 365 con su cuenta profesional o educativa.
    
2. Vaya al > **portal heredado**del **centro de administración de Microsoft Teams**.
    
3. En el panel de navegación izquierdo, vaya a**ubicaciones de emergencia**de **voz** > , seleccione la dirección que quiera eliminar y, en el panel de acciones, haga clic en **eliminar**.
    
    > [!IMPORTANT]
    > Para ver la opción de **voz** en el navegación izquierdo en el centro de administración de Skype empresarial, primero debe comprar al menos una **licencia de Enterprise E5**, una licencia de complemento de **sistema de teléfono** o una licencia de complemento de **audioconferencia** .

## <a name="troubleshooting"></a>Solución de problemas

**Número en estado "error".**

Después de adquirir un número desde el portal de Office 365, el Estado cambió de **"aprovisionamiento"** a **"error"**.

Este problema suele ocurrir cuando se agrega un número desde el portal, usando una dirección de emergencia que apunta a una ubicación que no coincide con el código de área del teléfono.

Para obtener más información sobre los números que no se han activado correctamente, ejecute el siguiente PowerShell:
 
> [! Sintaxis] Get-CsOnlineTelephoneNumber | Where-Object {$ _. ActivationState-cnotcontains "activado"} | FL

El resultado, aparte de otra información como región, identificador y ActivationState, debe contener también el CityCode.

**Ejemplo**, para un número Madrid, la CityCode devuelta será "EMEA-es-todo-M_MA".

En caso de que se haya utilizado una dirección de emergencia incorrecta, asegúrese de que ha creado una nueva dirección de emergencia correspondiente al código de área del número y asígnelo al número.

1. Inicie sesión en Office 365 con su cuenta profesional o educativa.
    
2. Vaya al > **portal heredado**del **centro de administración de Microsoft Teams**.
    
3. En el menú de navegación izquierdo, vaya a**números de teléfono**de **voz** > y, después, haga doble clic en el número de **"error"** y, en el menú del sitio de la derecha, seleccione la **nueva dirección de emergencia**.


Ten en cuenta que después de cambiar la dirección de emergencia, el estado del número cambiará a **"asignación pendiente"** y puede tardar hasta 24 horas en activarse correctamente.

## <a name="related-topics"></a>Temas relacionados
[¿Qué son las direcciones, las ubicaciones de emergencia y el enrutamiento de llamadas?](/microsoftteams/what-are-emergency-locations-addresses-and-call-routing)

[Administrar los números de teléfono para su organización](/microsoftteams/manage-phone-numbers-for-your-organization)

[Términos y condiciones de las llamadas de emergencia](/microsoftteams/emergency-calling-terms-and-conditions)

[Skype Empresarial Online: Etiqueta de aviso de declinación de responsabilidades de las llamadas de emergencia](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

  
 
