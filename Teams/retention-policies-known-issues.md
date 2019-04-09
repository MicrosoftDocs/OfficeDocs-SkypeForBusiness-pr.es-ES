---
title: Problemas conocidos para directivas de retención en Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/11/2018
ms.topic: reference
ms.service: msteams
ms.reviewer: anach
description: Lista actual de problemas conocidos de las directivas de retención de Microsoft Teams.
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: dca7decd2c3c051c0d56a14e2a2d1485b777f92e
ms.sourcegitcommit: 58fec9aebd80029e1f1e71376efe222f9abf707e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "31517066"
---
# <a name="known-issues-for-retention-policies-in-microsoft-teams"></a><span data-ttu-id="71bce-103">Problemas conocidos para directivas de retención en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="71bce-103">Known issues for retention policies in Microsoft Teams</span></span>

<span data-ttu-id="71bce-104">Los siguientes son problemas conocidos que para las directivas de retención en los equipos que se va a realizar un seguimiento e investigarse.</span><span class="sxs-lookup"><span data-stu-id="71bce-104">The following are known issues for retention policies in Teams that are being tracked and investigated.</span></span>

- <span data-ttu-id="71bce-105">Bajo Elija los equipos en la fila de ubicación de los mensajes de canal de los equipos, es posible que vea Office 365 grupos que están no también los equipos.</span><span class="sxs-lookup"><span data-stu-id="71bce-105">Under Choose Teams in the Teams Channel messages location row, you may see Office 365 Groups that are not also Teams.</span></span> <span data-ttu-id="71bce-106">Esto se solucionará en el futuro.</span><span class="sxs-lookup"><span data-stu-id="71bce-106">This will be addressed in the future.</span></span>

- <span data-ttu-id="71bce-107">En Elegir usuarios en la fila de la ubicación de los equipos de Chat, es posible que vea invitados y los usuarios de buzones que no sean.</span><span class="sxs-lookup"><span data-stu-id="71bce-107">Under Choose Users in the Teams Chat location row, you may see guests and non-mailbox users.</span></span> <span data-ttu-id="71bce-108">Las directivas de retención no están pensadas para establecerse para invitados, y estamos trabajando para quitar estos elementos de la lista.</span><span class="sxs-lookup"><span data-stu-id="71bce-108">Retention policies are not meant to be set for guests, and we are working to remove these from the list.</span></span>

- <span data-ttu-id="71bce-109">Asistente de ciclo de vida de Exchange (ELC) se ejecuta a diario, pero tiene un SLA de 7 días.</span><span class="sxs-lookup"><span data-stu-id="71bce-109">Exchange Life Cycle assistant (ELC) runs daily, but it has an SLA of 7 days.</span></span> <span data-ttu-id="71bce-110">Como resultado, es posible que, si tiene una directiva de retención de los equipos para eliminar los elementos de más de 60 días, pueden conservar estos elementos de 67 días.</span><span class="sxs-lookup"><span data-stu-id="71bce-110">As a result, it's possible that, if you have a Teams retention policy to delete items older than 60 days, these items could persist for up to 67 days.</span></span> <span data-ttu-id="71bce-111">Esto no es una situación nueva - sigue el modelo de Exchange.</span><span class="sxs-lookup"><span data-stu-id="71bce-111">This isn't a new situation - it follows the Exchange model.</span></span> <span data-ttu-id="71bce-112">Por supuesto, en la mayoría de los casos, no hay ningún retraso.</span><span class="sxs-lookup"><span data-stu-id="71bce-112">Of course, in most cases, there is no delay.</span></span>


| | | |
|---------|---------|---------|
|![Icono de Punto de decisión.](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image3.png)     |<span data-ttu-id="71bce-114">Puntos de decisión</span><span class="sxs-lookup"><span data-stu-id="71bce-114">Decision point</span></span>         |<span data-ttu-id="71bce-p104">¿Qué características de seguridad y cumplimiento requiere su organización? ¿Su organización tiene las licencias necesarias para cumplir con los requisitos empresariales de seguridad y cumplimiento?</span><span class="sxs-lookup"><span data-stu-id="71bce-p104">What security and compliance features does your organization require? Does your organization have the required licenses to meet Security and Compliance business requirements?</span></span>         |
|![Icono de Siguientes pasos.](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image4.png)     |<span data-ttu-id="71bce-118">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="71bce-118">Next steps</span></span>         |<span data-ttu-id="71bce-119">Documentar las características de seguridad y cumplimiento de normas necesarias.</span><span class="sxs-lookup"><span data-stu-id="71bce-119">Document your required security and compliance features.</span></span>         |
