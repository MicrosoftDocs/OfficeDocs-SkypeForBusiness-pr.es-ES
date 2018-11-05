---
title: 'Lync Server 2013: (Opcional) Comprobar conferencia de acceso telefónico local'
TOCTitle: (Opcional) Comprobar la conferencia de acceso telefónico local
ms:assetid: 3e2b4220-8fb3-442f-98b1-78447adb321f
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg425905(v=OCS.15)
ms:contentKeyID: 48275062
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# (Opcional) Comprobar la conferencia de acceso telefónico local en Lync Server 2013

 

_**Última modificación del tema:** 2011-01-21_

Para comprobar que la página web Configuración de la conferencia de acceso telefónico local y los números de acceso telefónico local funcionan correctamente, debe realizar las siguientes acciones:

  - Pruebe la página web Configuración de la conferencia de acceso telefónico local iniciando sesión en la dirección URL sencilla.

  - Pruebe que los números de acceso telefónico local funcionan correctamente para un grupo de servidores específico ejecutando el script que se ofrece más adelante en este tema. Este script simula llamadas a números de acceso. Para usar este script necesita la dirección SIP y las credenciales de un cliente de comunicaciones unificadas (UC) que se hospede en el grupo de servidores específico.

Este paso es opcional.

## Para probar números de acceso para un grupo de servidores específico

1.  Inicie sesión en el equipo como miembro del grupo RTCUniversalServerAdmins o como miembro del rol **Cs-ServerAdministrator** o **CsAdministrator**.

2.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y, después, en **Shell de administración de Lync Server**.

3.  Ejecute los siguientes comandos en símbolo del sistema:
    
        $credentials = Get-Credential
           User name:  testuser1@contoso.com
           Password:   ********
        Test-CsDialInConferencing -UserSipAddress sip:testuser1@contoso.com -UserCredential $credentials -TargetFqdn <serverName>.<domainName>.com -Verbose
    
    El informe resultante indica si hay errores, junto con la información de diagnóstico específica. La marca –Verbose proporciona más información sobre la cantidad de números de acceso que se encontraron y detalles sobre ellos.

