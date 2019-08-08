---
title: Comprobación de la preparación del entorno para Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 5/11/2018
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: dansteve
description: Sepa lo que debe buscar cuando compruebe si el entorno está preparado para Microsoft Teams.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: c0609efd8ac0286857b44996939378e57ce2702f
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/07/2019
ms.locfileid: "36234924"
---
<a name="check-your-environments-readiness-for-microsoft-teams"></a>Comprobación de la preparación del entorno para Microsoft Teams
===========================================

La transición a la nube será diferente para cada organización y su estado actual podría influir en el futuro funcionamiento de Teams.

Se recomienda a las instituciones educativas que [implementen School Data Sync](https://docs.microsoft.com/schooldatasync/) antes de implementar Microsoft Teams. School Data Sync usa los datos de la lista de SIS de su escuela para crear automáticamente clases y grupos para Microsoft Teams y otras aplicaciones.

Para obtener la mejor experiencia en Teams, su organización debe haber implementado Exchange Online y SharePoint Online. También debe asegurarse de que su entorno actual está listo para los equipos.  Consulte estos vínculos para obtener ayuda:

-   Si su organización no ha implementado ninguna carga de trabajo de Office 365, vea [Introducción a Office 365 para empresas](https://support.office.com/article/Get-started-with-Office-365-for-Business-d6466f0d-5d13-464a-adcb-00906ae87029).

-   Si su organización no ha agregado ni configurado un dominio verificado para Office 365, vea el tema sobre la [comprobación del dominio de Office 365](https://support.office.com/article/Verify-your-Office-365-domain-to-prove-ownership-nonprofit-or-education-status-or-to-activate-Yammer-87d1844e-aa47-4dc0-a61b-1b773fd4e590).

-   Si su organización no ha sincronizado identidades en Azure Active Directory, vea [Modelos de identidad y autenticación en Microsoft Teams](identify-models-authentication.md).

-   Si su organización no tiene Exchange Online, vea [Interacción entre Exchange y Microsoft Teams](Exchange-Teams-interact.md).

-   Si su organización no tiene SharePoint Online, vea [Interacción de SharePoint Online y OneDrive para la Empresa con Microsoft Teams](SharePoint-OneDrive-interact.md).

- Si su organización es un centro educativo y usa un sistema de información de estudiantes (SIS), [implemente School Data Sync](https://docs.microsoft.com/schooldatasync/) antes de implementar Microsoft Teams.

- Si su organización tiene una implementación local de Skype empresarial Server (o Lync Server) existente, debe configurar Azure AD Connect para sincronizar el directorio local con Office 365.  Para obtener más información, vea [configurar Azure ad Connect para Teams y Skype empresarial](https://docs.microsoft.com/en-us/skypeforbusiness/hybrid/configure-azure-ad-connect).