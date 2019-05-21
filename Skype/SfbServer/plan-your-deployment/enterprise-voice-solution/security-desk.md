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
# <a name="include-the-security-desk-in-skype-for-business-server"></a>Incluir el escritorio de seguridad en Skype empresarial Server
 
Planear cómo incluir el escritorio de seguridad de su organización en una implementación E9-1-1, en Skype empresarial Server Enterprise Voice.
  
Puede que su compañía requiera que el servicio de seguridad participe en una llamada de emergencia. Para ayudarle a decidir cómo integrar el servicio de seguridad en la implementación de E9-1-1, necesitarás responder a las preguntas que se indican a continuación.
  
**¿Desea que el departamento de seguridad reciba una notificación cuando haya una llamada de emergencia?**
  
Puede configurar la Directiva de ubicación para que Skype empresarial Server envíe alertas de mensajería instantánea (mi) a las direcciones SIP de Skype empresarial de uno o más personal de seguridad. Estas alertas incluyen el nombre, el número y la ubicación de la persona que realiza la llamada de emergencia, y facilita que el personal de seguridad pueda ayudar en la situación de emergencia.
    
**¿Desea que el departamento de seguridad establezca una conferencia en todas las llamadas de emergencia?**
  
En el caso de que el proveedor de servicios de emergencia lo permita, puedes configurar la directiva de ubicación para incluir un número de devolución de llamada ante cada llamada de emergencia. Este número lo usa después el proveedor para que el personal de seguridad de la organización establezca una conferencia en las llamadas de emergencia. Esta conferencia se puede configurar en la directiva de ubicación para que sea unidireccional (de solo escucha) o bidireccional (de dos vías).
    
> [!NOTE]
> Si lo deseas, puedes configurar miembros del personal de emergencia diferentes para cada directiva de ubicación. Esto te permite personalizar la respuesta para las diferentes áreas de la compañía o crear un comportamiento diferente para las llamadas de emergencia originadas en el interior en contraposición con las realizadas en el exterior de la red. Puedes usar grupos de distribución para especificar el personal al que deseas notificar. 
  

