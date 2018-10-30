---
title: Mover objetos de contacto de la mensajería unificada de Exchange
TOCTitle: Mover objetos de contacto de la mensajería unificada de Exchange
ms:assetid: 35c7e987-41b5-4798-b617-3303f20e52e3
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ688022(v=OCS.15)
ms:contentKeyID: 49889043
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Mover objetos de contacto de la mensajería unificada de Exchange

 

_**Última modificación del tema:** 2012-10-19_

Para migrar los objetos de contacto del Operador automático (AA) y de Acceso de suscriptor (SA) a la nueva implementación de Lync Server 2013, mueva primero los objetos de la implementación de Office Communications Server 2007 R2 heredada a la nueva implementación de Lync Server 2013 mediante los cmdlets de **Get-CsExUmContact** y **Move-CsExUmContact**. En Exchange Server, debe ejecutar luego el script **ExchUCUtil**Windows PowerShell para hacer lo siguiente para el grupo de servidores de Lync recién implementado:

  - Agregarlo a las puertas de enlace de IP de mensajería unificada.

  - Agregarlo a los grupos de búsqueda de Mensajería unificada.


> [!NOTE]
> Para usar los cmdlets <STRONG>Get-CsExUmContact</STRONG> y <STRONG>Move-CsExUmContact</STRONG>, debe pertenecer al grupo RTCUniversalUserAdmins y tener permiso de unidad organizativa (OU) en la OU en donde se almacenan los objetos de contacto. El permiso de OU se puede conceder con el cmdlet <STRONG>Grant-OUPermission</STRONG>.



## Para mover objetos de contacto mediante el Shell de administración de Lync Server

1.  Abra Shell de administración de Lync Server.

2.  Para cada grupo de servidores registrado con Mensajería unificada de Exchange (donde pool1.contoso.net es un grupo de servidores de la implementación de Office Communications Server 2007 R2 y pool2.contoso.net es el grupo de servidores de la implementación de Lync Server 2013), en la línea de comandos, escriba lo siguiente:
    
        Get-CsExUmContact -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsExUmContact -Target pool02.contoso.net
    
    Para comprobar que se mueven los objetos de contacto, ejecute el cmdlet **Get-CsExumContact** y confirme que **RegistrarPool** está señalando ahora al nuevo grupo de servidores.

## Para ejecutar el script ExchUCUtil de Windows PowerShell

1.  Inicie sesión en el servidor de Mensajería unificada de Exchange como usuario con privilegios de administrador de organización de Exchange.

2.  Vaya al script ExchUCUtil de Windows PowerShell.
    
    En Exchange 2007, ExchUCUtil.ps1 se encuentra en: **%Archivos de programa%\\Microsoft\\Exchange Server\\Scripts\\ExchUCUtil.ps1**
    
    En Exchange 2010, ExchUCUtil.ps1 se encuentra en: **%Archivos de programa%\\Microsoft\\Exchange Server\\V14\\Scripts\\ExchUCUtil.ps1**

3.  Si Exchange se implementa en un solo bosque, escriba:
    
        exchucutil.ps1
    
    En el caso de que Exchange se haya implementado en varios bosques, escriba lo siguiente:
    
        exchucutil.ps1 -Forest:" <forest FQDN>"
    
    where *forest FQDN* specifies the forest in which Lync Server 2013 is deployed.
    
    > [!IMPORTANT]  
    > Asegúrese de reiniciar el servicio <strong>Front-end de Lync Server</strong> (rtcsrv.exe) <em>después</em> de ejecutar exchucutil.ps1. De lo contrario, Lync Server 2013 no detectará la Mensajería unificada en la topología.
    

