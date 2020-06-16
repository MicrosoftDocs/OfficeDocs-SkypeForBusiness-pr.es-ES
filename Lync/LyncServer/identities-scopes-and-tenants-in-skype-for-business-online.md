---
title: Identidades, ámbitos e inquilinos en Skype empresarial online
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Identities, scopes, and tenants
ms:assetid: 7cfa194a-2d01-4370-9b48-ee13ff597fa5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362819(v=OCS.15)
ms:contentKeyID: 56558817
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c3e5217c4214e6e86ca4c1dff62410c247cf7f8c
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755434"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="identities-scopes-and-tenants-in-skype-for-business-online"></a>Identidades, ámbitos e inquilinos en Skype empresarial online

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2015-03-09_

Muchos de los cmdlets de Windows PowerShell que se usan para administrar Skype empresarial online requieren que sea muy específico sobre el elemento que está tratando de administrar. Por ejemplo, al ejecutar el cmdlet [set-CsUserAcp](https://docs.microsoft.com/powershell/module/skype/Set-CsUserAcp) , debe indicar qué usuario está tratando de administrar. Esto tiene sentido. A menos que indique específicamente al cmdlet qué cuenta de usuario va a administrar, el cmdlet **set-CsUserAcp** no tiene idea de qué información de audioconferencia del usuario debe modificarse. Por este motivo, cada vez que ejecute el cmdlet **set-CsUserAcp** , deberá incluir el parámetro Identity, seguido de la identidad de la cuenta de usuario que se va a modificar:

    Set-CsUserAcp -Identity "Ken Myer" -TollNumber "14255551298" -ParticipantPassCode 13761 -Domain "fabrikam.com" -Name "Fabrikam ACP"

Si el término *identidad* siempre hacía referencia a la identidad de una cuenta de usuario, habría poca causa de confusión. Cuando se trabaja con personas (usuarios, contactos, etc.), las identidades se refieren a los usuarios individuales. Sin embargo, los elementos que no son cuentas de usuario también tienen identidades. Cuando trabaja con componentes del servicio Skype empresarial online (directivas, opciones de configuración, etc.), el término identidad significa algo ligeramente diferente. Por ejemplo, considere este comando:

    Get-CsMeetingConfiguration -Identity "global"

En este caso, la identidad "global" se refiere al ámbito de las opciones de configuración de reunión. *Ámbito* es un término que se usa en Skype empresarial online (y en Lync Server) para designar esferas de administración. De forma predeterminada, las directivas y la configuración siempre tienen un ámbito global. La primera vez que configure la cuenta de Skype empresarial online tendrá, de forma predeterminada, una colección de directivas y opciones de configuración globales: opciones de configuración de reuniones globales, una directiva de acceso externo global, un plan de marcado global, etc.

Estas directivas y configuraciones globales se introdujeron en Microsoft Lync Server 2010 para ayudar a garantizar que todos los usuarios y todos los componentes siempre se administrarían de alguna manera. Esto no era necesariamente cierto en Microsoft Office Communicator 2007 R2. En función de cómo obtuvo acceso al sistema, es posible que acabe en un estado no administrado en gran medida (normalmente, porque no se pudo aplicar la Directiva de grupo a su cuenta de usuario). Por el contrario, en Lync Server y en Skype empresarial online, no se deja nada sin administrar. Esto se debe a que, en lugar de nada más, siempre se aplicará la configuración y las directivas globales.

¿Qué queremos decir con "en lugar de cualquier otro elemento?". Bueno, en el caso de Skype empresarial online, es posible crear directivas en el ámbito de la *etiqueta*o en una esfera de administración. Las directivas creadas en el ámbito de la etiqueta (también conocido como *ámbito por usuario*) tienen prioridad sobre las directivas creadas en el ámbito global. Es decir, una directiva por usuario siempre tendrá prioridad sobre una directiva global. Por ejemplo, puede tener dos directivas de acceso de usuarios externos. La directiva global prohíbe a los usuarios comunicarse con personas que tienen cuentas en proveedores de mensajería instantánea pública (mi), como Windows Live. La Directiva por usuario, AllowPublicIMCommunication, permite la comunicación con proveedores de mensajería instantánea pública.

También es posible que tenga dos usuarios: Ken Myer y Pilar Ackerman. Se ha asignado a Ken Myer la Directiva por usuario. Pilar Ackerman no tiene asignada una directiva por usuario; es decir, se administra mediante la directiva global de acceso externo. En la tabla siguiente se muestra qué usuario (si lo hay) se puede comunicar con los proveedores de mensajería instantánea pública:


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Configuración de Directiva</th>
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
<td><p>El usuario puede comunicarse con proveedores de mensajería instantánea pública</p></td>
<td><p>Sí</p></td>
<td><p>No</p></td>
</tr>
</tbody>
</table>


Como puede ver, Ken Myer tiene permiso para comunicarse con proveedores de mensajería instantánea pública. Esto se debe a que la configuración de la Directiva por usuario que se le ha asignado reemplaza la configuración de la directiva global. Pilar Ackerman no puede comunicarse con proveedores de mensajería instantánea pública. Esto se debe a que está administrado por la directiva global y la directiva global prohíbe dicha comunicación.

El soporte técnico de Microsoft debe crear directivas por usuario. Una vez creadas las directivas, puede asignarlas a los usuarios mediante el cmdlet **Grant-CS** correspondiente (por ejemplo, [Grant-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsExternalAccessPolicy)). Las directivas por usuario son fáciles de identificar porque la identidad de la Directiva siempre comienza con el **prefijo**de etiqueta. Por ejemplo:

    Identity : tag:AllowPublicIMCommunication

<div>


> [!NOTE]  
> Las fechas del <STRONG>prefijo</STRONG> de etiqueta de vuelta a los primeros días de desarrollo de Lync Server 2010. En esos días, las directivas por usuario se denominaban <EM>directivas de etiquetas</EM> y se identificaron con el <STRONG>prefijo</STRONG>de etiqueta. Estas directivas se denominan ahora con más precisión como <EM>directivas por usuario</EM>y el ámbito de la etiqueta se conoce con más precisión como <EM>ámbito por usuario</EM>. Sin embargo, por motivos técnicos, el <STRONG>prefijo</STRONG> de etiqueta nunca se cambió.



</div>

Otro término clave que se usa al trabajar con Skype empresarial online y Windows PowerShell es el *espacio empresarial*. Cuando se configura una cuenta de Skype empresarial online, a la nueva implementación se le asigna un número de identificador de inquilino, que es un identificador único global (GUID) similar al siguiente:

    bf19b7db-6960-41e5-a139-2aa373474354

Algunos de los cmdlets de Skype empresarial online requieren que escriba el identificador de inquilino cada vez que ejecute el cmdlet. Debe especificar el identificador de inquilino incluso si ha iniciado sesión y solo tiene un inquilino. Afortunadamente, no es necesario memorizar el identificador de inquilino. Puede recuperar el identificador de inquilino en cualquier momento ejecutando el siguiente comando de Windows PowerShell:

    Get-CsTenant | Select-Object TenantId

Por supuesto, saber cosas como la diferencia entre el ámbito global y el ámbito por usuario (o el ámbito de la etiqueta) es sólo la mitad de la batalla. También es importante saber cuándo (o incluso si) puede usar estos ámbitos. Lo mismo se aplica a las identidades y al parámetro tenant. En los siguientes temas se describe cómo los diferentes cmdlets de Skype empresarial online usan identidades, ámbitos y el parámetro tenant:

  - [Cmdlets de Skype empresarial online que solo usan el ámbito global](cmdlets-in-skype-for-business-online-that-use-only-the-global-scope.md)

  - [Cmdlets de Skype empresarial online que usan el ámbito global y el ámbito de etiqueta](cmdlets-in-skype-for-business-online-that-use-the-global-scope-and-the-tag-scope.md)

  - [Cmdlets de Skype empresarial online que usan una identidad de usuario](cmdlets-in-skype-for-business-online-that-use-a-user-identity.md)

  - [Cmdlets de Skype empresarial online que usan una identidad de usuario y el ámbito de etiqueta](cmdlets-in-skype-for-business-online-that-use-a-user-identity-and-the-tag-scope.md)

  - [Cmdlets en Skype empresarial online que usan el parámetro tenant](cmdlets-in-skype-for-business-online-that-use-the-tenant-parameter.md)

  - [Cmdlets de Skype empresarial online que usan una identidad de proveedor de conferencias](cmdlets-in-skype-for-business-online-that-use-a-conferencing-provider-identity.md)

  - [Cmdlets de Skype empresarial online que no usan un ámbito ni una identidad](cmdlets-in-skype-for-business-online-that-do-not-use-a-scope-or-an-identity.md)

</div>

<span> </span>

</div>

</div>

</div>

