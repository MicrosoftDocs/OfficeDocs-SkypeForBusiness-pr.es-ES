---
title: Configuración de troncos en Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Como parte de Telefonía IP empresarial implementación, puede configurar un tronco entre un servidor de mediación y uno o más sistemas del mismo nivel para proporcionar conectividad de red telefónica conmutada (RTC) para clientes y dispositivos de Telefonía IP empresarial de su organización.
ms.openlocfilehash: 57b8635d635c0fd0b8c41c95f92af768ff84dfd4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49800120"
---
# <a name="configuring-trunks-in-skype-for-business-server"></a><span data-ttu-id="04d2c-103">Configuración de troncos en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="04d2c-103">Configuring trunks in Skype for Business Server</span></span>

<span data-ttu-id="04d2c-104">Como parte de la implementación de Telefonía IP empresarial, puede configurar un tronco entre un servidor de mediación y uno o varios de los siguientes sistemas del mismo nivel para proporcionar conectividad de red telefónica conmutada (RTC) para los clientes y dispositivos de Telefonía IP empresarial de su organización:</span><span class="sxs-lookup"><span data-stu-id="04d2c-104">As part of Enterprise Voice deployment, you can configure a trunk between a Mediation Server and one or more of the following peers to provide public switched telephone network (PSTN) connectivity for Enterprise Voice clients and devices in your organization:</span></span>

- <span data-ttu-id="04d2c-105">Conexión basada en troncos SIP para un proveedor de servicio s de telefonía</span><span class="sxs-lookup"><span data-stu-id="04d2c-105">SIP trunk connection to an Internet telephony service provider (ITSP)</span></span>
- <span data-ttu-id="04d2c-106">Puerta de enlace RTC</span><span class="sxs-lookup"><span data-stu-id="04d2c-106">PSTN gateway</span></span>
- <span data-ttu-id="04d2c-107">Central de conmutación (PBX)</span><span class="sxs-lookup"><span data-stu-id="04d2c-107">Private branch exchange (PBX)</span></span>

<span data-ttu-id="04d2c-108">Para obtener más información, consulte [Plan for PSTN connectivity in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/pstn-connectivity-0.md).</span><span class="sxs-lookup"><span data-stu-id="04d2c-108">For details, see [Plan for PSTN connectivity in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/pstn-connectivity-0.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="04d2c-109">Antes de iniciar la configuración de troncos, verifique que se ha creado la topología y que el servidor de mediación y su par se han configurado y asociado entre sí.</span><span class="sxs-lookup"><span data-stu-id="04d2c-109">Before you begin trunk configuration, verify that the topology has been created and that the Mediation Server and its peer have been configured and associated with one another.</span></span> <span data-ttu-id="04d2c-110">Para obtener más información, [consulte Definir una puerta de enlace en topology Builder en Skype Empresarial Server.](../../deploy/deploy-enterprise-voice/define-a-gateway.md)</span><span class="sxs-lookup"><span data-stu-id="04d2c-110">For details, see [Define a gateway in Topology Builder in Skype for Business Server](../../deploy/deploy-enterprise-voice/define-a-gateway.md).</span></span>

> [!NOTE]
> <span data-ttu-id="04d2c-111">Como parte de la configuración del tronco, puede habilitar la característica de omisión de medios de Skype Empresarial Server, que permite a los medios omitir el servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="04d2c-111">As a part of trunk configuration, you can enable the Skype for Business Server media bypass feature, which enables media to bypass the Mediation Server.</span></span> <span data-ttu-id="04d2c-112">Los troncos pueden configurarse con el desvío de medios habilitado o deshabilitado, aunque le recomendamos que lo habilite.</span><span class="sxs-lookup"><span data-stu-id="04d2c-112">Trunks can be configured either with or without media bypass enabled, but we strongly recommend that you enable it.</span></span> <span data-ttu-id="04d2c-113">Para obtener más información, consulte [Plan for media bypass in Skype for Business](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md).</span><span class="sxs-lookup"><span data-stu-id="04d2c-113">For details, see [Plan for media bypass in Skype for Business](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md).</span></span>
