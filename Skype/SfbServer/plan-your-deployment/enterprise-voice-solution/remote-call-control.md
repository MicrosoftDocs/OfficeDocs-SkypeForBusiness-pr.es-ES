---
title: Planeación del control remoto de llamadas en Skype empresarial
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
ms.assetid: 688a0328-1aa7-449f-b5f7-98c876112ed2
description: El control remoto de llamadas era una característica en versiones anteriores de Lync Server que permitía a los usuarios controlar sus teléfonos PBX con Lync Server. En Skype empresarial Server, esta característica se ha reemplazado por Call Via work. En las versiones de cliente de Skype empresarial Server 2015 y en marcha hacia delante, el control remoto de llamadas ya no está disponible para la configuración en el cliente y se ha quitado para su uso.
ms.openlocfilehash: 788939c392b1d86d14590232c19979e664fa0c09
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2020
ms.locfileid: "41982805"
---
# <a name="plan-for-remote-call-control-in-skype-for-business"></a>Planeación del control remoto de llamadas en Skype empresarial
 
El control remoto de llamadas era una característica en versiones anteriores de Lync Server que permitía a los usuarios controlar sus teléfonos PBX con Lync Server. En Skype empresarial Server, esta característica se ha reemplazado por Call Via work.  *En las versiones de cliente de Skype empresarial Server 2015 y en marcha hacia delante, el control remoto de llamadas ya no está disponible para la configuración en el cliente y se ha quitado para su uso.* 
  
 Control remoto de llamadas los usuarios de su organización que estén hospedados en servidores front-end que ejecuten Lync Server pueden seguir usando el control remoto de llamadas, incluso si usan un cliente de Skype empresarial. Sin embargo, para los usuarios hospedados en Skype empresarial Server, no se admite el control remoto de llamadas. Consulte la tabla siguiente para ver las combinaciones de servidor y cliente, y si pueden admitir el control remoto de llamadas o llamar a través del trabajo.
  
||**Cliente de Skype empresarial con interfaz de usuario de Skype habilitada**|**Cliente de Skype empresarial con la interfaz de usuario de Lync habilitada**|**Cliente de Skype empresarial 2016**|**Cliente de Lync 2013**|**Cliente de Lync 2010**|
|:-----|:-----|:-----|:-----|:-----|:-----|
| Skype Empresarial Server <br/> |Llamar a través del trabajo  <br/> |1  <br/> |Llamar a través del trabajo  <br/> |1  <br/> |1  <br/> |
| Lync Server 2013 <br/> |Control remoto de llamadas  <br/> |Control remoto de llamadas  <br/> |1  <br/> |Control remoto de llamadas  <br/> |Control remoto de llamadas  <br/> |
| Lync Server 2010 <br/> |Control remoto de llamadas  <br/> |Control remoto de llamadas  <br/> |1  <br/> |Control remoto de llamadas  <br/> |Control remoto de llamadas  <br/> |
   
1. Ninguna de las características es compatible.
  
Para obtener más información, consulte [control remoto de llamadas](https://go.microsoft.com/fwlink/p/?LinkId=530208) en la documentación de Lync Server 2013.
  
## <a name="see-also"></a>Vea también

[Planificar la llamada mediante el trabajo en Skype empresarial Server](call-via-work.md)
  
[Comparación de características de cliente de escritorio para Skype empresarial](../../plan-your-deployment/clients-and-devices/desktop-feature-comparison.md)

[Realizar una llamada de Skype empresarial, pero usar el teléfono de escritorio PBX para el audio](https://support.office.com/article/Make-a-Skype-for-Business-call-but-use-your-PBX-desk-phone-for-audio-6a316c11-a05e-460c-b969-32ff0ad848e6)

