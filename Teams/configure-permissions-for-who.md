---
title: "Configurar los permisos de Quién"
author: ChuckEdmonson
ms.author: chucked
manager: lolaj
ms.date: 12/07/2017
ms.topic: article
ms.service: msteams
description: "Guía práctica para implementar características de voz en la nube en Microsoft Teams."
Set_Free_Tag: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8a5afb795e98accc1e441572d5fc56da16cb4d75
ms.sourcegitcommit: 4b69ae91de3f82912eda3513cec65ae12e1ce2b2
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/03/2018
---
<a name="configure-permissions-for-who"></a><span data-ttu-id="6f4c4-103">Configurar los permisos de Quién</span><span class="sxs-lookup"><span data-stu-id="6f4c4-103">Configure permissions for Who</span></span>
=============================

<span data-ttu-id="6f4c4-104">Los usuarios pueden usar la aplicación Quién con Microsoft Teams para realizar preguntas y buscar a personas en la organización en función de la tarea que estén realizando y con quién trabajen.</span><span class="sxs-lookup"><span data-stu-id="6f4c4-104">Users can use the Who app with Microsoft Teams to help them ask questions and find anyone in the organization based on what they're working on and who they work with.</span></span>

<span data-ttu-id="6f4c4-105">Para garantizar que los usuarios sacan el máximo partido de Quién, debe activar los siguientes permisos de miembros en Microsoft Graph.</span><span class="sxs-lookup"><span data-stu-id="6f4c4-105">To ensure users get the most out of Who, you must turn on the following member permissions in Microsoft Graph.</span></span>

- <span data-ttu-id="6f4c4-106">Calendarios.Lectura</span><span class="sxs-lookup"><span data-stu-id="6f4c4-106">Calendars.Read</span></span>

- <span data-ttu-id="6f4c4-107">Calendarios.Lectura.Compartidos</span><span class="sxs-lookup"><span data-stu-id="6f4c4-107">Calendars.Read.Shared</span></span>

- <span data-ttu-id="6f4c4-108">Correo.Lectura</span><span class="sxs-lookup"><span data-stu-id="6f4c4-108">Mail.Read</span></span>

- <span data-ttu-id="6f4c4-109">ConfiguraciónBuzón.LecturaEscritura</span><span class="sxs-lookup"><span data-stu-id="6f4c4-109">MailboxSettings.ReadWrite</span></span>

- <span data-ttu-id="6f4c4-110">Contactos.Lectura</span><span class="sxs-lookup"><span data-stu-id="6f4c4-110">People.Read</span></span>

- <span data-ttu-id="6f4c4-111">Contactos.Lectura.Todos</span><span class="sxs-lookup"><span data-stu-id="6f4c4-111">People.Read.All</span></span>

- <span data-ttu-id="6f4c4-112">Sitios.Lectura.Todos</span><span class="sxs-lookup"><span data-stu-id="6f4c4-112">Sites.Read.All</span></span>

- <span data-ttu-id="6f4c4-113">Usuario.Lectura.Todos</span><span class="sxs-lookup"><span data-stu-id="6f4c4-113">User.Read.All</span></span>

<span data-ttu-id="6f4c4-114">Para obtener información sobre cómo gestionar el ámbito de los permisos de Microsoft Graph, consulte [Ámbito de permisos](https://msdn.microsoft.com/en-us/Library/Azure/Ad/Graph/howto/azure-ad-graph-api-permission-scopes).</span><span class="sxs-lookup"><span data-stu-id="6f4c4-114">For more information about how to manage Microsoft Graph permission scopes, see [Permission scopes](https://msdn.microsoft.com/en-us/Library/Azure/Ad/Graph/howto/azure-ad-graph-api-permission-scopes).</span></span>
 
<span data-ttu-id="6f4c4-115">Para obtener información sobre los permisos de Microsoft Graph, consulte [Referencia de permisos de Microsoft Graph](https://developer.microsoft.com/en-us/graph/docs/concepts/permissions_reference).</span><span class="sxs-lookup"><span data-stu-id="6f4c4-115">For more information about Microsoft Graph permissions, see [Microsoft Graph permissions reference](https://developer.microsoft.com/en-us/graph/docs/concepts/permissions_reference).</span></span>