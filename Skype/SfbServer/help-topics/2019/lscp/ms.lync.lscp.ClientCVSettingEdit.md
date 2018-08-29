---
title: Configuración de la versión de cliente crear nuevos o editar los existentes
ms.author: SerdarS
author: SerdarSoysal
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ClientCVSettingEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 07fec57c-5cd3-422a-829a-0b62cb0092c4
ROBOTS: NOINDEX, NOFOLLOW
description: Los ajustes de configuración de versión de cliente se usan para activar o desactivar el control de versiones de cliente. La configuración de la versión de cliente Global se instala con Skype para Business Server y se usa para habilitar o deshabilitar el control de la versión de cliente para la implementación de servidores completa. Si la configuración Global está habilitada, las directivas de versión de cliente que tenga activas tendrán efecto cuando los usuarios intenten iniciar sesión. Puede deshabilitar la configuración de versión de cliente Global si no desea que se produzca ningún control de versiones de cliente.
ms.openlocfilehash: 6eacaddba90b123d04290640ebc8c0997e6904ce
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/28/2018
ms.locfileid: "23263495"
---
# <a name="client-version-configuration-create-new-or-edit-existing"></a><span data-ttu-id="2fdc6-106">Configuración de versiones de cliente: Crear nueva o editar existente</span><span class="sxs-lookup"><span data-stu-id="2fdc6-106">Client Version Configuration: Create New or Edit Existing</span></span>

<span data-ttu-id="2fdc6-107">Los ajustes de configuración de versión de cliente se usan para activar o desactivar el control de versiones de cliente.</span><span class="sxs-lookup"><span data-stu-id="2fdc6-107">Client version configuration settings are used to turn client version control on or off.</span></span> <span data-ttu-id="2fdc6-108">La configuración de la versión de cliente Global se instala con Skype para Business Server y se usa para habilitar o deshabilitar el control de la versión de cliente para la implementación de servidores completa.</span><span class="sxs-lookup"><span data-stu-id="2fdc6-108">The Global client version configuration installs with Skype for Business Server and is used to enable or disable client version control for the entire server deployment.</span></span> <span data-ttu-id="2fdc6-109">Si la configuración Global está habilitada, las directivas de versión de cliente que tenga activas tendrán efecto cuando los usuarios intenten iniciar sesión.</span><span class="sxs-lookup"><span data-stu-id="2fdc6-109">When the Global configuration is enabled, any client version policies you have in place will take effect when users attempt to log on.</span></span> <span data-ttu-id="2fdc6-110">Puede deshabilitar la configuración de versión de cliente Global si no desea que se produzca ningún control de versiones de cliente.</span><span class="sxs-lookup"><span data-stu-id="2fdc6-110">You can disable the Global client version configuration if you do not want any client version control to occur.</span></span>

<span data-ttu-id="2fdc6-p103">También puede crear configuraciones de versión de cliente específicas del sitio, lo que le permite habilitar o deshabilitar el control de versiones de cliente por sitio. Las configuraciones específicas del sitio prevalecen sobre la configuración Global.</span><span class="sxs-lookup"><span data-stu-id="2fdc6-p103">You can also create site-specific client version configurations, allowing you to enable or disable client version control by site. Site-specific configurations take precedence over the Global configuration.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="2fdc6-113">Tareas que puede realizar</span><span class="sxs-lookup"><span data-stu-id="2fdc6-113">Tasks you can perform</span></span>

<span data-ttu-id="2fdc6-114">En las páginas **Nueva configuración de versión de cliente** o **Editar configuración de versión de cliente** puede realizar las siguientes tareas:</span><span class="sxs-lookup"><span data-stu-id="2fdc6-114">You can perform the following tasks on the **New Client Version Configuration** or **Edit Client Version Configuration** page:</span></span>

- <span data-ttu-id="2fdc6-115">Agregar o modificar el nombre de la configuración de versión de cliente.</span><span class="sxs-lookup"><span data-stu-id="2fdc6-115">Add or modify the name of the client version configuration.</span></span>

- <span data-ttu-id="2fdc6-116">Habilitar o deshabilitar el control de versiones de cliente de forma global o para el sitio específico.</span><span class="sxs-lookup"><span data-stu-id="2fdc6-116">Enable or disable client version control globally or for the specific site.</span></span>

- <span data-ttu-id="2fdc6-117">Agregar o modificar la acción predeterminada para la configuración de versión de cliente.</span><span class="sxs-lookup"><span data-stu-id="2fdc6-117">Add or modify the default action for the client version configuration.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="2fdc6-118">Referencia de interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="2fdc6-118">UI Reference</span></span>

<span data-ttu-id="2fdc6-119">En las siguientes listas se describen los menús, comandos, campos y propiedades de la página.</span><span class="sxs-lookup"><span data-stu-id="2fdc6-119">The following lists describe the menus, command, fields, and properties on the page.</span></span>

