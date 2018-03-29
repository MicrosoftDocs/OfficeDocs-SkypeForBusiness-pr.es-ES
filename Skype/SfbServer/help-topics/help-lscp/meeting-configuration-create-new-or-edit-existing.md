---
title: Configuración de reunión crear nuevo o editar existente
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/24/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ConfMeetingSettingEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e8fc19fa-6cd7-4f68-b90a-1c7e1b649abd
description: Las opciones de configuración de reuniones definen la experiencia de unión de los usuarios a conferencias programadas. Estas opciones solo se aplican a las reuniones programadas. No se aplican a reuniones ad-hoc que se crean haciendo clic en la opción Reunirse ahora en el cliente.
ms.openlocfilehash: af9a1cca6a34320a7e2bd2ba53b08040351f784e
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="meeting-configuration-create-new-or-edit-existing"></a><span data-ttu-id="779df-105">Configuración de reuniones: Crear nueva o editar existente</span><span class="sxs-lookup"><span data-stu-id="779df-105">Meeting Configuration: Create New or Edit Existing</span></span>
 
<span data-ttu-id="779df-p102">Las opciones de configuración de reuniones definen la experiencia de unión de los usuarios a conferencias programadas. Estas opciones solo se aplican a las reuniones programadas. No se aplican a reuniones ad-hoc que se crean haciendo clic en la opción **Reunirse ahora** en el cliente.</span><span class="sxs-lookup"><span data-stu-id="779df-p102">Meeting configuration settings define the user join experience for conferences scheduled by users. These settings only apply to scheduled meetings. They do not apply to ad-hoc meetings created by clicking the **Meet Now** option in the client.</span></span>
  
## <a name="ui-reference"></a><span data-ttu-id="779df-109">Referencia de interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="779df-109">UI Reference</span></span>

<span data-ttu-id="779df-110">En la siguiente lista se describen los campos de la página.</span><span class="sxs-lookup"><span data-stu-id="779df-110">The following list describes the fields on the page.</span></span>
  
- <span data-ttu-id="779df-111">**Ámbito de aplicación** Identifica el ámbito de la configuración de la reunión que está creando o modificando: global, sitio o grupo.</span><span class="sxs-lookup"><span data-stu-id="779df-111">**Scope** Identifies the scope of the meeting configuration that you are creating or modifying: global, site, or pool.</span></span>
    
- <span data-ttu-id="779df-112">**Nombre** Configuraciones de reunión se denominan de forma predeterminada y no se puede cambiar el nombre.</span><span class="sxs-lookup"><span data-stu-id="779df-112">**Name** Meeting configurations are named by default, and the name cannot be changed.</span></span>
    
- <span data-ttu-id="779df-113">**Los llamadores PSTN omitir introductoria** Active esta casilla de verificación admitir automáticamente los usuarios que llaman a la conferencia sobre una línea de teléfono telefónica pública conmutada (PSTN) de la red.</span><span class="sxs-lookup"><span data-stu-id="779df-113">**PSTN callers bypass lobby** Select this check box to automatically admit users who are dialing in to the conference over a public switched telephone network (PSTN) phone line.</span></span> <span data-ttu-id="779df-114">Desactive esta casilla para enrutar a los autores de llamadas RTC a la sala de espera, donde se mantienen hasta que un moderador de conferencia les concede acceso a la conferencia.</span><span class="sxs-lookup"><span data-stu-id="779df-114">Clear this check box to route PSTN callers to the conference lobby, where they are on hold until a conference presenter grants them access to the conference.</span></span>
    
- <span data-ttu-id="779df-115">**Designar como moderador** Seleccione la categoría de usuarios (además del organizador de la reunión), que se designan automáticamente como moderadores cuando se unan a una conferencia.</span><span class="sxs-lookup"><span data-stu-id="779df-115">**Designate as presenter** Select the category of users (besides the meeting organizer) who are automatically designated as presenters when they join a conference.</span></span> <span data-ttu-id="779df-116">Independientemente de esta configuración, los moderadores pueden designarse de forma explícita como tales cuando se programa la reunión, o bien se les puede designar como moderadores durante la conferencia.</span><span class="sxs-lookup"><span data-stu-id="779df-116">Regardless of this setting, presenters can be explicitly designated as presenters when the conference is scheduled, or they can be explicitly promoted to presenter during the conference.</span></span> <span data-ttu-id="779df-117">Las opciones son:</span><span class="sxs-lookup"><span data-stu-id="779df-117">The options are:</span></span>
    
  - <span data-ttu-id="779df-118">**Ninguno** Seleccione esta opción si nadie que no sea el organizador se designa automáticamente como moderador.</span><span class="sxs-lookup"><span data-stu-id="779df-118">**None** Select this option if no one other than the organizer is automatically designated as a presenter.</span></span>
    
  - <span data-ttu-id="779df-119">**Compañía** Seleccione esta opción para designar automáticamente sólo los miembros de su organización como moderadores.</span><span class="sxs-lookup"><span data-stu-id="779df-119">**Company** Select this option to automatically designate only members of your organization as presenters.</span></span>
    
  - <span data-ttu-id="779df-120">**Todo el mundo** Seleccione esta opción para designar automáticamente cualquier persona sea un moderador.</span><span class="sxs-lookup"><span data-stu-id="779df-120">**Everyone** Select this option to automatically designate anyone to be a presenter.</span></span>
    
