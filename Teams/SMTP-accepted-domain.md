---
title: Agregar el dominio SMTP de Microsoft Teams como un dominio de remitente permitido en Exchange Online
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: anprakas
search.appverid: MET150
description: Aprenda a agregar el dominio SMTP de los equipos de Microsoft como un dominio de remitente permitidos en Exchange Online para enviar notificaciones a los miembros del equipo.
appliesto:
- Microsoft Teams
ms.openlocfilehash: ce0448ccdd124cf21db417f496d562e6fa9b6b76
ms.sourcegitcommit: 85c34280977fb2c15c8a43874a20e9492bdca57f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/07/2019
ms.locfileid: "30464471"
---
<a name="add-the-microsoft-teams-smtp-domain-as-an-allowed-sender-domain-in-exchange-online"></a><span data-ttu-id="cd671-103">Agregar el dominio SMTP de Microsoft Teams como un dominio de remitente permitido en Exchange Online</span><span class="sxs-lookup"><span data-stu-id="cd671-103">Add the Microsoft Teams SMTP domain as an allowed sender domain in Exchange Online</span></span> 
=============================================================================

<span data-ttu-id="cd671-p101">Tanto si crea un grupo de Office 365 en la consola de administración o usa Outlook, debe usar Exchange Online para enviar notificaciones de un miembro del equipo que se agrega a un grupo. Estos mensajes se generan desde su inquilino, ya que representan el FQDN de su dominio SMTP predeterminado.</span><span class="sxs-lookup"><span data-stu-id="cd671-p101">Whether you create an Office 365 Group in the admin console or by using Outlook, Exchange Online is used to send notifications of a team member being added to a Group. These messages are generated from your tenant as they represent your default domain SMTP FQDN.</span></span>

![Captura de pantalla de un encabezado de mensaje de correo electrónico de Outlook de ejemplo donde se ve que se ha agregado un usuario a un grupo.](media/Add_the_Microsoft_Teams_SMTP_domain_as_an_accepted_domain_in_Exchange_Online_image1.jpg)

<span data-ttu-id="cd671-107">Los equipos usa Microsoft Exchange Online así como para enviar notificaciones a los miembros del equipo cuando se ha añadido.</span><span class="sxs-lookup"><span data-stu-id="cd671-107">Teams uses Microsoft Exchange Online as well to send notifications to team members when they’ve been added.</span></span> <span data-ttu-id="cd671-108">La diferencia está en el FQDN del mensaje SMTP del dominio es "@email.teams.microsoft.com" para los inquilinos de negocio y comercial y "@GCC-email.teams.com" para los inquilinos de gobierno y puede capturarse mediante el filtrado de spam.</span><span class="sxs-lookup"><span data-stu-id="cd671-108">The difference being the domain FQDN of the SMTP message is “@email.teams.microsoft.com” for Commerical/Business tenants and "@GCC-email.teams.com" for Government tenants and could be caught by spam filtering.</span></span>

![Captura de pantalla de un encabezado de mensaje de correo electrónico de Outlook de ejemplo donde se ve que se ha agregado un usuario a un grupo.](media/Add_the_Microsoft_Teams_SMTP_domain_as_an_accepted_domain_in_Exchange_Online_image2.jpg)

<span data-ttu-id="cd671-110">Para obtener mejores resultados y un funcionamiento ininterrumpido, considere la posibilidad de agregar el dominio SMTP de los equipos de Microsoft a la lista "permitido de dominios de remitente" en su configuración de correo no deseado de Exchange Online:</span><span class="sxs-lookup"><span data-stu-id="cd671-110">For best result and seamless operation, consider adding the Microsoft Teams SMTP domain to your “allowed sender domains” list in your Exchange Online spam configuration:</span></span>

![Captura de pantalla de la sección Permitir listas de las opciones de configuración de correo no deseado de Exchange Online.](media/Add_the_Microsoft_Teams_SMTP_domain_as_an_accepted_domain_in_Exchange_Online_image3.png)
