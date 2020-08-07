---
title: Agregar el dominio SMTP de Teams como dominio de remitentes permitido en Exchange Online
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.date: 09/25/2017
ms.topic: article
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
ms.reviewer: anprakas
search.appverid: MET150
f1.keywords:
- NOCSH
description: Aprenda a agregar el dominio SMTP de Microsoft Teams como dominio de remitentes permitido en Exchange Online para enviar notificaciones a los miembros del equipo.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 33605a8250c9cd2bdcec90ade7b3fcea536f8977
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/06/2020
ms.locfileid: "46582057"
---
<a name="add-the-microsoft-teams-smtp-domain-as-an-allowed-sender-domain-in-exchange-online"></a><span data-ttu-id="a7dee-103">Agregar el dominio SMTP de Microsoft Teams como un dominio de remitente permitido en Exchange Online</span><span class="sxs-lookup"><span data-stu-id="a7dee-103">Add the Microsoft Teams SMTP domain as an allowed sender domain in Exchange Online</span></span> 
=============================================================================

<span data-ttu-id="a7dee-p101">Si crea un grupo de Microsoft 365 en la consola de administración o mediante Outlook, se usa Exchange Online para enviar las notificaciones de un miembro del equipo que se agrega a un grupo. Estos mensajes se generan desde tu espacio empresarial porque representan tu FQDN de dominio predeterminado.</span><span class="sxs-lookup"><span data-stu-id="a7dee-p101">Whether you create a Microsoft 365 group in the admin console or by using Outlook, Exchange Online is used to send notifications of a team member being added to a group. These messages are generated from your tenant as they represent your default domain SMTP FQDN.</span></span>

![Captura de pantalla de un encabezado de mensaje que muestra un usuario agregado a un grupo.](media/Add_the_Microsoft_Teams_SMTP_domain_as_an_accepted_domain_in_Exchange_Online_image1.jpg)

<span data-ttu-id="a7dee-107">Teams usa Microsoft Exchange Online para enviar notificaciones a los miembros del equipo cuando se hayan agregado.</span><span class="sxs-lookup"><span data-stu-id="a7dee-107">Teams uses Microsoft Exchange Online as well to send notifications to team members when they've been added.</span></span> <span data-ttu-id="a7dee-108">La diferencia es que el FQDN de dominio del mensaje SMTP es "@email. teams.microsoft.com" para los inquilinos comerciales/empresariales y "@GCC-email.teams.microsoft.com" para inquilinos de administración pública y podría ser detectado por el filtrado de correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="a7dee-108">The difference being the domain FQDN of the SMTP message is "@email.teams.microsoft.com" for Commercial/Business tenants and "@GCC-email.teams.microsoft.com" for Government tenants and could be caught by spam filtering.</span></span>

![Captura de pantalla de un encabezado de mensaje que muestra un usuario agregado a un grupo.](media/Add_the_Microsoft_Teams_SMTP_domain_as_an_accepted_domain_in_Exchange_Online_image2.jpg)

<span data-ttu-id="a7dee-110">Para obtener el mejor resultado y el funcionamiento sin problemas, considere la posibilidad de agregar el dominio SMTP de Microsoft Teams a la lista "dominios de remitente permitidos" de su configuración de correo no deseado de Exchange Online:</span><span class="sxs-lookup"><span data-stu-id="a7dee-110">For best result and seamless operation, consider adding the Microsoft Teams SMTP domain to your "allowed sender domains" list in your Exchange Online spam configuration:</span></span>

![Captura de pantalla de la sección permitir listas de opciones de configuración de correo no deseado](media/Add_the_Microsoft_Teams_SMTP_domain_as_an_accepted_domain_in_Exchange_Online_image3.png)
