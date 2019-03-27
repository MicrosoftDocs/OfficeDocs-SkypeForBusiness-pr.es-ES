---
title: Solicitud de certificado (entidad de certificación)
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/26/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployCertRequestCA
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a609f1b0-ae13-44ca-a467-b7fb14ff18a1
description: 'Al solicitar un certificado a una entidad de certificación en línea (o CA; suelen ser servidores ubicados en la red interna) en la página Elija una entidad de certificación, aparecen dos opciones:'
ms.openlocfilehash: 5681f570a6c418263545386afecfe4b7329bc45c
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30880196"
---
# <a name="certificate-request-certificate-authority"></a><span data-ttu-id="1864d-103">Solicitud de certificado (entidad de certificación)</span><span class="sxs-lookup"><span data-stu-id="1864d-103">Certificate Request (Certificate Authority)</span></span>
 
<span data-ttu-id="1864d-104">Al solicitar un certificado a una entidad de certificación en línea (o CA; suelen ser servidores ubicados en la red interna) en la página **Elija una entidad de certificación**, aparecen dos opciones:</span><span class="sxs-lookup"><span data-stu-id="1864d-104">When making a certificate request to an online certification authority (CA) (typically, these are servers that are on your internal network) on the **Choose a Certification Authority (CA)** page, you are presented with two options:</span></span>
  
1. <span data-ttu-id="1864d-105">Seleccionar una entidad de certificación de la lista detectada en el entorno.</span><span class="sxs-lookup"><span data-stu-id="1864d-105">Select a CA from the list detected in your environment.</span></span>
    
2. <span data-ttu-id="1864d-106">Especificar otra entidad de certificación.</span><span class="sxs-lookup"><span data-stu-id="1864d-106">Specify another certification authority.</span></span>
    
<span data-ttu-id="1864d-107">Si selecciona la primera opción, verá una lista desplegable que contiene todas las entidades de certificación basada en Windows Server que se detectaron en su entorno.</span><span class="sxs-lookup"><span data-stu-id="1864d-107">If you select the first option, you'll see a drop-down list that contains all Windows Server-based certification authorities that are detected in your environment.</span></span> <span data-ttu-id="1864d-108">Seleccione la entidad de certificación adecuada para el certificado.</span><span class="sxs-lookup"><span data-stu-id="1864d-108">Select the certification authority that is appropriate for your certificate.</span></span> <span data-ttu-id="1864d-109">Quizá deba consultar al administrador de la entidad de certificación para saber qué entidad se debe elegir.</span><span class="sxs-lookup"><span data-stu-id="1864d-109">You may need to consult with your CA administrator to know which CA to choose.</span></span>
  
<span data-ttu-id="1864d-p102">Si se inclina por la segunda opción, escriba el nombre de dominio completo y la instancia de entidad de certificación que usará para el certificado. Esta opción es la correcta si la entidad de certificación que quiere usar no se basa en servidores Windows; sin embargo, será válida para entidades basadas en servidores Windows.</span><span class="sxs-lookup"><span data-stu-id="1864d-p102">If you select the second option, type in the fully qualified domain name (FQDN) and CA instance for the certification authority that you will use for your certificate. This option is appropriate if the CA that you want to use is not a Windows Server-based CA, but will work for Windows Server-based CAs.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="1864d-112">Asegúrese de confirmar las pertenencias a grupos que necesita para que la solicitud del certificado sea válida.</span><span class="sxs-lookup"><span data-stu-id="1864d-112">Be sure to confirm the group memberships that you need to be successful with the certificate request.</span></span> <span data-ttu-id="1864d-113">Normalmente, las entidades de certificación tienen un requisito de permisos diferentes de los requisitos para instalar Skype para Business Server en servidores.</span><span class="sxs-lookup"><span data-stu-id="1864d-113">Typically, certification authorities have a different permission requirement from the requirements for installing Skype for Business Server on servers.</span></span> <span data-ttu-id="1864d-114">Confirme con el administrador de la entidad de certificación los requisitos para solicitar el certificado.</span><span class="sxs-lookup"><span data-stu-id="1864d-114">Confirm the requirements for requesting the certificate with your CA administrator.</span></span> 
  

