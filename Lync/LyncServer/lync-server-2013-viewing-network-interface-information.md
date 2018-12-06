---
title: Visualización de información de interfaz de red
TOCTitle: Visualización de información de interfaz de red
ms:assetid: e7dbb1ec-62b3-48be-a419-c493df5740e6
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ721916(v=OCS.15)
ms:contentKeyID: 49889775
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Visualización de información de interfaz de red

 

_**Última modificación del tema:** 2013-02-23_

## Visualizar la información de la interfaz de red con los cmdlets de Shell de administración de Lync Server

Vea la información de interfaz de red con el Shell de administración de Lync Server y el cmdlet **Get-CsNetworkInterface**. Ejecute este cmdlet desde el Shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell. Para más información sobre el uso de una conexión remota de Windows PowerShell a Lync Server, consulte el artículo del blog sobre Windows PowerShell de Lync Server "Inicio rápido: Administración de Microsoft Lync Server 2010 con PowerShell remoto" en [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## Para ver la información de interfaz de red

  - Para ver la información de interfaz de red, escriba el comando siguiente en el Shell de administración de Lync Server y presione ENTRAR:
    
        Get-CsNetworkInterface
    
    Este comando produce información similar a la siguiente para cada interfaz de red:
    
        Identity              : dc.vdomain.com/Primary/1
        ComputerFqdn          : dc.vdomain.com
        IPAddress             : 0.0.0.0
        IPv6Address           :
        Interface             : Primary
        InterfaceNumber       : 1
        ConfiguredFqdn        :
        ConfiguredIPAddress   :
        ConfiguredIPv6Address :

Para más información, vea [Get-CsNetworkInterface](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsNetworkInterface).

