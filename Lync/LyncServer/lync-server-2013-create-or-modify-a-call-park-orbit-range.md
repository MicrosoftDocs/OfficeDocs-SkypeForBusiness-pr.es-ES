---
title: 'Lync Server 2013: crear o modificar un intervalo de llamada de Parque orbital'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a Call Park orbit range
ms:assetid: 549ec118-eee5-4333-9416-80929ec057e0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398361(v=OCS.15)
ms:contentKeyID: 48184142
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bf215caacd0e380a14429bd2d34791048878fc96
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763382"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-call-park-orbit-range-in-lync-server-2013"></a>Crear o modificar un intervalo orbitar de llamadas en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-11-01_

Use los siguientes procedimientos para crear o modificar un intervalo de órbitas de estacionamiento de llamadas.

<div>

## <a name="to-use-lync-server-control-panel-to-create-or-modify-a-range-of-numbers-for-parking-calls"></a>Para usar el panel de control de Lync Server para crear o modificar un intervalo de números para las llamadas de aparcamiento

1.  Inicie sesión en el equipo como miembro del grupo RTCUniversalServerAdmins o como miembro del rol CsVoiceAdministrator, CsServerAdministrator o CsAdministrator. Para obtener más información, consulte [permisos de configuración de delegación en Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Características de voz** y, a continuación, en **Estacionamiento de llamadas**.

4.  En la página **Estacionamiento de llamadas**, siga uno de estos procedimientos:
    
      - Para crear un nuevo intervalo de órbitas, haga clic en **Nuevo**. En **Nombre**, escriba un nombre identificativo para este intervalo de números.
        
        <div>
        

        > [!NOTE]  
        > Una vez que haya confirmado el intervalo de órbitas para la base de datos, no podrá cambiar este nombre.

        
        </div>
    
      - Para modificar un intervalo de órbitas existente, escriba todo o parte del nombre del intervalo de órbitas en el campo de búsqueda. En la lista de órbitas resultante, haga clic en la órbita que desee, seleccione **Editar** y, a continuación, haga clic en **Mostrar detalles**.

5.  En el primer campo **Intervalo numérico**, escriba el número inicial del intervalo de extensiones para esta órbita de estacionamiento de llamadas y, en el segundo campo **Intervalo numérico**, escriba el número final del intervalo.
    
    <div>
    

    > [!NOTE]  
    > <UL>
    > <LI>
    > <P>El número inicial del intervalo debe ser menor o igual al número final.</P>
    > <LI>
    > <P>El valor del número inicial del intervalo debe tener la misma longitud que el número final.</P>
    > <LI>
    > <P>El intervalo de órbitas debe ser único. Este intervalo no se puede superponer con ningún otro.</P>
    > <LI>
    > <P>Si el intervalo de órbitas comienza con el carácter * o #, el intervalo debe ser mayor de 100.</P>
    > <LI>
    > <P>Valores válidos: deben coincidir con la cadena de\*expresión regular ([| #]? [ 1-9] \d{0,7}) | ([1-9] \d{0,8}). Esto significa que el valor debe ser una cadena que comience por los caracteres * o #, o bien un número del 1 al 9 (el primer carácter no puede ser un cero). Si el primer carácter es * o #, el siguiente debe ser un número del 1 al 9 (no puede ser un cero). Los siguientes caracteres pueden ser del 0 al 9 hasta siete caracteres adicionales (por ejemplo, "#6000", "*92000", "* 95551212" y "915551212"). Si el primer carácter no es * o #, tiene que ser un número entre 1 y 9 (no puede ser cero), seguido de un máximo de ocho caracteres, que deben ser números del 0 al 9 (por ejemplo, "915551212", "41212", "300").</P>
    > <LI>
    > <P>No debe tener más de 50 000 órbitas por grupo de servidores. Cada intervalo de órbitas normalmente está formado por 100 órbitas o menos, pero puede ser mucho mayor siempre que tenga menos de 10 000 órbitas. Por ejemplo, en lugar de especificar un número de inicio de "7000000" y un número de finalización de "8000000", piense en especificar un número de inicio de "7000000" y un número de finalización de "7000100".</P></LI></UL>

    
    </div>

6.  En **FQDN del servidor de destino**, haga clic en el nombre de dominio completo (FQDN) o el identificador de servicio del servicio de aplicación que hospeda la aplicación de estacionamiento de llamadas. Todas las llamadas estacionadas en números del intervalo especificado por el número de inicio y el número de finalización de cada intervalo de órbitas se enrutarán a este servidor o grupo de servidores.

7.  Haga clic en **Confirmar**.

</div>

<div>

## <a name="to-use-windows-powershell-to-create-or-modify-a-range-of-numbers-for-parking-calls"></a>Para usar Windows PowerShell para crear o modificar un intervalo de números para las llamadas de aparcamiento

1.  Inicie sesión en el equipo donde está instalado el shell de administración de Lync Server como miembro del grupo RTCUniversalServerAdmins o con los derechos de usuario necesarios, tal y como se describe en [permisos de configuración de delegado en Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Inicie el shell de administración de Lync Server: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **Shell de administración de Lync Server**.

3.  Use **New-CsCallParkOrbit** para crear un nuevo intervalo de números de órbitas. Use **Set-CsCallParkOrbit** para modificar un intervalo de números de órbitas existente.
    
    En la línea de comandos, ejecute:
    
        New-CsCallParkOrbit -Identity <name of orbit range> -NumberRangeStart <first number in orbit range> -NumberRangeEnd <last number in orbit range> -CallParkService <FQDN or service ID of the Application service that hosts the Call Park application>
    
    Por ejemplo:
    
        New-CsCallParkOrbit -Identity "Redmond orbit 1" -NumberRangeStart 100 -NumberRangeEnd 199 -CallParkService redmond-applicationserver-1
    
    En el ejemplo siguiente se muestra cómo modificar los números de un intervalos de órbitas existente,
    
        Set-CsCallParkOrbit -Identity "Redmond orbit 1" -NumberRangeStart 500 -NumberRangeEnd 699

</div>

<div>

## <a name="see-also"></a>Vea también


[Eliminar un intervalo orbitar de llamadas en Lync Server 2013](lync-server-2013-delete-a-call-park-orbit-range.md)  


[Nuevo: CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/New-CsCallParkOrbit)  
[Set-CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/Set-CsCallParkOrbit)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

