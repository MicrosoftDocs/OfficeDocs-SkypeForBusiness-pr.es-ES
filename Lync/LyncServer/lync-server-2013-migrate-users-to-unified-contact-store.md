---
title: "Lync Server 2013: Realizar la migración de usuarios a almacén de contactos unificados"
TOCTitle: Realizar la migración de usuarios a almacén de contactos unificados
ms:assetid: 215a8ec1-d63e-4fdf-b73d-75aeb9dddb43
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ204737(v=OCS.15)
ms:contentKeyID: 48274664
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Realizar la migración de usuarios a almacén de contactos unificados en Lync Server 2013

 

_**Última modificación del tema:** 2012-10-15_

Los contactos de un usuario se migran automáticamente al servidor Exchange 2013 cuando el usuario:

  - Tiene asignado una directiva de servicios del usuario que tiene UcsAllowed configurado en True.

  - Tiene aprovisionado un buzón de Exchange 2013 y ha iniciado sesión en el buzón al menos una vez.

  - Inicia sesión usando un cliente enriquecido de Lync 2013.

Si el usuario inicia sesión con un cliente de Lync 2010 o de una versión anterior, o si el usuario no está conectado con un servidor de Exchange 2013, se omitirá la directiva de servicios del usuario y los contactos del usuario permanecerán en Lync Server.

Puede determinar si se han migrado los contactos de un usuario usando uno de los métodos siguientes:

  - Compruebe la siguiente clave del registro en el equipo cliente:
    
    HKEY\_CURRENT\_USER\\Software\\Microsoft\\Office\\15.0\\Lync\\\<SIP URL\>\\UCS
    
    Si los contactos del usuario están almacenados en Exchange 2013, esta clave contiene en InUCSMode el valor 2165.

  - Ejecute el cmdlet **Test-CsUnifiedContactStore**. En la línea de comandos de Shell de administración de Lync Server, escriba:
    
        Test-CsUnifiedContactStore -UserSipAddress "sip:kenmyer@litwareinc.com" -TargetFqdn "atl-cs-001.litwareinc.com"
    
    Si el cmdlet **Test-CsUnifiedContactStore** se lleva a cabo con éxito, quiere decir que los contactos del usuario se han migrado al almacén de contactos unificado.

