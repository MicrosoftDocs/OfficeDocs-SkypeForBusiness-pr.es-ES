---
title: Seleccionar agentes
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.RgsSelAgent
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: b5cf912b-8273-4c2c-a1e5-f25530b264d0
ROBOTS: NOINDEX, NOFOLLOW
description: Los agentes son usuarios designados para responder a las llamadas del grupo de respuesta. Los grupos de respuesta deben tener un grupo de agentes asignado que identifique los agentes que pueden recibir llamadas para el grupo de respuesta. Una forma de crear un grupo de agentes es definir un grupo personalizado seleccionando usuarios elegibles. Los usuarios elegibles están habilitados para Skype Empresarial Server y Telefonía IP empresarial.
ms.openlocfilehash: 399ad65a2fe232d217ce4891061aeed8284277b9
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51118789"
---
# <a name="select-agents"></a><span data-ttu-id="d4394-106">Seleccionar agentes</span><span class="sxs-lookup"><span data-stu-id="d4394-106">Select Agents</span></span>

<span data-ttu-id="d4394-107">Los agentes son usuarios designados para responder a las llamadas del grupo de respuesta.</span><span class="sxs-lookup"><span data-stu-id="d4394-107">Agents are users who are designated to answer Response Group calls.</span></span> <span data-ttu-id="d4394-108">Los grupos de respuesta deben tener un grupo de agentes asignado que identifique los agentes que pueden recibir llamadas para el grupo de respuesta.</span><span class="sxs-lookup"><span data-stu-id="d4394-108">Response groups must have an assigned agent group that identifies the agents who can receive calls for the response group.</span></span> <span data-ttu-id="d4394-109">Una forma de crear un grupo de agentes es definir un grupo personalizado seleccionando usuarios elegibles.</span><span class="sxs-lookup"><span data-stu-id="d4394-109">One way to create an agent group is to define a custom group by selecting eligible users.</span></span> <span data-ttu-id="d4394-110">Los usuarios elegibles están habilitados para Skype Empresarial Server y Telefonía IP empresarial.</span><span class="sxs-lookup"><span data-stu-id="d4394-110">Eligible users are enabled for Skype for Business Server and Enterprise Voice.</span></span>

<span data-ttu-id="d4394-111">Use el cuadro **de diálogo Seleccionar agentes** para seleccionar los usuarios que se agregarán a un grupo de agentes.</span><span class="sxs-lookup"><span data-stu-id="d4394-111">You use the **Select Agents** dialog box to select users to be added to an agent group.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="d4394-112">Referencia de la interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="d4394-112">UI Reference</span></span>

<span data-ttu-id="d4394-113">En la siguiente lista se describen los controles del **cuadro de diálogo Seleccionar** agentes.</span><span class="sxs-lookup"><span data-stu-id="d4394-113">The following list describes the controls in the **Select Agents** dialog box.</span></span>

- <span data-ttu-id="d4394-114">**Buscar** Busca la dirección SIP o el nombre para mostrar de un usuario.</span><span class="sxs-lookup"><span data-stu-id="d4394-114">**Find** Searches for the SIP address or display name for a user.</span></span> <span data-ttu-id="d4394-115">Escriba todo o parte de la dirección o el nombre.</span><span class="sxs-lookup"><span data-stu-id="d4394-115">Enter all or part of the address or name.</span></span> <span data-ttu-id="d4394-116">Deje el cuadro de búsqueda vacío para mostrar todos los usuarios habilitados para Skype Empresarial Server y Telefonía IP empresarial.</span><span class="sxs-lookup"><span data-stu-id="d4394-116">Leave the search box empty to display all users who are enabled for Skype for Business Server and Enterprise Voice.</span></span>

- <span data-ttu-id="d4394-117">**Máximo de usuarios para mostrar** Cambia el número de resultados devueltos que se muestran.</span><span class="sxs-lookup"><span data-stu-id="d4394-117">**Maximum users to display** Changes the number of returned results that are displayed.</span></span> <span data-ttu-id="d4394-118">Use este contador para limitar la búsqueda si espera muchos resultados.</span><span class="sxs-lookup"><span data-stu-id="d4394-118">Use this counter to limit the search if you expect many results.</span></span>

<span data-ttu-id="d4394-119">En la lista siguiente se describen los campos del **cuadro de diálogo Seleccionar** agentes.</span><span class="sxs-lookup"><span data-stu-id="d4394-119">The following list describes the fields in the **Select Agents** dialog box.</span></span>

- <span data-ttu-id="d4394-120">**Agente** Muestra los nombres de usuario devueltos por la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="d4394-120">**Agent** Displays the user names returned by the search.</span></span>

- <span data-ttu-id="d4394-121">**Dirección SIP** Muestra las direcciones SIP de usuario devueltas por la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="d4394-121">**SIP address** Displays the user SIP addresses returned by the search.</span></span>

- <span data-ttu-id="d4394-122">**Telefonía** Muestra el valor del **campo Telefonía** definido para los usuarios.</span><span class="sxs-lookup"><span data-stu-id="d4394-122">**Telephony** Displays the value of the **Telephony** field defined for users.</span></span>

- <span data-ttu-id="d4394-123">**Habilitado** Muestra el valor del campo **Habilitado para Lync Server** definido para los usuarios.</span><span class="sxs-lookup"><span data-stu-id="d4394-123">**Enabled** Displays the value of the **Enabled for Lync Server** field defined for users.</span></span>

<span data-ttu-id="d4394-124">Para obtener detalles sobre cómo trabajar con grupos de agentes, vea [Managing Agent Groups](/previous-versions/office/lync-server-2013/lync-server-2013-managing-response-group-agent-groups) en la documentación de operaciones.</span><span class="sxs-lookup"><span data-stu-id="d4394-124">For details about working with agent groups, see [Managing Agent Groups](/previous-versions/office/lync-server-2013/lync-server-2013-managing-response-group-agent-groups) in the Operations documentation.</span></span>