- <span data-ttu-id="2fdc6-120">**Ámbito** Identifica el ámbito (Global o sitio) de la configuración de la versión de cliente.</span><span class="sxs-lookup"><span data-stu-id="2fdc6-120">**Scope** Identifies the scope (Global or Site) of the client version configuration.</span></span>

- <span data-ttu-id="2fdc6-121">**Nombre** Puede agregar o modificar el nombre de la configuración de la versión de cliente.</span><span class="sxs-lookup"><span data-stu-id="2fdc6-121">**Name** You can add or modify the name of the client version configuration.</span></span>

- <span data-ttu-id="2fdc6-122">**Habilitar control de versiones** Puede habilitar o deshabilitar el control de la versión de cliente globalmente o para el sitio, según el ámbito de la configuración.</span><span class="sxs-lookup"><span data-stu-id="2fdc6-122">**Enable version control** You can enable or disable client version control globally or for the site, depending on the scope of the configuration.</span></span>

- <span data-ttu-id="2fdc6-123">**Acción predeterminada** Puede seleccionar la acción predeterminada que se aplicará cuando un usuario intenta iniciar sesión con una aplicación de cliente para el que no hay ninguna directiva de versión de cliente específico.</span><span class="sxs-lookup"><span data-stu-id="2fdc6-123">**Default action** You can select the default action that will be applied when a user attempts to log on using a client application for which there is no specific client version policy.</span></span> <span data-ttu-id="2fdc6-124">Tiene las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="2fdc6-124">You have the following options:</span></span>

  - <span data-ttu-id="2fdc6-125">**Permitir** Permite que el cliente inicie la sesión si la versión de cliente no coincide con ningún filtro de la lista de directivas de versión de cliente.</span><span class="sxs-lookup"><span data-stu-id="2fdc6-125">**Allow** Allows the client to log on if the client version does not match any filter in the client version policies list.</span></span>

  - <span data-ttu-id="2fdc6-126">**Bloque** Impide que el cliente de inicio de sesión si la versión de cliente no coincide con ningún filtro de la lista de directivas de versión de cliente.</span><span class="sxs-lookup"><span data-stu-id="2fdc6-126">**Block** Prevents the client from logging on if the client version does not match any filter in the client version policies list.</span></span>

  - <span data-ttu-id="2fdc6-127">**Bloquear con dirección URL** Impide que el cliente de inicio de sesión si la versión de cliente no coincide con ningún filtro de la lista de directivas de versión de cliente e incluye un mensaje de error que contiene una dirección URL donde se puede descargar un cliente más reciente.</span><span class="sxs-lookup"><span data-stu-id="2fdc6-127">**Block with URL** Prevents the client from logging on if the client version does not match any filter in the client version policies list, and includes an error message containing a URL where a newer client can be downloaded.</span></span>

  - <span data-ttu-id="2fdc6-128">**Permitir con dirección URL** Permite que el cliente inicie la sesión si la versión de cliente no coincide con ningún filtro de la lista de directivas de versión de cliente e incluye un mensaje de error que contiene una dirección URL donde se puede descargar un cliente más reciente.</span><span class="sxs-lookup"><span data-stu-id="2fdc6-128">**Allow with URL** Allows the client to log on if the client version does not match any filter in the client version policies list, and includes an error message containing a URL where a newer client can be downloaded.</span></span>

  - <span data-ttu-id="2fdc6-129">**Dirección URL** Si ha seleccionado **Bloquear con dirección URL** o **Permitir con dirección URL**, puede especificar la dirección URL de descarga de cliente para incluir en el mensaje de error.</span><span class="sxs-lookup"><span data-stu-id="2fdc6-129">**URL** If you selected **Block with URL** or **Allow with URL**, you can specify the client download URL to include in the error message.</span></span>

<span data-ttu-id="2fdc6-130">Para obtener información detallada acerca de la interoperabilidad entre clientes y versiones de cliente, consulte [Interoperabilidad del cliente](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx) en la documentación de planeación.</span><span class="sxs-lookup"><span data-stu-id="2fdc6-130">For details about interoperability among clients and client versions, see [Client Interoperability](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx) in the Planning documentation.</span></span> <span data-ttu-id="2fdc6-131">Para obtener información detallada sobre cómo trabajar con las configuraciones de versión de cliente, vea [modificar la acción predeterminada para los clientes no admiten explícitamente o restringidos](https://technet.microsoft.com/library/548dd0f5-62fe-4c3f-8952-2b9fd4c5fff3.aspx) en la documentación sobre operaciones.</span><span class="sxs-lookup"><span data-stu-id="2fdc6-131">For details about working with client version configurations, see [Modify the Default Action for Clients Not Explicitly Supported or Restricted](https://technet.microsoft.com/library/548dd0f5-62fe-4c3f-8952-2b9fd4c5fff3.aspx) in the Operations documentation.</span></span>

