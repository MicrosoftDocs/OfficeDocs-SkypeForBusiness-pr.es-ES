---
title: Directivas de retención en Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: prvijay
description: Obtenga información sobre cómo usar las directivas de retención y cómo administrarlas en Teams.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 73d8de57b7b47ced8217e0f7aca384f4b55b0468
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/08/2020
ms.locfileid: "40988985"
---
# <a name="retention-policies-in-microsoft-teams"></a><span data-ttu-id="08d4d-103">Directivas de retención en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="08d4d-103">Retention policies in Microsoft Teams</span></span>

<span data-ttu-id="08d4d-104">Las conversaciones de Teams son persistentes y se conservan para siempre de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="08d4d-104">Teams conversations are persistent and retained forever by default.</span></span> <span data-ttu-id="08d4d-105">Con la introducción de las directivas de retención, los administradores pueden configurar directivas de retención (tanto de conservación como de eliminación) en el centro de cumplimiento de seguridad & para los mensajes de chat y de canal de Teams.</span><span class="sxs-lookup"><span data-stu-id="08d4d-105">With the introduction of retention policies, admins can configure retention policies (both preservation and deletion) in the Security & Compliance Center for Teams chat and channel messages.</span></span> <span data-ttu-id="08d4d-106">Esto ayuda a las organizaciones a retener datos de cumplimiento (concretamente, a la Directiva de conservación) durante un período específico o a deshacerse de los datos (es decir, la política de eliminación) si se considera un pasivo después de un período específico.</span><span class="sxs-lookup"><span data-stu-id="08d4d-106">This helps organizations either retain data for compliance (namely, preservation policy) for a specific period or get rid of data (namely, deletion policy) if it is considered a liability after a specific period.</span></span> <span data-ttu-id="08d4d-107">Las directivas de retención de Teams garantizan que cuando se eliminan datos, se quitan de todas las ubicaciones de almacenamiento de datos permanentes en el servicio de Teams.</span><span class="sxs-lookup"><span data-stu-id="08d4d-107">Teams retention policies ensure that when you delete data, it is removed from all permanent data storage locations on the Teams service.</span></span>

> [!NOTE]
> <span data-ttu-id="08d4d-108">Aún no se admite la configuración de retención de mensajes de canal privado.</span><span class="sxs-lookup"><span data-stu-id="08d4d-108">We don’t yet support configuration for retention of private channel messages.</span></span> <span data-ttu-id="08d4d-109">La retención de archivos compartidos en canales privados es compatible.</span><span class="sxs-lookup"><span data-stu-id="08d4d-109">Retention of files shared in private channels is supported.</span></span>

<span data-ttu-id="08d4d-110">Para administrar las directivas de retención de Teams, use la configuración y cmdlets del centro de cumplimiento de Office 365 Security & en**retención**de **gobierno** > de información.</span><span class="sxs-lookup"><span data-stu-id="08d4d-110">To manage Teams retention policies, use the settings and cmdlets in the Office 365 Security & Compliance Center under **Information governance** > **Retention**.</span></span>

<span data-ttu-id="08d4d-111">Las directivas de retención de Teams sí son compatibles:</span><span class="sxs-lookup"><span data-stu-id="08d4d-111">Teams retention policies do support:</span></span> 
    
- <span data-ttu-id="08d4d-112">Preservación: mantener los datos de Teams por una duración determinada y no hacer nada</span><span class="sxs-lookup"><span data-stu-id="08d4d-112">Preservation: Keep Teams data for a specified duration and then do nothing</span></span>
- <span data-ttu-id="08d4d-113">Preservación y, a continuación, eliminar: mantener los datos de Teams durante un período específico y, a continuación, eliminar</span><span class="sxs-lookup"><span data-stu-id="08d4d-113">Preservation and then delete: Keep Teams data for a specified duration and then delete</span></span>
- <span data-ttu-id="08d4d-114">Eliminación: eliminar datos de Teams después de un período de tiempo especificado</span><span class="sxs-lookup"><span data-stu-id="08d4d-114">Deletion: Delete Teams data after a specified duration</span></span>

<span data-ttu-id="08d4d-115">Las directivas de retención de Teams aún no son compatibles:</span><span class="sxs-lookup"><span data-stu-id="08d4d-115">Teams retention policies do not yet support:</span></span>

- <span data-ttu-id="08d4d-116">Las directivas de retención avanzadas no se aplican a los equipos chat y Teams canales de mensajes</span><span class="sxs-lookup"><span data-stu-id="08d4d-116">Advanced retention policies don't apply to Teams chat and Teams channel message locations</span></span>

