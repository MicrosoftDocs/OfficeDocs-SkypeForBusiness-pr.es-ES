---
title: Archivos y carpetas de Teams que se excluyen de la detección de virus
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: ramesa
audience: admin
description: Mejore el rendimiento de los equipos al excluir determinados archivos y carpetas de la exploración antivirus normal.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- Teams_ITAdmin_PracticalGuidance
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9c1519038cb2393687a031e9b2c1ea828f999728
ms.sourcegitcommit: bb88ac0c9489bb47957e5ef1074b5df3126b6fdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/25/2020
ms.locfileid: "42265625"
---
<a name="teams-files-and-folders-to-exclude-from-antivirus-scanning"></a><span data-ttu-id="63a1e-103">Archivos y carpetas de Teams que se excluyen de la detección de virus</span><span class="sxs-lookup"><span data-stu-id="63a1e-103">Teams files and folders to exclude from antivirus scanning</span></span>
=================================

<span data-ttu-id="63a1e-104">Puede mejorar el rendimiento general de la implementación de equipos impidiendo que los programas antivirus examinen determinados archivos y carpetas de Teams.</span><span class="sxs-lookup"><span data-stu-id="63a1e-104">You can improve the overall performance of your Teams deployment by preventing your antivirus programs from scanning certain Teams files and folders.</span></span> <span data-ttu-id="63a1e-105">Esto evitará el desembolso de los recursos del sistema al analizar archivos y carpetas que no es necesario analizar.</span><span class="sxs-lookup"><span data-stu-id="63a1e-105">This will avoid the expenditure of system resources on scanning files and folders that don't need to be scanned.</span></span>

> [!NOTE]
> <span data-ttu-id="63a1e-106">Cuando los usuarios descargan archivos o comparten archivos entre sí, no pasan por las ubicaciones que se muestran en la siguiente sección.</span><span class="sxs-lookup"><span data-stu-id="63a1e-106">When your users download files or share files with each other, those files don't pass through the locations listed in the following section.</span></span> <span data-ttu-id="63a1e-107">Las ubicaciones donde los usuarios carguen, descarguen o compartan archivos seguirán siendo analizados regularmente por el programa antivirus.</span><span class="sxs-lookup"><span data-stu-id="63a1e-107">The locations where your users do upload, download, or share files will still be regularly scanned by your antivirus program.</span></span>

## <a name="files-and-folders-to-add-to-your-antivirus-safe-lists"></a><span data-ttu-id="63a1e-108">Archivos y carpetas para agregar a las listas seguras con el antivirus</span><span class="sxs-lookup"><span data-stu-id="63a1e-108">Files and folders to add to your antivirus safe lists</span></span>

<span data-ttu-id="63a1e-109">Use los procedimientos admitidos por el programa antivirus para agregar los siguientes archivos y carpetas a las listas seguras.</span><span class="sxs-lookup"><span data-stu-id="63a1e-109">Use the procedures supported by your antivirus program to add the following files and folders to your safe lists.</span></span> <span data-ttu-id="63a1e-110">Si lo hace, se ahorrarán recursos del sistema evitando la detección de antivirus de estas ubicaciones.</span><span class="sxs-lookup"><span data-stu-id="63a1e-110">Doing so will conserve system resources by avoiding antivirus scans of these locations.</span></span>

### <a name="programs"></a><span data-ttu-id="63a1e-111">Programas</span><span class="sxs-lookup"><span data-stu-id="63a1e-111">Programs</span></span>

<span data-ttu-id="63a1e-112">Agregue los siguientes programas de Teams a la lista segura de antivirus.</span><span class="sxs-lookup"><span data-stu-id="63a1e-112">Add the following Teams programs to your antivirus safe list.</span></span>

<span data-ttu-id="63a1e-113">**%localappdata%\Microsoft\Teams\current\Teams.exe**</span><span class="sxs-lookup"><span data-stu-id="63a1e-113">**%localappdata%\Microsoft\Teams\current\Teams.exe**</span></span>

<span data-ttu-id="63a1e-114">**%localappdata%\Microsoft\Teams\Update.exe**</span><span class="sxs-lookup"><span data-stu-id="63a1e-114">**%localappdata%\Microsoft\Teams\Update.exe**</span></span>

### <a name="folders"></a><span data-ttu-id="63a1e-115">Las</span><span class="sxs-lookup"><span data-stu-id="63a1e-115">Folders</span></span>

<span data-ttu-id="63a1e-116">Agregue las siguientes carpetas de Teams a la lista segura de antivirus.</span><span class="sxs-lookup"><span data-stu-id="63a1e-116">Add the following Teams folders to your antivirus safe list.</span></span>

|<span data-ttu-id="63a1e-117">Categoría</span><span class="sxs-lookup"><span data-stu-id="63a1e-117">Category</span></span>  |<span data-ttu-id="63a1e-118">Ubicación</span><span class="sxs-lookup"><span data-stu-id="63a1e-118">Location</span></span>  |
|---------|---------|
|<span data-ttu-id="63a1e-119">Archivos de programa</span><span class="sxs-lookup"><span data-stu-id="63a1e-119">Program files</span></span>  |<span data-ttu-id="63a1e-120">%localappdata%\Microsoft\Teams</span><span class="sxs-lookup"><span data-stu-id="63a1e-120">%localappdata%\Microsoft\Teams</span></span>|
|<span data-ttu-id="63a1e-121">Archivos de datos</span><span class="sxs-lookup"><span data-stu-id="63a1e-121">Data files</span></span>     |<span data-ttu-id="63a1e-122">%appdata%\Microsoft\Teams</span><span class="sxs-lookup"><span data-stu-id="63a1e-122">%appdata%\Microsoft\Teams</span></span>\ |
