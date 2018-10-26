---
title: Crear o modificar un intervalo numérico de respuesta de llamadas en grupo
TOCTitle: Crear o modificar un intervalo numérico de respuesta de llamadas en grupo
ms:assetid: 4b442b98-df6b-4e50-8254-b3be9cde21dd
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ945627(v=OCS.15)
ms:contentKeyID: 52061682
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Crear o modificar un intervalo numérico de respuesta de llamadas en grupo

 

_**Última modificación del tema:** 2013-01-30_

Use el siguiente procedimiento para crear o modificar un intervalo de números del grupo de atención de llamadas en la tabla de órbitas de estacionamiento de llamadas.


> [!NOTE]
> Debe usar Shell de administración de Lync Server para crear, modificar, quitar y ver intervalos de números de atención de llamadas grupales en la tabla de órbitas de estacionamiento de llamadas. Los intervalos de números de atención de llamadas grupales no están disponibles en Panel de control de Lync Server.



> [!IMPORTANT]  
> Al intervalo de números del grupo de atención de llamadas se le debe asignar el tipo GroupPickup. Los usuarios solo se habilitan para la atención de llamadas grupales si el número del grupo que tienen asignado es de tipo GroupPickup.



Los intervalos de números del grupo de atención de llamadas deben cumplir con las siguientes reglas:

  - El número inicial del intervalo debe ser menor o igual al número final del intervalo.

  - El valor del número inicial del intervalo debe tener la misma longitud que el número final del intervalo.

  - El intervalo de números debe ser único. Este intervalo no se puede superponer con ningún otro.

  - Si el intervalo de números comienza con el carácter \* o \#, debe ser mayor que 100.

  - Valores válidos: Deben tener el mismo formato que la cadena de caracteres de la expresión regular (\[\\\*|\#\]?\[1-9\]\\d{0,7})|(\[1-9\]\\d{0,8}). Esto significa que el valor debe ser una cadena que comience con el carácter \* o \#, o con un número del 1 al 9 (el primer carácter no puede ser cero). Si el primer carácter es \* o \#, el siguiente debe ser un número del 1 al 9 (no puede ser cero). Los siguientes caracteres pueden ser cualquier número del 0 al 9, hasta un máximo de siete caracteres adicionales (por ejemplo, "\#6000", "\*92000", "\*95551212" y "915551212"). Si el primer carácter no es \* o \#, tiene que ser un número entre 1 y 9 (no puede ser cero), seguido de un máximo de ocho caracteres, que deben ser números del 0 al 9 (por ejemplo, "915551212", "41212", "300").

## Para crear o modificar un intervalo del grupo de atención de llamadas

1.  Inicie sesión en un equipo que tenga instalado el Shell de administración de Lync Server como miembro del grupo RTCUniversalServerAdmins o con los derechos de usuario necesarios que se describen en [Delegar permisos de instalación en Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y, después, en **Shell de administración de Lync Server**.

3.  Use **New-CsCallParkOrbit** para crear un nuevo intervalo de números del grupo de atención de llamadas. Use **Set-CsCallParkOrbit** para modificar un intervalo de números del grupo de atención de llamadas existente.
    
    En la línea de comandos, ejecute:
    
        New-CsCallParkOrbit -Identity <name of call pickup group range> -NumberRangeStart <first number in range> -NumberRangeEnd <last number in range> -CallParkService <FQDN or service ID of the Application service that hosts the Call Park application> -Type GroupPickup
    
    Por ejemplo:
    
        New-CsCallParkOrbit -Identity "Redmond call pickup" -NumberRangeStart 100 -NumberRangeEnd 199 -CallParkService redmond-applicationserver-1 -Type GroupPickup
    
    En el siguiente ejemplo, se muestra cómo modificar un intervalo de números de órbitas de estacionamiento de llamadas a grupos de atención de llamadas.
    
        Set-CsCallParkOrbit -Identity "Redmond call pickup" -Type GroupPickup
    
    > [!IMPORTANT]  
    > Use este cmdlet para modificar el tipo asignado a los intervalos de números únicamente si especificó el tipo incorrecto y el intervalo de números aún no se encuentra en uso. Si cambia el intervalo de números de CallPark a GroupPickup, o viceversa, y este ya se encuentra en uso, el estacionamiento de llamadas o la atención de llamadas grupales dejarán de funcionar para ese intervalo de números. Por ejemplo, si cambia un intervalo de números de CallPark a GroupPick, el Aplicación de estacionamiento de llamadas ya no podrá usar ese intervalo de órbitas para estacionar llamadas.
    


## Vea también

#### Tareas

[Eliminar un intervalo de órbitas para estacionamiento de llamadas en Lync Server 2013](lync-server-2013-delete-a-call-park-orbit-range.md)  

#### Otros recursos

[New-CsCallParkOrbit](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsCallParkOrbit)  
[Set-CsCallParkOrbit](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsCallParkOrbit)