<span data-ttu-id="08d4d-117">Los administradores pueden configurar directivas de retención diferentes para los chats privados de los equipos (1:1 o 1: muchos chats) y los mensajes de canal de Teams.</span><span class="sxs-lookup"><span data-stu-id="08d4d-117">Admins can set up separate retention policies for Teams private chats (1:1 or 1:Many chats) and Teams channel messages.</span></span> <span data-ttu-id="08d4d-118">En muchos casos, las organizaciones consideran que los datos de los chats privados son más responsabilidad de los mensajes de canal, que suelen ser más conversaciones relacionadas con el proyecto.</span><span class="sxs-lookup"><span data-stu-id="08d4d-118">In many cases, organizations consider private chat data as more of a liability than channel messages, which are usually more project-related conversations.</span></span> <span data-ttu-id="08d4d-119">Configure estas directivas en el centro de cumplimiento de & de seguridad,**retención**del **gobierno** > de la información.</span><span class="sxs-lookup"><span data-stu-id="08d4d-119">Set up these policies in the Security & Compliance Center, **Information governance** > **Retention**.</span></span> <span data-ttu-id="08d4d-120">Active **los mensajes de canal de Teams y los** **chats de equipos** y, a continuación, defina las directivas de retención para estas ubicaciones (también se muestra en el diagrama siguiente).</span><span class="sxs-lookup"><span data-stu-id="08d4d-120">Turn on **Teams channel messages** and **Teams chats** and then define retention policies for these locations (also shown in the diagram below).</span></span> 

<span data-ttu-id="08d4d-121">Al activar **los mensajes de canal de Teams**, puede especificar los equipos a los que se aplicará esta Directiva.</span><span class="sxs-lookup"><span data-stu-id="08d4d-121">When you turn on **Teams channel messages**, you can specify Teams to which this policy will apply.</span></span> <span data-ttu-id="08d4d-122">Por ejemplo, para Teams X, y y Z, el administrador puede establecer las directivas de eliminación para un año (seleccionando esos equipos individualmente) y aplicar una directiva de eliminación de 3 años al resto de los equipos.</span><span class="sxs-lookup"><span data-stu-id="08d4d-122">For example, for teams X, Y, and Z, the admin can set the deletion policies for 1 year (by selecting those teams individually), and apply a 3-year deletion policy to the rest of the teams.</span></span> 

<span data-ttu-id="08d4d-123">Puede hacer lo mismo para los **chats de Teams** seleccionando usuarios específicos y aplicando directivas de retención únicas.</span><span class="sxs-lookup"><span data-stu-id="08d4d-123">You can do the same thing for **Teams chats** by selecting specific users and applying unique retention policies.</span></span> 

![Diagrama del flujo de trabajo de los datos de Teams en Exchange y SharePoint.](media/Retention-Policies.png)


> [!IMPORTANT]
> <span data-ttu-id="08d4d-125">Las ubicaciones de los mensajes de canal y equipos de chat de equipos solo se redireccionan a las conversaciones de Teams almacenadas en buzones de Exchange Online (buzones de usuario y de grupo).</span><span class="sxs-lookup"><span data-stu-id="08d4d-125">The Teams channel message locations and Teams chats locations only address the Teams conversations stored in Exchange Online mailboxes (user and group mailboxes).</span></span> <span data-ttu-id="08d4d-126">Los mensajes se eliminan de todas las ubicaciones de almacenamiento relevantes, es decir, los buzones, el sustrato y el servicio de chat.</span><span class="sxs-lookup"><span data-stu-id="08d4d-126">The messages are deleted from all relevant storage locations, namely the mailboxes, substrate, and chat service.</span></span> 
> 
> <span data-ttu-id="08d4d-127">Para administrar las directivas de retención de los archivos de Teams, que se almacenan en OneDrive para la empresa y SharePoint, use sus directivas de retención.</span><span class="sxs-lookup"><span data-stu-id="08d4d-127">To manage retention policies for Teams files, which are stored in OneDrive for Business and SharePoint, use their retention policies.</span></span>

<span data-ttu-id="08d4d-128">Por diseño, las directivas de eliminación de los archivos de Teams se configuran a través de SharePoint Online y OneDrive para la empresa.</span><span class="sxs-lookup"><span data-stu-id="08d4d-128">By design, deletion policies for Teams files are configured through SharePoint Online and OneDrive for Business locations.</span></span> <span data-ttu-id="08d4d-129">Como resultado, es posible que una directiva pueda eliminar un archivo al que se hace referencia en una conversación de equipos o un mensaje de canal antes de que esos mensajes se eliminen.</span><span class="sxs-lookup"><span data-stu-id="08d4d-129">As a result, it's possible that a policy could delete a file referenced in a Teams chat or channel message before those messages get deleted.</span></span> <span data-ttu-id="08d4d-130">En este caso, el archivo seguirá apareciendo en el mensaje de Teams, pero si hace clic en el archivo, aparecerá el error "no se encuentra el archivo" (esto también podría ocurrir si alguien elimina manualmente un archivo de SharePoint Online o OneDrive para la empresa).</span><span class="sxs-lookup"><span data-stu-id="08d4d-130">In this case, the file will still show up in the Teams message, but if you click the file, you'll get a "File not found" error (this could also happen in the absence of a policy, if someone manually deletes a file from SharePoint Online or OneDrive for Business).</span></span>

<span data-ttu-id="08d4d-131">Para obtener información detallada sobre cómo configurar directivas de retención para Office 365, consulte [información general sobre las directivas de retención](https://support.office.com/article/overview-of-retention-policies-5e377752-700d-4870-9b6d-12bfc12d2423).</span><span class="sxs-lookup"><span data-stu-id="08d4d-131">For detailed information about configuring retention policies for Office 365, read [Overview of retention policies](https://support.office.com/article/overview-of-retention-policies-5e377752-700d-4870-9b6d-12bfc12d2423).</span></span>
 
