---
title: Estacionamiento de llamadas Crear nuevo o Editar existente
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.VoiceFeaCallParkEdit
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: e834d485-d25a-4eec-9090-2b8534ecf65d
ROBOTS: NOINDEX, NOFOLLOW
description: Los intervalos de números de estacionamiento de llamadas definen los números temporales en los que se mantienen las llamadas estacionadas hasta que alguien las recupera o se les hace el tiempo de espera.
ms.openlocfilehash: aa89ddc094f85607afb37c455b0f5a5e05df70de
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49820100"
---
# <a name="call-park-create-new-or-edit-existing"></a><span data-ttu-id="99544-103">Estacionamiento de llamadas: Crear nuevos o editar los existentes</span><span class="sxs-lookup"><span data-stu-id="99544-103">Call Park: Create New or Edit Existing</span></span>

<span data-ttu-id="99544-104">Los intervalos de números de estacionamiento de llamadas definen los números temporales en los que se mantienen las llamadas estacionadas hasta que alguien las recupera o se les hace el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="99544-104">Call Park number ranges define the temporary numbers where parked calls are held until someone retrieves them or they time out.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="99544-105">Referencia de la interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="99544-105">UI Reference</span></span>

<span data-ttu-id="99544-106">En la siguiente lista se describen los campos de la página.</span><span class="sxs-lookup"><span data-stu-id="99544-106">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="99544-107">**Nombre** Escriba un nombre descriptivo que identifique el intervalo de números.</span><span class="sxs-lookup"><span data-stu-id="99544-107">**Name** Type a descriptive name that identifies the number range.</span></span> <span data-ttu-id="99544-108">Una vez que guarde el intervalo numérico, el nombre no se podrá cambiar.</span><span class="sxs-lookup"><span data-stu-id="99544-108">After you save the number range, this name cannot be changed.</span></span>

