---
title: Eliminar un objeto de contacto de teléfono de área común
TOCTitle: Eliminar un objeto de contacto de teléfono de área común
ms:assetid: f4c139dc-f07c-4c75-9345-e291aea41173
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ994087(v=OCS.15)
ms:contentKeyID: 52061970
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Eliminar un objeto de contacto de teléfono de área común

 

_**Última modificación del tema:** 2013-02-20_

Es posible que quiera eliminar el objeto de contacto asociado con el teléfono de área común. Por ejemplo, si quita el teléfono de una sala de empleados, no es necesario tener un objeto de contacto asociado con dicho teléfono. El cmdlet **Remove-CsCommonAreaPhone** permite eliminar cuentas de teléfonos de área común. Cuando ejecute este cmdlet, el teléfono se eliminará de la lista de teléfonos de área común devueltos por **Get-CsCommonAreaPhone**. Además, el objeto de contacto asociado con el teléfono se eliminará de Servicios de dominio de Active Directory.

Use **Remove-CsCommonAreaPhone** para quitar un teléfono de área común o todos los teléfonos de área común que tienen un elemento en común como, por ejemplo, un nombre para mostrar o un código de área y de país. Ejecute este cmdlet desde Shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell. Para más información sobre el uso de una conexión remota de Windows PowerShell a Lync Server, consulte el artículo del blog sobre Windows PowerShell de Lync Server "Inicio rápido: Administración de Microsoft Lync Server 2010 con PowerShell remoto" en [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).


## Quitar un teléfono de área común especificado

  - El comando siguiente quita el teléfono de área común con la dirección SIP sip:mainlobby@litwareinc.com:
    
        Remove-CsCommonAreaPhone -Identity "sip:mainlobby@litwareinc.com"

## Quitar teléfonos de área común basándose en su nombre para mostrar

  - Este comando quita todos los teléfonos de área común donde el nombre para mostrar contiene el valor de cadena "Building 14":
    
        Get-CsCommonAreaPhone | Where-Object {$_.DisplayName -match "Building 14"} | Remove-CsCommonAreaPhone

## Quitar teléfonos de área común basándose en sus códigos de país o de área

  - Este comando quita todos los teléfonos de área común de los Estados Unidos (código de país 1) y el código de área 425:
    
        Get-CsCommonAreaPhone | Where-Object {$_.LineUri  -match "^tel:\+1425"} | Remove-CsCommonAreaPhone

Para más información, vea el tema de ayuda del cmdlet [Remove-CsCommonAreaPhone](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsCommonAreaPhone).

## Vea también

#### Otros recursos

[Get-CsCommonAreaPhone](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsCommonAreaPhone)

