---
title: Crear o modificar un intervalo de números de recogida de llamadas de grupo en Skype Empresarial
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 4b442b98-df6b-4e50-8254-b3be9cde21dd
description: Cree o modifique un intervalo de números de recogida de llamadas de grupo en Skype Empresarial Server Telefonía IP empresarial.
ms.openlocfilehash: 73c2c0b74c27fd59d94d97c5ee05e0da88219601e839d42dc12e0ec659db0aa3
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54307881"
---
# <a name="create-or-modify-a-group-call-pickup-number-range-in-skype-for-business"></a>Crear o modificar un intervalo de números de recogida de llamadas de grupo en Skype Empresarial

Cree o modifique un intervalo de números de recogida de llamadas de grupo en Skype Empresarial Server Telefonía IP empresarial.

La recogida de llamadas en grupo se basa en la aplicación Estacionamiento de llamadas. Al implementar la recogida de llamadas de grupo, debe configurar la tabla de órbitas de estacionamiento de llamadas con intervalos de números de teléfono designados como números de grupo de recogida de llamadas. Estos números de grupo son los números que los usuarios marcan para recoger las llamadas que están sonando para otro usuario.

Al igual que los números de órbita de estacionamiento de llamadas, los números de grupo de recogida de llamadas deben ser extensiones virtuales que no tienen ningún usuario o teléfono asignado. Cada grupo de servidores front-end donde implemente la recogida de llamadas de grupo puede tener uno o más intervalos de números de grupo de recogida de llamadas. Los intervalos de números de grupo deben ser únicos globalmente en la implementación y deben asignarse como el **tipo GroupPickup.**

Use el siguiente procedimiento para crear o modificar un intervalo de números de grupo de recogida de llamadas en la tabla de órbitas de estacionamiento de llamadas.

> [!NOTE]
> Debe usar el Shell Skype Empresarial Server administración para crear, modificar, quitar y ver intervalos de números de recogida de llamadas de grupo en la tabla de órbitas de estacionamiento de llamadas. Los intervalos de números de recogida de llamadas de grupo no están disponibles en Skype Empresarial Server Panel de control.

Los intervalos de números de grupo de recogida de llamadas deben cumplir las siguientes reglas:

- El número inicial del intervalo debe ser menor o igual al número final del intervalo.

- El valor del número inicial del intervalo debe tener la misma longitud que el número final del intervalo.

- El intervalo numérico debe ser único. Este intervalo no se puede superponer con ningún otro.

- Si el intervalo de números comienza con el carácter \* o #, el intervalo debe ser mayor que 100.

- Valores válidos: debe coincidir con la cadena de expresión regular ([ \\ *|#]?[ 1-9]\d {0,7} )| ([1-9]\d {0,8} ). Esto significa que el valor debe ser una cadena que comienza con el carácter o # o un número \* del 1 al 9 (el primer carácter no puede ser cero). Si el primer carácter es o #, el siguiente carácter debe ser un número del 1 al \* 9 (no puede ser cero). Los caracteres posteriores pueden ser cualquier número de 0 a 9 hasta siete caracteres adicionales (por ejemplo, "#6000", " \* 92000", " 95551212" y \* "915551212"). Si el primer carácter no es o #, el primer carácter debe ser un número del 1 al 9 (no puede ser cero), seguido de hasta ocho caracteres, cada uno de \* 0 a 9 (por ejemplo, "915551212", "41212", "300").

### <a name="to-create-or-modify-a-call-pickup-group-range"></a>Para crear o modificar un intervalo de grupos de recogida de llamadas

1. Inicie sesión en el equipo donde Skype Empresarial Server Shell de administración está instalado como miembro del grupo RTCUniversalServerAdmins o con los derechos de usuario necesarios, tal como se describe en **Delegate Setup Permissions**.

2. Inicie el Shell Skype Empresarial Server administración: haga clic en Inicio **,** todos los programas **,** haga clic en **Skype Empresarial 2015** y, a continuación, haga clic **Skype Empresarial Server Shell de administración**.

3. Use **New-CsCallParkOrbit para** crear un nuevo intervalo de números de grupo de recogida de llamadas. Use **Set-CsCallParkOrbit para** modificar un intervalo existente de números de recogida de llamadas.

    En la línea de comandos, ejecute:

   ```powershell
   New-CsCallParkOrbit -Identity <name of call pickup group range> -NumberRangeStart <first number in range> -NumberRangeEnd <last number in range> -CallParkService <FQDN or service ID of the Application service that hosts the Call Park application> -Type GroupPickup
   ```

    Por ejemplo:

   ```powershell
   New-CsCallParkOrbit -Identity "Redmond call pickup" -NumberRangeStart 100 -NumberRangeEnd 199 -CallParkService redmond-applicationserver-1 -Type GroupPickup
   ```

    En el ejemplo siguiente se muestra cómo cambiar un intervalo de números de órbitas de estacionamiento de llamadas a grupos de recogida de llamadas.

   ```powershell
   Set-CsCallParkOrbit -Identity "Redmond call pickup" -Type GroupPickup
   ```

    > [!IMPORTANT]
    > Use este cmdlet para cambiar el tipo asignado a intervalos de números solo si inicialmente especificó el tipo incorrecto y el intervalo de grupos aún no está en uso. Si cambia el intervalo de números de CallPark a GroupPickup o viceversa y el intervalo de números ya está en uso, el estacionamiento de llamadas o la recogida de llamadas de grupo dejarán de funcionar para ese intervalo de números. Por ejemplo, si cambia un intervalo de números de CallPark a GroupPick, la aplicación estacionamiento de llamadas ya no puede usar ese rango de órbitas para estacionar llamadas.

## <a name="see-also"></a>Consulte también

[New-CsCallParkOrbit](/powershell/module/skype/new-cscallparkorbit?view=skype-ps)

[Set-CsCallParkOrbit](/powershell/module/skype/set-cscallparkorbit?view=skype-ps)

[Eliminar un intervalo de órbitas para estacionamiento de llamadas](/previous-versions/office/lync-server-2013/lync-server-2013-delete-a-call-park-orbit-range)