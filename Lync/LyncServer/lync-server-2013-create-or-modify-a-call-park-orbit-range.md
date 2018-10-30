---
title: "Lync Server 2013: Crear/modificar intervalo de órbitas de estacionamiento de llamadas"
TOCTitle: Crear o modificar un intervalo de órbitas de estacionamiento de llamadas
ms:assetid: 549ec118-eee5-4333-9416-80929ec057e0
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398361(v=OCS.15)
ms:contentKeyID: 48275290
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Crear o modificar un intervalo de órbitas de estacionamiento de llamadas en Lync Server 2013

 

_**Última modificación del tema:** 2012-11-01_

Use los siguientes procedimientos para crear o modificar un intervalo de órbitas de estacionamiento de llamadas.

## Para usar Panel de control de Lync Server para crear o modificar un intervalo numérico para estacionar llamadas

1.  Inicie sesión en el equipo como miembro del grupo RTCUniversalServerAdmins o como miembro del rol CsVoiceAdministrator, CsServerAdministrator o CsAdministrator. Para más información, consulte [Delegar permisos de instalación en Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Abra una ventana del explorador y después introduzca la dirección URL de administración para abrir el panel de control de Lync Server. Para más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Abrir las herramientas administrativas de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Características de voz** y, a continuación, en **Estacionamiento de llamadas**.

4.  En la página **Estacionamiento de llamadas**, siga uno de estos procedimientos:
    
      - Para crear un nuevo intervalo de órbitas, haga clic en **Nuevo** . En **Nombre** , escriba un nombre identificativo para este intervalo de números.
        

        > [!NOTE]
        > Una vez haya confirmado el intervalo de órbitas para la base de datos, no podrá cambiar este nombre.

    
      - Para modificar un intervalo de órbitas existente, escriba todo o parte del nombre del intervalo de órbitas en el campo de búsqueda. En la lista de órbitas resultante, haga clic en la órbita que desee, seleccione **Editar** y, a continuación, haga clic en **Mostrar detalles** .

5.  En el primer campo **Intervalo numérico** , escriba el número inicial del intervalo de extensiones para esta órbita de estacionamiento de llamadas y en el segundo campo **Intervalo numérico** , escriba el número final del intervalo.
    

    > [!NOTE]
    > <UL>
    > <LI>
    > <P>El número inicial del intervalo debe ser menor o igual al número final del intervalo.</P>
    > <LI>
    > <P>El valor del número inicial del intervalo debe tener la misma longitud que el número final del intervalo.</P>
    > <LI>
    > <P>El intervalo de órbitas debe ser único. Este intervalo no se puede superponer con ningún otro.</P>
    > <LI>
    > <P>Si el intervalo de órbitas comienza con el carácter * o #, el intervalo debe ser mayor de 100.</P>
    > <LI>
    > <P>Valores válidos: Deben tener el mismo formato que la cadena de caracteres de la expresión regular ([\*|#]?[1-9]\d{0,7})|([1-9]\d{0,8}). Esto significa que el valor debe ser una cadena que comience con el carácter * o #, o un número del 1 al 9 (el primer carácter no puede ser un cero). Si el primer carácter es * o #, el siguiente debe ser un número del 1 al 9 (no puede ser un cero). Los siguientes caracteres pueden ser cualquier número del 0 al 9, hasta un máximo de siete caracteres adicionales (por ejemplo, "#6000", "*92000", "*95551212" y "915551212"). Si el primer carácter no es * o #, tiene que ser un número entre 1 y 9 (no puede ser cero), seguido de un máximo de ocho caracteres, que deben ser números del 0 al 9 (por ejemplo, "915551212", "41212", "300").</P>
    > <LI>
    > <P>No debe tener más de 50.000 órbitas por grupo de servidores. Cada intervalo de órbitas normalmente está formado por 100 órbitas o menos, pero puede ser mucho mayor siempre que tenga menos de 10.000 órbitas. Por ejemplo, en lugar de especificar un número de inicio de "7000000" y un número de finalización de "8000000", piense en especificar un número de inicio de "7000000" y un número de finalización de "7000100".</P></LI></UL>



6.  En **FQDN del servidor de destino** , haga clic en el nombre de dominio completo (FQDN) o ID de servicio del servicio de aplicación que aloja la Aplicación de estacionamiento de llamadas. Todas las llamadas estacionadas en números del intervalo especificado por el número de inicio y el número de finalización de cada intervalo de órbitas se enrutarán a este servidor o grupo de servidores.

7.  Haga clic en **Confirmar**.

## Para usar Windows PowerShell para crear o modificar un intervalo numérico para estacionar llamadas

1.  Inicie sesión en un equipo que tenga instalado el Shell de administración de Lync Server como miembro del grupo RTCUniversalServerAdmins o con los derechos de usuario necesarios que se describen en [Delegar permisos de instalación en Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y, después, en **Shell de administración de Lync Server**.

3.  Use **New-CsCallParkOrbit** para crear un nuevo intervalo de números de órbitas. Use **Set-CsCallParkOrbit** para modificar un intervalo de números de órbitas existente.
    
    En la línea de comandos, ejecute:
    
        New-CsCallParkOrbit -Identity <name of orbit range> -NumberRangeStart <first number in orbit range> -NumberRangeEnd <last number in orbit range> -CallParkService <FQDN or service ID of the Application service that hosts the Call Park application>
    
    Por ejemplo:
    
        New-CsCallParkOrbit -Identity "Redmond orbit 1" -NumberRangeStart 100 -NumberRangeEnd 199 -CallParkService redmond-applicationserver-1
    
    En el ejemplo siguiente se muestra cómo modificar los números de un intervalos de órbitas existente,
    
        Set-CsCallParkOrbit -Identity "Redmond orbit 1" -NumberRangeStart 500 -NumberRangeEnd 699

## Vea también

#### Tareas

[Eliminar un intervalo de órbitas para estacionamiento de llamadas en Lync Server 2013](lync-server-2013-delete-a-call-park-orbit-range.md)  

#### Otros recursos

[New-CsCallParkOrbit](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsCallParkOrbit)  
[Set-CsCallParkOrbit](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsCallParkOrbit)

