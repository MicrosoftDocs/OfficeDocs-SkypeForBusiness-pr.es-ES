---
title: Identidades, ámbitos e inquilinos
TOCTitle: Identidades, ámbitos e inquilinos
ms:assetid: 7cfa194a-2d01-4370-9b48-ee13ff597fa5
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Dn362819(v=OCS.15)
ms:contentKeyID: 56271290
ms.date: 06/02/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Identidades, ámbitos e inquilinos

 

_**Última modificación del tema:** 2015-06-22_

Muchos de los cmdlets de Windows PowerShell que se usan para administrar Skype Empresarial Online exigen ser muy específico sobre el elemento que se quiere administrar. Por ejemplo, al ejecutar el cmdlet [Set-CsUserAcp](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsUserAcp), hay que indicar qué usuario se quiere administrar, lo cual es lógico. A menos que le digamos al cmdlet específicamente la cuenta de usuario que tratamos de administrar, el cmdlet **Set-CsUserAcp** no sabrá cuál es la información de usuario de audioconferencia que hay que modificar. Por este motivo, cada vez que se ejecuta el cmdlet **Set-CsUserAcp**, hay que incluir el parámetro Identity seguido de la identidad de la cuenta de usuario que hay que modificar:

    Set-CsUserAcp -Identity "Ken Myer" -TollNumber "14255551298" -ParticipantPassCode 13761 -Domain "fabrikam.com" -Name "Fabrikam ACP"

Si el término *Identity* siempre hiciera referencia a la identidad de una cuenta de usuario, no habría mucho motivo de confusión. Cuando se trabaja con personas (usuarios, contactos, etc.), las identidades se refieren a los propios usuarios. Sin embargo, aparte de las cuentas de usuario, existen otros elementos con identidad. Al trabajar con componentes del servicio de Skype Empresarial Online (directivas, opciones de configuración, etc.), el término Identity significa algo un poco diferente. Fijémonos, por ejemplo, en este comando:

    Get-CsMeetingConfiguration -Identity "global"

En este caso, la identidad "global" se refiere al ámbito de las opciones de configuración de reunión. El término *ámbito* se usa en Skype Empresarial Online (y en Lync Server) para designar las esferas de administración. De manera predeterminada, las directivas y las configuraciones siempre tienen un ámbito global. Cuando configure su cuenta de Skype Empresarial Online por primera vez, tendrá, de manera predeterminada, una colección de configuraciones y directivas globales: opciones globales de configuración de reunión, una directiva global de acceso externo, un plan de marcado global, etc.

Estas configuraciones y directivas globales se introdujeron en Microsoft Lync Server 2010 para garantizar que todos los usuarios y componentes siempre se administrasen de algún modo, cosa que no necesariamente sucedía en Microsoft Office Communicator 2007 R2. En función de cómo se accediese al sistema, se podía llegar a un estado no administrado en su mayor parte (normalmente, por la imposibilidad de aplicar Directiva de grupo a su cuenta de usuario). En cambio, en Lync Server y en Skype Empresarial Online, no hay nada que se deje no administrado, ya que, en lugar de cualquier otra cosa, siempre se aplican las configuraciones y directivas globales.

¿Qué significa "en lugar de cualquier otra cosa"? En el caso de Skype Empresarial Online, podemos crear directivas en la esfera de administración o *ámbito de etiqueta*. Las directivas creadas en el ámbito de etiqueta (también denominado *ámbito por usuario*) tienen prioridad sobre las directivas creadas en el ámbito global. En otras palabras, una directiva por usuario siempre se aplicará antes que una directiva global. Supongamos que tiene, por ejemplo, dos directivas de acceso de usuarios externos. La directiva global impide a los usuarios comunicarse con personas que tengan cuentas en proveedores de mensajería instantánea (MI) pública, como Windows Live, mientras que la directiva por usuario, AllowPublicIMCommunication, permite la comunicación con estos proveedores.

