---
title: Solicitud de certificado (entidad de certificación)
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeployCertRequestCA
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a609f1b0-ae13-44ca-a467-b7fb14ff18a1
description: 'Al realizar una solicitud de certificado a una entidad de certificación (CA) en línea (normalmente, se trata de servidores que se encuentran en la red interna) en la página Elegir una entidad de certificación (CA), se le presentan dos opciones:'
ms.openlocfilehash: 0081ab852a1650dfafd61471891a002be60def3c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49805330"
---
# <a name="certificate-request-certificate-authority"></a><span data-ttu-id="04bb0-103">Solicitud de certificado (entidad de certificación)</span><span class="sxs-lookup"><span data-stu-id="04bb0-103">Certificate Request (Certificate Authority)</span></span>
 
<span data-ttu-id="04bb0-104">Al realizar una solicitud de certificado a una entidad de certificación (CA) en línea (normalmente, se trata de servidores que se encuentran en la red interna) en la página Elegir una entidad de certificación **(CA),** se le presentan dos opciones:</span><span class="sxs-lookup"><span data-stu-id="04bb0-104">When making a certificate request to an online certification authority (CA) (typically, these are servers that are on your internal network) on the **Choose a Certification Authority (CA)** page, you are presented with two options:</span></span>
  
1. <span data-ttu-id="04bb0-105">Seleccionar una entidad de certificación de la lista detectada en el entorno.</span><span class="sxs-lookup"><span data-stu-id="04bb0-105">Select a CA from the list detected in your environment.</span></span>
    
2. <span data-ttu-id="04bb0-106">Especificar otra entidad de certificación.</span><span class="sxs-lookup"><span data-stu-id="04bb0-106">Specify another certification authority.</span></span>
    
<span data-ttu-id="04bb0-107">Si seleccionas la primera opción, verás una lista desplegable que contiene todas las entidades de certificación basadas en Windows Server que se detectan en el entorno.</span><span class="sxs-lookup"><span data-stu-id="04bb0-107">If you select the first option, you'll see a drop-down list that contains all Windows Server-based certification authorities that are detected in your environment.</span></span> <span data-ttu-id="04bb0-108">Seleccione la entidad de certificación adecuada para el certificado.</span><span class="sxs-lookup"><span data-stu-id="04bb0-108">Select the certification authority that is appropriate for your certificate.</span></span> <span data-ttu-id="04bb0-109">Quizá deba consultar al administrador de la entidad de certificación para saber qué entidad se debe elegir.</span><span class="sxs-lookup"><span data-stu-id="04bb0-109">You may need to consult with your CA administrator to know which CA to choose.</span></span>
  
<span data-ttu-id="04bb0-110">Si selecciona la segunda opción, escriba el nombre de dominio completo (FQDN) y la instancia de ca para la entidad de certificación que usará para el certificado.</span><span class="sxs-lookup"><span data-stu-id="04bb0-110">If you select the second option, type in the fully qualified domain name (FQDN) and CA instance for the certification authority that you will use for your certificate.</span></span> <span data-ttu-id="04bb0-111">Esta opción es adecuada si la CA que desea usar no es una CA basada en Windows Server, pero funcionará para CA basadas en Windows Server.</span><span class="sxs-lookup"><span data-stu-id="04bb0-111">This option is appropriate if the CA that you want to use is not a Windows Server-based CA, but will work for Windows Server-based CAs.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="04bb0-112">Asegúrese de confirmar las pertenencias a grupos que necesita para realizar correctamente la solicitud de certificado.</span><span class="sxs-lookup"><span data-stu-id="04bb0-112">Be sure to confirm the group memberships that you need to be successful with the certificate request.</span></span> <span data-ttu-id="04bb0-113">Normalmente, las entidades de certificación tienen un requisito de permiso diferente de los requisitos para instalar Skype Empresarial Server en servidores.</span><span class="sxs-lookup"><span data-stu-id="04bb0-113">Typically, certification authorities have a different permission requirement from the requirements for installing Skype for Business Server on servers.</span></span> <span data-ttu-id="04bb0-114">Confirme con el administrador de la entidad de certificación los requisitos para solicitar el certificado.</span><span class="sxs-lookup"><span data-stu-id="04bb0-114">Confirm the requirements for requesting the certificate with your CA administrator.</span></span> 
  

