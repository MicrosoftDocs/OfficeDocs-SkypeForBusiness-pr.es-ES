---
title: 'Lync Server 2013: Comprobar la implementación de la movilidad'
TOCTitle: Comprobar la implementación de la movilidad
ms:assetid: 72f9b4d3-57b0-4705-9480-cfdca313a70c
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Hh690024(v=OCS.15)
ms:contentKeyID: 48275672
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Comprobar la implementación de la movilidad en Lync Server 2013

 

_**Última modificación del tema:** 2013-02-12_

    Some information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

Después de implementar los servicios Movilidad de Lync Server y Detección automática de Lync Server, ejecute una transacción de prueba para comprobar que la implementación funciona correctamente. Puede ejecutar **Test-CsUcwaConference** para probar la capacidad de dos usuarios que usen clientes Lync 2013 Mobile para crear, unirse y comunicarse en una conferencia. Para poder usar esta transacción de prueba, son necesarios dos usuarios reales o de prueba y sus credenciales completas.

Puede usar **Test-CsMcxP2PIM** para probar el envío de un mensaje instantáneo entre dos usuarios de Lync 2010 Mobile. Al igual que con **Test-CsUcwaConference**, use dos usuarios reales o dos usuarios de prueba predefinidos.

## Para probar la conferencia con clientes de Lync 2013 Mobile

1.  Inicie sesión como miembro del rol CsAdministrator en cualquier equipo que tenga instalado Shell de administración de Lync Server y Ocscore.

2.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y, después, en **Shell de administración de Lync Server**.

3.  En la línea de comandos, escriba lo siguiente:
    
        Test-CsUcwaConference -TargetFqdn <FQDN of Front End pool> -Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID> -OrganizerSipAddress sip:<SIP address of test user 1> -OrganizerCredential <test user 1 credentials> -ParticipantSipAddress sip:<SIP address of test user 2> -ParticipantCredential <test user 2 credentials> -v
    
    Puede definir las credenciales en un script y pasarlas al cmdlet de prueba. Por ejemplo:
    
        $passwd1 = ConvertTo-SecureString "Password01" -AsPlainText -Force
        $passwd2 = ConvertTo-SecureString "Password02" -AsPlainText -Force
        $testuser1 = New-Object Management.Automation.PSCredential("contoso\UserName1", $passwd1)
        $testuser2 = New-Object Management.Automation.PSCredential("contoso\UserName2", $passwd2)
        Test-CsUcwaConference -TargetFqdn pool01.contoso.com -Authentication Negotiate -OrganizerSipAddress sip:UserName1@contoso.com -OrganizerCredential $testuser1 -ParticipantSipAddress sip:UserName2@contoso.com -ParticipantCredential $testuser2 -v

## Para probar la mensajería instantánea (MI) de persona a persona con Lync 2010 Mobile

1.  Inicie sesión como miembro del rol CsAdministrator en cualquier equipo que tenga instalado Shell de administración de Lync Server y Ocscore.

2.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y, después, en **Shell de administración de Lync Server**.

3.  En la línea de comandos, escriba lo siguiente:
    
        Test-CsMcxP2PIM -TargetFqdn <FQDN of Front End pool> -Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID> -SenderSipAddress sip:<SIP address of test user 1> -SenderCredential <test user 1 credentials> -ReceiverSipAddress sip:<SIP address of test user 2> -ReceiverCredential <test user 2 credentials> -v
    
    Puede definir las credenciales en un script y pasarlas al cmdlet de prueba. Por ejemplo:
    
        $passwd1 = ConvertTo-SecureString "Password01" -AsPlainText -Force
        $passwd2 = ConvertTo-SecureString "Password02" -AsPlainText -Force
        $tuc1 = New-Object Management.Automation.PSCredential("contoso\UserName1", $passwd1)
        $tuc2 = New-Object Management.Automation.PSCredential("contoso\UserName2", $passwd2)
        Test-CsMcxP2PIM -TargetFqdn pool01.contoso.com -Authentication Negotiate -SenderSipAddress sip:UserName1@contoso.com -SenderCredential $tuc1 -ReceiverSipAddress sip:UserName2@contoso.com -ReceiverCredential $tuc2 -v

## Vea también

#### Otros recursos

[Test-CsMcxP2PIM](https://docs.microsoft.com/en-us/powershell/module/skype/Test-CsMcxP2PIM)  
[Test-CsUcwaConference](https://docs.microsoft.com/en-us/powershell/module/skype/Test-CsUcwaConference)

