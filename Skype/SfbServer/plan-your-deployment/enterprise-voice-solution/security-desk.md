---
title: Incluye el escritorio de seguridad en Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 4b1d9125-7488-419b-85dd-a8dd3ab5add3
description: Planear cómo incluir el escritorio de seguridad de su organización en una implementación de E9-1-1, en Skype Empresarial Server Telefonía IP empresarial.
ms.openlocfilehash: c99bdcbfaaaa74a5050c833dca3fd9a046ca41e5
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/26/2021
ms.locfileid: "58615606"
---
# <a name="include-the-security-desk-in-skype-for-business-server"></a>Incluye el escritorio de seguridad en Skype Empresarial Server
 
Planear cómo incluir el escritorio de seguridad de su organización en una implementación de E9-1-1, en Skype Empresarial Server Telefonía IP empresarial.
  
Puede que su compañía requiera que el departamento de seguridad participe en una llamada de emergencia. Para ayudarle a decidir cómo integrar el departamento de seguridad en la implementación de E9-1-1, deberá responder a las preguntas que se indican a continuación.
  
**¿Desea que el departamento de seguridad reciba una notificación cuando haya una llamada de emergencia?**
  
Puede configurar la directiva de ubicación para que Skype Empresarial Server las alertas de mensajería instantánea (MI) a las Skype Empresarial SIP de uno o más miembros del personal de seguridad. Entonces el departamento de seguridad puede confirmar que hay una emergencia.
    
**¿Desea que el departamento de seguridad establezca una conferencia en todas las llamadas de emergencia?**
  
En el caso de que el proveedor de servicios de emergencia lo permita, puede configurar la directiva de ubicación para incluir un número de devolución de llamada ante cada llamada de emergencia. Este número lo usa después el proveedor para que el personal de seguridad establezca una conferencia en cada llamada de emergencia.
    
> [!NOTE]
> En caso necesario, puede configurar personal de emergencia diferente para cada directiva de ubicación. Esto permite personalizar la respuesta para las diferentes áreas de su empresa o crear un comportamiento diferente para llamadas de emergencia originadas en el interior en contraposición con las realizadas en el exterior de la red. Puede usar grupos de distribución para especificar el personal al que desea notificar. 
  

