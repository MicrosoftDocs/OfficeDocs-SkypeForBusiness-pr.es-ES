---
title: Directivas de retención en Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/11/2018
ms.topic: article
ms.service: msteams
ms.reviewer: anach
description: Obtenga información sobre cómo las directivas de retención y cómo se administran en los equipos.
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4d07629f41a54dcab1995f2aef2d7536479be25d
ms.sourcegitcommit: 85c34280977fb2c15c8a43874a20e9492bdca57f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/07/2019
ms.locfileid: "30464559"
---
# <a name="retention-policies-in-microsoft-teams"></a><span data-ttu-id="ee53e-103">Directivas de retención en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="ee53e-103">Retention policies in Microsoft Teams</span></span>

<span data-ttu-id="ee53e-104">Las conversaciones de los equipos son persistentes y retenidas para siempre de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="ee53e-104">Teams conversations are persistent and retained forever by default.</span></span> <span data-ttu-id="ee53e-105">Con la introducción de las directivas de retención, los administradores pueden configurar las directivas de retención (conservación y eliminación) en el centro de cumplimiento de & de seguridad para los mensajes de chat y canal de los equipos.</span><span class="sxs-lookup"><span data-stu-id="ee53e-105">With the introduction of retention policies, admins can configure retention policies (both preservation and deletion) in the Security & Compliance Center for Teams chat and channel messages.</span></span> <span data-ttu-id="ee53e-106">Esto ayuda a las organizaciones retener datos para el cumplimiento (es decir, la directiva de conservación) durante un período específico o deshacerse de datos (es decir, la directiva de eliminación) si se considera una responsabilidad después de un período específico.</span><span class="sxs-lookup"><span data-stu-id="ee53e-106">This helps organizations either retain data for compliance (namely, preservation policy) for a specific period or get rid of data (namely, deletion policy) if it is considered a liability after a specific period.</span></span> <span data-ttu-id="ee53e-107">Las directivas de retención de los equipos Asegúrese de que al eliminar datos, se elimina de todas las ubicaciones de almacenamiento de datos permanente en el servicio de los equipos.</span><span class="sxs-lookup"><span data-stu-id="ee53e-107">Teams retention policies ensure that when you delete data, it is removed from all permanent data storage locations on the Teams service.</span></span> 

<span data-ttu-id="ee53e-108">Para administrar las directivas de retención de los equipos, use los cmdlets y la configuración en el centro de cumplimiento en **Datos de gobierno**de seguridad de Office 365 & > **retención**.</span><span class="sxs-lookup"><span data-stu-id="ee53e-108">To manage Teams retention policies, use the settings and cmdlets in the Office 365 Security & Compliance Center under **Data Governance** > **Retention**.</span></span>

<span data-ttu-id="ee53e-109">Son compatibles con las directivas de retención de los equipos:</span><span class="sxs-lookup"><span data-stu-id="ee53e-109">Teams retention policies do support:</span></span> 
    
- <span data-ttu-id="ee53e-110">Conservación: Conservar los datos de los equipos por una duración especificada y, a continuación, no haga nada</span><span class="sxs-lookup"><span data-stu-id="ee53e-110">Preservation: Keep Teams data for a specified duration and then do nothing</span></span>
- <span data-ttu-id="ee53e-111">Conservación y, a continuación, eliminar: conservar los datos de los equipos por una duración especificada y, a continuación, eliminar</span><span class="sxs-lookup"><span data-stu-id="ee53e-111">Preservation and then delete: Keep Teams data for a specified duration and then delete</span></span>
- <span data-ttu-id="ee53e-112">Eliminación: Eliminar datos de los equipos tras una duración especificada</span><span class="sxs-lookup"><span data-stu-id="ee53e-112">Deletion: Delete Teams data after a specified duration</span></span>

<span data-ttu-id="ee53e-113">Aún no admiten las directivas de retención de los equipos:</span><span class="sxs-lookup"><span data-stu-id="ee53e-113">Teams retention policies do not yet support:</span></span>

- <span data-ttu-id="ee53e-114">Las directivas de retención avanzadas no se aplican a conversaciones en los equipos y ubicaciones de mensajes de canal de los equipos</span><span class="sxs-lookup"><span data-stu-id="ee53e-114">Advanced retention policies don't apply to Teams chat and Teams channel message locations</span></span>
- <span data-ttu-id="ee53e-115">Duración de menos de 30 días</span><span class="sxs-lookup"><span data-stu-id="ee53e-115">Duration of fewer than 30 days</span></span>

