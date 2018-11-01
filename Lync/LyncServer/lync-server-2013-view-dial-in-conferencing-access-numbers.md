---
title: Ver los números de acceso a conferencias de acceso telefónico local
TOCTitle: Ver los números de acceso a conferencias de acceso telefónico local
ms:assetid: 41a7dfb4-0c89-4650-b61b-0e1bf875c62b
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ688037(v=OCS.15)
ms:contentKeyID: 49889058
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Ver los números de acceso a conferencias de acceso telefónico local

 

_**Última modificación del tema:** 2013-02-23_

En Panel de control de Lync Server 2013, proporciona números de acceso telefónico a los usuarios para que puedan unirse una reunión externamente.

## Para ver los números de acceso telefónico

1.  Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y después introduzca la dirección URL de administración para abrir el panel de control de Lync Server. Para más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Abrir las herramientas administrativas de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación de la izquierda, haga clic en **Conferencias** y, a continuación, en **Número de acceso telefónico**.

4.  En la página **Número de acceso telefónico**, haga clic en el número de acceso que desea ver.

5.  En **Editar**, active la casilla **Mostrar detalles...**.

## Visualización de números de acceso telefónico a conferencias con los cmdlets de Lync Server PowerShell

Los números de acceso telefónico a conferencias también pueden verse con Lync Server PowerShell y el cmdlet Get-CsDialInConferencingAccessNumber. Este cmdlet puede ejecutarse desde Shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell. Para más información sobre el uso de una conexión remota de Windows PowerShell a Lync Server, consulte el artículo del blog sobre Windows PowerShell de Lync Server "Inicio rápido: Administración de Microsoft Lync Server 2010 con PowerShell remoto" en [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## Visualización de información de configuración de tronco SIP

  - Para ver información sobre todos los números de acceso telefónico a conferencias, escriba el siguiente comando en Shell de administración de Lync Server y luego presione ENTRAR:
    
        Get-CsDialInConferencingAccessNumber
    
    Eso devolverá información similar a esta:
    
        Identity           : CN={20ca8dc8-5ff8-41f4-b5bb-22ba9972ae2e},
                             CN=Application Contacts,CN=RTCService=Services,
                             CN=Configuration,DC=litwareinc,DC=com
        PrimaryUri         : sip:testnumber@litwareinc.com
        DisplayName        : Test
        DisplayNumber      : 1-425-555-1019
        LineUri            : tel:+14255551019
        PrimaryLanguage    : en-US
        SecondaryLanguages : {}
        Pool               : atl-cs-001.litwareinc.com
        HostingProvider    :
        Regions            : {US}

Para más información, vea el tema de ayuda del cmdlet [Get-CsDialInConferencingAccessNumber](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsDialInConferencingAccessNumber).

