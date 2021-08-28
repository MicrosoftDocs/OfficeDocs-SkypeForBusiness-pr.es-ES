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
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
description: Obtenga información sobre cómo usar Microsoft Teams directorio de ámbito para proporcionar vistas personalizadas del directorio.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 82fb18f60bf812bcc6b7535cdbf2589e60e1d399
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/26/2021
ms.locfileid: "58627432"
---
# <a name="use-microsoft-teams-scoped-directory-search"></a>Usar la búsqueda de directorios enfocada de Microsoft Teams

Microsoft Teams de directorios de ámbito permite a las organizaciones crear límites virtuales que controlen cómo los usuarios pueden encontrar y comunicarse con otros usuarios de su organización. 

Microsoft Teams permite a las organizaciones proporcionar vistas personalizadas del directorio a sus usuarios. Microsoft Teams directivas [de Barrera de información](/microsoft-365/compliance/information-barriers) para admitir estas vistas personalizadas. Una vez habilitadas las directivas, los resultados devueltos por las búsquedas de otros usuarios (por ejemplo, para iniciar un chat o agregar miembros a un equipo) estarán en el ámbito de acuerdo con las directivas configuradas. Los usuarios no podrán buscar ni descubrir ningún equipo cuando la búsqueda con ámbito esté en vigor, pero los miembros existentes de esos equipos pueden agregar usuarios, tal y como permiten las directivas activas de Barrera de información.

> [!NOTE]
> En Exchange entornos híbridos, esta característica solo funciona con buzones Exchange Online y no con buzones locales.

Vea también [Directivas de libreta de direcciones en Exchange Online](/exchange/address-books/address-book-policies/address-book-policies).

## <a name="when-should-you-use-scoped-directory-searches"></a>¿Cuándo debe usar búsquedas de directorios con ámbito?

Los escenarios que se benefician de las búsquedas de directorios de ámbito son similares a los escenarios de directiva de libreta de direcciones. Por ejemplo, es posible que desee usar la búsqueda de directorios con ámbito en las siguientes situaciones:

- La organización tiene varias compañías en su inquilino, pero prefiere mantenerlas por separado. 
- Su centro educativo quiere limitar los chats entre el personal académico y los estudiantes. 
 
Para obtener información sobre cómo usar directivas de libreta de direcciones, lea Directivas de barrera de información [en Exchange Online](/microsoft-365/compliance/information-barriers).

> [!IMPORTANT]
> Las directivas de libreta de direcciones proporcionan solo una separación virtual de los usuarios de la perspectiva del directorio. También es importante tener en cuenta que los datos de usuario que ya se habían almacenado en caché, antes de la aplicación de directivas de libreta de direcciones nuevas o actualizadas, permanecerán disponibles para los usuarios durante un máximo de 30 días.

## <a name="turn-on-scoped-directory-search"></a>Activar la búsqueda de directorios con ámbito

1. Use directivas de Barrera de información para configurar su organización en subgrupos virtuales. Para obtener más información, vea [Definir directivas de barrera de información.](/microsoft-365/compliance/information-barriers-policies)

2. En el Microsoft Teams de administración, seleccione **Configuración de** toda la organización Teams  >  **configuración.**

3. En **Buscar**, junto a Búsqueda de directorio de ámbito en Teams mediante una directiva de libreta de direcciones **(ABP)** de Exchange , active el **botón de alternancia .**

    ![Búsqueda de directorios con ámbito en Microsoft Teams de administración](media/teams-scoped-directory-search-image1.png)


> [!IMPORTANT]
> Este cambio puede tardar unas horas en replicarse.
