---
title: Identidades, ámbitos y espacios empresariales en Skype empresarial online
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Identities, scopes, and tenants
ms:assetid: 7cfa194a-2d01-4370-9b48-ee13ff597fa5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362819(v=OCS.15)
ms:contentKeyID: 56558817
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8a759c53b717cbaf1ecdb747d5cb01e94b305f52
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842871"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="identities-scopes-and-tenants-in-skype-for-business-online"></a>Identidades, ámbitos y espacios empresariales en Skype empresarial online

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2015-03-09_

Muchos de los cmdlets de Windows PowerShell que se usan para administrar Skype empresarial online requieren que sea muy específico sobre el elemento que está tratando de administrar. Por ejemplo, cuando ejecuta el cmdlet [set-CsUserAcp](https://docs.microsoft.com/powershell/module/skype/Set-CsUserAcp) , debe indicar qué usuario está tratando de administrar. Esto tiene sentido. A menos que indique específicamente el cmdlet qué cuenta de usuario administrar, el cmdlet **set-CsUserAcp** no tiene la idea de qué información de las conferencias de audio del usuario debe modificarse. Por esta razón, cada vez que ejecute el cmdlet **set-CsUserAcp** , tendrá que incluir el parámetro Identity, seguido de la identidad de la cuenta de usuario que se va a modificar:

    Set-CsUserAcp -Identity "Ken Myer" -TollNumber "14255551298" -ParticipantPassCode 13761 -Domain "fabrikam.com" -Name "Fabrikam ACP"

Si el término *identidad* siempre se refiere a la identidad de una cuenta de usuario, habría poca causa de confusión. Cuando se trata de personas (usuarios, contactos, etc.), las identidades hacen referencia a los usuarios individuales. Sin embargo, los elementos que no sean cuentas de usuario también tienen identidades. Cuando trabaja con componentes del servicio Skype empresarial online (directivas, parámetros de configuración, etc.), el término identidad significa algo ligeramente diferente. Por ejemplo, considere este comando:

    Get-CsMeetingConfiguration -Identity "global"

En este caso, la identidad "global" se refiere al ámbito de la configuración de la reunión. *Ámbito* es un término que se usa en Skype empresarial online (y en Lync Server) para designar esferas de administración. De forma predeterminada, las directivas y la configuración siempre tienen un ámbito global. La primera vez que configure su cuenta de Skype empresarial online, tendrá, de forma predeterminada, un conjunto de directivas y configuraciones globales (configuración global de la reunión, una directiva global de acceso externo, un plan de marcado global, etc.).

Estas directivas y configuraciones globales se introdujeron en Microsoft Lync Server 2010 para garantizar que todos los usuarios y todos los componentes se administren siempre de algún modo. Esto no era necesariamente cierto en Microsoft Office Communicator 2007 R2. En función de cómo haya acusado al sistema, podría acabar en un estado demasiado no administrado (generalmente, porque no se pudo aplicar la Directiva de grupo a su cuenta de usuario). Por el contrario, en Lync Server y en Skype empresarial online, nada se queda sin administrar. Esto se debe a que, en lugar de algo más, siempre se aplicarán las directivas y la configuración global.

¿Qué significa "en lugar de algo más"? Bueno, en el caso de Skype empresarial online, es posible crear directivas en el ámbito de la *etiqueta*o en Sphere of Management. Las directivas creadas en el ámbito de la etiqueta (también conocido como *ámbito por usuario*) tienen prioridad sobre las directivas creadas en el ámbito global. En otras palabras, una directiva por usuario siempre tendrá prioridad sobre una directiva global. Por ejemplo, es posible que tenga dos directivas de acceso de usuarios externos. La directiva global impide que los usuarios se comuniquen con personas que tienen cuentas en proveedores de mensajería instantánea pública (mi), como Windows Live. La Directiva por usuario, AllowPublicIMCommunication, permite la comunicación con proveedores de mensajes instantáneos públicos.

Es posible que también tenga dos usuarios: Ken Myer y Pilar Ackerman. Ken Myer ha sido asignado a la Directiva por usuario. No se ha asignado una directiva por usuario a Pilar Ackerman. es decir, está administrado por la Directiva de acceso externo global. En la tabla siguiente se muestra qué usuario (si hay alguno) puede comunicarse con los proveedores de mensajes instantáneos públicos:


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Configuración de la Directiva</th>
<th>Ken Myer</th>
<th>Pilar Ackerman</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Configuración de directiva global para proveedores de mensajería instantánea pública</p></td>
<td><p>No</p></td>
<td><p>No</p></td>
</tr>
<tr class="even">
<td><p>Configuración de Directiva por usuario para proveedores de mensajería instantánea pública</p></td>
<td><p>Sí</p></td>
<td><p>No</p></td>
</tr>
<tr class="odd">
<td><p>El usuario puede comunicarse con proveedores de mensajes instantáneos públicos</p></td>
<td><p>Sí</p></td>
<td><p>No</p></td>
</tr>
</tbody>
</table>


Como puede ver, Ken Myer puede comunicarse con proveedores de mensajes instantáneos públicos. Esto se debe a que la configuración de la Directiva por usuario asignada suplanta la configuración de la directiva global. Pilar Ackerman no puede comunicarse con proveedores de mensajes instantáneos públicos. Esto se debe a que está administrado por la directiva global y la directiva global prohíbe dichas comunicaciones.

Las directivas por usuario deben crearse para usted por soporte técnico de Office 365. Después de crear las directivas, puede asignarlas a los usuarios mediante el cmdlet **Grant-CS** correspondiente (por ejemplo, [Grant-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsExternalAccessPolicy)). Las directivas por usuario son fáciles de identificar porque la identidad de la Directiva siempre comienza con **** el prefijo de etiqueta. Por ejemplo:

    Identity : tag:AllowPublicIMCommunication

<div>


> [!NOTE]  
> Las fechas <STRONG></STRONG> del prefijo de etiqueta a los primeros días de desarrollo de Lync Server 2010. En esos días, las directivas por usuario se denominaban <EM>directivas de etiquetas</EM> y fueron identificadas por el <STRONG>prefijo</STRONG>de etiqueta. Ahora estas directivas se conocen con más precisión como <EM>directivas por usuario</EM>y el ámbito de la etiqueta se conoce con más precisión como <EM>ámbito de usuario</EM>. Sin embargo, por razones técnicas, el <STRONG>prefijo</STRONG> de etiqueta nunca se cambió.



</div>

Otro término clave que se usa al trabajar con Skype empresarial online y Windows PowerShell es el *inquilino*. Al configurar una cuenta de Skype empresarial online, se asigna a su nueva implementación un número de identificador de inquilino, que es un identificador único global (GUID) similar a este:

    bf19b7db-6960-41e5-a139-2aa373474354

Algunos de los cmdlets de Skype empresarial online requieren especificar el identificador de inquilino cada vez que se ejecuta el cmdlet. Debe especificar el identificador de inquilino incluso si ha iniciado sesión y solo tiene un inquilino. Afortunadamente, no es necesario memorizar el identificador de inquilino. Puede recuperar su identificador de inquilino en cualquier momento ejecutando el siguiente comando de Windows PowerShell:

    Get-CsTenant | Select-Object TenantId

Por supuesto, conocer aspectos como la diferencia entre el ámbito global y el ámbito por usuario (o el ámbito de la etiqueta) es solo la mitad de la batalla. También es importante saber cuándo (o incluso si) puede usar estos ámbitos. Lo mismo sucede con las identidades y el parámetro tenant. En los siguientes temas se describe cómo los diferentes cmdlets de Skype empresarial online usan identidades, ámbitos y el parámetro arrendatario:

  - [Cmdlets de Skype empresarial online que solo usan el ámbito global](cmdlets-in-skype-for-business-online-that-use-only-the-global-scope.md)

  - [Cmdlets de Skype empresarial online que usan el ámbito global y el ámbito de la etiqueta](cmdlets-in-skype-for-business-online-that-use-the-global-scope-and-the-tag-scope.md)

  - [Cmdlets de Skype empresarial online que usan una identidad de usuario](cmdlets-in-skype-for-business-online-that-use-a-user-identity.md)

  - [Cmdlets de Skype empresarial online que usan una identidad de usuario y el ámbito de la etiqueta](cmdlets-in-skype-for-business-online-that-use-a-user-identity-and-the-tag-scope.md)

  - [Cmdlets de Skype empresarial online que usan el parámetro tenant](cmdlets-in-skype-for-business-online-that-use-the-tenant-parameter.md)

  - [Cmdlets de Skype empresarial online que usan una identidad de proveedor de conferencias](cmdlets-in-skype-for-business-online-that-use-a-conferencing-provider-identity.md)

  - [Cmdlets de Skype empresarial online que no usan un ámbito o una identidad](cmdlets-in-skype-for-business-online-that-do-not-use-a-scope-or-an-identity.md)

</div>

<span> </span>

</div>

</div>

</div>

