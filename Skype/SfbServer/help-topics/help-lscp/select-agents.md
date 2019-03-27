---
title: Seleccionar agentes
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/24/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.RgsSelAgent
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b5cf912b-8273-4c2c-a1e5-f25530b264d0
description: Los agentes son usuarios que se designan para atender las llamadas de grupo de respuesta. Los grupos de respuesta necesitan tener un grupo de agentes asignados que identifique los agentes que pueden recibir llamadas para el grupo de respuesta. Una forma de crear un grupo de agentes es definir un grupo personalizado seleccionando los usuarios aptos. Los usuarios optan están habilitados para Skype para Business Server y Enterprise Voice.
ms.openlocfilehash: 17a58df6e6729d5258e69007db98b480b83d46c4
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30888594"
---
# <a name="select-agents"></a><span data-ttu-id="1de64-106">Seleccionar agentes</span><span class="sxs-lookup"><span data-stu-id="1de64-106">Select Agents</span></span>

<span data-ttu-id="1de64-107">Los agentes son usuarios que se designan para atender las llamadas de grupo de respuesta.</span><span class="sxs-lookup"><span data-stu-id="1de64-107">Agents are users who are designated to answer Response Group calls.</span></span> <span data-ttu-id="1de64-108">Los grupos de respuesta necesitan tener un grupo de agentes asignados que identifique los agentes que pueden recibir llamadas para el grupo de respuesta.</span><span class="sxs-lookup"><span data-stu-id="1de64-108">Response groups must have an assigned agent group that identifies the agents who can receive calls for the response group.</span></span> <span data-ttu-id="1de64-109">Una forma de crear un grupo de agentes es definir un grupo personalizado seleccionando los usuarios aptos.</span><span class="sxs-lookup"><span data-stu-id="1de64-109">One way to create an agent group is to define a custom group by selecting eligible users.</span></span> <span data-ttu-id="1de64-110">Los usuarios optan están habilitados para Skype para Business Server y Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="1de64-110">Eligible users are enabled for Skype for Business Server and Enterprise Voice.</span></span>

<span data-ttu-id="1de64-111">Use el cuadro de diálogo **Seleccionar agentes** para seleccionar los usuarios que se van a agregar a un grupo de agentes.</span><span class="sxs-lookup"><span data-stu-id="1de64-111">You use the **Select Agents** dialog box to select users to be added to an agent group.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="1de64-112">Referencia de interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="1de64-112">UI Reference</span></span>

<span data-ttu-id="1de64-113">En la siguiente lista se describen los controles del cuadro de diálogo **Seleccionar agentes**.</span><span class="sxs-lookup"><span data-stu-id="1de64-113">The following list describes the controls in the **Select Agents** dialog box.</span></span>

- <span data-ttu-id="1de64-114">**Buscar** Busca el SIP dirección o nombre para mostrar para un usuario.</span><span class="sxs-lookup"><span data-stu-id="1de64-114">**Find** Searches for the SIP address or display name for a user.</span></span> <span data-ttu-id="1de64-115">Escriba una parte o la totalidad de la dirección o el nombre.</span><span class="sxs-lookup"><span data-stu-id="1de64-115">Enter all or part of the address or name.</span></span> <span data-ttu-id="1de64-116">Deje el cuadro de búsqueda en blanco para mostrar todos los usuarios que están habilitados para Skype para Business Server y Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="1de64-116">Leave the search box empty to display all users who are enabled for Skype for Business Server and Enterprise Voice.</span></span>

- <span data-ttu-id="1de64-117">**Número máximo de usuarios para mostrar** Cambia el número de resultados devueltos que se muestran.</span><span class="sxs-lookup"><span data-stu-id="1de64-117">**Maximum users to display** Changes the number of returned results that are displayed.</span></span> <span data-ttu-id="1de64-118">Use este contador para limitar la búsqueda si espera muchos resultados.</span><span class="sxs-lookup"><span data-stu-id="1de64-118">Use this counter to limit the search if you expect many results.</span></span>

<span data-ttu-id="1de64-119">En la siguiente lista se describen los campos del cuadro de diálogo **Seleccionar agentes**.</span><span class="sxs-lookup"><span data-stu-id="1de64-119">The following list describes the fields in the **Select Agents** dialog box.</span></span>

- <span data-ttu-id="1de64-120">**Agente** Muestra los nombres de usuario devueltos por la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="1de64-120">**Agent** Displays the user names returned by the search.</span></span>

- <span data-ttu-id="1de64-121">**Dirección SIP** Muestra las direcciones SIP de usuario devueltas por la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="1de64-121">**SIP address** Displays the user SIP addresses returned by the search.</span></span>

- <span data-ttu-id="1de64-122">**Telefonía** Muestra el valor del campo **telefonía** definido para los usuarios.</span><span class="sxs-lookup"><span data-stu-id="1de64-122">**Telephony** Displays the value of the **Telephony** field defined for users.</span></span>

- <span data-ttu-id="1de64-123">**Habilitado** Muestra el valor del campo **habilitado para Lync Server** definido para los usuarios.</span><span class="sxs-lookup"><span data-stu-id="1de64-123">**Enabled** Displays the value of the **Enabled for Lync Server** field defined for users.</span></span>

<span data-ttu-id="1de64-124">Para más información sobre cómo trabajar con grupos de agentes, mire [Managing Agent Groups](https://technet.microsoft.com/library/36084cdc-38f1-4c45-922f-f81c7e86210c.aspx) en la documentación de operaciones.</span><span class="sxs-lookup"><span data-stu-id="1de64-124">For details about working with agent groups, see [Managing Agent Groups](https://technet.microsoft.com/library/36084cdc-38f1-4c45-922f-f81c7e86210c.aspx) in the Operations documentation.</span></span>


