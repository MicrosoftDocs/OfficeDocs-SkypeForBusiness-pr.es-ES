---
title: Incluir el departamento de seguridad en Skype Empresarial Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 4b1d9125-7488-419b-85dd-a8dd3ab5add3
description: Planear cómo incluir el departamento de seguridad de su organización en una implementación de E9-1-1, en Skype para Business Server Enterprise Voice.
ms.openlocfilehash: adaa1096651c5e3f86d15af1b2409a8de03e6c9c
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="include-the-security-desk-in-skype-for-business-server-2015"></a><span data-ttu-id="5f4e8-103">Incluir el departamento de seguridad en Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="5f4e8-103">Include the security desk in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="5f4e8-104">Planear cómo incluir el departamento de seguridad de su organización en una implementación de E9-1-1, en Skype para Business Server Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="5f4e8-104">Planning how to include your organization's security desk in an E9-1-1 deployment, in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="5f4e8-p101">Puede que su compañía requiera que el servicio de seguridad participe en una llamada de emergencia. Para ayudarle a decidir cómo integrar el servicio de seguridad en la implementación de E9-1-1, necesitarás responder a las preguntas que se indican a continuación.</span><span class="sxs-lookup"><span data-stu-id="5f4e8-p101">Your company may require the security desk to become involved in an emergency call. To help decide how to integrate the Security Desk into you E9-1-1 deployment, you should answer the following questions.</span></span>
  
<span data-ttu-id="5f4e8-107">**¿Desea que el departamento de seguridad reciba una notificación cuando haya una llamada de emergencia?**</span><span class="sxs-lookup"><span data-stu-id="5f4e8-107">**Do you want the security desk to be notified when there is an emergency call?**</span></span>
  
<span data-ttu-id="5f4e8-108">Puede configurar la directiva de ubicación para que Skype para Business Server envía avisos por mensajería instantánea (IM) a la Skype para las direcciones SIP de negocio de personal de seguridad de uno o más.</span><span class="sxs-lookup"><span data-stu-id="5f4e8-108">You can configure the location policy so that Skype for Business Server sends instant messaging (IM) alerts to the Skype for Business SIP addresses of one or more security personnel.</span></span> <span data-ttu-id="5f4e8-109">Estas alertas incluyen el nombre, el número y la ubicación de la persona que realiza la llamada de emergencia, y facilita que el personal de seguridad pueda ayudar en la situación de emergencia.</span><span class="sxs-lookup"><span data-stu-id="5f4e8-109">These alerts contain the name, number, and location of the person placing the emergency call, and facilitate security personnel in assisting with the emergency situation.</span></span>
    
<span data-ttu-id="5f4e8-110">**¿Desea que el departamento de seguridad establezca una conferencia en todas las llamadas de emergencia?**</span><span class="sxs-lookup"><span data-stu-id="5f4e8-110">**Do you want to conference the security desk in on each emergency call?**</span></span>
  
<span data-ttu-id="5f4e8-p103">En el caso de que el proveedor de servicios de emergencia lo permita, puedes configurar la directiva de ubicación para incluir un número de devolución de llamada ante cada llamada de emergencia. Este número lo usa después el proveedor para que el personal de seguridad de la organización establezca una conferencia en las llamadas de emergencia. Esta conferencia se puede configurar en la directiva de ubicación para que sea unidireccional (de solo escucha) o bidireccional (de dos vías).</span><span class="sxs-lookup"><span data-stu-id="5f4e8-p103">If supported by the emergency services service provider, you can configure the location policy to include a callback number with each emergency call. This number is then used by the provider to conference your organization's security personnel into emergency calls. This conferencing can be configured in the location policy to be one-way (listen-only) or two-way (bidirectional).</span></span>
    
> [!NOTE]
> <span data-ttu-id="5f4e8-p104">Si lo deseas, puedes configurar miembros del personal de emergencia diferentes para cada directiva de ubicación. Esto te permite personalizar la respuesta para las diferentes áreas de la compañía o crear un comportamiento diferente para las llamadas de emergencia originadas en el interior en contraposición con las realizadas en el exterior de la red. Puedes usar grupos de distribución para especificar el personal al que deseas notificar.</span><span class="sxs-lookup"><span data-stu-id="5f4e8-p104">If desired, you can configure different emergency personnel for each location policy. This allows you to customize the response for different areas within your company, or create different behavior for emergency calls that originate from inside as opposed to outside the network. You can use distribution groups to specify the personnel you want to notify.</span></span> 
  

