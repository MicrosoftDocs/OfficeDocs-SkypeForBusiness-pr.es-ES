---
title: Experiencia de Teams en un inquilino multigeo de Microsoft 365 u Office 365 OneDrive y SharePoint Online
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: snigdhav
audience: admin
description: En este artículo, obtendrá información sobre cómo usar Teams en un inquilino multigeografía de Microsoft 365 u Office 365 y SharePoint Online.
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
ms.openlocfilehash: de73dc3edff66bfe8b427e570bfc661e1dec46b4
ms.sourcegitcommit: 1807ea5509f8efa6abba8462bce2f3646117e8bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/10/2020
ms.locfileid: "44689686"
---
<a name="teams-experience-in-a-microsoft-365-or-office-365-onedrive-and-sharepoint-online-multi-geo-enabled-tenancy"></a><span data-ttu-id="65e40-103">Experiencia de Teams en un inquilino multigeo de Microsoft 365 u Office 365 OneDrive y SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="65e40-103">Teams experience in a Microsoft 365 or Office 365 OneDrive and SharePoint Online Multi-Geo-enabled tenancy</span></span>
===========================================

<span data-ttu-id="65e40-104">Microsoft Teams es un software de chats grupales, el hub para el trabajo en equipo de Microsoft 365 y Office 365.</span><span class="sxs-lookup"><span data-stu-id="65e40-104">Microsoft Teams is group chat software, the hub for teamwork in Microsoft 365 and Office 365.</span></span> <span data-ttu-id="65e40-105">Está alimentado por el servicio de grupos de Microsoft 365, junto con SharePoint Online y OneDrive para la empresa para la experiencia de los archivos.</span><span class="sxs-lookup"><span data-stu-id="65e40-105">It is powered by the Microsoft 365 Groups service along with SharePoint Online and OneDrive for Business for its files experience.</span></span> <span data-ttu-id="65e40-106">En un inquilino multifunción de OneDrive para la empresa o SharePoint Online, en el que el inquilino se extiende a muchas ubicaciones geográficas, como Norteamérica, Europa y Australia, la experiencia de archivos subyacentes es la de multigeo, por lo que la experiencia de los equipos con la colaboración de archivos también está preparada para varios países.</span><span class="sxs-lookup"><span data-stu-id="65e40-106">In a OneDrive for Business/SharePoint Online Multi-Geo tenancy, in which the tenant is extended to many geographic locations such as North America, Europe, and Australia, the underlying files experience is Multi-Geo aware, so the Teams experience with file collaboration is also Multi-Geo aware.</span></span> <span data-ttu-id="65e40-107">Esta es una función líder de vanguardia para que los equipos se encaran de archivos alojados en varios GEOS en la experiencia de los archivos nativos.</span><span class="sxs-lookup"><span data-stu-id="65e40-107">This is a key leading-edge capability for Teams to surface files hosted across multiple Geos in its native files experience.</span></span>

<span data-ttu-id="65e40-108">Por ejemplo, en una empresa de Contoso con Europa como una geo de satélite y Norteamérica como la geo central, un usuario de satélite europeo verá sus archivos de OneDrive en la pestaña archivos en el panel izquierdo, aunque los archivos se hospeden en la ubicación de datos de Europa y los Estados Unidos sean la ubicación central del inquilino.</span><span class="sxs-lookup"><span data-stu-id="65e40-108">For example, in a Contoso tenancy with Europe as a satellite Geo and North America as the central Geo, a European satellite user will see his or her OneDrive files under the Files tab in left pane, although the files are hosted in the Europe data location and the United States is the tenant’s central location.</span></span> <span data-ttu-id="65e40-109">Además, el usuario puede acceder a los archivos usados recientemente en el blade de la vista recientes.</span><span class="sxs-lookup"><span data-stu-id="65e40-109">Also, the user can access the most recently used files under the Recent view blade.</span></span> <span data-ttu-id="65e40-110">Los archivos recientes pueden incluir archivos compartidos con el usuario de los usuarios en otros GEOS y podrían ser maestros en otras ubicaciones geográficas a las que se extiende el inquilino.</span><span class="sxs-lookup"><span data-stu-id="65e40-110">Recent files may include files shared with the user from users in other Geos and might be mastered in other Geo locations that the tenant is extended to.</span></span> 

<span data-ttu-id="65e40-111">Un sitio de grupo de un equipo determinado también es compatible con multigeografía.</span><span class="sxs-lookup"><span data-stu-id="65e40-111">A given Team’s group site is also Multi-Geo aware.</span></span> <span data-ttu-id="65e40-112">Es decir, si un usuario satélite europeo está creando un equipo, el sitio de grupos correspondiente se creará en la ubicación de Europa y los archivos asociados a ese grupo de equipo se mantendrán en la ubicación.</span><span class="sxs-lookup"><span data-stu-id="65e40-112">That is, if a European satellite user is creating a Team, the corresponding Groups site will be created in the Europe location and the files associated with that Team group will be kept at rest in that location.</span></span> <span data-ttu-id="65e40-113">Cualquier experiencia posterior, como cargar un archivo nuevo o editar el archivo, se dirigirá a esa ubicación Europea, manteniendo la promesa de residencia de datos para esos archivos.</span><span class="sxs-lookup"><span data-stu-id="65e40-113">Any subsequent experiences, such as uploading a new file or editing the file, will be targeted to that European location, keeping the promise of data residency for those files.</span></span> <span data-ttu-id="65e40-114">Esto es posible gracias a la base subyacente Microsoft 365 grupos que se están reconocendo con multigeografía.</span><span class="sxs-lookup"><span data-stu-id="65e40-114">This is all made possible by the underlying foundation Microsoft 365 Groups becoming Multi-Geo aware.</span></span>

<span data-ttu-id="65e40-115">Debido a que un inquilino multilingüe es un único inquilino global, durante las @ menciones, los usuarios satélite podrán ver a sus colegas de todo el mundo, sin importar dónde residan.</span><span class="sxs-lookup"><span data-stu-id="65e40-115">Because a Multi-Geo tenancy is a single global tenant, during @ mentions satellite users will be able to see their colleagues from across the globe, no matter where they reside.</span></span> 

<span data-ttu-id="65e40-116">Tenga en cuenta que las conversaciones en conversaciones y notas de mensajería instantánea de reuniones dentro de la experiencia de Teams no son muy importantes y se guardan solo dentro de la ubicación central del inquilino.</span><span class="sxs-lookup"><span data-stu-id="65e40-116">Note that conversations in chats and meeting IM notes within the Teams experience are not Multi-Geo aware and are all kept only inside the central location of the tenant.</span></span> <span data-ttu-id="65e40-117">Por lo general, las conversaciones de chat no se aplican a las necesidades de residencia de datos.</span><span class="sxs-lookup"><span data-stu-id="65e40-117">Typically, chat conversations aren’t applied to data residency needs.</span></span>

<span data-ttu-id="65e40-118">Para obtener más información sobre multi-Geo, consulte la [Página de funciones multigeo de Microsoft](https://aka.ms/multi-geo).</span><span class="sxs-lookup"><span data-stu-id="65e40-118">For more information about Multi-Geo, refer to the [Microsoft Multi-Geo capabilities page](https://aka.ms/multi-geo).</span></span>