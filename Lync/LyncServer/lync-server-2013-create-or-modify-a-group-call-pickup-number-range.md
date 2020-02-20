---
title: 'Lync Server 2013: crear o modificar un intervalo de números de llamada de llamada de grupo'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a Group Call Pickup number range
ms:assetid: 4b442b98-df6b-4e50-8254-b3be9cde21dd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945627(v=OCS.15)
ms:contentKeyID: 51541472
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d215fe6959b169ec5f092757174d105a75a5402a
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145529"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-group-call-pickup-number-range-in-lync-server-2013"></a>Crear o modificar un intervalo de números de atención de llamadas grupales en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-01-30_

Use el siguiente procedimiento para crear o modificar un intervalo de números del grupo de atención de llamadas en la tabla de órbitas de estacionamiento de llamadas.

<div>


> [!NOTE]  
> Debe usar el shell de administración de Lync Server para crear, modificar, quitar y ver intervalos de números de llamada de llamadas de grupo en la tabla de órbitas de estacionamiento de llamadas. Los intervalos de números de llamada de grupo no están disponibles en el panel de control de Lync Server.



</div>

<div>


> [!IMPORTANT]  
> El intervalo de números del grupo de atención a llamadas debe asignarse a un tipo de GroupPickup. Los usuarios solo están habilitados para la recogida de llamadas de grupo si el número de grupo al que se asignan es de tipo GroupPickup.



</div>

Los intervalos de números del grupo de recogida de llamadas deben cumplir con las siguientes reglas:

  - El número inicial del intervalo debe ser menor o igual al número final del intervalo.

  - El valor del número inicial del intervalo debe tener la misma longitud que el número final del intervalo.

  - El intervalo numérico debe ser único. Este intervalo no se puede superponer con ningún otro.

  - Si el intervalo de números comienza por el \* carácter \#o, el intervalo debe ser mayor que 100.

  - Valores válidos: deben coincidir con la cadena\[\\\*|\#\]de\[ expresión regular (? 1-9\]\\d{0,7}) | (\[1-9\]\\d{0,8}). Esto significa que el valor debe ser una cadena que comience por el \* carácter \# o o un número del 1 al 9 (el primer carácter no puede ser un cero). Si el primer carácter es \* o \#, el siguiente carácter debe ser un número del 1 al 9 (no puede ser un cero). Los siguientes caracteres pueden ser cualquier número del 0 al 9, hasta un máximo de siete caracteres adicionales\#(por ejemplo,\*"6000",\*"92000", "95551212" y "915551212"). Si el primer carácter no \* es o \#, el primer carácter debe ser un número del 1 al 9 (no puede ser cero), seguido de hasta ocho caracteres, cada uno de los números del 0 al 9 (por ejemplo, "915551212", "41212", "300").

<div>

## <a name="to-create-or-modify-a-call-pickup-group-range"></a>Para crear o modificar un intervalo de grupo de recogida de llamadas

1.  Inicie sesión en el equipo donde esté instalado el shell de administración de Lync Server como miembro del grupo RTCUniversalServerAdmins o con los derechos de usuario necesarios, tal y como se describe en [Delegate Setup Permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.

3.  Use **New-CsCallParkOrbit** para crear un nuevo intervalo de números de grupo de recogida de llamadas. Use **set-CsCallParkOrbit** para modificar un intervalo existente de números de atención de llamadas.
    
    En la línea de comandos, ejecute:
    
        New-CsCallParkOrbit -Identity <name of call pickup group range> -NumberRangeStart <first number in range> -NumberRangeEnd <last number in range> -CallParkService <FQDN or service ID of the Application service that hosts the Call Park application> -Type GroupPickup
    
    Por ejemplo:
    
        New-CsCallParkOrbit -Identity "Redmond call pickup" -NumberRangeStart 100 -NumberRangeEnd 199 -CallParkService redmond-applicationserver-1 -Type GroupPickup
    
    En el ejemplo siguiente se muestra cómo cambiar un intervalo de números de las órbitas de estacionamiento de llamadas a grupos de RECALL.
    
        Set-CsCallParkOrbit -Identity "Redmond call pickup" -Type GroupPickup
    
    <div>
    

    > [!IMPORTANT]  
    > Use este cmdlet para cambiar el tipo asignado a los intervalos de números solo si especificó inicialmente el tipo incorrecto y el intervalo de grupo todavía no está en uso. Si cambia el intervalo de números de CallPark a GroupPickup o viceversa y el intervalo de números ya está en uso, ya no podrá trabajar para ese intervalo de llamadas. Por ejemplo, si cambia un intervalo de números de CallPark a GroupPick, la aplicación estacionamiento de llamadas ya no podrá usar ese intervalo de órbitas para estacionar llamadas.

    
    </div>

</div>

<div>

## <a name="see-also"></a>Vea también


[Eliminar un intervalo de órbitas de estacionamiento de llamadas en Lync Server 2013](lync-server-2013-delete-a-call-park-orbit-range.md)  


[New-CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/New-CsCallParkOrbit)  
[Set-CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/Set-CsCallParkOrbit)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

