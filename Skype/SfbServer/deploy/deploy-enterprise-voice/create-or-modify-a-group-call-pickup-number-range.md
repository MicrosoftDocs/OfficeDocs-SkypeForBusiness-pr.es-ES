---
title: Crear o modificar un intervalo de números de recogida de llamadas grupales en Skype empresarial
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 4b442b98-df6b-4e50-8254-b3be9cde21dd
description: Crear o modificar un intervalo de números de recogida de llamadas grupales en la telefonía IP empresarial de Skype empresarial Server.
ms.openlocfilehash: 3098d7cf1554586dd2fd2ace934682ae58a90489
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/07/2019
ms.locfileid: "36233471"
---
# <a name="create-or-modify-a-group-call-pickup-number-range-in-skype-for-business"></a>Crear o modificar un intervalo de números de recogida de llamadas grupales en Skype empresarial

Crear o modificar un intervalo de números de recogida de llamadas grupales en la telefonía IP empresarial de Skype empresarial Server.

La recogida de llamadas grupales se basa en la aplicación de estacionamiento de llamadas. Cuando implemente la recogida de llamadas grupales, debe configurar la tabla Parque de llamadas en órbita con los rangos de números de teléfono que se designan como números de grupo de recogida de llamadas. Estos números de grupo son los números que los usuarios marcan para atender las llamadas que están sonando para otro usuario.

Al igual que sucede con los números de órbita de estacionamiento de llamadas, los números de grupo de atención a llamadas deben ser extensiones virtuales que no tengan asignado ningún usuario o teléfono. Cada grupo de servidores front-end en el que se implementa la recogida de llamadas grupales puede tener uno o más intervalos de números de grupo de recogida de llamadas. Estos intervalos tienen que ser únicos en toda la implementación y deben asignarse como el tipo **GroupPickup**.

Use el siguiente procedimiento para crear o modificar un intervalo de números del grupo de atención de llamadas en la tabla de órbitas de estacionamiento de llamadas.

> [!NOTE]
> Debe usar el shell de administración de Skype empresarial Server para crear, modificar, quitar y ver rangos de números de recogida de llamadas grupales en la tabla de llamadas en órbita. Los intervalos de números de recogida de llamadas grupales no están disponibles en el panel de control de Skype empresarial Server.

Los intervalos de números del grupo de atención de llamadas deben cumplir con las siguientes reglas:

- El número inicial del intervalo debe ser menor o igual al número final.

- El valor del número inicial del intervalo debe tener la misma longitud que el número final.

- El intervalo de números debe ser único. Este intervalo no se puede superponer a ningún otro.

- Si el intervalo de números comienza con el \* carácter o #, el intervalo debe ser mayor que 100.

- Valores válidos: deben coincidir con la cadena de\\expresión regular ([* | #]? [ 1-9] \d{0,7}) | ([1-9] \d{0,8}). Esto significa que el valor debe ser una cadena que comienza con el \* carácter o # o un número 1 a 9 (el primer carácter no puede ser un cero). Si el primer carácter es \* o #, el siguiente carácter debe ser un número del 1 al 9 (no puede ser un cero). Los siguientes caracteres pueden ser del 0 al 9 hasta siete caracteres adicionales (por ejemplo, "#6000", "\*92000", "\*95551212" y "915551212"). Si el primer carácter no \* es o #, el primer carácter debe ser un número del 1 al 9 (no puede ser cero), seguido de hasta ocho caracteres, cada uno de los números del 0 al 9 (por ejemplo, "915551212", "41212", "300").

### <a name="to-create-or-modify-a-call-pickup-group-range"></a>Para crear o modificar un intervalo del grupo de atención de llamadas

1. Inicie sesión en el equipo donde está instalado el shell de administración de Skype empresarial Server como miembro del grupo RTCUniversalServerAdmins o con los derechos de usuario necesarios, como se describe en **permisos de configuración de delegado**.

2. Inicie el Shell de administración de Skype Empresarial Server: haga clic en **Inicio**, **Todos los programas**, **Skype Empresarial Server 2015** y, después, en **Shell de administración de Skype Empresarial Server**.

3. Use **New-CsCallParkOrbit** para crear un nuevo intervalo de números del grupo de atención de llamadas. Use **Set-CsCallParkOrbit** para modificar un intervalo de números del grupo de atención de llamadas existente.

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
    > Use este cmdlet para cambiar el tipo asignado a los intervalos de números únicamente si especificó el tipo incorrecto y el intervalo de números aún no se encuentra en uso. Si cambia el intervalo de números de CallPark a GroupPickup, o viceversa, y este ya se encuentra en uso, el estacionamiento de llamadas o la atención de llamadas grupales dejará de funcionar para ese intervalo de números. Por ejemplo, si cambia un intervalo de números de CallPark a GroupPick, la aplicación estacionamiento de llamadas ya no podrá usar ese rango de órbitas para detener llamadas.

## <a name="see-also"></a>Vea también

[Nuevo: CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/new-cscallparkorbit?view=skype-ps)

[Set-CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/set-cscallparkorbit?view=skype-ps)

[Eliminar un intervalo orbitar de llamada](https://technet.microsoft.com/library/85e9f916-062d-450d-ac0a-aeaefc0f7cdc.aspx)
