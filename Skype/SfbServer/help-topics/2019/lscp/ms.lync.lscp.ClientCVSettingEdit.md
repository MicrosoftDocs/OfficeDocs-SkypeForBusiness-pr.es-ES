---
title: Configuración de la versión de cliente crear nueva o editar existente
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ClientCVSettingEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 07fec57c-5cd3-422a-829a-0b62cb0092c4
ROBOTS: NOINDEX, NOFOLLOW
description: Los ajustes de configuración de versión de cliente se usan para activar o desactivar el control de versiones de cliente. La configuración de la versión de cliente global se instala con Skype empresarial Server y se usa para habilitar o deshabilitar el control de versiones de cliente para toda la implementación del servidor. Si la configuración Global está habilitada, las directivas de versión de cliente que tenga activas tendrán efecto cuando los usuarios intenten iniciar sesión. Puede deshabilitar la configuración de versión de cliente Global si no desea que se produzca ningún control de versiones de cliente.
ms.openlocfilehash: 54a7929f91e4e944cbe431ae7a0193c50a12cfbd
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34300491"
---
# <a name="client-version-configuration-create-new-or-edit-existing"></a><span data-ttu-id="57965-106">Configuración de versiones de cliente: Crear nueva o editar existente</span><span class="sxs-lookup"><span data-stu-id="57965-106">Client Version Configuration: Create New or Edit Existing</span></span>

<span data-ttu-id="57965-107">Los ajustes de configuración de versión de cliente se usan para activar o desactivar el control de versiones de cliente.</span><span class="sxs-lookup"><span data-stu-id="57965-107">Client version configuration settings are used to turn client version control on or off.</span></span> <span data-ttu-id="57965-108">La configuración de la versión de cliente global se instala con Skype empresarial Server y se usa para habilitar o deshabilitar el control de versiones de cliente para toda la implementación del servidor.</span><span class="sxs-lookup"><span data-stu-id="57965-108">The Global client version configuration installs with Skype for Business Server and is used to enable or disable client version control for the entire server deployment.</span></span> <span data-ttu-id="57965-109">Si la configuración Global está habilitada, las directivas de versión de cliente que tenga activas tendrán efecto cuando los usuarios intenten iniciar sesión.</span><span class="sxs-lookup"><span data-stu-id="57965-109">When the Global configuration is enabled, any client version policies you have in place will take effect when users attempt to log on.</span></span> <span data-ttu-id="57965-110">Puede deshabilitar la configuración de versión de cliente Global si no desea que se produzca ningún control de versiones de cliente.</span><span class="sxs-lookup"><span data-stu-id="57965-110">You can disable the Global client version configuration if you do not want any client version control to occur.</span></span>

<span data-ttu-id="57965-p103">También puede crear configuraciones de versión de cliente específicas del sitio, lo que le permite habilitar o deshabilitar el control de versiones de cliente por sitio. Las configuraciones específicas del sitio prevalecen sobre la configuración Global.</span><span class="sxs-lookup"><span data-stu-id="57965-p103">You can also create site-specific client version configurations, allowing you to enable or disable client version control by site. Site-specific configurations take precedence over the Global configuration.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="57965-113">Tareas que puede realizar</span><span class="sxs-lookup"><span data-stu-id="57965-113">Tasks you can perform</span></span>

<span data-ttu-id="57965-114">En las páginas **Nueva configuración de versión de cliente** o **Editar configuración de versión de cliente** puede realizar las siguientes tareas:</span><span class="sxs-lookup"><span data-stu-id="57965-114">You can perform the following tasks on the **New Client Version Configuration** or **Edit Client Version Configuration** page:</span></span>

- <span data-ttu-id="57965-115">Agregar o modificar el nombre de la configuración de versión de cliente.</span><span class="sxs-lookup"><span data-stu-id="57965-115">Add or modify the name of the client version configuration.</span></span>

- <span data-ttu-id="57965-116">Habilitar o deshabilitar el control de versiones de cliente de forma global o para el sitio específico.</span><span class="sxs-lookup"><span data-stu-id="57965-116">Enable or disable client version control globally or for the specific site.</span></span>

- <span data-ttu-id="57965-117">Agregar o modificar la acción predeterminada para la configuración de versión de cliente.</span><span class="sxs-lookup"><span data-stu-id="57965-117">Add or modify the default action for the client version configuration.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="57965-118">Referencia de interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="57965-118">UI Reference</span></span>

<span data-ttu-id="57965-119">En las siguientes listas se describen los menús, comandos, campos y propiedades de la página.</span><span class="sxs-lookup"><span data-stu-id="57965-119">The following lists describe the menus, command, fields, and properties on the page.</span></span>

