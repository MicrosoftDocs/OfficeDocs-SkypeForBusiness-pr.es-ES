---
title: "Habilitar la integración de mensajería instantánea y Exchange 2013 Outlook Web App"
TOCTitle: "Act. d’Exchange 2013 Outlook Web App et intégration à la mes. instantanée"
ms:assetid: 44d08cf0-b17d-46e1-a4f0-fcc2fe96a958
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ204857(v=OCS.15)
ms:contentKeyID: 48275069
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Habilitar la integración de mensajería instantánea y Exchange 2013 Outlook Web App

 

_**Última modificación del tema:** 2012-10-19_

Para habilitar la integración de la mensajería instantánea (MI) y Outlook Web Access (OWA) de Exchange 2013 con Lync Server 2013, debe agregar el servidor de acceso de cliente (CAS) de Exchange 2013 a la topología de Lync Server 2013 como un servidor de aplicación de confianza.

## Para crear un grupo de aplicaciones de confianza

1.  Inicie la Shell de administración de Lync Server 2013.

2.  Ejecute el siguiente cmdlet:
    
        Get-CsSite
    
    Esto devuelve el siteID para el siteName en el que está creando el grupo. Para más información, vea [Get-CsSite](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsSite) en la documentación de Shell de administración de Lync Server 2013.

3.  Ejecute el siguiente cmdlet:
    
        New-CsTrustedApplicationPool -Identity <E14 CAS FQDN> -ThrottleAsServer $true -TreatAsAuthenticated $true -ComputerFQDN <E14 CAS FQDN> -Site <Site> -Registrar <Pool FQDN in the site> -RequiresReplication $false
    
    Para más información, vea [New-CsTrustedApplicationPool](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsTrustedApplicationPool) en la documentación de Shell de administración de Lync Server 2013.
    
    El FQDN de Exchange Server debe configurarse como el nombre alternativo del sujeto (SAN) o el nombre de sujeto (SN) del certificado de Exchange OWA.
    
    En Exchange OWA, compruebe que el FQDN del grupo también es de confianza.
    
    > [!IMPORTANT]  
    > Si su servidor CAS <em>no</em> está combinado en el mismo servidor que ejecuta la mensajería unificada de Exchange 2013, omita los pasos restantes en este procedimiento y realice el procedimiento “Crear una aplicación de confianza para el servidor CAS de Exchange 2013” más adelante en este tema. Si el servidor CAS está combinado en el mismo servidor que ejecuta la mensajería unificada de Exchange 2013, complete los pasos de este procedimiento y no siga el procedimiento “Crear una aplicación de confianza para el servidor CAS de Exchange 2013” más adelante en este tema.
    


4.  Ejecute **Enable-CsTopology**.

5.  Abra el Generador de topologías y descargue la topología existente.

6.  En el panel izquierdo, expanda el árbol hasta llegar a **Servidores de aplicaciones de confianza**.

7.  Expanda el nodo **Servidores de aplicaciones de confianza**.

8.  Debería ver ahora el servidor CAS de Exchange 2013 mostrado como una aplicación de confianza.

## Para crear una aplicación de confianza para el servidor CAS de Exchange 2013

1.  Inicie la Shell de administración de Lync Server 2013.

2.  Si su servidor CAS *no* está combinado en el mismo servidor que está ejecutando la mensajería unificada de Exchange 2013, ejecute el siguiente cmdlet:
    
        New-CsTrustedApplication -ApplicationId <AppID String> -TrustedApplicationPoolFqdn <E14 CAS FQDN> -Port <available port number>
    
    Para más información, vea el tema [New-CsTrustedApplication](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsTrustedApplication) en la documentación de Shell de administración de Lync Server 2013.

3.  Ejecute **Enable-CsTopology**.

4.  En el panel izquierdo del Generador de topologías, expanda el árbol hasta llegar a **Servidores de aplicaciones de confianza**.

5.  Expanda el nodo **Servidores de aplicaciones de confianza**.

6.  Debería ver ahora el servidor CAS de Exchange 2013 mostrado como una aplicación de confianza.

