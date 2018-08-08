---
title: Creación o modificación de un intervalo de números de grupo llamada recogida en Skype para la empresa
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 4b442b98-df6b-4e50-8254-b3be9cde21dd
description: Crear o modificar un intervalo de números de grupo llamada recogida en Skype para Business Server Enterprise Voice.
ms.openlocfilehash: 15906402fe81047f02fc033ba7a051a4169a0f26
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2018
ms.locfileid: "21002456"
---
# <a name="create-or-modify-a-group-call-pickup-number-range-in-skype-for-business"></a>Creación o modificación de un intervalo de números de grupo llamada recogida en Skype para la empresa
 
Crear o modificar un intervalo de números de grupo llamada recogida en Skype para Business Server Enterprise Voice.
  
Recogida de llamadas de grupo se basa en la aplicación de estacionamiento de llamadas. Al implementar recogida de llamadas de grupo, debe configurar la tabla de órbitas de estacionamiento de llamada con intervalos de números de teléfono que se designan como números de llamada de grupo pickup. Estos números de grupo son los números que los usuarios marcan para atender las llamadas que están sonando para otro usuario.
  
Al igual que sucede con los números de órbita de estacionamiento de llamadas, los números de grupo de atención a llamadas deben ser extensiones virtuales que no tengan asignado ningún usuario o teléfono. Cada grupo de servidores Front-End donde implementa recogida de llamadas de grupo puede tener uno o varios intervalos de números de llamada de grupo pickup. Estos intervalos tienen que ser únicos en toda la implementación y deben asignarse como el tipo **GroupPickup**.
  
Use el siguiente procedimiento para crear o modificar un intervalo de números del grupo de atención de llamadas en la tabla de órbitas de estacionamiento de llamadas. 
  
> [!NOTE]
> Debe usar Skype para Shell de administración de servidor empresarial para crear, modificar, quitar y ver los intervalos de números de recogida de llamadas de grupo en la tabla de órbitas de estacionamiento de llamada. Intervalos de números de llamada recogida de grupo no están disponibles en Skype para el Panel de Control de servidor empresarial. 
  
Los intervalos de números del grupo de atención de llamadas deben cumplir con las siguientes reglas:
  
- El número inicial del intervalo debe ser menor o igual al número final.
    
- El valor del número inicial del intervalo debe tener la misma longitud que el número final.
    
- El intervalo de números debe ser único. Este intervalo no se puede superponer a ningún otro.
    
- Si el intervalo numérico comienza con el carácter \* o #, el intervalo debe ser mayor que 100.
    
- Valores válidos: debe coincidir con la cadena de expresión regular ([\\* | #] ? [1-9] \d{0,7}) | (\d [1-9]{0,8}). Esto significa que el valor debe ser una cadena que empieza por puede ser el carácter \* o # o un número del 1 al 9 (el primer carácter no puede ser un cero). Si el primer carácter es \* o #, el carácter siguiente debe ser un número del 1 al 9 (no puede ser cero). Los caracteres siguientes pueden ser cualquier número de 0 a 9 hasta siete caracteres adicionales (por ejemplo, "#6000", "\*92000", "\*95551212" y "915551212"). Si el primer carácter no es \* o #, el primer carácter debe ser un número del 1 al 9 (no puede ser cero), seguido de un máximo de ocho caracteres, cada un número del 0 al 9 (por ejemplo, "915551212", "41212", "300").
    
### <a name="to-create-or-modify-a-call-pickup-group-range"></a>Para crear o modificar un intervalo del grupo de atención de llamadas

1. Inicie sesión en el equipo donde está instalado Skype para Shell de administración de servidor empresarial como un miembro del grupo RTCUniversalServerAdmins o con los derechos de usuario necesarios, tal como se describe en **Delegar permisos de instalación**.
    
2. Inicie el Shell de administración de Skype Empresarial Server: haga clic en **Inicio**, **Todos los programas**, **Skype Empresarial Server 2015** y, después, en **Shell de administración de Skype Empresarial Server**.
    
3. Use **New-CsCallParkOrbit** para crear un nuevo intervalo de números de llamada de grupo pickup. Usar **Set-CsCallParkOrbit** para modificar un intervalo de números de llamada pickup existente.
    
    En la línea de comandos, ejecute:
    
   ```
   New-CsCallParkOrbit -Identity <name of call pickup group range> -NumberRangeStart <first number in range> -NumberRangeEnd <last number in range> -CallParkService <FQDN or service ID of the Application service that hosts the Call Park application> -Type GroupPickup
   ```

    Por ejemplo:
    
   ```
   New-CsCallParkOrbit -Identity "Redmond call pickup" -NumberRangeStart 100 -NumberRangeEnd 199 -CallParkService redmond-applicationserver-1 -Type GroupPickup
   ```

    En el siguiente ejemplo, se muestra cómo modificar un intervalo de números de órbitas de estacionamiento de llamadas a grupos de atención de llamadas.
    
   ```
   Set-CsCallParkOrbit -Identity "Redmond call pickup" -Type GroupPickup
   ```

    > [!IMPORTANT]
    > Use este cmdlet para cambiar el tipo asignado a los intervalos de números únicamente si especificó el tipo incorrecto y el intervalo de números aún no se encuentra en uso. Si cambia el intervalo de números de CallPark a GroupPickup, o viceversa, y este ya se encuentra en uso, el estacionamiento de llamadas o la atención de llamadas grupales dejará de funcionar para ese intervalo de números. Por ejemplo, si cambia un intervalo de números de CallPark a GroupPick, la aplicación de estacionamiento de llamadas ya no puede utilizar ese intervalo de Órbitas para estacionar llamadas. 
  
## <a name="see-also"></a>Vea también

[Nuevo-CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/new-cscallparkorbit?view=skype-ps)
  
[Set-CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/set-cscallparkorbit?view=skype-ps)
  
[Eliminar un intervalo de órbitas de estacionamiento de llamadas](http://technet.microsoft.com/library/85e9f916-062d-450d-ac0a-aeaefc0f7cdc.aspx)