---
title: 'Lync Server 2013: eliminar un objeto de contacto telefónico de área común'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete a common area phone Contact object
ms:assetid: f4c139dc-f07c-4c75-9345-e291aea41173
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994087(v=OCS.15)
ms:contentKeyID: 51803999
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2a3088150c882a5ebca99318f7c85ddbddddc333
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741020"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-a-common-area-phone-contact-object-in-lync-server-2013"></a>Eliminar un objeto de contacto telefónico de área común en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-20_

Es posible que desee eliminar el objeto de contacto asociado a un teléfono de área común. Por ejemplo, si quitas el teléfono de la sala de un empleado, no es necesario que tengas un objeto de contacto asociado con ese teléfono. El cmdlet **Remove-CsCommonAreaPhone** le permite eliminar cuentas de teléfono de área común. Al ejecutar este cmdlet, el teléfono se elimina de la lista de teléfonos de área común devuelto por **Get-CsCommonAreaPhone**. Además, el objeto de contacto asociado con ese teléfono se eliminará de los servicios de dominio de Active Directory.

Usa **Remove-CsCommonAreaPhone** para quitar un teléfono de área común o todos los teléfonos de área común que tengan un elemento común, como un nombre para mostrar o un código de área y país. Puede ejecutar este cmdlet desde el shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell. Para obtener más información sobre cómo usar Windows PowerShell remoto para conectarse a Lync Server, consulte el artículo del blog de Lync Server de Windows PowerShell "Inicio rápido: administrar Microsoft Lync Server [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)2010 mediante PowerShell remoto" en.

<div>


<div>

## <a name="removing-a-specified-common-area-phone"></a>Quitar un teléfono de área común especificado

  - El siguiente comando quita el teléfono de área común con la dirección SIP sip:mainlobby@litwareinc.com:
    
        Remove-CsCommonAreaPhone -Identity "sip:mainlobby@litwareinc.com"

</div>

<div>

## <a name="removing-common-area-phones-based-on-their-display-name"></a>Quitar teléfonos de área común en función de su nombre para mostrar

  - Este comando quita todos los teléfonos comunes del área donde el nombre para mostrar incluye el valor de cadena "edificio 14":
    
        Get-CsCommonAreaPhone | Where-Object {$_.DisplayName -match "Building 14"} | Remove-CsCommonAreaPhone

</div>

<div>

## <a name="removing-common-area-phones-based-on-their-country-and-area-codes"></a>Quitar teléfonos de área comunes en función de sus códigos de área y país

  - Este comando elimina todos los teléfonos comunes de las áreas de los Estados Unidos (código de país 1) y el código de área 425:
    
        Get-CsCommonAreaPhone | Where-Object {$_.LineUri  -match "^tel:\+1425"} | Remove-CsCommonAreaPhone

</div>

Para obtener más información, vea el tema de ayuda sobre el cmdlet [Remove-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/Remove-CsCommonAreaPhone) .

</div>

<div>

## <a name="see-also"></a>Vea también


[Get-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/Get-CsCommonAreaPhone)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

