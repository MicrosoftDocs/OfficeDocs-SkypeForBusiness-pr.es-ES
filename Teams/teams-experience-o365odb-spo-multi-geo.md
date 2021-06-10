---
title: Teams experiencia en un Microsoft 365 multi-geo-enabled
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: snigdhav
audience: admin
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
- SPO_Content
ms.custom: seo-marvel-apr2020
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
description: En este artículo, aprenderá a usar Teams en un Microsoft 365 habilitado para varias ubicaciones geográficas.
ms.openlocfilehash: a1b86cf83a0eabde81331e5311561aa1600d3c7e
ms.sourcegitcommit: ca2230a981a1e3c03437d1ecb8727d66ad6967f9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/14/2021
ms.locfileid: "51760543"
---
# <a name="teams-experience-in-a-microsoft-365-multi-geo-enabled-tenancy"></a><span data-ttu-id="ae500-103">Teams experiencia en un Microsoft 365 de arrendamiento habilitado para varias ubicaciones geográficas</span><span class="sxs-lookup"><span data-stu-id="ae500-103">Teams experience in a Microsoft 365 Multi-Geo-enabled tenancy</span></span>

<span data-ttu-id="ae500-104">Microsoft Teams es el software de chat grupal, el centro para el trabajo en equipo en Microsoft 365 y Office 365.</span><span class="sxs-lookup"><span data-stu-id="ae500-104">Microsoft Teams is group chat software, the hub for teamwork in Microsoft 365 and Office 365.</span></span> <span data-ttu-id="ae500-105">Funciona con tecnología del servicio Microsoft 365 Groups junto con SharePoint Online y OneDrive para la Empresa para su experiencia de archivos.</span><span class="sxs-lookup"><span data-stu-id="ae500-105">It's powered by the Microsoft 365 Groups service along with SharePoint Online and OneDrive for Business for its files experience.</span></span> <span data-ttu-id="ae500-106">En una tenencia de OneDrive para la Empresa/SharePoint Online Multi-Geo, en la que el espacio empresarial se extiende a muchas ubicaciones geográficas como Norteamérica, Europa y Australia, la experiencia de archivos subyacentes es multi-geo-aware, por lo que la experiencia Teams con la colaboración de archivos también es multi-geo-aware.</span><span class="sxs-lookup"><span data-stu-id="ae500-106">In a OneDrive for Business/SharePoint Online Multi-Geo tenancy, in which the tenant is extended to many geographic locations such as North America, Europe, and Australia, the underlying files experience is Multi-Geo-aware, so the Teams experience with file collaboration is also Multi-Geo-aware.</span></span> <span data-ttu-id="ae500-107">Esta funcionalidad es una funcionalidad clave de vanguardia para Teams a los archivos de superficie hospedados en varios geos en su experiencia de archivos nativos.</span><span class="sxs-lookup"><span data-stu-id="ae500-107">This functionality is a key leading-edge capability for Teams to surface files that are hosted across multiple Geos in its native files experience.</span></span> <span data-ttu-id="ae500-108">Esto también incluye OneNote y wiki.</span><span class="sxs-lookup"><span data-stu-id="ae500-108">This also includes OneNote and Wiki files.</span></span>

<span data-ttu-id="ae500-109">Por ejemplo, en una tenencia de Contoso con Europa como satélite Geo y Norteamérica como geo central,  un usuario de satélite europeo verá sus archivos OneDrive en la pestaña Archivos en el panel izquierdo, aunque los archivos se hospedan en la ubicación de datos de Europa y Estados Unidos es la ubicación central del inquilino.</span><span class="sxs-lookup"><span data-stu-id="ae500-109">For example, in a Contoso tenancy with Europe as a satellite Geo and North America as the central Geo, a European satellite user will see their OneDrive files under the **Files** tab in left pane, although the files are hosted in the Europe data location and the United States is the tenant’s central location.</span></span> <span data-ttu-id="ae500-110">Además, el usuario puede obtener acceso a los archivos usados más recientemente en la **hoja Vista** reciente.</span><span class="sxs-lookup"><span data-stu-id="ae500-110">Also, the user can access the most recently used files under the **Recent** view blade.</span></span> <span data-ttu-id="ae500-111">Los archivos recientes pueden incluir archivos compartidos de usuarios en otras ubicaciones geográficas.</span><span class="sxs-lookup"><span data-stu-id="ae500-111">Recent files may include files shared from users in other geo locations.</span></span> 

