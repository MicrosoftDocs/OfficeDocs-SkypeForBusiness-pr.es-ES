---
title: Configuración de reunión Crear nueva o editar existente
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/24/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.ConfMeetingSettingEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e8fc19fa-6cd7-4f68-b90a-1c7e1b649abd
description: Los ajustes de configuración de reunión definen la experiencia de unión de los usuarios a conferencias programadas por usuarios. Estas opciones solo se aplican a reuniones programadas. No se aplican a reuniones ad hoc creadas haciendo clic en la opción Reunirse ahora en el cliente.
ms.openlocfilehash: dc37e3d76a81a09fe2cbd2407f4d3a2dff3d703e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49803940"
---
# <a name="meeting-configuration-create-new-or-edit-existing"></a><span data-ttu-id="953c4-105">Configuración de reuniones: Crear nuevos o editar los existentes</span><span class="sxs-lookup"><span data-stu-id="953c4-105">Meeting Configuration: Create New or Edit Existing</span></span>

<span data-ttu-id="953c4-106">Los ajustes de configuración de reunión definen la experiencia de unión de los usuarios a conferencias programadas por usuarios.</span><span class="sxs-lookup"><span data-stu-id="953c4-106">Meeting configuration settings define the user join experience for conferences scheduled by users.</span></span> <span data-ttu-id="953c4-107">Estas opciones solo se aplican a reuniones programadas.</span><span class="sxs-lookup"><span data-stu-id="953c4-107">These settings only apply to scheduled meetings.</span></span> <span data-ttu-id="953c4-108">No se aplican a reuniones ad hoc creadas haciendo clic en la opción **Reunirse** ahora en el cliente.</span><span class="sxs-lookup"><span data-stu-id="953c4-108">They do not apply to ad-hoc meetings created by clicking the **Meet Now** option in the client.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="953c4-109">Referencia de la interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="953c4-109">UI Reference</span></span>

<span data-ttu-id="953c4-110">En la siguiente lista se describen los campos de la página.</span><span class="sxs-lookup"><span data-stu-id="953c4-110">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="953c4-111">**Ámbito** Identifica el ámbito de la configuración de reunión que está creando o modificando: global, de sitio o de grupo.</span><span class="sxs-lookup"><span data-stu-id="953c4-111">**Scope** Identifies the scope of the meeting configuration that you are creating or modifying: global, site, or pool.</span></span>

- <span data-ttu-id="953c4-112">**Nombre** Las configuraciones de reuniones tienen un nombre predeterminado y no se puede cambiar el nombre.</span><span class="sxs-lookup"><span data-stu-id="953c4-112">**Name** Meeting configurations are named by default, and the name cannot be changed.</span></span>

- <span data-ttu-id="953c4-113">**Los autores de llamadas RTC omiten la sala de espera** Active esta casilla para admitir automáticamente a los usuarios que llamen a la conferencia a través de una línea telefónica de red telefónica conmutada (RTC).</span><span class="sxs-lookup"><span data-stu-id="953c4-113">**PSTN callers bypass lobby** Select this check box to automatically admit users who are dialing in to the conference over a public switched telephone network (PSTN) phone line.</span></span> <span data-ttu-id="953c4-114">Desactive esta casilla para enrutar a los autores de llamadas RTC a la sala de espera, donde se mantienen hasta que un moderador de conferencia les concede acceso a la conferencia.</span><span class="sxs-lookup"><span data-stu-id="953c4-114">Clear this check box to route PSTN callers to the conference lobby, where they are on hold until a conference presenter grants them access to the conference.</span></span>

- <span data-ttu-id="953c4-115">**Designar como moderador** Seleccione la categoría de usuarios (además del organizador de la reunión) que se designan automáticamente como presentadores cuando se unen a una conferencia.</span><span class="sxs-lookup"><span data-stu-id="953c4-115">**Designate as presenter** Select the category of users (besides the meeting organizer) who are automatically designated as presenters when they join a conference.</span></span> <span data-ttu-id="953c4-116">Independientemente de esta configuración, los moderadores pueden designarse de forma explícita como moderadores cuando se programa la reunión, o se les puede designar como moderadores durante la conferencia.</span><span class="sxs-lookup"><span data-stu-id="953c4-116">Regardless of this setting, presenters can be explicitly designated as presenters when the conference is scheduled, or they can be explicitly promoted to presenter during the conference.</span></span> <span data-ttu-id="953c4-117">Las opciones son:</span><span class="sxs-lookup"><span data-stu-id="953c4-117">The options are:</span></span>

  - <span data-ttu-id="953c4-118">**Ninguno** Seleccione esta opción si nadie más que el organizador se designa automáticamente como moderador.</span><span class="sxs-lookup"><span data-stu-id="953c4-118">**None** Select this option if no one other than the organizer is automatically designated as a presenter.</span></span>

  - <span data-ttu-id="953c4-119">**Compañía** Seleccione esta opción para designar automáticamente solo a los miembros de la organización como presentadores.</span><span class="sxs-lookup"><span data-stu-id="953c4-119">**Company** Select this option to automatically designate only members of your organization as presenters.</span></span>

  - <span data-ttu-id="953c4-120">**Todos** Seleccione esta opción para designar automáticamente a cualquiera como moderador.</span><span class="sxs-lookup"><span data-stu-id="953c4-120">**Everyone** Select this option to automatically designate anyone to be a presenter.</span></span>

