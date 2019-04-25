---
title: Usar la búsqueda de directorios enfocada de Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/08/2019
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: sbhatta
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
description: Obtenga información sobre cómo usar búsqueda de Active directory con ámbito de Microsoft Teams para proporcionar vistas personalizadas del directorio.
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: e3b51b56b8cc8a1f08d756cdab245915a2ac6824
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32226658"
---
# <a name="use-microsoft-teams-scoped-directory-search"></a>Usar la búsqueda de directorios enfocada de Microsoft Teams

Búsqueda en el directorio con ámbito Microsoft Teams permite a las organizaciones crear límites virtuales que controlan cómo los usuarios pueden encontrar y comunicarse con otros usuarios de su organización. 

Microsoft Teams permite a las organizaciones a proporcionar vistas personalizadas del directorio a sus usuarios. Microsoft Teams usa [directivas de la libreta de direcciones de Exchange](https://docs.microsoft.com/exchange/address-books/address-book-policies/address-book-policies) para admitir estas vistas personalizadas. Una vez que las directivas están habilitadas, se limita los resultados devueltos por las búsquedas para otros usuarios (por ejemplo, para iniciar una charla o para agregar a miembros a un equipo) según las directivas configuradas. Los usuarios no podrán buscar o detectar los equipos al ámbito de búsqueda está en vigor. 

## <a name="when-should-you-use-scoped-directory-searches"></a>¿Cuándo se debe utilizar las búsquedas de directorio con ámbito?

Escenarios que se benefician de las búsquedas de directorio con ámbito son similares a los escenarios de directiva de la libreta de direcciones. Por ejemplo, es posible que desee usar la búsqueda en el directorio con ámbito en las situaciones siguientes:

- La organización tiene varias compañías en su inquilino, pero prefiere mantenerlas por separado. 
- Su centro educativo quiere limitar los chats entre el personal académico y los estudiantes. 
 
Para obtener información sobre cómo usar directivas de la libreta de direcciones, lea la [Libreta de direcciones de directivas en Exchange Online](https://docs.microsoft.com/exchange/address-books/address-book-policies/address-book-policies).

> [!IMPORTANT]
> Directivas de la libreta de direcciones proporcionan sólo una virtual separación de los usuarios desde la perspectiva de Active directory. Los usuarios aún pueden iniciar comunicaciones con otros usuarios proporcionando direcciones de correo electrónico completa. También es importante tener en cuenta que los datos de usuario que tenían ya ha almacenado en caché, antes de la aplicación de directivas de la libreta de direcciones nuevos o actualizados, permanecerá disponibles para los usuarios de hasta 30 días.

## <a name="enable-scoped-directory-search"></a>Habilitar la búsqueda de Active directory con ámbito

1.  Usar directivas de la libreta de direcciones para configurar su organización en subgrupos virtuales. Para obtener más información, vea [procedimientos para directivas de la libreta de direcciones](https://docs.microsoft.com/exchange/address-books/address-book-policies/address-book-policies).

2.  Inicie sesión en el centro de administración de Microsoft 365, seleccione **centros de administración**y, a continuación, seleccione **los equipos & Skype**.
 
3.  En el centro de administración de Microsoft Teams, seleccione **configuración de toda la organización** > **configuración de los equipos**.

4.  En la **búsqueda**, junto a **búsqueda de Active directory de ámbito en los equipos mediante una directiva de la libreta de direcciones de Exchange (APB)**, activar la alternancia **en**. 

    ![Ámbito de búsqueda en el directorio en el centro de administración de Microsoft Teams](media/teams-scoped-directory-search-image1.png)

> [!NOTE]
> Configuraciones híbridas (los equipos con Exchange local) no admiten el modo de búsqueda con un ámbito. 

