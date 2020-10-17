---
title: 'Lync Server 2013: asignar una directiva de correo de voz hospedado por usuario'
description: 'Lync Server 2013: asignar una directiva de correo de voz hospedado por usuario.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign a per-user hosted voice mail policy
ms:assetid: d44c71a0-4407-4ab4-b7e0-d671dde3425f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398919(v=OCS.15)
ms:contentKeyID: 48185456
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 071d504c452b4d3adb1b636cb5c4ff8835200107
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48559896"
---
# <a name="assign-a-per-user-hosted-voice-mail-policy-in-lync-server-2013"></a>Asignar una directiva de correo de voz hospedado por usuario en Lync Server 2013

 


Implementar una o varias directivas de correo de voz que hospeda el usuario es opcional. Si no implementa las directivas por usuario, es preciso que las asigne explícitamente a objetos de usuario, grupo o contacto.

Para obtener más información sobre cómo asignar o quitar la asignación de directivas de correo de voz hospedado por usuario, consulte la documentación del shell de administración de Lync Server para los siguientes cmdlets:

  - Grant-CsHostedVoicemailPolicy

  - Remove-CsHostedVoicemailPolicy

## <a name="to-assign-a-per-user-hosted-voice-mail-policy"></a>Para asignar una directiva de correo de voz que hospeda el usuario:

1.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.

2.  Ejecute el cmdlet Grant-CsHostedVoicemailPolicy para asignar la directiva de correo de voz que hospeda el usuario a objetos contacto, usuarios individuales y grupos. Por ejemplo, ejecute lo siguiente:
    
        Grant-CsHostedVoicemailPolicy -Identity "Ken Myer" -PolicyName ExRedmond
    
    En este ejemplo hemos asignado la directiva de correo de voz hospedado ExRedmond al usuario Antonio Bermejo.
    
    **Identity** especifica la cuenta de usuario que se debe modificar. El valor de Identity puede especificarse con cualquiera de los formatos siguientes:
    
      - La dirección SIP del usuario
    
      - El nombre principal de usuario de Active Directory del usuario
    
      - El nombre de inicio de sesión del dominio del usuario \\ (por ejemplo, contoso \\ kenmyer)
    
      - El nombre para mostrar de Servicios de dominio de Active Directory (por ejemplo, Ken Myer). Si usa el Display-Name como valor de identidad, puede usar el \* carácter comodín asterisco (). Por ejemplo, la identidad " \* Smith" devuelve todos los usuarios que tienen una Display-Name que termina con el valor de cadena "Smith".
    

    > [!NOTE]  
    > El nombre de cuenta SAM de Active Directory del usuario no se puede usar como valor de Identity porque puede que no sea único en el bosque.