- <span data-ttu-id="779df-121">**Tipo de conferencia asignados de forma predeterminada** Esta configuración controla si el complemento de conferencia de Outlook siempre programar conferencias mediante el organizador asignado conferencia, lo que significa que programa conferencias siempre tiene la misma dirección URL de la combinación y la información de audio.</span><span class="sxs-lookup"><span data-stu-id="779df-121">**Assigned conference type by default** This setting controls whether the Outlook Conferencing Addin always schedules conferences by using the organizer's assigned conference, which means that scheduled conferences always have the same join URL and audio information.</span></span> <span data-ttu-id="779df-122">Active esta casilla para que las conferencias programadas usen siempre la misma dirección URL.</span><span class="sxs-lookup"><span data-stu-id="779df-122">Select this check box to have scheduled conferences always use the same join URL.</span></span> <span data-ttu-id="779df-123">Desactívela para usar una dirección URL distinta en cada conferencia.</span><span class="sxs-lookup"><span data-stu-id="779df-123">Clear this check box to use a different join URL for each conference.</span></span>
    
- <span data-ttu-id="779df-124">**Admitir usuarios anónimos de forma predeterminada** Seleccione esta casilla de verificación si anónimo (es decir, no autenticado) los usuarios pueden asistir a conferencias de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="779df-124">**Admit anonymous users by default** Select this check box if anonymous (that is, unauthenticated) users are allowed to attend conferences by default.</span></span> <span data-ttu-id="779df-125">Desactívela si los usuarios anónimos no pueden asistir a conferencias de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="779df-125">Clear this check box if anonymous users are not allowed to attend conferences by default.</span></span>
    
- <span data-ttu-id="779df-126">**Dirección URL del logotipo** Escriba la dirección URL que contiene la imagen que se utilizará para las invitaciones de conferencia personalizado.</span><span class="sxs-lookup"><span data-stu-id="779df-126">**Logo URL** Type the URL that has the image to be used for custom conference invitations.</span></span>
    
- <span data-ttu-id="779df-127">**Dirección URL de ayuda** Escriba la dirección URL de un sitio Web donde los usuarios pueden obtener asistencia para unirse a la conferencia.</span><span class="sxs-lookup"><span data-stu-id="779df-127">**Help URL** Type the URL for a website where users can obtain assistance for joining the conference.</span></span>
    
- <span data-ttu-id="779df-128">**Dirección URL de texto legal** Escriba la dirección URL de un sitio Web que tiene la información legal y renuncias de responsabilidad para la conferencia.</span><span class="sxs-lookup"><span data-stu-id="779df-128">**Legal text URL** Type the URL for a website that has the legal information and disclaimers for the conference.</span></span>
    
- <span data-ttu-id="779df-129">**Texto de pie de página personalizado** Escriba el texto que se utilizará en las invitaciones de conferencia personalizado.</span><span class="sxs-lookup"><span data-stu-id="779df-129">**Custom footer text** Type the text to be used on custom conference invitations.</span></span>
    
<span data-ttu-id="779df-130">Para obtener más información acerca de cómo trabajar con las configuraciones de la reunión, consulte [crear un o modificar una configuración colección del encuentro de](http://technet.microsoft.com/library/ce6773c1-a0d5-4405-8e32-33a6f3a46a1a.aspx) en la documentación de las operaciones.</span><span class="sxs-lookup"><span data-stu-id="779df-130">For details about working with meeting configurations, see [Create a or modify a Collection of Meeting Configuration Settings](http://technet.microsoft.com/library/ce6773c1-a0d5-4405-8e32-33a6f3a46a1a.aspx) in the Operations documentation.</span></span> <span data-ttu-id="779df-131">Para obtener más información acerca de cómo establecer configuraciones de reunión para grandes reuniones, vea [Configuración de soporte para grandes reuniones](http://technet.microsoft.com/library/8e22d34b-b395-408d-9d48-8f2a3abe9513.aspx) en la documentación de planeamiento.</span><span class="sxs-lookup"><span data-stu-id="779df-131">For details about setting meeting configurations for large meetings, see [Setting Up Support for Large Meetings](http://technet.microsoft.com/library/8e22d34b-b395-408d-9d48-8f2a3abe9513.aspx) in the Planning documentation.</span></span>
  

