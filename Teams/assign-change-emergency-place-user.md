---
title: Asignar y cambiar lugares para ubicaciones de emergencia para los usuarios
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: jastark, roykuntz
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- NOCSH
description: En este artículo, aprenderá a asignar o cambiar el lugar de una ubicación de emergencia para los usuarios de su organización.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 8cb8d51f35799ddb8610e7b3b36b43bf7f1fb890
ms.sourcegitcommit: 75adb0cc163974772617c5e78a1678d9dbd9d76f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/22/2021
ms.locfileid: "60537211"
---
# <a name="assign-or-change-the-place-for-an-emergency-location-for-a-user"></a>Asignar o cambiar el lugar de una ubicación de emergencia para un usuario

Cada número de teléfono activo debe tener una ubicación de emergencia asociada al asignar el número de teléfono a un usuario. La dirección se asocia cuando recibe un número de teléfono en Microsoft 365, cuando transfiere un número de teléfono a Microsoft 365 o cuando recibe un número de teléfono de su proveedor.

Al asociar el número a una ubicación de emergencia, también puede agregar un lugar para proporcionar una ubicación más exacta dentro de una ubicación física. Un lugar puede ser el piso, el ala del edificio u número de oficina donde se encuentra el usuario. Puede tener un número ilimitado de lugares para una ubicación de emergencia determinada y puede cambiar el lugar si el usuario se mueve a otra oficina o edificio. Por ejemplo, si el usuario se mueve del piso 34 al piso 35.
  
Puede asignar o cambiar el lugar de una ubicación de emergencia para un usuario en el centro de administración de Microsoft Teams o mediante PowerShell.

## <a name="using-the-microsoft-teams-admin-center"></a>Usar el Centro de administración de Microsoft Teams

1. En el panel de navegación izquierdo del centro Microsoft Teams de administración, haga **clic**  >  **en Teléfono números.**

2. En la **Teléfono números,** haga  clic en la pestaña Números, seleccione un número de usuario en la lista y, a continuación, haga clic en **Editar.**

3. En el **panel Editar,** en **Ubicación de emergencia**, realice una de las siguientes acciones:

    - Para asignar un lugar, busque la ubicación o el lugar y, a continuación, seleccione el lugar en los resultados de la búsqueda.

    - Para cambiar el lugar que ya está asignado al usuario, haga clic en **X** para quitar la ubicación y el lugar existentes, busque y seleccione el lugar que desea asignar.

4. Dependiendo de si desea enviar un correo electrónico al usuario con su información de número de teléfono, desactive o active Usuario de correo electrónico con información **de número de teléfono.** De forma predeterminada, está en.

5. Haga clic en **Aplicar**.

## <a name="using-powershell"></a>Con PowerShell

Vea [Set-CsOnlineLisLocation](/powershell/module/skype/set-csonlinelislocation).
    
## <a name="related-topics"></a>Temas relacionados

- [Administrar llamadas de emergencia](what-are-emergency-locations-addresses-and-call-routing.md)
- [Agregar, cambiar o quitar una ubicación de emergencia para su organización](add-change-remove-emergency-location-organization.md)
- [Agregar, cambiar o quitar una ubicación de emergencia para su organización](add-change-remove-emergency-place-organization.md)
- [Asignar o cambiar la ubicación de emergencia de un usuario](assign-change-emergency-location-user.md)
- [Administrar los números de teléfono para su organización](/microsoftteams/manage-phone-numbers-for-your-organization)
- [Términos y condiciones de las llamadas de emergencia](./emergency-calling-terms-and-conditions.md)