---
title: Usar la búsqueda de directorios enfocada de Microsoft Teams
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.date: 06/21/2019
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: sbhatta
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
description: Aprenda a usar la búsqueda en el directorio de ámbito de Microsoft Teams para proporcionar vistas personalizadas del directorio.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: e4f478bba8c396f0f20b95f69f56c2ded556224d
ms.sourcegitcommit: 2300595db7779da7a127ae9ee16e474452df02d3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2021
ms.locfileid: "49779934"
---
# <a name="use-microsoft-teams-scoped-directory-search"></a>Usar la búsqueda de directorios enfocada de Microsoft Teams

La búsqueda en el directorio de ámbito de Microsoft Teams permite a las organizaciones crear límites virtuales que controlan la forma en que los usuarios pueden encontrar y comunicarse con otros usuarios de su organización. 

Microsoft Teams permite a las organizaciones proporcionar vistas personalizadas del directorio a sus usuarios. Microsoft Teams usa directivas [de Barrera de la](https://docs.microsoft.com/microsoft-365/compliance/information-barriers) información para admitir estas vistas personalizadas. Una vez habilitadas las directivas, los resultados devueltos por las búsquedas de otros usuarios (por ejemplo, para iniciar un chat o agregar miembros a un equipo) estarán en el ámbito según las directivas configuradas. Los usuarios no podrán buscar o descubrir equipos cuando la búsqueda de ámbito esté en vigor. 

> [!NOTE]
> En entornos híbridos de Exchange, esta característica solo funciona con buzones de Exchange Online y no con buzones locales.

## <a name="when-should-you-use-scoped-directory-searches"></a>¿Cuándo debería usar búsquedas en directorios de ámbito?

Los escenarios que se benefician de las búsquedas en directorios de ámbito son similares a los escenarios de directivas de libreta de direcciones. Por ejemplo, es posible que desee usar búsqueda en el directorio de ámbito en las situaciones siguientes:

- La organización tiene varias compañías en su inquilino, pero prefiere mantenerlas por separado. 
- Su centro educativo quiere limitar los chats entre el personal académico y los estudiantes. 
 
Para obtener información sobre cómo usar las directivas de la libreta de direcciones, lea las directivas de Barrera de [la información en Exchange Online.](https://docs.microsoft.com/microsoft-365/compliance/information-barriers)

> [!IMPORTANT]
> Las directivas de libreta de direcciones proporcionan solo una separación virtual de los usuarios desde la perspectiva del directorio. También es importante tener en cuenta que los datos de usuario que ya se almacenaron en caché, antes de aplicar directivas de libreta de direcciones nuevas o actualizadas, permanecerán disponibles para los usuarios durante un máximo de 30 días.

## <a name="turn-on-scoped-directory-search"></a>Activar búsqueda de directorios de ámbito

1. Use las directivas de Barrera de información para configurar su organización en subgrupos virtuales. Para obtener más información, vea [Definir directivas de barreras de información.](https://docs.microsoft.com/microsoft-365/compliance/information-barriers-policies)

2. En el Centro de administración de Microsoft Teams, seleccione **configuración de Teams** para toda la  >  **organización.**

3. En **Búsqueda,** junto a Búsqueda en el directorio Ámbito en Teams con una directiva de libreta de direcciones de **Exchange (ABP),** active el botón de **alternancia.**

    ![Búsqueda de directorios de ámbito en el Centro de administración de Microsoft Teams](media/teams-scoped-directory-search-image1.png)


> [!IMPORTANT]
> Este cambio puede tardar unas horas en replicarse.
