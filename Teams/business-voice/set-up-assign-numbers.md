---
title: Asignar Teams Sistema telefónico números de teléfono a los usuarios
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
f1.keywords:
- NOCSH
ms.localizationpriority: medium
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- Teams_Business_Voice
search.appverid: MET150
description: Obtenga información sobre cómo asignar Microsoft Teams Sistema telefónico números de teléfono a los usuarios de su organización.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9ac68e38975eaece18554a1aa04f18734da2c851
ms.sourcegitcommit: e86e3824c300c24e022d5cb1848338278a5a96a8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/03/2022
ms.locfileid: "63053019"
---
# <a name="step-5-assign-teams-phone-system-phone-numbers-to-your-users"></a>Paso 5: Asignar Teams Sistema telefónico números de teléfono a los usuarios

Antes de que los Teams puedan realizar o recibir llamadas telefónicas a o desde líneas telefónicas normales, debe asignarles números de teléfono. En Microsoft Teams, el número de teléfono que asigna a un usuario aparece en el teclado de marcado cuando el usuario hace clic en **Llamadas**. Haga lo siguiente para cada usuario que necesite un número de teléfono.

> [!NOTE]
> Si no ve ningún número de teléfono, espere. Los nuevos números de teléfono pueden tardar varias horas en estar disponibles en Teams.

1. Abra el Microsoft Teams de administración e inicie sesión con un usuario que sea administrador global. Normalmente, esta es la cuenta que usó para registrarse para Microsoft 365.
1. En el panel de navegación izquierdo, vaya a <a href="https://admin.teams.microsoft.com/phone-numbers" target="_blank">**Números** >  **de Teléfono voz**</a>.
1. En la **Teléfono números**, seleccione un número sinsignado en la lista y, a continuación, haga clic en **Editar**.  
1. En el **panel Editar** , en **Asignado** a, busque al usuario por nombre para mostrar o nombre de usuario y, a continuación, haga clic en **Asignar**.
1. En Ubicación **de** emergencia, puede seleccionar la ubicación de emergencia que agregó en el [](set-up-emergency-locations.md) paso Configurar ubicaciones de emergencia, o si necesita crear una nueva ubicación para otra oficina o una oficina principal, haga clic en Agregar **una ubicación**.
1. Decida si desea enviar un correo electrónico de bienvenida con información de número de teléfono al usuario. Si quiere:
    - **Lleve los números de teléfono existentes** a Sistema telefónico (denominado porte de números de teléfono *),* anule la selección de Usuario de **correo electrónico con información de número de teléfono**.
    - **Use los nuevos números de teléfono** seleccionados por Sistema telefónico, *seleccione* Usuario **de correo electrónico con información de número de teléfono**.
1. Haga clic en **Guardar**.
1. Repita los pasos anteriores para cada usuario al que desee asignar un número de teléfono.

> [!NOTE]
> Después de asignar un plan de llamadas de Microsoft a un usuario, pueden tardar hasta 24 horas en ver el teclado de marcado en su Teams cliente. Si el teclado de marcado no se muestra en 24 horas, compruebe la configuración [del teclado de marcado](/microsoftteams/dial-pad-configuration). Si es necesario, también puede ponerse [en contacto con el soporte técnico](/microsoft-365/admin/contact-support-for-business-products).

> [!div class="nextstepaction"]
> [Paso siguiente: Configurar un operador automático](set-up-auto-attendant.md?tabs=general-info#steps)
