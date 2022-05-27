---
title: Buscar números de teléfono para los usuarios
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: davlick, roykuntz, jastark
ms.topic: article
ms.assetid: cc22c49a-c644-4151-a2fc-a1474148f8ba
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Calling Plans
description: Vea cómo buscar números de teléfono que puede asignar a sus usuarios, por país o región y ciudad, y especifique la cantidad de números que necesita.
ms.openlocfilehash: 4cb30e6ef03e50c3524ccd9b5c36ae10fb8b5ab2
ms.sourcegitcommit: cc6a3b30696bf5d254a3662d8d2b328cbb1fa9d1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/25/2022
ms.locfileid: "65681801"
---
# <a name="search-for-telephone-numbers-for-users"></a>Buscar números de teléfono para los usuarios

Al configurar los usuarios de su organización para realizar y recibir llamadas telefónicas con números de teléfono proporcionados por Microsoft, primero debe usar el centro de administración **de Microsoft Teams** y adquirir números de teléfono para que se asignen a los usuarios. El número de teléfono que asigne a un usuario será un número de teléfono que haya adquirido previamente para su organización; el número se mostrará en la lista desplegable cuando edite las propiedades del usuario y haga clic en **Asignar**.
  
Antes de poder asignar números de teléfono proporcionados por Microsoft a los usuarios, debe usar la página **Obtener números nuevos** para buscar los números de teléfono disponibles. Puede buscar por **País (Mercado),** **Tipo de número** y **Ubicación**. Entonces verá una lista de operadores que suministran números en ese país.

Si selecciona Microsoft como operador, puede adquirir los números en el centro de administración de Teams especificando la cantidad de números de teléfono que necesitará para los usuarios. La página limitará automáticamente la cantidad en función de la cantidad que todavía tengas disponible para adquirir. Si seleccionas un operador de Conexión con operador, se te dirigirá a la página de aterrizaje de tu operador seleccionado para completar el número de pedido.

La forma de adquirir y administrar números de teléfono varía según la opción de conectividad con RTC: Planes de llamadas de Microsoft, Conexión con operador o Enrutamiento directo.

Este artículo se aplica a los [planes de llamadas de Microsoft](#search-for-telephone-numbers-for-microsoft-calling-plans) y [Conexión con operador](#search-for-telephone-numbers-for-operator-connect). Para obtener más información sobre todas las opciones, vea [Administrar los números de teléfono de su organización](/microsoftteams/manage-phone-numbers-landing-page).

## <a name="search-for-telephone-numbers-for-microsoft-calling-plans"></a>Buscar números de teléfono para planes de llamadas de Microsoft

Para buscar números de teléfono para los usuarios:
  
1. Vaya al **Centro de administración de Microsoft Teams**.

2. En el panel de navegación izquierdo, seleccione **Números de voz** >  **Teléfono** > **Obtener números nuevos**.
  
    > [!IMPORTANT]
    > Para ver la opción **Voz** en el panel de navegación izquierdo del centro de administración de Teams, primero debe comprar al menos una **licencia de Enterprise E5 o E3**, una **licencia de complemento Sistema telefónico** o una licencia **de complemento de Audioconferencia**.  

3. En la página **Seleccionar ubicación y cantidad** , seleccione una ubicación en la lista desplegable **País (mercado** ).

4. Seleccione **Usuario** en la lista desplegable **Tipo de número** .

5. Dependiendo del País (Mercado) que haya seleccionado, ahora tendrá diferentes opciones disponibles para localizar los números de teléfono que necesite.  

6. En **Cantidad**, escriba el número de números de teléfono que desee para su organización y, a continuación, haga clic en **Siguiente**. Tiene 10 minutos para seleccionar los números de teléfono. Si tarda más de 10 minutos, los números se devolverán al grupo de números de teléfono.

    > [!NOTE]
    > Puede ver el número de números de teléfono disponibles (que se basa en el número de licencias) que aparecen junto a **Cantidad**.
  
7. En la página **Obtener números** , seleccione los números de teléfono que desee, haga clic en **Adquirir números** y, a continuación, haga clic en **Siguiente**.

    > [!IMPORTANT]
    > Puede adquirir más números de teléfono que las licencias de Microsoft. Para determinar cuántos números de teléfono puede adquirir, tome su número de licencias de Microsoft Calling Plan, agregue el 10 por ciento del número de licencias, agregue 10 y, a continuación, quite las licencias que ya haya adquirido. Por ejemplo, si tiene 100 licencias de **Microsoft Domestic Calling Plan**, **International Calling Plan** y/o **Domestic and International Calling Plan** , puede reservar 120 números de teléfono, suponiendo que aún no haya adquirido algunos números de teléfono para esos 100 usuarios. Para obtener más información, consulte [¿Cuántos números de teléfono puede obtener?](./how-many-phone-numbers-can-you-get.md)

8. En la página **Confirmación** , comprueba tus opciones y, a continuación, haz clic en **Realizar pedido**.

9. Cuando vuelva a la página **números de Teléfono**, seleccione el número de teléfono o los números que desea asignar y, a continuación, haga clic en **Editar** para asignarlo a un usuario.

## <a name="search-for-telephone-numbers-for-operator-connect"></a>Buscar números de teléfono para Conexión con operador

1. Vaya al **Centro de administración de Microsoft Teams**.

2. En el panel de navegación izquierdo, seleccione **Números de voz** >  **Teléfono** > **Obtener números nuevos**.
  
    > [!IMPORTANT]
    > Para ver la opción **Voz** en el panel de navegación izquierdo del centro de administración de Teams, primero debe comprar al menos una **licencia de Enterprise E5 o E3**, una **licencia de complemento Sistema telefónico** o una licencia **de complemento de Audioconferencia**.  

3. En la página **Seleccionar ubicación y cantidad** , seleccione una ubicación en la lista desplegable **País (mercado** ).

4. Seleccione **Usuario** en la lista desplegable **Tipo de número** .

5. Dependiendo del País (Mercado) que haya seleccionado, ahora tendrá diferentes opciones disponibles para localizar los números de teléfono que necesite. Puede filtrar para mostrar solo los operadores que ha agregado seleccionando **Mostrar mis operadores**.

6. Si ya has dado tu consentimiento al operador, se te dirigirá a la página de aterrizaje del operador para completar el proceso de pedido.

7. Si no ha dado su consentimiento al operador, se le dirigirá a habilitarlo en la página del operador elegido en el centro de administración de Teams. Para obtener más información, vea [Habilitar un operador](operator-connect-configure.md#enable-an-operator).

8. Una vez completado el pedido, el operador cargará los números de teléfono a su inquilino y podrá asignarlos a los usuarios.  

## <a name="related-topics"></a>Temas relacionados

[Administrar los números de teléfono de su organización](manage-phone-numbers-landing-page.md)

[Términos y condiciones de las llamadas de emergencia](./emergency-calling-terms-and-conditions.md)

[Etiqueta de declinación de responsabilidades de llamadas de emergencia](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)