<span data-ttu-id="ae500-112">Un determinado sitio de SharePoint equipo también es multiges geoeconsciente.</span><span class="sxs-lookup"><span data-stu-id="ae500-112">A given Team’s SharePoint site is also Multi-Geo-aware.</span></span> <span data-ttu-id="ae500-113">Es decir, si un usuario de satélite europeo está creando un equipo, el sitio SharePoint se creará en la ubicación de Europa.</span><span class="sxs-lookup"><span data-stu-id="ae500-113">That is, if a European satellite user is creating a Team, the corresponding SharePoint site will be created in the Europe location.</span></span> <span data-ttu-id="ae500-114">Los archivos asociados a ese equipo se conservarán en reposo en esa ubicación.</span><span class="sxs-lookup"><span data-stu-id="ae500-114">The files that are associated with that Team will be kept at rest in that location.</span></span> <span data-ttu-id="ae500-115">Cualquier experiencia posterior, como cargar un archivo nuevo o editarlo, se almacenará en esa ubicación europea, manteniendo la promesa de residencia de datos para esos archivos.</span><span class="sxs-lookup"><span data-stu-id="ae500-115">Any subsequent experiences, such as uploading a new file or editing the file, will be stored in that European location, keeping the promise of data residency for those files.</span></span>

<span data-ttu-id="ae500-116">Dado que una tenencia Multi-Geo es un único inquilino global, durante @ menciones los usuarios de satélite podrán ver a sus compañeros de todo el mundo, independientemente de dónde estén.</span><span class="sxs-lookup"><span data-stu-id="ae500-116">Because a Multi-Geo tenancy is a single global tenant, during @ mentions satellite users will be able to see their colleagues from across the globe, no matter where they are.</span></span>

<span data-ttu-id="ae500-117">Las conversaciones en chats, mensajes de canales y chats de mensajería instantánea de reunión dentro de la experiencia de Teams no son multigestivas y se mantienen solo dentro de la ubicación central del inquilino.</span><span class="sxs-lookup"><span data-stu-id="ae500-117">Conversations in chats, channels messages, and meeting IM notes/chats within the Teams experience aren't Multi-Geo-aware and are all kept only inside the central location of the tenant.</span></span> <span data-ttu-id="ae500-118">Normalmente, las conversaciones de chat no se aplican a las necesidades de residencia de datos.</span><span class="sxs-lookup"><span data-stu-id="ae500-118">Typically, chat conversations aren’t applied to data residency needs.</span></span> <span data-ttu-id="ae500-119">Para obtener más información, vea [Ubicación de datos en Microsoft Teams](location-of-data-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="ae500-119">For more information, see [Location of data in Microsoft Teams](location-of-data-in-teams.md).</span></span>

<span data-ttu-id="ae500-120">La compatibilidad multiges geográfica para Teams está en el [mapa Microsoft 365 ruta.](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=70783)</span><span class="sxs-lookup"><span data-stu-id="ae500-120">Multi-Geo support for Teams is on the [Microsoft 365 roadmap](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=70783).</span></span>

<span data-ttu-id="ae500-121">Para obtener más información sobre Multi-Geo, consulte la página de capacidades [multi geo de Microsoft](https://aka.ms/multi-geo).</span><span class="sxs-lookup"><span data-stu-id="ae500-121">For more info about Multi-Geo, refer to the [Microsoft Multi-Geo capabilities page](https://aka.ms/multi-geo).</span></span>
