---
title: Experiencia de Teams en un entorno multigeómico de Microsoft 365
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
description: En este artículo, aprenderá a usar Teams en un entorno multigeómico de Microsoft 365.
ms.openlocfilehash: 43abe221c6159e6dfed1705f5cbc4839c1ce57db
ms.sourcegitcommit: 93d84e172cb4b19acde4b8bae9b77efe96c44c00
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/05/2021
ms.locfileid: "50122250"
---
# <a name="teams-experience-in-a-microsoft-365-multi-geo-enabled-tenancy"></a><span data-ttu-id="b087a-103">Experiencia de Teams en un entorno multigeómico de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="b087a-103">Teams experience in a Microsoft 365 Multi-Geo-enabled tenancy</span></span>

<span data-ttu-id="b087a-104">Microsoft Teams es un software de chat grupal, el centro para el trabajo en equipo en Microsoft 365 y Office 365.</span><span class="sxs-lookup"><span data-stu-id="b087a-104">Microsoft Teams is group chat software, the hub for teamwork in Microsoft 365 and Office 365.</span></span> <span data-ttu-id="b087a-105">Se usa con tecnología del servicio Microsoft 365 Groups junto con SharePoint Online y OneDrive para la Empresa para mejorar su experiencia con los archivos.</span><span class="sxs-lookup"><span data-stu-id="b087a-105">It's powered by the Microsoft 365 Groups service along with SharePoint Online and OneDrive for Business for its files experience.</span></span> <span data-ttu-id="b087a-106">En un entorno multige geográfico de OneDrive para la Empresa/SharePoint Online, en el que el espacio empresarial se extiende a muchas ubicaciones geográficas como Norteamérica, Europa y Australia, la experiencia de archivos subyacentes es multigeado, por lo que la experiencia de Teams con la colaboración de archivos también es multigeado.</span><span class="sxs-lookup"><span data-stu-id="b087a-106">In a OneDrive for Business/SharePoint Online Multi-Geo tenancy, in which the tenant is extended to many geographic locations such as North America, Europe, and Australia, the underlying files experience is Multi-Geo-aware, so the Teams experience with file collaboration is also Multi-Geo-aware.</span></span> <span data-ttu-id="b087a-107">Esta funcionalidad es una funcionalidad principal de Teams para surface los archivos hospedados en varias ubicaciones geográficas en su experiencia de archivos nativos.</span><span class="sxs-lookup"><span data-stu-id="b087a-107">This functionality is a key leading-edge capability for Teams to surface files that are hosted across multiple Geos in its native files experience.</span></span> <span data-ttu-id="b087a-108">Esto también incluye archivos de OneNote y wiki.</span><span class="sxs-lookup"><span data-stu-id="b087a-108">This also includes OneNote and Wiki files.</span></span>

<span data-ttu-id="b087a-109">Por ejemplo, en un entorno de Contoso con Europa como satélite Geo y Norteamérica como geo central, un usuario satélite europeo verá sus archivos de OneDrive en la pestaña Archivos en el panel izquierdo, aunque los archivos se hospedan en la ubicación de datos de Europa y Estados Unidos es la ubicación central del inquilino. </span><span class="sxs-lookup"><span data-stu-id="b087a-109">For example, in a Contoso tenancy with Europe as a satellite Geo and North America as the central Geo, a European satellite user will see their OneDrive files under the **Files** tab in left pane, although the files are hosted in the Europe data location and the United States is the tenant’s central location.</span></span> <span data-ttu-id="b087a-110">Además, el usuario puede acceder a los archivos usados recientemente en la **hoja vista** Recientes.</span><span class="sxs-lookup"><span data-stu-id="b087a-110">Also, the user can access the most recently used files under the **Recent** view blade.</span></span> <span data-ttu-id="b087a-111">Los archivos recientes pueden incluir archivos compartidos por usuarios de otras ubicaciones geográficas.</span><span class="sxs-lookup"><span data-stu-id="b087a-111">Recent files may include files shared from users in other geo locations.</span></span> 

<span data-ttu-id="b087a-112">Un sitio de SharePoint de un equipo determinado también es multigeómico.</span><span class="sxs-lookup"><span data-stu-id="b087a-112">A given Team’s SharePoint site is also Multi-Geo-aware.</span></span> <span data-ttu-id="b087a-113">Es decir, si un usuario satélite europeo está creando un Equipo, el sitio de SharePoint correspondiente se creará en la ubicación de Europa.</span><span class="sxs-lookup"><span data-stu-id="b087a-113">That is, if a European satellite user is creating a Team, the corresponding SharePoint site will be created in the Europe location.</span></span> <span data-ttu-id="b087a-114">Los archivos asociados a ese Equipo se mantendrán en reposo en esa ubicación.</span><span class="sxs-lookup"><span data-stu-id="b087a-114">The files that are associated with that Team will be kept at rest in that location.</span></span> <span data-ttu-id="b087a-115">Las experiencias subsiguientes, como cargar un nuevo archivo o editar el archivo, se almacenarán en esa ubicación europea, manteniendo la promesa de residencia de datos para esos archivos.</span><span class="sxs-lookup"><span data-stu-id="b087a-115">Any subsequent experiences, such as uploading a new file or editing the file, will be stored in that European location, keeping the promise of data residency for those files.</span></span>

<span data-ttu-id="b087a-116">Como un espacio empresarial multigemico es un único inquilino global, los usuarios de satélites podrán ver a sus compañeros de todo el mundo, independientemente de dónde estén.</span><span class="sxs-lookup"><span data-stu-id="b087a-116">Because a Multi-Geo tenancy is a single global tenant, during @ mentions satellite users will be able to see their colleagues from across the globe, no matter where they are.</span></span>

<span data-ttu-id="b087a-117">Las conversaciones en chats, mensajes de canales y notas de mensajería instantánea de reuniones o chats dentro de la experiencia de Teams no son multiempresa y se mantienen solo dentro de la ubicación central del inquilino.</span><span class="sxs-lookup"><span data-stu-id="b087a-117">Conversations in chats, channels messages, and meeting IM notes/chats within the Teams experience aren't Multi-Geo-aware and are all kept only inside the central location of the tenant.</span></span> <span data-ttu-id="b087a-118">Normalmente, las conversaciones de chat no se aplican a las necesidades de residencia de datos.</span><span class="sxs-lookup"><span data-stu-id="b087a-118">Typically, chat conversations aren’t applied to data residency needs.</span></span> <span data-ttu-id="b087a-119">Para obtener más información, [vea Ubicación de los datos en Microsoft Teams.](location-of-data-in-teams.md)</span><span class="sxs-lookup"><span data-stu-id="b087a-119">For more information, see [Location of data in Microsoft Teams](location-of-data-in-teams.md).</span></span>

<span data-ttu-id="b087a-120">Para obtener más información sobre multige geo, consulte la página de [capacidades multige geo de Microsoft.](https://aka.ms/multi-geo)</span><span class="sxs-lookup"><span data-stu-id="b087a-120">For more info about Multi-Geo, refer to the [Microsoft Multi-Geo capabilities page](https://aka.ms/multi-geo).</span></span>