- <span data-ttu-id="953c4-121">**Tipo de conferencia asignado de forma predeterminada** Esta configuración controla si el Complemento de conferencias de Outlook siempre programa conferencias mediante la conferencia asignada por el organizador, lo que significa que las conferencias programadas siempre tienen la misma dirección URL de unión e información de audio.</span><span class="sxs-lookup"><span data-stu-id="953c4-121">**Assigned conference type by default** This setting controls whether the Outlook Conferencing Addin always schedules conferences by using the organizer's assigned conference, which means that scheduled conferences always have the same join URL and audio information.</span></span> <span data-ttu-id="953c4-122">Active esta casilla para que las conferencias programadas siempre usen la misma dirección URL.</span><span class="sxs-lookup"><span data-stu-id="953c4-122">Select this check box to have scheduled conferences always use the same join URL.</span></span> <span data-ttu-id="953c4-123">Desactívela para usar una dirección URL distinta para cada conferencia.</span><span class="sxs-lookup"><span data-stu-id="953c4-123">Clear this check box to use a different join URL for each conference.</span></span>

- <span data-ttu-id="953c4-124">**Admitir usuarios anónimos de forma predeterminada** Active esta casilla si los usuarios anónimos (es decir, no autenticados) pueden asistir a conferencias de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="953c4-124">**Admit anonymous users by default** Select this check box if anonymous (that is, unauthenticated) users are allowed to attend conferences by default.</span></span> <span data-ttu-id="953c4-125">Desactívela si los usuarios anónimos no pueden asistir a conferencias de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="953c4-125">Clear this check box if anonymous users are not allowed to attend conferences by default.</span></span>

- <span data-ttu-id="953c4-126">**Dirección URL del logotipo** Escriba la dirección URL que tiene la imagen que se usará para las invitaciones de conferencia personalizadas.</span><span class="sxs-lookup"><span data-stu-id="953c4-126">**Logo URL** Type the URL that has the image to be used for custom conference invitations.</span></span>

- <span data-ttu-id="953c4-127">**Dirección URL de ayuda** Escriba la dirección URL de un sitio web donde los usuarios puedan obtener ayuda para unirse a la conferencia.</span><span class="sxs-lookup"><span data-stu-id="953c4-127">**Help URL** Type the URL for a website where users can obtain assistance for joining the conference.</span></span>

- <span data-ttu-id="953c4-128">**Dirección URL de texto legal** Escriba la dirección URL de un sitio web que tenga la información legal y los avisos de declinación de responsabilidades de la conferencia.</span><span class="sxs-lookup"><span data-stu-id="953c4-128">**Legal text URL** Type the URL for a website that has the legal information and disclaimers for the conference.</span></span>

- <span data-ttu-id="953c4-129">**Texto de pie de página personalizado** Escriba el texto que se usará en invitaciones de conferencia personalizadas.</span><span class="sxs-lookup"><span data-stu-id="953c4-129">**Custom footer text** Type the text to be used on custom conference invitations.</span></span>

<span data-ttu-id="953c4-130">Para obtener detalles sobre cómo trabajar con configuraciones de reunión, vea [Create a or modify a Collection of Meeting Configuration Settings](https://technet.microsoft.com/library/ce6773c1-a0d5-4405-8e32-33a6f3a46a1a.aspx) en la documentación de operaciones.</span><span class="sxs-lookup"><span data-stu-id="953c4-130">For details about working with meeting configurations, see [Create a or modify a Collection of Meeting Configuration Settings](https://technet.microsoft.com/library/ce6773c1-a0d5-4405-8e32-33a6f3a46a1a.aspx) in the Operations documentation.</span></span> <span data-ttu-id="953c4-131">Para obtener detalles sobre cómo configurar configuraciones de reuniones para reuniones grandes, vea [Setting Up Support for Large Meetings](https://technet.microsoft.com/library/8e22d34b-b395-408d-9d48-8f2a3abe9513.aspx) en la documentación de planeación.</span><span class="sxs-lookup"><span data-stu-id="953c4-131">For details about setting meeting configurations for large meetings, see [Setting Up Support for Large Meetings](https://technet.microsoft.com/library/8e22d34b-b395-408d-9d48-8f2a3abe9513.aspx) in the Planning documentation.</span></span>


