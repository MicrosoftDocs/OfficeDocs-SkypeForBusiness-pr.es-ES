---
title: Agregar, cambiar o quitar una dirección de emergencia para la organización
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
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Calling Plans
description: 'Learn how to add an emergency address to your Skype for Business account. '
ms.openlocfilehash: b3fab8d41c1b6f59961feee09f5eae888d32b362
ms.sourcegitcommit: 60e8365281ec6d780f1b2439bedef0bd71f002d8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2019
ms.locfileid: "30047742"
---
# <a name="add-change-or-remove-an-emergency-address-for-your-organization"></a>Agregar, cambiar o quitar una dirección de emergencia para la organización

Una dirección de emergencia debe asociarse con un número de teléfono, pero cuando esto sucede puede variar entre países o regiones. Por ejemplo, en los Estados Unidos, debe asociar una dirección de emergencia al asignar el número de teléfono al usuario. En el Reino Unido, debe asociar una dirección de emergencia al número de teléfono al obtener los números de teléfono de Office 365 o transferir los números de teléfono de su proveedor de servicio actual.
  
Independientemente del país o región en que se encuentre, es posible agregar una ubicación o ubicaciones a una dirección de emergencia o quitar una dirección de emergencia. Dependiendo del número de ubicaciones físicas en la organización, puede crear para los edificios, plantas y oficinas. Vea [¿Cuáles son las ubicaciones de emergencia, las direcciones y el enrutamiento de llamadas?](/microsoftteams/what-are-emergency-locations-addresses-and-call-routing) para obtener algunos detalles.
  
Para obtener información sobre cómo obtener planes de llamadas y su coste, vea [Licencias de complementos de Skype for Business y Microsoft Teams](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).
  
## <a name="add-an-emergency-address"></a>Agregar una dirección de emergencia

1. Inicie sesión en Office 365 con su cuenta profesional o educativa.
    
2. Vaya al **Centro de administración de equipos de Microsoft** > **portal heredado**.
    
3. En el panel de navegación izquierdo, vaya a VozUbicaciones de emergenciay, a continuación, haga clic en el botón Agregar nueva dirección.** **  >  ** ** ** **
    
    > [!Important]
    > Para que pueda ver la opción de **voz** en la izquierda en la Skype para el centro de administración de negocio, primero debe comprar una licencia adicional para **Conferencias de Audio** , una licencia adicional para **El sistema de teléfono** o al menos una **licencia Enterprise E5**.
    
4. En el Panel de acciones, en **Nueva dirección**, escriba la información necesaria en las casillas.
    
5. Después de escribir toda la información de la dirección, haga clic en **Validar**.
    
    > [!IMPORTANT]
    > Validar una dirección civil o postal implica asegurarse de que sea legítima y tenga el formato correcto. Es posible que una dirección de emergencia parcialmente correcta, por ejemplo con el nombre de la ciudad mal escrito, pueda seguir pasando como válida. Incluso si está mal escrita, pero pasó la validación, la combinación del nombre de la ciudad mal escrito junto con las demás partes correctas de la dirección constituye información suficiente para dirigir la llamada al centro de distribución emergencia correspondiente. 
    
    > Nota: En Bélgica, Francia, Alemania, Irlanda, países bajos y España es importante comprender que para poder activar correctamente un número de teléfono en Office 365, el programa de instalación de la dirección en la ubicación de emergencia, que se usará para adquirir el número, deben coincidir con el código de área del número de teléfono.
  
    Si no se puede validar la dirección, puede enviar una solicitud de validación manual haciendo clic en **Enviar una solicitud de validación** si está intentando validar una dirección de Estados Unidos, o haga clic en **Abrir una solicitud de servicio para obtener ayuda con la validación de direcciones** si está fuera de la Estados Unidos.
    
6. Después de validar la dirección, haga clic en **Guardar**.
    
## <a name="change-an-emergency-address"></a>Cambiar una dirección de emergencia

1. Inicie sesión en Office 365 con su cuenta profesional o educativa.
    
2. Vaya al **Centro de administración de equipos de Microsoft** > **portal heredado**.
    
3. En el panel de navegación izquierdo, vaya a **voz** > **ubicaciones de emergencia**, seleccione la dirección que desea cambiar y, en el panel de acciones, haga clic en **Editar**.
    
    > [!IMPORTANT]
    > Para que pueda ver la opción de **voz** en la izquierda en la Skype para el centro de administración de negocio, primero debe comprar una licencia adicional para **Conferencias de Audio** , una licencia adicional para **El sistema de teléfono** o al menos una **licencia Enterprise E5**.

4. Realice los cambios y, a continuación, haga clic en **Validar**.

5. Haga clic en **Guardar**.

## <a name="remove-an-emergency-address"></a>Quitar una dirección de emergencia

1. Inicie sesión en Office 365 con su cuenta profesional o educativa.
    
2. Vaya al **Centro de administración de equipos de Microsoft** > **portal heredado**.
    
3. En el panel de navegación izquierdo, vaya a **voz** > **ubicaciones de emergencia**, seleccione la dirección que desea eliminar y, en el panel de acciones, haga clic en **Eliminar**.
    
    > [!IMPORTANT]
    > Para que pueda ver la opción de **voz** en la izquierda en la Skype para el centro de administración de negocio, primero debe comprar una licencia adicional para **Conferencias de Audio** , una licencia adicional para **El sistema de teléfono** o al menos una **licencia Enterprise E5**.

## <a name="troubleshooting"></a>Solución de problemas

**Número en el estado de "Error".**

Después de adquirir un número desde el portal de Office 365, el estado cambia de **"Aprovisionamiento"** a **"Error"**.

A menudo, este problema se produce cuando se agrega un número desde el portal, con una dirección de emergencia que apunta a una ubicación que no es coincida con el código de área del teléfono.

Para obtener más información acerca de los números que no se han activado correctamente, ejecute el siguiente Powershell:
 
> [! SINTAXIS] Get-CsOnlineTelephoneNumber | Where-Object {$_. ActivationState - cnotcontains "Activado"} | fl *

El resultado, reservar otra información como la región, identificador y ActivationState, también debe contener el CityCode.

**Ejemplo**, para un número de Madrid, el CityCode devuelto será "EMEA ES-todas las M_MA".

Si en realidad se ha utilizado una dirección de emergencia incorrecta, asegúrese de que ha creado una nueva dirección de emergencia correspondiente al código de área del número y asignar al número.

1. Inicie sesión en Office 365 con su cuenta profesional o educativa.
    
2. Vaya al **Centro de administración de equipos de Microsoft** > **portal heredado**.
    
3. En el panel de navegación izquierdo, vaya a **voz** > **Los números de teléfono**y, a continuación, haga doble clic en el número en estado de **"Error"** y, en el menú de sitio de la derecha, seleccione la **Nueva dirección de emergencia**.


Tenga en cuenta después de cambiar la dirección de emergencia, el estado del número cambiará a **"asignación pendiente"** y puede tardar hasta 24 horas para activar correctamente.

## <a name="related-topics"></a>Temas relacionados
[¿Qué son las direcciones, las ubicaciones de emergencia y el enrutamiento de llamadas?](/microsoftteams/what-are-emergency-locations-addresses-and-call-routing)

[Administrar los números de teléfono para su organización](/microsoftteams/manage-phone-numbers-for-your-organization)

[Términos y condiciones de las llamadas de emergencia](/microsoftteams/emergency-calling-terms-and-conditions)

[Skype for Business Online: Etiqueta de aviso de declinación de responsabilidades de las llamadas de emergencia](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

  
 
