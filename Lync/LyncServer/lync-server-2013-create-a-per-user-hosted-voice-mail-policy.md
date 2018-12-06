---
title: "Créer une strat. de mess. Voc. hébergée par utilisateur dans Lync Server 2013"
TOCTitle: "Créer une strat. de mess. Voc. hébergée par utilisateur dans Lync Server 2013"
ms:assetid: 39018a7c-e0c3-46a2-be4e-05604ec67a50
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg425867(v=OCS.15)
ms:contentKeyID: 48274971
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Crear una directiva de correo de voz hospedado por usuario en Lync Server 2013

 

_**Última modificación del tema:** 2012-09-24_

Una directiva *por usuario* solo puede afectar a usuarios individuales, grupos y objetos de contacto. Para implementar una directiva por usuario, debe asignar explícitamente la directiva a uno o varios usuarios, grupos u objetos de contacto. Para obtener más información, consulte [Asignar una directiva de correo de voz hospedado por usuario en Lync Server 2013](lync-server-2013-assign-a-per-user-hosted-voice-mail-policy.md).

Para obtener más información sobre cómo trabajar con directivas de correo de voz hospedado por usuario, consulte la documentación del Shell de administración de Lync Server acerca de los siguientes cmdlets:

  - [New-CsHostedVoicemailPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsHostedVoicemailPolicy)

  - [Set-CsHostedVoicemailPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsHostedVoicemailPolicy)

  - [Get-CsHostedVoicemailPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsHostedVoicemailPolicy)

## Para crear una directiva de correo de voz hospedado por usuario

1.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y, después, en **Shell de administración de Lync Server**.

2.  Ejecute el cmdlet New-CsHostedVoicemailPolicy para crear la directiva. Por ejemplo, ejecute lo siguiente:
    
        New-CsHostedVoicemailPolicy -Identity ExRedmond -Destination ExUM.fabrikam.com -Description "Hosted voice mail policy for Redmond users." -Organization "corp1.litwareinc.com, corp2.litwareinc.com"
    
    En el ejemplo anterior se crea una directiva de correo de voz hospedado con un ámbito por usuario y se establecen los siguientes parámetros:
    
      - **Identity** hace referencia a un identificador único de la directiva, en el que se incluye el ámbito. En una directiva con ámbito por usuario, este valor de parámetro se especifica como una cadena sencilla, como por ejemplo, ExRedmond.
    
      - **Destination** especifica el nombre de dominio completo (FQDN) del servicio de mensajería unificada de Exchange hospedado. Este parámetro es opcional pero, si trata de habilitar a un usuario para el correo de voz hospedado y la directiva asignada al usuario no tiene ningún valor de Destination, no podrá habilitarlo.
    
      - **Description** ofrece información descriptiva opcional acerca de la directiva.
    
      - **Organization** especifica una lista separada por comas de los arrendatarios de Exchange que contienen usuarios de Lync Server 2013. Cada arrendatario se debe especificar como el FQDN del arrendatario en cuestión en el servicio de mensajería unificada de Exchange hospedado.

## Vea también

#### Tareas

[Asignar una directiva de correo de voz hospedado por usuario en Lync Server 2013](lync-server-2013-assign-a-per-user-hosted-voice-mail-policy.md)