- <span data-ttu-id="99544-109">**Intervalo de números** En el primer campo, escriba el número inicial del intervalo de números.</span><span class="sxs-lookup"><span data-stu-id="99544-109">**Number range** In the first field, type the beginning number of the number range.</span></span> <span data-ttu-id="99544-110">En el segundo campo, escriba el número de finalización del intervalo numérico.</span><span class="sxs-lookup"><span data-stu-id="99544-110">In the second field, type the ending number of the number range.</span></span>

  - <span data-ttu-id="99544-111">El número inicial del intervalo debe ser menor o igual al número final del intervalo.</span><span class="sxs-lookup"><span data-stu-id="99544-111">The beginning number of the range must be less than or equal to the ending number of the range.</span></span>

  - <span data-ttu-id="99544-112">El valor del número inicial del intervalo debe tener la misma longitud que el número final del intervalo.</span><span class="sxs-lookup"><span data-stu-id="99544-112">The value of the beginning number of the range must be the same length as the ending number of the range.</span></span>

  - <span data-ttu-id="99544-p103">El intervalo numérico debe ser único. Este intervalo no se puede superponer con ningún otro.</span><span class="sxs-lookup"><span data-stu-id="99544-p103">The number range must be unique. This range cannot overlap with any other range.</span></span>

  - <span data-ttu-id="99544-115">Si el intervalo de números comienza con el carácter \* o #, el intervalo debe ser mayor que 100.</span><span class="sxs-lookup"><span data-stu-id="99544-115">If the number range begins with the character \* or #, the range must be greater than 100.</span></span>

  - <span data-ttu-id="99544-116">Valores válidos: deben coincidir con la cadena de expresión regular ([ \\ \*|#]?[ 1-9]\d {0,7} )| ([1-9]\d {0,8} ).</span><span class="sxs-lookup"><span data-stu-id="99544-116">Valid values: Must match the regular expression string ([\\*|#]?[1-9]\d{0,7})|([1-9]\d{0,8}).</span></span> <span data-ttu-id="99544-117">Esto significa que el valor debe ser una cadena que comienza con el carácter o # o un número del 1 al 9 (el primer carácter \* no puede ser cero).</span><span class="sxs-lookup"><span data-stu-id="99544-117">This means the value must be a string beginning with either the character \* or # or a number 1 through 9 (the first character cannot be a zero).</span></span> <span data-ttu-id="99544-118">Si el primer carácter es o #, el siguiente carácter debe ser un número del 1 al \* 9 (no puede ser un cero).</span><span class="sxs-lookup"><span data-stu-id="99544-118">If the first character is \* or #, the following character must be a number 1 through 9 (it cannot be a zero).</span></span> <span data-ttu-id="99544-119">Los caracteres subsiguientes pueden ser cualquier número del 0 al 9 hasta siete caracteres adicionales (por ejemplo, "#6000", " \* 92000", " \* 95551212" y "915551212").</span><span class="sxs-lookup"><span data-stu-id="99544-119">Subsequent characters can be any number 0 through 9 up to seven additional characters (for example, "#6000", "\*92000", "\*95551212", and "915551212").</span></span> <span data-ttu-id="99544-120">Si el primer carácter no es o #, el primer carácter debe ser un número del 1 al 9 (no puede ser cero), seguido de hasta ocho caracteres, cada uno de los números del 0 al \* 9 (por ejemplo: 915551212;41212;300).</span><span class="sxs-lookup"><span data-stu-id="99544-120">If the first character is not \* or #, the first character must be a number 1 through 9 (it cannot be zero), followed by up to eight characters, each a number 0 through 9 (for example: 915551212;41212;300).</span></span>

  - <span data-ttu-id="99544-p105">No debe tener más de 50.000 números por grupo de servidores. Cada intervalo numérico normalmente está formado por 100 números o menos, pero puede ser mucho mayor siempre que tenga menos de 10.000 números. Por ejemplo, en lugar de especificar un número de inicio de "7000000" y un número de finalización de "8000000", piense en especificar un número de inicio de "7000000" y un número de finalización de "7000100".</span><span class="sxs-lookup"><span data-stu-id="99544-p105">You should not have more than a total of 50,000 numbers per pool. Each number range typically encompasses 100 or fewer numbers, but it can be much larger as long as it includes fewer than 10,000 numbers. For example, instead of specifying a starting number of "7000000" and an ending number of "8000000," consider specifying a starting number of "7000000" and an ending number of "7000100."</span></span>

- <span data-ttu-id="99544-124">**FQDN del servidor de destino** Seleccione el nombre de dominio completo (FQDN) o el identificador de servicio del servicio de aplicación que hospeda la aplicación Estacionamiento de llamadas.</span><span class="sxs-lookup"><span data-stu-id="99544-124">**FQDN of destination server** Select the fully qualified domain name (FQDN) or service ID of the Application service that hosts the Call Park application.</span></span> <span data-ttu-id="99544-125">Todas las llamadas estacionadas en números del intervalo especificado por el número de inicio y el número de finalización de cada intervalo numérico se enrutarán a este servidor o grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="99544-125">All calls parked to numbers within the range specified by the start number and end number in the number range will be routed to this server or pool.</span></span>

<span data-ttu-id="99544-126">Para obtener más información sobre las características y capacidades del estacionamiento de llamadas, consulte [Plan for Call Park in Skype for Business](../../../plan-your-deployment/enterprise-voice-solution/call-park.md).</span><span class="sxs-lookup"><span data-stu-id="99544-126">For details about Call Park features and capabilities, see [Plan for Call Park in Skype for Business](../../../plan-your-deployment/enterprise-voice-solution/call-park.md).</span></span> <span data-ttu-id="99544-127">Para obtener más información sobre cómo trabajar con intervalos de números de estacionamiento de llamadas, vea [Configure Phone Number Extensions for Parking Calls](https://technet.microsoft.com/library/fbf97624-9587-42a6-b276-1b69c574a74d.aspx).</span><span class="sxs-lookup"><span data-stu-id="99544-127">For details about working with Call Park number ranges, see [Configure Phone Number Extensions for Parking Calls](https://technet.microsoft.com/library/fbf97624-9587-42a6-b276-1b69c574a74d.aspx).</span></span>


