---
title: Problemas conocidos para directivas de retención en Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/11/2018
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: anach
description: Lista actual de problemas conocidos para las directivas de retención de Microsoft Teams.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5565409ea2f3dbb83754ced08a78e12283b1601c
ms.sourcegitcommit: 4a22bf77f529cfc2e68a6498a0c4aa9030ee2168
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/05/2019
ms.locfileid: "37968341"
---
# <a name="known-issues-for-retention-policies-in-microsoft-teams"></a><span data-ttu-id="85f56-103">Problemas conocidos para directivas de retención en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="85f56-103">Known issues for retention policies in Microsoft Teams</span></span>

> [!NOTE]
> <span data-ttu-id="85f56-104">Aún no se admite la configuración de retención de mensajes de canal privado.</span><span class="sxs-lookup"><span data-stu-id="85f56-104">We don’t yet support configuration for retention of private channel messages.</span></span> <span data-ttu-id="85f56-105">La retención de archivos compartidos en canales privados es compatible.</span><span class="sxs-lookup"><span data-stu-id="85f56-105">Retention of files shared in private channels is supported.</span></span>

<span data-ttu-id="85f56-106">A continuación se muestran algunos problemas conocidos relacionados con las directivas de retención en Teams en los que se realiza el seguimiento e investigación.</span><span class="sxs-lookup"><span data-stu-id="85f56-106">The following are known issues for retention policies in Teams that are being tracked and investigated.</span></span>

- <span data-ttu-id="85f56-107">En elegir equipos en la fila ubicaciones de los mensajes del canal de Teams, es posible que vea Office 365 grupos que no son también equipos.</span><span class="sxs-lookup"><span data-stu-id="85f56-107">Under Choose Teams in the Teams Channel messages location row, you may see Office 365 Groups that are not also Teams.</span></span> <span data-ttu-id="85f56-108">Esto se corregirá en el futuro.</span><span class="sxs-lookup"><span data-stu-id="85f56-108">This will be addressed in the future.</span></span>

- <span data-ttu-id="85f56-109">En elegir usuarios en la fila de ubicación de chats de equipos, es posible que vea invitados y usuarios que no son buzones de correo.</span><span class="sxs-lookup"><span data-stu-id="85f56-109">Under Choose Users in the Teams Chat location row, you may see guests and non-mailbox users.</span></span> <span data-ttu-id="85f56-110">Las directivas de retención no se deben configurar para los invitados y estamos trabajando para eliminarlas de la lista.</span><span class="sxs-lookup"><span data-stu-id="85f56-110">Retention policies are not meant to be set for guests, and we are working to remove these from the list.</span></span>

- <span data-ttu-id="85f56-111">El Asistente de ciclo de vida de Exchange (ELC) se ejecuta diariamente, pero tiene un SLA de 7 días.</span><span class="sxs-lookup"><span data-stu-id="85f56-111">Exchange Life Cycle assistant (ELC) runs daily, but it has an SLA of 7 days.</span></span> <span data-ttu-id="85f56-112">Como resultado, es posible que, si tiene una directiva de retención de equipos para eliminar elementos anteriores a 60 días, estos elementos podrían persistir durante un máximo de 67 días.</span><span class="sxs-lookup"><span data-stu-id="85f56-112">As a result, it's possible that, if you have a Teams retention policy to delete items older than 60 days, these items could persist for up to 67 days.</span></span> <span data-ttu-id="85f56-113">Esta no es una nueva situación: sigue el modelo de Exchange.</span><span class="sxs-lookup"><span data-stu-id="85f56-113">This isn't a new situation - it follows the Exchange model.</span></span> <span data-ttu-id="85f56-114">Por supuesto, en la mayoría de los casos, no hay demora.</span><span class="sxs-lookup"><span data-stu-id="85f56-114">Of course, in most cases, there is no delay.</span></span>


| | | |
|---------|---------|---------|
|![Un icono que representa un punto de decisión](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image3.png)     |<span data-ttu-id="85f56-116">Puntos de decisión</span><span class="sxs-lookup"><span data-stu-id="85f56-116">Decision point</span></span>         |<span data-ttu-id="85f56-p105">¿Qué características de seguridad y cumplimiento requiere su organización? ¿Su organización tiene las licencias necesarias para cumplir con los requisitos empresariales de seguridad y cumplimiento?</span><span class="sxs-lookup"><span data-stu-id="85f56-p105">What security and compliance features does your organization require? Does your organization have the required licenses to meet Security and Compliance business requirements?</span></span>         |
|![Un icono que representa los pasos siguientes](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image4.png)     |<span data-ttu-id="85f56-120">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="85f56-120">Next steps</span></span>         |<span data-ttu-id="85f56-121">Documente las características de seguridad y cumplimiento necesarias.</span><span class="sxs-lookup"><span data-stu-id="85f56-121">Document your required security and compliance features.</span></span>         |
