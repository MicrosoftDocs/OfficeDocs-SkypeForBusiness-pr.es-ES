---
title: Usar la búsqueda de directorios enfocada de Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
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
description: Aprenda a usar la búsqueda de directorios de Microsoft Teams en el ámbito para proporcionar vistas personalizadas del directorio.
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 094d83f8f6b21fc5e820235b91fa14820f6b407e
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2019
ms.locfileid: "37570118"
---
# <a name="use-microsoft-teams-scoped-directory-search"></a>Usar la búsqueda de directorios enfocada de Microsoft Teams

El ámbito de la búsqueda de directorios de Microsoft Teams permite a las organizaciones crear límites virtuales que controlan cómo los usuarios pueden buscar y comunicarse con otros usuarios de su organización. 

Microsoft Teams permite a las organizaciones proporcionar vistas personalizadas del directorio a sus usuarios. Microsoft Teams usa [directivas de barrera de información](https://docs.microsoft.com/microsoft-365/compliance/information-barriers) para admitir estas vistas personalizadas. Una vez que se habilitan las directivas, los resultados devueltos por las búsquedas de otros usuarios (por ejemplo, para iniciar una conversación o agregar miembros a un equipo) se regirán según las directivas configuradas. Los usuarios no podrán buscar ni descubrir equipos cuando la búsqueda de ámbito está activa. 

> [!NOTE]
> En entornos híbridos de Exchange, esta característica solo funciona con los buzones de Exchange Online y no con los buzones locales.

## <a name="when-should-you-use-scoped-directory-searches"></a>¿Cuándo debería usar búsquedas de directorio de ámbito?

Los escenarios que se benefician de las búsquedas de directorio de ámbito son similares a los escenarios de directiva de libreta de direcciones. Por ejemplo, es posible que desee usar la búsqueda de directorios con ámbito en las siguientes situaciones:

- La organización tiene varias compañías en su inquilino, pero prefiere mantenerlas por separado. 
- Su centro educativo quiere limitar los chats entre el personal académico y los estudiantes. 
 
Para obtener información sobre cómo usar las directivas de la libreta de direcciones, lea [directivas de la barrera de información en Exchange Online](https://docs.microsoft.com/microsoft-365/compliance/information-barriers).

> [!IMPORTANT]
> Las directivas de la libreta de direcciones proporcionan solo una separación virtual de los usuarios de la perspectiva del directorio. Los usuarios pueden seguir iniciando comunicaciones con otras personas proporcionando direcciones de correo electrónico completas. También es importante tener en cuenta que todos los datos de usuario que ya se habían almacenado en la memoria caché antes de la aplicación de directivas de libreta de direcciones nuevas o actualizadas seguirán estando disponibles para los usuarios durante un máximo de 30 días.

## <a name="turn-on-scoped-directory-search"></a>Activar la búsqueda de directorio en el ámbito

1. Use directivas de barrera de información para configurar su organización en subgrupos virtuales. Para obtener más información, consulte [definir directivas de barrera](https://docs.microsoft.com/microsoft-365/compliance/information-barriers-policies)de la información.

2. En el centro de administración de Microsoft Teams, seleccione Configuración de**Teams**de la **organización** > .

3. En **Buscar**, junto a la **búsqueda en el directorio de ámbito en Teams mediante una directiva de la libreta de direcciones de Exchange (APB)**, active la opción **de**alternancia.

    ![Búsqueda de directorio de ámbito en el centro de administración de Microsoft Teams](media/teams-scoped-directory-search-image1.png)



