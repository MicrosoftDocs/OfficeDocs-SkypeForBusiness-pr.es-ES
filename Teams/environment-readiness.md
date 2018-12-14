---
title: Comprobación de la preparación del entorno para Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 5/11/2018
ms.topic: article
ms.service: msteams
ms.reviewer: dansteve
description: Sepa lo que debe buscar cuando compruebe si el entorno está preparado para Microsoft Teams.
localization_priority: Normal
search.appverid: MET150
MS.collection: Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
ms.openlocfilehash: 057493f42a4bbfa012fb57c2394c372dfc25c9fc
ms.sourcegitcommit: a3181bc3707b09c1e3f87c343b38259fdc6dabd2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/14/2018
ms.locfileid: "27264831"
---
<a name="check-your-environments-readiness-for-microsoft-teams"></a>Comprobación de la preparación del entorno para Microsoft Teams
===========================================

La transición a la nube será diferente para cada organización y su estado actual podría influir en el futuro funcionamiento de Teams.

Se recomienda encarecidamente [implementar la sincronización de datos de School](https://docs.microsoft.com/schooldatasync/) instituciones educativas antes de implementar Microsoft Teams. Sincronización de datos de escuela utiliza datos de lista de participantes de su escuela SIS para crear automáticamente las clases y los grupos para Microsoft Teams y otras aplicaciones.

Para obtener la mejor experiencia en los equipos, su organización debe haber implementado Exchange Online y SharePoint Online. También debe asegurarse de que está listo para los equipos de su entorno actual.  Hacer referencia a estos vínculos para obtener ayuda:

-   Si su organización no ha implementado ninguna carga de trabajo de Office 365, vea [Introducción a Office 365 para empresas](https://support.office.com/article/Get-started-with-Office-365-for-Business-d6466f0d-5d13-464a-adcb-00906ae87029).

-   Si su organización no ha agregado ni configurado un dominio verificado para Office 365, vea el tema sobre la [comprobación del dominio de Office 365](https://support.office.com/article/Verify-your-Office-365-domain-to-prove-ownership-nonprofit-or-education-status-or-to-activate-Yammer-87d1844e-aa47-4dc0-a61b-1b773fd4e590).

-   Si su organización no ha sincronizado identidades en Azure Active Directory, vea [Modelos de identidad y autenticación en Microsoft Teams](identify-models-authentication.md).

-   Si su organización no tiene Exchange Online, vea [Interacción entre Exchange y Microsoft Teams](Exchange-Teams-interact.md).

-   Si su organización no tiene SharePoint Online, vea [Interacción de SharePoint Online y OneDrive para la Empresa con Microsoft Teams](SharePoint-OneDrive-interact.md).

- Si la organización es una institución de enseñanza y usar un sistema de información de estudiantes (SIS), que [implementar la sincronización de datos de escuela](https://docs.microsoft.com/schooldatasync/) antes de implementar Microsoft Teams.

- Si su organización tiene un Skype local existente para la implementación de Business Server (o Lync Server), debe configurar Azure Connect de AD para sincronizar el directorio local con Office 365.  Para obtener más información, vea [Configurar Azure AD conectar para equipos y Skype para la empresa](https://docs.microsoft.com/en-us/skypeforbusiness/hybrid/configure-azure-ad-connect).