También puede tener dos usuarios: Ken Myer y Pilar Ackerman. A Ken Myer se le ha asignado la directiva por usuario y a Pilar Ackerman no se le ha asignado ninguna directiva por usuario, es decir, que a ella la administra la directiva de acceso externo global. En la tabla siguiente se ve qué usuario (si existe alguno) se puede comunicar con proveedores de mensajería instantánea pública:


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Configuración de directiva</th>
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
<td><p>Configuración de directiva por usuario para proveedores de mensajería instantánea pública</p></td>
<td><p>Sí</p></td>
<td><p>No</p></td>
</tr>
<tr class="odd">
<td><p>El usuario se puede comunicar con proveedores de mensajería instantánea pública</p></td>
<td><p>Sí</p></td>
<td><p>No</p></td>
</tr>
</tbody>
</table>


Como puede ver, Ken Myer se puede comunicar con los proveedores de mensajería instantánea pública. Esto se debe a que la configuración de la directiva por usuario que tiene asignada él invalida la configuración de la directiva global. Pilar Ackerman no se puede comunicar con los proveedores de mensajería instantánea pública porque a ella la administra la directiva global, que prohíbe las comunicaciones de este tipo.

Las directivas por usuario las tiene que crear el equipo de soporte técnico de Office 365. Una vez creadas, las podrá asignar a los usuarios usando el cmdlet **Grant-Cs** apropiado (por ejemplo [Grant-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsExternalAccessPolicy)). Estas directivas se reconocen fácilmente porque la identidad de la directiva siempre empieza por el **prefijo** "tag" (etiqueta). Por ejemplo:

    Identity : tag:AllowPublicIMCommunication


> [!NOTE]
> El <STRONG>prefijo</STRONG> "tag" se remonta a los inicios del desarrollo de Lync Server 2010. Por aquel entonces, las directivas por usuario se denominaban <EM>directivas de etiqueta</EM> y se identifican por el <STRONG>prefijo</STRONG> "tag". Estas directivas reciben ahora el nombre de <EM>directivas por usuario</EM>, que es más preciso, y el ámbito de etiqueta se conoce como <EM>ámbito por usuario</EM>, denominación también más precisa. Sin embargo, por motivos técnicos, el <STRONG>prefijo</STRONG> "tag" nunca se cambió.



Otro término clave que se usa al trabajar con Skype Empresarial Online y Windows PowerShell es *inquilino*. Al configurar una cuenta de Skype Empresarial Online, a la nueva implementación se le asigna un número de identificación de inquilino, que es un identificador único global (GUID) parecido a este:

    bf19b7db-6960-41e5-a139-2aa373474354

Algunos de los cmdlets de Skype Empresarial Online requieren escribir el id. de inquilino cada vez que se ejecutan. Tiene que escribir el id. de inquilino aunque haya iniciado sesión en el inquilino y este sea el único que tenga. Afortunadamente, no es necesario memorizar el id. de inquilino; lo puede recuperar en cualquier momento ejecutando el siguiente comando de Windows PowerShell:

    Get-CsTenant | Select-Object TenantId

Saber cosas como la diferencia entre el ámbito global y el ámbito por usuario (o ámbito de etiqueta) ya es un gran paso, pero también es importante saber cuándo se pueden usar estos ámbitos (o, incluso, si son necesarios). Lo mismo pasa con las identidades y los parámetros de inquilino. En los temas siguientes se explica cómo los distintos cmdlets de Skype Empresarial Online usan las identidades, los ámbitos y el parámetro de inquilino:

  - [Cmdlets exclusivamente de ámbito global](cmdlets-in-skype-for-business-online-that-use-only-the-global-scope.md)

  - [Cmdlets de ámbito global y de etiqueta](cmdlets-in-skype-for-business-online-that-use-the-global-scope-and-the-tag-scope.md)

  - [Cmdlets que usan identidades de usuario](cmdlets-in-skype-for-business-online-that-use-a-user-identity.md)

  - [Cmdlets con identidad de usuario y ámbito de etiqueta](cmdlets-in-skype-for-business-online-that-use-a-user-identity-and-the-tag-scope.md)

  - [Cmdlets que usan el parámetro Tenant](cmdlets-in-skype-for-business-online-that-use-the-tenant-parameter.md)

  - [Cmdlets que usan identidades de proveedores de servicios de conferencia](cmdlets-in-skype-for-business-online-that-use-a-conferencing-provider-identity.md)

  - [Cmdlets que no usan ámbitos ni identidades](cmdlets-in-skype-for-business-online-that-do-not-use-a-scope-or-an-identity.md)

