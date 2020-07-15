---
title: Compartir archivos en Microsoft Teams
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: haagaraw
audience: admin
search.appverid: MET150
description: Obtenga más información sobre la experiencia de uso compartido de archivos en Microsoft Teams.
localization_priority: Normal
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 98935f7d8629e22b733b12f3f046ccb7af36b396
ms.sourcegitcommit: 70b80892a152f86a6d596f0f5b58cf391bc29098
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/15/2020
ms.locfileid: "45138382"
---
# <a name="sharing-files-in-microsoft-teams"></a><span data-ttu-id="50551-103">Compartir archivos en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="50551-103">Sharing files in Microsoft Teams</span></span>

<span data-ttu-id="50551-104">En Microsoft Teams, los usuarios pueden compartir contenido con otros usuarios de Teams dentro y fuera de su organización.</span><span class="sxs-lookup"><span data-stu-id="50551-104">In Microsoft Teams, users can share content with other Teams users within and outside their organization.</span></span> <span data-ttu-id="50551-105">El uso compartido en Teams se basa en la configuración establecida en SharePoint y OneDrive, por lo que todo lo que configure para SharePoint y OneDrive controlará también el uso compartido en Teams.</span><span class="sxs-lookup"><span data-stu-id="50551-105">Sharing in Teams is based on the settings configured in SharePoint and OneDrive, so whatever you set up for SharePoint and OneDrive will control sharing in Teams as well.</span></span>

## <a name="overview"></a><span data-ttu-id="50551-106">Información general</span><span class="sxs-lookup"><span data-stu-id="50551-106">Overview</span></span>

<span data-ttu-id="50551-107">Los usuarios pueden compartir archivos de OneDrive, desde los equipos y los sitios a los que tienen acceso y desde su equipo.</span><span class="sxs-lookup"><span data-stu-id="50551-107">Users can share files from OneDrive, from teams and sites they have access to, and from their computer.</span></span> <span data-ttu-id="50551-108">Para compartir un archivo, los usuarios pueden hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="50551-108">To share a file, users can do the following:</span></span>

- <span data-ttu-id="50551-109">En un canal, haga clic en **adjuntar** (el icono de clip), seleccione **recientes**, **examinar equipos y canales**, **OneDrive**o **cargar desde mi equipo**y, a continuación, elija el archivo que desea compartir.</span><span class="sxs-lookup"><span data-stu-id="50551-109">In a channel, click **Attach** (the paperclip icon), select **Recent**, **Browse Teams and Channels**, **OneDrive**, or **Upload from my computer**, and then choose the file they want to share.</span></span> <br> 
    <span data-ttu-id="50551-110">![Captura de pantalla que muestra el uso compartido de un archivo desde un canal](media/share-files-channel.png)</span><span class="sxs-lookup"><span data-stu-id="50551-110">![Screenshot showing sharing a file from a channel](media/share-files-channel.png)</span></span>
- <span data-ttu-id="50551-111">En un chat, haga clic en **adjuntar** (el icono de clip), seleccione o **OneDrive** o **cargar desde mi equipo**y, a continuación, elija el archivo que desea compartir.</span><span class="sxs-lookup"><span data-stu-id="50551-111">In a chat, click **Attach** (the paperclip icon), select  or **OneDrive** or **Upload from my computer**, and then choose the file they want to share.</span></span> <br>
    <span data-ttu-id="50551-112">![Captura de pantalla que muestra compartir un archivo desde un chat](media/share-files-chat.png)</span><span class="sxs-lookup"><span data-stu-id="50551-112">![Screenshot showing sharing a file from a chat](media/share-files-chat.png)</span></span>
- <span data-ttu-id="50551-113">Copie y pegue el vínculo para compartir en el cuadro de redacción.</span><span class="sxs-lookup"><span data-stu-id="50551-113">Copy and paste the sharing link in the compose box.</span></span><br>
    <span data-ttu-id="50551-114">![Captura de pantalla que muestra la vista previa del archivo en el cuadro de redacción](media/share-files-link.png)</span><span class="sxs-lookup"><span data-stu-id="50551-114">![Screenshot showing file preview in the compose box](media/share-files-link.png)</span></span>

### <a name="what-you-need-to-know-about-the-file-sharing-experience"></a><span data-ttu-id="50551-115">Lo que debe saber sobre la experiencia de uso compartido de archivos</span><span class="sxs-lookup"><span data-stu-id="50551-115">What you need to know about the file sharing experience</span></span>

### <a name="permissions-of-shared-files-and-sharing-links"></a><span data-ttu-id="50551-116">Permisos de archivos compartidos y vínculos de uso compartido</span><span class="sxs-lookup"><span data-stu-id="50551-116">Permissions of shared files and sharing links</span></span>

