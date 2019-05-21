---
title: Incluir el escritorio de seguridad en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 4b1d9125-7488-419b-85dd-a8dd3ab5add3
description: Planear cómo incluir el escritorio de seguridad de su organización en una implementación E9-1-1, en Skype empresarial Server Enterprise Voice.
ms.openlocfilehash: 7be3533879f36c897d148194345e1496945359b6
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34276457"
---
# <a name="include-the-security-desk-in-skype-for-business-server"></a><span data-ttu-id="9fc68-103">Incluir el escritorio de seguridad en Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="9fc68-103">Include the security desk in Skype for Business Server</span></span>
 
<span data-ttu-id="9fc68-104">Planear cómo incluir el escritorio de seguridad de su organización en una implementación E9-1-1, en Skype empresarial Server Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="9fc68-104">Planning how to include your organization's security desk in an E9-1-1 deployment, in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="9fc68-p101">Puede que su compañía requiera que el servicio de seguridad participe en una llamada de emergencia. Para ayudarle a decidir cómo integrar el servicio de seguridad en la implementación de E9-1-1, necesitarás responder a las preguntas que se indican a continuación.</span><span class="sxs-lookup"><span data-stu-id="9fc68-p101">Your company may require the security desk to become involved in an emergency call. To help decide how to integrate the Security Desk into you E9-1-1 deployment, you should answer the following questions.</span></span>
  
<span data-ttu-id="9fc68-107">**¿Desea que el departamento de seguridad reciba una notificación cuando haya una llamada de emergencia?**</span><span class="sxs-lookup"><span data-stu-id="9fc68-107">**Do you want the security desk to be notified when there is an emergency call?**</span></span>
  
<span data-ttu-id="9fc68-108">Puede configurar la Directiva de ubicación para que Skype empresarial Server envíe alertas de mensajería instantánea (mi) a las direcciones SIP de Skype empresarial de uno o más personal de seguridad.</span><span class="sxs-lookup"><span data-stu-id="9fc68-108">You can configure the location policy so that Skype for Business Server sends instant messaging (IM) alerts to the Skype for Business SIP addresses of one or more security personnel.</span></span> <span data-ttu-id="9fc68-109">Estas alertas incluyen el nombre, el número y la ubicación de la persona que realiza la llamada de emergencia, y facilita que el personal de seguridad pueda ayudar en la situación de emergencia.</span><span class="sxs-lookup"><span data-stu-id="9fc68-109">These alerts contain the name, number, and location of the person placing the emergency call, and facilitate security personnel in assisting with the emergency situation.</span></span>
    
<span data-ttu-id="9fc68-110">**¿Desea que el departamento de seguridad establezca una conferencia en todas las llamadas de emergencia?**</span><span class="sxs-lookup"><span data-stu-id="9fc68-110">**Do you want to conference the security desk in on each emergency call?**</span></span>
  
<span data-ttu-id="9fc68-p103">En el caso de que el proveedor de servicios de emergencia lo permita, puedes configurar la directiva de ubicación para incluir un número de devolución de llamada ante cada llamada de emergencia. Este número lo usa después el proveedor para que el personal de seguridad de la organización establezca una conferencia en las llamadas de emergencia. Esta conferencia se puede configurar en la directiva de ubicación para que sea unidireccional (de solo escucha) o bidireccional (de dos vías).</span><span class="sxs-lookup"><span data-stu-id="9fc68-p103">If supported by the emergency services service provider, you can configure the location policy to include a callback number with each emergency call. This number is then used by the provider to conference your organization's security personnel into emergency calls. This conferencing can be configured in the location policy to be one-way (listen-only) or two-way (bidirectional).</span></span>
    
> [!NOTE]
> <span data-ttu-id="9fc68-p104">Si lo deseas, puedes configurar miembros del personal de emergencia diferentes para cada directiva de ubicación. Esto te permite personalizar la respuesta para las diferentes áreas de la compañía o crear un comportamiento diferente para las llamadas de emergencia originadas en el interior en contraposición con las realizadas en el exterior de la red. Puedes usar grupos de distribución para especificar el personal al que deseas notificar.</span><span class="sxs-lookup"><span data-stu-id="9fc68-p104">If desired, you can configure different emergency personnel for each location policy. This allows you to customize the response for different areas within your company, or create different behavior for emergency calls that originate from inside as opposed to outside the network. You can use distribution groups to specify the personnel you want to notify.</span></span> 
  

