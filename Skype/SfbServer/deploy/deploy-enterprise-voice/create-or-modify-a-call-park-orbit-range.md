---
title: Crear o modificar un intervalo de llamada de Parque orbital en Skype empresarial
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
ms.assetid: 549ec118-eee5-4333-9416-80929ec057e0
description: Crear o modificar una tabla de intervalos orbitar de llamadas en Skype empresarial Server Enterprise Voice.
ms.openlocfilehash: a5df3b61baf66a09bf968daf5c088e1c2ebf5734
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41767903"
---
# <a name="create-or-modify-a-call-park-orbit-range-in-skype-for-business"></a>Crear o modificar un intervalo de llamada de Parque orbital en Skype empresarial

Crear o modificar una tabla de intervalos orbitar de llamadas en Skype empresarial Server Enterprise Voice.

El parque de llamadas usa órbitas para hacer llamadas de aparcamiento. Para que los usuarios puedan detener y recuperar llamadas, debe configurar la tabla de llamadas de la órbita de estacionamiento. Debe especificar los intervalos de números de extensión (órbitas) que la organización reservará para las llamadas de aparcamiento y definir la distribución de esos intervalos especificando qué grupo de estacionamiento de llamadas controla cada rango. A la hora de definir intervalos de órbitas, el objetivo es tener una cantidad suficiente de órbitas, de modo que ninguna de las órbitas vuelva a usarse en seguida; con todo, tampoco se deben tener demasiadas órbitas porque esto limitaría el número de extensiones disponibles para los usuarios u otros servicios. Puede crear varios intervalos órbitas de estacionamiento de llamadas para cada grupo de servidores de Skype empresarial en el que se implemente la aplicación de estacionamiento de llamadas. Cada intervalo de estacionamiento de llamadas debe tener un nombre único global y un conjunto único de extensiones.

> [!IMPORTANT]
> Un intervalo de órbitas suele estar formado por 100 órbitas o menos, pero puede ser mucho mayor, siempre que tenga menos de 10 000 órbitas (número máximo) por intervalo y que usted tenga menos de 50 000 órbitas por grupo de servidores. Si un intervalo es demasiado pequeño, las órbitas se volverán a usar con mayor rapidez.

Use bloques de extensiones virtuales (extensiones que no tengan asignado ningún usuario ni teléfono) para los intervalos de órbitas.

> [!NOTE]
> No se admite la asignación de números de marcación directa (hecho) como números en órbita en la tabla de llamadas en órbita de estacionamiento.

Use los siguientes procedimientos para crear o modificar un intervalo de órbitas de estacionamiento de llamadas.

### <a name="to-use-skype-for-business-server-control-panel-to-create-or-modify-a-range-of-numbers-for-parking-calls"></a>Para usar el panel de control de Skype empresarial Server para crear o modificar un intervalo de números para las llamadas de aparcamiento

1. Inicie sesión en el equipo como miembro del grupo RTCUniversalServerAdmins o como miembro del rol CsVoiceAdministrator, CsServerAdministrator o CsAdministrator. Para más información, consulte **Delegate Setup Permissions**.

2. Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Skype empresarial Server.

3. En la barra de navegación izquierda, haga clic en **Características de voz** y, a continuación, en **Estacionamiento de llamadas**.

4. En la página **Estacionamiento de llamadas**, siga uno de estos procedimientos:

   - Para crear un nuevo intervalo de órbitas, haga clic en **Nuevo**. En **Nombre**, escriba un nombre identificativo para este intervalo de números.

     > [!NOTE]
     > Una vez que haya confirmado el intervalo de órbitas para la base de datos, no podrá cambiar este nombre.

   - Para modificar un intervalo de órbitas existente, escriba todo o parte del nombre del intervalo de órbitas en el campo de búsqueda. En la lista de órbitas resultante, haga clic en la órbita que desee, seleccione **Editar** y, a continuación, haga clic en **Mostrar detalles**.

