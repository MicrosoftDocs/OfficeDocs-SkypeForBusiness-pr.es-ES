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
description: El control remoto de llamadas era una característica en versiones anteriores de Lync Server que permitía a los usuarios controlar sus teléfonos PBX con Lync Server. En Skype Empresarial Server, esta característica se ha reemplazado por Llamar a través del trabajo. En las versiones de cliente para Skype Empresarial Server 2015 y en adelante, el control remoto de llamadas ya no está disponible para configurarse en el cliente y se ha quitado para su uso.
ms.openlocfilehash: c7b4156c90810206824d922af17b83381a64afe17a3a927825eae91445245cfa
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54302374"
---
# <a name="plan-for-remote-call-control-in-skype-for-business"></a>Planear el control remoto de llamadas en Skype Empresarial
 
El control remoto de llamadas era una característica en versiones anteriores de Lync Server que permitía a los usuarios controlar sus teléfonos PBX con Lync Server. En Skype Empresarial Server, esta característica se ha reemplazado por Llamar a través del trabajo.  *En las versiones de cliente para Skype Empresarial Server 2015 y en adelante, el control remoto de llamadas ya no está disponible para configurarse en el cliente y se ha quitado para su uso.* 
  
 Los usuarios de control remoto de llamadas de la organización que se encuentran en servidores front-end que ejecutan Lync Server pueden seguir usando el control remoto de llamadas, incluso si usan un Skype Empresarial cliente. Sin embargo, para los usuarios que se alojan en Skype Empresarial Server, no se admite el control remoto de llamadas. Consulte la siguiente tabla para ver las combinaciones de servidor y cliente y si pueden admitir el control remoto de llamadas o llamar a través del trabajo.
  
||**Skype Empresarial Cliente con Skype ui habilitada**|**Skype Empresarial Cliente con la interfaz de usuario de Lync habilitada**|**Skype Empresarial cliente de 2016**|**Cliente de Lync 2013**|**Cliente de Lync 2010**|
|:-----|:-----|:-----|:-----|:-----|:-----|
| Skype Empresarial Server <br/> |Llamar a través del trabajo  <br/> |1 <br/> |Llamar a través del trabajo  <br/> |1 <br/> |1 <br/> |
| Lync Server 2013 <br/> |Control remoto de llamadas  <br/> |Control remoto de llamadas  <br/> |1 <br/> |Control remoto de llamadas  <br/> |Control remoto de llamadas  <br/> |
| Lync Server 2010 <br/> |Control remoto de llamadas  <br/> |Control remoto de llamadas  <br/> |1 <br/> |Control remoto de llamadas  <br/> |Control remoto de llamadas  <br/> |
   
1. No se admite ninguna característica.
  
Para obtener más información, [consulte Control remoto de llamadas](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-remote-call-control) en la documentación de Lync Server 2013.
  
## <a name="see-also"></a>Consulte también

[Plan for Call Via Work in Skype Empresarial Server](call-via-work.md)
  
[Comparación de características de cliente de escritorio para Skype Empresarial](../../plan-your-deployment/clients-and-devices/desktop-feature-comparison.md)

[Realiza una Skype Empresarial pero usa el teléfono de escritorio PBX para audio](https://support.office.com/article/Make-a-Skype-for-Business-call-but-use-your-PBX-desk-phone-for-audio-6a316c11-a05e-460c-b969-32ff0ad848e6)