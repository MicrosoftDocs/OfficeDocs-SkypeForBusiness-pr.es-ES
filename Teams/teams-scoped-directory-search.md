---
title: Limitar a quién pueden ver los usuarios al buscar en el directorio en Teams
author: MikePlumleyMSFT
ms.author: mikeplum
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: sbhatta
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
description: Obtenga información sobre cómo limitar a qué usuarios pueden ver al buscar en el directorio en Teams.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: c20c5acdafff69e5a43f02093b515b456daa8ff7
ms.sourcegitcommit: 193aec6f3f6b6ac14b07e778b3485eed813f5e99
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/13/2022
ms.locfileid: "66046432"
---
# <a name="limit-who-users-can-see-when-searching-the-directory-in-teams"></a>Limitar a quién pueden ver los usuarios al buscar en el directorio en Teams

Microsoft Teams permite a las organizaciones proporcionar vistas personalizadas del directorio a sus usuarios. Estas vistas pueden ser útiles si:

- La organización tiene varias compañías en su inquilino, pero prefiere mantenerlas por separado.
- Las directivas empresariales requieren que impida que determinados grupos de la organización se comuniquen entre sí.
- Su centro educativo quiere limitar los chats entre el personal académico y los estudiantes.

Hay dos opciones para limitar a qué usuarios pueden ver al buscar en el directorio en Teams:

- [Barreras de la información en Microsoft Teams](/MicrosoftTeams/information-barriers-in-teams)
- [Directivas de libreta de direcciones en Exchange Online](/exchange/address-books/address-book-policies/address-book-policies)

Si usa cualquiera de las dos opciones, debe activar la búsqueda por nombre en el centro de administración de Teams.

Se recomienda usar barreras de información si su organización cumple con los [permisos y licencias necesarios](/microsoft-365/compliance/information-barriers#required-licenses-and-permissions).

Para activar la búsqueda por nombre

1. En el Centro de administración de Microsoft Teams, seleccione Configuración **de Teams** >  **Teams**.

1. En **Buscar por nombre**, junto a **Buscar en el directorio de ámbito mediante una directiva de libreta de direcciones de Exchange**, active **el botón de** alternancia.

> [!Note]
> Este cambio puede tardar unas horas en surtir efecto.
> 
> Al activar la búsqueda por nombre, se oculta el cuadro **Buscar equipos** y la lista de equipos públicos en **Unirse a un equipo o crear uno** en Teams. También deshabilitará unirse a un equipo escribiendo `/join` en el cuadro de comandos de la parte superior de Teams.
