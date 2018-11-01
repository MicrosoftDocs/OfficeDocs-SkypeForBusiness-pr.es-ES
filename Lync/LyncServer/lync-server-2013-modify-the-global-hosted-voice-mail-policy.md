---
title: "Mod. la stratégie de messagerie vocale hébergée globale dans Lync Server 2013"
TOCTitle: "Mod. la stratégie de messagerie vocale hébergée globale dans Lync Server 2013"
ms:assetid: f059b3ce-a7d8-4ea9-b10b-0052222ec2ce
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg412994(v=OCS.15)
ms:contentKeyID: 48277111
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Modificar la directiva de correo de voz hospedado global en Lync Server 2013

 

_**Última modificación del tema:** 2012-09-24_

La directiva de correo de voz hospedado *global* se instala con Lync Server 2013. Puede modificarla para adaptarla a sus necesidades, pero no puede cambiarle el nombre ni eliminarla. Para modificar la directiva global, use el cmdlet Set-CsHostedVoicemailPolicy para asignar los valores pertinentes a los parámetros de una determinada implementación.

Para ver los detalles sobre el cmdlet [Set-CsHostedVoicemailPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsHostedVoicemailPolicy), consulte la documentación de Shell de administración de Lync Server.

## Para modificar una directiva global de correo de voz hospedado

1.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y, después, en **Shell de administración de Lync Server**.

2.  Ejecute el cmdlet Set-CsHostedVoicemailPolicy para establecer los parámetros de la directiva global del entorno. Por ejemplo, ejecute lo siguiente:
    
        Set-CsHostedVoicemailPolicy -Destination ExUM.fabrikam.com -Organization "corp1.litwareinc.com"
    
    Como este comando no especifica el parámetro Identity de la directiva, Interfaz de la línea de comandos Windows PowerShell establece los valores siguientes en la directiva global de correo de voz hospedado:
    
      - **Destination** especifica el nombre de dominio completo (FQDN) del servicio de mensajería unificada de Exchange hospedado. Este parámetro es opcional pero, si trata de habilitar a un usuario para el correo de voz hospedado y la directiva asignada al usuario no tiene ningún valor de Destination, no podrá habilitarlo.
    
      - **Organization** especifica una lista separada por comas de los arrendatarios de Exchange que contienen usuarios de Lync Server. Cada arrendatario se debe especificar como el FQDN del arrendatario en cuestión en el servicio de mensajería unificada de Exchange hospedado.
    

    > [!NOTE]
    > En el cmdlet de ejemplo anterior, el valor “corp1.litwareinc.com” reemplaza cualquier valor que ya estuviera presente en el parámetro Organization. Por ejemplo, si la directiva ya contiene una lista de organizaciones separadas por comas, se reemplazará toda la lista. Si desea agregar una organización a la lista en lugar de reemplazar toda la lista, ejecute un comando similar al siguiente.

    
        $a = Get-CsHostedVoicemailPolicy
        $a.Organization += ",corp3.litwareinc.com"
        Set-CsHostedVoicemailPolicy -Organization $a.Organization

