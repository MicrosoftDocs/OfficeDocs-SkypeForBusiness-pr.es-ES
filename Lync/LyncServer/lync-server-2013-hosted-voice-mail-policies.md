---
title: 'Lync Server 2013: Directivas de correo de voz hospedado'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Hosted voice mail policies
ms:assetid: d62a35ed-cbe2-4f06-86b4-e192c18435c1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398932(v=OCS.15)
ms:contentKeyID: 48185506
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9a23f5fa67a34d479bbc5b9d5c9bf55071b187c1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34835062"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="hosted-voice-mail-policies-in-lync-server-2013"></a>Directivas de correo de voz hospedado en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-01_

Una *Directiva de correo de voz hospedada* proporciona información a la aplicación de enrutamiento de 2013 ExUM de Lync Server acerca de dónde enrutar las llamadas de los usuarios cuyos buzones se encuentran en un servicio de Exchange hospedado.

<div>


> [!NOTE]  
> Las directivas de correo de voz hospedado solo son necesarias para la integración de Lync Server 2013 con mensajería unificada de Exchange hospedado. No son necesarios para la integración con la mensajería unificada de Exchange local.



</div>

<div>

## <a name="hosted-voice-mail-policy-scope"></a>Ámbito de directiva de correo de voz hospedado

El ámbito de la Directiva de correo de voz hospedado determina el nivel jerárquico al que se aplica la Directiva. Puede configurar directivas de correo de voz hospedado con los siguientes niveles de ámbito:

  - La directiva *global* puede afectar potencialmente a todos los usuarios de la implementación de Lync Server 2013. Si un usuario está habilitado para el acceso a la mensajería unificada de Exchange hospedado y no se le ha asignado una directiva por usuario, y si no se ha asignado una directiva de sitio al sitio del usuario, se aplicará la directiva global. La directiva global se instala con Lync Server 2013. Puede modificarla para satisfacer sus necesidades, pero no puede cambiarle el nombre ni eliminarla.

  - Una directiva de *sitio* puede afectar a todos los usuarios alojados en el sitio para el que se define la Directiva. Si un usuario está configurado para el acceso a mensajería unificada de Exchange hospedado y no se le ha asignado una directiva por usuario, se aplicará la Directiva de sitio.

  - Una directiva *por usuario* solo puede afectar a usuarios individuales o grupos. Para exigir una directiva por usuario, debe asignarla explícitamente a usuarios individuales, grupos y objetos de contacto.

<div>


> [!NOTE]  
> En la mayoría de los casos, solo se necesita una directiva de correo de voz hospedado. A menudo puede modificar la directiva global para satisfacer todas sus necesidades. Si implementa varias directivas de correo de voz hospedado, todas las directivas tienen ámbito por usuario.



</div>

</div>

<div>

## <a name="hosted-voice-mail-policy-attributes"></a>Atributos de directiva de correo de voz hospedado

Una directiva de correo de voz define dos atributos que la aplicación de enrutamiento ExUM de Lync Server 2013 inserta en el URI de la solicitud de un mensaje de invitación que se envía a la implementación de mensajería unificada de Exchange hospedada:

  - **Destino:** El nombre de dominio completo (FQDN) del servicio de mensajería unificada de Exchange hospedado. Este valor lo usa el servidor perimetral local de Lync Server para fines de enrutamiento.
    
    <div>
    

    > [!NOTE]  
    > El FQDN de Exchange Online es exap.um.outlook.com.

    
    </div>

  - **Organización:** El FQDN del inquilino en el servicio hospedado de mensajería unificada de Exchange que aloja los buzones de los usuarios de Lync Server 2013. Una directiva de correo de voz puede contener varias organizaciones. Si se incluye más de una organización en la Directiva, este atributo debe ser una lista separada por comas de los inquilinos de Exchange Server que alojan los buzones de usuario de Lync Server 2013.

<div>


> [!NOTE]  
> El administrador de inquilinos del servicio de mensajería unificada de Exchange hospedado proporcionará los valores necesarios para la configuración de los atributos de destino y organización. Para configurar la Directiva, debe ejecutar el cmdlet New-CsHostedVoicemailPolicy o usar el cmdlet Set-CsHostedVoicemailPolicy para modificar una que exista (por ejemplo, la directiva global).



</div>

Para obtener detalles sobre la administración de directivas de correo de voz hospedado, consulte la documentación del shell de administración de Lync Server para los siguientes cmdlets:

  - New-CsHostedVoicemailPolicy

  - Set-CsHostedVoicemailPolicy

  - Get-CsHostedVoicemailPolicy

</div>

<div>

## <a name="per-user-voice-mail-policy-assignment"></a>Asignación de directiva de correo de voz por usuario

Si su Directiva de correo de voz hospedada se define con ámbito por usuario, debe asignarla de forma explícita. Puede ejecutar el cmdlet Grant-CsHostedVoicemailPolicy para asignar la Directiva a usuarios individuales o a grupos.

Para obtener información detallada sobre cómo asignar o quitar una directiva de correo de voz hospedado por usuario, consulte la documentación del shell de administración de Lync Server para los siguientes cmdlets:

  - Grant-CsHostedVoicemailPolicy

  - Remove-CsHostedVoicemailPolicy

</div>

</div>

<span> </span>

</div>

</div>

</div>

