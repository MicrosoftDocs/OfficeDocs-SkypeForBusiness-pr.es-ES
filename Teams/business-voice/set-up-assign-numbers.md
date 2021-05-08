---
title: Asignar números de teléfono de Business Voice a los usuarios
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
f1.keywords:
- NOCSH
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- Teams_Business_Voice
search.appverid: MET150
description: Obtenga información sobre cómo asignar Microsoft 365 Business Voice números de teléfono a los usuarios de su organización.
appliesto:
- Microsoft Teams
ms.openlocfilehash: d380fe3b3f5524f756a85f7b51037a07cd8cfc45
ms.sourcegitcommit: 32e3bb588abcbeded2d885483384c06706b280eb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/08/2021
ms.locfileid: "52282577"
---
# <a name="step-5-assign-business-voice-phone-numbers-to-your-users"></a>Paso 5: Asignar números de teléfono de Business Voice a los usuarios

Antes de que los usuarios puedan usar Teams realizar o recibir llamadas telefónicas a o desde líneas telefónicas normales, debe asignarles números de teléfono. En Microsoft Teams clientes, el número de teléfono que asigna a un usuario se muestra en el teclado de marcado cuando el usuario hace clic en **Llamadas.** Haga lo siguiente para cada usuario que necesite un número de teléfono.

![El número de teléfono del usuario se muestra en Teams.](../media/teams-phone-number.png)

> [!NOTE]
> Si no ve ningún número de teléfono, espere. Los nuevos números de teléfono pueden tardar varias horas en estar disponibles en Teams.

1. Abra el Microsoft Teams de administración e inicie sesión con un usuario que sea administrador global (normalmente es la cuenta que usó para registrarse para Microsoft 365).
1. En el panel de navegación izquierdo, vaya <a href="https://admin.teams.microsoft.com/phone-numbers" target="_blank"> **a Números**  >  **Teléfono voz.**</a>
1. En la **Teléfono números,** seleccione un número sinsignado en la lista y, a continuación, haga clic en **Editar.**  
1. En el **panel Editar,** en **Asignado a**, busque al usuario por nombre para mostrar o nombre de usuario y, a continuación, haga clic en **Asignar**.
1. En Ubicación **de** emergencia , puede seleccionar la [](set-up-emergency-locations.md) ubicación de emergencia que agregó en el paso Configurar ubicaciones de emergencia, o si necesita crear una nueva ubicación para otra oficina o una oficina en el hogar, haga clic en Agregar **una ubicación.**
1. Decida si desea enviar un correo electrónico de bienvenida con información de número de teléfono al usuario. Si quiere:
    - **Lleve los números de teléfono existentes** a Business Voice (denominado porte de números de *teléfono),* anule la selección de Usuario de **correo electrónico con información de número de teléfono.**
    - **Use los nuevos números de teléfono** seleccionados por Business Voice, seleccione *Usuario* **de correo electrónico con información de número de teléfono.**
1. Haga clic en **Guardar**.
1. Repita los pasos anteriores para cada usuario al que desee asignar un número de teléfono.

> [!NOTE]
> Debido a la latencia entre Microsoft 365 o Office 365 y Teams, los usuarios pueden tardar hasta 24 horas en habilitarse. Si el número de teléfono no se asigna correctamente después de 24 horas, póngase en contacto con el soporte técnico para productos [empresariales: Ayuda para administradores.](/microsoft-365/admin/contact-support-for-business-products) Estamos aquí para ayudarle.

> [!div class="nextstepaction"]
> [Paso siguiente: Configurar un operador automático](set-up-auto-attendant.md?tabs=general-info#steps)
