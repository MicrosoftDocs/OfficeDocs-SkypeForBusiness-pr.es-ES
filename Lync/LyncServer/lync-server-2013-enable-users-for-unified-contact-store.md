---
title: "Lync Server 2013: Habilitar usuarios para el almacenamiento de contactos unificado"
TOCTitle: Habilitar usuarios para el almacenamiento de contactos unificado
ms:assetid: 7b46a01f-beb5-4a33-adb0-35f0502b168d
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ205024(v=OCS.15)
ms:contentKeyID: 48275771
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Habilitar usuarios para el almacenamiento de contactos unificado en Lync Server 2013

 

_**Última modificación del tema:** 2012-10-07_

Al implementar Lync Server 2013 y publicar la topología, el almacén de contactos unificados se habilita para todos los usuarios de manera predeterminada. No necesita realizar ninguna acción adicional para habilitar el almacén de contactos unificados después de implementar Lync Server 2013. Sin embargo, puede usar el cmdlet **Set-CsUserServicesPolicy** para personalizar qué usuarios tienen disponible el almacén de contactos unificados. Puede habilitar esta característica globalmente, por sitio, por inquilino o por individuos o grupos de individuos.

## Procedimiento para habilitar usuarios para el almacén de contactos unificados

1.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y, después, en **Shell de administración de Lync Server**.

2.  Haga lo siguiente:
    
      - Para habilitar el almacén de contactos unificados globalmente para todos los usuarios de Lync Server, en la línea de comandos, escriba:
        
            Set-CsUserServicesPolicy -Identity global -UcsAllowed $True
    
      - Para habilitar el almacén de contactos unificados para los usuarios de un sitio específico, en la línea de comandos, escriba:
        
            New-CsUserServicesPolicy -Identity site:<site name> -UcsAllowed $True
        
        Por ejemplo:
        
            New-CsUserServicesPolicy -Identity site:Redmond -UcsAllowed $True
    
      - Para habilitar el almacén de contactos unificados por arrendatario, en la línea de comandos, escriba:
        
            Set-CsUserServicesPolicy -Tenant <tenantId> -UcsAllowed $True
        
        Por ejemplo:
        
            Set-CsUserServicesPolicy -Tenant "38aad667-af54-4397-aaa7-e94c79ec2308" -UcsAllowed $True
    
      - Para habilitar el almacén de contactos unificados para los usuarios especificados, en la línea de comandos, escriba:
        
            New-CsUserServicesPolicy -Identity "<policy name>" -UcsAllowed $True
            Grant-CsUserServicesPolicy -Identity "<user display name>" -PolicyName <"policy name">
        

        > [!NOTE]
        > También puede usar alias de usuario o URI de SIP en lugar del nombre para mostrar del usuario.

        
        Por ejemplo:
        
            New-CsUserServicesPolicy -Identity "UCS Enabled Users" -UcsAllowed $True
            Grant-CsUserServicesPolicy -Identity "Ken Myer" -PolicyName "UCS Enabled Users"
        

        > [!NOTE]
        > En el ejemplo anterior, el primer comando crea una nueva directiva por usuario denominada <EM>Usuarios habilitados para UC</EM> con el indicador UcsAllowed establecido en Verdadero. El segundo comando asigna la directiva al usuario con el nombre para mostrar Ken Myer, lo cual significa que Ken Myer ahora está habilitado para el almacén de contactos unificados.


