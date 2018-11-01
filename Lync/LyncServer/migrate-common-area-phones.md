---
title: Migrar teléfonos de área común
TOCTitle: Migrar teléfonos de área común
ms:assetid: 31bd26fc-861b-45c6-8221-18df16e575de
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ688015(v=OCS.15)
ms:contentKeyID: 49889032
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Migrar teléfonos de área común

 

_**Última modificación del tema:** 2012-09-29_

Los teléfonos de área común son teléfonos IP que a menudo se encuentran en un espacio de trabajo compartido o un área común, como una sala de espera, cocina o una fábrica. Los teléfonos de área común no se tienen que conectar a un equipo para proporcionar funcionalidad UC de Lync Server. Tras migrar una implementación de Lync Server 2010 a Lync Server 2013, también debe migrar los objetos de contacto asociados con el teléfono de área común. Mediante Shell de administración de Lync Server recuperará primero todos los objetos de contacto asociados con los teléfonos de área común de Lync Server 2010 y, a continuación, moverá esos objetos al grupo de servidores de Lync Server 2013.

**Migrar teléfonos de área común**

1.  Desde el servidor front-end de Lync Server 2013, abra Shell de administración de Lync Server.

2.  En la línea de comandos, escriba lo siguiente:
    
        Get-CsCommonAreaPhone -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsCommonAreaPhone -Target pool02.contoso.net

3.  Para comprobar que todos los objetos de contacto se han movido al grupo de usuarios de Lync Server 2013, desde el Shell de administración de Lync Server escriba lo siguiente:
    
        Get-CsCommonAreaPhone -Filter {RegistrarPool -eq "pool02.contoso.net"}
    
    Compruebe que todos los objetos de contacto están asociados ahora al grupo de servidores de Lync Server 2013.