<span data-ttu-id="50551-117">Cuando los usuarios comparten un archivo desplazándose hasta él en OneDrive o en equipos y canales, a todos los destinatarios se les concede acceso junto con los [permisos predeterminados que se establecen en el nivel de la organización](https://docs.microsoft.com/sharepoint/change-default-sharing-link).</span><span class="sxs-lookup"><span data-stu-id="50551-117">When users share a file by browsing to it in OneDrive or teams and channels, all recipients are granted access along with the [default permission that's set at the organization level](https://docs.microsoft.com/sharepoint/change-default-sharing-link).</span></span>

<span data-ttu-id="50551-118">Cuando un usuario copia y pega un vínculo de uso compartido, se consiguen los permisos establecidos en ese vínculo para compartir y la dirección URL de SharePoint se acorta al nombre de archivo.</span><span class="sxs-lookup"><span data-stu-id="50551-118">When a user copies and pastes a sharing link, the permissions set on that sharing link are honored and the SharePoint URL is shortened to the file name.</span></span> <span data-ttu-id="50551-119">En otras palabras, Teams usa solo el nombre de archivo para vincular a un archivo.</span><span class="sxs-lookup"><span data-stu-id="50551-119">In other words, Teams uses just the file name to link to a file.</span></span>

<span data-ttu-id="50551-120">Cuando los usuarios comparten un archivo desde Teams, pueden establecer quién puede acceder al archivo de la misma manera que en Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="50551-120">When users share a file from within Teams, they can set who can access the file just like they do across Microsoft 365.</span></span> <span data-ttu-id="50551-121">Pueden dar acceso a cualquier persona, a las personas de su organización, a personas con acceso existente o a personas específicas (que pueden incluir a las personas en un chat de 1:1, una conversación grupal o un canal).</span><span class="sxs-lookup"><span data-stu-id="50551-121">They can give access to anyone, people in your organization, people with existing access, or specific people (which can include the people in a 1:1 chat, group chat, or channel).</span></span>  <span data-ttu-id="50551-122">Cuando un archivo está compartido, la vista previa del archivo está disponible en el mensaje, junto con todas las acciones de archivo, como **abrir en línea**, **Descargar**y **Copiar vínculo**.</span><span class="sxs-lookup"><span data-stu-id="50551-122">When a file is shared, the file preview is available in the message, along with all file actions such as **Open online**, **Download**, and **Copy link**.</span></span> <span data-ttu-id="50551-123">De forma predeterminada, el archivo se abre en Teams.</span><span class="sxs-lookup"><span data-stu-id="50551-123">By default, the file opens in Teams.</span></span> <span data-ttu-id="50551-124">En ocasiones, es posible que el vínculo para compartir no se haya convertido a una vista previa de archivo en el momento en que un usuario envía el mensaje.</span><span class="sxs-lookup"><span data-stu-id="50551-124">Sometimes, the sharing link may not have converted to a file preview by the time a user sends the message.</span></span> <span data-ttu-id="50551-125">El sistema generará la vista previa del archivo, pero en este escenario, el vínculo para compartir no se acortará al único nombre de archivo.</span><span class="sxs-lookup"><span data-stu-id="50551-125">The file preview will be generated by the system, but in this scenario, the sharing link won't be shortened to the only the file name.</span></span>

<span data-ttu-id="50551-126">Cuando los usuarios comparten un archivo en un canal o una conversación, se les notifica si algunos o todos los destinatarios no tienen permiso para ver el archivo.</span><span class="sxs-lookup"><span data-stu-id="50551-126">When users share a file in a chat or channel, they're notified whether some or all recipients don't have permission to view the file.</span></span> <span data-ttu-id="50551-127">Pueden cambiar los permisos del archivo antes de compartirlo haciendo clic en la flecha situada junto a la vista previa del archivo que aparece en el mensaje.</span><span class="sxs-lookup"><span data-stu-id="50551-127">They can change the permissions on the file before they share it by clicking the arrow next to the file preview that now appears in the message.</span></span>

![Captura de pantalla de la notificación si los destinatarios no tienen permisos](media/share-files-permissions.png)

### <a name="copy-a-sharing-link-in-teams"></a><span data-ttu-id="50551-129">Copiar un vínculo para compartir en Teams</span><span class="sxs-lookup"><span data-stu-id="50551-129">Copy a sharing link in Teams</span></span>

<span data-ttu-id="50551-130">Los usuarios pueden copiar un vínculo para compartir de SharePoint y cambiar los permisos de uso compartido del mismo modo que en Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="50551-130">Users can copy a SharePoint sharing link and change sharing permissions just like they do across Microsoft 365.</span></span> <span data-ttu-id="50551-131">Pueden conceder acceso a cualquier persona, a personas de su organización, a personas con acceso existente o a personas específicas.</span><span class="sxs-lookup"><span data-stu-id="50551-131">They can give access to anyone, people in your organization, people with existing access, or specific people.</span></span> <span data-ttu-id="50551-132">El permiso predeterminado del vínculo es el mismo que el conjunto de permisos predeterminado en el nivel de la organización, a menos que los permisos del nivel del sitio de SharePoint lo reemplacen.</span><span class="sxs-lookup"><span data-stu-id="50551-132">The default permission of the link is the same as the default permission set at the organization level unless SharePoint site level permissions override it.</span></span>

## <a name="configure-sharing-in-onedrive-and-sharepoint"></a><span data-ttu-id="50551-133">Configurar el uso compartido en OneDrive y SharePoint</span><span class="sxs-lookup"><span data-stu-id="50551-133">Configure sharing in OneDrive and SharePoint</span></span>

<span data-ttu-id="50551-134">Para obtener más información sobre cómo compartir archivos en OneDrive y SharePoint, incluido cómo configurar el uso compartido y cómo activar y desactivar el uso compartido, vea:</span><span class="sxs-lookup"><span data-stu-id="50551-134">For more information about sharing files in OneDrive and SharePoint, including how to configure sharing and how to turn sharing on and off, see:</span></span>

- <span data-ttu-id="50551-135">[Información general sobre el uso compartido externo](https://docs.microsoft.com/sharepoint/external-sharing-overview) : describe lo que ocurre cuando los usuarios comparten, en función de lo que estén compartiendo y con quién.</span><span class="sxs-lookup"><span data-stu-id="50551-135">[External sharing overview](https://docs.microsoft.com/sharepoint/external-sharing-overview) - describes what happens when users share, depending on what they're sharing and with whom.</span></span>

- <span data-ttu-id="50551-136">[Administrar la configuración de uso compartido](https://docs.microsoft.com/sharepoint/turn-external-sharing-on-or-off) : describe cómo los administradores globales y de SharePoint pueden cambiar la configuración de uso compartido en el nivel de organización para SharePoint y OneDrive.</span><span class="sxs-lookup"><span data-stu-id="50551-136">[Manage sharing settings](https://docs.microsoft.com/sharepoint/turn-external-sharing-on-or-off) - describes how global and SharePoint admins can change their organization-level sharing settings for SharePoint and OneDrive.</span></span>

- <span data-ttu-id="50551-137">[Activar o desactivar el uso compartido externo en un sitio](https://docs.microsoft.com/sharepoint/change-external-sharing-site) : describe cómo los administradores globales y de SharePoint pueden activar o desactivar el uso compartido externo en un sitio.</span><span class="sxs-lookup"><span data-stu-id="50551-137">[Turn external sharing on or off for a site](https://docs.microsoft.com/sharepoint/change-external-sharing-site) – describes how global and SharePoint admins can turn external sharing on or off for a site.</span></span>

- <span data-ttu-id="50551-138">[Cambiar el tipo de vínculo predeterminado para un sitio](https://docs.microsoft.com/sharepoint/change-default-sharing-link) : describe cómo establecer el tipo de vínculo predeterminado para que sea más restrictivo.</span><span class="sxs-lookup"><span data-stu-id="50551-138">[Change the default link type for a site](https://docs.microsoft.com/sharepoint/change-default-sharing-link) - describes how to set the default link type so that it's more restrictive.</span></span>

## <a name="more-information"></a><span data-ttu-id="50551-139">Más información</span><span class="sxs-lookup"><span data-stu-id="50551-139">More information</span></span>

- [<span data-ttu-id="50551-140">Interacción de SharePoint Online y OneDrive para la Empresa con Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="50551-140">How SharePoint Online and OneDrive for Business interact with Microsoft Teams</span></span>](sharepoint-onedrive-interact.md)

- [<span data-ttu-id="50551-141">SharePoint y Teams: mejor juntos</span><span class="sxs-lookup"><span data-stu-id="50551-141">SharePoint and Teams: better together</span></span>](https://techcommunity.microsoft.com/t5/Microsoft-SharePoint-Blog/SharePoint-and-Teams-Better-Together/ba-p/189593)

- [<span data-ttu-id="50551-142">Compartir archivos y carpetas de OneDrive</span><span class="sxs-lookup"><span data-stu-id="50551-142">Share OneDrive files and folders</span></span>](https://support.office.com/article/Share-OneDrive-files-and-folders-9fcc2f7d-de0c-4cec-93b0-a82024800c07#OS_Type=OneDrive_-_Business)

- [<span data-ttu-id="50551-143">Compartir archivos o carpetas de SharePoint</span><span class="sxs-lookup"><span data-stu-id="50551-143">Share SharePoint files or folders</span></span>](https://support.office.com/article/share-sharepoint-files-or-folders-1fe37332-0f9a-4719-970e-d2578da4941c)
