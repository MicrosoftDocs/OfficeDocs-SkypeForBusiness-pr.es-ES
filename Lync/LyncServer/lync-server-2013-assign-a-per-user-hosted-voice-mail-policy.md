---
title: 'Lync Server 2013: asignar una directiva de correo de voz hospedado por usuario'
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
ms.openlocfilehash: 95413733a9b23ce1f749ebb16521a3349b00165d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41722960"
---
# <a name="assign-a-per-user-hosted-voice-mail-policy-in-lync-server-2013"></a>Asignar una directiva de correo de voz hospedado por usuario en Lync Server 2013

 


Implementar una o más directivas de correo de voz hospedado por cada usuario es opcional. Si implementa directivas por usuario, debe asignarlas explícitamente a usuarios, grupos o objetos de contacto.

Para obtener más información sobre cómo asignar o quitar la asignación de directivas de correo de voz hospedado por usuario, consulte la documentación del shell de administración de Lync Server para los siguientes cmdlets:

  - Grant-CsHostedVoicemailPolicy

  - Remove-CsHostedVoicemailPolicy

## <a name="to-assign-a-per-user-hosted-voice-mail-policy"></a>Para asignar una directiva de correo de voz hospedado por usuario

1.  Inicie el shell de administración de Lync Server: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **Shell de administración de Lync Server**.

2.  Ejecute el cmdlet Grant-CsHostedVoicemailPolicy para asignar la Directiva de correo de voz hospedado por usuario a usuarios individuales, grupos y objetos de contacto. Por ejemplo, ejecute lo siguiente:
    
        Grant-CsHostedVoicemailPolicy -Identity "Ken Myer" -PolicyName ExRedmond
    
    Este ejemplo asigna la Directiva de correo de voz hospedada de exredmond a usuario Ken Myer.
    
    **Identity** especifica la cuenta de usuario que se va a modificar. El valor de identidad puede especificarse con cualquiera de los siguientes formatos:
    
      - Dirección SIP del usuario
    
      - Nombre principal de usuario de Active Directory del usuario
    
      - Nombre de inicio de\\sesión de dominio del usuario (por\\ejemplo, contoso kenmyer)
    
      - El nombre para mostrar de los servicios de dominio de Active Directory del usuario (por ejemplo, Ken Myer). Si usa el nombre para mostrar como valor de identidad, puede usar el carácter comodín asterisco\*(). Por ejemplo, la identidad "\* Smith" devuelve todos los usuarios que tienen un nombre para mostrar que termina con el valor de cadena "Smith".
    

    > [!NOTE]  
    > El nombre de cuenta SAM del usuario de Active Directory no se puede usar como valor de identidad porque el nombre de cuenta SAM no es necesariamente único en el bosque.


