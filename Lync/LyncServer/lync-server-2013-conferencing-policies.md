---
title: 'Lync Server 2013: directivas de conferencia'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Conferencing policies
ms:assetid: 8f92eb7c-ee66-4df6-a726-4bff93b122cb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688133(v=OCS.15)
ms:contentKeyID: 49733732
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b60b521c69b821dacfe8bd569a6300b4c21e0287
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842468"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conferencing-policies-in-lync-server-2013"></a><span data-ttu-id="2cb45-102">Directivas de conferencia en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2cb45-102">Conferencing policies in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2cb45-103">_**Última modificación del tema:** 2012-09-18_</span><span class="sxs-lookup"><span data-stu-id="2cb45-103">_**Topic Last Modified:** 2012-09-18_</span></span>

<span data-ttu-id="2cb45-104">La Directiva de conferencia define las características y capacidades que los usuarios tienen disponibles durante una conferencia (también conocido como reunión).</span><span class="sxs-lookup"><span data-stu-id="2cb45-104">Conferencing policy defines the features and capabilities that users have available during a conference (also known as a meeting).</span></span> <span data-ttu-id="2cb45-105">La configuración de directivas de conferencia contiene una amplia variedad de opciones de programación y participación, que van desde si una reunión puede incluir audio y vídeo IP hasta la cantidad máxima de personas que pueden asistir.</span><span class="sxs-lookup"><span data-stu-id="2cb45-105">Conferencing policy settings encompass a wide variety of scheduling and participation options, ranging from whether a meeting can include IP audio and video to the maximum number of people who can attend.</span></span> <span data-ttu-id="2cb45-106">Los administradores pueden usar la Directiva de conferencia para administrar la seguridad, el ancho de banda y los aspectos legales de las reuniones.</span><span class="sxs-lookup"><span data-stu-id="2cb45-106">Administrators can use conferencing policy to manage security, bandwidth, and legal aspects of meetings.</span></span>

<span data-ttu-id="2cb45-107">Puede definir la directiva de conferencias en tres niveles: ámbito global, ámbito de sitio y ámbito de usuario.</span><span class="sxs-lookup"><span data-stu-id="2cb45-107">You can define conferencing policy on three levels: global scope, site scope, and user scope.</span></span> <span data-ttu-id="2cb45-108">La configuración se aplica a un usuario específico del ámbito más limitado al ámbito más extenso.</span><span class="sxs-lookup"><span data-stu-id="2cb45-108">Settings apply to a specific user from the narrowest scope to the widest scope.</span></span> <span data-ttu-id="2cb45-109">Si asigna una directiva de usuario a un usuario, la configuración tendrá prioridad.</span><span class="sxs-lookup"><span data-stu-id="2cb45-109">If you assign a user policy to a user, those settings take precedence.</span></span> <span data-ttu-id="2cb45-110">Si no asigna una directiva de usuario, se aplicará la configuración de sitio.</span><span class="sxs-lookup"><span data-stu-id="2cb45-110">If you do not assign a user policy, site settings apply.</span></span> <span data-ttu-id="2cb45-111">Si no se aplica ni la directiva de usuario ni la de sitio, la directiva global proporcionará la configuración predeterminada.</span><span class="sxs-lookup"><span data-stu-id="2cb45-111">If no user or site policies apply, global policy provides the default settings.</span></span>

<span data-ttu-id="2cb45-112">Existe una directiva global predeterminada, de modo que no puede crear una nueva directiva global.</span><span class="sxs-lookup"><span data-stu-id="2cb45-112">A global policy exists by default, so you cannot create a new global policy.</span></span> <span data-ttu-id="2cb45-113">Tampoco puede eliminar la directiva global existente, pero puede cambiar la directiva global para personalizar la configuración predeterminada.</span><span class="sxs-lookup"><span data-stu-id="2cb45-113">You also cannot delete the existing global policy, but you can change the existing global policy to customize your default settings.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="2cb45-114">En esta sección</span><span class="sxs-lookup"><span data-stu-id="2cb45-114">In This Section</span></span>

  - [<span data-ttu-id="2cb45-115">Ver información de directiva de conferencia en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2cb45-115">View conferencing policy information in Lync Server 2013</span></span>](lync-server-2013-view-conferencing-policy-information.md)

  - [<span data-ttu-id="2cb45-116">Crear o modificar una directiva de conferencia en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2cb45-116">Create or modify a conferencing policy in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-conferencing-policy.md)

  - [<span data-ttu-id="2cb45-117">Eliminar una directiva de conferencia existente en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2cb45-117">Delete an existing conferencing policy in Lync Server 2013</span></span>](lync-server-2013-delete-an-existing-conferencing-policy.md)

  - [<span data-ttu-id="2cb45-118">Referencia de configuración de directiva de conferencia para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2cb45-118">Conferencing policy settings reference for Lync Server 2013</span></span>](lync-server-2013-conferencing-policy-settings-reference.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