5. En el primer campo **Intervalo numérico**, escriba el número inicial del intervalo de extensiones para esta órbita de estacionamiento de llamadas y, en el segundo campo **Intervalo numérico**, escriba el número final del intervalo. Tenga en cuenta lo siguiente:

   - El número inicial del intervalo debe ser menor o igual al número final.

   - El valor del número inicial del intervalo debe tener la misma longitud que el número final.

   - El intervalo de órbitas debe ser único. Este intervalo no se puede superponer con ningún otro.

   - Si el intervalo de órbita comienza con el \* carácter o #, el intervalo debe ser mayor que 100.

   - Valores válidos: deben coincidir con la cadena de\\expresión regular ([* | #]? [ 1-9] \d{0,7}) | ([1-9] \d{0,8}). Esto significa que el valor debe ser una cadena que comienza con el \* carácter o # o un número 1 a 9 (el primer carácter no puede ser un cero). Si el primer carácter es \* o #, el siguiente carácter debe ser un número del 1 al 9 (no puede ser un cero). Los siguientes caracteres pueden ser del 0 al 9 hasta siete caracteres adicionales (por ejemplo, "#6000", "\*92000", "\*95551212" y "915551212"). Si el primer carácter no \* es o #, el primer carácter debe ser un número del 1 al 9 (no puede ser cero), seguido de hasta ocho caracteres, cada uno de los números del 0 al 9 (por ejemplo, "915551212", "41212", "300").

   - No debe tener más de 50 000 órbitas por grupo de servidores. Cada intervalo de órbitas normalmente está formado por 100 órbitas o menos, pero puede ser mucho mayor siempre que tenga menos de 10 000 órbitas. Por ejemplo, en lugar de especificar un número de inicio de "7000000" y un número de finalización de "8000000", piense en especificar un número de inicio de "7000000" y un número de finalización de "7000100".

6. En **FQDN del servidor de destino**, haga clic en el nombre de dominio completo (FQDN) o el identificador de servicio del servicio de aplicación que hospeda la aplicación de estacionamiento de llamadas. Todas las llamadas estacionadas en números del intervalo especificado por el número de inicio y el número de finalización de cada intervalo de órbitas se enrutarán a este servidor o grupo de servidores.

7. Haga clic en **Confirmar**.

### <a name="to-use-skype-for-business-server-management-shell-to-create-or-modify-a-range-of-numbers-for-parking-calls"></a>Para usar el shell de administración de Skype empresarial para crear o modificar un intervalo de números para las llamadas de aparcamiento

1. Inicie sesión en el equipo donde está instalado el shell de administración de Skype empresarial Server como miembro del grupo RTCUniversalServerAdmins o con los derechos de usuario necesarios, como se describe en **permisos de configuración de delegado**.

2. Inicie el Shell de administración de Skype Empresarial Server: haga clic en **Inicio**, **Todos los programas**, **Skype Empresarial Server 2015** y, después, en **Shell de administración de Skype Empresarial Server**.

3. Use **New-CsCallParkOrbit** para crear un nuevo intervalo de números de órbitas. Use **Set-CsCallParkOrbit** para modificar un intervalo de números de órbitas existente.

    En la línea de comandos, ejecute:

   ```powershell
   New-CsCallParkOrbit -Identity <name of orbit range> -NumberRangeStart <first number in orbit range> -NumberRangeEnd <last number in orbit range> -CallParkService <FQDN or service ID of the Application service that hosts the Call Park application>
   ```

    Por ejemplo:

   ```powershell
   New-CsCallParkOrbit -Identity "Redmond orbit 1" -NumberRangeStart 100 -NumberRangeEnd 199 -CallParkService redmond-applicationserver-1
   ```

    En el ejemplo siguiente se muestra cómo modificar los números de un intervalos de órbitas existente,

   ```powershell
   Set-CsCallParkOrbit -Identity "Redmond orbit 1" -NumberRangeStart 500 -NumberRangeEnd 699
   ```

## <a name="see-also"></a>Vea también

[Nuevo: CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/new-cscallparkorbit?view=skype-ps)

[Set-CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/set-cscallparkorbit?view=skype-ps)

[Eliminar un intervalo orbitar de llamada](https://technet.microsoft.com/library/85e9f916-062d-450d-ac0a-aeaefc0f7cdc.aspx)
