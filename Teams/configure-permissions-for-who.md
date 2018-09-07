---
title: Configurar los permisos de Quién
author: ChuckEdmonson
ms.author: chucked
manager: serdars
ms.date: 12/07/2017
ms.topic: article
ms.service: msteams
search.appverid: MET150
description: Guía práctica para implementar características de voz en la nube en Microsoft Teams.
Set_Free_Tag: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: cc8fe9a21cdfa4d1df0bf3f11631d103a13fe94b
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2018
ms.locfileid: "23860218"
---
<a name="configure-permissions-for-who"></a><span data-ttu-id="147cd-103">Configurar los permisos de Quién</span><span class="sxs-lookup"><span data-stu-id="147cd-103">Configure permissions for Who</span></span>
=============================

<span data-ttu-id="147cd-104">Los usuarios pueden usar la aplicación Quién con Microsoft Teams para realizar preguntas y buscar a personas en la organización en función de la tarea que estén realizando y con quién trabajen.</span><span class="sxs-lookup"><span data-stu-id="147cd-104">Users can use the Who app with Microsoft Teams to help them ask questions and find anyone in the organization based on what they're working on and who they work with.</span></span>

<span data-ttu-id="147cd-105">Para garantizar que los usuarios sacan el máximo partido de Quién, debe activar los siguientes permisos de miembros en Microsoft Graph.</span><span class="sxs-lookup"><span data-stu-id="147cd-105">To ensure users get the most out of Who, you must turn on the following member permissions in Microsoft Graph.</span></span>

- <span data-ttu-id="147cd-106">Calendarios.Lectura</span><span class="sxs-lookup"><span data-stu-id="147cd-106">Calendars.Read</span></span>

- <span data-ttu-id="147cd-107">Calendarios.Lectura.Compartidos</span><span class="sxs-lookup"><span data-stu-id="147cd-107">Calendars.Read.Shared</span></span>

- <span data-ttu-id="147cd-108">Correo.Lectura</span><span class="sxs-lookup"><span data-stu-id="147cd-108">Mail.Read</span></span>

- <span data-ttu-id="147cd-109">ConfiguraciónBuzón.LecturaEscritura</span><span class="sxs-lookup"><span data-stu-id="147cd-109">MailboxSettings.ReadWrite</span></span>

- <span data-ttu-id="147cd-110">Contactos.Lectura</span><span class="sxs-lookup"><span data-stu-id="147cd-110">People.Read</span></span>

- <span data-ttu-id="147cd-111">Contactos.Lectura.Todos</span><span class="sxs-lookup"><span data-stu-id="147cd-111">People.Read.All</span></span>

- <span data-ttu-id="147cd-112">Sitios.Lectura.Todos</span><span class="sxs-lookup"><span data-stu-id="147cd-112">Sites.Read.All</span></span>

- <span data-ttu-id="147cd-113">Usuario.Lectura.Todos</span><span class="sxs-lookup"><span data-stu-id="147cd-113">User.Read.All</span></span>

<span data-ttu-id="147cd-114">Para obtener información sobre cómo gestionar el ámbito de los permisos de Microsoft Graph, consulte [Ámbito de permisos](https://msdn.microsoft.com/Library/Azure/Ad/Graph/howto/azure-ad-graph-api-permission-scopes).</span><span class="sxs-lookup"><span data-stu-id="147cd-114">For more information about how to manage Microsoft Graph permission scopes, see [Permission scopes](https://msdn.microsoft.com/Library/Azure/Ad/Graph/howto/azure-ad-graph-api-permission-scopes).</span></span>
 
<span data-ttu-id="147cd-115">Para obtener información sobre los permisos de Microsoft Graph, consulte [Referencia de permisos de Microsoft Graph](https://developer.microsoft.com/graph/docs/concepts/permissions_reference).</span><span class="sxs-lookup"><span data-stu-id="147cd-115">For more information about Microsoft Graph permissions, see [Microsoft Graph permissions reference](https://developer.microsoft.com/graph/docs/concepts/permissions_reference).</span></span>