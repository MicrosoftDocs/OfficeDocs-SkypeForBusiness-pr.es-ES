---
title: "Crear una directiva de correo de voz hospedado a nivel de sitio en Lync Server 2013"
TOCTitle: "Créer une strat. de mess. vocale hébergée pour un site dans Lync Server 2013"
ms:assetid: 145892c8-a6ca-45fb-9e83-786f709dd775
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398216(v=OCS.15)
ms:contentKeyID: 48274511
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Crear una directiva de correo de voz hospedado a nivel de sitio en Lync Server 2013

 

_**Última modificación del tema:** 2012-09-24_

Una directiva del *sitio* puede afectar a todos los usuarios del sitio en el que la directiva en cuestión está definida. En caso de que un usuario esté configurado para tener acceso a la mensajería unificada de Exchange hospedada y no tenga asignada una directiva específica de usuario, se aplicará la directiva del sitio y, si no hay una directiva del sitio implementada, se usará la directiva global.

Para obtener información detallada sobre cómo configurar directivas del sitio, consulte la documentación del Shell de administración de Lync Server relativa a los siguientes cmdlet:

  - [New-CsHostedVoicemailPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsHostedVoicemailPolicy)

  - [Set-CsHostedVoicemailPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsHostedVoicemailPolicy)

  - [Get-CsHostedVoicemailPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsHostedVoicemailPolicy)

## Para crear una directiva de correo de voz hospedado del sitio

1.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y, después, en **Shell de administración de Lync Server**.

2.  Ejecute el cmdlet New-CsHostedVoicemailPolicy para crear la directiva. Por ejemplo, ejecute lo siguiente:
    
        New-CsHostedVoicemailPolicy -Identity site:Redmond -Destination ExUM.fabrikam.com -Description "Hosted voice mail policy for the Redmond site." -Organization "corp1.litwareinc.com, corp2.litwareinc.com"
    
    Con este ejemplo se crea una directiva de correo de voz hospedado con ámbito de sitio y se establecen los parámetros descritos a continuación:
    
      - **Identity** hace referencia a un identificador único de la directiva, en el que se incluye el ámbito. En el caso de una directiva con ámbito de sitio, el valor del parámetro Identity se debe especificar con el formato `site:`*\<nombre\>* (por ejemplo, `site:Redmond`).
    
      - **Destination** especifica el nombre de dominio completo (FQDN) del servicio de mensajería unificada de Exchange hospedado. Este parámetro es opcional pero, si trata de habilitar a un usuario para el correo de voz hospedado y la directiva asignada al usuario no tiene ningún valor de Destination, no podrá habilitarlo.
    
      - **Description** ofrece información descriptiva opcional acerca de la directiva.
    
      - **Organization** especifica una lista separada por comas de los arrendatarios de Exchange que contienen usuarios de Lync Server 2013. Cada arrendatario se debe especificar como el FQDN del arrendatario en cuestión en el servicio de mensajería unificada de Exchange hospedado.

