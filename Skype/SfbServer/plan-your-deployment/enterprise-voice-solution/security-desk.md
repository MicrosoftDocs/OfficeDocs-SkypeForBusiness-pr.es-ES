---
title: Incluir el servicio de seguridad en Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 4b1d9125-7488-419b-85dd-a8dd3ab5add3
description: Planear cómo incluir el servicio de seguridad de su organización en una implementación de E9-1-1, en Skype Empresarial Server Telefonía IP empresarial.
ms.openlocfilehash: 756af940eb327bc4744454e9ed9ef7a7fbfd517d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813410"
---
# <a name="include-the-security-desk-in-skype-for-business-server"></a><span data-ttu-id="3b8d0-103">Incluir el servicio de seguridad en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="3b8d0-103">Include the security desk in Skype for Business Server</span></span>
 
<span data-ttu-id="3b8d0-104">Planear cómo incluir el servicio de seguridad de su organización en una implementación de E9-1-1, en Skype Empresarial Server Telefonía IP empresarial.</span><span class="sxs-lookup"><span data-stu-id="3b8d0-104">Planning how to include your organization's security desk in an E9-1-1 deployment, in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="3b8d0-p101">Puede que su compañía requiera que el departamento de seguridad participe en una llamada de emergencia. Para ayudarle a decidir cómo integrar el departamento de seguridad en la implementación de E9-1-1, deberá responder a las preguntas que se indican a continuación.</span><span class="sxs-lookup"><span data-stu-id="3b8d0-p101">Your company may require the security desk to become involved in an emergency call. To help decide how to integrate the Security Desk into you E9-1-1 deployment, you should answer the following questions.</span></span>
  
<span data-ttu-id="3b8d0-107">**¿Desea que el departamento de seguridad reciba una notificación cuando haya una llamada de emergencia?**</span><span class="sxs-lookup"><span data-stu-id="3b8d0-107">**Do you want the security desk to be notified when there is an emergency call?**</span></span>
  
<span data-ttu-id="3b8d0-108">Puede configurar la directiva de ubicación para que Skype Empresarial Server envíe alertas de mensajería instantánea (MI) a las direcciones SIP de Skype Empresarial de uno o más miembros del personal de seguridad.</span><span class="sxs-lookup"><span data-stu-id="3b8d0-108">You can configure the location policy so that Skype for Business Server sends instant messaging (IM) alerts to the Skype for Business SIP addresses of one or more security personnel.</span></span> <span data-ttu-id="3b8d0-109">Entonces el departamento de seguridad puede confirmar que hay una emergencia.</span><span class="sxs-lookup"><span data-stu-id="3b8d0-109">These alerts contain the name, number, and location of the person placing the emergency call, and facilitate security personnel in assisting with the emergency situation.</span></span>
    
<span data-ttu-id="3b8d0-110">**¿Desea que el departamento de seguridad establezca una conferencia en todas las llamadas de emergencia?**</span><span class="sxs-lookup"><span data-stu-id="3b8d0-110">**Do you want to conference the security desk in on each emergency call?**</span></span>
  
<span data-ttu-id="3b8d0-p103">En el caso de que el proveedor de servicios de emergencia lo permita, puede configurar la directiva de ubicación para incluir un número de devolución de llamada ante cada llamada de emergencia. Este número lo usa después el proveedor para que el personal de seguridad establezca una conferencia en cada llamada de emergencia.</span><span class="sxs-lookup"><span data-stu-id="3b8d0-p103">If supported by the emergency services service provider, you can configure the location policy to include a callback number with each emergency call. This number is then used by the provider to conference your organization's security personnel into emergency calls. This conferencing can be configured in the location policy to be one-way (listen-only) or two-way (bidirectional).</span></span>
    
> [!NOTE]
> <span data-ttu-id="3b8d0-p104">En caso necesario, puede configurar personal de emergencia diferente para cada directiva de ubicación. Esto permite personalizar la respuesta para las diferentes áreas de su empresa o crear un comportamiento diferente para llamadas de emergencia originadas en el interior en contraposición con las realizadas en el exterior de la red. Puede usar grupos de distribución para especificar el personal al que desea notificar.</span><span class="sxs-lookup"><span data-stu-id="3b8d0-p104">If desired, you can configure different emergency personnel for each location policy. This allows you to customize the response for different areas within your company, or create different behavior for emergency calls that originate from inside as opposed to outside the network. You can use distribution groups to specify the personnel you want to notify.</span></span> 
  

