---
title: Cumplimiento de las comunicaciones de Microsoft Teams
author: robmazz
ms.author: robmazz
manager: laurawi
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: anwara
description: Aprender sobre el cumplimiento de las comunicaciones, parte de la solución de riesgos de Insider, desde la perspectiva de Microsoft Teams (esta es parte de la funcionalidad de cumplimiento de comunicaciones de M365).
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 01d9906044fe0ea8472cd8bb2ba8ccf247cdbeb9
ms.sourcegitcommit: 113e3a7314505cf78da57917ff62642125fb11fd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/14/2020
ms.locfileid: "45121700"
---
# <a name="communication-compliance-for-microsoft-teams"></a><span data-ttu-id="7d783-103">Cumplimiento de las comunicaciones de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="7d783-103">Communication compliance for Microsoft Teams</span></span>

<span data-ttu-id="7d783-104">El cumplimiento de la comunicación forma parte de la nueva solución de riesgo de Insider de Microsoft 365 que ayuda a minimizar los riesgos de comunicación ayudándole a detectar, capturar y tomar medidas de corrección para los mensajes inapropiados de su organización.</span><span class="sxs-lookup"><span data-stu-id="7d783-104">Communication compliance is part of the new insider risk solution set in Microsoft 365 that helps minimize communication risks by helping you detect, capture, and take remediation actions for inappropriate messages in your organization.</span></span> <span data-ttu-id="7d783-105">Ayuda a identificar el lenguaje ofensivo y el Antiacoso de los canales del equipo o 1:1 y los chats grupales.</span><span class="sxs-lookup"><span data-stu-id="7d783-105">It helps in identifying Offensive language and anti-harassment in Team Channels or 1:1 and Group chats.</span></span> <span data-ttu-id="7d783-106">También puede configurar directivas para ver si hay información confidencial compartida como parte de los canales del equipo o 1:1 y chats grupales.</span><span class="sxs-lookup"><span data-stu-id="7d783-106">You can also set policies to see if any Sensitive information is being shared as part of Team channels or 1:1 and Group chats.</span></span> <span data-ttu-id="7d783-107">Para obtener más información sobre los distintos tipos de directivas y sobre cómo configurar, consulte el [artículo M365](https://docs.microsoft.com/microsoft-365/compliance/communication-compliance).</span><span class="sxs-lookup"><span data-stu-id="7d783-107">For more information on different types of policies and how to set up refer to the [M365 article](https://docs.microsoft.com/microsoft-365/compliance/communication-compliance).</span></span>

## <a name="how-to-use-communication-compliance-in-teams"></a><span data-ttu-id="7d783-108">Cómo usar el cumplimiento de las comunicaciones en Teams</span><span class="sxs-lookup"><span data-stu-id="7d783-108">How to use communication compliance in Teams</span></span>

### <a name="identify-inappropriate-messages"></a><span data-ttu-id="7d783-109">Identificar mensajes inapropiados</span><span class="sxs-lookup"><span data-stu-id="7d783-109">Identify inappropriate messages</span></span>

<span data-ttu-id="7d783-110">Si desea identificar los mensajes que se envían en Microsoft Teams (1:1, chats grupales o conversaciones de canales) contienen lenguaje ofensivo o Antiacoso, puede habilitar las directivas para identificar esta opción y el revisor puede consultar los mensajes y llevar a cabo los pasos necesarios, como enviar material de formación o escalar a las autoridades adecuadas.</span><span class="sxs-lookup"><span data-stu-id="7d783-110">If you want to identify any messages that are sent in Microsoft Teams (1:1, Group Chats or Channel conversations) contain Offensive Language or anti-harassment, you can enable policies to identify this and the reviewer can look into the messages and take necessary steps like sending training material or escalate to the right authorities.</span></span>

### <a name="identify-sensitive-or-regulatory-information"></a><span data-ttu-id="7d783-111">Identificar información confidencial o normativa</span><span class="sxs-lookup"><span data-stu-id="7d783-111">Identify sensitive or Regulatory information</span></span>

<span data-ttu-id="7d783-112">Si desea analizar los mensajes enviados en Microsoft Teams (1:1, chats grupales o conversaciones de canal) para obtener información confidencial o tipos normativos, puede elegir directivas que admitan tipos predefinidos para la normativa o sensible.</span><span class="sxs-lookup"><span data-stu-id="7d783-112">If you want to scan messages sent in Microsoft Teams (1:1, Group Chats or Channel conversations) for sensitive information or regulatory types, you can choose policies that support predefined sensitive or regulatory types.</span></span>

> [!NOTE]
> <span data-ttu-id="7d783-113">Los canales privados no son compatibles con el cumplimiento de la comunicación.</span><span class="sxs-lookup"><span data-stu-id="7d783-113">Private channels are not supported by communication compliance.</span></span>

### <a name="custom-policy"></a><span data-ttu-id="7d783-114">Directiva personalizada</span><span class="sxs-lookup"><span data-stu-id="7d783-114">Custom Policy</span></span>

<span data-ttu-id="7d783-115">Use esta plantilla para configurar canales de comunicación específicos, condiciones de detección individuales y la cantidad de contenido que se debe supervisar y revisar en la organización.</span><span class="sxs-lookup"><span data-stu-id="7d783-115">Use this template to configure specific communication channels, individual detection conditions, and the amount of content to monitor and review in your organization.</span></span>

### <a name="custom-trainable-classifier"></a><span data-ttu-id="7d783-116">Clasificador personalizado personalizado</span><span class="sxs-lookup"><span data-stu-id="7d783-116">Custom Trainable classifier</span></span>

<span data-ttu-id="7d783-117">Use clasificadores capacitables cuando uno de los clasificadores del cuadro no se ajuste a sus necesidades.</span><span class="sxs-lookup"><span data-stu-id="7d783-117">Use trainable classifiers when one of the out of the box classifiers won't meet your needs.</span></span> <span data-ttu-id="7d783-118">Un clasificador de Microsoft 365 es una herramienta que se puede utilizar para reconocer diversos tipos de contenido, proporcionándoles ejemplos para verlos.</span><span class="sxs-lookup"><span data-stu-id="7d783-118">A Microsoft 365 classifier is a tool you can train to recognize various types of content by giving it samples to look at.</span></span> <span data-ttu-id="7d783-119">La formación del clasificador implica que, en primer lugar, las muestras de los seres humanos se seleccionan y cumplen positivamente la categoría.</span><span class="sxs-lookup"><span data-stu-id="7d783-119">Training the classifier involves first giving it samples that are human picked and positively match the category.</span></span> <span data-ttu-id="7d783-120">Después, después de que haya procesado esos ejemplos, pruebe las predicciones asignándole una combinación de muestras positivas y negativas.</span><span class="sxs-lookup"><span data-stu-id="7d783-120">Then, after it has processed those samples, you test the predictions by giving it a mix of positive and negative samples.</span></span> <span data-ttu-id="7d783-121">Para obtener más información sobre este tema, consulta el [artículo M365](https://docs.microsoft.com/microsoft-365/compliance/classifier-creating-a-trainable-classifier) para obtener más información sobre este tema.</span><span class="sxs-lookup"><span data-stu-id="7d783-121">To Lean more about this refer to the [M365 article](https://docs.microsoft.com/microsoft-365/compliance/classifier-creating-a-trainable-classifier) for more on this topic.</span></span>

> [!NOTE]
> <span data-ttu-id="7d783-122">El cumplimiento de la comunicación ahora es compatible con las implementaciones híbridas de Exchange.</span><span class="sxs-lookup"><span data-stu-id="7d783-122">Communication compliance now supports Exchange hybrid deployments.</span></span>

<span data-ttu-id="7d783-123">El cumplimiento de la comunicación admite el historial de conversaciones para todos los mensajes que coincidan con las directivas.</span><span class="sxs-lookup"><span data-stu-id="7d783-123">Communication compliance supports conversation history for any messages that match the polices.</span></span> <span data-ttu-id="7d783-124">Esto proporciona contexto al administrador instructora.</span><span class="sxs-lookup"><span data-stu-id="7d783-124">This provides context to the investigating admin.</span></span>

:::image type="content" source="media/communication-compliance-1.png" alt-text="Una pantalla para el cumplimiento de la comunicación en Microsoft Teams.":::

## <a name="where-communication-policies-can-be-applied-in-teams"></a><span data-ttu-id="7d783-126">Dónde se pueden aplicar las directivas de comunicación en Teams</span><span class="sxs-lookup"><span data-stu-id="7d783-126">Where communication policies can be applied in Teams</span></span>

<span data-ttu-id="7d783-127">Las directivas de cumplimiento de comunicaciones se pueden configurar para los mensajes enviados en Teams en los siguientes niveles:</span><span class="sxs-lookup"><span data-stu-id="7d783-127">Communication compliance policies can be setup for messages sent in Teams at the following levels:</span></span>

- <span data-ttu-id="7d783-128">Nivel de usuario: un administrador puede configurar directivas a un nivel de usuario individual o aplicarlas a todos los usuarios del espacio empresarial.</span><span class="sxs-lookup"><span data-stu-id="7d783-128">User level : An admin can set up policies at an individual user level or apply it to all the users on the tenant.</span></span> <span data-ttu-id="7d783-129">Esto solo cubrirá los mensajes que un usuario envió en 1:1 o conversaciones grupales.</span><span class="sxs-lookup"><span data-stu-id="7d783-129">This will only covers messages that a user sent in 1:1 or Group chats.</span></span>
- <span data-ttu-id="7d783-130">Nivel de equipo: un administrador también puede configurar directivas en un equipo.</span><span class="sxs-lookup"><span data-stu-id="7d783-130">Team Level: An admin can also set up policies on a team.</span></span> <span data-ttu-id="7d783-131">Esto cubre todos los mensajes enviados en el canal de ese equipo (no se admiten mensajes de canal privado).</span><span class="sxs-lookup"><span data-stu-id="7d783-131">This covers all the messages sent in the channel in that team (Private channel messages are not supported).</span></span>