- <span data-ttu-id="57965-120">**Ámbito** Identifica el ámbito (global o de sitio) de la configuración de versión del cliente.</span><span class="sxs-lookup"><span data-stu-id="57965-120">**Scope** Identifies the scope (Global or Site) of the client version configuration.</span></span>

- <span data-ttu-id="57965-121">**Nombre** Puede Agregar o modificar el nombre de la configuración de la versión del cliente.</span><span class="sxs-lookup"><span data-stu-id="57965-121">**Name** You can add or modify the name of the client version configuration.</span></span>

- <span data-ttu-id="57965-122">**Habilitar el control de versiones** Puede habilitar o deshabilitar el control de versiones de cliente globalmente o para el sitio, según el ámbito de la configuración.</span><span class="sxs-lookup"><span data-stu-id="57965-122">**Enable version control** You can enable or disable client version control globally or for the site, depending on the scope of the configuration.</span></span>

- <span data-ttu-id="57965-123">**Acción predeterminada** Puede seleccionar la acción predeterminada que se aplicará cuando un usuario intente iniciar sesión con una aplicación cliente para la que no haya ninguna directiva de versión de cliente específica.</span><span class="sxs-lookup"><span data-stu-id="57965-123">**Default action** You can select the default action that will be applied when a user attempts to log on using a client application for which there is no specific client version policy.</span></span> <span data-ttu-id="57965-124">Tiene las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="57965-124">You have the following options:</span></span>

  - <span data-ttu-id="57965-125">**Permitir** Permite al cliente iniciar sesión si la versión del cliente no coincide con ningún filtro de la lista de directivas de versión del cliente.</span><span class="sxs-lookup"><span data-stu-id="57965-125">**Allow** Allows the client to log on if the client version does not match any filter in the client version policies list.</span></span>

  - <span data-ttu-id="57965-126">**Bloquear** Impide que el cliente inicie sesión si la versión del cliente no coincide con ningún filtro de la lista de directivas de versión del cliente.</span><span class="sxs-lookup"><span data-stu-id="57965-126">**Block** Prevents the client from logging on if the client version does not match any filter in the client version policies list.</span></span>

  - <span data-ttu-id="57965-127">**Bloque con dirección URL** Impide que el cliente inicie sesión si la versión del cliente no coincide con ningún filtro de la lista de directivas de versión del cliente e incluye un mensaje de error que contiene una dirección URL donde se puede descargar un cliente más reciente.</span><span class="sxs-lookup"><span data-stu-id="57965-127">**Block with URL** Prevents the client from logging on if the client version does not match any filter in the client version policies list, and includes an error message containing a URL where a newer client can be downloaded.</span></span>

  - <span data-ttu-id="57965-128">**Permitir con URL** Permite al cliente iniciar sesión si la versión del cliente no coincide con ningún filtro de la lista de directivas de versión del cliente e incluye un mensaje de error que contiene una dirección URL donde se puede descargar un cliente más reciente.</span><span class="sxs-lookup"><span data-stu-id="57965-128">**Allow with URL** Allows the client to log on if the client version does not match any filter in the client version policies list, and includes an error message containing a URL where a newer client can be downloaded.</span></span>

  - <span data-ttu-id="57965-129">**Dirección URL** Si ha seleccionado **bloquear con URL** o **permitir con URL**, puede especificar la dirección URL de descarga del cliente que se incluirá en el mensaje de error.</span><span class="sxs-lookup"><span data-stu-id="57965-129">**URL** If you selected **Block with URL** or **Allow with URL**, you can specify the client download URL to include in the error message.</span></span>

<span data-ttu-id="57965-130">Para obtener más información sobre la interoperabilidad entre los clientes y las versiones de cliente, consulte interoperabilidad de [cliente](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx) en la documentación de planificación.</span><span class="sxs-lookup"><span data-stu-id="57965-130">For details about interoperability among clients and client versions, see [Client Interoperability](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx) in the Planning documentation.</span></span> <span data-ttu-id="57965-131">Para más detalles sobre cómo trabajar con configuraciones de versiones de clientes, mire [Modify the Default Action for Clients Not Explicitly Supported or Restricted](https://technet.microsoft.com/library/548dd0f5-62fe-4c3f-8952-2b9fd4c5fff3.aspx) en la documentación de operaciones.</span><span class="sxs-lookup"><span data-stu-id="57965-131">For details about working with client version configurations, see [Modify the Default Action for Clients Not Explicitly Supported or Restricted](https://technet.microsoft.com/library/548dd0f5-62fe-4c3f-8952-2b9fd4c5fff3.aspx) in the Operations documentation.</span></span>