<span data-ttu-id="ee53e-116">Los administradores pueden configurar las directivas de retención independiente para chats privadas de los equipos (1:1 o 1: muchas chats) y los mensajes del canal de los equipos.</span><span class="sxs-lookup"><span data-stu-id="ee53e-116">Admins can set up separate retention policies for Teams private chats (1:1 or 1:Many chats) and Teams channel messages.</span></span> <span data-ttu-id="ee53e-117">En muchos casos, las organizaciones, tenga en cuenta los datos de chat privado como más de un pasivo que no son mensajes de canal, que suelen ser más conversaciones relacionados con el proyecto.</span><span class="sxs-lookup"><span data-stu-id="ee53e-117">In many cases, organizations consider private chat data as more of a liability than channel messages, which are usually more project-related conversations.</span></span> <span data-ttu-id="ee53e-118">Configurar estas directivas en el centro de cumplimiento, de & seguridad **Gobierno datos** > **retención**.</span><span class="sxs-lookup"><span data-stu-id="ee53e-118">Set up these policies in the Security & Compliance Center, **Data governance** > **Retention**.</span></span> <span data-ttu-id="ee53e-119">Activar **los mensajes del canal de los equipos** y **los equipos de chat** y, a continuación, defina las directivas de retención para estas ubicaciones (también se muestra en el diagrama siguiente).</span><span class="sxs-lookup"><span data-stu-id="ee53e-119">Turn on **Teams channel messages** and **Teams chats** and then define retention policies for these locations (also shown in the diagram below).</span></span> 

<span data-ttu-id="ee53e-120">Cuando se activa en **los equipos de los mensajes del canal**, puede especificar los equipos a los que se aplicará esta directiva.</span><span class="sxs-lookup"><span data-stu-id="ee53e-120">When you turn on **Teams channel messages**, you can specify Teams to which this policy will apply.</span></span> <span data-ttu-id="ee53e-121">Por ejemplo, para equipos de X, Y y Z, el administrador puede establecer las directivas de eliminación para 1 año (seleccionando esos equipos de forma individual) y aplicar una directiva de eliminación de 3 años para el resto de los equipos.</span><span class="sxs-lookup"><span data-stu-id="ee53e-121">For example, for teams X, Y, and Z, the admin can set the deletion policies for 1 year (by selecting those teams individually), and apply a 3-year deletion policy to the rest of the teams.</span></span> 

<span data-ttu-id="ee53e-122">Puede hacer lo mismo para **los equipos de chat** mediante la selección de usuarios específicos y aplicar las directivas de retención único.</span><span class="sxs-lookup"><span data-stu-id="ee53e-122">You can do the same thing for **Teams chats** by selecting specific users and applying unique retention policies.</span></span> 

![Diagrama del flujo de trabajo de los datos de Teams en Exchange y SharePoint.](media/Retention-Policies.png)


> [!IMPORTANT]
> <span data-ttu-id="ee53e-124">Las ubicaciones de mensaje de canal de los equipos y ubicaciones de los equipos chats dirección sólo las conversaciones de los equipos almacenadas en los buzones de Exchange Online (buzones de usuario y de grupo).</span><span class="sxs-lookup"><span data-stu-id="ee53e-124">The Teams channel message locations and Teams chats locations only address the Teams conversations stored in Exchange Online mailboxes (user and group mailboxes).</span></span> <span data-ttu-id="ee53e-125">Los mensajes se eliminan de todas las ubicaciones de almacenamiento de información relevante, es decir, los buzones de correo, sustrato y servicio de chat.</span><span class="sxs-lookup"><span data-stu-id="ee53e-125">The messages are deleted from all relevant storage locations, namely the mailboxes, substrate, and chat service.</span></span> 
> 
> <span data-ttu-id="ee53e-126">Para administrar las directivas de retención para los archivos de los equipos, que se almacenan en OneDrive para profesionales y SharePoint, use sus directivas de retención.</span><span class="sxs-lookup"><span data-stu-id="ee53e-126">To manage retention policies for Teams files, which are stored in OneDrive for Business and SharePoint, use their retention policies.</span></span>

<span data-ttu-id="ee53e-127">Por diseño, se configuran las directivas de eliminación para los archivos de los equipos a través de SharePoint Online y OneDrive para las ubicaciones de negocio.</span><span class="sxs-lookup"><span data-stu-id="ee53e-127">By design, deletion policies for Teams files are configured through SharePoint Online and OneDrive for Business locations.</span></span> <span data-ttu-id="ee53e-128">Como resultado, es posible que una directiva pudo eliminar un archivo al que hace referencia en un mensaje de chat o canal de los equipos antes de que se eliminan los mensajes.</span><span class="sxs-lookup"><span data-stu-id="ee53e-128">As a result, it's possible that a policy could delete a file referenced in a Teams chat or channel message before those messages get deleted.</span></span> <span data-ttu-id="ee53e-129">En este caso, el archivo aún se mostrará en el mensaje de los equipos, pero si hace clic en el archivo, obtendrá un error de "Archivo no encontrado" (también puede suceder en ausencia de una directiva, si alguien elimina manualmente un archivo de SharePoint Online o OneDrive para la empresa).</span><span class="sxs-lookup"><span data-stu-id="ee53e-129">In this case, the file will still show up in the Teams message, but if you click the file, you'll get a "File not found" error (this could also happen in the absence of a policy, if someone manually deletes a file from SharePoint Online or OneDrive for Business).</span></span>

<span data-ttu-id="ee53e-130">Para obtener información detallada acerca de cómo configurar las directivas de retención para Office 365, lea [información general de las directivas de retención](https://support.office.com/article/overview-of-retention-policies-5e377752-700d-4870-9b6d-12bfc12d2423).</span><span class="sxs-lookup"><span data-stu-id="ee53e-130">For detailed information about configuring retention policies for Office 365, read [Overview of retention policies](https://support.office.com/article/overview-of-retention-policies-5e377752-700d-4870-9b6d-12bfc12d2423).</span></span>
 
