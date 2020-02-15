---
title: 'Lync Server 2013: directivas de correo de voz hospedado'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Hosted voice mail policies
ms:assetid: d62a35ed-cbe2-4f06-86b4-e192c18435c1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398932(v=OCS.15)
ms:contentKeyID: 48185506
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 01e844e62934a697b12afa76d2e9c9405a30a4a4
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043182"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="hosted-voice-mail-policies-in-lync-server-2013"></a>Directivas de correo de voz hospedado en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-01_

Una *Directiva de correo de voz hospedada* proporciona información a la aplicación de enrutamiento ExUM de Lync Server 2013 sobre dónde enrutar las llamadas de los usuarios cuyos buzones se encuentran en un servicio de Exchange hospedado.

<div>


> [!NOTE]  
> Las directivas de correo de voz hospedado solo son necesarias para la integración de Lync Server 2013 con mensajería unificada de Exchange hospedada. No son necesarias para la integración con la mensajería unificada local de Exchange.



</div>

<div>

## <a name="hosted-voice-mail-policy-scope"></a>Ámbito de directiva de correo de voz hospedado

El ámbito de directiva de correo de voz hospedado determina el nivel jerárquico en que se aplica la directiva. Configure directivas de correo de voz hospedado con los niveles de ámbito siguientes:

  - La directiva *global* puede afectar potencialmente a todos los usuarios de la implementación de Lync Server 2013. Si un usuario está habilitado para el acceso a la mensajería unificada hospedada de Exchange y no se le ha asignado una directiva por usuario, y si no se ha asignado una directiva de sitio al sitio del usuario, se aplicará la directiva global. La directiva global se instala con Lync Server 2013. Modifíquela para adaptarla a sus necesidades, aunque no puede cambiarle el nombre ni eliminarla.

  - Una directiva de *sitio* puede afectar a todos los usuarios que están hospedados en el sitio para el que se ha definido la directiva. Si un usuario está configurado para el acceso a la mensajería unificada hospedada de Exchange y no se le ha asignado una directiva por usuario, se aplicará la directiva de sitio.

  - Una directiva *por usuario* solo afecta a grupos o usuarios individuales. Para aplicar una directiva por usuario, debe asignar de forma explícita la directiva a objetos de contacto, usuarios y grupos.

<div>


> [!NOTE]  
> En la mayoría de los casos, solo es necesaria una directiva de correo de voz hospedado. Por lo general, es posible modificar la directiva global para adaptarla a nuestras necesidades específicas. Si implementa varias directivas de correo de voz hospedado, todas estas directivas serán de ámbito por usuario.



</div>

</div>

<div>

## <a name="hosted-voice-mail-policy-attributes"></a>Atributos de directiva de correo de voz hospedado

Una directiva de correo de voz define dos atributos que la aplicación de enrutamiento ExUM de Lync Server 2013 inserta en el URI de solicitud de un mensaje INVITE que se envía a la implementación de la mensajería unificada de Exchange hospedada:

  - **Destino:** El nombre de dominio completo (FQDN) del servicio de mensajería unificada de Exchange hospedado. Este valor se usa en el servidor perimetral de Lync Server local para fines de enrutamiento.
    
    <div>
    

    > [!NOTE]  
    > El FQDN para Exchange Online es exap.um.outlook.com.

    
    </div>

  - **Organización:** El FQDN del inquilino en el servicio de mensajería unificada de Exchange hospedado que aloja los buzones de correo de los usuarios de Lync Server 2013. Una directiva de correo de voz puede contener varias organizaciones. Si se incluye más de una organización en la Directiva, este atributo debe ser una lista separada por comas de los inquilinos de Exchange Server que hospedan los buzones de usuario de Lync Server 2013.

<div>


> [!NOTE]  
> El administrador de arrendatarios del servicio de mensajería unificada hospedada de Exchange proporcionará los valores necesarios para la configuración de los atributos Destination y Organization. Para configurar su directiva, ejecute el cmdlet New-CsHostedVoicemailPolicy o use el cmdlet Set-CsHostedVoicemailPolicy para modificar una que ya exista (por ejemplo, la directiva global).



</div>

Para obtener información detallada sobre la administración de directivas de correo de voz hospedado, consulte la documentación del shell de administración de Lync Server para los siguientes cmdlets:

  - New-CsHostedVoicemailPolicy

  - Set-CsHostedVoicemailPolicy

  - Get-CsHostedVoicemailPolicy

</div>

<div>

## <a name="per-user-voice-mail-policy-assignment"></a>Asignación de directivas de correo de voz por usuario

Si su directiva de correo de voz hospedado se ha definido con el ámbito por usuario, asígnela de forma explícita. Puede ejecutar el cmdlet Grant-CsHostedVoicemailPolicy para asignar la directiva a grupos o usuarios individuales.

Para obtener más información sobre cómo asignar o quitar una directiva de correo de voz hospedado por usuario, consulte la documentación del shell de administración de Lync Server para los siguientes cmdlets:

  - Grant-CsHostedVoicemailPolicy

  - Remove-CsHostedVoicemailPolicy

</div>

</div>

<span> </span>

</div>

</div>

</div>

