---
title: Uso Microsoft Teams con ámbito de búsqueda en el directorio
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 10/09/2018
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: sbhatta
localization_priority: Normal
search.appverid: MET150
description: Obtenga información sobre cómo usar búsqueda de Active directory con ámbito de Microsoft Teams para proporcionar vistas personalizadas del directorio.
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1b62b3e27cf0aa10ea6719cb1f27980ee83f4421
ms.sourcegitcommit: c4254b6119bbce274f895e20d30cb3c513d5a2de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/09/2018
ms.locfileid: "25455974"
---
# <a name="use-microsoft-teams-scoped-directory-search"></a>Uso Microsoft Teams con ámbito de búsqueda en el directorio

Búsqueda en el directorio con ámbito Microsoft Teams permite a las organizaciones crear límites virtuales que controlan cómo los usuarios pueden encontrar y comunicarse con otros usuarios de su organización. 

Microsoft Teams permite a las organizaciones a proporcionar vistas personalizadas del directorio a sus usuarios. Microsoft Teams usa [directivas de la libreta de direcciones de Exchange](https://docs.microsoft.com/en-us/Exchange/email-addresses-and-address-books/address-book-policies/address-book-policies?view=exchserver-2019) para admitir estas vistas personalizadas. Una vez que las directivas están habilitadas, se limita los resultados devueltos por las búsquedas para otros usuarios (por ejemplo, para iniciar una charla o para agregar a miembros a un equipo) según las directivas configuradas. Los usuarios no podrán buscar o detectar y unirse a nuevos equipos fuera de estas directivas. 

## <a name="when-should-you-use-scroped-directory-searches"></a>¿Cuándo se debe utilizar las búsquedas de directorio de scroped?

Escenarios que se benefician de las búsquedas de directorio con ámbito son similares a los escenarios de directiva de la libreta de direcciones. Por ejemplo, es posible que desee usar la búsqueda en el directorio con ámbito en las situaciones siguientes:

- Su organización tiene varias empresas dentro de su inquilino que desea mantener separados. 
- Su escuela desea limitar chats entre profesores y estudiantes. 
 
Encontrará más información acerca de cómo se pueden usar las directivas de la libreta de direcciones [aquí](https://docs.microsoft.com/en-us/Exchange/email-addresses-and-address-books/address-book-policies/abp-scenarios?view=exchserver-2019).

> [!IMPORTANT]
> Directivas de la libreta de direcciones proporcionan sólo una virtual separación de los usuarios desde la perspectiva de Active directory. Los usuarios aún pueden iniciar comunicaciones con otros usuarios proporcionando direcciones de correo electrónico completa. 

## <a name="enable-scoped-directory-search"></a>Habilitar la búsqueda de Active directory con ámbito

1.  Usar directivas de la libreta de direcciones para configurar su organización en subgrupos virtuales. Para obtener más información, vea [procedimientos para directivas de la libreta de direcciones](https://docs.microsoft.com/en-us/Exchange/email-addresses-and-address-books/address-book-policies/abp-procedures?view=exchserver-2019).

2.  Inicie sesión en el centro de administración de Microsoft 365, seleccione **centros de administración**y, a continuación, seleccione **los equipos & Skype**.
 
3.  En el Microsoft Teams & Skype para el centro de administración de negocio, seleccione **configuración de toda la organización** > **configuración de los equipos**.

4.  En la **búsqueda**, junto a **búsqueda de Active directory de ámbito en los equipos mediante una directiva de la libreta de direcciones de Exchange (APB)**, activar la alternancia **en**. 

    ![Ámbito de búsqueda en el directorio en los equipos & Skype para el centro de administración de negocio](media/teams-scoped-directory-search-image1.png)

> [!NOTE]
> Configuraciones híbridas (los equipos con Exchange local) no admiten el modo de búsqueda con un ámbito. 

