---
title: Agregar el dominio SMTP de Microsoft Teams como un dominio de remitente permitido en Exchange Online
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: article
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
ms.reviewer: anprakas
search.appverid: MET150
description: Aprenda a agregar el dominio SMTP de Microsoft Teams como dominio de remitentes permitido en Exchange Online para enviar notificaciones a los miembros del equipo.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5ae8be5c4b596b8815b8677b6214163924cbb183
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2019
ms.locfileid: "37567131"
---
<a name="add-the-microsoft-teams-smtp-domain-as-an-allowed-sender-domain-in-exchange-online"></a><span data-ttu-id="fbee3-103">Agregar el dominio SMTP de Microsoft Teams como un dominio de remitente permitido en Exchange Online</span><span class="sxs-lookup"><span data-stu-id="fbee3-103">Add the Microsoft Teams SMTP domain as an allowed sender domain in Exchange Online</span></span> 
=============================================================================

<span data-ttu-id="fbee3-p101">Tanto si crea un grupo de Office 365 en la consola de administración o usa Outlook, debe usar Exchange Online para enviar notificaciones de un miembro del equipo que se agrega a un grupo. Estos mensajes se generan desde su inquilino, ya que representan el FQDN de su dominio SMTP predeterminado.</span><span class="sxs-lookup"><span data-stu-id="fbee3-p101">Whether you create an Office 365 Group in the admin console or by using Outlook, Exchange Online is used to send notifications of a team member being added to a Group. These messages are generated from your tenant as they represent your default domain SMTP FQDN.</span></span>

![Captura de pantalla de un encabezado de mensaje que muestra un usuario agregado a un grupo.](media/Add_the_Microsoft_Teams_SMTP_domain_as_an_accepted_domain_in_Exchange_Online_image1.jpg)

<span data-ttu-id="fbee3-107">Teams usa Microsoft Exchange Online para enviar notificaciones a los miembros del equipo cuando se hayan agregado.</span><span class="sxs-lookup"><span data-stu-id="fbee3-107">Teams uses Microsoft Exchange Online as well to send notifications to team members when they’ve been added.</span></span> <span data-ttu-id="fbee3-108">La diferencia es que el FQDN de dominio del mensaje SMTP es "@email. teams.microsoft.com" para los inquilinos comerciales/empresariales y "@GCC-email.teams.com" para inquilinos de administración pública y podría ser detectado por el filtrado de correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="fbee3-108">The difference being the domain FQDN of the SMTP message is “@email.teams.microsoft.com” for Commercial/Business tenants and "@GCC-email.teams.com" for Government tenants and could be caught by spam filtering.</span></span>

![Captura de pantalla de un encabezado de mensaje que muestra un usuario agregado a un grupo.](media/Add_the_Microsoft_Teams_SMTP_domain_as_an_accepted_domain_in_Exchange_Online_image2.jpg)

<span data-ttu-id="fbee3-110">Para obtener el mejor resultado y el funcionamiento sin problemas, considere la posibilidad de agregar el dominio SMTP de Microsoft Teams a la lista "dominios de remitente permitidos" de su configuración de correo no deseado de Exchange Online:</span><span class="sxs-lookup"><span data-stu-id="fbee3-110">For best result and seamless operation, consider adding the Microsoft Teams SMTP domain to your “allowed sender domains” list in your Exchange Online spam configuration:</span></span>

![Captura de pantalla de la sección permitir listas de opciones de configuración de correo no deseado](media/Add_the_Microsoft_Teams_SMTP_domain_as_an_accepted_domain_in_Exchange_Online_image3.png)
