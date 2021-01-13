---
title: Planear el control remoto de llamadas en Skype Empresarial
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
ms.assetid: 688a0328-1aa7-449f-b5f7-98c876112ed2
description: El control remoto de llamadas era una característica de versiones anteriores de Lync Server que permitía a los usuarios controlar sus teléfonos PBX con Lync Server. En Skype Empresarial Server, esta característica se ha reemplazado por Vía trabajo. En las versiones de cliente de Skype Empresarial Server 2015 y en el futuro, el control remoto de llamadas ya no está disponible para configurarse en el cliente y se ha quitado para su uso.
ms.openlocfilehash: b48eeed656f5889d08fe892da7d7a6896f8a11c3
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813520"
---
# <a name="plan-for-remote-call-control-in-skype-for-business"></a>Planear el control remoto de llamadas en Skype Empresarial
 
El control remoto de llamadas era una característica de versiones anteriores de Lync Server que permitía a los usuarios controlar sus teléfonos PBX con Lync Server. En Skype Empresarial Server, esta característica se ha reemplazado por Vía trabajo.  *En las versiones de cliente de Skype Empresarial Server 2015 y en el futuro, el control remoto de llamadas ya no está disponible para configurarse en el cliente y se ha quitado para su uso.* 
  
 Los usuarios de control remoto de llamadas de su organización que se encuentran en servidores front-end que ejecutan Lync Server pueden seguir usando el control remoto de llamadas, incluso si usan un cliente de Skype Empresarial. Sin embargo, para los usuarios que están en Skype Empresarial Server, no se admite el control remoto de llamadas. Consulte la tabla siguiente para ver las combinaciones de servidor/cliente y si pueden admitir el control remoto de llamadas o Vía trabajo.
  
||**Cliente de Skype Empresarial con la interfaz de usuario de Skype habilitada**|**Cliente de Skype Empresarial con la interfaz de usuario de Lync habilitada**|**Cliente de Skype Empresarial 2016**|**Cliente de Lync 2013**|**Cliente de Lync 2010**|
|:-----|:-----|:-----|:-----|:-----|:-----|
| Skype Empresarial Server <br/> |Vía trabajo  <br/> |1  <br/> |Vía trabajo  <br/> |1  <br/> |1  <br/> |
| Lync Server 2013 <br/> |Control remoto de llamadas  <br/> |Control remoto de llamadas  <br/> |1  <br/> |Control remoto de llamadas  <br/> |Control remoto de llamadas  <br/> |
| Lync Server 2010 <br/> |Control remoto de llamadas  <br/> |Control remoto de llamadas  <br/> |1  <br/> |Control remoto de llamadas  <br/> |Control remoto de llamadas  <br/> |
   
1. No se admite ninguna característica.
  
Para obtener más información, [consulte Control remoto de](https://go.microsoft.com/fwlink/p/?LinkId=530208) llamadas en la documentación de Lync Server 2013.
  
## <a name="see-also"></a>Vea también

[Plan for Call Via Work in Skype for Business Server](call-via-work.md)
  
[Comparación de características de cliente de escritorio para Skype Empresarial](../../plan-your-deployment/clients-and-devices/desktop-feature-comparison.md)

[Realizar una llamada de Skype Empresarial pero usar el teléfono de escritorio PBX para audio](https://support.office.com/article/Make-a-Skype-for-Business-call-but-use-your-PBX-desk-phone-for-audio-6a316c11-a05e-460c-b969-32ff0ad848e6)

